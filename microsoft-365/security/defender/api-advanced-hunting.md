---
title: Microsoft 365 Defender 헌팅 API
description: 고급 헌팅 API를 사용하여 고급 헌팅 Microsoft 365 Defender 방법을 배우기
keywords: 고급 헌팅, API, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2752de976329f3fbef047557e6a626afd05a520f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206640"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender 고급 헌팅 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

[고급 헌팅은](advanced-hunting-overview.md) 특수하게 생성되는 [](advanced-hunting-query-language.md) 쿼리를 사용하여 30일 동안의 이벤트 데이터를 검사하는 위협 헌팅 Microsoft 365 Defender. 고급 헌팅 쿼리를 사용하여 비정상적인 활동을 검사하고, 가능한 위협을 감지하고, 공격에 대응할 수 있습니다. 고급 헌팅 API를 사용하면 프로그래밍적으로 이벤트 데이터를 쿼리할 수 있습니다.

## <a name="quotas-and-resource-allocation"></a>할당량 및 리소스 할당

다음 조건은 모든 쿼리와 관련이 있습니다.

1. 쿼리는 지난 30일 동안의 데이터를 탐색하고 반환합니다.
2. 결과는 최대 100,000개 행을 반환할 수 있습니다.
3. 테넌트당 분당 최대 15통의 통화를 만들 수 있습니다.
4. 다음 15분 주기가 지날 때까지 테넌트가 100%에 도달하면 쿼리가 차단됩니다.
5. 단일 요청이 10분 이상 실행되는 경우 시간이 너무 까다로우며 오류가 반환됩니다.
6. HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다. 응답 본문을 읽고 도달한 제한을 이해합니다. 

> [!NOTE]
> 위에 나열된 모든 할당량(예: 분당 통화 수 15개)은 테넌트 크기당입니다. 이러한 할당량은 최소값입니다.

## <a name="permissions"></a>사용 권한

고급 헌팅 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Access the Microsoft 365 Defender Protection API를 참조합니다.](api-access.md)

사용 권한 유형 | 사용 권한 | 사용 권한 표시 이름
-|-|-
응용 프로그램 | AdvancedHunting.Read.All | 고급 쿼리 실행
위임(직장 또는 학교 계정) | AdvancedHunting.Read | 고급 쿼리 실행

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
>- 사용자에게 '데이터 보기' AD 역할이 필요합니다.
>- 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다.

## <a name="http-request"></a>HTTP 요청

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>요청 헤더

헤더 | 값
-|-
권한 부여 | Bearer {token} **참고: 필수**
Content-Type | application/json

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수 | 유형 | 설명
-|-|-
쿼리 | 텍스트 | 실행할 쿼리입니다. **참고: 필수**

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 `200 OK` 및 _QueryResponse_ 개체를 반환합니다.

응답 개체에는 세 가지 최상위 속성이 포함되어 있습니다.

1. 통계 - 쿼리 성능 통계 사전입니다.
2. Schema - 응답의 schema, 각 열에 Name-Type 쌍의 목록입니다.
3. 결과 - 고급 헌팅 이벤트 목록입니다.

## <a name="example"></a>예제

다음 예제에서는 사용자가 아래 쿼리를 보내고 , 및 가 포함된 API 응답 개체를 `Stats` `Schema` `Results` 수신합니다.

### <a name="query"></a>쿼리

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>응답 개체

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a>관련 문서

- [MICROSOFT 365 DEFENDER API에 액세스](api-access.md)
- [API 제한 및 라이선싱에 대해 자세히 알아보기](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
- [지능형 헌팅 개요](advanced-hunting-overview.md)

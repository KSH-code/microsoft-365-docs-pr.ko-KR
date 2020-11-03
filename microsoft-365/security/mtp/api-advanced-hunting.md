---
title: 고급 구하기 Api
description: Microsoft 365 Defender API를 사용 하 여 고급 구하기 쿼리를 실행 하는 방법에 대해 알아봅니다.
keywords: 고급 구하기, Api, api, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844035"
---
# <a name="advanced-hunting-apis"></a>고급 구하기 Api

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>제한 사항
1. 지난 30 일간의 데이터에 대해서만 쿼리를 실행할 수 있습니다.
2. 결과에는 최대 10만 행이 포함 됩니다.
3. 실행 횟수는 테 넌 트 당 초당 최대 10 개의 통화, 시간당 10 분의 실행 시간, 그리고 하루에 4 시간까지 실행할 수 있습니다.
4. 단일 요청의 최대 실행 시간은 10 분입니다.
5. 429 응답은 요청 수 또는 CPU로 인해 할당량 제한에 도달 하는 것을 나타냅니다. 또한 429 응답 본문은 할당량이 갱신 될 때 까지의 시간도 나타냅니다. 


## <a name="permissions"></a>권한
이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다. 사용 권한을 선택 하는 방법을 비롯 하 여 자세한 내용을 보려면 [Microsoft 365 Defender Api 액세스](api-access.md) 를 참조 하세요.

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   AdvancedHunting 모든 |  ' 고급 쿼리 실행 '
위임 됨 (회사 또는 학교 계정) | AdvancedHunting 읽기 | ' 고급 쿼리 실행 '

>[!Note]
> 사용자 자격 증명을 사용 하 여 토큰을 가져올 때:
>- 사용자에 게 ' View Data ' AD 역할이 있어야 합니다.
>- 장치 그룹 설정에 따라 사용자에 게 장치에 대 한 액세스 권한이 있어야 합니다.

## <a name="http-request"></a>HTTP 요청
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>요청 헤더

Header | 값 
:---|:---
권한 부여 | 전달자 {토큰}. **필수** 입니다.
Content-Type    | application/json

## <a name="request-body"></a>요청 본문
요청 본문에서 다음 매개 변수를 사용 하 여 JSON 개체를 제공 합니다.

매개 변수 | 유형    | 설명
:---|:---|:---
Query | 텍스트 |  실행할 쿼리입니다. **필수** 입니다.

## <a name="response"></a>응답
성공 하면이 메서드는 응답 본문에 200 OK 및 _Queryresponse_ 개체를 반환 합니다. <br><br>

Response 개체는 3 개의 부분으로 나뉩니다 (속성).<br>
1) ```Stats``` -성능 통계를 쿼리 합니다.<br>
2) ```Schema``` -응답의 스키마 이며, 각 열에 대 한 Name-Type 쌍 목록입니다. <br>
3) ```Results``` -고급 구하기 이벤트 목록입니다.

## <a name="example"></a>예제

요청이

다음은 요청의 예입니다.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

응답

다음은 응답의 예입니다.


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

## <a name="related-topic"></a>관련 항목
- [Microsoft 365 Defender Api 액세스](api-access.md)

---
title: 고급 헌팅 API
ms.reviewer: ''
description: 고급 헌팅 API를 사용하여 끝점용 Microsoft Defender에서 고급 쿼리를 실행하는 방법을 학습합니다. 제한 사항을 찾아 예제를 참조합니다.
keywords: api, 지원되는 api, 고급 헌팅, 쿼리
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 40487143ff18cedb76c9f3f33c52cab24687c282
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604372"
---
# <a name="advanced-hunting-api"></a>고급 헌팅 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>제한 사항

1. 지난 30일 동안의 데이터에 대한 쿼리만 실행할 수 있습니다.

2. 결과에는 최대 100,000개 행이 포함됩니다.

3. 실행 수는 테넌트당 제한됩니다.
   - API 호출: 분당 최대 45통, 시간당 최대 1500통
   - 실행 시간: 매시간 10분의 실행 시간 및 하루 3시간의 실행 시간입니다.

4. 단일 요청의 최대 실행 시간은 10분입니다.

5. 429 응답은 요청 수 또는 CPU에 의해 할당량 제한에 도달하는 경우를 나타내게 됩니다. 응답 본문을 읽고 도달한 제한을 이해합니다. 

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   AdvancedQuery.Read.All |    '고급 쿼리 실행'
위임(직장 또는 학교 계정) | AdvancedQuery.Read | '고급 쿼리 실행'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>- 사용자에게 '데이터 보기' AD 역할이 필요합니다.
>- 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>요청 헤더

머리글 | 값 
:---|:---
권한 부여 | Bearer {token}. **필수입니다**.
Content-Type    | application/json

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수 | 유형    | 설명
:---|:---|:---
Query | 텍스트 |  실행할 쿼리입니다. **필수입니다**.

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 200 OK 및 _QueryResponse_ 개체를 반환합니다.


## <a name="example"></a>예제

##### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a>응답

다음은 응답의 예입니다.

>[!NOTE]
>여기에 표시된 응답 개체는 표시가 까다로우면 자르기될 수 있습니다. 모든 속성은 실제 호출에서 반환됩니다.

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>관련 항목

- [끝점 API용 Microsoft Defender 소개](apis-intro.md)
- [포털에서 고급 헌팅](advanced-hunting-query-language.md)
- [PowerShell을 사용하는 지능형 헌팅](run-advanced-query-sample-powershell.md)

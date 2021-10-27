---
title: 표시기 가져오기 API
description: 끝점용 Microsoft Defender에서 지표 API의 가져오기 일괄 처리를 사용하는 방법을 학습합니다.
keywords: api, 지원되는 api, 제출, ti, 표시기, 업데이트
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: api
ms.openlocfilehash: 222659172b939587a74a2fd34deb53f6140f414b
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588367"
---
# <a name="import-indicators-api"></a>표시기 가져오기 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

표시기 엔터티의 일괄 [처리를 제출하거나](ti-indicator.md) 업데이트합니다.

IP에 대한 CIDR은 지원되지 않습니다.

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 30개 호출입니다.
2. 테넌트당 활성 표시기는 15,000개로 제한됩니다. [](ti-indicator.md)
3. 하나의 API 호출에 대한 최대 일괄 처리 크기는 500입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Ti.ReadWrite|'읽기 및 쓰기 표시기'
응용 프로그램|Ti.ReadWrite.All|'모든 지표 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Ti.ReadWrite|'읽기 및 쓰기 표시기'

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|문자열|Bearer {token}. **필수입니다**.
Content-Type|문자열|application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수|유형|설명
:---|:---|:---
지표|목록<[표시기](ti-indicator.md)>|표시기 [목록입니다.](ti-indicator.md) **필수**

## <a name="response"></a>응답

- 성공하면 이 메서드는 표시기당 가져오기 결과 목록이 있는 200 - 확인 응답 코드를 반환합니다. 아래 예제를 참조하세요.
- 성공하지 못하면 이 메서드는 400 - 잘못된 요청을 반환합니다. 잘못된 요청은 일반적으로 잘못된 본문을 나타냅니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>관련 항목

- [지표 관리](manage-indicators.md)

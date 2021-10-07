---
title: 제출 또는 업데이트 표시기 API
description: 제출 또는 업데이트 표시기 API를 사용하여 끝점용 Microsoft Defender에서 새 지표 엔터티를 제출하거나 업데이트하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 제출, ti, 표시기, 업데이트
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 299a6fff547c921dfdc02d4c23bfd8947b878875
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157881"
---
# <a name="submit-or-update-indicator-api"></a>제출 또는 업데이트 표시기 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

새 Indicator [엔터티를 제출하거나 업데이트합니다.](ti-indicator.md)

IP에 대한 CIDR은 지원되지 않습니다.

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.
2. 테넌트당 활성 표시기는 15,000개로 제한됩니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Ti.ReadWrite|'읽기 및 쓰기 표시기'
응용 프로그램|Ti.ReadWrite.All|'모든 지표 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Ti.ReadWrite|'읽기 및 쓰기 표시기'

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.
Content-Type|문자열|application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수|유형|설명
:---|:---|:---
indicatorValue|String|Indicator [엔터티의 ID입니다.](ti-indicator.md) **필수**
indicatorType|Enum|표시기 유형입니다. 가능한 값은 "FileSha1", "FileMd5", "CertificateThumbprint", "FileSha256", "IpAddress", "DomainName" 및 "Url"입니다. **필수**
조치|Enum|표시기가 조직에서 검색되는 경우 수행되는 작업입니다. 가능한 값은 "Alert", "Warn", "Block", "Audit, "BlockAndRemediate", "AlertAndBlock" 및 "Allowed"입니다. **필수**
application|String|표시기와 연결된 응용 프로그램입니다. 이 필드는 새 표시기에서만 작동합니다. 기존 표시기에서 값을 업데이트하지 않습니다. **옵션**
title|String|표시기 경고 제목입니다. **필수**
설명|String|표시기 설명입니다. **필수**
expirationTime|DateTimeOffset|표시기 만료 시간입니다. **선택**
심각도|Enum|표시기 심각도입니다. 가능한 값은 "Informational", "Low", "Medium" 및 "High"입니다. **옵션**
recommendedActions|String|TI 표시기 경고 권장 작업. **선택**
rbacGroupNames|String|콤보로 구분된 RBAC 그룹 이름 목록 표시기가 적용됩니다. **옵션**

## <a name="response"></a>응답

- 성공하면 이 메서드는 응답 본문에 200 - 확인 응답 코드와 생성/업데이트된 [Indicator](ti-indicator.md) 엔터티를 반환합니다.
- 성공하지 못하면 이 메서드는 400 - 잘못된 요청을 반환합니다. 잘못된 요청은 일반적으로 잘못된 본문을 나타냅니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>관련 항목

- [지표 관리](manage-indicators.md)

---
title: 표시기 리소스 유형
description: 엔터티 세부 정보를 지정하고 끝점용 Microsoft Defender를 사용하여 표시기 만료를 정의합니다.
keywords: api, 지원되는 api, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: b4ba3db32004eb9ce80e386d918e470d1361e404
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785633"
---
# <a name="indicator-resource-type"></a>표시기 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

- 포털에서 [](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) 해당 지표 페이지를 참조하세요.

메서드|반환 형식|설명
:---|:---|:---
[지표 목록](get-ti-indicators-collection.md)|[표시기](ti-indicator.md) 컬렉션|[표시기](ti-indicator.md) 엔터티를 나열합니다.
[지표 제출](post-ti-indicator.md)|[표시기](ti-indicator.md)|표시기 [엔터티를 제출하거나](ti-indicator.md) 업데이트합니다.
[표시기 가져오기](import-ti-indicators.md)|[표시기](ti-indicator.md) 컬렉션|표시기 [엔터티를 제출하거나](ti-indicator.md) 업데이트합니다.
[지표 삭제](delete-ti-indicator-by-id.md)|콘텐츠 없음|표시기 [엔터티를](ti-indicator.md) 삭제합니다.

## <a name="properties"></a>속성

속성|유형|설명
:---|:---|:---
id|문자열|Indicator [엔터티의 ID입니다.](ti-indicator.md)
indicatorValue|문자열|표시기 [값입니다.](ti-indicator.md)
indicatorType|Enum|표시기 유형입니다. 가능한 값은 "FileSha1", "FileSha256", "FileMd5", "CertificateThumbprint", "IpAddress", "DomainName" 및 "Url"입니다.
application|문자열|표시기와 연결된 응용 프로그램입니다.
조치|Enum|표시기가 조직에서 검색되는 경우 수행되는 작업입니다. 가능한 값은 "Warn", "Block", "Audit", "Alert", "AlertAndBlock", "BlockAndRemediate" 및 "Allowed"입니다.
|externalID|문자열|고객이 사용자 지정 상관 관계 요청에 제출할 수 있는 ID입니다.|
sourceType|Enum|사용자가 만든 표시기(예: 포털에서)의 경우 API를 통해 자동화된 응용 프로그램을 사용하여 제출한 경우 "사용자"입니다.
createdBySource|문자열|표시기를 제출한 사용자/응용 프로그램의 이름입니다.
createdBy|문자열|표시기를 제출한 사용자/응용 프로그램의 고유 ID입니다.
lastUpdatedBy|문자열|표시기를 마지막으로 업데이트한 사용자/응용 프로그램의 ID입니다.
creationTimeDateTimeUtc|DateTimeOffset|표시기를 만든 날짜 및 시간입니다.
expirationTime|DateTimeOffset|표시기 만료 시간입니다.
lastUpdateTime|DateTimeOffset|표시기가 마지막으로 업데이트된 시간입니다.
심각도|Enum|표시기 심각도입니다. 가능한 값은 "Informational", "Low", "Medium" 및 "High"입니다.
title|문자열|표시기 제목입니다.
description|문자열|표시기 설명입니다.
recommendedActions|문자열|표시기를 위한 권장 작업입니다.
rbacGroupNames|문자열 목록|표시기가 노출되어 활성 상태인 RBAC 장치 그룹 이름입니다. 모든 장치에 노출되는 경우 빈 목록입니다.
rbacGroupIds|문자열 목록|RBAC 장치 그룹 ID에서 표시기가 노출되어 활성 상태입니다. 모든 장치에 노출되는 경우 빈 목록입니다.
generateAlert|Enum|**True이면** 경고 생성이 필요하고 **False이면** 경고가 생성되지 않습니다.

## <a name="indicator-types"></a>표시기 유형

API에서 지원하는 표시기 작업 유형은 다음입니다.

- 허용됨
- 감사
- 차단
- BlockAndRemediate
- 경고(MCAS 전용)

응답 작업 유형에 대한 자세한 내용은 [지표 만들기를 참조하세요.](manage-indicators.md)

> [!Note]
>
> 이전 응답 작업(AlertAndBlock 및 Alert)은 2022년 1월까지 지원됩니다. 이 날짜 이후에는 모든 고객이 위에 나열된 작업 유형 중 하나를 사용해야 합니다.

## <a name="json-representation"></a>Json 표현

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```

---
title: SharePoint 온라인 최신 포털 사이트 제한
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: SharePoint 및 외부 끝점에 대한 통화 제한과 같은 SharePoint 성능 권장 사항에 대해 자세히 알아보습니다.
ms.openlocfilehash: 6d09af30f5bdc8866b44047771060ced86362565
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214192"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint 온라인 최신 포털 사이트 제한

이 문서에서는 온라인에서 최신 포털 사이트에 대한 성능 SharePoint 제공합니다. 이 문서의 지침을 사용하여 최신 포털 사이트 성능을 최적화하고 일반적인 성능 문제를 방지할 수 있습니다.

## <a name="performance-considerations-for-modern-portal-sites"></a>최신 포털 사이트에 대한 성능 고려 사항

성능 최적화의 관점에서 볼 때 최신 포털 사이트를 고유하게 만드는 몇 가지 특성이 있습니다. 온라인에서 공동 작업 사이트와 포털 사이트의 SharePoint 가장 큰 차이는 확장됩니다. 포털 사이트는 일반적으로 공동 작업 사이트보다 많은 수의 사용자에게 더 많은 페이지 보기를 제공해야 하며 더 많은 정적 콘텐츠를 포함하며 편집 가능한 리소스가 적을 수 있습니다. 또한 최신 사이트의 아키텍처는 페이지 렌더링 및 코드 실행과 관련된 대부분의 처리가 서버가 아닌 클라이언트에서 수행되는 클래식 사이트와 다릅니다.

최신 포털 사이트에 대한 성능 최적화는 주로 몇 가지 전반적인 목표에 중점을 두습니다.

- 각 사이트 페이지의 구성 요소의 총 크기 줄이기
- 이미지, 스타일시트 및 스크립트와 같은 일반적인 정적 파일의 호스팅을 오프로드하여 CDN
- 필요한 SharePoint 및 외부 끝점에 대한 호출 제한
- 동일한 콘텐츠에 대한 중복 요청 방지

이 문서의 많은 지침은 온라인에 대한 통화를 최소화하고 최적화하는 SharePoint 있습니다. 페이지가 로드될 때마다 반복적인 호출을 하면 변경되지 않은 경우에도 매시간 서비스에서 정보를 검색하기에 따라 사용자의 성능에 영향을 미치게 됩니다. 따라서 SharePoint 요청은 모든 사용자에 대해 공통되는 통화 또는 각 개별 사용자에 필요한 통화로 분류될 수 있습니다. 사용자 환경을 최적화하기 위해 이러한 두 통화 범주의 결과를 캐시해야 합니다.

>[!NOTE]
>SharePoint [](./page-diagnostics-for-spo.md) 온라인 사이트 페이지에서 특정 성능 메트릭을 분석하기 위한 시작점으로 SharePoint 진단 도구를 사용합니다.

## <a name="modern-portal-site-limits-and-recommendations"></a>최신 포털 사이트 제한 및 권장 사항

|**제한 유형**|**최대 권장 값**|**참고**|
|:-----|:-----|:-----|:-----|
|페이지 및 뉴스 항목  <br/> |사이트당 5,000개  <br/> |최신 포털 사이트의 페이지 및 뉴스 항목 수를 5,000개 미만으로 제한하는 것이 좋습니다.  <br/> |
|페이지의 웹 파트  <br/> |페이지당 20개  <br/> |Microsoft 웹 파트와 사용자 지정 웹 파트를 모두 포함하여 페이지당 총 웹 파트를 20개 이하로 사용하는 것이 좋습니다. <br/> 자세한 내용은 온라인 최신 사이트 페이지에서 웹 파트 SharePoint [최적화를 참조하세요.](modern-web-part-optimization.md)  <br/> |
|페이지의 동적 웹 파트  <br/> |페이지당 4개  <br/> |최신 데이터를 수집하기 위해 하나 이상의 쿼리를 SharePoint 동적 웹 파트는 페이지당 4개로 제한해야 합니다. 뉴스 _웹_ 파트는 동적 웹 파트의 예입니다. <br/> 자세한 내용은 온라인 최신 사이트 페이지에서 웹 파트 SharePoint [최적화를 참조하세요.](modern-web-part-optimization.md)    <br/> |
|보안 그룹  <br/> |사이트당 20개  <br/> |보안 그룹 수는 최신 포털 사이트에서 많은 쿼리의 규모에 영향을 미치게 됩니다. 사이트당 20개까지만 가능한 한 적은 수의 보안 그룹으로 제한하는 것이 좋습니다.  <br/> |
|사이트 탐색의 항목  <br/> |사이트당 100개  <br/> |사이트 탐색에 100개 미만의 항목을 추가하는 것이 좋습니다. 즉, 첫 탐색 컨트롤을 사용하는 것이 좋습니다.  <br/> 자세한 내용은 온라인 최신 사이트 페이지에서 페이지 [SharePoint 최적화를 참조하세요.](modern-page-weight-optimization.md) <br/> |
|최대 이미지 크기  <br/> |이미지당 300 Kb  <br/> |이미지 크기를 300kb 이상으로 제한하고 이미지, 스타일시트 및 스크립트를 호스팅하는 데 CDN 사용하는 것이 좋습니다. <br/>자세한 내용은 SharePoint [Online](modern-image-optimization.md) 최신 사이트 페이지에서 이미지 최적화 및 [Office 365 Content Delivery Network(CDN)를 SharePoint 참조하세요.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|편집 권한을 있는 사용자  <br/> |사이트당 사용자 200명  <br/> |SharePoint 포털 사이트는 콘텐츠를 보고 사용하는 데 최적화되어 있습니다. 포털의 편집 권한은 제한된 사용자 그룹으로 제한되어야 합니다. 편집 권한은 추가 컨트롤을 다운로드하므로 해당 사용자의 경우 속도가 느려지기 때문에 제한됩니다. 따라서 편집 권한이 있는 사용자의 수가 과도하면 전체 환경이 영향을 미치게 됩니다. <br/> |
|타사 iFrame  <br/> |페이지당 2개  <br/> |iFrame은 javascript, CSS 및 프레임워크 요소와 같은 모든 관련 콘텐츠를 포함하여 별도의 외부 페이지를 로드하기 때문에 예측할 수 없는 속도가 느립니다. iFrame을 사용해야 하는 경우 페이지당 수를 2 이하로 제한합니다.<br/> 자세한 내용은 온라인 최신 및 클래식 게시 [SharePoint 페이지에서 iFrame 최적화를 참조하세요.](modern-iframe-optimization.md) <br/> |
|UPA 서비스에 대한 호출  <br/> |시간당 사용자당 1명  <br/> |UPA(User Profile  Application) 서비스에 대한 요청당 호출을 걸지 않습니다. [Microsoft Graph API](/graph/call-api) 및 [PageContext를](/javascript/api/sp-page-context/pagecontext) 사용하여 사용자 정보를 쿼리할 수 있습니다.  <br/> UPA 서비스 호출이 필요한 경우 필요한 경우 단일 호출을 한 다음 동일한 세션에서 다시 사용할 수 있도록 정보를 캐시합니다. |
|Taxonomy Service에 대한 호출  <br/> |시간당 사용자당 5명  <br/> |세분화 서비스에 _대한_ 요청당 호출을 걸지 말아야 합니다. 세분화 서비스 호출이 필요한 경우 동일한 세션에서 다시 사용할 정보를 캐시합니다. <br/> 자세한 내용은 온라인 최신 및 클래식 게시 SharePoint 페이지에서 페이지 통화 [최적화를 참조하세요.](modern-page-call-optimization.md) <br/> |

## <a name="related-topics"></a>관련 항목

[정상 상태의 SharePoint 만들기](/sharepoint/portal-health)

[SharePoint Online 성능 조정](tune-sharepoint-online-performance.md)

[Office 365 성능 조정](tune-microsoft-365-performance.md)

[SharePoint Online 제한 사항](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[최신 SharePoint 환경의 성능](/sharepoint/modern-experience-performance)

[SharePoint Online 포털에 대한 성능 지침](/sharepoint/dev/solution-guidance/portal-performance)

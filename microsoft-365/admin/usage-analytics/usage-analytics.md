---
title: Microsoft 365 사용 현황 분석
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 77ff780d-ab19-4553-adea-09cb65ad0f1f
description: 조직에서 커뮤니케이션및 협업을 위해 Microsoft 365 서비스를 채택하는 방법에 대한 개요를 확인하세요.
ms.openlocfilehash: f641e2b99e2d61881eb86506a1770f4401cb98bc
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572336"
---
# <a name="microsoft-365-usage-analytics"></a>Microsoft 365 사용 현황 분석

Power BI 내의 Microsoft 365 사용 분석을 사용하여 조직이 Microsoft 365 내의 다양한 서비스를 채택하는 방법에 대한 통찰력을 얻을 수 있습니다. Microsoft 365 사용 데이터를 시각화하고 분석하고, 사용자 지정 보고서를 만들고, 조직 내에서 통찰력을 공유할 수 있습니다. 특정 지역 또는 부서가 Microsoft 365 사용하는 방식에 대한 통찰력을 얻을 수도 있습니다.
  
Microsoft 365 사용 분석은 지난 12개월 동안 의 제품 간 보기를 제공하고 여러 사전 빌드된 보고서를 포함하는 사전 빌드된 대시보드에 액세스할 수 있습니다. 각 보고서는 특정 사용 현황 정보를 제공합니다. 사용자 별 정보는 지난 전체 달력 달에 사용할 수 있습니다.
  
템플릿 앱에 권한을 부여하는 [데이터 모델에는](usage-analytics-data-model.md) Active Directory의 사용자 특성이 포함되어 있어 특정 보고서에서 피벗할 수 있습니다. 위치, 부서 및 조직에는 다음과 같은 Active Directory 속성이 포함됩니다. 
  
데이터 수집을 시작하려면 [Microsoft 365 사용 현황 분석을 사용하도록 설정](enable-usage-analytics.md)을 참조하세요. 
  
Microsoft 365 사용 분석에는 다음 섹션에 자세히 설명된 여러 보고서가 포함되어 있습니다. 

데이터 테이블을 선택하여 각 영역에 대한 자세한 보고서에 액세스할 수 있습니다. 사이트 하단의 탭을 선택하여 미리 빌드된 모든 보고서를 볼 수 있습니다. 자세한 지침은 보고서 [탐색 및 활용 및 보고서](navigate-and-utilize-reports.md) 사용자 [지정을](customize-reports.md)참조하십시오.

## <a name="executive-summary"></a>요약

요약은 비즈니스 채택, 사용, 이동성, 커뮤니케이션, 협업 및 스토리지 보고서를 위한 Microsoft 365 대한 높은 수준의 한눈에 볼 수 있으며 비즈니스 의사 결정자를 위한 것입니다. 활성화된 모든 사용자와 활성 상태인 사용자를 기반으로 일부 개별 서비스가 어떻게 사용되는지 에 대한 보기를 제공합니다. 보고서에 표시된 월의 모든 값은 최신 전체 월을 참조합니다. 

이 요약을 사용하면 Office 사용 패턴과 직원들이 협업하는 방법과 위치를 신속하게 이해할 수 있습니다.

![Microsoft 365 사용 집행 요약의 이미지.](../../media/office365usage-exec-summary.png)

## <a name="overview"></a>개요

Microsoft 365 개요 보고서에는 다음 보고서가 포함되어 있습니다. 보고서 페이지 상단의 탭을 선택하여 볼 수 있습니다. 보고서의 맨 위 섹션에 표시된 월의 모든 값은 최신 전체 월을 참조합니다.

- **입양** &ndash; 채택 동향에 대한 요약을 제공합니다. 이 섹션의 보고서를 사용하여 사용자가 Microsoft 365 채택한 방법과 개별 서비스의 전반적인 사용이 월에 어떻게 변경되었는지 알아봅니다. 사용자가 활성화되는 방법, 조직의 사용자가 적극적으로 Microsoft 365 사용하는 사용자 수, 사용자를 반품하는 사용자 수, 제품을 처음 사용하는 사용자 수를 확인할 수 있습니다.

- **사용 법** &ndash; 지난 12개월 동안 활성 사용자의 볼륨과 각 제품의 주요 활동에 대한 드릴다운 보기를 제공합니다. 이 섹션의 보고서를 사용하여 조직의 사람들이 Microsoft 365 사용하는 방법을 알아봅니다.

- **통신** &ndash; 조직의 사용자가 Teams, Yammer, 이메일 또는 Skype 통화를 사용하여 연락을 유지하는 것을 선호하는지 한눈에 알 수 있습니다. 직원 간에 통신 도구를 사용하는 패턴이 변경되었는지 확인할 수 있습니다. 

- **공동 작업** &ndash; 조직의 사람들이 OneDrive 및 SharePoint 사용하여 문서를 저장하고 서로 공동 작업을 하는 방법과 이러한 추세가 월에 어떻게 진화하는지 알아보십시오. 또한 내부적으로 또는 외부에서 공유되는 문서 수와 소유자 및 기타 공동 작업자에 의해 세분화된 SharePoint 사이트 또는 OneDrive 계정이 적극적으로 사용되고 있는지 확인할 수 있습니다.

- **Storage** &ndash; 이 보고서를 사용하여 사서함, OneDrive 및 SharePoint 사이트의 클라우드 저장소를 추적합니다.

- **이동성** &ndash; 사람들이 이메일, Teams, Skype 또는 Yammer 연결하는 데 사용하는 클라이언트와 장치를 추적합니다.

## <a name="activation-and-licensing"></a>활성화 및 라이선싱

활성화 및 라이센스 페이지는 활성화에 대한 보고서를 Microsoft 365 제공합니다. 즉, Office 앱을 다운로드하고 활성화한 사용자 수와 조직에서 할당된 라이선스 수입니다. 위쪽의 월값은 현재 월을 나타내며 메트릭은 월 초부터 현재 날짜까지 집계된 값을 반영합니다.

- **활성화** &ndash; 조직의 서비스 계획(예: 엔터프라이즈용 Microsoft 365 앱, Project 및 Visio) 활성화를 추적합니다. Office 라이선스를 보유한 각 사용자는 최대 5대의 장치에 제품을 설치할 수 있습니다. 이 섹션의 보고서를 사용하여 사용자가 앱을 설치한 장치를 Office 볼 수도 있습니다. 계획을 활성화하려면 사용자가 앱을 설치하고 계정으로 로그인해야 합니다.

- **라이선스** &ndash; 이 보고서에는 라이선스 유형에 대한 개요, 각 라이선스 유형에 할당된 사용자 수 및 매월 라이선스 할당 배포가 포함됩니다. 위쪽의 월값은 현재 월을 나타내며 메트릭은 월 초부터 현재 날짜까지 집계된 값을 반영합니다.

## <a name="product-usage"></a>제품 사용

이 보고서에는 Exchange, Microsoft 365 그룹, OneDrive, SharePoint, Skype, Teams 및 Yammer 포함한 각 Microsoft 365 서비스에 대한 별도의 보고서가 포함되어 있습니다. 각 보고서에는 총 활성화된 사용자 보고서, 사서함, 사이트, 그룹 및 계정과 같은 엔터티 수와 적절한 경우 활동 유형 보고서가 포함됩니다. 보고서의 맨 위 섹션에 표시된 월의 모든 값은 최신 전체 월을 참조합니다.

## <a name="user-activity"></a>사용자 활동

사용자 활동 보고서는 특정 개별 서비스에서 사용할 수 있습니다. 이러한 보고서는 Active Directory 특성과 결합된 사용자 수준 세부 사용 데이터를 제공합니다. 또한 부서 채택 보고서를 사용하면 Active Directory 특성으로 슬라이스하여 모든 개별 서비스에서 활성 사용자를 볼 수 있습니다. 모든 측정항목은 최신 한 달 동안 집계됩니다.

## <a name="faq"></a>FAQ

### <a name="is-this-template-app-going-to-be-available-through-purchase-or-will-it-be-free"></a>이 템플릿 앱은 구매를 통해 사용할 수 있을까요 아니면 무료일까요?

그것은 무료가 아닙니다, 당신은 Power BI Pro 라이센스가 필요합니다. 자세한 내용은 템플릿 앱을 설치, 사용자 지정 및 배포하기 위한 [필수 구성 사항을](/power-bi/service-template-apps-install-distribute#prerequisites) 참조하십시오.

대시보드를 다른 사용자와 공유하려면 공유 [대시보드 및 보고서에서](/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports)자세한 내용은 참조하세요.
### <a name="is-the-usage-summary-reports-reader-role-enough-to-view-the-usage-analytics"></a>사용 요약 보고서 판독기 역할이 사용 분석을 볼 수 있습니까?

사용 요약 보고서 리더 역할은 Microsoft 365 사용 분석에서 테넌트 수준 집계에만 액세스할 수 있습니다.  변경 관리 및 채택을 담당하지만 반드시 IT 관리자가 아닌 모든 사람에게 보고서 판독기 또는 사용 요약 보고서 리더 역할을 하는 것이 좋습니다.

### <a name="who-can-connect-to-microsoft-365-usage-analytics"></a>누가 Microsoft 365 사용 현황 분석에 연결할 수 있나요?

템플릿 앱에 대한 연결을 설정하려면 **글로벌 관리자,** **관리자 Exchange,** **관리자 비즈니스용 Skype 관리자,** **SharePoint 관리자,** **글로벌 리더** 또는 **보고서 리더가** 되어야 합니다. 자세한 내용은 [관리자 역할에 대해](../add-users/about-admin-roles.md) 참조하세요.

### <a name="who-can-customize-the-usage-analytics-reports"></a>Who 사용 분석 보고서를 사용자 지정할 수 있습니까?

템플릿 앱에 초기 연결을 만든 사용자만 보고서를 사용자 지정하거나 Power BI 웹 인터페이스에서 새 보고서를 만들 수 있습니다. [Microsoft 365 사용 분석에서 보고서 사용자 지정을](customize-reports.md) 참조하여 지침을 참조하십시오.

### <a name="can-i-only-customize-the-reports-from-the-power-bi-web-interface"></a>Power BI 웹 인터페이스에서 보고서만 사용자 지정할 수 있습니까?

Power BI 웹 인터페이스에서 보고서를 사용자 지정하는 것 외에도 사용자는 Power BI Desktop 사용하여 Microsoft 365 보고 서비스에 직접 연결하여 자체 보고서를 작성할 수도 있습니다.

### <a name="how-can-i-get-the-pbit-file-that-this-dashboard-is-associated-with"></a>이 대시보드가 연결된 pbit 파일을 어떻게 얻을 수 있습니까?

[Microsoft 다운로드 센터에서](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)pbit 파일에 액세스할 수 있습니다.

### <a name="who-can-view-the-dashboards-and-reports"></a>Who 대시보드 및 보고서를 볼 수 있습니까?

템플릿 앱에 연결한 경우 [공유 기능을](/power-bi/collaborate-share/service-share-dashboards)사용하여 다른 사용자와 공유할 수 있습니다. 라이선스Power BI 대시보드를 공유하는 사용자와 사용자 모두 Power BI Pro 또는 Power BI Premium 있어야 합니다.

### <a name="can-anyone-share-the-dashboard-or-does-it-have-to-be-the-person-who-connected-to-the-dashboard"></a>누구나 대시보드를 공유할 수 있습니까? 아니면 대시보드에 연결된 사용자여야 합니까?

대시보드를 공유할 때 사용자가 대시보드를 다른 사용자와 다시 공유할 수 있도록 허용할 수 있습니다. 공유 시 이 옵션을 설정할 수 있습니다.

### <a name="is-it-possible-to-work-on-and-customize-the-same-template-app-with-a-group-of-people"></a>사용자 그룹과 동일한 템플릿 앱을 작업하고 사용자 지정할 수 있습니까?

예. 관리자 그룹이 동일한 템플릿 앱에서 함께 작동하도록 하려면 Power BI 앱 작업 영역 기능을 활용하여 자세한 내용은 [대시보드 및 보고서를 어떻게 공동 작업하고 공유해야 합니까?](/power-bi/collaborate-share/service-how-to-collaborate-distribute-dashboards-reports) 

### <a name="for-which-timeframe-is-data-available"></a>얼마 동안 데이터를 사용할 수 있습니까?

보고서의 대부분은 지난 12개월 동안의 데이터를 표시합니다. 그러나 일부 차트에서는 다른 제품 및 보고서에 대한 데이터 수집이 서로 다른 시간에 시작되므로 전체 12개월 동안의 데이터를 사용할 수 없으므로 기록이 적을 수 있습니다. 모든 보고서는 결국 12 개월의 역사를 쌓을 것입니다. 사용자 수준 세부 정보를 표시하는 보고서에는 이전 전월의 데이터가 표시됩니다.

### <a name="what-data-is-included-in-the-template-app"></a>템플릿 앱에 포함된 데이터는 무엇입니까?

템플릿 앱의 데이터는 현재 활동 보고서에서 사용할 수 있는 동일한 활동 메트릭 집합을 [다룹니다.](../activity-reports/activity-reports.md) 보고서가 활동 보고서에 추가되면 향후 릴리스에서 템플릿 앱에 추가됩니다.

### <a name="how-does-the-data-in-the-template-app-differ-from-the-data-in-the-usage-reports"></a>템플릿 앱의 데이터는 사용 보고서의 데이터와 어떻게 다른가요?

템플릿 앱에 표시되는 기본 데이터는 Microsoft 365 관리 센터의 활동 보고서에 표시되는 데이터와 일치합니다. 주요 차이점은 템플릿 앱이 최대 12개월 동안 매월 데이터를 제공하는 동안 관리 센터 데이터를 지난 7/30/90/180일 동안 사용할 수 있다는 것입니다.

또한 템플릿 앱의 사용자 수준 세부 정보는 제품 라이선스를 할당하고 활동을 수행한 사용자가 지난 달에만 사용할 수 있습니다.

### <a name="when-should-i-use-the-template-app-and-when-the-usage-reports"></a>템플릿 앱은 언제 사용해야 하고 사용 이 보고서가 보고되나요?

[활동 보고서는](../activity-reports/activity-reports.md) Microsoft 365 사용 및 채택을 이해하는 좋은 출발점입니다. 템플릿 앱은 Microsoft 365 사용 데이터와 조직의 Active Directory 정보를 결합하고 관리자가 Power BI 시각적 분석 기능을 사용하여 데이터 집합을 분석할 수 있도록 합니다. 이를 통해 관리자는 Microsoft 365 사용 데이터를 시각화하고 분석할 뿐만 아니라 부서, 위치 등과 같은 Active Directory 속성으로 슬라이스할 수 있습니다. 또한 사용자 지정 보고서를 만들고 조직 내에서 인사이트를 공유할 수도 있습니다. 

### <a name="how-often-is-the-data-refreshed"></a>데이터가 얼마나 자주 새로 고침되나요? 

처음으로 템플릿 앱에 연결하면 이전 12개월 동안 자동으로 데이터로 채워집니다. 그런 다음 템플릿 앱 데이터가 매주 새로 고쳐집니다. 고객은 이 데이터를 사용하여 다른 업데이트 리듬이 요구되는 경우 새로 고침 일정을 수정하도록 선택할 수 있습니다.

백 엔드 Microsoft 365 서비스는 매일 데이터를 새로 고치고 현재 날짜로부터 5-8일 의 잠재 데이터를 제공합니다.

각 데이터 집합의 **콘텐츠 날짜** 열은 템플릿 앱에서 데이터의 새로 고침 날짜를 나타냅니다.

### <a name="how-is-an-active-user-defined"></a>활성 사용자는 어떻게 정의합니까?

활성 사용자의 정의는 활동 보고서에서 [활성 사용자의](../activity-reports/active-users.md) 정의와 동일합니다.

### <a name="what-sharepoint-site-collections-are-included-in-the-sharepoint-reports"></a>SharePoint 보고서에는 어떤 SharePoint 사이트 모음이 포함되어 있나요?

템플릿 앱의 현재 버전에는 SharePoint 팀 사이트 와 SharePoint 그룹 사이트의 파일 활동이 포함됩니다.

### <a name="which-groups-are-included-in-the-microsoft-365-groups-usage-report"></a>Microsoft 365 그룹 사용 보고서에 포함되는 그룹은 무엇입니까?

템플릿 앱의 현재 버전에는 Outlook 그룹, Yammer 그룹 및 SharePoint 그룹의 사용량이 포함됩니다. Microsoft Teams 또는 플래너와 관련된 그룹은 포함되지 않습니다.

### <a name="when-will-an-updated-version-of-the-template-app-become-available"></a>업데이트된 버전의 템플릿 앱을 언제 사용할 수 있습니까?

템플릿 앱의 주요 변경 사항은 새 보고서 또는 새 데이터가 포함될 수 있는 일년에 두 번 릴리스됩니다. 보고서의 사소한 변경 사항은 보다 자주 릴리스될 수 있습니다.

### <a name="is-it-possible-to-integrate-the-data-from-the-template-app-into-existing-solutions"></a>템플릿 앱의 데이터를 기존 솔루션에 통합할 수 있습니까? 

템플릿 앱의 데이터는 Microsoft 365 API(미리 보기)를 통해 검색할 수 있습니다. 그들이 생산에 발송 할 때 그들은 [마이크로 소프트 Graph 보고 API](https://go.microsoft.com/fwlink/p/?linkid=848843)내에서 병합됩니다. 

### <a name="are-there-plans-to-expand-the-template-app-to-show-usage-data-from-other-microsoft-products"></a>다른 Microsoft 제품의 사용 데이터를 표시하도록 템플릿 앱을 확장할 계획이 있습니까?

이는 향후 개선을 위해 고려됩니다. Microsoft 365 [로드맵에서](https://www.microsoft.com/microsoft-365/roadmap) 업데이트를 확인합니다.

### <a name="how-can-i-pivot-by-company-information-in-active-directory"></a>Active Directory에서 회사 정보를 활용하려면 어떻게 합니까?

회사 정보는 템플릿 앱의 Active Directory 필드 중 하나가 포함되어 있으며 제품 사용자 **활동** 보고서에서 미리 빌드된 필터로 볼 수 있습니다. UserState 테이블에서 열로 사용할 수 **있습니다.**

### <a name="is-it-possible-to-bring-in-additional-fields-from-active-directory"></a>Active Directory에서 추가 필드를 가져올 수 있나요?

이 데이터에 대한 추가 사용자 지정은 [Microsoft Graph 보고 API에](https://go.microsoft.com/fwlink/p/?linkid=848843) 연결하여 Azure Active Directory 추가 필드를 가져오고 데이터 집합에 참여하여 가능합니다. 

### <a name="is-it-possible-to-aggregate-the-information-in-the-template-app-across-multiple-subscriptions"></a>여러 구독에서 템플릿 앱의 정보를 집계할 수 있습니까?

이 때 템플릿 앱은 처음에 연결하는 데 사용된 자격 증명과 연결되기 때문에 단일 구독용입니다.

### <a name="is-it-possible-to-see-usage-by-plan-ie-e1-e3"></a>계획(예: E1, E3)으로 사용량을 볼 수 있습니까?

템플릿 앱에서 사용량은 제품 수준당 표시됩니다. 사용자에게 할당된 다양한 구독에 대한 데이터가 제공되지만 사용자에게 할당된 구독과 사용자 활동의 상관 관계를 제공할 수는 없습니다.

### <a name="is-it-possible-to-integrate-other-data-sets-into-the-template-app"></a>다른 데이터 세트를 템플릿 앱에 통합할 수 있습니까?

Power BI Desktop 사용하여 Microsoft 365 API(미리 보기)에 연결하여 템플릿 앱 데이터와 결합할 추가 데이터 원본을 가져올 수 있습니다.

자세한 내용은 [사용자 지정 문서를](customize-reports.md)참조하십시오.

### <a name="is-it-possible-to-see-the-top-users-reports-for-a-specific-timeframe"></a>특정 기간에 대한 "상위 사용자" 보고서를 볼 수 있습니까?

모든 사용자 수준 보고서에는 이전 달에 대한 집계된 데이터가 표시됩니다.

### <a name="will-the-template-app-be-localized"></a>템플릿 앱이 지역화되나요? 

현재 로드맵에 있지 않습니다.

### <a name="i-have-a-specific-question-about-the-data-im-seeing-for-my-organization-who-can-i-reach-out-to"></a>내 조직에 대해 표시되는 데이터에 대한 구체적인 질문이 있습니다. 누구에게 연락할 수 있나요?

관리자 센터 활동 개요 페이지에서 피드백 단추를 사용하거나 지원 [사례를](../../business-video/get-help-support.md) 열어 템플릿 앱에 대한 도움말을 얻을 수 있습니다. 

### <a name="how-can-partners-access-the-data"></a>파트너는 데이터에 어떻게 액세스할 수 있습니까?

파트너가 관리자 권한을 위임한 경우 고객을 대신하여 템플릿 앱에 연결할 수 있습니다.

### <a name="can-i-hide-identifiable-information-such-as-user-group-and-site-names-in-reports"></a>보고서에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보를 숨길 수 있습니까?

예, [수집된 데이터 익명으로 만들기를](enable-usage-analytics.md#make-the-collected-data-anonymous)참조하십시오.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 사용 현황 분석 사용](enable-usage-analytics.md)(문서)

[Microsoft 365 사용 분석(문서)에서 보고서를 탐색하고 활용합니다.](navigate-and-utilize-reports.md)

[Microsoft 365 사용 보고서](../../business-video/act-on-report.md) 검토(동영상)
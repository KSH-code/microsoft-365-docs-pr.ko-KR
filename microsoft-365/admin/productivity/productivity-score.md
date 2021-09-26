---
title: Microsoft 생산성 점수
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
description: Microsoft 생산성 점수가 사용자 및 기술 경험 측정값을 반영하는 방식을 알아보고 비슷한 크기의 조직과 비교해 보세요.
ms.openlocfilehash: 0c0d260ebea02d57e099c84acdbc8960d58f3638
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774174"
---
# <a name="microsoft-productivity-score"></a>Microsoft 생산성 점수 

생산성 점수는 조직이 Microsoft 365를 사용하는 방법과 이를 지원하는 기술 경험에 대한 통찰력을 통해 디지털 전환을 지원합니다. 조직의 점수는 직원 및 기술 경험의 측정값을 반영하며, 규모와 유사한 조직의 벤치마크와 비교할 수 있습니다.

이 점수는 다음과 같은 기능을 제공합니다.

- 디지털 변환 경로의 현재 위치를 확인하는 데 도움이 되는 **메트릭스** 입니다.
- **데이터에 대해** 를 표시하여 조직의 생산성 및 만족도를 개선할 수 있는 기회를 식별할 수 있도록 지원합니다.
- **권장 작업** 을(를) 통해 조직이 Microsoft 365 제품을 효율적으로 사용할 수 있도록 지원할 수 있습니다.

Microsoft는 두 가지 영역에서 메트릭, 인사이트 및 권장 사항을 제공합니다. 

- **사용자의 경험:** 컨텐츠 협업, 이동성, 커뮤니케이션, 모임 및 팀워크와 같은 Microsoft 365 범주를 사용하여 조직의 작동 방식을 수량화합니다.  

    언급된 각 범주에 대해, 우리는 공공 연구를 검토하여 조직 효과의 형태로 몇 가지 모범 사례와 관련 편익을 식별합니다. 예를 들어 Forrester 조사에 따르면 사용자가 첨부 파일을 전자 메일로 보내는 대신 클라우드에서 협업하고 콘텐츠를 공유할 때 일주일에 최대 100분을 절약할 수 있습니다. 또한 Microsoft는 조직에서 이러한 모범 사례를 사용하여 디지털 전환 과정의 현재 위치를 파악할 수 있도록 지원합니다. 

- **기술 경험:** 조직은 신뢰할 수 있고 성능이 우수한 기술과 Microsoft 365의 효율적인 사용에 의존합니다. [엔드포인트 분석](https://aka.ms/endpointanalytics)를 사용하면 하드웨어 및 소프트웨어의 성능 및 상태 문제로 인해 조직에 어떤 영향을 미칠 수 있는지 이해할 수 있습니다. Microsoft 365 앱 상태를 사용하면 조직의 장치에서 권장 채널에서 Microsoft 365 앱을 실행하고 있는지 여부를 파악할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

개요와 필수 구성 요소 세부 사항에 대한 자세한 내용은 [엔드포인트 분석이란](/mem/analytics/overview)을 참조하세요. Microsoft 365 네트워크 연결 인사이트에 대한 자세한 내용은 [네트워크 연결 개요](../../enterprise/microsoft-365-networking-overview.md)를 참조하세요.

사용자 경험 데이터의 경우 비즈니스용 Microsoft 365 또는 Office 365 enterprise 구독이 필요합니다. 테넌트에 대한 엔드포인트 분석 데이터의 경우 구독에 Microsoft Intune을 추가해야 합니다. Intune을 사용하면 장치와 앱을 관리하여 조직 데이터를 보호할 수 있습니다. Intune을 설치하면 Intune 환경에서 엔드포인트 분석을 켤 수 있습니다. Microsoft Intune에 대해 자세히 알아보려면 [Microsoft Intune 문서](/mem/intune/)를 확인하세요. 

> [!NOTE]
> 생산성 점수 기능을 사용하기 위해 Workplace Analytics에 대한 라이선스는 필요하지 않습니다.

생산성 점수는 Microsoft 365 관리 센터에서만 사용할 수 있으며 다음 역할 중 하나를 가진 IT 전문가만 액세스할 수 있습니다.  

- 전역 관리자
- Exchange 관리자
- SharePoint 관리자
- 비즈니스용 Skype 관리자
- Teams 관리자
- 전역 읽기 권한자
- 보고서 읽기 권한자
- 사용 현황 요약 보고서 읽기 권한자

> [!NOTE]
> 전역 관리자 역할이 있는 IT 전문가만 생산성 점수를 위해 테넌트에 등록하거나 옵트인할 수 있습니다.

생산성 점수를 위한 역할 기반 액세스 제어 모델을 통해 조직에서 Microsoft 365를 통해 조직 내 IT 전문가에게 역할을 유연하게 할당할 수 있습니다.

Microsoft는 개인의 프라이버시를 보호하기 위해 노력하고 있습니다. 이 [개인정보 보호 문서](privacy.md)에서는 조직의 IT 관리자로서 Microsoft 에서 사용자가 신뢰하는 바를 훼손하지 않으면서 정보를 작업할 수 있도록 하기 위해 Microsoft에서 제공하는 제어 기능에 대해 설명합니다.

**보고서** > **생산성 점수** 의 Microsoft 365 관리자 홈에서 경험에 액세스할 수 있습니다.
  
## <a name="how-the-score-is-calculated"></a>점수 계산 방법

생산성 점수는 사용자 및 기술 경험 범주에 대한 총 점수를 기준으로 합니다. 각 범주는 총 100포인트의 동등한 가중치를 가집니다. 가능한 최대 생산성 점수는 800점입니다.

### <a name="score-categories"></a>점수 범주 

- 커뮤니케이션(100포인트)
- 모임(100포인트)
- 콘텐츠 공동 작업(100포인트)
- 팀워크(100포인트)
- 이동성(100포인트)
- 엔드포인트 분석(100포인트)
- 네트워크 연결(100포인트)
- Microsoft 365 앱 상태(100포인트)
- **가능한 총 합계 = 800포인트**
 
각 점수 범주에서 Microsoft 365를 디지털 혁신으로 전환하는 과정에서 사용하는 방법에 대한 주요 지표를 수량화합니다. 주요 활동에 대한 28일 및 180일 뷰를 제공합니다. 또한 점수 계산에는 포함되지 않지만 해결할 수 있는 기본 사용량 통계 및 구성을 식별하는 데 중요한 지원 메트릭도 제공합니다.

### <a name="products-included-in-productivity-score"></a>생산성 점수에 포함된 제품 

생산성 점수는 Exchange, SharePoint, OneDrive, Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer 및 Skype의 데이터를 포함합니다.

조직의 점수는 매일 업데이트되며 지난 28일(현재 포함)에 완료된 사용자 작업을 반영합니다.

## <a name="interpreting-your-organizations-productivity-score"></a>조직의 생산성 점수 해석 

생산성 점수 홈페이지에는 조직의 총 점수, 점수 기록, 각 범주에 대한 주요 인사이트가 표시됩니다.

:::image type="content" source="../../media/prodscore-landing.png" alt-text="보고서의 생산성 점수 페이지.":::

**조직의 점수** 는 퍼센트 값과 포인트로 표시됩니다. 분자에서 자신의 점을 볼 수 있고 분모에서 가능한 최대 점을 볼 수 있습니다.

**피어 벤치마크** 를 사용하여 귀사와 비슷한 조직과 점수를 비교할 수 있습니다. 사용자 경험 범주의 피어 벤치마크는 유사한 조직 집합 내의 측정값 평균으로 계산됩니다. 조직 집합은 라이선스가 있는 사용자, 라이선스 유형, 산업, Microsoft 365 사용 기간 수가 유사한 귀하 지역의 조직으로 구성됩니다.

> [!NOTE]
> Microsoft는 내부 데이터를 사용해 조직이 매핑되는 업계를 결정합니다. 부모 조직 아래 테넌트는 부모 조직과 동일한 업계로 매핑됩니다. 조직은 업계 매핑을 보거나 수정할 수 없습니다.

엔드포인트 분석 피어 벤치마크에는 장치 시작 성능 및 모든 테넌트의 집계된 중간값 값을 기반으로 권장되는 소프트웨어 구성에 대한 대상이 포함됩니다.

네트워크 연결의 경우 권장되는 벤치마크는 80포인트입니다.

**점수 분석** 섹션에서는 사용자 및 기술 경험 영역별로 벤치마크와 함께 생산성 점수 분석을 제공합니다.

점수 기록에서는 지난 6개월 동안 각 범주의 점수가 어떻게 변했는지를 표시합니다.

**사용자 경험** 과 **기술 경험** 영역에는 해당 영역의 범주에 대한 주요 인사이트가 포함되어 있습니다. 각 범주를 선택하여 세부 인사이트를 확인할 수 있습니다.

## <a name="category-details-pages"></a>범주 세부 정보 페이지

각 범주 세부 정보 페이지에는 주요 인사이트와 지원 메트릭과 함께 조직에서 변경을 촉진하는 데 사용할 수 있는 관련 리서치 및 조치가 표시됩니다. 리서치는 각 범주에 대한 주요 인사이트의 중요성과 근거를 지원합니다. 자세한 정보는 [Forrester 보고서를 참조하세요](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2PBrb).

범주 세부 정보 페이지:
- [콘텐츠 공동 작업 – 사용자 환경](content-collaboration.md)
- [커뮤니케이션 – 사용자 환경](communication.md)
- [모임 – 사용자 환경](meetings.md)
- [이동성 – 사용자 환경](mobility.md)
- [팀워크 – 사용자 환경](teamwork.md)
- [Microsoft 365 Apps 상태 - 기술 경험](apps-health.md)
- [끝점 분석](/mem/analytics/productivity-score)

## <a name="business-continuity-special-report"></a>비즈니스 연속성 특별 보고서

비즈니스 연속성 보고서는 이 어려운 시기에 조직을 가이드하는 데 도움이 되는 모든 Microsoft 365 고객에게 제공되는 제한된 시간의 작업 공간 인텔리전스 보고서입니다.  

이 보고서는 조직이 다음을 이해하는 데 도움이 됩니다. 

- 원격 작업으로의 전환에 따라 협업과 통신이 어떻게 영향을 받는지 알아봅니다. 

- 사람들이 집에서 일하는 것에 적응함에 따라 일과 삶의 균형에 미치는 영향입니다. 

- 원격 모임이 효과적인 의사 결정을 지원하는지 여부를 나타냅니다.

[비즈니스 연속성 보고서에 대한 자세한 정보](/Workplace-Analytics/tutorials/bcrps)

[Microsoft Graph에 대한 자세한 정보](/graph/)

> [!NOTE]
> 또한 사용자는 [MyAnalytics 대시보드](/workplace-analytics/myanalytics/use/dashboard-2)에서 생산성 인사이트를 얻을 수 있는 옵션도 있습니다.


## <a name="we-want-to-hear-from-you"></a>의견을 보내 주세요.

생산성 점수와 개선할 수 있는 방법에 대한 아이디어를 공유하세요. 제품 내에서 **피드백** 섹션을 사용하거나 prodscorefeedback@microsoft.com의 Productivity Score 팀에 문의합니다.

## <a name="related-content"></a>관련 콘텐츠

[보고서를 이용하여 Microsoft 365 활동 모니터링](../../admin/activity-reports/activity-reports.md)(게시물)
[Microsoft 365 사용 현황 분석 사용](../../admin/usage-analytics/enable-usage-analytics.md)(게시물)
[Microsoft 365 관리 센터 개요](../../business-video/admin-center-overview.md)(동영상)
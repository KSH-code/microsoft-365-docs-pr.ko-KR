---
title: 가시성 및 인사이트 시작
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 가시성 및 인사이트를 시작합니다.
ms.openlocfilehash: 12c1a01667b1bda545b619e931d99132e6611e35
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420269"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="52235-103">가시성 및 인사이트 시작</span><span class="sxs-lookup"><span data-stu-id="52235-103">Get started with visibility and insights</span></span>

><span data-ttu-id="52235-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="52235-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="52235-105">가장 먼저 시작할 곳은 [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance)의 앱 거버넌스 대시보드입니다.</span><span class="sxs-lookup"><span data-stu-id="52235-105">The first place to get started is the app governance dashboard at [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="52235-106">앱 거버넌스 데이터를 보려면 로그인 계정에 [이와 같은 앱 거버넌스 관리자 역할 ](app-governance-get-started.md#administrator-roles) 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52235-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Microsoft 365 준수 센터의 앱 거버넌스 개요 페이지](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="52235-108">**Microsoft 365 관리 센터 > Microsoft 365 준수 센터 > 앱 거버넌스 > 개요 페이지** 에서 앱 거버넌스 대시보드에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52235-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="52235-109">대시보드에서 사용할 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="52235-109">What’s available on the dashboard</span></span>

<span data-ttu-id="52235-110">대시보드에는 테넌트에서 Microsoft 365 앱 에코시스템의 구성 요소에 대한 요약이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52235-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="52235-111">**테넌트 요약**: 주요 앱 및 경고 범주의 수</span><span class="sxs-lookup"><span data-stu-id="52235-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="52235-112">**검색 및 정책 경고**: 테넌트에서 가장 최근의 활성 경고</span><span class="sxs-lookup"><span data-stu-id="52235-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="52235-113">**데이터 및 리소스 액세스**: 테넌트에서 상위 리소스의 전체 사용량 및 애플리케이션 API 액세스를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="52235-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="52235-114">그래프의 매월 열을 마우스로 클릭하여 해당 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="52235-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="52235-115">**앱 보호 및 거버넌스 개선**: 앱 사용 또는 권한 정책 만들기와 같은 권장 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="52235-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="52235-116">**범주별 상위 앱**: 다음 범주별로 정렬된 상위 앱:</span><span class="sxs-lookup"><span data-stu-id="52235-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="52235-117">**모든 범주**: 사용 가능한 모든 범주를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="52235-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="52235-118">**높은 권한**: 높은 권한은 플랫폼 기계 학습 및 신호를 기반으로 내부적으로 결정되는 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="52235-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="52235-119">**과도한 권한 부여**: 앱 거버넌스가 지난 90일 동안 애플리케이션에 부여된 사용 권한이 사용되지 않았음을 나타내는 원격 분석을 수신하면 해당 애플리케이션에 과도한 권한이 부여되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52235-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="52235-120">앱 거버넌스가 90일 이상 작동하여 앱이 초과 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52235-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="52235-121">**확인되지 않음**: [게시자 인증](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview)을 받지 못한 응용 프로그램은 확인되지 않은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="52235-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="52235-122">**앱만 해당**: [애플리케이션 사용 권한](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types)은 로그인한 사용자 없이 실행할 수 있는 앱에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52235-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="52235-123">테넌트 전체에서 데이터에 액세스할 수 있는 권한이 있는 앱은 잠재적으로 더 높은 위험 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="52235-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="52235-124">**새 앱**: 지난 7일 동안 등록된 새 Microsoft 365 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="52235-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="52235-125">다음 단계</span><span class="sxs-lookup"><span data-stu-id="52235-125">Next step</span></span>

<span data-ttu-id="52235-126">[특정 앱에 대한 자세한 인사이트를 가져옵니다](app-governance-visibility-insights-view-apps.md).</span><span class="sxs-lookup"><span data-stu-id="52235-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>

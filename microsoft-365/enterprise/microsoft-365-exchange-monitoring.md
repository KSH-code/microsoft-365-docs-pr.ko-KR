---
title: Microsoft 365의 Exchange Online 모니터링
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Microsoft 365의 메일 인시던트 또는 권고에 대한 자세한 내용은 Exchange Online 모니터링을 사용하세요.
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286444"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="08428-103">Microsoft 365의 Exchange Online 모니터링</span><span class="sxs-lookup"><span data-stu-id="08428-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="08428-104">Microsoft 365 관리 센터에서 Exchange Online 모니터링을 사용하여 조직의 Microsoft 365 구독에 대한 Exchange 서비스의 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="08428-105">Exchange Online 모니터링에서는 다음 범주에서 수집되는 인시던트와 권고에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="08428-106">**인프라**: Microsoft에서 정기 업데이트와 문제 해결을 위해 보유하고 있는 Microsoft 365 인프라에서 문제가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="08428-107">예를 들어, Exchange 또는 기타 Microsoft 365 클라우드 인프라에 발생한 문제로 인해 Exchange Online에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="08428-108">**타사 인프라**: 조직이 하위 항목을 보유하는 타사 인프라에서 문제가 발견되었고 해결하려면 조직의 조치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="08428-109">예를 들어, 사용자 인증 거래는 사용자가 Exchange Online에 연결하는 것을 차단하는 타사 STS(보안 토큰 서비스) 공급자에 의해 제한을 받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="08428-110">**고객 인프라**: 조직 인프라에서 문제가 발견되었고 해결하려면 조직의 조치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="08428-111">예를 들어, 만료된 인증서로 인해 사용자가 조직에서 호스트하는 STS 공급자로부터 인증 토큰을 받을 수 없으므로 Exchange Online에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="08428-112">다음은 Microsoft 365 관리 센터에서 **서비스 상태** 페이지에 대한 예이며, **상태 > 서비스 상태** 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Microsoft 365 관리 센터의 서비스 상태 페이지](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="08428-114">**상태** 열의 값은 서비스가 정상인지를 나타내고 Microsoft에서 유지 관리하는 클라우드 서비스를 기반으로 권고나 인시던트를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="08428-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="08428-115">**조직 및 타사 문제점** 열의 값은 조직의 인프라 또는 타사 소프트웨어에서 Exchange Online을 사용하여 사용자의 서비스 상태 환경에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08428-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="08428-116">권고나 인시던트를 해결하려면 *사용자의 조치* 가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="08428-117">다음은 Microsoft 365 관리 센터에서 **Exchange Online** 모니터링 페이지에 대한 예이며, **상태 > 서비스 상태 > Exchange Online** 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Microsoft 365 관리 센터의 Exchange Online 모니터링 페이지](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="08428-119">**Exchange Online** 모니터링 페이지를 사용하여 Exchange Online 서비스가 정상인지 여부를 확인하고 연결된 인시던트나 권고 사항이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="08428-120">Exchange Online 모니터링을 사용하여 특정 메일 시나리오에 대한 서비스 상태를 확인하고 거의 실시간 신호를 보고 시나리오의 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="08428-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08428-121">Requirements</span></span>

<span data-ttu-id="08428-122">다음 요구 사항을 충족하는 고객은 해당 미리 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="08428-123">조직에서는 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5 제품 중 하나 또는 조합에서 최소 5,000개의 라이선스를 보유하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="08428-124">예를 들어 조직에서는 적격 제품 총 5,500개의 라이센스에 대해 3,000개의 Office 365 E3 라이선스 및 2,500개의 Microsoft 365 E5 라이선스를 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="08428-125">조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="08428-126">Exchange Online 모니터링을 사용하여 메일 읽기 활동을 기반으로 다음 메일 클라이언트의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="08428-127">Outlook 데스크톱</span><span class="sxs-lookup"><span data-stu-id="08428-127">Outlook Desktop</span></span>
- <span data-ttu-id="08428-128">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="08428-128">Outlook on the Web</span></span>
- <span data-ttu-id="08428-129">IOS 및 Android의 기본 메일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="08428-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="08428-130">IOS 및 Android의 Outlook Mobile 앱</span><span class="sxs-lookup"><span data-stu-id="08428-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="08428-131">Outlook Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="08428-131">Outlook Mac client</span></span>

<span data-ttu-id="08428-132">해당 클라이언트의 경우, 대시보드에서 인시던트와 권고 수와 함께, 메일을 읽는 사용자를 기반으로 지난 30분 동안의 활성 사용자 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="08428-133">지난 주에 대해 동일한 간격으로 이 데이터를 비교하여 문제가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="08428-134">활성 사용자 수는 단일 활동(예: 사용자가 메일을 읽는 경우)으로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="08428-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="08428-135">지난 30분 동안의 활동만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="08428-136">다음과 같은 경우에도 Exchange Online 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="08428-137">**메일 흐름**: 메시지가 Microsoft 365 네트워크에 연결된 후 지연 없이 사서함에 성공적으로 전달되는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08428-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="08428-138">**기본 인증 및 최신 인증**: Exchange Online 서비스에서 성공적으로 유효성 검사된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08428-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![메일 전달에 대한 Exchange 상태 모니터링의 예](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="08428-140">모든 관련 시나리오의 경우, 주요 숫자는 주 대시보드의 마지막 30분에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08428-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="08428-141">각 시나리오에 대한 자세한 보기에서는 이전 주와 비교한 30분 집계를 사용하여 7일에 대한 거의 실시간 추세를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08428-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="08428-142">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="08428-142">Send us feedback</span></span>

<span data-ttu-id="08428-143">다음과 같은 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="08428-144">Microsoft 365 관리 센터의 모든 페이지에서 **의견 보내기** 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="08428-145">특정 인시던트나 권고에 **이 게시물이 유용한가요?** 링크를 사용하여 의견 제출</span><span class="sxs-lookup"><span data-stu-id="08428-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![“이 게시물이 유용한가요?”](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="08428-148">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="08428-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="08428-149">1. Microsoft 365 관리 센터의 상태 아래에 "Exchange Online 모니터링"이 표시되지 않는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="08428-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="08428-150">먼저 Microsoft 365 관리 센터의 **홈** 페이지에서 새 관리 센터를 사용하도록 설정했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="08428-151">그런 후, 다음 요구 사항을 모두 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="08428-152">조직에서는 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5 제품 중 하나 또는 조합에서 최소 5,000개의 라이선스를 보유하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="08428-153">조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="08428-154">조직의 라이선스 수가 5,000명 미만이고 월간 활성 사용자가 50명 미만인 경우, 해당 요구 사항이 충족될 때까지 Exchange Online 모니터링을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="08428-155">2. 각 클라이언트에 대한 대시보드의 활성 사용자 수가 낮은 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08428-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="08428-156">사용자에게 많은 활성 라이선스가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="08428-157">시나리오</span><span class="sxs-lookup"><span data-stu-id="08428-157">What does this mean?</span></span> 

<span data-ttu-id="08428-158">모니터링에 표시되는 활성 사용자 수는 기능에서 호출한 활동을 수행한 30분 창을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="08428-159">이 수치와 사용량 수치를 혼동해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08428-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="08428-160">사용량 수치를 보려면 Microsoft 365 관리 센터에서 활동 보고서 **(보고서 > 사용**)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="08428-161">3. Teams 및 SharePoint와 같은 기타 서비스에 대한 다른 모니터링 시나리오가 있나요?</span><span class="sxs-lookup"><span data-stu-id="08428-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="08428-162">Microsoft에서 Microsoft 365 관리 센터의 서비스 상태 대시보드 내부에서 이 환경을 바로 통합했습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="08428-163">이를 통해 Microsoft에서 다른 서비스에 대한 모니터링 시나리오를 확장할 수 있는 기회를 갖게 됩니다. 이 기능은 공유할 뉴스가 있을 경우 발표될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="08428-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="08428-164">4 .이 환경의 출시 계획은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="08428-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="08428-165">Microsoft에서 Microsoft 365 관리 센터의 **서비스 상태** 대시보드 내부에서 Exchange Online 모니터링을 바로 통합했습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="08428-166">새로운 통합 환경에서 Microsoft의 계획은 사용자 의견을 수집하고 출시 계획을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08428-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="08428-167">5. 이 기능은 무료(포함)인가요? 무료(추가)인가요?</span><span class="sxs-lookup"><span data-stu-id="08428-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="08428-168">이 기능은 공개 미리 보기 상태이며 질문 1에 있는 요구 사항을 충족하는 고객만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08428-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="08428-169">6. 사용자 의견을 제공하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="08428-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="08428-170">일반적인 사용자 의견을 보려면 **Exchange Online** 모니터링 페이지의 오른쪽 아래 모서리에 있는 **의견 보내기** 아이콘을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="08428-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="08428-171">인시던트나 권고에 대한 의견을 보려면 **이 게시물이 유용한가요?** 링크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="08428-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="08428-172">7. 활동 경향을 보여주는 시나리오의 데이터는 어디에서 측정됩니까?</span><span class="sxs-lookup"><span data-stu-id="08428-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="08428-p114">데이터는 Exchange Online 서비스에서 계측됩니다. 요청이 Exchange Online에 도달하기 전에 오류가 발생하거나 Exchange Online에서 오류가 발생한 경우 작업 신호가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="08428-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

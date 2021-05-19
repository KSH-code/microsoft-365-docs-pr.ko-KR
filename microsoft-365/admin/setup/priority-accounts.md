---
title: 우선 순위 계정 관리 및 모니터링
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: 비즈니스에 큰 영향을 미치는 계정으로 보내거나 보낸 전자 메일로 전송된 실패 및 지연된 전자 메일 메시지를 모니터링합니다.
ms.openlocfilehash: 2a58f4090244fc6d68be69cf6b3c8ab6e00874fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535809"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="ca15b-103">우선 순위 계정 관리 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="ca15b-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="ca15b-104">모든 Microsoft 365 조직에는 중요한 정보, 소유 정보 또는 높은 우선 순위 정보에 액세스할 수 있는 임원, 리더, 관리자 또는 기타 사용자와 같이 필수적인 사람이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="ca15b-105">조직에서 이러한 계정을 보호할 수 있도록 이제 특정 사용자를 우선 순위 계정으로 지정하고 추가 보호를 제공하는 앱별 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="ca15b-106">앞으로 더 많은 앱 및 기능이 우선 순위 계정을 지원할 예정으로, 우선  순위 계정 보호 및 프리미엄 메일 흐름 모니터링의 두 가지 기능을 **발표했습니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="ca15b-107">**우선** 순위 계정 보호 - Microsoft Defender for Office 365(Office 365 Advanced Threat Protection)는 경고, 보고서 및 조사에서 필터에 사용할 수 있는 태그로 우선 순위 계정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="ca15b-108">자세한 내용은 에 대한 [Microsoft Defender의 사용자 태그를 Office 365.](../../security/office-365-security/user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ca15b-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="ca15b-109">"모든 사용자가 우선 순위가 아닌가요?</span><span class="sxs-lookup"><span data-stu-id="ca15b-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="ca15b-110">모든 사용자를 우선 순위 계정으로 지정하지 않는 이유는 무엇일까요?"</span><span class="sxs-lookup"><span data-stu-id="ca15b-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="ca15b-111">예, 모든 사용자가 우선 순위이지만 우선 순위 계정 보호는 다음과 같은 추가 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="ca15b-112">**추가추가:** Microsoft 데이터 센터에서 메일 흐름을 분석하면 회사 임원의 메일 흐름 패턴이 평균 직원과 다르다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="ca15b-113">우선 순위 계정 보호는 정규 직원에게 도움이되지 않는 회사 임원에게 특별히 조정된 추가적 이론을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="ca15b-114">**보고의** 추가 표시 여부: 모든 사용자(또는 영향을 받는 모든 사용자)에 대한 정보는 경고, 보고서 및 조사에서 이미 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="ca15b-115">우선 순위 계정 태그를 필터로 사용하면 특별히 조사 대상을 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="ca15b-116">**Premium 메일** Flow 모니터링 - 정상 메일 흐름은 비즈니스 성공에 중요할 수 있으며 배달 지연 또는 오류는 비즈니스에 부정적인 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="ca15b-117">실패 또는 지연된 전자 메일에 대한 임계값을 선택하고, 해당 임계값을 초과하면 경고를 수신하고, 우선 순위 계정에 대한 전자 메일 문제에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="ca15b-118">자세한 내용은 최신 [EAC에서](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) 우선 순위 계정 보고서에 대한 전자 메일 문제 확인</span><span class="sxs-lookup"><span data-stu-id="ca15b-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="ca15b-119">우선 순위 계정에 대한 보안 모범 사례는 우선 순위 계정에 [대한 보안 권장 사항을 참조하세요.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="ca15b-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ca15b-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="ca15b-120">Before you begin</span></span>

<span data-ttu-id="ca15b-121">이 **항목에 설명된** 우선 순위 계정 보호 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="ca15b-122">Microsoft Defender for Office 365 요금제 2에는 E3, Office 365 E5, Office 365, Microsoft 365 E5 또는 Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="ca15b-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="ca15b-123">이 **Premium 메일** Flow 모니터링 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="ca15b-124">조직에 라이선스 수가 10,000개 이상(예: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ca15b-124">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="ca15b-125">예를 들어 조직에는 3,000개 Office 365 E3 라이선스와 8500개 Microsoft 365 E5 수 있으며, 적격 제품의 총 라이선스 수가 11,500개일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-125">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="ca15b-126">조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="ca15b-127">최대 250개 우선 순위 계정을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="ca15b-128">사서함에 우선 순위 계정 보호를 적용할 때 사서함에 액세스할 수 있는 사용자(예: CEO 및 CEO의 일정을 관리하는 CEO의 임원 비서)에도 우선 순위 계정 보호를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="ca15b-129">설치 페이지에서 우선 순위 계정 추가</span><span class="sxs-lookup"><span data-stu-id="ca15b-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="ca15b-130">설치 페이지에서 우선 순위 **계정을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="ca15b-131">에서 Microsoft 365 관리 센터로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="ca15b-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ca15b-132">조직 정보  >  **설정으로 이동하여** **가장** 중요한 계정 **모니터링에서 보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="ca15b-133">선택 **시작** 또는 **관리 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="ca15b-134">우선 **순위** 계정 추가 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름 또는 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="ca15b-135">실패하거나 지연된 전자 메일에 대한 전자 메일 임계값을 설정하고 우선 순위 계정에 대한 문제에 대한 주간 보고서를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="ca15b-136">사용자를 선택하고 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="ca15b-137">활성 사용자 페이지에서 우선 순위 계정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="ca15b-138">활성 사용자 페이지에서 우선 순위 계정 추가</span><span class="sxs-lookup"><span data-stu-id="ca15b-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="ca15b-139">활성 사용자 페이지에서 우선 순위 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="ca15b-140"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ca15b-141">사용자 활성 **사용자로** 이동하여 페이지 맨 위에 있는 세 개의 점(추가 작업)을  >   선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="ca15b-142">우선 **순위 계정 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="ca15b-143">계정 **추가를** 선택하고 우선 순위 계정 추가 **페이지의** 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15b-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="ca15b-144">사용자를 선택하고 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="ca15b-145">우선 순위 계정 목록에서 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="ca15b-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="ca15b-146">에서 Microsoft 365 관리 센터로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="ca15b-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ca15b-147">조직 정보  >  **설정으로 이동하여** **가장** 중요한 계정 **모니터링에서 보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="ca15b-148">On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature**.</span><span class="sxs-lookup"><span data-stu-id="ca15b-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="ca15b-149">우선 **순위 계정** 페이지에서 목록에서 제거할 사용자를 선택하고 계정 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca15b-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca15b-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ca15b-150">Related topics</span></span>

[<span data-ttu-id="ca15b-151">2016에서 우선 순위 계정 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca15b-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)

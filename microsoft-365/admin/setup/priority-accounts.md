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
description: 비즈니스에 큰 영향을 미치는 계정으로 보내거나 보낸 실패 및 지연된 전자 메일 메시지를 모니터링합니다.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477616"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="004aa-103">우선 순위 계정 관리 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="004aa-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="004aa-104">모든 Microsoft 365 조직에는 중요한 정보, 소유 정보 또는 높은 우선 순위 정보에 액세스할 수 있는 임원, 리더, 관리자 또는 기타 사용자와 같이 필수적인 사람이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="004aa-105">조직에서 이러한 계정을 보호하도록 지원하기 위해 이제 특정 사용자를 우선 순위 계정으로 지정하고 추가 보호를 제공하는 앱별 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="004aa-106">앞으로 더 많은 앱 및 기능이 우선 순위 계정을 지원할 예정으로, 우선  순위 계정 보호 및 프리미엄 메일 흐름 모니터링의 두 가지 기능을 **발표했습니다.**</span><span class="sxs-lookup"><span data-stu-id="004aa-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="004aa-107">**우선 순위** 계정 보호 - Office 365용 Microsoft Defender(이전의 Office 365 Advanced Threat Protection)는 경고, 보고서 및 조사에서 필터에 사용할 수 있는 태그로 우선 순위 계정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="004aa-108">자세한 내용은 Microsoft [Defender for Office 365에서 사용자 태그를 확인하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="004aa-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="004aa-109">**고급 메일 흐름 모니터링** - 정상 메일 흐름은 비즈니스 성공에 중요할 수 있으며, 배달 지연 또는 오류는 비즈니스에 부정적인 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="004aa-110">실패 또는 지연된 전자 메일에 대한 임계값을 선택하고, 임계값을 초과하면 경고를 수신하고, 우선 순위 계정에 대한 전자 메일 문제 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="004aa-111">자세한 내용은 최신 [EAC에서](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)우선 순위 계정 보고서에 대한 전자 메일 문제를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="004aa-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="004aa-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="004aa-112">Before you begin</span></span>

<span data-ttu-id="004aa-113">이 **항목에 설명된** 우선 순위 계정 보호 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="004aa-114">Office 365 E3, Office 365 E5, Microsoft 365 E5 또는 Microsoft 365 E5 보안이 있는 Microsoft Defender를 포함하여 Office 365 계획 2용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="004aa-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="004aa-115">이 **항목에 설명된** 고급 메일 흐름 모니터링 기능은 다음 요구 사항을 충족하는 조직에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="004aa-116">조직은 Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5 중 하나 또는 제품의 조합에서 최소 10,000개 이상의 라이선스 수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="004aa-117">예를 들어 조직에서는 Office 365 E3 라이선스 3,000개와 Microsoft 365 E5 8500을 사용할 수 있으며 적격 제품의 라이선스는 총 11,500개입니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="004aa-118">조직에는 매월 최소 50명의 활성 Exchange Online 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="004aa-119">우선 순위 계정을 250개까지 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="004aa-120">설치 페이지에서 우선 순위 계정 추가</span><span class="sxs-lookup"><span data-stu-id="004aa-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="004aa-121">설치 페이지에서 우선 순위 계정을 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="004aa-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="004aa-122">Microsoft 365 관리 센터로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="004aa-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="004aa-123">조직 지식 **설정으로** 이동한 후 가장 중요한 계정 모니터링에서  >   **보기를 선택하십시오.** </span><span class="sxs-lookup"><span data-stu-id="004aa-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="004aa-124">시작 **또는** **관리** 선택 .</span><span class="sxs-lookup"><span data-stu-id="004aa-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="004aa-125">우선 **순위** 계정 추가 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름 또는 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="004aa-126">실패 또는 지연된 전자 메일에 대한 전자 메일 임계값을 설정하고 우선 순위 계정에 대한 문제에 대한 주간 보고서를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="004aa-127">사용자를 선택하고 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="004aa-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="004aa-128">활성 사용자 페이지에서 우선 순위 계정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="004aa-129">활성 사용자 페이지에서 우선 순위 계정 추가</span><span class="sxs-lookup"><span data-stu-id="004aa-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="004aa-130">활성 사용자 페이지에서 우선 순위 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="004aa-131"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="004aa-132">사용자 활성 **사용자로** 이동하여 페이지 맨 위에 있는  >   **...를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="004aa-133">우선 **순위 계정 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="004aa-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="004aa-134">계정 **추가를** 선택하고  우선 순위 계정 추가 페이지의 검색 필드에 우선 순위 계정 목록에 추가할 사람의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="004aa-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="004aa-135">사용자를 선택하고 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="004aa-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="004aa-136">우선 순위 계정 목록에서 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="004aa-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="004aa-137">Microsoft 365 관리 센터로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="004aa-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="004aa-138">조직 지식 **설정으로** 이동한 후 가장 중요한 계정 모니터링에서  >   **보기를 선택하십시오.** </span><span class="sxs-lookup"><span data-stu-id="004aa-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="004aa-139">On the **Monitor your most accounts** page, choose Priority **accounts** under Manage **this feature.**</span><span class="sxs-lookup"><span data-stu-id="004aa-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="004aa-140">우선 **순위 계정** 페이지에서 목록에서 제거할 사용자를 선택하고 계정을 **제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="004aa-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="004aa-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="004aa-141">Related topics</span></span>

[<span data-ttu-id="004aa-142">Microsoft 365에서 우선 순위 계정 사용</span><span class="sxs-lookup"><span data-stu-id="004aa-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
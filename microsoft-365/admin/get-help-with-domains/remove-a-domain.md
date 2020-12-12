---
title: 도메인 제거
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365에서 이전 도메인을 제거하고 사용자 및 그룹을 다른 도메인으로 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: cddbb0ef9cf48147e33b93a4a8def15576edfab5
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655533"
---
# <a name="remove-a-domain"></a><span data-ttu-id="5de06-103">도메인 제거</span><span class="sxs-lookup"><span data-stu-id="5de06-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5de06-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-104">The admin center is changing.</span></span> <span data-ttu-id="5de06-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="5de06-106">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-106">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5de06-107">다른 Microsoft 365 구독 요금제에 도메인을 추가하려는 경우 도메인을 제거하고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="5de06-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="5de06-108">아니면 단지 구독을 취소하고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="5de06-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="5de06-109">[ 또는 구독을 변경 ](../../commerce/subscriptions/switch-to-a-different-plan.md)하거나 [구독을 취소](../../commerce/subscriptions/cancel-your-subscription.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="5de06-110">1단계: 사용자를 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="5de06-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="5de06-111">사용자 이동</span><span class="sxs-lookup"><span data-stu-id="5de06-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5de06-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="5de06-113">사용자 **활성 사용자를** > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="5de06-114">이동할 모든 사용자의 이름 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="5de06-115">Select **More options** (**...**), at the top of the page, and then choose **Change domains**.</span><span class="sxs-lookup"><span data-stu-id="5de06-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="5de06-116">도메인 **변경 창에서** 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="5de06-p103">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5de06-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="5de06-120">사용자 **활성 사용자를** > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="5de06-121">이동할 모든 사용자의 이름 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="5de06-122">At the top of the page, choose **More** > **Edit domains.**</span><span class="sxs-lookup"><span data-stu-id="5de06-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="5de06-123">도메인 **편집 창에서** 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="5de06-p104">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5de06-126"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="5de06-127">사용자 **활성 사용자를** > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="5de06-128">이동할 모든 사용자의 이름 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="5de06-129">At the top of the page, choose **More** > **Edit domains.**</span><span class="sxs-lookup"><span data-stu-id="5de06-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="5de06-130">도메인 **편집 창에서** 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="5de06-p105">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="5de06-133">직접 이동</span><span class="sxs-lookup"><span data-stu-id="5de06-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5de06-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="5de06-135">사용자  활성 \> **사용자로 이동한** 후 목록에서 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="5de06-136">계정 **탭에서** **사용자** 이름 관리를 선택한 다음 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="5de06-137">At the top, select your account name, then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="5de06-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="5de06-138">새 도메인과 동일한 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="5de06-139">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="5de06-140">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="5de06-141">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5de06-142">사용자  활성 \> **사용자로 이동한** 다음 목록에서 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="5de06-143">사용자 **이름/전자 메일 섹션에서** 편집을 선택한 다음 다른 도메인을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5de06-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="5de06-144">기본 **저장 닫기로** > **설정 선택** > </span><span class="sxs-lookup"><span data-stu-id="5de06-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="5de06-145">At the top, select your account name, then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="5de06-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="5de06-146">새 도메인과 동일한 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="5de06-147">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="5de06-148">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="5de06-149">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5de06-150">사용자  활성 \> **사용자로 이동한** 다음 목록에서 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="5de06-151">사용자 **이름/전자 메일 섹션에서** 편집을 선택한 다음 다른 도메인을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5de06-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="5de06-152">기본 **저장 닫기로** > **설정 선택** > </span><span class="sxs-lookup"><span data-stu-id="5de06-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="5de06-153">At the top, select your account name, then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="5de06-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="5de06-154">새 도메인과 동일한 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="5de06-155">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="5de06-156">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="5de06-157">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="5de06-158">2단계: 다른 도메인으로 그룹 이동</span><span class="sxs-lookup"><span data-stu-id="5de06-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5de06-159">관리 센터에서 그룹 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="5de06-160">그룹 이름을 선택한 다음 전자  메일 주소 기본 아래에 있는 일반 탭에서 **편집을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="5de06-161">드롭다운 목록을 사용하여 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="5de06-162">**저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="5de06-163">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5de06-164">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>그룹 **그룹** > **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="5de06-165">그룹 이름을 선택하고 이름 옆에 **있는** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="5de06-166">드롭다운 목록을 사용하여 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="5de06-167">**저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="5de06-168">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5de06-169">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>그룹 **그룹** > **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="5de06-170">그룹 이름을 선택하고 이름 옆에 **있는** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="5de06-171">드롭다운 목록을 사용하여 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="5de06-172">**저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="5de06-173">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="5de06-174">3단계: 이전 도메인 제거</span><span class="sxs-lookup"><span data-stu-id="5de06-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5de06-175">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="5de06-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5de06-176">관리 센터에서 설치  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인 페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5de06-177">관리 센터에서 설치  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인 페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="5de06-178">도메인 **페이지에서** 제거할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="5de06-179">오른쪽 창에서 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="5de06-180">추가 프롬프트에 따라 닫기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5de06-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="5de06-181">도메인을 제거하는 데 걸리는 시간은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="5de06-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="5de06-182">보안 그룹, 메일 그룹, 사용자 및 Microsoft 365 그룹과 같은 많은 곳에서 참조되지 않는 경우 Microsoft 365에서 도메인을 제거하는 데 5분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="5de06-183">도메인을 사용하는 참조가 많으면 도메인을 제거하는 데 몇 시간(하루)이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="5de06-p113">수백 또는 수천 명의 사용자가 있는 경우 PowerShell을 사용하여 모든 사용자에 대해 쿼리한 다음 사용자를 다른 도메인으로 이동합니다. 그러지 않으면 UI에서 몇 명의 사용자가 누락될 수 있으며, 이 경우 도메인을 제거하기 위해 이동하면 도메인을 제거할 수 없으며 이유를 알지 못하게 됩니다. 자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5de06-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="5de06-188">아직 해결되지 않았습니까?</span><span class="sxs-lookup"><span data-stu-id="5de06-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="5de06-189">계정에서 [". onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 도메인을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="5de06-p114">여전히 작동하지 않나요? 도메인을 수동으로 제거해야 할 수도 있습니다. [전화로 연락주시면](../contact-support-for-business-products.md) 작업을 수행할 수 있도록 지원하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5de06-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="5de06-193">관련 문서</span><span class="sxs-lookup"><span data-stu-id="5de06-193">Related articles</span></span>

[<span data-ttu-id="5de06-194">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="5de06-194">Domains FAQ</span></span>](../setup/domains-faq.yml)

[<span data-ttu-id="5de06-195">다른 비즈니스용 Microsoft 365 요금제로 전환</span><span class="sxs-lookup"><span data-stu-id="5de06-195">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="5de06-196">구독 취소</span><span class="sxs-lookup"><span data-stu-id="5de06-196">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)

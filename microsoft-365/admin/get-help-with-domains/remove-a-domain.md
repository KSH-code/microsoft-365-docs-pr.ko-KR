---
title: 도메인 제거
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365에서 이전 도메인을 제거 하 고 사용자 및 그룹을 다른 도메인으로 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ef0209d6ccb7534745172585fe599f627e386cb4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140408"
---
# <a name="remove-a-domain"></a><span data-ttu-id="50a2a-103">도메인 제거</span><span class="sxs-lookup"><span data-stu-id="50a2a-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="50a2a-104">관리 센터가 변경 되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-104">The admin center is changing.</span></span> <span data-ttu-id="50a2a-105">환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="50a2a-106">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="50a2a-107">다른 Microsoft 365 구독 계획에 추가 하려고 하기 때문에 도메인을 제거 하 고 계십니까?</span><span class="sxs-lookup"><span data-stu-id="50a2a-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="50a2a-108">아니면 단지 구독을 취소하고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="50a2a-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="50a2a-109">[ 또는 구독을 변경 ](../../commerce/subscriptions/switch-to-a-different-plan.md)하거나 [구독을 취소](../../commerce/subscriptions/cancel-your-subscription.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="50a2a-110">1 단계: 사용자를 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="50a2a-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="50a2a-111">사용자 이동</span><span class="sxs-lookup"><span data-stu-id="50a2a-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="50a2a-112">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="50a2a-113"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="50a2a-114">**사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="50a2a-115">이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="50a2a-116">페이지 맨 위에 있는 **기타 옵션** (**...**)을 선택 하 고 **도메인 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="50a2a-117">**도메인 변경** 창에서 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="50a2a-p103">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="50a2a-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="50a2a-121">**사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="50a2a-122">이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="50a2a-123">페이지 맨 위에서 **기타** > **도메인 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="50a2a-124">**도메인 편집** 창에서 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="50a2a-p104">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="50a2a-127"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="50a2a-128">**사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="50a2a-129">이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="50a2a-130">페이지 맨 위에서 **기타** > **도메인 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="50a2a-131">**도메인 편집** 창에서 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="50a2a-p105">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="50a2a-134">직접 이동</span><span class="sxs-lookup"><span data-stu-id="50a2a-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="50a2a-135">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="50a2a-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="50a2a-137">**사용자** \> **활성 사용자**로 이동한 다음 목록에서 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="50a2a-138">**계정** 탭에서 **사용자 이름 관리**를 선택 하 고 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="50a2a-139">맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="50a2a-140">새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="50a2a-141">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="50a2a-142">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="50a2a-143">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="50a2a-144">**사용자** \> **활성 사용자**로 이동한 다음 목록에서 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="50a2a-145">**사용자 이름/전자 메일** 섹션에서 **편집**을 선택 하 고 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="50a2a-146">기본 > **Save** 저장 > **닫기를** **설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="50a2a-147">맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="50a2a-148">새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="50a2a-149">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="50a2a-150">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="50a2a-151">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="50a2a-152">**사용자** \> **활성 사용자**로 이동한 다음 목록에서 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="50a2a-153">**사용자 이름/전자 메일** 섹션에서 **편집**을 선택 하 고 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="50a2a-154">기본 > **Save** 저장 > **닫기를** **설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="50a2a-155">맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="50a2a-156">새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="50a2a-157">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="50a2a-158">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="50a2a-159">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="50a2a-160">2 단계: 그룹을 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="50a2a-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="50a2a-161">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="50a2a-162">그룹 이름을 선택한 다음 **일반** 탭의 **전자 메일 주소, 주**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="50a2a-163">드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="50a2a-164">**저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="50a2a-165">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="50a2a-166"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="50a2a-167">그룹 이름을 선택한 다음 **이름**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="50a2a-168">드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="50a2a-169">**저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="50a2a-170">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="50a2a-171"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="50a2a-172">그룹 이름을 선택한 다음 **이름**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="50a2a-173">드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="50a2a-174">**저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="50a2a-175">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="50a2a-176">3 단계: 이전 도메인 제거</span><span class="sxs-lookup"><span data-stu-id="50a2a-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="50a2a-177">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="50a2a-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="50a2a-178">관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> **설정** \> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="50a2a-179">관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> **설정** \> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="50a2a-180">**도메인** 페이지에서 제거 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="50a2a-181">오른쪽 창에서 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="50a2a-182">추가 프롬프트를 따른 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="50a2a-183">도메인을 제거하는 데 걸리는 시간은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="50a2a-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="50a2a-184">Microsoft 365이 보안 그룹, 메일 그룹, 사용자 및 Microsoft 365 그룹과 같은 많은 위치에서 참조 되지 않는 경우 도메인을 제거 하는 데에는 5 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="50a2a-185">도메인을 사용하는 참조가 많으면 도메인을 제거하는 데 몇 시간(하루)이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="50a2a-p113">수백 또는 수천 명의 사용자가 있는 경우 PowerShell을 사용하여 모든 사용자에 대해 쿼리한 다음 사용자를 다른 도메인으로 이동합니다. 그러지 않으면 UI에서 몇 명의 사용자가 누락될 수 있으며, 이 경우 도메인을 제거하기 위해 이동하면 도메인을 제거할 수 없으며 이유를 알지 못하게 됩니다. 자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="50a2a-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="50a2a-190">여전히 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="50a2a-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="50a2a-191">계정에서 [". onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 도메인을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="50a2a-p114">여전히 작동하지 않나요? 도메인을 수동으로 제거해야 할 수도 있습니다. [전화로 연락주시면](../contact-support-for-business-products.md) 작업을 수행할 수 있도록 지원하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="50a2a-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="50a2a-195">관련 문서</span><span class="sxs-lookup"><span data-stu-id="50a2a-195">Related articles</span></span>

[<span data-ttu-id="50a2a-196">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="50a2a-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="50a2a-197">Office 365 도메인에 대 한 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="50a2a-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="50a2a-198">다른 비즈니스용 Microsoft 365 요금제로 전환</span><span class="sxs-lookup"><span data-stu-id="50a2a-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="50a2a-199">구독 취소</span><span class="sxs-lookup"><span data-stu-id="50a2a-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)

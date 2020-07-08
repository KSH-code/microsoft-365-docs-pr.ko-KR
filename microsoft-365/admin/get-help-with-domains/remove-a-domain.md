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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365에서 이전 도메인을 제거 하 고 사용자 및 그룹을 다른 도메인으로 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079764"
---
# <a name="remove-a-domain"></a><span data-ttu-id="b8e1c-103">도메인 제거</span><span class="sxs-lookup"><span data-stu-id="b8e1c-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b8e1c-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-104">The admin center is changing.</span></span> <span data-ttu-id="b8e1c-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="b8e1c-106">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b8e1c-107">다른 Microsoft 365 구독 계획에 추가 하려고 하기 때문에 도메인을 제거 하 고 계십니까?</span><span class="sxs-lookup"><span data-stu-id="b8e1c-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="b8e1c-108">아니면 단지 구독을 취소하고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="b8e1c-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="b8e1c-109">[ 또는 구독을 변경 ](../../commerce/subscriptions/switch-to-a-different-plan.md)하거나 [구독을 취소](../../commerce/subscriptions/cancel-your-subscription.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="b8e1c-110">1 단계: 사용자를 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="b8e1c-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="b8e1c-111">사용자 이동</span><span class="sxs-lookup"><span data-stu-id="b8e1c-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8e1c-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="b8e1c-113">**사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="b8e1c-114">이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="b8e1c-115">페이지 맨 위에 있는 **기타 옵션** (**...**)을 선택 하 고 **도메인 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="b8e1c-116">**도메인 변경** 창에서 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="b8e1c-117">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-117">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="b8e1c-118">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-118">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8e1c-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="b8e1c-120">**사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="b8e1c-121">이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="b8e1c-122">페이지 맨 위에서 **기타** > **도메인 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="b8e1c-123">**도메인 편집** 창에서 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="b8e1c-124">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-124">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="b8e1c-125">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-125">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8e1c-126"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="b8e1c-127">**사용자** > **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="b8e1c-128">이동 하려는 모든 사용자의 이름 옆에 있는 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="b8e1c-129">페이지 맨 위에서 **기타** > **도메인 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="b8e1c-130">**도메인 편집** 창에서 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="b8e1c-131">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-131">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="b8e1c-132">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-132">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="b8e1c-133">직접 이동</span><span class="sxs-lookup"><span data-stu-id="b8e1c-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8e1c-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터로</a>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="b8e1c-135">**사용자** \> **활성 사용자**로 이동한 다음 목록에서 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="b8e1c-136">**계정** 탭에서 **사용자 이름 관리**를 선택 하 고 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="b8e1c-137">맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="b8e1c-138">새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="b8e1c-139">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="b8e1c-140">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="b8e1c-141">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8e1c-142">**사용자** \> **활성 사용자**로 이동한 다음 목록에서 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="b8e1c-143">**사용자 이름/전자 메일** 섹션에서 **편집**을 선택 하 고 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="b8e1c-144">기본 저장 닫기를 **설정을** 선택 > **Save** > **Close**합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="b8e1c-145">맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="b8e1c-146">새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="b8e1c-147">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="b8e1c-148">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="b8e1c-149">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8e1c-150">**사용자** \> **활성 사용자**로 이동한 다음 목록에서 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="b8e1c-151">**사용자 이름/전자 메일** 섹션에서 **편집**을 선택 하 고 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="b8e1c-152">기본 저장 닫기를 **설정을** 선택 > **Save** > **Close**합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="b8e1c-153">맨 위에서 계정 이름을 선택한 다음 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="b8e1c-154">새 도메인 및 같은 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="b8e1c-155">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="b8e1c-156">자세한 내용은 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="b8e1c-157">기본 도메인을 설정하려면 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="b8e1c-158">2 단계: 그룹을 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="b8e1c-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8e1c-159">관리 센터에서 **그룹** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">그룹</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b8e1c-160">그룹 이름을 선택한 다음 **일반** 탭의 **전자 메일 주소, 주**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="b8e1c-161">드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="b8e1c-162">**저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="b8e1c-163">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8e1c-164"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>에서 **그룹** > **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="b8e1c-165">그룹 이름을 선택한 다음 **이름**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="b8e1c-166">드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="b8e1c-167">**저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="b8e1c-168">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8e1c-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>에서 **그룹** > **그룹** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="b8e1c-170">그룹 이름을 선택한 다음 **이름**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="b8e1c-171">드롭다운 목록을 사용 하 여 다른 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="b8e1c-172">**저장**을 선택한 다음 **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="b8e1c-173">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="b8e1c-174">3 단계: 이전 도메인 제거</span><span class="sxs-lookup"><span data-stu-id="b8e1c-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8e1c-175">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8e1c-176">관리 센터에서 **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 설정 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8e1c-177">관리 센터에서 **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 설정 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="b8e1c-178">**도메인** 페이지에서 제거 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="b8e1c-179">오른쪽 창에서 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="b8e1c-180">추가 프롬프트를 따른 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="b8e1c-181">도메인을 제거하는 데 걸리는 시간은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="b8e1c-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="b8e1c-182">Microsoft 365이 보안 그룹, 메일 그룹, 사용자 및 Microsoft 365 그룹과 같은 많은 위치에서 참조 되지 않는 경우 도메인을 제거 하는 데에는 5 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="b8e1c-183">도메인을 사용하는 참조가 많으면 도메인을 제거하는 데 몇 시간(하루)이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="b8e1c-184">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-184">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain.</span></span> <span data-ttu-id="b8e1c-185">Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-185">Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why.</span></span> <span data-ttu-id="b8e1c-186">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-186">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="b8e1c-187">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="b8e1c-187">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="b8e1c-188">아직 해결되지 않았습니까?</span><span class="sxs-lookup"><span data-stu-id="b8e1c-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b8e1c-189">계정에서 [". onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 도메인을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="b8e1c-190">Still not working?</span><span class="sxs-lookup"><span data-stu-id="b8e1c-190">Still not working?</span></span> <span data-ttu-id="b8e1c-191">Your domain might need to be manually removed.</span><span class="sxs-lookup"><span data-stu-id="b8e1c-191">Your domain might need to be manually removed.</span></span> <span data-ttu-id="b8e1c-192">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span><span class="sxs-lookup"><span data-stu-id="b8e1c-192">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="b8e1c-193">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b8e1c-193">Related articles</span></span>

[<span data-ttu-id="b8e1c-194">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="b8e1c-194">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="b8e1c-195">Microsoft 365 도메인에 대 한 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="b8e1c-195">Get help with Microsoft 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="b8e1c-196">다른 비즈니스용 Microsoft 365 요금제로 전환</span><span class="sxs-lookup"><span data-stu-id="b8e1c-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="b8e1c-197">구독 취소</span><span class="sxs-lookup"><span data-stu-id="b8e1c-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)

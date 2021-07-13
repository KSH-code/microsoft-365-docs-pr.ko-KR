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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 이전 도메인에서 이전 도메인을 제거하고 Microsoft 365 다른 도메인으로 이동하거나 구독을 취소하는 방법을 학습합니다.
ms.openlocfilehash: 227ca3e58a4c6278278048deeffcf68c1d659546
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393874"
---
# <a name="remove-a-domain"></a><span data-ttu-id="3d8c1-103">도메인 제거</span><span class="sxs-lookup"><span data-stu-id="3d8c1-103">Remove a domain</span></span>

 <span data-ttu-id="3d8c1-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="3d8c1-105">도메인을 다른 구독 계획에 추가하려는 경우 도메인을 Microsoft 365 있나요?</span><span class="sxs-lookup"><span data-stu-id="3d8c1-105">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="3d8c1-106">아니면 단지 구독을 취소하고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="3d8c1-106">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="3d8c1-107">[ 또는 구독을 변경 ](../../commerce/subscriptions/switch-to-a-different-plan.md)하거나 [구독을 취소](../../commerce/subscriptions/cancel-your-subscription.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-107">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>

### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="3d8c1-108">1단계: 사용자를 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="3d8c1-108">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="3d8c1-109">사용자 이동</span><span class="sxs-lookup"><span data-stu-id="3d8c1-109">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3d8c1-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-110">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3d8c1-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3d8c1-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

::: moniker-end

2. <span data-ttu-id="3d8c1-113">사용자 **활성 사용자를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d8c1-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3d8c1-114">이동할 모든 사용자의 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3d8c1-115">At the top of the page, and then choose **Change domains**.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-115">At the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="3d8c1-116">도메인 **변경 창에서** 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="3d8c1-p102">현재 제거 중인 도메인에 있는 경우 직접 이 작업을 해야 합니다. 사용자 계정의 도메인을 편집하는 경우 계속하려면 로그아웃한 후 선택한 새 도메인을 사용하여 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

#### <a name="move-yourself"></a><span data-ttu-id="3d8c1-119">직접 이동</span><span class="sxs-lookup"><span data-stu-id="3d8c1-119">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3d8c1-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3d8c1-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3d8c1-122"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-122">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

::: moniker-end

2. <span data-ttu-id="3d8c1-123">사용자  활성 \> **사용자로 이동하여** 목록에서 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-123">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="3d8c1-124">계정 **탭에서** 사용자 이름 **관리를** 선택한 다음 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-124">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>

4. <span data-ttu-id="3d8c1-125">At the top, select your account name, then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-125">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3d8c1-126">새 도메인과 동일한 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-126">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3d8c1-p103">PowerShell을 사용하여 사용자를 다른 도메인으로 이동할 수도 있습니다. 자세한 내용은 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-p103">You can also use PowerShell to move users to another domain. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span></span>

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="3d8c1-130">2단계: 그룹을 다른 도메인으로 이동</span><span class="sxs-lookup"><span data-stu-id="3d8c1-130">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3d8c1-131">관리 센터에서 그룹 그룹  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="3d8c1-132">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">센터에서</a>그룹 그룹 **페이지로** >  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3d8c1-133">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">센터에서</a>그룹 그룹 **페이지로** >  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

::: moniker-end

2. <span data-ttu-id="3d8c1-134">그룹 이름을 선택하고 전자 메일  주소의 일반 **탭에서 기본** 에서 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d8c1-134">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="3d8c1-135">드롭다운 목록을 사용하여 다른 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-135">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3d8c1-136">**저장** 을 선택한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-136">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3d8c1-137">제거하려는 도메인과 연관된 그룹 또는 분배 목록에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-137">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="3d8c1-138">3단계: 이전 도메인 제거</span><span class="sxs-lookup"><span data-stu-id="3d8c1-138">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3d8c1-139">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3d8c1-140">관리 센터에서 설치 도메인  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-140">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3d8c1-141">관리 센터에서 설치 도메인  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-141">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="3d8c1-142">도메인 **페이지에서** 제거할 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-142">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="3d8c1-143">오른쪽 창에서 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d8c1-143">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="3d8c1-144">추가 프롬프트를 따르고 닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d8c1-144">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="3d8c1-145">도메인을 제거하는 데 걸리는 시간은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="3d8c1-145">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="3d8c1-146">보안 그룹, 메일 그룹Microsoft 365 사용자 및 사용자 그룹과 같은 많은 장소에서 참조되지 않는 경우 도메인을 제거하는 데 5분 정도 걸릴 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-146">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="3d8c1-147">도메인을 사용하는 참조가 많으면 도메인을 제거하는 데 몇 시간(하루)이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-147">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>

<span data-ttu-id="3d8c1-p106">수백 또는 수천 명의 사용자가 있는 경우 PowerShell을 사용하여 모든 사용자에 대해 쿼리한 다음 사용자를 다른 도메인으로 이동합니다. 그러지 않으면 UI에서 몇 명의 사용자가 누락될 수 있으며, 이 경우 도메인을 제거하기 위해 이동하면 도메인을 제거할 수 없으며 이유를 알지 못하게 됩니다. 자세한 내용은 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)을 참조하세요. 기본 도메인을 설정하려면 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-p106">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span></span>

## <a name="still-need-help"></a><span data-ttu-id="3d8c1-152">아직 해결되지 않았습니까?</span><span class="sxs-lookup"><span data-stu-id="3d8c1-152">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3d8c1-153">계정에서 [". onmicrosoft.com"](../setup/domains-faq.yml) 도메인을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-153">You can't remove the [".onmicrosoft.com"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="3d8c1-154">도메인을 제거하면 사용자 계정이 ".onmicrosoft.com" 주소로 되돌아가 기본 SMTP/UserprincipalName으로 되돌아가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-154">When you remove a domain, user accounts will revert back to the ".onmicrosoft.com" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="3d8c1-p108">여전히 작동하지 않나요? 도메인을 수동으로 제거해야 할 수도 있습니다. [전화로 연락주시면](../../business-video/get-help-support.md) 작업을 수행할 수 있도록 지원하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-p108">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md) and we'll help you take care of it!</span></span>

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> <span data-ttu-id="3d8c1-158">계정에서 [".onmicrosoft.de"](../setup/domains-faq.yml) 도메인을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-158">You can't remove the [".onmicrosoft.de"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="3d8c1-159">도메인을 제거하면 사용자 계정이 ".onmicrosoft.de" 주소로 되돌아가 기본 SMTP/UserprincipalName으로 되돌아가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-159">When you remove a domain, user accounts will revert back to the ".onmicrosoft.de" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="3d8c1-p110">여전히 작동하지 않나요? 도메인을 수동으로 제거해야 할 수도 있습니다. [전화로 연락주시면](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true) 작업을 수행할 수 있도록 지원하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-p110">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true) and we'll help you take care of it!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3d8c1-163">계정에서 [".partner.onmschina.cn"](../setup/domains-faq.yml) 도메인을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-163">You can't remove the [".partner.onmschina.cn"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="3d8c1-164">도메인을 제거하면 사용자 계정이 ".partner.onmschina.cn" 주소로 되돌아가 기본 SMTP/UserprincipalName으로 되돌아가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-164">When you remove a domain, user accounts will revert back to the ".partner.onmschina.cn" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="3d8c1-p112">여전히 작동하지 않나요? 도메인을 수동으로 제거해야 할 수도 있습니다. [전화로 연락주시면](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) 작업을 수행할 수 있도록 지원하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8c1-p112">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) and we'll help you take care of it!</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="3d8c1-168">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="3d8c1-168">Related content</span></span>

<span data-ttu-id="3d8c1-169">[도메인 FAQ](../setup/domains-faq.yml) (문서)</span><span class="sxs-lookup"><span data-stu-id="3d8c1-169">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="3d8c1-170">[다른 비즈니스용 Microsoft 365 요금제로](../../commerce/subscriptions/switch-to-a-different-plan.md) 전환(문서)</span><span class="sxs-lookup"><span data-stu-id="3d8c1-170">[Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md) (article)</span></span>

<span data-ttu-id="3d8c1-171">[구독 취소(문서)](../../commerce/subscriptions/cancel-your-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="3d8c1-171">[Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md) (article)</span></span>

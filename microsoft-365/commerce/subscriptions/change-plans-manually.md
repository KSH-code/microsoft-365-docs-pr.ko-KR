---
title: 수동으로 Office 365 for business 요금제 변경
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 새 구독을 구입 하 고 구독이 모두 나열 되 고 활성 상태가 되도록 하 여 수동으로 구독을 변경 합니다.
ms.openlocfilehash: 0042e0fd2fa5ac10be512246c252bc1d0f679709
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245988"
---
# <a name="change-plans-manually"></a><span data-ttu-id="76ba0-103">수동으로 계획 변경</span><span class="sxs-lookup"><span data-stu-id="76ba0-103">Change plans manually</span></span>

> [!NOTE]
> <span data-ttu-id="76ba0-104">이 문서는 새 관리 센터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-104">This article applies to the new admin center.</span></span> <span data-ttu-id="76ba0-105">새 관리 센터는 모든 Microsoft 365 관리자가 사용할 수 있으며, 홈 페이지 맨 위에 있는 **새 관리 센터** 전환 사용을 선택 하 여 옵트인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-105">The new admin center is available to all Microsoft 365 admins, and you can opt in by selecting **Try the new admin center** toggle located at the top of the Home page.</span></span> <span data-ttu-id="76ba0-106">자세한 내용은 [새 Microsoft 365 관리 센터 정보](../../admin/microsoft-365-admin-center-preview.md)를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="76ba0-106">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span> <span data-ttu-id="76ba0-107">이전 관리 센터에 대 한 문서를 보려면 [Office 365 for business 요금제를 수동으로 전환을](switch-plans-manually.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76ba0-107">To view the article about the old admin center, see [Switch Office 365 for business plans manually](switch-plans-manually.md).</span></span>

## <a name="step-1-decide-how-to-change-plans"></a><span data-ttu-id="76ba0-108">1 단계: 요금제 변경 방법 결정</span><span class="sxs-lookup"><span data-stu-id="76ba0-108">Step 1: Decide how to change plans</span></span>

<span data-ttu-id="76ba0-109">모든 사용자를 한 요금제에서 다른 계획으로 변경 하는 가장 좋은 방법은 [Upgrade 탭을 사용](upgrade-to-different-plan.md)하는 것입니다. 때로는 가능 하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-109">The best way to change all your users from one plan to another is to [use the Upgrade tab](upgrade-to-different-plan.md). Sometimes this isn't possible.</span></span> <span data-ttu-id="76ba0-110">대신 수동으로 요금제를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-110">Change plans manually instead:</span></span>

- <span data-ttu-id="76ba0-111">**업그레이드** 탭에 현재 요금제를 업그레이드할 수 없는 것으로 표시 되는 경우</span><span class="sxs-lookup"><span data-stu-id="76ba0-111">If the **Upgrade** tab indicates you can't upgrade the current plan.</span></span>

- <span data-ttu-id="76ba0-112">**업그레이드** 탭을 선택 하면 원하는 요금제가 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-112">If, when you select the **Upgrade** tab, the plan you want isn't listed.</span></span>

- <span data-ttu-id="76ba0-113">모든 사용자를 동일한 방식으로 업그레이드 하지 않으려는 경우</span><span class="sxs-lookup"><span data-stu-id="76ba0-113">If you don't want to upgrade all your users in the same way.</span></span> <span data-ttu-id="76ba0-114">일부 회사에서는 다른 요금제로 구독 하는 다른 사용자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-114">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="76ba0-115">이를 위해 수동 변경 내용을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-115">Use a manual change for this.</span></span>

<span data-ttu-id="76ba0-116">수동 변경 작업을 계속 하려면이 항목의 [2 단계: 새 구독 구입](#step-2-buy-a-new-subscription) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76ba0-116">To continue with a manual change, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76ba0-117">현재 계획 (다운 그레이드) 보다 더 작은 데이터 관련 서비스를 사용 하 여 계획으로 변경 하는 경우에는 유지할 데이터를 수동으로 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-117">If you are changing to a plan with fewer data-related services than your current plan (downgrading), you need to manually back up any data you wish to keep.</span></span> <span data-ttu-id="76ba0-118">자세한 내용은 [비즈니스 계획을 위한 O365을 전환 하기 전에 데이터 백업을](back-up-data-before-switching-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76ba0-118">For more information, see [Back up data before switching O365 for business plans](back-up-data-before-switching-plans.md).</span></span>

## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="76ba0-119">2 단계: 새 구독 구입</span><span class="sxs-lookup"><span data-stu-id="76ba0-119">Step 2: Buy a new subscription</span></span>

<span data-ttu-id="76ba0-120">**이미 구입 했습니까?**</span><span class="sxs-lookup"><span data-stu-id="76ba0-120">**Already purchased?**</span></span> <span data-ttu-id="76ba0-121">사용자를 이동 하려는 구독이 이미 있는 경우이 단계를 건너뛰고이 항목의 [3 단계: 새 구독 및 라이선스 확인](#step-3-check-your-new-subscription-and-licenses) 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-121">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>

<span data-ttu-id="76ba0-122">또는</span><span class="sxs-lookup"><span data-stu-id="76ba0-122">OR</span></span>

<span data-ttu-id="76ba0-123">**새 구독 및 라이선스를 구입 합니다.** 새 구독을 구입 하려면 [비즈니스용 Office 365 for business subscription](../buy-another-subscription.md) 의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-123">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Office 365 for business subscription](../buy-another-subscription.md) to buy a new subscription.</span></span>

<span data-ttu-id="76ba0-124">사용자가 현재 있는 동일한 조직에 대 한 구독을 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-124">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="76ba0-125">예를 들어 이동 하려는 Office 365 사용자의 전자 메일 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-125">For example, check the email addresses for the Office 365 users you want to move.</span></span> <span data-ttu-id="76ba0-126">전자 메일 주소에 contoso.com \@가 포함 된 경우 contoso.com에 대 한 새 구독을 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-126">If their email addresses include \@contoso.com, you must purchase a new subscription for contoso.com.</span></span>
<span data-ttu-id="76ba0-127">이동 하려는 각 사용자에 대 한 라이선스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-127">Include a license for each user that you want to move.</span></span>

## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="76ba0-128">3 단계: 새 구독 및 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="76ba0-128">Step 3: Check your new subscription and licenses</span></span>

1. <span data-ttu-id="76ba0-129">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품 및 서비스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-129">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="76ba0-130">**두 구독이 모두 나열 되 고 활성 상태 인지 확인** 사용자를 이동 하는 구독과 사용자를 이동 하려는 구독은 함께 나열 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-130">**Verify that both subscriptions are listed and active** The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="76ba0-131">처음 확인할 때 새 구독이 없으면 나중에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="76ba0-131">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="76ba0-132">두 구독이 모두 활성 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-132">Check that both subscriptions are active.</span></span> <span data-ttu-id="76ba0-133">[새 구독이 나열 되지 않거나 활성](#the-new-subscription-isnt-listed-or-isnt-active)상태가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-133">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

3. <span data-ttu-id="76ba0-134">**각 사용자에 대 한 라이선스가 충분 한지 확인** 각 사용자에 게는 구독과 일치 하는 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-134">**Check that you have enough licenses for each user** Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="76ba0-135">따라서 10 명의 사용자를 Office 365 Enterprise e 5로 이동 하려는 경우에는 라이선스를 10 개 사용할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-135">So if you want to move ten users to Office 365 Enterprise E5, you'll need to make sure ten licenses are available.</span></span>

4. <span data-ttu-id="76ba0-136">**새 구독에 대 한 라이선스가 더 필요 한가요?**</span><span class="sxs-lookup"><span data-stu-id="76ba0-136">**Need more licenses for the new subscription?**</span></span>
   <span data-ttu-id="76ba0-137">**Products & services** 페이지로 이동 하 여 [추가 라이선스를 구입](../licenses/buy-licenses.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-137">Go to the **Products & services** page and [buy more licenses](../licenses/buy-licenses.md).</span></span>

> [<span data-ttu-id="76ba0-138">이전 라이선스는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="76ba0-138">What about the old licenses?</span></span>](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="76ba0-139">새 구독이 나열 되지 않거나 활성 상태가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-139">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="76ba0-140">**두 구독을 구매한 경우 둘 다 여기에 나열 되어 있지 않은 경우**에는 다른 조직에 대해 다른 도메인에 대해 구매한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-140">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="76ba0-141">구독은 조직 경계를 교차할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-141">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="76ba0-142">**추가 구독이 있고**여기에 나열 되어 있지 않거나 활성 상태가 아니면 [Microsoft 지원에 문의](../../admin/contact-support-for-business-products.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="76ba0-142">**If you know you have an additional subscription**, and it's not listed here, or is not active, [call Microsoft support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="76ba0-143">이전 라이선스는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="76ba0-143">What about the old licenses?</span></span>

<span data-ttu-id="76ba0-144">현재 구독에 대 한 라이선스는 나중에 제거 됩니다. 이 경우에는 새 사용자 라이선스에 대 한 결제만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-144">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>

## <a name="step-4-reassign-licenses"></a><span data-ttu-id="76ba0-145">4 단계: 라이선스 다시 할당</span><span class="sxs-lookup"><span data-stu-id="76ba0-145">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="76ba0-146">한 사용자에 대 한 라이선스 다시 할당</span><span class="sxs-lookup"><span data-stu-id="76ba0-146">Reassign a license for one user</span></span>

1. <span data-ttu-id="76ba0-147">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="76ba0-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="76ba0-148">**활성 사용자** 페이지에서 라이선스를 할당 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-148">On the **Active users** page, select the user to whom you want to assign a license.</span></span>

3. <span data-ttu-id="76ba0-149">Te **라이선스 및 앱** 탭에서 **라이선스**를 확장 하 고 할당 하려는 라이선스에 대 한 상자를 선택한 다음 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-149">On te **Licenses and Apps** tab, expand **Licenses**, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="76ba0-150">한 번에 여러 사용자에 대해 라이선스 다시 할당</span><span class="sxs-lookup"><span data-stu-id="76ba0-150">Reassign licenses for multiple users at once</span></span>

1. <span data-ttu-id="76ba0-151">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="76ba0-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="76ba0-152">기존 라이선스를 바꾸려는 사용자의 이름 옆에 있는 원을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-152">Select the circles next to the names of the users for whom you want to replace existing licenses.</span></span>

3. <span data-ttu-id="76ba0-153">맨 위에서 **기타 옵션** (**...**)을 선택 하 고 **제품 라이선스 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-153">At the top, select **More options** (**...**), and then choose **Manage product licenses**.</span></span>

4. <span data-ttu-id="76ba0-154">**기존 제품 라이선스 할당 바꾸기** \> **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-154">Select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="76ba0-155">해당 사용자에 게 할당 하려는 제품 **에 대 한 설정 위치로 전환** 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-155">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="76ba0-156">사용자가 사용할 수 있는 서비스를 제한 하려면 해당 사용자에 대해 제거할 서비스에 대 한 **해제** 위치로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-156">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="76ba0-157">예를 들어 사용자에 게 비즈니스용 Skype Online을 제외한 모든 사용 가능한 서비스에 대 한 액세스 권한을 제공 하려는 경우 비즈니스용 Skype Online 서비스에 대 한 토글을 **해제** 위치로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-157">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="76ba0-158">선택한 사용자에 대한 모든 이전 라이선스 할당이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-158">Any previous license assignments for the selected users will be removed.</span></span>

6. <span data-ttu-id="76ba0-159">**기존 제품 바꾸기** 창의 아래쪽에서 **바꾸기** \> **닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-159">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="76ba0-160">5 단계: 구독을 취소 하거나 더 이상 필요 없는 라이선스 제거 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="76ba0-160">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="76ba0-161">모든 사용자를 한 구독에서 다른 구독으로 전환한 경우 원래 구독이 더 이상 필요 없으면 [구독을 취소](cancel-your-subscription.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-161">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>

<span data-ttu-id="76ba0-162">일부 사용자만 다른 구독으로 이동한 경우 더 이상 필요 없는 [라이선스를 제거](../licenses/remove-licenses-from-subscription.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ba0-162">If you moved only some users to a different subscription, [remove licenses](../licenses/remove-licenses-from-subscription.md) that you no longer need.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="76ba0-163">요금제를 변경 하는 데 도움이 되는 통화 지원</span><span class="sxs-lookup"><span data-stu-id="76ba0-163">Call support to help you change plans</span></span>
[<span data-ttu-id="76ba0-164">Microsoft 지원 서비스에 문의</span><span class="sxs-lookup"><span data-stu-id="76ba0-164">Call Microsoft support</span></span>](../../admin/contact-support-for-business-products.md)
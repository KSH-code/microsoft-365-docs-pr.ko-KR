---
title: 비즈니스 요금제에 대 한 Office 365을 변경할 수 없는 이유는 무엇 인가요?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ROBOTS: NOINDEX
description: 때로는 요금제를 수동으로 변경 하거나 지원 서비스를 호출 하 여 계획을 수행 해야 하는 이유를 이해 합니다.
monikerRange: o365-worldwide
ms.openlocfilehash: 4f193db074dccb8146615b72febc62f47a44b7d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246961"
---
# <a name="why-cant-i-upgrade-plans"></a><span data-ttu-id="8c2ff-103">요금제를 업그레이드할 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8c2ff-103">Why can't I upgrade plans?</span></span>

<span data-ttu-id="8c2ff-104">**업그레이드** 탭에 계획이 표시 되지 않으면 요금제가 자동으로 업그레이드 되지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-104">If you don't see any plans on the **Upgrade** tab, it means your plan can't be upgraded automatically.</span></span> <span data-ttu-id="8c2ff-105">경우에 따라 업그레이드할 수 있는 요금제를 볼 수 있도록 문제를 해결할 수 있거나, 대신 수동으로 계획을 업그레이드 하거나 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-105">In some cases, you might be able to resolve the issue so that you can view plans available for upgrade, or you might be able to upgrade or change plans manually, instead.</span></span>

> [!NOTE]
> <span data-ttu-id="8c2ff-106">이 문서는 새 관리 센터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-106">This article applies to the new admin center.</span></span> <span data-ttu-id="8c2ff-107">새 관리 센터는 모든 Microsoft 365 관리자가 사용할 수 있으며, 홈 페이지 맨 위에 있는 **새 관리 센터** 전환 사용을 선택 하 여 옵트인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-107">The new admin center is available to all Microsoft 365 admins, and you can opt in by selecting **Try the new admin center** toggle located at the top of the Home page.</span></span> <span data-ttu-id="8c2ff-108">자세한 내용은 [새 Microsoft 365 관리 센터 정보](../../admin/microsoft-365-admin-center-preview.md)를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-108">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span> <span data-ttu-id="8c2ff-109">이전 관리 센터에 대 한 문서를 보려면 [왜 Office 365 for business 요금제를 전환할 수 없는 이유](why-can-t-i-switch-plans.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-109">To view the article about the old admin center, see [Why can't I switch Office 365 for business plans?](why-can-t-i-switch-plans.md).</span></span>

## <a name="why-are-there-no-plans-listed-to-upgrade"></a><span data-ttu-id="8c2ff-110">업그레이드에 대 한 계획이 나열 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8c2ff-110">Why are there no plans listed to upgrade?</span></span>

### <a name="you-cant-upgrade-subscriptions-now-because-you-have-more-users-than-licenses"></a><span data-ttu-id="8c2ff-111">라이선스 보다 더 많은 사용자가 있으므로 지금 구독을 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-111">You can't upgrade subscriptions now because you have more users than licenses.</span></span>

<span data-ttu-id="8c2ff-112">요금제를 자동으로 업그레이드 하려면 모든 사용자에 게 유효한 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-112">To upgrade plans automatically, all of your users need to be assigned valid licenses.</span></span> <span data-ttu-id="8c2ff-113">구매한 것보다 많은 라이선스를 할당한 경우 <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지에 해결해야 할 라이선스 충돌이 있다고 알리는 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-113">If you have assigned more licenses than you have purchased, you'll see an alert on the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page that says you have a licensing conflict that needs to be resolved.</span></span> <span data-ttu-id="8c2ff-114">[라이선스 충돌 해결 방법을 알아보세요](../../admin/manage/resolve-license-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="8c2ff-114">[Learn how to resolve license conflicts](../../admin/manage/resolve-license-conflicts.md).</span></span> <span data-ttu-id="8c2ff-115">라이선스 충돌을 해결 한 후에는 **업그레이드** 탭에 나열 된 요금제를 볼 수 있습니다. 그렇지 않은 경우 요금제를 [수동으로 변경](change-plans-manually.md)하거나 [지원 서비스에 문의할](../../admin/contact-support-for-business-products.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-115">After you have resolved any licensing conflicts, you should see plans listed on the **Upgrade** tab. If not, you can [change plans manually](change-plans-manually.md), or [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="you-cant-upgrade-subscriptions-right-now-because-this-subscription-isnt-fully-set-up-or-the-service-isnt-available"></a><span data-ttu-id="8c2ff-116">이 구독이 완전히 설정 되지 않았거나 서비스\'를 사용할 수 없음 이므로 지금 구독을 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-116">You can't upgrade subscriptions right now because this subscription isn't fully set up or the service isn\'t available.</span></span>

<span data-ttu-id="8c2ff-117">예를 들어 서비스 중 하나에 인시던트가 있는 경우 모든 서비스가 정상 상태가 될 때까지 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-117">For example, if one of the services has an incident, you won't be able to upgrade until all services are healthy.</span></span> <span data-ttu-id="8c2ff-118">프로 비전 또는 서비스 상태 문제가 있는지 확인 하려면 관리 센터에서 **상태** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">서비스 상태</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-118">To see if there are provisioning or service health issues, in the admin center, go to the **Health** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">Service health</a> page.</span></span>

<span data-ttu-id="8c2ff-119">서비스가 완전히 프로비전되지 않았거나 서비스 상태 문제가 있는 경우 몇 시간 후에 서비스를 이용할 수 있을 때까지 기다린 다음 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-119">If you find that a service is not fully provisioned, or you have a service health issue, please wait a few hours for your service to become available, and try again.</span></span> <span data-ttu-id="8c2ff-120">여전히 문제가 있는 경우 [지원 서비스에 문의](../../admin/contact-support-for-business-products.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-120">If you still have a problem, please [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="you-cant-upgrade-plans-because-another-plan-is-in-the-process-of-being-upgraded-or-is-pending-a-credit-check"></a><span data-ttu-id="8c2ff-121">다른 요금제가 업그레이드 중이거나 신용 검사 보류 중 이므로 요금제를 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-121">You can't upgrade plans because another plan is in the process of being upgraded or is pending a credit check.</span></span>

<span data-ttu-id="8c2ff-122">요금제를 업그레이드 하기 전에 신용 검사가 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-122">Wait until the credit check has been completed before upgrading plans.</span></span> <span data-ttu-id="8c2ff-123">신용 검사에는 최대 2일이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-123">Credit checks can take up to two working days.</span></span>

### <a name="currently-this-subscription-is-not-eligible-to-upgrade"></a><span data-ttu-id="8c2ff-124">이 구독은 현재 업그레이드에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-124">Currently, this subscription is not eligible to upgrade.</span></span>

<span data-ttu-id="8c2ff-125">요금제를 [수동으로 변경](change-plans-manually.md) 하거나 [지원 서비스에 문의할](../../admin/contact-support-for-business-products.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-125">You can [change plans manually](change-plans-manually.md) or [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="i-see-a-different-message-than-whats-listed-here"></a><span data-ttu-id="8c2ff-126">여기에 나열된 내용과 다른 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-126">I see a different message than what's listed here.</span></span>

<span data-ttu-id="8c2ff-127">요금제를 [수동으로 변경](change-plans-manually.md) 하거나 [지원 서비스에 문의할](../../admin/contact-support-for-business-products.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-127">You can [change plans manually](change-plans-manually.md) or [call support](../../admin/contact-support-for-business-products.md).</span></span>

## <a name="additional-reasons-you-cant-upgrade"></a><span data-ttu-id="8c2ff-128">업그레이드할 수 없는 추가 이유</span><span class="sxs-lookup"><span data-stu-id="8c2ff-128">Additional reasons you can't Upgrade</span></span>

### <a name="you-have-two-or-more-plans-for-the-same-product"></a><span data-ttu-id="8c2ff-129">동일한 제품에 대 한 요금제가 두 개 이상 있는 경우</span><span class="sxs-lookup"><span data-stu-id="8c2ff-129">You have two or more plans for the same product</span></span>

<span data-ttu-id="8c2ff-130">모든 사용자가 동일한 요금제를 구독 하는 경우에만 **업그레이드** 탭을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-130">You can only use the **Upgrade** tab if all users subscribe to the same plan.</span></span> <span data-ttu-id="8c2ff-131">예를 들어 두 개의 Office 365 Business Premium 요금제가 있는 경우 이러한 계획 중 하나를 자동으로 다른 요금제로 업그레이드할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-131">For example, if you have two Office 365 Business Premium plans, you won't be able to automatically upgrade one of them to another plan.</span></span>

### <a name="you-have-a-prepaid-plan"></a><span data-ttu-id="8c2ff-132">선불 요금제를 사용 중인 경우</span><span class="sxs-lookup"><span data-stu-id="8c2ff-132">You have a prepaid plan</span></span>

<span data-ttu-id="8c2ff-133">구독에 대해 미리 지불 한 경우 [요금제를 수동으로 변경할](change-plans-manually.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-133">If you've paid for your subscription in advance, you might be able to [change plans manually](change-plans-manually.md).</span></span> <span data-ttu-id="8c2ff-134">하지만 현재 요금제가 만료 되기 전에 요금제를 업그레이드 하는 경우 현재 구독의 남은 시간에 대 한 학점을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-134">However, you won't receive a credit for unused time remaining on your current subscription if you upgrade plans before the current plan expires.</span></span>

<span data-ttu-id="8c2ff-135">[지원을 요청할](../../admin/contact-support-for-business-products.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-135">You can also [call support](../../admin/contact-support-for-business-products.md) for help.</span></span>

### <a name="you-have-a-government-or-non-profit-plan"></a><span data-ttu-id="8c2ff-136">Government 또는 Nonprofit 요금제를 보유하고 있는 경우</span><span class="sxs-lookup"><span data-stu-id="8c2ff-136">You have a government or non-profit plan</span></span>

<span data-ttu-id="8c2ff-137">정부 또는 비영리 요금제가 있는 경우 [요금제를 수동으로 변경](change-plans-manually.md) 하거나 [지원 서비스에 문의](../../admin/contact-support-for-business-products.md) 하 여 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-137">If you have a government or non-profit plan, you can [change plans manually](change-plans-manually.md) or [call support](../../admin/contact-support-for-business-products.md) for help.</span></span>

### <a name="the-subscription-that-you-want-to-upgrade-from-has-a-temporary-issue"></a><span data-ttu-id="8c2ff-138">업그레이드 하려는 구독에 일시적인 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-138">The subscription that you want to upgrade from has a temporary issue</span></span>

<span data-ttu-id="8c2ff-139">서비스가 많은 양의 요금제를 업그레이드 하는 중 이므로 **업그레이드** 탭에 계획이 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-139">You might not see any plans on the **Upgrade** tab because the service is in the process of upgrading a high volume of plans.</span></span> <span data-ttu-id="8c2ff-140">첫 번째 시도 후 1시간 정도 후에 다시 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-140">Try again in about an hour after your first attempt.</span></span>

### <a name="the-plan-that-you-want-to-upgrade-to-isnt-a-supported-option"></a><span data-ttu-id="8c2ff-141">업그레이드 하려는 계획은 지원 되지 않는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-141">The plan that you want to upgrade to isn't a supported option</span></span>

<span data-ttu-id="8c2ff-142">요금제를 업그레이드할 때 업그레이드에 사용할 수 있는 요금제는 현재 요금제의 서비스를 기반으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-142">When you upgrade plans, the plans that are available for you to upgrade to are displayed based on the services in your current plan.</span></span> <span data-ttu-id="8c2ff-143">Exchange Online, SharePoint Online 등의 데이터 관련 서비스가 동일 하거나 상위 버전의 요금제로만 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-143">You can only upgrade to a plan that has the same data-related services, such as Exchange Online or SharePoint Online, or to a higher version of them.</span></span> <span data-ttu-id="8c2ff-144">이렇게 하면 사용자가\'업그레이드 중에 해당 서비스와 관련 된 데이터가 손실 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-144">This ensures that users don\'t lose data related to those services during the upgrade.</span></span>

<span data-ttu-id="8c2ff-145">요금제가 계획을 자동으로 업그레이드할 수 없는 경우 대신 [요금제를 수동으로 변경할](change-plans-manually.md)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-145">If your plan isn't eligible to upgrade plans automatically, you might be able to [change plans manually](change-plans-manually.md), instead.</span></span> <span data-ttu-id="8c2ff-146">[지원을 요청할](../../admin/contact-support-for-business-products.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-146">You can also [call support](../../admin/contact-support-for-business-products.md) for help.</span></span>

### <a name="your-subscription-has-an-add-on"></a><span data-ttu-id="8c2ff-147">구독에 추가 기능이 있음</span><span class="sxs-lookup"><span data-stu-id="8c2ff-147">Your subscription has an Add-on</span></span>

<span data-ttu-id="8c2ff-148">구독에 대 한 추가 기능을 사용 하는 경우에는 [요금제를 수동으로 변경할](change-plans-manually.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-148">If you have an Add-on with your subscription, you might be able to [change plans manually](change-plans-manually.md).</span></span>

### <a name="your-subscription-has-an-unpaid-balance"></a><span data-ttu-id="8c2ff-149">구독의 잔액이 송장의</span><span class="sxs-lookup"><span data-stu-id="8c2ff-149">Your subscription has an unpaid balance</span></span>

<span data-ttu-id="8c2ff-150">이 문제를 해결 하려면 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> 페이지에서 구독을 찾은 다음 **청구** 섹션에서 **지금 결제** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-150">To resolve this, find the subscription on the <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page, and select the **Pay now** link in the **Billing** section.</span></span> <span data-ttu-id="8c2ff-151">지불이 끝나면 **업그레이드** 탭을 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2ff-151">After the payment has been made, check the **Upgrade** tab again.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="8c2ff-152">요금제를 변경 하는 데 도움이 되는 통화 지원</span><span class="sxs-lookup"><span data-stu-id="8c2ff-152">Call support to help you change plans</span></span>
[<span data-ttu-id="8c2ff-153">Microsoft 지원 서비스에 문의</span><span class="sxs-lookup"><span data-stu-id="8c2ff-153">Call Microsoft support</span></span>](../../admin/contact-support-for-business-products.md)
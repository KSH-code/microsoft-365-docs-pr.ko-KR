---
title: 조직의 소프트웨어 as-a-a-service 앱 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft 365 관리 센터에서 타사 앱을 활성화하고 관리하는 방법을 학습합니다.
ms.openlocfilehash: f560b23871fc6d6ecb319a5704453f2400cb9982
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911413"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="e25ea-103">조직의 타사 앱 구독 관리</span><span class="sxs-lookup"><span data-stu-id="e25ea-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="e25ea-104">새 Microsoft 365 관리 센터에서 타사 앱에 대한 라이선스 및 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="e25ea-105">업데이트된 기능에는 향상된 구독 관리, 청구 정보에 대한 액세스 향상, 청구 관리 유연성 향상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="e25ea-106">구독 관리는 Microsoft의 업데이트된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="e25ea-107">이는 고객이 직접 구매하는 소프트웨어 as-a-service 앱 또는 타사 공급자의 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e25ea-108">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-108">The admin center is changing.</span></span> <span data-ttu-id="e25ea-109">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e25ea-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e25ea-110">미리 보기 모드가 켜져 있는 Microsoft 365 관리 센터에서 타사 앱에 대한 라이선스 및 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="e25ea-111">업데이트된 기능에는 향상된 구독 관리, 청구 정보에 대한 액세스 향상, 청구 관리 유연성 향상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="e25ea-112">구독 관리는 Microsoft의 업데이트된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="e25ea-113">이는 고객이 직접 구매하는 소프트웨어 as-a-service 앱 또는 타사 공급자의 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="e25ea-114">서비스로 소프트웨어 앱을 다운로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="e25ea-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="e25ea-115">타사 앱을 구입하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="e25ea-116">**직접 구매** – 고객은 Azure [Marketplace](https://azuremarketplace.microsoft.com/marketplace/)또는 [AppSource에서](https://www.appsource.com/)직접 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="e25ea-117">**파트너 구매** – 파트너 센터를 통해 파트너와 협력하여 구독을 구매합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="e25ea-118">**Microsoft 제안** – 타사 앱을 포함하는 Microsoft Sales의 제안에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="e25ea-119">고객이 앱을 구매하고 Microsoft 고객 계약에 동의하면 Microsoft 365 관리 센터 또는 비즈니스용 Microsoft Store에서 앱을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="e25ea-120">앱 공급자는 앱을 단가로 판매하거나 사용자용 라이선스를 구입하여 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="e25ea-121">**플랫 요금** – 사이트 기반 가격이라고도 하는 앱은 월간 또는 연간 가격으로 가격을 책정합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="e25ea-122">앱 페이지에서 라이선스 수량은 Unlimited에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="e25ea-123">**라이선스** – 앱의 가격은 라이선스로 정해진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="e25ea-124">고객이 조직의 각 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="e25ea-125">지원되는 지역</span><span class="sxs-lookup"><span data-stu-id="e25ea-125">Supported regions</span></span>

<span data-ttu-id="e25ea-126">타사 앱에 대한 지원은 다음 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="e25ea-127">아르헨티나</span><span class="sxs-lookup"><span data-stu-id="e25ea-127">Argentina</span></span>
- <span data-ttu-id="e25ea-128">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="e25ea-128">Australia</span></span>
- <span data-ttu-id="e25ea-129">캐나다</span><span class="sxs-lookup"><span data-stu-id="e25ea-129">Canada</span></span>
- <span data-ttu-id="e25ea-130">칠레</span><span class="sxs-lookup"><span data-stu-id="e25ea-130">Chile</span></span>
- <span data-ttu-id="e25ea-131">프랑스</span><span class="sxs-lookup"><span data-stu-id="e25ea-131">France</span></span>
- <span data-ttu-id="e25ea-132">독일</span><span class="sxs-lookup"><span data-stu-id="e25ea-132">Germany</span></span>
- <span data-ttu-id="e25ea-133">그리스</span><span class="sxs-lookup"><span data-stu-id="e25ea-133">Greece</span></span>
- <span data-ttu-id="e25ea-134">푸에르토리코</span><span class="sxs-lookup"><span data-stu-id="e25ea-134">Puerto Rico</span></span>
- <span data-ttu-id="e25ea-135">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="e25ea-135">South Africa</span></span>
- <span data-ttu-id="e25ea-136">영국</span><span class="sxs-lookup"><span data-stu-id="e25ea-136">United Kingdom</span></span>
- <span data-ttu-id="e25ea-137">미국</span><span class="sxs-lookup"><span data-stu-id="e25ea-137">United States</span></span>
- <span data-ttu-id="e25ea-138">서유럽</span><span class="sxs-lookup"><span data-stu-id="e25ea-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="e25ea-139">타사 앱 활성화</span><span class="sxs-lookup"><span data-stu-id="e25ea-139">Activate third-party apps</span></span>

<span data-ttu-id="e25ea-140">관리자는 타사 앱을 사용자에게 할당하기 전에 정품 인증을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e25ea-141">이러한 앱은 타사 게시자의 포털에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="e25ea-142">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="e25ea-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e25ea-143">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e25ea-144">설정 **& 작업에서** 게시자의 **포털에서 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e25ea-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="e25ea-145">앱을 활성화할 수 있는 앱 게시자의 사이트로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="e25ea-146">타사 앱 관리</span><span class="sxs-lookup"><span data-stu-id="e25ea-146">Manage third-party apps</span></span>

<span data-ttu-id="e25ea-147">관리자는 Microsoft 365 관리 센터와 타사 앱 공급자 포털의 두 위치에서 타사 앱을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="e25ea-148">다음은 각 포털에서 할 수 있는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="e25ea-149">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="e25ea-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="e25ea-150">앱 게시자 포털</span><span class="sxs-lookup"><span data-stu-id="e25ea-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="e25ea-151">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="e25ea-151">Change license quantity</span></span> <br> <span data-ttu-id="e25ea-152">청구서 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="e25ea-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e25ea-153">청구서 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="e25ea-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e25ea-154">결제 방법 변경(신용 카드)</span><span class="sxs-lookup"><span data-stu-id="e25ea-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="e25ea-155">송장 보기</span><span class="sxs-lookup"><span data-stu-id="e25ea-155">View invoice</span></span> <br> <span data-ttu-id="e25ea-156">앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="e25ea-156">Cancel app subscription</span></span> | <span data-ttu-id="e25ea-157">앱 설정(각 앱에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="e25ea-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="e25ea-158">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="e25ea-158">Assign licenses to users</span></span> <br> <span data-ttu-id="e25ea-159">기술 지원</span><span class="sxs-lookup"><span data-stu-id="e25ea-159">Technical support</span></span> |

<span data-ttu-id="e25ea-160">앱이 활성화된 후 취소, 만료 또는 지급이 최신 상태로 유지되지 않는 한 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="e25ea-161">이러한 이벤트는 앱 상태를 사용하지 않도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-161">These events change the app status to disabled.</span></span> <span data-ttu-id="e25ea-162">앱을 사용하지 않도록 설정한 후 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="e25ea-163">앱을 계속 사용 하 여, 다른 복사본을 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="e25ea-164">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="e25ea-164">Assign licenses</span></span>

<span data-ttu-id="e25ea-165">관리자는 타사 앱을 사용자에게 할당하기 전에 정품 인증을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e25ea-166">이러한 사이트는 타사 게시자의 포털에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="e25ea-167">앱 페이지의 설정 & **작업에서** 라이선스를 할당할 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="e25ea-168">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="e25ea-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e25ea-169">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e25ea-170">설정 **& 작업에서** 게시자 포털에서 **관리로 연결되는 링크를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e25ea-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="e25ea-171">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="e25ea-171">Change license quantity</span></span>

<span data-ttu-id="e25ea-172">관리자는 조직에서 소유한 라이선스 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="e25ea-173">이 설정은 사용자 수 기준 가격으로 구매한 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="e25ea-174">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="e25ea-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e25ea-175">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e25ea-176">라이선스 **수량 변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e25ea-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="e25ea-177">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="e25ea-177">Manage payment methods</span></span>

<span data-ttu-id="e25ea-178">As-a-Service 앱에는 각각 청구 프로필이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="e25ea-179">청구 프로필을 사용하면 송장에 포함된 제품과 송장 결제 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="e25ea-180">주요 관련자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-180">They include:</span></span>

- <span data-ttu-id="e25ea-181">**결제 방법** - 신용 카드 또는 수표/송금</span><span class="sxs-lookup"><span data-stu-id="e25ea-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="e25ea-182">**연락처 정보** - 청구 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="e25ea-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="e25ea-183">**역할** - 청구 프로필을 변경하거나, 청구서를 지불하거나, 청구 프로필에서 결제 방법을 사용하여 구매할 수 있는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="e25ea-184">청구 프로필에 대한 자세한 내용은 청구 프로필 이해를 [참조하세요.](/microsoft-store/billing-profile)</span><span class="sxs-lookup"><span data-stu-id="e25ea-184">For more information on billing profiles, see [Understand billing profiles](/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e25ea-185">소프트웨어 as-a-service 앱 구독에서 청구 프로필 변경</span><span class="sxs-lookup"><span data-stu-id="e25ea-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="e25ea-186">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="e25ea-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e25ea-187">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e25ea-188">청구 프로필 **옆에 있는** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e25ea-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="e25ea-189">송장에 대한 자세한 내용은 청구서 또는 [송장 이해를 참조하세요.](billing-and-payments/understand-your-invoice.md)</span><span class="sxs-lookup"><span data-stu-id="e25ea-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e25ea-190">서비스용 소프트웨어 앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="e25ea-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="e25ea-191">앱 페이지에서 서비스로 소프트웨어 앱을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="e25ea-192">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="e25ea-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e25ea-193">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e25ea-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e25ea-194">설정 **& 작업에서** 구독 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e25ea-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>
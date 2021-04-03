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
ms.openlocfilehash: 974ce99b55dcb078286d7f6dba35166e51ce62a7
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576916"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="92337-103">조직의 타사 앱 구독 관리</span><span class="sxs-lookup"><span data-stu-id="92337-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="92337-104">새 Microsoft 365 관리 센터에서 타사 앱에 대한 라이선스 및 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="92337-105">업데이트된 기능에는 향상된 구독 관리, 청구 정보에 대한 액세스 향상, 청구 관리 유연성 향상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="92337-106">구독 관리는 Microsoft의 업데이트된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="92337-107">이는 고객이 직접 구매하는 소프트웨어 as-a-service 앱 또는 타사 공급자의 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

<span data-ttu-id="92337-108">미리 보기 모드가 켜져 있는 Microsoft 365 관리 센터에서 타사 앱에 대한 라이선스 및 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-108">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="92337-109">업데이트된 기능에는 향상된 구독 관리, 청구 정보에 대한 액세스 향상, 청구 관리 유연성 향상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-109">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="92337-110">구독 관리는 Microsoft의 업데이트된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-110">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="92337-111">이는 고객이 직접 구매하는 소프트웨어 as-a-service 앱 또는 타사 공급자의 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-111">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="92337-112">서비스로 소프트웨어 앱을 다운로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="92337-112">How to get software-as-a-service apps</span></span>

<span data-ttu-id="92337-113">타사 앱을 구입하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-113">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="92337-114">**직접 구매** – 고객은 Azure [Marketplace](https://azuremarketplace.microsoft.com/marketplace/)또는 [AppSource에서](https://www.appsource.com/)직접 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-114">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="92337-115">**파트너 구매** – 파트너 센터를 통해 파트너와 협력하여 구독을 구매합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-115">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="92337-116">**Microsoft 제안** – 타사 앱을 포함하는 Microsoft Sales의 제안에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-116">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="92337-117">고객이 앱을 구매하고 Microsoft 고객 계약에 동의하면 Microsoft 365 관리 센터 또는 비즈니스용 Microsoft Store에서 앱을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-117">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="92337-118">앱 공급자는 앱을 단가로 판매하거나 사용자용 라이선스를 구입하여 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-118">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="92337-119">**플랫 요금** – 사이트 기반 가격이라고도 하는 앱은 월간 또는 연간 가격으로 가격을 책정합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-119">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="92337-120">앱 페이지에서 라이선스 수량은 Unlimited에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-120">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="92337-121">**라이선스** – 앱의 가격은 라이선스로 정해진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92337-121">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="92337-122">고객이 조직의 각 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-122">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="92337-123">지원되는 지역</span><span class="sxs-lookup"><span data-stu-id="92337-123">Supported regions</span></span>

<span data-ttu-id="92337-124">타사 앱에 대한 지원은 다음 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-124">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="92337-125">아르헨티나</span><span class="sxs-lookup"><span data-stu-id="92337-125">Argentina</span></span>
- <span data-ttu-id="92337-126">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="92337-126">Australia</span></span>
- <span data-ttu-id="92337-127">캐나다</span><span class="sxs-lookup"><span data-stu-id="92337-127">Canada</span></span>
- <span data-ttu-id="92337-128">칠레</span><span class="sxs-lookup"><span data-stu-id="92337-128">Chile</span></span>
- <span data-ttu-id="92337-129">프랑스</span><span class="sxs-lookup"><span data-stu-id="92337-129">France</span></span>
- <span data-ttu-id="92337-130">독일</span><span class="sxs-lookup"><span data-stu-id="92337-130">Germany</span></span>
- <span data-ttu-id="92337-131">그리스</span><span class="sxs-lookup"><span data-stu-id="92337-131">Greece</span></span>
- <span data-ttu-id="92337-132">푸에르토리코</span><span class="sxs-lookup"><span data-stu-id="92337-132">Puerto Rico</span></span>
- <span data-ttu-id="92337-133">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="92337-133">South Africa</span></span>
- <span data-ttu-id="92337-134">영국</span><span class="sxs-lookup"><span data-stu-id="92337-134">United Kingdom</span></span>
- <span data-ttu-id="92337-135">미국</span><span class="sxs-lookup"><span data-stu-id="92337-135">United States</span></span>
- <span data-ttu-id="92337-136">서유럽</span><span class="sxs-lookup"><span data-stu-id="92337-136">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="92337-137">타사 앱 활성화</span><span class="sxs-lookup"><span data-stu-id="92337-137">Activate third-party apps</span></span>

<span data-ttu-id="92337-138">관리자는 타사 앱을 사용자에게 할당하기 전에 정품 인증을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-138">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="92337-139">이러한 앱은 타사 게시자의 포털에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-139">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="92337-140">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="92337-140">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="92337-141">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-141">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="92337-142">설정 **& 작업에서** 게시자의 **포털에서 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92337-142">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="92337-143">앱을 활성화할 수 있는 앱 게시자의 사이트로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-143">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="92337-144">타사 앱 관리</span><span class="sxs-lookup"><span data-stu-id="92337-144">Manage third-party apps</span></span>

<span data-ttu-id="92337-145">관리자는 Microsoft 365 관리 센터와 타사 앱 공급자 포털의 두 위치에서 타사 앱을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-145">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="92337-146">다음은 각 포털에서 할 수 있는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="92337-146">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="92337-147">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="92337-147">Microsoft 365 admin center</span></span> | <span data-ttu-id="92337-148">앱 게시자 포털</span><span class="sxs-lookup"><span data-stu-id="92337-148">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="92337-149">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="92337-149">Change license quantity</span></span> <br> <span data-ttu-id="92337-150">청구서 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="92337-150">Manage how you pay your bill</span></span> <br> <span data-ttu-id="92337-151">청구서 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="92337-151">Manage how you pay your bill</span></span> <br> <span data-ttu-id="92337-152">결제 방법 변경(신용 카드)</span><span class="sxs-lookup"><span data-stu-id="92337-152">Change payment method (credit card)</span></span> <br> <span data-ttu-id="92337-153">송장 보기</span><span class="sxs-lookup"><span data-stu-id="92337-153">View invoice</span></span> <br> <span data-ttu-id="92337-154">앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="92337-154">Cancel app subscription</span></span> | <span data-ttu-id="92337-155">앱 설정(각 앱에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="92337-155">Set up app (once for each app)</span></span> <br> <span data-ttu-id="92337-156">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="92337-156">Assign licenses to users</span></span> <br> <span data-ttu-id="92337-157">기술 지원</span><span class="sxs-lookup"><span data-stu-id="92337-157">Technical support</span></span> |

<span data-ttu-id="92337-158">앱이 활성화된 후 취소, 만료 또는 지급이 최신 상태로 유지되지 않는 한 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-158">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="92337-159">이러한 이벤트는 앱 상태를 사용하지 않도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-159">These events change the app status to disabled.</span></span> <span data-ttu-id="92337-160">앱을 사용하지 않도록 설정한 후 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-160">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="92337-161">앱을 계속 사용 하 여, 다른 복사본을 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-161">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="92337-162">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="92337-162">Assign licenses</span></span>

<span data-ttu-id="92337-163">관리자는 타사 앱을 사용자에게 할당하기 전에 정품 인증을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-163">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="92337-164">이러한 사이트는 타사 게시자의 포털에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-164">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="92337-165">앱 페이지의 설정 & **작업에서** 라이선스를 할당할 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-165">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="92337-166">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="92337-166">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="92337-167">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-167">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="92337-168">설정 **& 작업에서** 게시자 포털에서 **관리로 연결되는 링크를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92337-168">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="92337-169">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="92337-169">Change license quantity</span></span>

<span data-ttu-id="92337-170">관리자는 조직에서 소유한 라이선스 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-170">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="92337-171">이 설정은 사용자 수 기준 가격으로 구매한 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-171">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="92337-172">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="92337-172">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="92337-173">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-173">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="92337-174">라이선스 **수량 변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92337-174">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="92337-175">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="92337-175">Manage payment methods</span></span>

<span data-ttu-id="92337-176">As-a-Service 앱에는 각각 청구 프로필이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-176">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="92337-177">청구 프로필을 사용하면 송장에 포함된 제품과 송장 결제 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-177">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="92337-178">다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="92337-178">They include:</span></span>

- <span data-ttu-id="92337-179">**결제 방법** - 신용 카드 또는 수표/송금</span><span class="sxs-lookup"><span data-stu-id="92337-179">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="92337-180">**연락처 정보** - 청구 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="92337-180">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="92337-181">**역할** - 청구 프로필을 변경하거나, 청구서를 지불하거나, 청구 프로필에서 결제 방법을 사용하여 구매할 수 있는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="92337-181">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="92337-182">청구 프로필에 대한 자세한 내용은 청구 프로필 이해를 [참조하세요.](/microsoft-store/billing-profile)</span><span class="sxs-lookup"><span data-stu-id="92337-182">For more information on billing profiles, see [Understand billing profiles](/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="92337-183">소프트웨어 as-a-service 앱 구독에서 청구 프로필 변경</span><span class="sxs-lookup"><span data-stu-id="92337-183">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="92337-184">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="92337-184">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="92337-185">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-185">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="92337-186">청구 프로필 **옆에 있는** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92337-186">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="92337-187">송장에 대한 자세한 내용은 청구서 또는 [송장 이해를 참조하세요.](billing-and-payments/understand-your-invoice.md)</span><span class="sxs-lookup"><span data-stu-id="92337-187">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="92337-188">서비스용 소프트웨어 앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="92337-188">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="92337-189">앱 페이지에서 서비스로 소프트웨어 앱을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92337-189">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="92337-190">관리 센터에서 청구 제품 앱  >  **페이지로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">이동합니다.</a></span><span class="sxs-lookup"><span data-stu-id="92337-190">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="92337-191">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92337-191">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="92337-192">설정 **& 작업에서** 구독 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="92337-192">Under **Settings & actions**, select **Cancel subscription**.</span></span>
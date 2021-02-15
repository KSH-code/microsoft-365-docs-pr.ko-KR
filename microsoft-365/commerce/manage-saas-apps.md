---
title: 조직에 대한 서비스형 소프트웨어 앱 관리
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
ms.openlocfilehash: 071f95c838620fb11350a829cbfed249e7c34f6e
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114720"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="9b95c-103">조직의 타사 앱 구독 관리</span><span class="sxs-lookup"><span data-stu-id="9b95c-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="9b95c-104">새 Microsoft 365 관리 센터에서 타사 앱에 대한 라이선스 및 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="9b95c-105">업데이트된 기능에는 향상된 구독 관리, 청구 정보에 대한 향상된 액세스, 청구 관리 유연성 향상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="9b95c-106">구독 관리는 Microsoft의 업데이트된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="9b95c-107">이는 고객이 직접 구매하는 소프트웨어 as-a-service 앱 또는 타사 공급자의 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9b95c-108">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-108">The admin center is changing.</span></span> <span data-ttu-id="9b95c-109">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b95c-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="9b95c-110">미리 보기 모드가 켜져 있는 Microsoft 365 관리 센터에서 타사 앱에 대한 라이선스 및 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="9b95c-111">업데이트된 기능에는 향상된 구독 관리, 청구 정보에 대한 향상된 액세스, 청구 관리 유연성 향상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="9b95c-112">구독 관리는 Microsoft의 업데이트된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="9b95c-113">이는 고객이 직접 구매하는 소프트웨어 as-a-service 앱 또는 타사 공급자의 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="9b95c-114">서비스용 소프트웨어 앱을 다운로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="9b95c-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="9b95c-115">타사 앱을 구입하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="9b95c-116">**직접 구매** - 고객이 Azure [Marketplace](https://azuremarketplace.microsoft.com/marketplace/)또는 [AppSource에서](https://www.appsource.com/)직접 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="9b95c-117">**파트너 구매** – 파트너 센터를 통해 파트너와 협력하여 구독을 구매합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="9b95c-118">**Microsoft 제안** - 타사 앱을 포함하는 Microsoft Sales의 제안에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="9b95c-119">고객이 앱을 구매하고 Microsoft 고객 계약에 동의하면 Microsoft 365 관리 센터 또는 비즈니스용 Microsoft Store에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="9b95c-120">앱 공급자는 앱을 단가로 판매하거나 사용자용 라이선스를 구입하여 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="9b95c-121">**정가** – 사이트 기반 가격 책정이라고도 하는 앱은 월별 또는 연간 가격으로 가격이 책정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="9b95c-122">앱 페이지에서 라이선스 수량은 무제한으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="9b95c-123">**라이선스** - 앱의 가격은 라이선스로 정해진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="9b95c-124">고객이 조직의 각 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="9b95c-125">지원되는 지역</span><span class="sxs-lookup"><span data-stu-id="9b95c-125">Supported regions</span></span>

<span data-ttu-id="9b95c-126">타사 앱에 대한 지원은 다음 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="9b95c-127">아르헨티나</span><span class="sxs-lookup"><span data-stu-id="9b95c-127">Argentina</span></span>
- <span data-ttu-id="9b95c-128">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="9b95c-128">Australia</span></span>
- <span data-ttu-id="9b95c-129">캐나다</span><span class="sxs-lookup"><span data-stu-id="9b95c-129">Canada</span></span>
- <span data-ttu-id="9b95c-130">칠레</span><span class="sxs-lookup"><span data-stu-id="9b95c-130">Chile</span></span>
- <span data-ttu-id="9b95c-131">프랑스</span><span class="sxs-lookup"><span data-stu-id="9b95c-131">France</span></span>
- <span data-ttu-id="9b95c-132">독일</span><span class="sxs-lookup"><span data-stu-id="9b95c-132">Germany</span></span>
- <span data-ttu-id="9b95c-133">그리스</span><span class="sxs-lookup"><span data-stu-id="9b95c-133">Greece</span></span>
- <span data-ttu-id="9b95c-134">푸에르토리코</span><span class="sxs-lookup"><span data-stu-id="9b95c-134">Puerto Rico</span></span>
- <span data-ttu-id="9b95c-135">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="9b95c-135">South Africa</span></span>
- <span data-ttu-id="9b95c-136">영국</span><span class="sxs-lookup"><span data-stu-id="9b95c-136">United Kingdom</span></span>
- <span data-ttu-id="9b95c-137">미국</span><span class="sxs-lookup"><span data-stu-id="9b95c-137">United States</span></span>
- <span data-ttu-id="9b95c-138">서유럽</span><span class="sxs-lookup"><span data-stu-id="9b95c-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="9b95c-139">타사 앱 활성화</span><span class="sxs-lookup"><span data-stu-id="9b95c-139">Activate third-party apps</span></span>

<span data-ttu-id="9b95c-140">관리자는 타사 앱을 사용자에게 할당하기 전에 정품 인증을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="9b95c-141">이러한 앱은 타사 게시자의 포털에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="9b95c-142">관리 센터에서 청구 제품   >  **앱**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="9b95c-143">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="9b95c-144">설정 **& 작업** 아래에서 게시자의 **포털에서 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b95c-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="9b95c-145">앱을 활성화할 수 있는 앱 게시자의 사이트로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="9b95c-146">타사 앱 관리</span><span class="sxs-lookup"><span data-stu-id="9b95c-146">Manage third-party apps</span></span>

<span data-ttu-id="9b95c-147">관리자는 Microsoft 365 관리 센터와 타사 앱 공급자 포털의 두 위치에서 타사 앱을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="9b95c-148">다음은 각 포털에서 할 수 있는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="9b95c-149">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="9b95c-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="9b95c-150">앱 게시자 포털</span><span class="sxs-lookup"><span data-stu-id="9b95c-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="9b95c-151">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="9b95c-151">Change license quantity</span></span> <br> <span data-ttu-id="9b95c-152">청구서 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="9b95c-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="9b95c-153">청구서 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="9b95c-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="9b95c-154">결제 방법 변경(신용 카드)</span><span class="sxs-lookup"><span data-stu-id="9b95c-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="9b95c-155">송장 보기</span><span class="sxs-lookup"><span data-stu-id="9b95c-155">View invoice</span></span> <br> <span data-ttu-id="9b95c-156">앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="9b95c-156">Cancel app subscription</span></span> | <span data-ttu-id="9b95c-157">앱 설정(각 앱에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="9b95c-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="9b95c-158">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9b95c-158">Assign licenses to users</span></span> <br> <span data-ttu-id="9b95c-159">기술 지원</span><span class="sxs-lookup"><span data-stu-id="9b95c-159">Technical support</span></span> |

<span data-ttu-id="9b95c-160">앱이 활성화된 후 취소, 만료 또는 지급이 최신 상태로 유지되지 않는 한 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="9b95c-161">이러한 이벤트는 앱 상태를 사용하지 않도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-161">These events change the app status to disabled.</span></span> <span data-ttu-id="9b95c-162">앱을 사용하지 않도록 설정하면 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="9b95c-163">앱을 계속 사용하세우기 위해 다른 복사본을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="9b95c-164">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9b95c-164">Assign licenses</span></span>

<span data-ttu-id="9b95c-165">관리자는 타사 앱을 사용자에게 할당하기 전에 정품 인증을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="9b95c-166">타사 게시자의 포털에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="9b95c-167">앱 페이지의 설정 및 & 라이선스를 할당할 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="9b95c-168">관리 센터에서 청구 제품   >  **앱**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="9b95c-169">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="9b95c-170">설정 **& 작업에서** 게시자의 포털에서 관리 링크를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b95c-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="9b95c-171">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="9b95c-171">Change license quantity</span></span>

<span data-ttu-id="9b95c-172">관리자는 조직 소유의 라이선스 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="9b95c-173">이는 사용자 수 기준 가격으로 구매한 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="9b95c-174">관리 센터에서 청구 제품   >  **앱**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="9b95c-175">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="9b95c-176">라이선스 **수량 변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b95c-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="9b95c-177">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="9b95c-177">Manage payment methods</span></span>

<span data-ttu-id="9b95c-178">서비스용 소프트웨어 앱에는 각각 청구 프로필이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="9b95c-179">청구 프로필을 사용하면 송장에 포함된 제품과 송장 결제 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="9b95c-180">주요 관련자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-180">They include:</span></span>

- <span data-ttu-id="9b95c-181">**결제 방법** - 신용 카드 또는 수표/송금</span><span class="sxs-lookup"><span data-stu-id="9b95c-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="9b95c-182">**연락처 정보** - 대금 청구 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="9b95c-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="9b95c-183">**역할** - 청구 프로필을 변경하거나, 청구서를 지불하거나, 청구 프로필에서 결제 방법을 사용하여 구매할 수 있도록 하는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="9b95c-184">청구 프로필에 대한 자세한 내용은 청구 프로필 [이해를 참조하세요.](https://docs.microsoft.com/microsoft-store/billing-profile)</span><span class="sxs-lookup"><span data-stu-id="9b95c-184">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="9b95c-185">서비스용 소프트웨어 앱 구독에서 청구 프로필 변경</span><span class="sxs-lookup"><span data-stu-id="9b95c-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="9b95c-186">관리 센터에서 청구 제품   >  **앱**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="9b95c-187">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="9b95c-188">청구 프로필 **옆에서** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b95c-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="9b95c-189">송장에 대한 자세한 내용은 청구서 또는 [송장 이해를 참조하세요.](billing-and-payments/understand-your-invoice.md)</span><span class="sxs-lookup"><span data-stu-id="9b95c-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="9b95c-190">서비스용 소프트웨어 앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="9b95c-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="9b95c-191">앱 페이지에서 서비스용 소프트웨어 앱을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="9b95c-192">관리 센터에서 청구 제품   >  **앱**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="9b95c-193">관리할 앱을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b95c-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="9b95c-194">설정 **& 아래에서** 구독 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b95c-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>
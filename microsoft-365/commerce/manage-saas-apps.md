---
title: 조직에 대 한 소프트웨어 as-서비스 앱 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft 365 관리 센터에서 타사 앱을 활성화 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ed1a88345ae5cc135a43f4297ce518b444eaabe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402585"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="91f52-103">조직에 대 한 타사 앱 구독 관리</span><span class="sxs-lookup"><span data-stu-id="91f52-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="91f52-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-104">The admin center is changing.</span></span> <span data-ttu-id="91f52-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91f52-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="91f52-106">미리 보기 모드를 설정한 상태에서 Microsoft 365 관리 센터의 타사 앱에 대 한 라이선스 및 대금 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="91f52-107">업데이트 된 기능으로는 향상 되는 구독 관리, 대금 청구 정보에 대 한 액세스 향상, 비용 관리 유연성 향상 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="91f52-108">구독 관리는 Microsoft의 업데이트 된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="91f52-109">이는 고객이 직접 구입 하거나 타사 공급자 로부터 제공 하는 서비스와 동일한 소프트웨어에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="91f52-110">서비스를 제공 하는 소프트웨어 앱을 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="91f52-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="91f52-111">타사 앱을 구입 하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="91f52-112">**직접 구매** -고객은 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)또는 [appsource](https://www.appsource.com/)에서 구독을 직접 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="91f52-113">**파트너 구매** -구독을 구매 하기 위해 파트너 센터를 통해 파트너와 협력 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="91f52-114">**Microsoft 제안서** -타사 앱이 포함 된 microsoft Sales의 제안에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="91f52-115">고객이 앱을 구입 하 고 Microsoft 고객 계약에 동의 하면 Microsoft 365 관리 센터 또는 Microsoft Store for Business에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="91f52-116">앱 공급자는 사용자에 대 한 라이선스를 구입 하 여 또는 일반 속도로 앱을 판매 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="91f52-117">**단층 속도** -사이트 기반 가격 산정이 라고도 하며, 앱은 월별 또는 연간 가격으로 가격이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="91f52-118">앱 페이지에서 라이선스 수량이 무제한으로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="91f52-119">**라이선스** -앱이 라이선스로 가격이 책정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="91f52-120">고객은 조직의 각 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="91f52-121">지원 지역</span><span class="sxs-lookup"><span data-stu-id="91f52-121">Supported regions</span></span>

<span data-ttu-id="91f52-122">타사 앱에 대 한 지원은 다음 지역에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="91f52-123">아르헨티나</span><span class="sxs-lookup"><span data-stu-id="91f52-123">Argentina</span></span>
- <span data-ttu-id="91f52-124">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="91f52-124">Australia</span></span>
- <span data-ttu-id="91f52-125">캐나다</span><span class="sxs-lookup"><span data-stu-id="91f52-125">Canada</span></span>
- <span data-ttu-id="91f52-126">칠레</span><span class="sxs-lookup"><span data-stu-id="91f52-126">Chile</span></span>
- <span data-ttu-id="91f52-127">프랑스</span><span class="sxs-lookup"><span data-stu-id="91f52-127">France</span></span>
- <span data-ttu-id="91f52-128">독일</span><span class="sxs-lookup"><span data-stu-id="91f52-128">Germany</span></span>
- <span data-ttu-id="91f52-129">그리스</span><span class="sxs-lookup"><span data-stu-id="91f52-129">Greece</span></span>
- <span data-ttu-id="91f52-130">푸에르토리코</span><span class="sxs-lookup"><span data-stu-id="91f52-130">Puerto Rico</span></span>
- <span data-ttu-id="91f52-131">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="91f52-131">South Africa</span></span>
- <span data-ttu-id="91f52-132">영국</span><span class="sxs-lookup"><span data-stu-id="91f52-132">United Kingdom</span></span>
- <span data-ttu-id="91f52-133">미국</span><span class="sxs-lookup"><span data-stu-id="91f52-133">United States</span></span>
- <span data-ttu-id="91f52-134">서유럽</span><span class="sxs-lookup"><span data-stu-id="91f52-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="91f52-135">타사 앱 정품 인증</span><span class="sxs-lookup"><span data-stu-id="91f52-135">Activate third-party apps</span></span>

<span data-ttu-id="91f52-136">관리자는 타사 앱을 사용자에 게 할당 하기 전에 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="91f52-137">이러한 앱은 타사 게시자 포털에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="91f52-138">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91f52-139">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91f52-140">**작업 설정 &** 에서 **Publisher 포털에서 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="91f52-141">앱을 정품 인증할 수 있는 앱 게시자의 사이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="91f52-142">타사 앱 관리</span><span class="sxs-lookup"><span data-stu-id="91f52-142">Manage third-party apps</span></span>

<span data-ttu-id="91f52-143">관리자는 타사 앱을 Microsoft 365 관리 센터 및 타사 앱 공급자 포털의 두 위치에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="91f52-144">각 포털에서 수행할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="91f52-145">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="91f52-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="91f52-146">앱 게시자 포털</span><span class="sxs-lookup"><span data-stu-id="91f52-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="91f52-147">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="91f52-147">Change license quantity</span></span> <br> <span data-ttu-id="91f52-148">청구 비용 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="91f52-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="91f52-149">청구 비용 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="91f52-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="91f52-150">결제 방법 변경 (신용 카드)</span><span class="sxs-lookup"><span data-stu-id="91f52-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="91f52-151">송장 보기</span><span class="sxs-lookup"><span data-stu-id="91f52-151">View invoice</span></span> <br> <span data-ttu-id="91f52-152">앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="91f52-152">Cancel app subscription</span></span> | <span data-ttu-id="91f52-153">앱 설정 (각 앱에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="91f52-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="91f52-154">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="91f52-154">Assign licenses to users</span></span> <br> <span data-ttu-id="91f52-155">기술 지원</span><span class="sxs-lookup"><span data-stu-id="91f52-155">Technical support</span></span> |

<span data-ttu-id="91f52-156">앱이 활성화 된 후에는 취소 되거나 만료 되거나 지불 되지 않는 경우에만 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="91f52-157">이러한 이벤트는 앱 상태를 사용 안 함으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-157">These events change the app status to disabled.</span></span> <span data-ttu-id="91f52-158">앱이 사용 하지 않도록 설정 되 면 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="91f52-159">앱을 계속 사용 하려면 다른 복사본을 구입 하세요.</span><span class="sxs-lookup"><span data-stu-id="91f52-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="91f52-160">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="91f52-160">Assign licenses</span></span>

<span data-ttu-id="91f52-161">관리자는 타사 앱을 사용자에 게 할당 하기 전에 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="91f52-162">타사 게시자 포털에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="91f52-163">앱 페이지의 **설정 & 작업**에서 라이선스를 할당 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="91f52-164">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91f52-165">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91f52-166">**작업 설정 &** 에서 **Publisher 포털에서 관리할**링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="91f52-167">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="91f52-167">Change license quantity</span></span>

<span data-ttu-id="91f52-168">관리자는 조직에서 소유한 라이선스 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="91f52-169">이는 사용자의 중심 가격을 사용 하 여 구매한 앱에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="91f52-170">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91f52-171">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91f52-172">**라이선스 수량 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="91f52-173">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="91f52-173">Manage payment methods</span></span>

<span data-ttu-id="91f52-174">서비스를 포함 하는 앱은 각각 대금 청구 프로필을 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="91f52-175">청구 프로필을 사용 하 여 송장에 포함 되는 제품을 사용자 지정 하 고 청구서 비용을 지불 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="91f52-176">주요 관련자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-176">They include:</span></span>

- <span data-ttu-id="91f52-177">**결제 방법** -신용 카드 또는 확인/회선 전송</span><span class="sxs-lookup"><span data-stu-id="91f52-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="91f52-178">**연락처 정보** -청구지 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="91f52-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="91f52-179">**역할** -대금 청구 프로필을 변경 하거나, 청구서를 지불 하거나, 대금 청구 프로필에서 결제 방법을 사용 하 여 구매를 수행할 수 있도록 하는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="91f52-180">대금 청구 프로필에 대 한 자세한 내용은 [청구 프로필 이해](https://docs.microsoft.com/microsoft-store/billing-profile)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91f52-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="91f52-181">서비스를 사용 하는 소프트웨어 앱 구독에서 대금 청구 프로필 변경</span><span class="sxs-lookup"><span data-stu-id="91f52-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="91f52-182">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91f52-183">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91f52-184">**청구 프로필**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="91f52-185">송장에 대 한 자세한 내용은 [청구서 또는 송장 이해](billing-and-payments/understand-your-invoice.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91f52-185">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="91f52-186">서비스를 사용 하는 소프트웨어 앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="91f52-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="91f52-187">앱 페이지에서 서비스를 통해 소프트웨어 앱을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="91f52-188">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91f52-189">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91f52-190">**작업 설정 &** 에서 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91f52-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>

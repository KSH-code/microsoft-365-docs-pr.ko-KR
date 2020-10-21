---
title: 조직에 대 한 소프트웨어 as-서비스 앱 관리
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
description: Microsoft 365 관리 센터에서 타사 앱을 활성화 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c1565f0edb2f78302c0186aa3bd89d1ff5a51e5c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638174"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="8302f-103">조직에 대 한 타사 앱 구독 관리</span><span class="sxs-lookup"><span data-stu-id="8302f-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="8302f-104">새 Microsoft 365 관리 센터에서 타사 앱에 대 한 라이선스 및 대금 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="8302f-105">업데이트 된 기능으로는 향상 되는 구독 관리, 대금 청구 정보에 대 한 액세스 향상, 비용 관리 유연성 향상 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="8302f-106">구독 관리는 Microsoft의 업데이트 된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="8302f-107">이는 고객이 직접 구입 하거나 타사 공급자가 제공 하는 소프트웨어 as-서비스 앱에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8302f-108">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-108">The admin center is changing.</span></span> <span data-ttu-id="8302f-109">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8302f-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8302f-110">미리 보기 모드를 설정한 상태에서 Microsoft 365 관리 센터의 타사 앱에 대 한 라이선스 및 대금 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="8302f-111">업데이트 된 기능으로는 향상 되는 구독 관리, 대금 청구 정보에 대 한 액세스 향상, 비용 관리 유연성 향상 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="8302f-112">구독 관리는 Microsoft의 업데이트 된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="8302f-113">이는 고객이 직접 구입 하거나 타사 공급자 로부터 제공 하는 서비스와 동일한 소프트웨어에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="8302f-114">서비스를 제공 하는 소프트웨어 앱을 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="8302f-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="8302f-115">타사 앱을 구입 하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="8302f-116">**직접 구매** -고객은 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)또는 [appsource](https://www.appsource.com/)에서 구독을 직접 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="8302f-117">**파트너 구매** -구독을 구매 하기 위해 파트너 센터를 통해 파트너와 협력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="8302f-118">**Microsoft 제안서** -타사 앱이 포함 된 microsoft Sales의 제안에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="8302f-119">고객이 앱을 구입 하 고 Microsoft 고객 계약에 동의 하면 Microsoft 365 관리 센터 또는 Microsoft Store for Business에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="8302f-120">앱 공급자는 사용자에 대 한 라이선스를 구입 하 여 또는 일반 속도로 앱을 판매 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="8302f-121">**단층 속도** -사이트 기반 가격 산정이 라고도 하며, 앱은 월별 또는 연간 가격으로 가격이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="8302f-122">앱 페이지에서 라이선스 수량이 무제한으로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="8302f-123">**라이선스** -앱이 라이선스로 가격이 책정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="8302f-124">고객은 조직의 각 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="8302f-125">지원 지역</span><span class="sxs-lookup"><span data-stu-id="8302f-125">Supported regions</span></span>

<span data-ttu-id="8302f-126">타사 앱에 대 한 지원은 다음 지역에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="8302f-127">아르헨티나</span><span class="sxs-lookup"><span data-stu-id="8302f-127">Argentina</span></span>
- <span data-ttu-id="8302f-128">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="8302f-128">Australia</span></span>
- <span data-ttu-id="8302f-129">캐나다</span><span class="sxs-lookup"><span data-stu-id="8302f-129">Canada</span></span>
- <span data-ttu-id="8302f-130">칠레</span><span class="sxs-lookup"><span data-stu-id="8302f-130">Chile</span></span>
- <span data-ttu-id="8302f-131">프랑스</span><span class="sxs-lookup"><span data-stu-id="8302f-131">France</span></span>
- <span data-ttu-id="8302f-132">독일</span><span class="sxs-lookup"><span data-stu-id="8302f-132">Germany</span></span>
- <span data-ttu-id="8302f-133">그리스</span><span class="sxs-lookup"><span data-stu-id="8302f-133">Greece</span></span>
- <span data-ttu-id="8302f-134">푸에르토리코</span><span class="sxs-lookup"><span data-stu-id="8302f-134">Puerto Rico</span></span>
- <span data-ttu-id="8302f-135">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="8302f-135">South Africa</span></span>
- <span data-ttu-id="8302f-136">영국</span><span class="sxs-lookup"><span data-stu-id="8302f-136">United Kingdom</span></span>
- <span data-ttu-id="8302f-137">미국</span><span class="sxs-lookup"><span data-stu-id="8302f-137">United States</span></span>
- <span data-ttu-id="8302f-138">서유럽</span><span class="sxs-lookup"><span data-stu-id="8302f-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="8302f-139">타사 앱 정품 인증</span><span class="sxs-lookup"><span data-stu-id="8302f-139">Activate third-party apps</span></span>

<span data-ttu-id="8302f-140">관리자는 타사 앱을 사용자에 게 할당 하기 전에 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="8302f-141">이러한 앱은 타사 게시자 포털에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="8302f-142">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8302f-143">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8302f-144">**작업 설정 &** 에서 **Publisher 포털에서 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="8302f-145">앱을 정품 인증할 수 있는 앱 게시자의 사이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="8302f-146">타사 앱 관리</span><span class="sxs-lookup"><span data-stu-id="8302f-146">Manage third-party apps</span></span>

<span data-ttu-id="8302f-147">관리자는 타사 앱을 Microsoft 365 관리 센터 및 타사 앱 공급자 포털의 두 위치에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="8302f-148">각 포털에서 수행할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="8302f-149">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="8302f-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="8302f-150">앱 게시자 포털</span><span class="sxs-lookup"><span data-stu-id="8302f-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="8302f-151">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="8302f-151">Change license quantity</span></span> <br> <span data-ttu-id="8302f-152">청구 비용 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8302f-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="8302f-153">청구 비용 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8302f-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="8302f-154">결제 방법 변경 (신용 카드)</span><span class="sxs-lookup"><span data-stu-id="8302f-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="8302f-155">송장 보기</span><span class="sxs-lookup"><span data-stu-id="8302f-155">View invoice</span></span> <br> <span data-ttu-id="8302f-156">앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="8302f-156">Cancel app subscription</span></span> | <span data-ttu-id="8302f-157">앱 설정 (각 앱에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="8302f-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="8302f-158">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8302f-158">Assign licenses to users</span></span> <br> <span data-ttu-id="8302f-159">기술 지원</span><span class="sxs-lookup"><span data-stu-id="8302f-159">Technical support</span></span> |

<span data-ttu-id="8302f-160">앱이 활성화 된 후에는 취소 되거나 만료 되거나 지불 되지 않는 경우에만 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="8302f-161">이러한 이벤트는 앱 상태를 사용 안 함으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-161">These events change the app status to disabled.</span></span> <span data-ttu-id="8302f-162">앱이 사용 하지 않도록 설정 되 면 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="8302f-163">앱을 계속 사용 하려면 다른 복사본을 구입 하세요.</span><span class="sxs-lookup"><span data-stu-id="8302f-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="8302f-164">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8302f-164">Assign licenses</span></span>

<span data-ttu-id="8302f-165">관리자는 타사 앱을 사용자에 게 할당 하기 전에 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="8302f-166">타사 게시자 포털에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="8302f-167">앱 페이지의 **설정 & 작업**에서 라이선스를 할당 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="8302f-168">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8302f-169">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8302f-170">**작업 설정 &** 에서 **Publisher 포털에서 관리할**링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="8302f-171">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="8302f-171">Change license quantity</span></span>

<span data-ttu-id="8302f-172">관리자는 조직에서 소유한 라이선스 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="8302f-173">이는 사용자의 중심 가격을 사용 하 여 구매한 앱에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="8302f-174">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8302f-175">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8302f-176">**라이선스 수량 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="8302f-177">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8302f-177">Manage payment methods</span></span>

<span data-ttu-id="8302f-178">서비스를 포함 하는 앱은 각각 대금 청구 프로필을 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="8302f-179">청구 프로필을 사용 하 여 송장에 포함 되는 제품을 사용자 지정 하 고 청구서 비용을 지불 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="8302f-180">주요 관련자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-180">They include:</span></span>

- <span data-ttu-id="8302f-181">**결제 방법** -신용 카드 또는 확인/회선 전송</span><span class="sxs-lookup"><span data-stu-id="8302f-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="8302f-182">**연락처 정보** -청구지 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="8302f-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="8302f-183">**역할** -대금 청구 프로필을 변경 하거나, 청구서를 지불 하거나, 대금 청구 프로필에서 결제 방법을 사용 하 여 구매를 수행할 수 있도록 하는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="8302f-184">대금 청구 프로필에 대 한 자세한 내용은 [청구 프로필 이해](https://docs.microsoft.com/microsoft-store/billing-profile)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8302f-184">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="8302f-185">서비스를 사용 하는 소프트웨어 앱 구독에서 대금 청구 프로필 변경</span><span class="sxs-lookup"><span data-stu-id="8302f-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="8302f-186">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8302f-187">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8302f-188">**청구 프로필**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="8302f-189">송장에 대 한 자세한 내용은 [청구서 또는 송장 이해](billing-and-payments/understand-your-invoice.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8302f-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="8302f-190">서비스를 사용 하는 소프트웨어 앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="8302f-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="8302f-191">앱 페이지에서 서비스를 통해 소프트웨어 앱을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="8302f-192">관리 센터에서 **Billing**  >  **제품**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">앱</a> 대금 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8302f-193">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8302f-194">**작업 설정 &** 에서 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8302f-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>
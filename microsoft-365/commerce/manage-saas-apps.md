---
title: 조직에 대 한 소프트웨어 as-서비스 앱 관리
description: Microsoft 365 관리 센터에서 타사 앱을 활성화 하 고 관리 하는 방법에 대해 알아봅니다.
ms.prod: ''
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: ''
search.appverid: MET150
author: trudyha
ms.author: TrudyHa
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/31/2019
ms.openlocfilehash: 047c93dd6dbeeb1e55bfc22b337f42870f34e104
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753557"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="8d44d-103">조직에 대 한 타사 앱 구독 관리</span><span class="sxs-lookup"><span data-stu-id="8d44d-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="8d44d-104">미리 보기 모드를 설정한 상태에서 Microsoft 365 관리 센터의 타사 앱에 대 한 라이선스 및 대금 청구를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-104">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="8d44d-105">업데이트 된 기능으로는 향상 되는 구독 관리, 대금 청구 정보에 대 한 액세스 향상, 비용 관리 유연성 향상 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="8d44d-106">구독 관리는 Microsoft의 업데이트 된 상거래 플랫폼을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="8d44d-107">이는 고객이 직접 구입 하거나 타사 공급자 로부터 제공 하는 서비스와 동일한 소프트웨어에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-107">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="8d44d-108">서비스를 제공 하는 소프트웨어 앱을 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="8d44d-108">How to get software-as-a-service apps</span></span>
<span data-ttu-id="8d44d-109">타사 앱을 구입 하는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-109">There are a few ways to purchase third-party apps.</span></span>
- <span data-ttu-id="8d44d-110">**직접 구매** -고객은 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)또는 [appsource](https://www.appsource.com/)에서 구독을 직접 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-110">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span> 
- <span data-ttu-id="8d44d-111">**파트너 구매** -구독을 구매 하기 위해 파트너 센터를 통해 파트너와 협력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-111">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span> 
- <span data-ttu-id="8d44d-112">**Microsoft 제안서** -타사 앱이 포함 된 microsoft Sales의 제안에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-112">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span> 

<span data-ttu-id="8d44d-113">고객이 앱을 구입 하 고 Microsoft 고객 계약에 동의 하면 Microsoft 365 관리 센터 또는 Microsoft Store for Business에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-113">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="8d44d-114">앱 공급자는 사용자에 대 한 라이선스를 구입 하 여 또는 일반 속도로 앱을 판매 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-114">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span> 
- <span data-ttu-id="8d44d-115">**단층 속도** -사이트 기반 가격 산정이 라고도 하며, 앱은 월별 또는 연간 가격으로 가격이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-115">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="8d44d-116">앱 페이지에서 라이선스 수량이 무제한으로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-116">On the app page, license quantity is listed at Unlimited.</span></span> 
- <span data-ttu-id="8d44d-117">**라이선스** -앱이 라이선스로 가격이 책정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-117">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="8d44d-118">고객은 조직의 각 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-118">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="8d44d-119">지원 지역</span><span class="sxs-lookup"><span data-stu-id="8d44d-119">Supported regions</span></span>
<span data-ttu-id="8d44d-120">타사 앱에 대 한 지원은 다음 지역에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-120">Support for third-party apps is available in these regions:</span></span>
- <span data-ttu-id="8d44d-121">아르헨티나</span><span class="sxs-lookup"><span data-stu-id="8d44d-121">Argentina</span></span>
- <span data-ttu-id="8d44d-122">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="8d44d-122">Australia</span></span>
- <span data-ttu-id="8d44d-123">캐나다</span><span class="sxs-lookup"><span data-stu-id="8d44d-123">Canada</span></span>
- <span data-ttu-id="8d44d-124">칠레</span><span class="sxs-lookup"><span data-stu-id="8d44d-124">Chile</span></span>
- <span data-ttu-id="8d44d-125">프랑스</span><span class="sxs-lookup"><span data-stu-id="8d44d-125">France</span></span>
- <span data-ttu-id="8d44d-126">독일</span><span class="sxs-lookup"><span data-stu-id="8d44d-126">Germany</span></span>
- <span data-ttu-id="8d44d-127">그리스</span><span class="sxs-lookup"><span data-stu-id="8d44d-127">Greece</span></span>
- <span data-ttu-id="8d44d-128">푸에르토리코</span><span class="sxs-lookup"><span data-stu-id="8d44d-128">Puerto Rico</span></span>
- <span data-ttu-id="8d44d-129">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="8d44d-129">South Africa</span></span>
- <span data-ttu-id="8d44d-130">영국</span><span class="sxs-lookup"><span data-stu-id="8d44d-130">United Kingdom</span></span>
- <span data-ttu-id="8d44d-131">NZRatingAO</span><span class="sxs-lookup"><span data-stu-id="8d44d-131">United States</span></span>
- <span data-ttu-id="8d44d-132">서유럽</span><span class="sxs-lookup"><span data-stu-id="8d44d-132">Western Europe</span></span>

## <a name="set-up-app"></a><span data-ttu-id="8d44d-133">앱 설정</span><span class="sxs-lookup"><span data-stu-id="8d44d-133">Set up app</span></span>
<span data-ttu-id="8d44d-134">관리자는 타사 앱을 사용자에 게 할당 하기 전에 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-134">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="8d44d-135">이러한 앱은 타사 게시자 포털에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-135">These apps are activated in the third-party publisher’s portal.</span></span> 

<span data-ttu-id="8d44d-136">**타사 앱을 정품 인증 하려면**</span><span class="sxs-lookup"><span data-stu-id="8d44d-136">**To activate third-party apps**</span></span>
1. <span data-ttu-id="8d44d-137">[Microsoft 365 관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=837890)이동 하 여 **미리 보기를 사용해 보세요**.</span><span class="sxs-lookup"><span data-stu-id="8d44d-137">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="8d44d-138">**청구** > **제품 & 서비스** > **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-138">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="8d44d-139">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-139">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="8d44d-140">**작업 설정 &** 에서 **Publisher 포털에서 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span> 

<span data-ttu-id="8d44d-141">앱을 정품 인증할 수 있는 앱 게시자의 사이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-141">You’ll be directed to the app publisher’s site where you can activate the app.</span></span> 

## <a name="managing-third-party-apps"></a><span data-ttu-id="8d44d-142">타사 앱 관리</span><span class="sxs-lookup"><span data-stu-id="8d44d-142">Managing third-party apps</span></span>
<span data-ttu-id="8d44d-143">관리자는 타사 앱을 Microsoft 365 관리 센터 및 타사 앱 공급자 포털의 두 위치에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider’s portal.</span></span> <span data-ttu-id="8d44d-144">각 포털에서 수행할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-144">Here’s what you can do in each portal.</span></span>

### <a name="app-status"></a><span data-ttu-id="8d44d-145">앱 상태</span><span class="sxs-lookup"><span data-stu-id="8d44d-145">App status</span></span>
<span data-ttu-id="8d44d-146">일단 활성화 되 면 앱은 취소 되거나 만료 되거나 지불이 현재 상태로 유지 되지 않는 한 활성 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-146">Once activated, the app remains active unless it is canceled, expires, or if payment is not kept current.</span></span> <span data-ttu-id="8d44d-147">이러한 이벤트는 앱 상태를 사용 안 함으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-147">These events change the app status to disabled.</span></span> <span data-ttu-id="8d44d-148">앱이 사용 하지 않도록 설정 되 면 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-148">Once an app is disabled, it can’t be reactivated.</span></span> <span data-ttu-id="8d44d-149">계속 사용 하려면 앱의 다른 복사본을 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-149">You need to buy another copy of the app to continue using it.</span></span>

| <span data-ttu-id="8d44d-150">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="8d44d-150">Microsoft 365 admin center</span></span> | <span data-ttu-id="8d44d-151">앱 게시자 포털</span><span class="sxs-lookup"><span data-stu-id="8d44d-151">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="8d44d-152">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="8d44d-152">Change license quantity</span></span> <br> <span data-ttu-id="8d44d-153">청구 비용 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8d44d-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="8d44d-154">청구 비용 결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8d44d-154">Manage how you pay your bill</span></span> <br> <span data-ttu-id="8d44d-155">결제 방법 변경 (신용 카드)</span><span class="sxs-lookup"><span data-stu-id="8d44d-155">Change payment method (credit card)</span></span> <br> <span data-ttu-id="8d44d-156">송장 보기</span><span class="sxs-lookup"><span data-stu-id="8d44d-156">View invoice</span></span> <br> <span data-ttu-id="8d44d-157">앱 구독 취소</span><span class="sxs-lookup"><span data-stu-id="8d44d-157">Cancel app subscription</span></span> | <span data-ttu-id="8d44d-158">앱 설정 (각 앱에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="8d44d-158">Set up app (once for each app)</span></span> <br> <span data-ttu-id="8d44d-159">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8d44d-159">Assign licenses to users</span></span> <br> <span data-ttu-id="8d44d-160">기술 지원</span><span class="sxs-lookup"><span data-stu-id="8d44d-160">Technical support</span></span> |

## <a name="assign-licenses"></a><span data-ttu-id="8d44d-161">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8d44d-161">Assign licenses</span></span>
<span data-ttu-id="8d44d-162">관리자는 타사 앱을 사용자에 게 할당 하기 전에 정품 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-162">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="8d44d-163">타사 게시자 포털에서 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-163">They're activated in the third-party publisher’s portal.</span></span> <span data-ttu-id="8d44d-164">앱 페이지의 **설정 & 작업**에서 라이선스를 할당 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-164">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

<span data-ttu-id="8d44d-165">**타사 앱을 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="8d44d-165">**To assign third-party apps**</span></span>

1. <span data-ttu-id="8d44d-166">[Microsoft 365 관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=837890)이동 하 여 **미리 보기를 사용해 보세요**.</span><span class="sxs-lookup"><span data-stu-id="8d44d-166">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="8d44d-167">**청구** > **제품 & 서비스** > **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-167">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="8d44d-168">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-168">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="8d44d-169">**작업 설정 &** 에서 **Publisher 포털에서 관리할**링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-169">Under **Settings & actions**, select the link to **Manage in publisher’s portal**.</span></span> 
 
## <a name="change-license-quantity"></a><span data-ttu-id="8d44d-170">라이선스 수량 변경</span><span class="sxs-lookup"><span data-stu-id="8d44d-170">Change license quantity</span></span>
<span data-ttu-id="8d44d-171">관리자는 조직에서 소유한 라이선스 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-171">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="8d44d-172">이는 사용자의 중심 가격을 사용 하 여 구매한 앱에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-172">This only applies to apps purchased with seat-based pricing.</span></span>

<span data-ttu-id="8d44d-173">**라이선스 수량을 변경 하려면**</span><span class="sxs-lookup"><span data-stu-id="8d44d-173">**To change license quantity**</span></span>

1. <span data-ttu-id="8d44d-174">[Microsoft 365 관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=837890)이동 하 여 **미리 보기를 사용해 보세요**.</span><span class="sxs-lookup"><span data-stu-id="8d44d-174">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="8d44d-175">**청구** > **제품 & 서비스** > **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-175">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="8d44d-176">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-176">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="8d44d-177">**라이선스 수량 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-177">Select **Change license quantity**.</span></span> 

## <a name="manage-payment-methods"></a><span data-ttu-id="8d44d-178">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8d44d-178">Manage payment methods</span></span>
<span data-ttu-id="8d44d-179">서비스를 포함 하는 앱은 각각 대금 청구 프로필을 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-179">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="8d44d-180">청구 프로필을 사용 하 여 송장에 포함 되는 제품을 사용자 지정 하 고 청구서 비용을 지불 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-180">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="8d44d-181">주요 관련자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-181">They include:</span></span>

- <span data-ttu-id="8d44d-182">**결제 방법** -신용 카드 또는 확인/회선 전송</span><span class="sxs-lookup"><span data-stu-id="8d44d-182">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="8d44d-183">**연락처 정보** -청구지 주소 및 연락처 이름</span><span class="sxs-lookup"><span data-stu-id="8d44d-183">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="8d44d-184">**역할** -대금 청구 프로필을 변경 하거나, 청구서를 지불 하거나, 대금 청구 프로필에서 결제 방법을 사용 하 여 구매를 수행할 수 있도록 하는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-184">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span> 

<span data-ttu-id="8d44d-185">대금 청구 프로필에 대 한 자세한 내용은 [청구 프로필 이해](https://docs.microsoft.com/microsoft-store/billing-profile)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d44d-185">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span> 

<span data-ttu-id="8d44d-186">**소프트웨어 as-서비스 앱 구독에서 대금 청구 프로필을 변경 하려면**</span><span class="sxs-lookup"><span data-stu-id="8d44d-186">**To change the billing profile on a software-as-a-service app subscription**</span></span>

1. <span data-ttu-id="8d44d-187">[Microsoft 365 관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=837890)이동 하 여 **미리 보기를 사용해 보세요**.</span><span class="sxs-lookup"><span data-stu-id="8d44d-187">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="8d44d-188">**청구** > **제품 & 서비스** > **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-188">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="8d44d-189">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-189">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="8d44d-190">**청구 프로필**옆에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-190">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="8d44d-191">송장에 대 한 자세한 내용은 [Microsoft 고객 계약 송장 이해](https://docs.microsoft.com/microsoft-store/billing-understand-your-invoice-msfb)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d44d-191">For more information on invoices, see [Understand your Microsoft Customer Agreement invoice](https://docs.microsoft.com/microsoft-store/billing-understand-your-invoice-msfb).</span></span>

## <a name="cancel-subscription"></a><span data-ttu-id="8d44d-192">구독 취소</span><span class="sxs-lookup"><span data-stu-id="8d44d-192">Cancel subscription</span></span>
<span data-ttu-id="8d44d-193">고객은 앱 페이지에서 소프트웨어 as-서비스 앱을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-193">Customers can cancel software-as-a-service app from the app page.</span></span> 

<span data-ttu-id="8d44d-194">**소프트웨어 as-서비스 앱 구독을 취소 하려면**</span><span class="sxs-lookup"><span data-stu-id="8d44d-194">**To cancel software-as-a-service app subscription**</span></span>

1. <span data-ttu-id="8d44d-195">[Microsoft 365 관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=837890)이동 하 여 **미리 보기를 사용해 보세요**.</span><span class="sxs-lookup"><span data-stu-id="8d44d-195">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="8d44d-196">**청구** > **제품 & 서비스** > **앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-196">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="8d44d-197">관리 하려는 앱을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-197">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="8d44d-198">**작업 설정 &** 에서 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d44d-198">Under **Settings & actions**, select **Cancel subscription**.</span></span>
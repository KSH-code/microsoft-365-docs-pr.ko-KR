---
title: 셀프 서비스 구매 FAQ
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: 셀프 서비스 구매에 대한 자주 묻는 질문에 대한 답변을 찾아보는 것이 가장 흔합니다.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333197"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="51f0a-103">셀프 서비스 구매 FAQ</span><span class="sxs-lookup"><span data-stu-id="51f0a-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="51f0a-104">셀프 서비스 구매는 사용자에게 새로운 기술을 사용해 보거나 궁극적으로 대규모 조직에 혜택을 주는 솔루션을 개발할 수 있는 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="51f0a-105">중앙 조달 및 IT 팀은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터를 통해 셀프 서비스 구매 솔루션을 구입하고 배포하는 모든 사용자에게 가시성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="51f0a-106">관리자는 PowerShell을 통해 제품 기준으로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="51f0a-107">자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조합니다.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="51f0a-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="51f0a-108">셀프 서비스 구매는 Power Platform(Power BI, Power Apps 및 Power Automate), Project 및 Visio에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="51f0a-109">셀프 서비스 구매는 인도 또는 정부 또는 교육 고객에게는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-109">Self-service purchase isn’t available in India or for government or education customers.</span></span> <span data-ttu-id="51f0a-110">Project 및 Visio는 브라질과 Congo의 민주 공화국에서 셀프 서비스 구매에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-110">Project and Visio are not available for self-service purchase in Brazil and the Democratic Republic of Congo.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="51f0a-111">셀프 서비스 구매 만들기</span><span class="sxs-lookup"><span data-stu-id="51f0a-111">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="51f0a-112">고객이 셀프 서비스를 구입하는 방법</span><span class="sxs-lookup"><span data-stu-id="51f0a-112">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="51f0a-113">고객은 제품 웹 사이트 또는 앱에서 구매 프롬프트에서 온라인으로 셀프 서비스 구매를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-113">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="51f0a-114">고객은 먼저 기존 Azure AD(Active Directory) 테넌트의 사용자인 경우 전자 메일 주소를 입력하도록 요청됩니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-114">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="51f0a-115">다음으로 Azure AD 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-115">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="51f0a-116">로그인한 후 고객은 구입하려는 구독 수를 선택하고 신용 카드 결제를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-116">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="51f0a-117">구매가 완료되면 구독 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-117">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="51f0a-118">구매는 조직의 다른 사용자에게 제품에 라이선스를 할당할 수 있는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> 관리 센터의 제한된 보기에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-118">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="51f0a-119">셀프 서비스 구매에 대한 결제 옵션은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="51f0a-119">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="51f0a-120">현재 신용 카드만 사용할 수 있는 결제 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-120">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="51f0a-121">송장 결제는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-121">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="51f0a-122">셀프 서비스 구매를 통해 구입할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="51f0a-122">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="51f0a-123">관리되는 Azure AD 테넌트에 비 게스트 사용자 계정이 있는 모든 사용자는 셀프 서비스 구매를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-123">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="51f0a-124">정부 또는 교육 기관인 테넌트에서는 셀프 서비스 구매를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-124">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="51f0a-125">조직에 적용되는 경우 셀프 서비스 구매를 제어하기 위해 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-125">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="51f0a-126">셀프 서비스 구매 자격이 없는 조직 또는 시장의 사용자는 IT 관리자에게 문의할 수 있는 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-126">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="51f0a-127">게스트 사용자가 셀프 서비스 구매를 통해 구매할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-127">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="51f0a-128">아니요. 게스트 사용자는 게스트인 테넌트에서 셀프 서비스 구매를 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-128">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="51f0a-129">사용자가 셀프 서비스 구매를 통해 사내 Active Directory에서 동기화할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-129">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="51f0a-130">적합한 Azure AD 테넌트에서 활성 사용자 계정이 있는 사용자는 셀프 서비스 구매를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-130">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="51f0a-131">셀프 서비스 구매자가 라이선스를 할당할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="51f0a-131">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="51f0a-132">셀프 서비스 구매자는 동일한 Azure AD 테넌트의 사용자에게만 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-132">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="51f0a-133">구매자를 통해 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> 관리 센터의 제한된 보기에 액세스하여 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-133">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="51f0a-134">구매자는 셀프 서비스 구매를 통해 구입한 제품에 라이선스를 할당할 수 있으며 동일한 Azure AD 테넌트의 사용자에게만 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-134">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="51f0a-135">셀프 서비스 구매는 어디에서 구매를 보고 관리하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-135">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="51f0a-136">셀프 서비스 구매자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터의 제한된 보기에서 구매를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-136">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="51f0a-137">구매자는 항상 모든 Microsoft 365 및 Dynamics 온라인 앱에 기본 제공되는 앱 시작 관리자의 관리 타일에서 관리 센터에 액세스할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="51f0a-137">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="51f0a-138">구매자는 구매한 구매를 보고, 동일한 서비스에 대한 추가 구독을 구입하고, 해당 구독에 대한 라이선스를 조직의 다른 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-138">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="51f0a-139">또한 구매자는 청구서를 보고 결제하고, 결제 방법을 업데이트하고, 구독을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-139">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="51f0a-140">가격</span><span class="sxs-lookup"><span data-stu-id="51f0a-140">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="51f0a-141">셀프 서비스 구매의 가격은 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-141">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="51f0a-142">셀프 서비스 구매를 위한 각 제품에 대한 가격은 Microsoft 웹 사이트에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-142">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="51f0a-143">가격은 사용자가 셀프 서비스 구매를 할 때 체크 아웃 환경의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-143">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="51f0a-144">이러한 가격은 파트너를 통해 중앙 구매를 할 때 조직이 지불하는 가격과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-144">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="51f0a-145">지불 책임은 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-145">Who is responsible for payment?</span></span>

<span data-ttu-id="51f0a-146">셀프 서비스 구매를 통해 구독을 구입하는 사람은 청구가 청구된 사람이고 구매 약관 및 가격에 따라 결제를 담당하는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-146">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="51f0a-147">관리자 기능</span><span class="sxs-lookup"><span data-stu-id="51f0a-147">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="51f0a-148">관리자가 셀프 서비스 구매를 위해 어떤 기능을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-148">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="51f0a-149">관리자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터에서 조직에서 만든 모든 셀프 서비스 구매를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-149">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="51f0a-150">각 셀프 서비스 구매에 대한 제품, 구매자 이름, 구독, 만료 날짜, 주문 내역, 구매 가격 및 할당된 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-150">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="51f0a-151">Power Platform 관리 센터에서 관리자는 셀프 서비스 구매 용량도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-151">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="51f0a-152">조직에 필요한 경우 관리자는 PowerShell을 통해 제품 기준으로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-152">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="51f0a-153">관리자는 셀프 서비스 구매를 통해 구입하거나 중앙에서 구입한 제품에 대해 동일한 데이터 관리 및 액세스 정책을 습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-153">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="51f0a-154">관리자는 조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-154">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="51f0a-155">자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조하세요.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="51f0a-155">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="51f0a-156">Microsoft는 셀프 서비스 구매를 사용하도록 설정하여 데이터 거버넌스 및 규정 준수를 어떻게 준수하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-156">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="51f0a-157">관리자는 데이터 거버넌스 및 규정 준수 요구 사항에 따라 테넌트 내에서 사용할 수 있는 서비스 및 제품을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-157">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="51f0a-158">조직에서 설정한 모든 데이터 관리 및 액세스 정책은 사용 가능한 셀프 서비스 구매 서비스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-158">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="51f0a-159">셀프 서비스 구매로 만든 제품 데이터를 누가 소유하고 있나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-159">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="51f0a-160">셀프 서비스 구매를 통해 구입한 제품에서 만든 데이터는 조직에서 소유하고 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-160">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="51f0a-161">셀프 서비스 구매를 통해 구매한 구매를 중앙 집중화하는 방법</span><span class="sxs-lookup"><span data-stu-id="51f0a-161">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="51f0a-162">관리자는 셀프 서비스 구매에 할당된 사용자의 기존 계약 및 가격을 통해 기존 라이선스를 할당하거나 셀프 서비스 구매 제품의 추가 구독을 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-162">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="51f0a-163">중앙에서 구입한 라이선스를 할당한 후 관리자는 구매자에 기존 구독을 취소할 수 있도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-163">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="51f0a-164">관리자에게 셀프 서비스 구매는 어디에서 표시하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-164">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="51f0a-165">전역 및 대금 청구 관리자는   >   <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터에서 청구 제품에서 셀프 서비스 구매를 통해 구입한 구독을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-165">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="51f0a-166">중앙 조달을 통해 구매한 구독만 표시하거나 셀프 서비스 구매를 통해 구입한 구독을 포함하기 위해 제품 목록을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-166">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="51f0a-167">관리자는 제품, 구매자 이름, 구독 구매, 만료 날짜, 주문 내역, 구매 가격 및 할당된 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-167">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="51f0a-168">지원 및 교육</span><span class="sxs-lookup"><span data-stu-id="51f0a-168">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="51f0a-169">고객의 IT 부서 또는 파트너가 셀프 서비스 구매를 통해 구입한 제품을 지원해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-169">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="51f0a-170">IT 부서와 파트너는 셀프 서비스 구매를 통해 구입한 제품에 대한 지원을 제공할 것으로 예상되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-170">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="51f0a-171">Microsoft는 셀프 서비스 구매자에 대한 표준 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-171">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="51f0a-172">셀프 서비스 구매자가 지원을 요청하는 경우 고객의 프리미어 지원 인시던트가 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-172">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="51f0a-173">셀프 서비스 구매자는 셀프 서비스 구매에 대한 지원을 받는 데 고객의 프리미어 지원 인시던트가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-173">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="51f0a-174">셀프 서비스 구매를 통해 구입하는 제품에 대한 교육을 받는 사용자는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-174">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="51f0a-175">사용자에 대한 광범위한 교육은 제품 웹 사이트에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-175">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="51f0a-176">이 제품은 학습, 설명서, 샘플 및 강력한 커뮤니티를 안내하여 다른 사용자로부터 직접 답변과 팁을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-176">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="51f0a-177">사용자가 조직을 떠나면 셀프 서비스 구매는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="51f0a-177">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="51f0a-178">셀프 서비스 구매 제품을 처음 구입한 사용자가 조직을 떠나도 유효한 사용자는 구독 기간 동안 제품을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-178">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="51f0a-179">구독은 고객이 직접 취소하거나 관리자가 고객 지원을 통해 구독 취소를 요청할 때까지 활성 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-179">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="51f0a-180">관리자는 중앙에서 구입한 라이선스를 취소된 구독 사용자에게 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-180">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="51f0a-181">파트너</span><span class="sxs-lookup"><span data-stu-id="51f0a-181">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="51f0a-182">셀프 서비스 구매 시 Microsoft 파트너의 역할은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="51f0a-182">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="51f0a-183">관리 권한을 위임한 파트너는 관리자와 마찬가지로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>관리 센터에서 셀프 서비스 구매를 볼 수 있습니다. 파트너는 셀프 서비스 구매를 통해 구입한 제품을 중앙 집중화하려는 조직을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-183">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="51f0a-184">또한 파트너는 셀프 서비스 구매 기능을 확장하는 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f0a-184">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>
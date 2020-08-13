---
title: 셀프 서비스 구매 FAQ
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 셀프 서비스 구매에 대 한 일반적인 질문과 대답을 확인할 수 있습니다.
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653704"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="0963c-103">셀프 서비스 구매 FAQ</span><span class="sxs-lookup"><span data-stu-id="0963c-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="0963c-104">셀프 서비스 구매 기능을 통해 사용자는 새로운 기술을 시험해 보고 궁극적으로는 대규모 조직에 이익이 되는 솔루션을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="0963c-105">중앙 조달 및 IT 팀은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 통해 셀프 서비스 구매 솔루션을 구입 하 고 배포 하는 모든 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="0963c-106">관리자는 PowerShell을 통해 제품별로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="0963c-107">자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0963c-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="0963c-108">셀프 서비스 구매는 전원 플랫폼 (Power BI, Power Apps 및 Power 자동화), Project 및 Visio에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="0963c-109">셀프 서비스 구매는 인도에서 사용할 수 없으며 정부 또는 교육 고객은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-109">Self-service purchase isn’t available in India, and isn’t available to government or education customers.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="0963c-110">셀프 서비스 구매</span><span class="sxs-lookup"><span data-stu-id="0963c-110">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="0963c-111">고객이 셀프 서비스를 구매 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-111">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="0963c-112">고객은 제품 웹 사이트 또는 앱 내 구매 음성 안내에서 온라인 셀프 서비스를 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-112">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="0963c-113">고객은 먼저 전자 메일 주소를 입력 하 여 기존 Azure AD (Active Directory) 테 넌 트에서 사용자 인지 확인 하 라는 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-113">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="0963c-114">다음으로, Azure AD 자격 증명을 사용 하 여 로그인 하도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-114">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="0963c-115">로그인 한 후 고객에 게 구매할 구독 수를 선택 하 고 신용 카드 결제를 제공 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-115">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="0963c-116">구매가 완료 되 면 구독 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-116">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="0963c-117">구매자는 조직의 다른 사용자에 게 제품 라이선스를 할당할 수 있는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a> 의 제한 된 보기에 대 한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-117">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="0963c-118">셀프 서비스 구매에 대 한 결제 옵션은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="0963c-118">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="0963c-119">현재 신용 카드만 사용할 수 있는 결제 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-119">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="0963c-120">송장 결제 통과는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-120">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="0963c-121">셀프 서비스 구매를 통해 구매할 수 있는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-121">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="0963c-122">관리 되는 Azure AD 테 넌 트에 비 게스트 사용자 계정을 가진 모든 사용자는 셀프 서비스를 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-122">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="0963c-123">셀프 서비스 구매는 정부 또는 교육 조직에 해당 하는 테 넌 트에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-123">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="0963c-124">이 사항이 조직에 적용 되는 경우 셀프 서비스 구매를 제어 하기 위해 추가 작업을 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-124">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="0963c-125">셀프 서비스 구매가 적합 하지 않은 조직이 나 시장의 사용자는 IT 관리자에 게 문의 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-125">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="0963c-126">게스트 사용자가 셀프 서비스 구매를 통해 구매할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="0963c-126">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="0963c-127">아니요, 게스트 사용자는 게스트가 고 있는 테 넌 트에서 셀프 서비스 구매를 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-127">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="0963c-128">셀프 서비스 구매를 통해 온-프레미스 Active Directory에서 사용자를 동기화 할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="0963c-128">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="0963c-129">사용자가 적합 한 Azure AD 테 넌 트에 활성 사용자 계정을 가진 경우 셀프 서비스 구매를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-129">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="0963c-130">Purchasers에서 라이선스를 할당할 수 있는 사용자는 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-130">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="0963c-131">셀프 서비스 purchasers는 동일한 Azure AD 테 넌 트의 사용자 에게만 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-131">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="0963c-132">구매자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a> 의 제한 된 보기에 액세스 하 여 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-132">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="0963c-133">Purchasers는 셀프 서비스 구매를 통해 구매한 제품에 라이선스를 할당할 수 있으며, 이러한 라이선스를 동일한 Azure AD 테 넌 트의 사용자 에게만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-133">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="0963c-134">셀프 서비스 구매자가 구매를 확인 하 고 관리 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-134">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="0963c-135">셀프 서비스 purchasers은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>의 제한 된 보기에서 해당 구매를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-135">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="0963c-136">Purchasers는 항상 모든 Microsoft 365 및 Dynamics online 앱에 기본적으로 제공 되는 앱 시작 **관리자 타일의 관리 센터** 에서 관리 센터로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-136">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="0963c-137">Purchasers에서는 사용자가 수행한 구매를 확인 하 고, 같은 서비스에 대 한 추가 구독을 구입 하 고, 해당 구독에 대 한 라이선스를 조직의 다른 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-137">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="0963c-138">또한 purchasers에서 청구서를 보고 요금을 지불 하 고, 결제 방법을 업데이트 하 고, 구독을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-138">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="0963c-139">산정</span><span class="sxs-lookup"><span data-stu-id="0963c-139">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="0963c-140">셀프 서비스 구매의 가격은 얼마 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-140">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="0963c-141">Microsoft 웹 사이트에서 셀프 서비스 구매 제품 각각에 대 한 가격 산정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-141">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="0963c-142">가격은 사용자가 셀프 서비스를 구매 하는 경우 체크아웃 환경의 일부로도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-142">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="0963c-143">이러한 가격은 조직이 중앙 구매 또는 가격을 통해 제공 되는 경우 조직에서 지불 하는 가격과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-143">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="0963c-144">지불 책임이 있는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-144">Who is responsible for payment?</span></span>

<span data-ttu-id="0963c-145">셀프 서비스 구매를 통해 구독을 구매한 사람은 대금을 지불 하 고 구매 약관을 기준으로 결제를 담당 하는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-145">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="0963c-146">관리 기능</span><span class="sxs-lookup"><span data-stu-id="0963c-146">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="0963c-147">관리자가 셀프 서비스를 구매 하는 데 사용할 수 있는 기능은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="0963c-147">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="0963c-148">관리자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 조직에 적용 된 모든 셀프 서비스 구매를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-148">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="0963c-149">제품, 구매자 이름, 구독 구입, 만료 날짜, 주문 내역, 구매 가격 및 각 셀프 서비스 구매에 대 한 사용자 지정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-149">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="0963c-150">Power Platform 관리 센터에서는 관리자가 셀프 서비스 구매 용량을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-150">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="0963c-151">조직에 필요한 경우 관리자는 PowerShell을 통해 제품별로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-151">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="0963c-152">관리자는 셀프 서비스 구매 또는 중앙을 통해 구매한 제품에 대해 동일한 데이터 관리 및 액세스 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-152">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="0963c-153">관리자는 또한 조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부도 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-153">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="0963c-154">자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0963c-154">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="0963c-155">Microsoft는 셀프 서비스 구매를 사용 하 여 데이터를 관리 하 고 규정 준수 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-155">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="0963c-156">관리자는 데이터 거 버 넌 스 및 규정 준수 요구 사항에 따라 해당 사용자의 테 넌 트 내에서 사용할 수 있는 서비스 및 제품을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-156">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="0963c-157">조직이 설정 된 모든 데이터 관리 및 액세스 정책이 사용 가능한 셀프 서비스 구입 서비스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-157">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="0963c-158">셀프 서비스 구매에서 만든 제품 데이터는 누구 입니까?</span><span class="sxs-lookup"><span data-stu-id="0963c-158">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="0963c-159">셀프 서비스 구매를 통해 구매한 제품에서 생성 된 데이터는 조직에서 소유 하 고 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-159">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="0963c-160">셀프 서비스 구매를 통한 구매를 중앙 집중화 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-160">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="0963c-161">관리자가 기존 라이선스를 할당 하거나 셀프 서비스 구매에 할당 된 사용자에 대 한 기존 계약 및 가격 산정을 통해 셀프 서비스 구매 제품의 추가 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-161">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="0963c-162">중앙에서 구매한 라이선스를 할당 한 후 관리자는 purchasers에서 기존 구독을 취소 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-162">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="0963c-163">관리자가 셀프 서비스 구매를 참조 하는 위치</span><span class="sxs-lookup"><span data-stu-id="0963c-163">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="0963c-164">전역 및 대금 청구 관리자 **Billing**  >  는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서**제품을** 대금 청구 하 여 셀프 서비스 구매를 통해 구매한 구독을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-164">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="0963c-165">제품 목록을 필터링 하 여 중앙 조달을 통해 구매한 구독을 표시 하거나 셀프 서비스 구매를 통해 구입한 구독을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-165">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="0963c-166">관리자는 제품, 구매자 이름, 구독 구입, 만료 날짜, 주문 내역, 구매 가격 및 할당 된 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-166">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="0963c-167">지원 및 교육</span><span class="sxs-lookup"><span data-stu-id="0963c-167">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="0963c-168">고객의 IT 부서 또는 파트너가 셀프 서비스 구매를 통해 구매한 제품을 지원 하기를 기대 하나요?</span><span class="sxs-lookup"><span data-stu-id="0963c-168">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="0963c-169">IT 부서 및 파트너가 셀프 서비스 구매를 통해 구매한 제품에 대 한 지원을 제공 하지 않을 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-169">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="0963c-170">Microsoft는 셀프 서비스 purchasers에 대 한 표준 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-170">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="0963c-171">셀프 서비스 구매자가 지원을 요청 하는 경우 고객의 프리미어 지원 인시던트를 사용 합니까?</span><span class="sxs-lookup"><span data-stu-id="0963c-171">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="0963c-172">셀프 서비스 purchasers 고객의 프리미어 지원 인시던트를 사용 하 여 셀프 서비스 구매 지원을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-172">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="0963c-173">사용자가 셀프 서비스 구매를 통해 구입한 제품에 대 한 교육을 받을 것으로 예상 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-173">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="0963c-174">사용자에 대 한 광범위 한 교육은 제품 웹 사이트에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-174">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="0963c-175">제품에는 안내 학습, 설명서, 샘플 및 강력한 커뮤니티를 통해 다른 사용자 로부터 직접 응답과 팁을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-175">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="0963c-176">사용자가 조직을 떠나는 경우 셀프 서비스 구매는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="0963c-176">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="0963c-177">원래 셀프 서비스 구매 제품을 구매한 사용자가 조직을 벗어나면 유효한 사용자는 구독 기간 동안 제품을 완전히 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-177">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="0963c-178">구독은 구매자가 직접 취소 하거나 고객 지원을 통해 구독에 대 한 관리자 요청 취소를 취소할 때까지 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-178">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="0963c-179">또한 관리자는 취소 된 구독 사용자에 게 중앙에서 구매한 라이선스를 할당 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-179">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="0963c-180">파트너</span><span class="sxs-lookup"><span data-stu-id="0963c-180">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="0963c-181">셀프 서비스 구매에서의 Microsoft 파트너 역할은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0963c-181">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="0963c-182">관리 권한을 위임 받은 파트너는 관리자와 마찬가지로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 셀프 서비스 구매를 볼 수 있습니다. 파트너는 셀프 서비스 구매를 통해 구매한 제품을 중앙 집중식으로 관리 하려는 조직을 지 원하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-182">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="0963c-183">또한 파트너는 셀프 서비스 구매 기능을 확장 하는 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0963c-183">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>
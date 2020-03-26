---
title: 구독이 종료되면 내 데이터와 액세스 권한에 어떤 변화가 있나요?
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
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Office 365 for business 구독이 만료 되거나, 사용 하지 않도록 설정 되었거나, 취소 된 경우 데이터에 대 한 결과를 알아봅니다.
ms.openlocfilehash: 2529d5027305a9ceaf71033b4de52a867b9fa9fb
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955676"
---
# <a name="what-happens-to-my-data-and-access-when-my-office-365-for-business-subscription-ends"></a><span data-ttu-id="00a08-103">비즈니스에 대 한 Office 365 구독이 종료 되 면 내 데이터 및 액세스에 대 한 변화</span><span class="sxs-lookup"><span data-stu-id="00a08-103">What happens to my data and access when my Office 365 for business subscription ends?</span></span>

<span data-ttu-id="00a08-104">구독이 만료 되는 경우 또는 취소 하기로 결정 하는 경우, 구독을 완전히 해제 하기 전에 Office 365 서비스, 응용 프로그램 및 고객 데이터에 대 한 액세스 권한이 여러 상태를 *구축*합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-104">If your subscription ends—either because it expires, or because you decide to cancel—your access to Office 365 services, applications, and customer data go through multiple states before the subscription is fully turned off, or *deprovisioned*.</span></span> <span data-ttu-id="00a08-105">이 단계를 이해 하 고 있는 경우 구독을 이전 상태로 되돌릴 것이 더 나, Office 365를 떠나는 경우 최종적으로 삭제 되기 전에 데이터를 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-105">If you are aware of this progression, you'll be better equipped to return your subscription to an active state before it's too late, or—if you're leaving Office 365—back up your data before it is ultimately deleted.</span></span>
  
## <a name="office-365-for-business-subscription-lifecycle"></a><span data-ttu-id="00a08-106">Office 365 for business: 구독 수명 주기</span><span class="sxs-lookup"><span data-stu-id="00a08-106">Office 365 for business: Subscription lifecycle</span></span>
- <span data-ttu-id="00a08-107">구독이 만료 되는 경우 만료/사용 안 함/구축 단계를 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-107">If your subscription expires, it goes through the following stages: Expired / Disabled / Deprovisioned.</span></span> <span data-ttu-id="00a08-108">만료 된 단계는 구독이 종료 날짜에 도달한 직후에 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-108">The Expired stage starts immediately after the subscription has reached its end date.</span></span>
- <span data-ttu-id="00a08-109">연간 구독에 대해 되풀이 되는 대금 청구를 해제 하는 경우 만료 된 구독과 동일한 단계를 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-109">If you turn off recurring billing on your annual subscription, it goes through the same stages as an expired subscription.</span></span> <span data-ttu-id="00a08-110">첫 번째 단계는 구독의 되풀이 비용 설정을 해제 한 날짜부터 시작 하지 않고 연간 구독의 기념일입니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-110">The first stage starts are the anniversary of the annual subscription, not starting on the date that you turned off the subscription's recurring billing setting.</span></span>
- <span data-ttu-id="00a08-111">매월 구독을 취소 하면 즉시 사용 하지 않도록 설정 됩니다 (취소 날짜).</span><span class="sxs-lookup"><span data-stu-id="00a08-111">If you cancel your monthly subscription, it will be disabled immediately (at the date of cancellation).</span></span> <span data-ttu-id="00a08-112">즉, 사용자는 즉시 Office 365 자산에 대 한 액세스 권한을 잃게 되며 관리자만 다음 90 일 동안 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-112">This means your users will lose access to the Office 365 assets immediately and only admins will have access to the data for the next 90 days.</span></span>

<span data-ttu-id="00a08-113">다음 표에서는 유료 Office 365 for business 구독이 만료 되는 경우 발생할 수 있는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-113">The following table explains what you can expect when a paid Office 365 for business subscription expires.</span></span>

| <span data-ttu-id="00a08-114">**활성**</span><span class="sxs-lookup"><span data-stu-id="00a08-114">**Active**</span></span>                                                             | <span data-ttu-id="00a08-115">**만료 <br/>(30 일\*)**</span><span class="sxs-lookup"><span data-stu-id="00a08-115">**Expired <br/>(30 days\*)**</span></span>                                                | <span data-ttu-id="00a08-116">**사용 <br/>안 함 (\*90 일)**</span><span class="sxs-lookup"><span data-stu-id="00a08-116">**Disabled <br/>(90 days\*)**</span></span>                                               | <span data-ttu-id="00a08-117">**프로비전 해제됨**</span><span class="sxs-lookup"><span data-stu-id="00a08-117">**Deprovisioned**</span></span>                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="00a08-118">*모든 데이터에 액세스할 수 있음*</span><span class="sxs-lookup"><span data-stu-id="00a08-118">*Data accessible to all*</span></span>                                               | <span data-ttu-id="00a08-119">*모든 데이터에 액세스할 수 있음*</span><span class="sxs-lookup"><span data-stu-id="00a08-119">*Data accessible to all*</span></span>                                                     | <span data-ttu-id="00a08-120">*관리자만 데이터에 액세스할 수 있음*</span><span class="sxs-lookup"><span data-stu-id="00a08-120">*Data accessible to admins only*</span></span>                                             | <span data-ttu-id="00a08-121">**다른 서비스<br/>에서 사용 하 고 있지 않은 경우 삭제 된 데이터가 Azure Active Directory를 제거 함**</span><span class="sxs-lookup"><span data-stu-id="00a08-121">**Data deleted<br/>Azure Active Directory is removed, if not in use by other services**</span></span> |
| <span data-ttu-id="00a08-122">사용자에 게 Office 365, 데이터 및 Office 응용 프로그램에 대 한 일반 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="00a08-122">Users have normal access to Office 365, data, and Office applications</span></span>  | <span data-ttu-id="00a08-123">사용자에 게 Office 365, 파일 및 응용 프로그램에 대 한 일반 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="00a08-123">Users have normal access to Office 365, files, and applications</span></span>              | <span data-ttu-id="00a08-124">사용자가 Office 365, 파일 또는 응용 프로그램에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="00a08-124">Users can't access Office 365, files, or applications</span></span>                        | <span data-ttu-id="00a08-125">사용자가 Office 365, 파일 또는 응용 프로그램에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="00a08-125">Users can't access Office 365, files, or applications</span></span>                                     |
| <span data-ttu-id="00a08-126">관리자가 Office 365, 데이터 및 Office 응용 프로그램에 대 한 일반 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="00a08-126">Admins have normal access to Office 365, data, and Office applications</span></span> | <span data-ttu-id="00a08-127">관리자가 관리 센터에 액세스할 수 있으 나 사용자에 게 라이선스 할당 불가</span><span class="sxs-lookup"><span data-stu-id="00a08-127">Admins can access the admin center, but can't assign licenses to users</span></span>   | <span data-ttu-id="00a08-128">관리자가 관리 센터에 액세스할 수 있으 나 사용자에 게 라이선스 할당 불가</span><span class="sxs-lookup"><span data-stu-id="00a08-128">Admins can access the admin center, but can't assign licenses to users</span></span>       | <span data-ttu-id="00a08-129">관리자가 관리 센터에 액세스 하 여 다른 구독을 구매 및 관리할 수 있음</span><span class="sxs-lookup"><span data-stu-id="00a08-129">Admins can access the admin center to purchase and manage other subscriptions</span></span>             |
|                                                                        | <span data-ttu-id="00a08-130">전역 또는 대금 청구 관리자는 관리 센터에서 구독을 다시 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-130">Global or billing admins can reactivate the subscription in the admin center</span></span> | <span data-ttu-id="00a08-131">전역 또는 대금 청구 관리자는 관리 센터에서 구독을 다시 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-131">Global or billing admins can reactivate the subscription in the admin center</span></span> |                                                                                           |

<span data-ttu-id="00a08-132">\* 대부분의 국가 및 지역에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-132">\*For most offers, in most countries and regions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00a08-133">**"고객 데이터" 란?**</span><span class="sxs-lookup"><span data-stu-id="00a08-133">**What is "customer data"?**</span></span> <span data-ttu-id="00a08-134">[Microsoft Online Services 조항](https://go.microsoft.com/fwlink/p/?LinkId=613649)에 정의 된 대로 고객 데이터는 고객의 Office 365 서비스 사용을 통해 고객에 게 Microsoft에 제공 되는 모든 텍스트, 사운드 또는 이미지 파일을 포함 하 여 모든 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-134">Customer data, as defined in the [Microsoft Online Service Terms](https://go.microsoft.com/fwlink/p/?LinkId=613649), refers to all data, including all text, sound, or image files that are provided to Microsoft by, or on behalf of, the customer through the customer's use of Office 365 services.</span></span> <span data-ttu-id="00a08-135">고객 데이터를 보호 하는 방법에 대 한 자세한 내용은 [Microsoft Service Trust Portal 시작](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-135">To learn more about the protection of customer data, see the [Get started with the Microsoft Service Trust Portal](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662).</span></span>
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a><span data-ttu-id="00a08-136">구독 만료를 위해 내 옵션 이란?</span><span class="sxs-lookup"><span data-stu-id="00a08-136">What are my options if my subscription is about to expire?</span></span>

<span data-ttu-id="00a08-137">구독을 사용 하는 경우 사용자와 최종 사용자는 전자 메일 및 비즈니스용 OneDrive, Office 응용 프로그램 등의 데이터에 대 한 일반 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-137">While a subscription is active, you and your end users have normal access to your data, services like email and OneDrive for Business, and Office applications.</span></span> <span data-ttu-id="00a08-138">관리자는 구독 만료 날짜가 임박 하면서 전자 메일 및 관리 센터에서 일련의 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-138">As the admin, you'll receive a series of notifications via email and in the admin center as your subscription nears its expiration date.</span></span>
  
<span data-ttu-id="00a08-139">구독이 실제로 만료 날짜에 도달 하기 전에 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-139">Before the subscription actually reaches its expiration date, you have a few options:</span></span>

::: moniker range="o365-worldwide"
  
- <span data-ttu-id="00a08-140">**구독에 대해 되풀이 되는 대금 청구를 사용 하도록 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-140">**Enable recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="00a08-141">되풀이 되는 **대금 청구** 가 이미 설정 된 경우에는 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-141">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="00a08-142">귀하의 구독은 자동으로 청구 되며, 현재 결제 빈도에 따라 추가 연도 또는 월에 대 한 비용이 청구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-142">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="00a08-143">**정기적으로 대금 청구** 를 해제 한 경우에는 항상 되풀이 되는 [대금 청구를 다시 켤](renew-your-subscription.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-143">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="00a08-144">선불 카드를 사용 하 여 Office 365 Business를 구매한 경우 구독에 대해 되풀이 되는 [대금 청구 기능을 켤](renew-your-subscription.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-144">If you purchased Office 365 Business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="00a08-145">1 년 동안의 선불 구독을 가진 오픈 볼륨 라이선스 고객 인 경우 파트너에 게 문의 하 여 새 제품 키를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-145">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key.</span></span> <span data-ttu-id="00a08-146">[볼륨 라이선스 서비스 센터](https://go.microsoft.com/fwlink/p/?LinkID=282016)에서 전자 메일을 통해 키를 활성화 하는 지침을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-146">You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016).</span></span> <span data-ttu-id="00a08-147">새 파트너 또는 이전에 작업 한 파트너를 찾는 방법에 대 한 자세한 내용은 [파트너 또는 대리점 찾기를](../../admin/manage/find-your-partner-or-reseller.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-147">To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="00a08-148">Office 365 Business가 있는 경우 [구독에 대 한 되풀이 된 청구 관리](renew-your-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-148">If you have Office 365 Business, see [Manage recurring billing for your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="00a08-149">**구독 만료를 허용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-149">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="00a08-150">신용 카드 또는 송장에 따라 지불 하는 경우 구독을 계속 하지 않으려면 되풀이 되는 [대금 청구를 해제](renew-your-subscription.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-150">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="00a08-151">구독은 만료 날짜에 만료 되며 관련 된 모든 전자 메일 알림을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-151">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="00a08-152">파트너와 함께 작업 중인 오픈 Volume License customer 인 경우에는 아무런 작업도 수행 하지 않고 구독이 만료 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-152">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="00a08-153">Office 365 Small Business Premium 고객용이 고 Office 365에 대 한 선불 제품 키를 사용 하 여 정품 인증을 받은 경우에는 아무런 작업도 수행 하지 않고 구독 만료를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-153">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="00a08-154">**구독이 만료 되기 전에 취소 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-154">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="00a08-155">자세한 내용은 [구독 취소](cancel-your-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-155">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
  
- <span data-ttu-id="00a08-156">**구독에 대 한 정기 청구를 관리 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-156">**Manage recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="00a08-157">되풀이 되는 **대금 청구** 가 이미 설정 된 경우에는 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-157">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="00a08-158">귀하의 구독은 자동으로 청구 되며, 현재 결제 빈도에 따라 추가 연도 또는 월에 대 한 비용이 청구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-158">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="00a08-159">**정기적으로 대금 청구** 를 해제 한 경우에는 항상 되풀이 되는 [대금 청구를 다시 켤](renew-your-subscription.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-159">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="00a08-160">선불 카드를 사용 하 여 Office 365 Business를 구매한 경우 구독에 대해 되풀이 되는 [대금 청구 기능을 켤](renew-your-subscription.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-160">If you purchased Office 365 Business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="00a08-161">1 년 동안의 선불 구독을 가진 오픈 볼륨 라이선스 고객 인 경우 파트너에 게 문의 하 여 새 제품 키를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-161">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key.</span></span> <span data-ttu-id="00a08-162">[볼륨 라이선스 서비스 센터](https://go.microsoft.com/fwlink/p/?LinkID=282016)에서 전자 메일을 통해 키를 활성화 하는 지침을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-162">You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016).</span></span> <span data-ttu-id="00a08-163">새 파트너 또는 이전에 작업 한 파트너를 찾는 방법에 대 한 자세한 내용은 [파트너 또는 대리점 찾기를](../../admin/manage/find-your-partner-or-reseller.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-163">To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="00a08-164">Office 365 Business가 있는 경우 [구독 갱신](renew-your-subscription.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-164">If you have Office 365 Business, see [Renew your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="00a08-165">**구독 만료를 허용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-165">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="00a08-166">신용 카드 또는 송장에 따라 지불 하는 경우 구독을 계속 하지 않으려면 되풀이 되는 [대금 청구를 해제](renew-your-subscription.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-166">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="00a08-167">구독은 만료 날짜에 만료 되며 관련 된 모든 전자 메일 알림을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-167">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="00a08-168">파트너와 함께 작업 중인 오픈 Volume License customer 인 경우에는 아무런 작업도 수행 하지 않고 구독이 만료 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-168">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="00a08-169">Office 365 Small Business Premium 고객용이 고 Office 365에 대 한 선불 제품 키를 사용 하 여 정품 인증을 받은 경우에는 아무런 작업도 수행 하지 않고 구독 만료를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-169">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="00a08-170">**구독이 만료 되기 전에 취소 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-170">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="00a08-171">자세한 내용은 [구독 취소](cancel-your-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-171">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- <span data-ttu-id="00a08-172">**구독을 갱신 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-172">**Renew the subscription.**</span></span> <span data-ttu-id="00a08-173">되풀이 되는 **대금 청구** 가 이미 설정 된 경우에는 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-173">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="00a08-174">귀하의 구독은 자동으로 청구 되며, 현재 결제 빈도에 따라 추가 연도 또는 월에 대 한 비용이 청구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-174">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="00a08-175">**정기적으로 대금 청구** 를 해제 한 경우에는 항상 되풀이 되는 [대금 청구를 다시 켤](renew-your-subscription.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-175">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

- <span data-ttu-id="00a08-176">**구독 만료를 허용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-176">**Let the subscription expire.**</span></span> <span data-ttu-id="00a08-177">신용 카드 또는 송장에 따라 지불 하는 경우 구독을 계속 하지 않으려면 되풀이 되는 [대금 청구를 해제](renew-your-subscription.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-177">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="00a08-178">구독은 만료 날짜에 만료 되며 관련 된 모든 전자 메일 알림을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-178">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

- <span data-ttu-id="00a08-179">**구독이 만료 되기 전에 취소 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-179">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="00a08-180">자세한 내용은 [구독 취소](cancel-your-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-180">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a><span data-ttu-id="00a08-181">구독이 만료 되 면 어떻게 됩니까?</span><span class="sxs-lookup"><span data-stu-id="00a08-181">What happens after my subscription expires?</span></span>
<span data-ttu-id="00a08-182">구독 만료를 허용 하는 경우 최종적으로 삭제 되기 전에 여러 상태가 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-182">If you let your subscription expire, it goes through multiple states before it is ultimately deleted.</span></span> <span data-ttu-id="00a08-183">이렇게 하면 관리자가 서비스를 계속 진행 하려는 경우 다시 활성화 하거나, 구독을 더 이상 사용 하지 않기로 결정 한 경우 데이터를 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-183">This gives you, as the admin, time to reactivate if you want to continue the service, or to back up your data if you decide you no longer want the subscription.</span></span>
  
<span data-ttu-id="00a08-184">구독이 각 상태에 있을 때 예상 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-184">Here's what you can expect when your subscription is in each state.</span></span>
  
### <a name="state-expired"></a><span data-ttu-id="00a08-185">상태: 만료 됨</span><span class="sxs-lookup"><span data-stu-id="00a08-185">State: Expired</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="00a08-186">**예상 결과:** 대부분의 국가 및 지역에서 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298)을 통해 구매한 구독을 포함 하 여 대부분의 구독에서 만료 됨 상태가 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-186">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions.</span></span> <span data-ttu-id="00a08-187">Microsoft Open을 제외 하 고 볼륨 라이선스 제품의 경우 만료 됨 상태는 90 일에 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-187">For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="00a08-188">**예상 결과:** 대부분의 국가 및 지역에서 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298)을 통해 구매한 구독을 포함 하 여 대부분의 구독에서 만료 됨 상태가 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-188">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions.</span></span> <span data-ttu-id="00a08-189">Microsoft Open을 제외 하 고 볼륨 라이선스 제품의 경우 만료 됨 상태는 90 일에 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-189">For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="00a08-190">**예상 결과:** 대부분의 국가 및 지역에서 만료 된 상태는 대부분의 구독에 대해 30 일입니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-190">**What to expect:** The expired state is 30 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

<span data-ttu-id="00a08-191">이 상태에서는 사용자가 Office 365 포털, Office 응용 프로그램 및 서비스 (예: 전자 메일 및 SharePoint Online)에 대 한 일반 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-191">In this state, users have normal access to the Office 365 portal, Office applications, and services such as email and SharePoint Online.</span></span>
  
<span data-ttu-id="00a08-192">관리자는 여전히 관리 센터에 대 한 액세스 권한이 있지만 사용자에 게 라이선스를 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-192">As an admin, you still have access to the admin center, but can't assign licenses to users.</span></span> <span data-ttu-id="00a08-193">전역 또는 대금 청구 관리자 [는 구독을 다시 활성화](reactivate-your-subscription.md) 하 고 Office 365를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-193">Global or billing admins can [reactivate the subscription](reactivate-your-subscription.md) and continue using Office 365.</span></span> <span data-ttu-id="00a08-194">다시 활성화 하지 않으면 [데이터를 백업](back-up-data-before-switching-plans.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-194">If you don't reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>
  
### <a name="state-disabled"></a><span data-ttu-id="00a08-195">상태: 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="00a08-195">State: Disabled</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="00a08-196">**예상 결과:** 만료 된 상태에서 구독을 다시 활성화 하지 않으면 대부분의 국가 및 지역에서 대부분의 구독에서 90 일 동안 지속 되는 비활성 상태로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-196">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="00a08-197">볼륨 라이선스 제품의 경우 사용 하지 않도록 설정 된 상태는 30 일이 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-197">For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="00a08-198">**예상 결과:** 만료 된 상태에서 구독을 다시 활성화 하지 않으면 대부분의 국가 및 지역에서 대부분의 구독에서 90 일 동안 지속 되는 비활성 상태로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-198">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="00a08-199">볼륨 라이선스 제품의 경우 사용 하지 않도록 설정 된 상태는 30 일이 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-199">For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="00a08-200">**예상 결과:** 만료 된 상태에서 구독을 다시 활성화 하지 않으면 대부분의 국가 및 지역에서 사용 되지 않는 상태로 전환 되며, 대부분의 구독에서 90 일입니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-200">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="00a08-201">이 상태에서는 액세스 성능이 크게 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-201">In this state, your access decreases significantly.</span></span> <span data-ttu-id="00a08-202">사용자가 로그인 하거나 전자 메일 또는 SharePoint Online 등의 서비스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-202">Your users can't sign in, or access services like email or SharePoint Online.</span></span> <span data-ttu-id="00a08-203">Office 응용 프로그램은 결국 읽기 전용, 기능 제한 모드 및 허가 되지 않은 [제품 알림을](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-203">Office applications eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span> <span data-ttu-id="00a08-204">계속 해 서 로그인 하 고 관리 센터에 액세스할 수 있지만 사용자에 게 라이선스를 할당 하지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-204">You can still sign in and get to the admin center, but can't assign licenses to users.</span></span> <span data-ttu-id="00a08-205">모든 사용자 데이터, 전자 메일 및 팀 사이트의 파일을 비롯 한 고객 데이터는 사용자 및 다른 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-205">Your customer data, including all user data, email, and files on team sites, is available only to you and other admins.</span></span>

::: moniker-end

<span data-ttu-id="00a08-206">전역 또는 대금 청구 관리자는 모든 고객 데이터를 그대로 유지 하면서 [구독을 다시 활성화](reactivate-your-subscription.md) 하 고 Office 365을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-206">As a global or billing admin, you can [reactivate the subscription](reactivate-your-subscription.md) and continue using Office 365 with all of your customer data intact.</span></span> <span data-ttu-id="00a08-207">다시 활성화 하지 않도록 선택한 경우 [데이터를 백업](back-up-data-before-switching-plans.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-207">If you choose not to reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>

### <a name="state-deprovisioned"></a><span data-ttu-id="00a08-208">상태: 구축</span><span class="sxs-lookup"><span data-stu-id="00a08-208">State: Deprovisioned</span></span>
  
 <span data-ttu-id="00a08-209">**예상 결과:** 유예 또는 사용 하지 않도록 설정 된 상태에서 구독을 다시 활성화 하지 않으면 구축이 구독 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-209">**What to expect:** If you don't reactivate your subscription while it is in grace or disabled, the subscription is deprovisioned.</span></span>
  
<span data-ttu-id="00a08-210">관리자 및 사용자는 더 이상 구독과 함께 제공 된 서비스 또는 Office 응용 프로그램에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-210">Admins and users no longer have access to the services or Office applications that came with the subscription.</span></span> <span data-ttu-id="00a08-211">모든 고객 데이터 (사용자 데이터에서 문서 및 전자 메일까지)는 영구적으로 삭제 되며 어떤 방식으로든 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-211">All customer data—from user data to documents and email—is permanently deleted and unable to be recovered in any way.</span></span>
  
<span data-ttu-id="00a08-212">이 시점에서는 구독을 다시 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-212">At this point, you can't reactivate the subscription.</span></span> <span data-ttu-id="00a08-213">그러나 전역 또는 대금 청구 관리자는 여전히 관리 센터에 액세스 하 여 다른 구독을 관리 하거나 비즈니스 요구 사항에 맞게 새 구독을 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-213">However, as a global or billing admin, you can still access the admin center to manage other subscriptions, or to buy new subscriptions to meet your business needs.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00a08-214">구축에 있는 같은 유형의 새 구독을 추가 해도 구축 구독과 연결 된 데이터는 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-214">Adding a new subscription of the same type that has been deprovisioned does not restore the data that was associated with the deprovisioned subscription.</span></span>

### <a name="what-happens-when-my-trial-ends"></a><span data-ttu-id="00a08-215">평가판이 종료 되 면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="00a08-215">What happens when my trial ends?</span></span>

<span data-ttu-id="00a08-216">평가판이 끝나면 Office 365을 무료로 계속 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-216">When your trial ends, you won't be able to continue using Office 365 for free.</span></span> <span data-ttu-id="00a08-217">다음 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-217">You have a few options:</span></span>

::: moniker range="o365-worldwide"
- <span data-ttu-id="00a08-218">**Office 365을 구입 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-218">**Buy Office 365.**</span></span> <span data-ttu-id="00a08-219">평가판이 만료 되 면 유예 기간 동안 최대 30 일 (대부분의 국가 및 지역에서 대부분의 평가판)을 제공 하 여 Office 365을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-219">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="00a08-220">평가판을 유료 구독으로 변환 하는 방법에 대 한 자세한 내용은 [비즈니스용 Office 365 평가판 구매 버전 구입](../buy-a-subscription-from-your-free-trial.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00a08-220">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Office 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"
- <span data-ttu-id="00a08-221">**Office 365을 구입 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-221">**Buy Office 365.**</span></span> <span data-ttu-id="00a08-222">평가판이 만료 되 면 유예 기간 동안 최대 30 일 (대부분의 국가 및 지역에서 대부분의 평가판)을 제공 하 여 Office 365을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-222">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="00a08-223">평가판을 유료 구독으로 변환 하는 방법에 대 한 자세한 내용은 [비즈니스용 Office 365 평가판 구매 버전 구입](../buy-a-subscription-from-your-free-trial.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00a08-223">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Office 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"
- <span data-ttu-id="00a08-224">**Office 365을 구입 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-224">**Buy Office 365.**</span></span> <span data-ttu-id="00a08-225">평가판이 만료 되 면 유예 기간 동안 최대 30 일 (대부분의 국가 및 지역에서 대부분의 평가판)을 제공 하 여 Office 365을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-225">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="00a08-226">평가판을 유료 구독으로 변환 하는 방법에 [대 한 자세한 내용은 구입 또는 사용해 서 21vianet에서 운영 하는 Office 365 구독 시도](../../admin/services-in-china/buy-or-try-subscriptions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-226">To learn how to convert your trial into a paid subscription, see [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).</span></span>

::: moniker-end

- <span data-ttu-id="00a08-227">**평가판을 확장 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-227">**Extend your trial.**</span></span> <span data-ttu-id="00a08-228">Office 365을 평가 하는 데 더 많은 시간이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="00a08-228">Need more time to evaluate Office 365?</span></span> <span data-ttu-id="00a08-229">경우에 따라 [평가판을 연장할](../extend-your-trial.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-229">In certain cases, you may be able to [extend your trial](../extend-your-trial.md).</span></span>

- <span data-ttu-id="00a08-230">**평가판을 취소 하거나 만료 되도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="00a08-230">**Cancel the trial or let it expire.**</span></span> <span data-ttu-id="00a08-231">Office 365을 구입 하지 않기로 결정 한 경우 평가판이 만료 되도록 하거나 [취소할](cancel-your-subscription.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-231">If you decide not to buy Office 365, you can let your trial expire or [cancel it](cancel-your-subscription.md).</span></span> <span data-ttu-id="00a08-232">보존 하려는 데이터를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-232">Be sure to back up any data you want to keep.</span></span> <span data-ttu-id="00a08-233">30 일 유예 기간이 지난 후에는 평가판 계정 정보 및 데이터를 영구적으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-233">Soon after the 30 day grace period, your trial account information and data is permanently erased.</span></span>

## <a name="what-happens-if-i-cancel-a-subscription"></a><span data-ttu-id="00a08-234">구독을 취소할 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="00a08-234">What happens if I cancel a subscription?</span></span>

<span data-ttu-id="00a08-235">기간 종료 날짜 이전에 구독을 취소 하면 구독은 만료 됨 상태를 건너뛰고 대부분의 국가 및 지역에서 사용 되지 않는 상태 (대부분의 구독에서 90 일)로 바로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-235">If you cancel your subscription before its term end date, the subscription skips the expired state and moves directly into the disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="00a08-236">취소 하기 전에 [데이터를 백업](back-up-data-before-switching-plans.md) 하는 것이 좋지만 관리자 인 경우에도 사용 하지 않도록 설정 된 상태에서 조직의 데이터에 액세스 하 여 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-236">We recommend that you [back up your data](back-up-data-before-switching-plans.md) before canceling, but as an admin, you can still access and back up data for your organization while it is in the disabled state.</span></span> <span data-ttu-id="00a08-237">남겨진 모든 고객 데이터는 90일 후에 삭제될 수 있으며, 취소 후 180일 내에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-237">Any customer data that you leave behind may be deleted after 90 days, and will be deleted no later than 180 days after cancellation.</span></span>
  
<span data-ttu-id="00a08-238">구독을 취소 하는 경우에는 다음 작업을 통해 사용자에 게 기대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-238">Here's what to expect for you and your users if you cancel a subscription.</span></span>
  
- <span data-ttu-id="00a08-239">**관리자 액세스 권한** 관리자는 계속 해 서 관리자 센터에 로그인 하 고 액세스할 수 있으며, 필요에 따라 다른 구독을 구입할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-239">**Admin access** Admins can still sign in and access the admin center, and buy other subscriptions as needed.</span></span> <span data-ttu-id="00a08-240">전역 또는 대금 청구 관리자는 90 일 이내에 모든 데이터를 그대로 사용 하 여 [구독을 다시 활성화할](reactivate-your-subscription.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-240">As a global or billing admin, you have 90 days to [reactivate the subscription](reactivate-your-subscription.md) with all data intact.</span></span>

- <span data-ttu-id="00a08-241">**사용자 액세스** 사용자는 비즈니스용 OneDrive와 같은 서비스를 사용 하거나 고객 데이터 (예: 전자 메일 또는 팀 사이트의 문서)에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-241">**User access** Your users won't be able to use services like OneDrive for Business, or access customer data—for example, email or documents on team sites.</span></span> <span data-ttu-id="00a08-242">Word 및 Excel 등의 Office 응용 프로그램은 읽기 전용 상태가 되어 기능 제한 모드로 실행되며 [사용 허가되지 않은 제품 알림](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-242">Office applications, like Word and Excel, will eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span>

<span data-ttu-id="00a08-243">취소 방법에 대 한 자세한 내용은 [구독 취소](cancel-your-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00a08-243">To learn how to cancel, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="00a08-244">일반적인 비활성 기간이 끝나기 전에 구독 데이터를 삭제 하려면 긴급 프로 비전 해제를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-244">If you want your subscription data to be deleted before the typical Disabled period is over, you can request expedited deprovisioning.</span></span> <span data-ttu-id="00a08-245">긴급 프로비전 해제를 요청하면 취소일로부터 3일 이내에 구독 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-245">When you request expedited deprovisioning, your subscription data is deleted within 3 days of cancellation.</span></span> <span data-ttu-id="00a08-246">긴급 프로 비전 해제를 사용 하려면 [지원 서비스를 호출](../../admin/contact-support-for-business-products.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-246">To use expedited deprovisioning, [call support](../../admin/contact-support-for-business-products.md).</span></span>

> [!NOTE]
> <span data-ttu-id="00a08-247">이 페이지의 정보는 [Microsoft 정책 고 지 사항 및 변경 알림에 따라 달라](https://go.microsoft.com/fwlink/p/?LinkId=613651)집니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-247">The information on this page is subject to the [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651).</span></span> <span data-ttu-id="00a08-248">이 사이트로 주기적으로 돌아가 변경 내용을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a08-248">Return to this site periodically to review any changes.</span></span>

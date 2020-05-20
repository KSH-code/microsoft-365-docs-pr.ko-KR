---
title: 결제 방법 관리
f1.keywords:
- CSH
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
ms.custom:
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Microsoft 365 관리 센터에서 결제 방법을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d31da19c10eb61719ba813d271dbdcf573a5aff3
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322162"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="8f2c7-103">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="8f2c7-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="8f2c7-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-104">The admin center is changing.</span></span> <span data-ttu-id="8f2c7-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="8f2c7-106">Microsoft에서 비즈니스 제품 또는 서비스를 구매할 때 기존 결제 방법을 사용 하거나 새 지불 방법을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="8f2c7-107">신용 또는 직불 카드 또는 은행 계좌를 사용 하 여 구매 하는 항목에 대 한 요금을 지불할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="8f2c7-108">비즈니스 계정에 대금 청구 프로필이 있고 대금 청구 프로필 소유자 또는 대금 청구 프로필 참가자 인 경우 신용 카드 또는 송장 지불로 지원 되는 대금 청구 프로필을 사용 하 여 구매 또는 지불 명세서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="8f2c7-109">청구 송장 관리자는 대금 청구 프로필만 사용 하 여 자재 명세서를 지불할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="8f2c7-110">대금 청구 프로필 및 역할에 대 한 자세한 내용은 [청구 프로필 관리](manage-billing-profiles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="8f2c7-111">비즈니스 계정에 대금 청구 프로필이 없는 경우 전역 또는 대금 청구 관리자는 비즈니스 계정에 추가 된 모든 은행 계정을 관리 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="8f2c7-112">그러나 추가한 신용 카드만 관리 하거나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="8f2c7-113">일부 국가나 지역에서는 은행 계좌 결제 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="8f2c7-114">테 넌 트와 동일한 국가에서 발급 된 결제 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="8f2c7-115">결제 방법 추가</span><span class="sxs-lookup"><span data-stu-id="8f2c7-115">Add a payment method</span></span>

<span data-ttu-id="8f2c7-116">결제 방법을 추가 해도 구독이 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="8f2c7-117">지불 방법에 대해 단일 구독을 할당 하려면 [단일 구독에 대 한 결제 방법 변경을](#change-a-payment-method-for-a-single-subscription)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="8f2c7-118">다른 결제 방법을 사용 하는 모든 구독을 새 것으로 바꾸려면 [결제 방법 바꾸기를](#replace-a-payment-method)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="8f2c7-119">관리 센터에서 **청구** > **금액 & 지불** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">지불 방법</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="8f2c7-120">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="8f2c7-121">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="8f2c7-122">**결제 방법 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="8f2c7-123">**결제 방법** 페이지의 드롭다운 메뉴에서 결제 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="8f2c7-124">새 카드나 은행 계좌에 대 한 정보를 입력 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="8f2c7-125">결제 방법 세부 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="8f2c7-125">Update payment method details</span></span>

<span data-ttu-id="8f2c7-126">기존 결제 방법의 신용 또는 직불 카드, 대금 청구 주소 또는 만료 날짜에 대 한 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="8f2c7-127">그러나 카드나 계정 번호는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="8f2c7-128">계정 번호가 변경 된 경우에는 [해당 번호를 다른 결제 방법으로 바꾼](#replace-a-payment-method)다음 [이전 항목을 삭제](#delete-a-payment-method)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="8f2c7-129">관리 센터에서 **청구** > **금액 & 지불** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">지불 방법</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="8f2c7-130">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="8f2c7-131">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="8f2c7-132">업데이트할 결제 방법의 행을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="8f2c7-133">오른쪽 창에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="8f2c7-134">신용, 직불 카드, 대금 청구 주소, 만료 날짜 등의 결제 방법 정보를 업데이트 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="8f2c7-135">결제 방법 바꾸기</span><span class="sxs-lookup"><span data-stu-id="8f2c7-135">Replace a payment method</span></span>

<span data-ttu-id="8f2c7-136">결제 방법을 바꾸면 같은 결제 방법을 사용 하는 모든 구독 및 대금 청구 프로필에 대해 교체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="8f2c7-137">결제 방법을 바꾸면 기존 결제 방법이 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="8f2c7-138">다른 구독 및 대금 청구 프로필에 대해 계속 해 서 선택 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="8f2c7-139">단일 구독에 대 한 결제 방법을 변경 하려면 [단일 구독에 대 한 결제 방법 변경을](#change-a-payment-method-for-a-single-subscription)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="8f2c7-140">관리 센터에서 **청구** > **금액 & 지불** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">지불 방법</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="8f2c7-141">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="8f2c7-142">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="8f2c7-143">바꿀 지불 방법의 행을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="8f2c7-144">오른쪽 창에는 선택한 결제 방법을 사용 하는 모든 청구 프로필 및 개별 구독이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="8f2c7-145">오른쪽 창에서 **모든 항목에 대 한 결제 방법 바꾸기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="8f2c7-146">기존 결제 방법을 사용 하려면 드롭다운 목록에서 항목을 선택 하 고 **바꾸기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="8f2c7-147">청구 프로필과 연결 된 구독이 있는 경우 신용 또는 직불 카드만 사용 하 여 요금을 지불할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="8f2c7-148">**결제 방법** 페이지에 나열 된 은행 계좌는 드롭다운 목록에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="8f2c7-149">새 결제 방법을 추가 하려면 **지불 방법 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="8f2c7-150">**결제 방법 추가** 창에서 계정 정보를 입력 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="8f2c7-151">테 넌 트와 동일한 국가의 결제 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="8f2c7-152">드롭다운 목록에서 새 결제 방법이 이미 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="8f2c7-153">**바꾸기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="8f2c7-154">단일 구독에 대 한 결제 방법 변경</span><span class="sxs-lookup"><span data-stu-id="8f2c7-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="8f2c7-155">단일 구독에 대해 요금을 지불 하는 데 사용 되는 결제 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="8f2c7-156">관리 센터에서 **결제**> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="8f2c7-157">관리 센터에서 **결제**> **내 상품**페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="8f2c7-158">관리 센터에서 **결제**> **내 상품**페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="8f2c7-159">**구독** 탭에서 대체 결제 방법으로 결제 하려는 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="8f2c7-160">**청구**아래의 결제 방법 옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="8f2c7-161">기존 결제 방법 옆에 있는 **변경**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="8f2c7-162">드롭다운 목록에서 대체 결제 방법을 선택 하거나 결제 방법 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="8f2c7-163">결제 방법을 추가 하는 경우 카드 또는 계정 세부 정보를 입력 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="8f2c7-164">선택한 결제 방법이 올바른지 확인 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="8f2c7-165">결제 방법 삭제</span><span class="sxs-lookup"><span data-stu-id="8f2c7-165">Delete a payment method</span></span>

<span data-ttu-id="8f2c7-166">구독 또는 대금 청구 프로필에 연결 되지 않은 결제 방법만 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="8f2c7-167">이는 모든 구독 상태에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="8f2c7-168">구독 또는 대금 청구 프로필을 연결 하지 않은 결제 방법 삭제</span><span class="sxs-lookup"><span data-stu-id="8f2c7-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="8f2c7-169">결제 방법이 구독 또는 대금 청구 프로필과 연결 되어 있지 않으면 즉시 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="8f2c7-170">관리 센터에서 **청구** > **금액 & 지불** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">지불 방법</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="8f2c7-171">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="8f2c7-172">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="8f2c7-173">삭제할 결제 방법을 찾은 다음 3 개의 점을 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="8f2c7-174">오른쪽 창 맨 아래에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="8f2c7-175">구독 또는 대금 청구 프로필을 연결 하 여 결제 방법 삭제</span><span class="sxs-lookup"><span data-stu-id="8f2c7-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="8f2c7-176">결제 방법이 구독 또는 대금 청구 프로필에 첨부 된 경우 먼저 기존 결제 방법으로 교체 하거나 새 결제 방법을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="8f2c7-177">관리 센터에서 **청구** > **금액 & 지불** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">지불 방법</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="8f2c7-178">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="8f2c7-179">관리 센터에서 **청구** > **금액 & 지불** > **지불 방법** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="8f2c7-180">삭제할 지불 방법의 행을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="8f2c7-181">오른쪽 창에는 해당 결제 방법을 사용 하는 기존 구독이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="8f2c7-182">오른쪽 창에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="8f2c7-183">기존 결제 방법을 사용 하려면 드롭다운 목록에서 **다음**을 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="8f2c7-184">청구 프로필과 연결 된 구독이 있는 경우 신용 카드로 결제 하는 경우에만 해당 구독을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="8f2c7-185">**결제 방법** 페이지에 나열 된 은행 계좌는 드롭다운 목록에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="8f2c7-186">새 결제 방법을 추가 하려면 **지불 방법 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="8f2c7-187">추가 하려는 결제 방법의 유형을 선택 하 고 계정 정보를 입력 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="8f2c7-188">드롭다운 목록에서 새 결제 방법이 이미 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="8f2c7-189">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-189">Select **Next**.</span></span>

8. <span data-ttu-id="8f2c7-190">**삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="8f2c7-191">결제 방법 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8f2c7-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="8f2c7-192">**문제**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-192">**Issue**</span></span>|<span data-ttu-id="8f2c7-193">**문제 해결 단계**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="8f2c7-194">**"브라우저가 현재 쿠키를 차단 하도록 설정 되어 있습니다." 라는 오류 메시지가 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="8f2c7-195">타사 쿠키를 허용하도록 브라우저를 설정하고 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="8f2c7-196">**내 신용 카드 또는 직불 카드가 거절 되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="8f2c7-197">신용 카드 또는 직불 카드로 결제 하는 경우 카드가 거절 되 면 Microsoft에서 해당 결제를 처리할 수 없음을 알리는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="8f2c7-198">카드 정보 &mdash; 카드 번호, 만료 날짜, 카드의 이름, 주소, 구/군/시, 시/도 및 우편 번호를 포함 하는 주소가 &mdash; 카드와 명령문에서 수행 하는 것과 정확히 동일 하 게 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="8f2c7-199">구독 세부 정보 페이지의 청구 섹션에 있는 **임금** **잔액** 링크를 사용 하 여 카드 정보를 업데이트 하 고 대금을 즉시 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="8f2c7-200">자세한 내용은 다음을 참조 하세요. [신용 카드를 거절 했 고 결제 기한이 경과 된 경우](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="8f2c7-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="8f2c7-201">"거부 됨" 메시지가 계속 표시 되 면 해당 은행에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="8f2c7-202">사용자의 카드가 활성 상태가 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="8f2c7-203">최근 만료 날짜를 사용 하 여 메일에서 카드를 받은 경우 해당 사용자가 활성화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="8f2c7-204">또한 은행에서 온라인, 국제 또는 되풀이 되는 거래에 대해 카드가 승인 되지 않은 경우를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="8f2c7-205">**카드나 은행 계좌 번호를 업데이트 하려고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="8f2c7-206">기존 결제 방법에서는 카드나 계정 번호를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="8f2c7-207">카드나 계정 번호가 변경 된 경우 지불 방법에서 새 구독으로 이동 하는 [다른 결제 방법으로 바꾼](#replace-a-payment-method)다음 [이전 결제 방법을 삭제](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="8f2c7-208">**내 계정에 카드 또는 은행 계정이 하나 뿐 이며 제거 하려고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="8f2c7-209">결제 방법이 하나인 경우에는 삭제 하기 전에 [새 결제 방법으로 교체](#replace-a-payment-method) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="8f2c7-210">**내 카드 또는 은행 계좌를 추가할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="8f2c7-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="8f2c7-211">테 넌 트와 동일한 국가에서 발급 된 결제 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="8f2c7-212">카드 또는 은행 계좌 정보를 입력 하는 데 문제가 있는 경우 [지원 서비스에 문의할](../../admin/contact-support-for-business-products.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2c7-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="8f2c7-213">관련 문서</span><span class="sxs-lookup"><span data-stu-id="8f2c7-213">Related articles</span></span>

[<span data-ttu-id="8f2c7-214">비즈니스 구독 결제</span><span class="sxs-lookup"><span data-stu-id="8f2c7-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="8f2c7-215">청구 프로필 관리</span><span class="sxs-lookup"><span data-stu-id="8f2c7-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="8f2c7-216">결제 빈도 변경</span><span class="sxs-lookup"><span data-stu-id="8f2c7-216">Change your payment frequency</span></span>](change-payment-frequency.md)
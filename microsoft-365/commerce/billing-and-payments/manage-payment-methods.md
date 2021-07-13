---
title: 결제 방법 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: 기존 결제 방법을 사용하거나 Microsoft 365 관리 센터에서 새 결제 방법을 추가하여 Microsoft에서 비즈니스 제품 또는 서비스를 구매하세요.
ms.date: 04/02/2021
ms.openlocfilehash: e944547e69ea8774690852d1b3123578d40bd3c0
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394620"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="2b45f-103">결제 방법 관리</span><span class="sxs-lookup"><span data-stu-id="2b45f-103">Manage payment methods</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b45f-104">2021년 1월 26일 현재 벨기에, 프랑스, 이탈리아, 룩셈부르크, 포르투갈, 스페인 및 미국의 고객에게는 새 은행 계좌가 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-104">As of January 26, 2021, new bank accounts are no longer supported for customers in Belgium, France, Italy, Luxembourg, Portugal, Spain, and the United States.</span></span> <span data-ttu-id="2b45f-105">해당 국가 중 하나의 기존 고객인 경우 기존 은행 계좌로 구독료를 계속 결제할 수 있으며 은행 계좌 상태가 양호한 경우에만 새 구독을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-105">If you’re an existing customer in one of those countries, you can continue paying for your subscription with an existing bank account, and you can add new subscriptions to it, but only as long as the bank account is in good standing.</span></span>

<span data-ttu-id="2b45f-106">Microsoft에서 비즈니스 제품 또는 서비스를 구입하는 경우 기존 결제 방법을 사용하거나 새 결제 방법을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="2b45f-107">신용 카드 또는 직불 카드 또는 은행 계좌를 사용하여 구입한 금액을 지불할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="2b45f-108">비즈니스 계정에 청구 프로필이 있고 청구 프로필 소유자 또는 청구 프로필 기여자인 경우 신용 카드 또는 송장 결제로 지원되는 청구 프로필을 사용하여 구매 또는 청구서를 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="2b45f-109">청구 송장 관리자인 경우 청구 프로필만을 사용하여 청구서를 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="2b45f-110">청구 프로필 및 역할에 대한 자세한 내용은 [청구 프로필 관리](manage-billing-profiles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="2b45f-p104">비즈니스 계정에 청구 프로필이 없는 경우 전역 관리자나 청구 관리자는 비즈니스 계정에 추가된 모든 은행 계좌를 관리하고 사용할 수 있습니다. 그러나 추가한 신용 카드만 관리하거나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-p104">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account. However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="2b45f-113">일부 국가나 지역에서는 은행 계좌로 결제하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="2b45f-114">테넌트와 동일한 국가에서 발급한 결제 방법을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2b45f-115">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="2b45f-115">Before you begin</span></span>

<span data-ttu-id="2b45f-116">이 문서의 작업을 수행하려면 전역 관리자 또는 청구 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-116">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="2b45f-117">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="2b45f-118">결제 방법 추가</span><span class="sxs-lookup"><span data-stu-id="2b45f-118">Add a payment method</span></span>

<span data-ttu-id="2b45f-119">결제 방법을 추가해도 구독과 연결되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-119">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="2b45f-120">결제 방법에 대해 단일 구독을 할당하려면 [단일 구독에 대한 결제 방법 변경](#change-a-payment-method-for-a-single-subscription)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-120">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="2b45f-121">다른 결제 방법을 사용하는 모든 구독을 새로운 결제 방법으로 바꾸기하려면 [결제 방법 교체](#replace-a-payment-method)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-121">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="2b45f-122">관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="2b45f-123">**결제 방법 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-123">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="2b45f-124">**결제 방법** 페이지의 드롭다운 메뉴에서 결제 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-124">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="2b45f-125">새 카드 또는 은행 계좌의 정보를 입력한 다음 **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-125">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="2b45f-126">결제 방법 세부 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="2b45f-126">Update payment method details</span></span>

<span data-ttu-id="2b45f-127">기존 결제 방법에 대한 신용 카드 또는 직불 카드의 이름, 청구 주소 또는 만료 날짜를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-127">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="2b45f-128">하지만 카드 또는 계좌 번호를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-128">However, you can't change the card or account number.</span></span> <span data-ttu-id="2b45f-129">계정 번호가 변경된 경우 [다른 제 방법으로 교체](#replace-a-payment-method)한 다음, [이전 계정을 삭제](#delete-a-payment-method)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-129">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="2b45f-130">관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-130">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="2b45f-131">업데이트할 결제 방법의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-131">Select the row of the payment method to update.</span></span> <span data-ttu-id="2b45f-132">오른쪽 창에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-132">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="2b45f-133">신용 카드나 직불 카드의 이름, 대금 청구 주소 또는 만료 날짜를 비롯한 결제 방법 정보를 업데이트하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-133">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="2b45f-134">결제 방법 변경</span><span class="sxs-lookup"><span data-stu-id="2b45f-134">Replace a payment method</span></span>

<span data-ttu-id="2b45f-135">결제 방법을 바꾸면 동일한 결제 방법을 사용하는 모든 구독 및 청구 프로필에 대해 결제 방법을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-135">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="2b45f-136">결제 방법을 바꾸는다고 해서 기존 결제 방법이 삭제되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-136">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="2b45f-137">여전히 다른 구독 및 청구 프로필을 선택하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-137">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="2b45f-138">단일 구독의 결제 방법을 변경하려면 [단일 구독에 대한 결제 방법 변경](#change-a-payment-method-for-a-single-subscription)을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-138">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="2b45f-139">관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-139">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="2b45f-140">변경할 결제 방법의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-140">Select the row of the payment method to replace.</span></span> <span data-ttu-id="2b45f-141">오른쪽 창에는 선택한 결제 방법을 사용하는 모든 청구 프로필 및 개인 구독이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-141">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="2b45f-142">오른쪽 창에서 **모든 항목에 대해 결제 방법 변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-142">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="2b45f-143">기존 결제 방법을 사용하려는 경우, 드롭다운 목록에서 하나를 선택하고 **변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-143">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2b45f-144">청구 프로필과 연결된 구독이 있는 경우, 신용 카드나 직불 카드로만 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-144">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="2b45f-145">**결제 방법** 페이지에 나열된 은행 계좌를 사용하는 경우, 드롭다운 목록에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-145">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="2b45f-146">새 결제 방법을 추가하려면 **결제 방법 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-146">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="2b45f-147">**결제 방법 추가** 창에서 계좌 정보를 입력하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-147">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="2b45f-148">테넌트와 동일한 국가의 결제 방법을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-148">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="2b45f-149">드롭다운 목록에 새 결제 방법이 이미 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-149">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="2b45f-150">**변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-150">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="2b45f-151">단일 구독의 결제 방법 변경</span><span class="sxs-lookup"><span data-stu-id="2b45f-151">Change a payment method for a single subscription</span></span>

<span data-ttu-id="2b45f-152">단일 구독 비용을 지불하는 데 사용하는 결제 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-152">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="2b45f-153">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-153">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="2b45f-154">**제품** 탭에서 대체 결제 방법으로 결제하려는 구독을 찾으세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-154">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="2b45f-155">점 3개(추가 작업)를 선택한 다음 **결제 방법 교체** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-155">Select the three dots (more actions), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="2b45f-156">**결제 방법** 드롭다운 목록에서 대체 결제 방법을 선택하거나 결제 방법을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-156">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="2b45f-157">결제 방법을 추가하는 경우 카드 또는 계좌 정보를 입력한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-157">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="2b45f-158">선택한 결제 방법이 올바른지 확인한 다음 **교체** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-158">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="2b45f-159">결제 방법 삭제</span><span class="sxs-lookup"><span data-stu-id="2b45f-159">Delete a payment method</span></span>

<span data-ttu-id="2b45f-160">구독 또는 청구 프로필에 첨부되지 않은 결제 방법만 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-160">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="2b45f-161">상태와 관계 없이 모든 구독에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-161">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="2b45f-162">구독 또는 청구 프로필이 첨부되지 않는 결제 방법 삭제</span><span class="sxs-lookup"><span data-stu-id="2b45f-162">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="2b45f-163">결제 방법이 구독 또는 청구 프로필과 관련이 없는 경우 바로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-163">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="2b45f-164">관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-164">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="2b45f-165">삭제할 결제 방법을 찾고 점 세 개를 선택한 다음 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-165">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="2b45f-166">오른쪽 창의 맨 아래에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-166">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="2b45f-167">구독 또는 청구 프로필이 연결된 결제 방법 삭제</span><span class="sxs-lookup"><span data-stu-id="2b45f-167">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="2b45f-168">구독 또는 청구 프로필에 결제 방법이 연결되어 있는 경우 먼저 기존 결제 방법으로 바꾸거나 새 결제 방법을 추가한 다음 이전 결제 방법을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-168">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="2b45f-169">관리 센터에서 **청구** > **청구서 및 결제** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">결제 방법</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-169">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="2b45f-170">삭제할 결제 방법의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-170">Select the row for the payment method to delete.</span></span> <span data-ttu-id="2b45f-171">오른쪽 창에는 해당 결제 방법을 사용하는 기존 구독이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-171">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="2b45f-172">오른쪽 창에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-172">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="2b45f-173">기존 결제 방법을 사용하려면 드롭다운 목록에서 결제 방법을 하나 선택하고 **다음** 을 선택한 다음 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-173">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2b45f-174">청구 프로필과 연결된 구독이 있는 경우 신용 카드로만 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-174">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="2b45f-175">**결제 방법** 페이지에 은행 계좌가 있는 경우 드롭다운 목록에서 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-175">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="2b45f-176">새 결제 방법을 추가하려면 **결제 방법 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-176">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="2b45f-177">추가할 결제 방법 유형을 선택하고 계정 정보를 입력한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-177">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="2b45f-178">드롭다운 목록에 새 결제 방법이 이미 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-178">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="2b45f-179">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-179">Select **Next**.</span></span>
8. <span data-ttu-id="2b45f-180">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-180">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="2b45f-181">결제 방법 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2b45f-181">Troubleshoot payment methods</span></span>

| <span data-ttu-id="2b45f-182">문제</span><span class="sxs-lookup"><span data-stu-id="2b45f-182">Issue</span></span> | <span data-ttu-id="2b45f-183">문제 해결 단계</span><span class="sxs-lookup"><span data-stu-id="2b45f-183">Troubleshooting steps</span></span> |
|:----------|:-----|
|<span data-ttu-id="2b45f-184">**"현재 브라우저가 쿠키를 차단하도록 설정되어 있습니다"라는 오류 메시지가 나타납니다.**</span><span class="sxs-lookup"><span data-stu-id="2b45f-184">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="2b45f-185">타사 쿠키를 허용하도록 브라우저를 설정하고 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-185">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="2b45f-186">**내 신용 카드 또는 직불 카드가 거부되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="2b45f-186">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="2b45f-187">신용 카드나 직불 카드로 결제하는 데 카드가 거부된 경우 Microsoft에서 결제를 처리하지 못했다는 내용의 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-187">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="2b45f-188">카드 세부 정보 &mdash;카드 번호, 만료 날짜, 카드에 적힌 이름, 도시, 주 및 우편 번호를 포함한 주소&mdash;가 카드 및 명세서에 표시된 것과 정확히 일치하는지 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-188">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="2b45f-189">**구독 세부 정보** 페이지의 결제 섹션에 있는 **잔액 정산** 링크를 사용하여 카드 정보를 업데이트하고 즉시 결제를 제출할 수 있습니다..</span><span class="sxs-lookup"><span data-stu-id="2b45f-189">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="2b45f-190">자세한 내용은 [미지불 잔액이 있는 경우 어떻게 해야 하나요?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-190">For more information, see [What if I have an outstanding balance?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span></span>  <br/><br/>  <span data-ttu-id="2b45f-191">"거부"되었다는 메시지가 계속 표시되면 해당 은행에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="2b45f-191">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="2b45f-192">카드가 활성화되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-192">It's possible that your card isn't active.</span></span> <span data-ttu-id="2b45f-193">최근에 업데이트된 만료 날짜가 있는 카드를 메일에 받은 경우 카드가 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-193">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="2b45f-194">또한 해당 은행에서 카드가 온라인 거래, 국제 거래 또는 반복 거래에 대해 승인되지 않았는지 여부를 알려줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-194">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="2b45f-195">**카드 또는 은행 계좌 번호를 업데이트하려고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2b45f-195">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="2b45f-196">기존 결제 방법으로는 카드 또는 계좌 번호를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-196">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="2b45f-197">카드 또는 계좌 번호가 변경된 경우 [다른 결제 수단으로 교체](#replace-a-payment-method)하여 모든 활성 구독을 결제 수단에서 새 결제 수단으로 이동한 다음, [이전 결제 수단을 삭제](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-197">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="2b45f-198">**계정에 카드 또는 은행 계좌가 하나밖에 없는데 그 카드 또는 은행 계좌를 제거하고 싶습니다.**</span><span class="sxs-lookup"><span data-stu-id="2b45f-198">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="2b45f-199">결제 수단이 하나 뿐인 경우 삭제하기 전에 [새 결제 수단으로 교체](#replace-a-payment-method)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-199">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="2b45f-200">**카드 또는 은행 계좌를 추가할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="2b45f-200">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="2b45f-201">테넌트와 동일한 국가에서 발급한 결제 방법을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-201">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="2b45f-202">카드 또는 은행 계좌 정보를 입력하는 데 문제가 있는 경우 [지원에 문의](../../business-video/get-help-support.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b45f-202">If you have trouble entering your card or bank account information, you can [contact support](../../business-video/get-help-support.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="2b45f-203">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="2b45f-203">Related content</span></span>

<span data-ttu-id="2b45f-204">[비즈니스 구독 요금 지불](pay-for-your-subscription.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="2b45f-204">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="2b45f-205">[웹용 청구 프로필 관리](manage-billing-profiles.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="2b45f-205">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="2b45f-206">[청구 주기 변경](change-payment-frequency.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="2b45f-206">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>

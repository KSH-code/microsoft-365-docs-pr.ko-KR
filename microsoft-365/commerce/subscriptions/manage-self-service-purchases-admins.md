---
title: 관리자 (셀프 서비스 구입) 관리
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 관리자는 조직의 사용자가 만든 셀프 서비스 구매를 관리 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: f10f525f8efc6bc63e2fa042c299a6d03c77d0cb
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430001"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="37c81-103">셀프 서비스 구매(관리자) 관리</span><span class="sxs-lookup"><span data-stu-id="37c81-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="37c81-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-104">The admin center is changing.</span></span> <span data-ttu-id="37c81-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c81-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="37c81-106">관리자는 조직의 사용자가 만든 셀프 서비스 구매를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="37c81-107">제품 이름, 구매자 이름, 구독 구입, 만료 날짜, 구입 가격 및 각 셀프 서비스 구매에 대 한 사용자 지정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="37c81-108">조직에서 필요한 경우 PowerShell을 통해 제품별로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="37c81-109">셀프 서비스 구매 나 중앙을 통해 구매한 제품에 대해 동일한 데이터 관리 및 액세스 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="37c81-110">조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="37c81-111">자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="37c81-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="37c81-112">셀프 서비스 구독 보기</span><span class="sxs-lookup"><span data-stu-id="37c81-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="37c81-113">관리 센터에서 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="37c81-114">**결과 구체화**옆의 **계정 유형** 드롭다운에서 **셀프 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>
3. <span data-ttu-id="37c81-115">구독에 대 한 세부 정보를 보려면 목록에서 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="37c81-116">셀프 서비스 구매 구독 라이선스를 가진 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="37c81-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="37c81-117">관리 센터에서 **청구**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="37c81-118">필터 아이콘을 선택한 다음 **셀프 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-118">Choose the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="37c81-119">사용자에 게 할당 된 라이선스를 볼 제품을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="37c81-120">제품에 대 한 구매를 여러 개 사용 하는 경우 해당 제품이 한 번만 나열 되며 **사용 가능한 수량** 열에 해당 제품에 대해 구매한 모든 구독의 합계가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="37c81-121">**사용자** 목록은 셀프 서비스 구매를 수행한 사용자 이름별로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="37c81-122">이러한 구독에 대 한 라이선스가 있는 사용자 목록을 내보내려면 내보낼 구독을 선택 하 고 **사용자 내보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="37c81-123">셀프 서비스 구매 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="37c81-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="37c81-124">조직의 사용자에 대해 셀프 서비스 구매를 사용 하지 않도록 설정 하거나 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="37c81-125">**MSCommerce** PowerShell 모듈에는 조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부 및 해당 제품에 **대 한 정책에 대** 한 **policyid** 매개 변수 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="37c81-126">**MSCommerce** PowerShell 모듈을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="37c81-127">제품에서 사용 하거나 사용 하지 않도록 설정 되었는지 여부에 관계 없이 **AllowSelfServicePurchase** 매개 변수 값의 기본 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="37c81-128">해당 하는 제품 목록 및 셀프 서비스 구매가 사용 하도록 설정 되었는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="37c81-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="37c81-129">특정 제품에 대 한 현재 설정을 보거나 수정 하 여 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="37c81-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="37c81-130">자세한 내용은 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="37c81-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="37c81-131">단일 구독을 통해 라이선스 중앙 집중화</span><span class="sxs-lookup"><span data-stu-id="37c81-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="37c81-132">기존 라이선스를 할당 하거나 셀프 서비스 구매에 할당 된 사용자에 대 한 기존 계약을 통해 추가 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="37c81-133">이러한 중앙에서 구매한 라이선스를 할당 한 후에는 purchasers에서 기존 구독을 취소 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="37c81-134">전역 관리자 또는 청구 관리자 계정을 사용 하 여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a> 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>
2. <span data-ttu-id="37c81-135">**결제**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">구매 서비스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
3. <span data-ttu-id="37c81-136">구매할 제품을 찾아 선택한 다음 **구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
4. <span data-ttu-id="37c81-137">나머지 단계를 완료 하 여 구매를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-137">Complete the remaining steps to complete your purchase.</span></span>
5. <span data-ttu-id="37c81-138">보기의 단계에 따라 [셀프 서비스를 구매한 구독에 대 한 라이선스를 가진](#view-who-has-licenses-for-a-self-service-purchase-subscription) 사용자 목록을 내보내 6 단계에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>
6. <span data-ttu-id="37c81-139">다른 구독에 라이선스가 있는 모든 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="37c81-140">전체 단계는 [사용자에 게 라이선스 할당](../../admin/manage/assign-licenses-to-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37c81-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
7. <span data-ttu-id="37c81-141">셀프 서비스 구매 구독을 구매한 사용자에 게 문의 하 여 취소 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="37c81-142">셀프 서비스 구매 구독 사용</span><span class="sxs-lookup"><span data-stu-id="37c81-142">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="37c81-143">조직의 사용자가 만든 셀프 서비스 구매 구독을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-143">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="37c81-144">셀프 서비스 구매 구독을 사용 하는 경우 다음 두 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-144">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="37c81-145">사용자를 다른 구독으로 이동 하 고 원래 구독을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-145">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="37c81-146">셀프 서비스 구매 구독을 취소 하 고 할당 된 사용자 로부터 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-146">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="37c81-147">다른 구독으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="37c81-147">Move users to a different subscription</span></span>

<span data-ttu-id="37c81-148">사용자를 다른 구독으로 이동 하면 이전 구독이 자동으로 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-148">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="37c81-149">최초 셀프 서비스 구매 구독을 구매한 사용자에 게 구독이 취소 되었음을 알리는 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-149">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="37c81-150">사용자를 이동 하는 구독에서 이동할 각 사용자에 대해 사용 가능한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-150">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="37c81-151">관리 센터에서 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-151">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="37c81-152">**제품** 탭에서 필터 아이콘을 선택한 다음 **셀프 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-152">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="37c81-153">수행 하려는 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-153">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="37c81-154">구독 정보 페이지의 **구독 및 설정** 섹션에서 **이 구독에 대 한 제어권 적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-154">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="37c81-155">오른쪽 창에서 **사용자 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-155">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="37c81-156">사용자를 이동할 대상 제품을 선택 하 고 **사용자 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-156">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="37c81-157">**사용자 이동** 상자에서 **사용자 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-157">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="37c81-158">이동 프로세스는 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-158">The move process might take several minutes.</span></span> <span data-ttu-id="37c81-159">프로세스를 실행 하는 동안 브라우저를 닫지 마세요.</span><span class="sxs-lookup"><span data-stu-id="37c81-159">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="37c81-160">이동 프로세스가 완료 되 면 **이동 완료 창을**닫습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-160">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="37c81-161">구독 정보 페이지에는 셀프 서비스를 구매한 구독의 **구독 상태가** **삭제**됨으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-161">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="37c81-162">셀프 서비스 구매 구독 취소</span><span class="sxs-lookup"><span data-stu-id="37c81-162">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="37c81-163">셀프 서비스 구매 구독을 취소 하도록 선택 하면 라이선스가 있는 사용자가 제품에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-163">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="37c81-164">최초 셀프 서비스 구매 구독을 구매한 사용자에 게 구독이 취소 되었음을 알리는 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-164">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="37c81-165">관리 센터에서 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 청구 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-165">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="37c81-166">**제품** 탭에서 필터 아이콘을 선택한 다음 **셀프 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-166">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="37c81-167">취소할 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-167">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="37c81-168">구독 정보 페이지의 **구독 및 설정** 섹션에서 **이 구독에 대 한 제어권 적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-168">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="37c81-169">오른쪽 창에서 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-169">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="37c81-170">드롭다운 목록에서 취소에 대 한 이유를 선택한 다음 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-170">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="37c81-171">취소 하 시겠습니까 **?** 상자에서 **구독 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-171">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="37c81-172">오른쪽 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-172">Close the right pane.</span></span>
9. <span data-ttu-id="37c81-173">구독 정보 페이지에서 **구독 상태가** **삭제**됨으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c81-173">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="37c81-174">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="37c81-174">Need help?</span></span> <span data-ttu-id="37c81-175">문의처.</span><span class="sxs-lookup"><span data-stu-id="37c81-175">Contact us.</span></span>

<span data-ttu-id="37c81-176">셀프 서비스 구매에 대 한 일반적인 질문은 [셀프 서비스 구매 FAQ](self-service-purchase-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37c81-176">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="37c81-177">궁금한 사항이 있거나 셀프 서비스 구매에 도움이 필요한 경우 [고객 지원에 문의 하세요](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="37c81-177">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
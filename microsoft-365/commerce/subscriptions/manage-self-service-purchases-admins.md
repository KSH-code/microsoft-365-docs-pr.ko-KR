---
title: 셀프 서비스 구매 관리(관리자)
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 관리자는 조직의 사용자가 만든 셀프 서비스 구매를 관리하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920183"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="5cdf5-103">셀프 서비스 구매(관리자) 관리</span><span class="sxs-lookup"><span data-stu-id="5cdf5-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5cdf5-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-104">The admin center is changing.</span></span> <span data-ttu-id="5cdf5-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="5cdf5-106">관리자는 조직의 사용자가 셀프 서비스 구매를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="5cdf5-107">각 셀프 서비스 구매에 대한 제품 이름, 구매자 이름, 구입한 구독, 만료 날짜, 구매 가격 및 할당된 사용자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="5cdf5-108">조직에서 요구하는 경우 PowerShell을 통해 제품 기준으로 셀프 서비스 구매를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5cdf5-109">셀프 서비스 구매 또는 중앙에서 구입한 제품에 대해 동일한 데이터 관리 및 액세스 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="5cdf5-110">조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="5cdf5-111">자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조하세요.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf5-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="5cdf5-112">셀프 서비스 구독 보기</span><span class="sxs-lookup"><span data-stu-id="5cdf5-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="5cdf5-113">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5cdf5-114">제품 **탭에서** 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="5cdf5-115">구독에 대한 자세한 내용을 확인하려면 목록에서 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="5cdf5-116">셀프 서비스 구매 구독에 대한 라이선스가 있는 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="5cdf5-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="5cdf5-117">관리 센터에서 청구 라이선스   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="5cdf5-118">필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="5cdf5-119">제품을 선택하여 사용자에게 할당된 라이선스를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="5cdf5-120">제품에 대한 구매가 여러 번 있는 경우 해당 제품은  한 번만 나열됩니다. 사용 가능한 수량 열에는 해당 제품에 대해 구입한 모든 구독의 총계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="5cdf5-121">사용자 **목록은** 셀프 서비스 구매를 한 사용자의 이름으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="5cdf5-122">이러한 구독에 대한 라이선스가 있는 사용자 목록을 내보내기하려면 내보낼 구독을 선택한 다음 사용자 **내보내기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="5cdf5-123">셀프 서비스 구매 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5cdf5-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="5cdf5-124">조직의 사용자에 대해 셀프 서비스 구매를 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="5cdf5-125">**MSCommerce** PowerShell 모듈에는 조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부와 제품을 제어할 수 있는 **AllowSelfServicePurchase에** 대한 **PolicyID** 매개 변수 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="5cdf5-126">**MSCommerce** PowerShell 모듈을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="5cdf5-127">**AllowSelfServicePurchase** 매개 변수 값의 기본 상태(제품에서 사용 또는 사용 안 하도록 설정되어 있는지 여부)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="5cdf5-128">해당 제품 목록 및 셀프 서비스 구매를 사용할 수 있는지 여부 보기</span><span class="sxs-lookup"><span data-stu-id="5cdf5-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="5cdf5-129">특정 제품의 현재 설정을 보거나 수정하여 특정 제품을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5cdf5-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="5cdf5-130">자세한 내용은 [MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용을 참조하세요.](allowselfservicepurchase-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf5-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="5cdf5-131">단일 구독에서 라이선스 중앙 집중화</span><span class="sxs-lookup"><span data-stu-id="5cdf5-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="5cdf5-132">셀프 서비스 구매에 할당된 사용자의 기존 계약을 통해 기존 라이선스를 할당하거나 추가 구독을 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="5cdf5-133">중앙에서 구입한 라이선스를 할당한 후 구매자에 기존 구독을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="5cdf5-134">관리 센터에서 청구  구매 서비스 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="5cdf5-135">구입하려는 제품을 찾아 선택한 다음 구입 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="5cdf5-136">나머지 단계를 완료하여 구매를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="5cdf5-137">셀프 서비스 [](#view-who-has-licenses-for-a-self-service-purchase-subscription) 구매 구독에 대한 라이선스가 있는 사용자 보기의 단계에 따라 다음 단계에서 참조할 사용자 목록을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="5cdf5-138">다른 구독에 라이선스가 있는 모든 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="5cdf5-139">전체 단계는 [사용자에게 라이선스 할당을 참조하세요.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf5-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="5cdf5-140">셀프 서비스 구매 구독을 구입한 담당자에게 연락하여 [취소해달고 요청합니다.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="5cdf5-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="5cdf5-141">셀프 서비스 구매 구독 인계</span><span class="sxs-lookup"><span data-stu-id="5cdf5-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="5cdf5-142">조직의 사용자가 만든 셀프 서비스 구매 구독을 대신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="5cdf5-143">셀프 서비스 구매 구독을 인계할 경우 다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="5cdf5-144">사용자를 다른 구독으로 이동하고 원래 구독을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="5cdf5-145">셀프 서비스 구매 구독을 취소하고 할당된 사용자에서 라이선스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="5cdf5-146">다른 구독으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="5cdf5-146">Move users to a different subscription</span></span>

<span data-ttu-id="5cdf5-147">사용자를 다른 구독으로 이동하면 이전 구독이 자동으로 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="5cdf5-148">셀프 서비스 구매 구독을 처음 구입한 사용자는 구독이 취소되었습니다.는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="5cdf5-149">사용자를 이동하는 구독에서 이동하는 각 사용자에 대해 사용 가능한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="5cdf5-150">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5cdf5-151">제품 **탭에서** 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="5cdf5-152">인계할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="5cdf5-153">구독 세부 정보 페이지의 구독 및 설정 **섹션에서** 이 구독 **제어 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="5cdf5-154">오른쪽 창에서 사용자 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="5cdf5-155">사용자를 이동할 제품을 선택한 다음 사용자 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="5cdf5-156">사용자 **이동 상자에서** 사용자 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="5cdf5-157">이동 프로세스는 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-157">The move process might take several minutes.</span></span> <span data-ttu-id="5cdf5-158">프로세스가 실행되는 동안 브라우저를 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="5cdf5-159">이동 프로세스가 완료되면 완료된 **이동 창을 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="5cdf5-160">구독 세부 정보 페이지에서  셀프 서비스 구매 구독의 구독 상태는 **삭제된 으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="5cdf5-161">셀프 서비스 구매 구독 취소</span><span class="sxs-lookup"><span data-stu-id="5cdf5-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="5cdf5-162">셀프 서비스 구매 구독을 취소하기로 선택하면 라이선스가 있는 사용자는 제품에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="5cdf5-163">셀프 서비스 구매 구독을 처음 구입한 사용자는 구독이 취소되었습니다.는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="5cdf5-164">관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5cdf5-165">제품 **탭에서** 필터 아이콘을 선택한 다음 셀프 **서비스 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="5cdf5-166">취소할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="5cdf5-167">구독 세부 정보 페이지의 구독 및 설정 **섹션에서** 이 구독 **제어 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="5cdf5-168">오른쪽 창에서 구독 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="5cdf5-169">드롭다운 목록에서 취소 이유를 선택한 다음 구독 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="5cdf5-170">**취소할지 여부** 상자에서 구독 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="5cdf5-171">오른쪽 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-171">Close the right pane.</span></span>
9. <span data-ttu-id="5cdf5-172">구독 세부 정보 페이지에서 구독 **상태가** 삭제된 **것으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="5cdf5-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="5cdf5-173">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="5cdf5-173">Need help?</span></span> <span data-ttu-id="5cdf5-174">문의해 주시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5cdf5-174">Contact us.</span></span>

<span data-ttu-id="5cdf5-175">셀프 서비스 구매에 대한 일반적인 질문은 셀프 서비스 [구매 FAQ를 참조하세요.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf5-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="5cdf5-176">셀프 서비스 구매에 대한 질문이나 도움이 필요한 경우 고객 [지원에 문의하세요.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf5-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
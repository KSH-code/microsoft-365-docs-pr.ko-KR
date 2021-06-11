---
title: 자동 클레임 정책 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.review: yinggiy, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
description: 특정 앱에 대한 라이선스를 사용자에게 자동으로 할당하는 자동 클레임 정책을 만들고 관리하는 방법을 학습합니다.
search.appverid: MET150
ms.date: 04/06/2021
ms.openlocfilehash: b104700905b3753466036411368951f12a7012d8
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331649"
---
# <a name="manage-auto-claim-policies"></a><span data-ttu-id="1e279-103">자동 클레임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="1e279-103">Manage auto-claim policies</span></span>

<span data-ttu-id="1e279-104">자동 클레임 정책을 사용하면 사용자가 앱에 처음 로그인할 때 제품에 대한 라이선스를 자동으로 클레임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-104">An auto-claim policy lets users automatically claim a license for a product the first time that they sign into an app.</span></span> <span data-ttu-id="1e279-105">관리자는 일반적으로 수동으로 또는 그룹 기반 라이선싱을 사용하여 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-105">As an admin, you typically assign licenses to users either manually, or by using group-based licensing.</span></span> <span data-ttu-id="1e279-106">자동 클레임 정책을 사용하면 사용자가 라이선스를 자동으로 클레임할 수 있는 제품을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-106">By using auto-claim policies, you manage the products for which users can automatically claim licenses.</span></span> <span data-ttu-id="1e279-107">또한 해당 라이선스가 시작되는 제품을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-107">You can also control which products those licenses come from.</span></span>

<span data-ttu-id="1e279-108">자동 클레임 정책을 만든 후 다음 작업을 수행하여 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-108">After you create an auto-claim policy, you can do the following tasks to manage the policy:</span></span>

- [<span data-ttu-id="1e279-109">정책 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="1e279-109">Turn the policy on or off</span></span>](#turn-a-policy-on-or-off)
- [<span data-ttu-id="1e279-110">정책 이름 편집</span><span class="sxs-lookup"><span data-stu-id="1e279-110">Edit the policy friendly name</span></span>](#edit-the-policy-friendly-name)
- [<span data-ttu-id="1e279-111">백업 제품 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="1e279-111">Add or remove backup products</span></span>](#add-or-remove-backup-products)
- [<span data-ttu-id="1e279-112">할당 앱 및 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="1e279-112">Manage the assigning apps and services</span></span>](#change-the-assigning-apps-and-services)
- [<span data-ttu-id="1e279-113">할당 순서 변경</span><span class="sxs-lookup"><span data-stu-id="1e279-113">Change the assigning order</span></span>](#change-the-assigning-order-for-backup-products)
- [<span data-ttu-id="1e279-114">정책 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="1e279-114">View a policy report</span></span>](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> <span data-ttu-id="1e279-115">자동 클레임 정책은 현재 해당 정책에 대해 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e279-115">Auto-claim policies are currently only available for Microsoft Teams.</span></span> <span data-ttu-id="1e279-116">향후에 더 많은 제품을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-116">More products will be available to use in the future.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1e279-117">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="1e279-117">Before you begin</span></span>

<span data-ttu-id="1e279-118">자동 클레임 정책을 만들고 관리하려면 전역, 사용자 또는 라이선스 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-118">You must be a Global, User, or License admin to create and manage auto-claim policies.</span></span> <span data-ttu-id="1e279-119">자세한 내용은 [Microsoft 365 관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e279-119">For more information, see [About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a><span data-ttu-id="1e279-120">자동 클레임 정책 기능 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="1e279-120">Turn the auto-claim policy feature on or off</span></span>

<span data-ttu-id="1e279-121">기본적으로 자동 클레임 정책 기능은 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-121">By default, the auto-claim policy feature is turned off.</span></span> <span data-ttu-id="1e279-122">기능을 사용하려면 먼저 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-122">Before you can use the feature, you must first turn it on.</span></span> <span data-ttu-id="1e279-123">기능을 켜고 나면 자동 클레임 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-123">After you turn on the feature, you can create an auto-claim policy.</span></span>

### <a name="turn-on-auto-claim-policies"></a><span data-ttu-id="1e279-124">자동 클레임 정책 켜기</span><span class="sxs-lookup"><span data-stu-id="1e279-124">Turn on auto-claim policies</span></span>

1. <span data-ttu-id="1e279-125">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-125">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-126">페이지 가운데에서 설정 **켜기 단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-126">In the center of the page, select the **Turn on setting** button.</span></span>

### <a name="turn-off-auto-claim-policies"></a><span data-ttu-id="1e279-127">자동 클레임 정책 끄기</span><span class="sxs-lookup"><span data-stu-id="1e279-127">Turn off auto-claim policies</span></span>

<span data-ttu-id="1e279-128">전역 관리자만 자동 클레임 정책 설정을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-128">Only a Global admin can turn off an auto-claim policy setting.</span></span>

1. <span data-ttu-id="1e279-129">관리 센터에서 설정  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">설정 페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-129">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org settings</a> page.</span></span>
2. <span data-ttu-id="1e279-130">표 아래쪽에서 사용자 소유 앱 및 **서비스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-130">Near the bottom of the table, select **User owned apps and services**.</span></span>
3. <span data-ttu-id="1e279-131">오른쪽 창에서 사용자가 처음 로그인할 때 라이선스를 자동 클레임할 수 있도록 합니다. 상자의 **선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-131">In the right pane, clear the box for **Let users auto-claim licenses the first time they sign in**.</span></span>

<span data-ttu-id="1e279-132">이미 활성 정책이 있지만 더 이상 사용자가 라이선스를 클레임하지 못하게 하려는 경우 [정책을 해제합니다.](#turn-a-policy-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="1e279-132">If you already have an active policy, but you don't want any more users to claim licenses, [turn off the policy](#turn-a-policy-on-or-off).</span></span> <span data-ttu-id="1e279-133">자동 클레임 정책을 끄면 더 이상 사용자가 해당 시점부터 라이선스를 클레임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-133">When you turn off an auto-claim policy, no more users can claim a license from that point on.</span></span> <span data-ttu-id="1e279-134">이미 라이선스를 요구한 사용자는 라이선스를 잃지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-134">Users who already claimed a license don't lose their license.</span></span>

## <a name="create-an-auto-claim-policy"></a><span data-ttu-id="1e279-135">자동 클레임 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1e279-135">Create an auto-claim policy</span></span>

<span data-ttu-id="1e279-136">자동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">클레임 정책</a> 탭에는 만든 정책이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-136">The <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab lists the policies that you create.</span></span> <span data-ttu-id="1e279-137">이 탭에서 정책의 이름, 정책과 연결된 앱, 정책에 할당된 제품, 사용 가능한 라이선스 수 및 정책 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-137">On this tab, you can see: the name of the policy, the app that is associated with the policy, the product that's assigned to the policy, the number of available licenses, and the status of the policy.</span></span>

<span data-ttu-id="1e279-138">자동 클레임 정책을 만들 때 백업 제품을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-138">When you create an auto-claim policy, you can add a backup product to it.</span></span> <span data-ttu-id="1e279-139">기본 제품이 라이선스가 부재 중이면 백업 제품을 사용하여 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-139">If the primary product is out of licenses, the backup product is used to assign licenses to users.</span></span> <span data-ttu-id="1e279-140">최대 4개의 백업 제품을 추가하고 백업 제품을 사용하는 순서를 [변경할 수 있습니다.](#change-the-assigning-order-for-backup-products)</span><span class="sxs-lookup"><span data-stu-id="1e279-140">You can add up to four backup products and [change the order in which they're used](#change-the-assigning-order-for-backup-products).</span></span> <span data-ttu-id="1e279-141">자세한 내용은 백업 제품 [추가 또는 제거를 참조합니다.](#add-or-remove-backup-products)</span><span class="sxs-lookup"><span data-stu-id="1e279-141">To learn more, see [Add or remove backup products](#add-or-remove-backup-products).</span></span>

> [!NOTE]
> <span data-ttu-id="1e279-142">현재는 자동 클레임 정책을 하나만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-142">Currently, you can only create one auto-claim policy.</span></span> <span data-ttu-id="1e279-143">더 많은 제품이 이 기능을 사용할 수 있게 수록 만들 수 있는 정책의 수가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-143">The number of policies you can create will increase as more products are able to use this feature.</span></span>

1. <span data-ttu-id="1e279-144">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-144">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-145">정책 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-145">Select **Add a policy**.</span></span>
3. <span data-ttu-id="1e279-146">이 **자동 클레임** 정책 이름 지정 페이지에서 정책의 이름을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-146">On the **Name this auto-claim policy** page, enter a name for the policy, then select **Next**.</span></span>
4. <span data-ttu-id="1e279-147">자동 **클레임** 앱 및 제품 설정 페이지에서 라이선스를 할당할 앱 및 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-147">On the **Set an auto-claim app and product** page, select an app and the subscription to assign licenses from.</span></span>
5. <span data-ttu-id="1e279-148">백업 제품을 추가하려면 이 정책에 백업 제품 추가를 선택한 다음 목록에서 제품을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="1e279-148">If you want to add a backup product, select **Add a backup product to this policy**, then select the product from the list.</span></span>
6. <span data-ttu-id="1e279-149">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-149">Select **Next**.</span></span>
7. <span data-ttu-id="1e279-150">앱 **선택 페이지에서** 제외하거나 라이선스에 포함할 앱의 상자를 선택 취소하거나 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-150">On the **Select apps** page, clear or select the boxes for the apps to exclude or include with the license, then select **Next**.</span></span>
8. <span data-ttu-id="1e279-151">백업 제품을 하나 이상 추가한 경우 각 제품에 대해 7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-151">If you added one or more backup products, repeat step 7 for each product.</span></span> <span data-ttu-id="1e279-152">그렇지 않으면 9단계로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-152">Otherwise, go to step 9.</span></span>
9. <span data-ttu-id="1e279-153">검토 **및 완료 페이지에서** 새 정책 정보를 확인하고 필요한 사항을 변경한 다음 정책 만들기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-153">On the **Review and finish** page, verify the new policy information, make any necessary changes, then select **Create policy**.</span></span>
10. <span data-ttu-id="1e279-154">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-154">Select **Close**.</span></span>

## <a name="turn-a-policy-on-or-off"></a><span data-ttu-id="1e279-155">정책 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="1e279-155">Turn a policy on or off</span></span>

<span data-ttu-id="1e279-156">정책을 해제하면 더 이상 사용자가 해당 정책에 따라 라이선스를 클레임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-156">When you turn off a policy, no more users can claim licenses under that policy.</span></span> <span data-ttu-id="1e279-157">이 변경은 해당 정책에 따라 라이선스를 이미 클레임한 사용자에게는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-157">The change doesn't affect users who already claimed licenses under that policy.</span></span>

1. <span data-ttu-id="1e279-158">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-158">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-159">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-159">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="1e279-160">세부 정보 창의 이 정책을 켜거나 끄기에서 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-160">In the details pane, under **Turn this policy on or off**, select or clear the check box.</span></span>
4. <span data-ttu-id="1e279-161">**저장을** 선택하여 세부 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-161">Select **Save** to close the details pane.</span></span>

## <a name="edit-the-policy-friendly-name"></a><span data-ttu-id="1e279-162">정책 이름 편집</span><span class="sxs-lookup"><span data-stu-id="1e279-162">Edit the policy friendly name</span></span>

1. <span data-ttu-id="1e279-163">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-163">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-164">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-164">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="1e279-165">세부 정보 창의 정책 **이름 섹션에서** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-165">In the details pane, in the **Policy name** section, select **Edit**.</span></span>
4. <span data-ttu-id="1e279-166">새 정책 이름을 입력한 다음 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-166">Enter a new policy name, then select **Save**.</span></span>
5. <span data-ttu-id="1e279-167">**저장을** 선택하여 세부 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-167">Select **Save** to close the details pane.</span></span>

## <a name="add-or-remove-backup-products"></a><span data-ttu-id="1e279-168">백업 제품 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="1e279-168">Add or remove backup products</span></span>

<span data-ttu-id="1e279-169">정책을 만들 때 제품에 제품을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-169">When you create a policy, you add a product to it.</span></span> <span data-ttu-id="1e279-170">그러면 해당 라이선스 풀의 사용자에게 라이선스가 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-170">Licenses are then automatically assigned to users from that pool of licenses.</span></span> <span data-ttu-id="1e279-171">자동 클레임 정책에 대한 제품을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-171">You can add or remove products for an auto-claim policy at any time.</span></span> <span data-ttu-id="1e279-172">정책과 연결된 제품이 하나 이미 있는 경우 추가하는 제품은 백업 제품으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-172">If you already have one product associated with the policy, any products that you add are considered backup products.</span></span> <span data-ttu-id="1e279-173">첫 번째 제품의 사용 가능한 라이선스 수를 사용하는 경우 정책은 목록의 다음 백업 제품을 사용하여 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-173">When the available number of licenses from the first product are used up, the policy uses the next backup product on the list to assign licenses from.</span></span> <span data-ttu-id="1e279-174">원하는 경우 제품 목록의 다시 [오더를 할](#change-the-assigning-apps-and-services) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-174">You [can reorder the list of products](#change-the-assigning-apps-and-services) as you like.</span></span>

<span data-ttu-id="1e279-175">백업 제품을 제거하면 라이선스를 할당하는 데 더 이상 사용이 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-175">When you remove a backup product, it's no longer used to assign licenses.</span></span> <span data-ttu-id="1e279-176">기존 라이선스가 있는 사용자는 해당 라이선스를 계속 사용하지만 새 사용자는 해당 제품에 대한 라이선스를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-176">Users with an existing license still have that license, but no new users can receive licenses for that product.</span></span>

> [!NOTE]
> <span data-ttu-id="1e279-177">자동 클레임 정책에는 제품이 하나 이상 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-177">An auto-claim policy must contain at least one product.</span></span> <span data-ttu-id="1e279-178">정책에서 모든 제품을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-178">You can't remove all products from a policy.</span></span> <span data-ttu-id="1e279-179">더 이상 특정 자동 클레임 정책에서 라이선스를 할당하지 않는 경우 [정책을 해제합니다.](#view-an-auto-claim-policy-report)</span><span class="sxs-lookup"><span data-stu-id="1e279-179">If you don't want to assign licenses from a specific auto-claim policy anymore, [turn off the policy](#view-an-auto-claim-policy-report).</span></span>

### <a name="add-a-backup-product"></a><span data-ttu-id="1e279-180">백업 제품 추가</span><span class="sxs-lookup"><span data-stu-id="1e279-180">Add a backup product</span></span>

1. <span data-ttu-id="1e279-181">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-181">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-182">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-182">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="1e279-183">세부 정보 창의 아래쪽에서 이 정책에 백업 **제품 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-183">In the details pane, at the bottom, select **Add a backup product to this policy**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="1e279-184">이 링크가 없는 경우 계정과 연결된 제품이 하나뿐이기 때문에 이 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-184">If you don't see this link, it's because you only have one product associated with your account.</span></span>
4. <span data-ttu-id="1e279-185">제품 **추가 창에서** 드롭다운을 사용하여 정책에 추가할 제품을 선택한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-185">In the **Add a product** pane, use the drop-down to choose a product to add to the policy, then select **Add**.</span></span>
5. <span data-ttu-id="1e279-186">**저장을** 선택하여 세부 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-186">Select **Save** to close the details pane.</span></span>

### <a name="remove-a-backup-product"></a><span data-ttu-id="1e279-187">백업 제품 제거</span><span class="sxs-lookup"><span data-stu-id="1e279-187">Remove a backup product</span></span>

1. <span data-ttu-id="1e279-188">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-188">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-189">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-189">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="1e279-190">세부 정보 창의 아래쪽에서 제품 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-190">In the details pane, at the bottom, select **Remove a product**.</span></span>
4. <span data-ttu-id="1e279-191">정책에서 제품 제거 **창에서** 제거할 정책의 상자를 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-191">In the **Remove a product from the policy** pane, select the box for the policy that you want to remove, then select **Save**.</span></span>
5. <span data-ttu-id="1e279-192">세부 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-192">Close the details pane.</span></span>

## <a name="change-the-assigning-apps-and-services"></a><span data-ttu-id="1e279-193">할당 앱 및 서비스 변경</span><span class="sxs-lookup"><span data-stu-id="1e279-193">Change the assigning apps and services</span></span>

<span data-ttu-id="1e279-194">각 제품에는 앱 및 서비스 모음이 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-194">Each product has a collection of apps and services associated with it.</span></span>
<span data-ttu-id="1e279-195">자동 클레임 정책의 각 제품에 대해 사용자에게 해당 제품에 대한 라이선스가 자동으로 할당될 때 포함할 앱 및 서비스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-195">For each product in your auto-claim policy, you can specify which apps and services to include when a user is automatically assigned a license to that product.</span></span>

1. <span data-ttu-id="1e279-196">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-196">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-197">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-197">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="1e279-198">세부 정보 창의 앱 및 서비스 **에서** 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-198">In the details pane, under **Apps and services**, select **Edit**.</span></span>
4. <span data-ttu-id="1e279-199">앱 **및 서비스 창의** 제품  드롭다운에서 단일 제품을 선택하거나 모든 제품을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-199">In the **Apps and services** pane, from the **Product** drop-down, select a single product, or select **All products**.</span></span>
5. <span data-ttu-id="1e279-200">사용자가 액세스할 수 있도록 할 앱 및 서비스에 대한 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-200">Check or clear the boxes for apps and services that you want users to have or not have access to.</span></span>
6. <span data-ttu-id="1e279-201">완료되면 저장을 선택한 다음 세부 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-201">When you're finished, select **Save**, then close the details pane.</span></span>

## <a name="change-the-assigning-order-for-backup-products"></a><span data-ttu-id="1e279-202">백업 제품의 할당 순서 변경</span><span class="sxs-lookup"><span data-stu-id="1e279-202">Change the assigning order for backup products</span></span>

<span data-ttu-id="1e279-203">정책에 할당된 백업 제품이 있는 경우 사용자가 앱에 로그인할 때 라이선스를 할당하는 데 사용되는 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-203">If you have backup products assigned to the policy, you can change the order in which they're used to assign licenses when users sign in to the app.</span></span>

1. <span data-ttu-id="1e279-204">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-204">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-205">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-205">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="1e279-206">세부 정보 창의 제품  라이선스 섹션에서 이동할 제품 옆의 상자를 선택한 다음 아래로  이동 또는 아래로 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-206">In the details pane, in the **Product licenses** section, select the box next to the product that you want to move, then select **Move up** or **Move down**.</span></span>
4. <span data-ttu-id="1e279-207">다시 오더할 각 제품에 대해 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-207">Repeat step 3 for each product that you want to reorder.</span></span>
5. <span data-ttu-id="1e279-208">제품 재배치가 끝나면 저장을 선택하여 세부  정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-208">When you're finished reordering the products, select **Save** to close the details pane.</span></span>

## <a name="view-an-auto-claim-policy-report"></a><span data-ttu-id="1e279-209">자동 클레임 정책 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="1e279-209">View an auto-claim policy report</span></span>

1. <span data-ttu-id="1e279-210">관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-210">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="1e279-211">보고서 **보기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e279-211">Select **View report**.</span></span> <span data-ttu-id="1e279-212">자동 **클레임 정책 보고서 페이지에** 지난 90일 동안 각 정책에서 할당된 모든 라이선스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-212">The **Auto-claim policy report** page lists all licenses assigned from each policy in the last 90 days.</span></span> <span data-ttu-id="1e279-213">기본적으로 페이지에 지난 90일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-213">By default, the page shows the past 90 days.</span></span>
3. <span data-ttu-id="1e279-214">표시된 기간을 변경하려면 지난 **30일** 드롭다운 목록을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-214">To change the time period shown, select the **Past 30 days** drop-down list.</span></span> <span data-ttu-id="1e279-215">지난 1, 7, 30 및 90 일에 대 한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-215">You can view reports for the past 1, 7, 30, and 90 days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e279-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1e279-216">Next steps</span></span>

<span data-ttu-id="1e279-217">주기적으로 자동 클레임  정책 탭으로 돌아가서 만든 정책에 따라 라이선스가 클레임된 사용자 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e279-217">You can periodically return to the **Auto-claim policy** tab to see a list of users who have claimed licenses under the policies you created.</span></span>

## <a name="related-content"></a><span data-ttu-id="1e279-218">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="1e279-218">Related content</span></span>

<span data-ttu-id="1e279-219">[사용자에게 라이선스 할당](../../admin/manage/assign-licenses-to-users.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="1e279-219">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="1e279-220">[구독 라이선스 구입 또는](buy-licenses.md) 제거(문서)</span><span class="sxs-lookup"><span data-stu-id="1e279-220">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>\
<span data-ttu-id="1e279-221">[구독 및 라이선스](subscriptions-and-licenses.md) 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="1e279-221">[Understand subscriptions and licenses](subscriptions-and-licenses.md) (article)</span></span>
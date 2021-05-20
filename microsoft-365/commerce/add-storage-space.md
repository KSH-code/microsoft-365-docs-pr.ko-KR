---
title: 구독에 대한 저장소 공간 추가
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: 사용자 구독에 파일 Microsoft 365 추가합니다. 추가 파일 저장소를 사용하면 추가 콘텐츠를 온라인 및 SharePoint 저장할 수 OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: b573205c7053aba0339d1f32deb2996ef80f8754
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572324"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="19e6d-104">구독에 대한 저장소 공간 추가</span><span class="sxs-lookup"><span data-stu-id="19e6d-104">Add storage space for your subscription</span></span>

<span data-ttu-id="19e6d-105">SharePoint Online 사이트 모음의 저장소 공간이 부족해지면 해당 플랜에 자격이 있는 경우 구독에 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="19e6d-106">사용 가능한 추가 **Office 365 Extra File Storage** 목록에 해당 목록이 없는 경우 요금제가 부적격하지 않다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="19e6d-107">자세한 내용은 내 계획에 [적합한가요?를 참조하세요.](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="19e6d-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="19e6d-108">볼륨 라이선싱 또는 CSP를 통해 구독을 구입한  경우 Microsoft에서 직접 조직의 Office 365 Extra File Storage 구입할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="19e6d-109">담당자 또는 파트너에게 도움을 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="19e6d-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="19e6d-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="19e6d-110">Before you begin</span></span>

<span data-ttu-id="19e6d-111">이 문서의 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="19e6d-112">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19e6d-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="19e6d-113">사용 가능한 저장소 보기</span><span class="sxs-lookup"><span data-stu-id="19e6d-113">View available storage</span></span>

1. <span data-ttu-id="19e6d-114">SharePoint 관리 센터에서 활성 사이트 페이지로 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">이동한</a> 다음 조직에 대한 [](/sharepoint/sharepoint-admin-role) 관리자 권한이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="19e6d-115">페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="19e6d-116">조직에서 여러 위치에서 Multi-Geo를 Office 365 모든 지리적 위치에서 사용되는 저장소의 양도 표시줄에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![활성 사이트 페이지의 저장소 표시줄](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="19e6d-118">사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="19e6d-119">사용하는 저장소의 용량을 확인한 후 구독에 대한 저장소 공간을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="19e6d-120">저장소 공간을 추가하는 데 얼마나 드는 비용은 이 문서의 단계를 따르고, 추가 구입 전에 가격 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="19e6d-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="19e6d-121">사이트 모음 저장 용량 제한을 설정하는 데 대한 자세한 내용은 [Manage site collection storage limits를 참조하십시오.](/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="19e6d-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="19e6d-122">구독에 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="19e6d-122">Add storage to your subscription</span></span>

<span data-ttu-id="19e6d-123">구독에 대한 추가 저장소를 아직 구입하지 않은 경우 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="19e6d-124">관리 센터에서 청구 구매  서비스 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="19e6d-125">서비스 구매 페이지의  아래쪽에 있는  추가 기능 섹션에서 Office 365 Extra File Storage 및 세부 **정보를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="19e6d-126">제품 세부 정보 페이지에서 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="19e6d-127">필요한 경우 기본 구독을 선택한 다음 추가할 저장소의 기가바이트 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="19e6d-128">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="19e6d-129">어떻게 **표시하나요?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="19e6d-130">주문 **완료 페이지에서** 합계를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="19e6d-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="19e6d-131">변경해야 하는 경우 순서 **편집 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="19e6d-132">주문에 신용 검사가 필요한 경우 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="19e6d-133">완료되면 관리 홈으로  \> **이동 순서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="19e6d-134">저장소 확대 또는 축소</span><span class="sxs-lookup"><span data-stu-id="19e6d-134">Increase or decrease storage</span></span>

<span data-ttu-id="19e6d-135">Office 365 Extra File Storage 추가 기능을 통해 추가 파일  저장소를 이미 구입한 경우 다음 단계를 사용하여 구독에 대한 추가 저장소 공간을 늘리거나 줄이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="19e6d-136">저장소를 1기가바이트까지 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="19e6d-137">추가 저장소 공간을 모두 제거하려면 고객 [지원에 문의합니다.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="19e6d-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="19e6d-138">관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="19e6d-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="19e6d-139">제품 **탭에서** 추가 기능을 포함하는  Office 365 Extra File Storage 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="19e6d-140">제품 세부 정보 페이지의 추가 기능 **섹션에서** 추가 기능 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="19e6d-141">추가 기능 관리 **창의** 추가 기능  목록에서 추가 **Office 365 Extra File Storage.**</span><span class="sxs-lookup"><span data-stu-id="19e6d-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="19e6d-142">수량 **텍스트 상자에** 구독에 사용할 저장소 공간의 GB 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="19e6d-143">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="19e6d-144">내 요금제로 Office 365 추가 파일 저장소를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="19e6d-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="19e6d-145">Office 365 추가 파일 저장소는 다음 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="19e6d-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="19e6d-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="19e6d-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="19e6d-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="19e6d-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="19e6d-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="19e6d-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="19e6d-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="19e6d-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="19e6d-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="19e6d-151">웹용 Office 계획 SharePoint 있는 경우</span><span class="sxs-lookup"><span data-stu-id="19e6d-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="19e6d-152">웹용 Office 계획 SharePoint 있는 경우</span><span class="sxs-lookup"><span data-stu-id="19e6d-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="19e6d-153">SharePoint Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="19e6d-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="19e6d-154">SharePoint Online 요금제 2</span><span class="sxs-lookup"><span data-stu-id="19e6d-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="19e6d-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="19e6d-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="19e6d-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="19e6d-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="19e6d-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="19e6d-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="19e6d-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="19e6d-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="19e6d-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="19e6d-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="19e6d-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="19e6d-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="19e6d-161">Office 365 Extra File Storage High 및 DOD 계획에 GCC, GCC 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19e6d-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="19e6d-162">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="19e6d-162">Related content</span></span>

<span data-ttu-id="19e6d-163">[사이트 저장 용량 제한](/sharepoint/manage-site-collection-storage-limits) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="19e6d-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="19e6d-164">[사용자에 대한](/onedrive/set-default-storage-space)기본 OneDrive 공간 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="19e6d-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>

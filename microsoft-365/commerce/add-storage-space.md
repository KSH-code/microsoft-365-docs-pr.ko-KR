---
title: 구독에 대한 저장소 공간 추가
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Microsoft 365 구독에서 파일 저장소를 추가하고 줄이는 방법을 학습하세요. 추가 파일 저장소를 사용하면 SharePoint Online 및 OneDrive에 더 많은 콘텐츠를 저장할 수 있습니다.
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405891"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="46d8a-104">구독에 대한 저장소 공간 추가</span><span class="sxs-lookup"><span data-stu-id="46d8a-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="46d8a-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-105">The admin center is changing.</span></span> <span data-ttu-id="46d8a-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46d8a-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="46d8a-107">SharePoint Online 사이트 모음의 저장소 공간이 부족해지면 해당 플랜에 자격이 있는 경우 구독에 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="46d8a-108">사용 가능한 추가 기능 목록에 **Office 365 추가** 파일 저장소가 없는 경우 요금제가 자격이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="46d8a-109">자세한 내용은 내 계획에 [적합한가요?를 참조하세요.](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="46d8a-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="46d8a-110">볼륨 라이선스 또는 CSP를 통해 구독을 구입한 경우 Microsoft에서 직접 조직의 **Office 365 추가** 파일 저장소를 구입할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="46d8a-111">담당자 또는 파트너에게 도움을 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="46d8a-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="46d8a-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="46d8a-112">Before you begin</span></span>

<span data-ttu-id="46d8a-113">이 문서의 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="46d8a-114">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46d8a-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="46d8a-115">사용 가능한 저장소 보기</span><span class="sxs-lookup"><span data-stu-id="46d8a-115">View available storage</span></span>

1. <span data-ttu-id="46d8a-116">SharePoint 관리 센터에서 활성 사이트 페이지로 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">이동한</a> 다음 조직에 [](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) 대한 관리자 권한이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="46d8a-117">페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="46d8a-118">조직에서 Office 365에서 Multi-Geo를 구성한 경우 표시줄에는 모든 지리적 위치에서 사용되는 저장소의 양도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="46d8a-120">사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="46d8a-121">사용하는 저장소의 용량을 확인한 후 구독에 대한 저장소 공간을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="46d8a-122">저장소 공간을 추가하는 데 얼마나 드는 비용은 이 문서의 단계를 따르고, 추가 구입 전에 가격 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="46d8a-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="46d8a-123">사이트 모음 저장 용량 제한을 설정하는 데 대한 자세한 내용은 [Manage site collection storage limits를 참조하십시오.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="46d8a-123">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="46d8a-124">구독에 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="46d8a-124">Add storage to your subscription</span></span>

<span data-ttu-id="46d8a-125">구독에 대한 추가 저장소를 아직 구입하지 않은 경우 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="46d8a-126">관리 센터에서 청구 구매  서비스 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="46d8a-127">서비스 구매 페이지의  아래쪽에 있는  추가 기능 섹션에서 **Office 365 추가** 파일 저장소를 찾고 세부 **정보를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="46d8a-128">제품 세부 정보 페이지에서 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="46d8a-129">필요한 경우 기본 구독을 선택한 다음 추가할 저장소의 기가바이트 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="46d8a-130">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="46d8a-131">어떻게 **표시하나요?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="46d8a-132">주문 **완료 페이지에서** 합계를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="46d8a-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="46d8a-133">변경해야 하는 경우 순서 **편집 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="46d8a-134">주문에 신용 검사가 필요한 경우 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="46d8a-135">완료되면 관리 홈으로  \> **이동 순서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="46d8a-136">저장소 확대 또는 축소</span><span class="sxs-lookup"><span data-stu-id="46d8a-136">Increase or decrease storage</span></span>

<span data-ttu-id="46d8a-137">**Office 365** 추가 파일 저장소 추가 기능을 통해 추가 파일 저장소를 이미 구입한 경우 다음 단계를 사용하여 구독에 대한 추가 저장소 공간을 늘리거나 줄이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="46d8a-138">저장소를 1기가바이트까지 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="46d8a-139">추가 저장소 공간을 모두 제거하려면 고객 [지원에 문의합니다.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="46d8a-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="46d8a-140">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="46d8a-141">제품 **탭에서** **Office 365** 추가 파일 저장소 추가 기능을 포함하는 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="46d8a-142">제품 세부 정보 페이지의 추가 기능 **섹션에서** 추가 기능 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="46d8a-143">추가 기능 관리 **창의** 추가 기능  목록에서 Office **365 추가 파일 저장소 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46d8a-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="46d8a-144">수량 **텍스트 상자에** 구독에 사용할 저장소 공간의 GB 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="46d8a-145">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="46d8a-146">내 요금제로 Office 365 추가 파일 저장소를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="46d8a-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="46d8a-147">Office 365 추가 파일 저장소는 다음 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="46d8a-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="46d8a-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="46d8a-149">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="46d8a-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="46d8a-150">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="46d8a-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="46d8a-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="46d8a-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="46d8a-152">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="46d8a-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="46d8a-153">SharePoint 계획 1을 통해 웹용 Office</span><span class="sxs-lookup"><span data-stu-id="46d8a-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="46d8a-154">SharePoint 계획 2를 통해 웹용 Office</span><span class="sxs-lookup"><span data-stu-id="46d8a-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="46d8a-155">SharePoint Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="46d8a-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="46d8a-156">SharePoint Online 요금제 2</span><span class="sxs-lookup"><span data-stu-id="46d8a-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="46d8a-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="46d8a-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="46d8a-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="46d8a-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="46d8a-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="46d8a-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="46d8a-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="46d8a-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="46d8a-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="46d8a-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="46d8a-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="46d8a-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="46d8a-163">GCC, GCC High 및 DOD 계획에도 Office 365 추가 파일 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d8a-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="46d8a-164">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="46d8a-164">Related content</span></span>

<span data-ttu-id="46d8a-165">[사이트 저장 용량 제한](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="46d8a-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="46d8a-166">[OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)사용자의 기본 저장소 공간 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="46d8a-166">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
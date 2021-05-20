---
title: 구독을 위한 저장 공간 추가
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
description: Microsoft 365 구독에 파일 저장소를 추가합니다. 추가 파일 저장소를 사용하면 SharePoint 온라인 및 OneDrive 더 많은 콘텐츠를 저장할 수 있습니다.
ms.date: 04/02/2021
ms.openlocfilehash: b573205c7053aba0339d1f32deb2996ef80f8754
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572324"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="dedbc-104">구독을 위한 저장 공간 추가</span><span class="sxs-lookup"><span data-stu-id="dedbc-104">Add storage space for your subscription</span></span>

<span data-ttu-id="dedbc-105">SharePoint Online 사이트 모음의 저장소 공간이 부족해지면 해당 플랜에 자격이 있는 경우 구독에 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="dedbc-106">사용 가능한 추가 기능 목록에 **Office 365 Extra File Storage** 표시되지 않으면 계획이 유효하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="dedbc-107">자세한 내용은 [내 계획이 적격합니까?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="dedbc-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="dedbc-108">볼륨 라이선싱 또는 CSP를 통해 구독을 구입한 경우 Microsoft에서 직접 조직에 대한 **Office 365 Extra File Storage** 구입할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="dedbc-109">담당자 또는 파트너에게 문의하여 도움을 요청하십시오.</span><span class="sxs-lookup"><span data-stu-id="dedbc-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dedbc-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="dedbc-110">Before you begin</span></span>

<span data-ttu-id="dedbc-111">이 문서에서 작업을 수행하려면 글로벌 또는 SharePoint 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="dedbc-112">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dedbc-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="dedbc-113">사용 가능한 저장소 보기</span><span class="sxs-lookup"><span data-stu-id="dedbc-113">View available storage</span></span>

1. <span data-ttu-id="dedbc-114">SharePoint 관리 센터에서 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active 사이트</a> 페이지로 이동하여 조직에 대한 관리자 권한이 있는 계정으로 [로그인합니다.](/sharepoint/sharepoint-admin-role)</span><span class="sxs-lookup"><span data-stu-id="dedbc-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="dedbc-115">페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="dedbc-116">조직에서 Office 365 Multi-Geo를 구성한 경우 막대에는 모든 지리적 위치에서 사용되는 저장소 양도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![활성 사이트 페이지의 저장소 표시줄](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="dedbc-118">사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="dedbc-119">사용 중의 저장소 양을 결정한 후 구독에 대한 저장소 공간을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="dedbc-120">저장소 공간을 추가하는 데 드는 비용을 알아보려면 이 문서의 단계를 따르고 더 많이 구입하기 전에 가격 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="dedbc-121">사이트 수집 저장소 제한 설정에 대한 자세한 내용은 [사이트 수집 저장소 관리 제한을](/sharepoint/manage-site-collection-storage-limits)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dedbc-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="dedbc-122">구독에 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="dedbc-122">Add storage to your subscription</span></span>

<span data-ttu-id="dedbc-123">아직 구독에 대한 추가 저장소를 구입하지 않은 경우 그렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="dedbc-124">관리 센터에서 청구 구매  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">서비스</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="dedbc-125">**구매 서비스** 페이지 하단에서 추가 **기능** 섹션에서 **Office 365 Extra File Storage** 찾아 **세부 정보를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="dedbc-126">제품 세부 정보 페이지에서 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="dedbc-127">필요한 경우 기본 구독을 선택한 다음 추가할 기가바이트의 저장소 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="dedbc-128">**지금 체크 아웃을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="dedbc-129">이 **모양은 어떻게 보입니까?** 페이지에서 선택한 기가바이트의 저장소 수를 확인하고 가격 정보를 검토한 다음 **다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="dedbc-130">전체 **주문** 페이지에서 합계를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="dedbc-131">변경해야 하는 경우 순서 **편집을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="dedbc-132">주문에 신용 확인이 필요한 경우 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="dedbc-133">완료되면 관리자 홈으로 **이동하려면 정렬** \> **순서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dedbc-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="dedbc-134">저장소 확대 또는 축소</span><span class="sxs-lookup"><span data-stu-id="dedbc-134">Increase or decrease storage</span></span>

<span data-ttu-id="dedbc-135">**이미 Office 365 Extra File Storage 추가** 기능을 통해 추가 파일 저장소를 구입한 경우 다음 단계를 사용하여 구독의 추가 저장소 공간을 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="dedbc-136">스토리지를 1기가바이트까지 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="dedbc-137">모든 추가 저장 공간을 제거하려면 [지원팀에 문의하십시오.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="dedbc-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="dedbc-138">관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="dedbc-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="dedbc-139">**제품** 탭에서 **Office 365 Extra File Storage** 추가 기능이 포함된 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="dedbc-140">제품 세부 정보 페이지에서 **추가 기능** 섹션에서 **추가 기능 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dedbc-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="dedbc-141">추가 **기능 관리** 창에서 **추가 기능** 목록에서 **Office 365 Extra File Storage** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="dedbc-142">**수량** 텍스트 상자에 구독에 대해 원하는 저장 공간의 GB 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="dedbc-143">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="dedbc-144">내 요금제로 Office 365 추가 파일 저장소를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dedbc-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="dedbc-145">Office 365 추가 파일 저장소는 다음 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="dedbc-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="dedbc-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="dedbc-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="dedbc-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="dedbc-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="dedbc-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="dedbc-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="dedbc-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="dedbc-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="dedbc-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="dedbc-151">SharePoint 플랜 1의 웹용 Office</span><span class="sxs-lookup"><span data-stu-id="dedbc-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="dedbc-152">SharePoint 플랜 2를 가진 웹용 Office</span><span class="sxs-lookup"><span data-stu-id="dedbc-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="dedbc-153">SharePoint Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="dedbc-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="dedbc-154">SharePoint Online 요금제 2</span><span class="sxs-lookup"><span data-stu-id="dedbc-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="dedbc-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="dedbc-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="dedbc-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="dedbc-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="dedbc-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="dedbc-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="dedbc-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="dedbc-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="dedbc-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dedbc-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="dedbc-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="dedbc-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="dedbc-161">Office 365 Extra File Storage GCC, GCC 높음 및 DOD 계획에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedbc-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="dedbc-162">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="dedbc-162">Related content</span></span>

<span data-ttu-id="dedbc-163">[사이트 저장소 제한](/sharepoint/manage-site-collection-storage-limits) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="dedbc-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="dedbc-164">[OneDrive 사용자의 기본 저장소 공간](/onedrive/set-default-storage-space)설정(문서)</span><span class="sxs-lookup"><span data-stu-id="dedbc-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>

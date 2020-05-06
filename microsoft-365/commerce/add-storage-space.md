---
title: 구독에 대 한 저장소 공간 추가
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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEU150
- GEA150
- GSP150
ms.assetid: 96ea3533-de64-4b01-839a-c560875a662c
description: Microsoft 365 구독에서 파일 저장소를 추가 하 고 줄이는 방법에 대해 알아봅니다. 추가 파일 저장소를 사용 하는 경우 SharePoint Online 및 OneDrive에 더 많은 콘텐츠를 저장할 수 있습니다.
ms.openlocfilehash: a944c272f456fd6f284e1df28c52420e4deb40d4
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045943"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="59759-104">구독에 대 한 저장소 공간 추가</span><span class="sxs-lookup"><span data-stu-id="59759-104">Add storage space for your subscription</span></span>

<span data-ttu-id="59759-105">SharePoint Online 사이트 모음의 저장소 공간이 부족해지면 해당 플랜에 자격이 있는 경우 구독에 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="59759-106">사용 가능한 추가 기능 목록에 **Office 365 추가 파일 저장소가** 표시 되지 않으면 계획이 적합 하지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="59759-107">자세한 내용은 [내 요금제를 참조 하세요](#is-my-plan-eligible-for-office-365-extra-file-storage) .</span><span class="sxs-lookup"><span data-stu-id="59759-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="59759-108">사용 가능한 저장소 보기</span><span class="sxs-lookup"><span data-stu-id="59759-108">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59759-109">[새 SharePoint 관리 센터의 활성 사이트 페이지](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true)로 이동하여 조직에 대한 [관리자 권한](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-109">Go to the [Active sites page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true), and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="59759-110">페이지 오른쪽 위에서 모든 사이트에서 사용 되는 저장소의 크기와 구독의 총 저장소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-110">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="59759-111">(조직이 Office 365에서 다중 Geo를 구성한 경우에도 막대에는 모든 지리적 위치에서 사용 된 저장소의 양이 표시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="59759-111">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59759-112">https://portal.office.de 전역 또는 SharePoint 관리자 권한으로 로그인 한 다음 관리 타일을 선택 하 여 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="59759-112">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="59759-113">(페이지에 액세스할 수 있는 권한이 없다는 메시지가 표시 되는 경우 조직에 Microsoft 365 관리자 권한이 없는 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="59759-113">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="59759-114">왼쪽 창의 **관리 센터**에서 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-114">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="59759-115">기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기**를 선택하여 새 SharePoint 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="59759-115">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="59759-116">새 SharePoint 관리 센터의 왼쪽 창에서 **활성 사이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-116">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="59759-117">페이지 오른쪽 위에서 모든 사이트에서 사용 되는 저장소의 크기와 구독의 총 저장소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59759-118">https://login.partner.microsoftonline.cn/ 전역 또는 SharePoint 관리자 권한으로 로그인 한 다음 관리 타일을 선택 하 여 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="59759-118">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="59759-119">(페이지에 액세스할 수 있는 권한이 없다는 메시지가 표시 되는 경우 조직에 Microsoft 365 관리자 권한이 없는 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="59759-119">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="59759-120">왼쪽 창의 **관리 센터**에서 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-120">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="59759-121">기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기**를 선택하여 새 SharePoint 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="59759-121">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="59759-122">새 SharePoint 관리 센터의 왼쪽 창에서 **활성 사이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-122">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="59759-123">페이지 오른쪽 위에서 모든 사이트에서 사용 되는 저장소의 크기와 구독의 총 저장소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-123">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end

![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="59759-125">사용 된 저장소에 지난 24-48 시간 동안의 변경 내용은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-125">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="59759-126">사용 중인 저장소의 용량을 확인한 후에는 구독에 대해 저장소 공간을 추가 또는 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-126">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="59759-127">저장소 공간을 추가 하는 데 드는 비용을 확인 하려면이 문서에 나와 있는 단계를 수행 하 고 구입 하기 전에 가격 산정 정보를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="59759-127">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="59759-128">사이트 모음 저장 용량 제한을 설정 하는 방법에 대 한 자세한 내용은 [사이트 모음 저장 용량 제한 관리](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59759-128">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="59759-129">구독에 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="59759-129">Add storage to your subscription</span></span>

<span data-ttu-id="59759-130">구독에 대 한 추가 저장소를 아직 구입 하지 않은 경우이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-130">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59759-131">관리 센터에서 **결제** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">구매 서비스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="59759-132">**서비스 구매** 페이지 아래쪽에서 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-132">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="59759-133">**Office 365 추가 파일 저장소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-133">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="59759-134">표시 되는 경우 **Office 365 추가 파일 저장소** 페이지에서 기본 구독을 선택한 다음 추가할 저장소의 기가바이트 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-134">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="59759-135">**지금 체크 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-135">Select **Check out now**.</span></span>

6. <span data-ttu-id="59759-136">표시 **방법** 페이지에서 선택한 저장소의 기가바이트 수를 확인 하 고 가격 정보를 검토 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-136">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="59759-137">**전체 순서** 페이지에서 합계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-137">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="59759-138">변경 작업을 수행 해야 하는 경우에는 **순서 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-138">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="59759-139">주문에 신용 검사가 필요한 경우 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-139">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="59759-140">작업이 완료 되 면 " **주문** \> " **을 선택 하 고 관리 홈으로 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-140">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59759-141">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동 합니다.  </span><span class="sxs-lookup"><span data-stu-id="59759-141">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="59759-142">**구독** 페이지에서 저장소 공간을 추가 하려는 구독을 선택 하 고 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-142">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="59759-144">**추가 기능이**표시 되지 않는 경우 파트너를 통해 구독을 구매한 경우 **볼륨 라이선스 서비스 센터 (VLSC)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-144">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="59759-145">**추가 기능 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-145">Select **Buy add-ons**.</span></span>

    ![관리 센터의 구독 페이지에서 추가 기능 구입 링크를 사용 하세요.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="59759-147">**서비스 구매** 페이지에서 **Office 365 추가 파일 저장소**를 마우스로 가리키거나 탭 한 다음 **지금 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-147">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="59759-148">필요한 사용자 라이선스 수를 입력 하 고 표시 되는 경우 기본 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-148">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="59759-149">**지금 체크 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-149">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="59759-150">표시 **방법** 페이지에서 선택한 저장소의 기가바이트 수를 확인 하 고 가격 정보를 검토 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-150">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="59759-151">**전체 순서** 페이지에서 **주문을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-151">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59759-152">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-152">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="59759-153">**구독** 페이지에서 저장소 공간을 추가 하려는 구독을 선택 하 고 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="59759-155">**추가 기능이**표시 되지 않는 경우 파트너를 통해 구독을 구매한 경우 **볼륨 라이선스 서비스 센터 (VLSC)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="59759-156">**추가 기능 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-156">Select **Buy add-ons**.</span></span>

    ![관리 센터의 구독 페이지에서 추가 기능 구입 링크를 사용 하세요.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="59759-158">**서비스 구매** 페이지에서 **Office 365 추가 파일 저장소**를 마우스로 가리키거나 탭 한 다음 **지금 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="59759-159">필요한 사용자 라이선스 수를 입력 하 고 표시 되는 경우 기본 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="59759-160">**지금 체크 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="59759-161">표시 **방법** 페이지에서 선택한 저장소의 기가바이트 수를 확인 하 고 가격 정보를 검토 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="59759-162">**전체 순서** 페이지에서 **주문을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="59759-163">저장소 확대 또는 축소</span><span class="sxs-lookup"><span data-stu-id="59759-163">Increase or decrease storage</span></span>

<span data-ttu-id="59759-164">**Office 365 추가 파일 저장소** 추가 기능을 통해 추가 파일 저장소를 이미 구매한 경우 이러한 단계를 사용 하 여 구독에 대 한 추가 저장소 공간을 늘리거나 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-164">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="59759-165">저장소 용량을 1gb로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-165">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="59759-166">추가 저장 공간을 모두 제거 하려면 [지원 서비스에 문의](../admin/contact-support-for-business-products.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-166">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59759-167">관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> **청구** \> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-167">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="59759-168">**Office 365 기타 파일 저장소** 추가 기능을 포함 하는 구독을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-168">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="59759-169">**추가 기능**을 선택한 다음 **수량 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-169">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="59759-170">**기가바이트 추가/제거** 창에서 구독에 대해 원하는 총 기가바이트를 입력 한 다음 **변경 내용 제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-170">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59759-171">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-171">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="59759-172">**구독** 페이지에서 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-172">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="59759-174">**추가 기능이**표시 되지 않는 경우 파트너를 통해 구독을 구매한 경우 **볼륨 라이선스 서비스 센터 (VLSC)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-174">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="59759-175">**Office 365 추가 파일 저장소**에서 **수량 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-175">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![수량 변경 링크](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="59759-177">오른쪽 창에서 필요한 총 기가바이트 수를 입력 한 다음 **제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-177">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="59759-178">예를 들어, 현재 추가 파일 저장소가 200기가바이트인데 100기가바이트만 필요한 경우 이 상자에 **100**을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-178">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="59759-179">**닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-179">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59759-180">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-180">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="59759-181">**구독** 페이지에서 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-181">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="59759-183">**추가 기능이**표시 되지 않는 경우 파트너를 통해 구독을 구매한 경우 **볼륨 라이선스 서비스 센터 (VLSC)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-183">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="59759-184">**Office 365 추가 파일 저장소**에서 **수량 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-184">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![수량 변경 링크](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="59759-186">오른쪽 창에서 필요한 총 기가바이트 수를 입력 한 다음 **제출을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-186">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="59759-187">예를 들어, 현재 추가 파일 저장소가 200기가바이트인데 100기가바이트만 필요한 경우 이 상자에 **100**을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-187">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="59759-188">**닫기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59759-188">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="59759-189">내 요금제로 Office 365 추가 파일 저장소를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="59759-189">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="59759-190">Office 365 추가 파일 저장소는 다음 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-190">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="59759-191">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="59759-191">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="59759-192">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="59759-192">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="59759-193">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="59759-193">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="59759-194">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="59759-194">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="59759-195">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="59759-195">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="59759-196">SharePoint 계획 1을 사용 하는 웹의 Office</span><span class="sxs-lookup"><span data-stu-id="59759-196">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="59759-197">SharePoint 계획 2를 사용 하는 웹의 Office</span><span class="sxs-lookup"><span data-stu-id="59759-197">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="59759-198">SharePoint Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="59759-198">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="59759-199">SharePoint Online 요금제 2</span><span class="sxs-lookup"><span data-stu-id="59759-199">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="59759-200">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="59759-200">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="59759-201">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="59759-201">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="59759-202">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="59759-202">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="59759-203">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="59759-203">Microsoft 365 E3</span></span>

- <span data-ttu-id="59759-204">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="59759-204">Microsoft 365 E5</span></span>

- <span data-ttu-id="59759-205">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="59759-205">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="59759-206">Office 365 GCC, GCC High 및 DOD 계획에도 추가 파일 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59759-206">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

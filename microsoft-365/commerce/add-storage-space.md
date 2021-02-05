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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 365 구독에서 파일 저장소를 추가하고 줄이는 방법을 학습합니다. 추가 파일 저장소를 사용하면 SharePoint Online 및 OneDrive에 더 많은 콘텐츠를 저장할 수 있습니다.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114910"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="69b75-104">구독에 대한 저장소 공간 추가</span><span class="sxs-lookup"><span data-stu-id="69b75-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="69b75-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-105">The admin center is changing.</span></span> <span data-ttu-id="69b75-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69b75-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="69b75-107">SharePoint Online 사이트 모음의 저장소 공간이 부족해지면 해당 플랜에 자격이 있는 경우 구독에 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="69b75-108">사용 가능한 추가 기능 목록에 **Office 365 추가** 파일 저장소가 없는 경우 요금제가 자격이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="69b75-109">자세한 내용은 내 계획이 [적합한지 여부](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="69b75-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="69b75-110">볼륨 라이선스 또는 CSP를 통해 구독을 구입한 경우 Microsoft에서 직접 조직의 **Office 365 추가** 파일 저장소를 구입할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="69b75-111">담당자나 파트너에게 도움을 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="69b75-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="69b75-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="69b75-112">Before you begin</span></span>

<span data-ttu-id="69b75-113">이 문서의 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="69b75-114">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69b75-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="69b75-115">사용 가능한 저장소 보기</span><span class="sxs-lookup"><span data-stu-id="69b75-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="69b75-116">SharePoint 관리 센터에서 활성 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> 사이트 페이지로 이동한 다음 조직에 [](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) 대한 관리자 권한이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="69b75-117">페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="69b75-118">조직에서 Office 365에서 Multi-Geo를 구성한 경우 표시줄에는 모든 지리적 위치에서 사용되는 저장소의 양도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="69b75-120">사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="69b75-121">전역 또는 SharePoint 관리자로 로그인한 다음 관리 타일을 선택하여 관리 https://portal.office.de 센터를 하세요.</span><span class="sxs-lookup"><span data-stu-id="69b75-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="69b75-122">페이지에 액세스할 수 있는 권한이 없는 메시지가 표시면 조직에 Microsoft 365 관리자 권한이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="69b75-123">왼쪽 창의 관리 센터에서 **SharePoint를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="69b75-124">기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기** 를 선택하여 새 SharePoint 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="69b75-125">새 SharePoint 관리 센터의 왼쪽 창에서 **활성 사이트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="69b75-126">페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="69b75-128">사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="69b75-129">전역 또는 SharePoint 관리자로 로그인한 다음 관리 타일을 선택하여 관리 https://login.partner.microsoftonline.cn/ 센터를 하세요.</span><span class="sxs-lookup"><span data-stu-id="69b75-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="69b75-130">페이지에 액세스할 수 있는 권한이 없는 메시지가 표시된 경우 조직에 Microsoft 365 관리자 권한이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="69b75-131">왼쪽 창의 관리 센터에서 **SharePoint를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="69b75-132">기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기** 를 선택하여 새 SharePoint 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="69b75-133">새 SharePoint 관리 센터의 왼쪽 창에서 **활성 사이트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="69b75-134">페이지의 오른쪽 위에서 모든 사이트에서 사용된 저장소의 크기와 구독에 대한 총 저장소 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![활성 사이트 페이지의 저장소 표시줄](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="69b75-136">사용된 저장소에는 최근 24-48시간 내에 변경한 내용이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="69b75-137">사용 중인 저장소의 용량을 확인한 후에는 구독에 대해 저장소 공간을 추가 또는 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="69b75-138">저장소 공간을 추가하는 데 드는 비용에 대해 자세한 내용은 이 문서의 단계를 따르고 구매하기 전에 가격 정보를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="69b75-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="69b75-139">사이트 모음 저장 용량 제한 설정에 대한 자세한 내용은 사이트 모음 저장 용량 제한 [관리를 참조하십시오.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="69b75-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="69b75-140">구독에 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="69b75-140">Add storage to your subscription</span></span>

<span data-ttu-id="69b75-141">구독에 대한 추가 저장소를 아직 구매하지 않은 경우 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="69b75-142">관리 센터에서 대금  청구 서비스 페이지로 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank"></a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="69b75-143">서비스 구매 페이지의 맨 **아래에서** 추가 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="69b75-144">**Office 365 추가 파일 저장소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="69b75-145">Office **365 추가** 파일 저장소 페이지에 표시되는 경우 기본 구독을 선택한 다음 추가할 저장소의 기가바이트 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="69b75-146">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="69b75-147">어떻게 **표시합니까?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="69b75-148">주문 **완료 페이지에서** 합계를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="69b75-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="69b75-149">변경해야 하는 경우 순서 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="69b75-150">주문에 신용 검사가 필요한 경우 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="69b75-151">완료되면 관리 홈으로 이동  \> **순서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="69b75-152">관리 센터에서 청구 구독  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">페이지로</a> 이동합니다.  </span><span class="sxs-lookup"><span data-stu-id="69b75-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="69b75-153">구독 **페이지에서** 저장소 공간을 추가할 구독을 선택한 다음 추가 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="69b75-155">추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="69b75-156">추가 **기능 구입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-156">Select **Buy add-ons**.</span></span>

    ![관리 센터의 구독 페이지에서 추가 기능 링크를 구입합니다.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="69b75-158">서비스 **구매 페이지에서** **Office 365** 추가 파일 저장소를 마우스로 마우스로 클릭하거나 탭한 다음 지금 **구입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="69b75-159">필요한 사용자 라이선스 수를 입력하고 표시되는 경우 기본 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="69b75-160">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="69b75-161">어떻게 **표시합니까?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="69b75-162">주문 **완료 페이지에서** **주문을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="69b75-163">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="69b75-164">구독 **페이지에서** 저장소 공간을 추가할 구독을 선택한 다음 추가 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="69b75-166">추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="69b75-167">추가 **기능 구입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-167">Select **Buy add-ons**.</span></span>

    ![관리 센터의 구독 페이지에서 추가 기능 링크를 구입합니다.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="69b75-169">서비스 **구매 페이지에서** **Office 365** 추가 파일 저장소를 마우스로 마우스로 클릭하거나 탭한 다음 지금 **구입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="69b75-170">필요한 사용자 라이선스 수를 입력하고 표시되는 경우 기본 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="69b75-171">지금 **체크 아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="69b75-172">어떻게 **표시합니까?** 페이지에서 선택한 저장소의 기가바이트 수를 확인하고 가격 정보를 검토한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="69b75-173">주문 **완료 페이지에서** **주문을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="69b75-174">저장소 확대 또는 축소</span><span class="sxs-lookup"><span data-stu-id="69b75-174">Increase or decrease storage</span></span>

<span data-ttu-id="69b75-175">**Office 365** 추가 파일 저장소 추가 기능을 통해 추가 파일 저장소를 이미 구입한 경우 다음 단계를 사용하여 구독에 대한 추가 저장소 공간을 늘리거나 줄이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="69b75-176">저장소를 1기가바이트까지 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="69b75-177">추가 저장소 공간을 모두 제거하려면 고객 [지원에 문의합니다.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="69b75-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="69b75-178">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="69b75-179">제품 **탭에서** **Office 365** 추가 파일 저장소 추가 기능을 포함하는 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="69b75-180">제품 세부 정보 페이지의 추가  기능 섹션에서 추가 기능 관리 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="69b75-181">추가 기능 관리 **창의** 추가 기능  목록에서 Office **365 추가 파일 저장소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="69b75-182">수량 **입력란에** 구독에 사용할 저장소 공간의 GB 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="69b75-183">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="69b75-184">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="69b75-185">구독 **페이지에서** 추가 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="69b75-187">추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="69b75-188">**Office 365 추가 파일 저장소에서** 수량 **변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![수량 변경 링크](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="69b75-190">오른쪽 창에 필요한 총 기가바이트 수를 입력한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="69b75-191">예를 들어, 현재 추가 파일 저장소가 200기가바이트인데 100기가바이트만 필요한 경우 이 상자에 **100** 을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="69b75-192">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="69b75-193">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="69b75-194">구독 **페이지에서** 추가 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="69b75-196">추가 기능을 볼 수 없는 경우 파트너를 통해 구독을 구매한 경우 **VLSC(볼륨** 라이선스 서비스 센터)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="69b75-197">**Office 365 추가 파일 저장소에서** 수량 **변경을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![수량 변경 링크](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="69b75-199">오른쪽 창에 필요한 총 기가바이트 수를 입력한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="69b75-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="69b75-200">예를 들어, 현재 추가 파일 저장소가 200기가바이트인데 100기가바이트만 필요한 경우 이 상자에 **100** 을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="69b75-201">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="69b75-202">내 요금제로 Office 365 추가 파일 저장소를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="69b75-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="69b75-203">Office 365 추가 파일 저장소는 다음 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="69b75-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="69b75-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="69b75-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="69b75-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="69b75-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="69b75-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="69b75-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="69b75-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="69b75-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="69b75-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="69b75-209">SharePoint 계획 1을 통해 웹용 Office</span><span class="sxs-lookup"><span data-stu-id="69b75-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="69b75-210">SharePoint 요금제 2를 통해 웹용 Office</span><span class="sxs-lookup"><span data-stu-id="69b75-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="69b75-211">SharePoint Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="69b75-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="69b75-212">SharePoint Online 요금제 2</span><span class="sxs-lookup"><span data-stu-id="69b75-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="69b75-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="69b75-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="69b75-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="69b75-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="69b75-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="69b75-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="69b75-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="69b75-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="69b75-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="69b75-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="69b75-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="69b75-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="69b75-219">GCC, GCC High 및 DOD 계획에도 Office 365 추가 파일 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69b75-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="69b75-220">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="69b75-220">Related content</span></span>

<span data-ttu-id="69b75-221">[사이트 저장 용량 제한](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="69b75-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="69b75-222">[OneDrive 사용자에](https://docs.microsoft.com/onedrive/set-default-storage-space)대한 기본 저장소 공간 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="69b75-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>

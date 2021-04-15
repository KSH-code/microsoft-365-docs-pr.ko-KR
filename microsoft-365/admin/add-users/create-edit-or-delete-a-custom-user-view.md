---
title: 사용자 지정 사용자 보기 만들기, 편집 또는 삭제
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: 필터를 사용하여 Microsoft 365에서 사용자 지정 사용자 보기를 만들거나 편집하거나 삭제하는 방법을 학습합니다.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759933"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="79da5-103">사용자 지정 사용자 보기 만들기, 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="79da5-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="79da5-104">비즈니스용 Microsoft 365 구독의 전역 관리자 또는 사용자 관리 관리자인 경우 사용자 지정 사용자 보기를 만들어 특정 사용자 하위 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="79da5-105">이러한 보기는 표준 보기 집합에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="79da5-106">사용자 지정 사용자 보기를 만들거나 편집하거나 삭제할 수 있으며, 만든 사용자 지정 보기는 모든 관리자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="79da5-107">관리 센터의 사용자 지정 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="79da5-107">Custom user views in the admin center</span></span>

<span data-ttu-id="79da5-108">사용자 지정 사용자 보기를 만들거나 편집하거나 삭제하면 변경  내용이 회사 내 모든 관리자가 사용자 페이지로 이동하면 표시되는 필터 목록에 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="79da5-109">최대 50개 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="79da5-110">표준 사용자 보기는 필터  드롭다운 목록에 기본적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="79da5-111">표준 필터에는 모든 **사용자,** 라이선스가 있는 **사용자,** **게스트** **사용자,** 로그인 **허용,** 로그인 **차단,** 허가되지 않은 **사용자,** 오류가 있는 사용자, **대금** 청구 관리자, 전역 **관리자,** **헬프데스크** **관리자,** 서비스 관리자 및 사용자 관리 관리자가 **포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="79da5-112">표준 보기는 편집하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="79da5-113">표준 보기에 대해 주의해야 할 몇 가지 사항:</span><span class="sxs-lookup"><span data-stu-id="79da5-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="79da5-114">목록에 사용자가 2,000명 이상인 경우 일부 표준 보기에는 목록의 목록이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-114">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="79da5-115">이 목록에서 특정 사용자를 찾으면 검색 상자를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="79da5-115">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="79da5-116">Microsoft에서 Microsoft 365를 구매하지 않은 경우 **청구** 관리자는 표준 보기 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="79da5-117">자세한 내용은 [관리 역할 지정](assign-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79da5-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="79da5-118">사용자 지정 사용자 보기에 대한 필터 선택</span><span class="sxs-lookup"><span data-stu-id="79da5-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="79da5-119">사용자 지정 필터 창에서 사용자 지정 보기를 만들고 **편집할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="79da5-120">여러 필터 옵션을 선택하면 선택한 모든 조건과 일치하는 사용자가 포함된 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="79da5-121">다음 예제에서는 캐나다에 있는 특정 도메인의 모든 사용자를 표시하는 "Canadian users"라는 사용자 지정 보기를 만드는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="79da5-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="79da5-122">**A - 도메인** 조직에 여러 도메인이 있는 경우 사용 가능한 도메인의 드롭다운 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="79da5-123">**B - 로그인 상태** 허용되거나 차단되는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="79da5-124">**C - 위치** 국가 드롭다운 목록에서 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="79da5-125">**D - 할당된 제품 라이선스** 조직에서 사용할 수 있는 라이선스의 드롭다운 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="79da5-126">이 필터를 사용하여 선택한 라이선스가 있는 사용자를 사용자에게 보여 주면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="79da5-127">사용자에게 추가 라이선스가 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="79da5-128">부서, 구 또는 시,도, 국가 또는 지역 또는 직위와 같이 조직에서 사용되는 추가 사용자 프로필 세부 정보를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="79da5-129">**기타 조건:**</span><span class="sxs-lookup"><span data-stu-id="79da5-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="79da5-130">**동기화된 사용자만** 사용자가 활성화되어 있는지 여부에 관계없이 로컬 Active Directory와 동기화된 모든 사용자를 표시하려면 이 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="79da5-131">**오류가 있는 사용자** 프로비전 오류가 있을 수 있는 사용자를 표시하려면 이 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="79da5-132">**라이선스가 없는 사용자** 라이선스가 할당되지 않은 모든 사용자를 찾으하려면 이 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-132">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="79da5-133">이 보기의 결과에는 Exchange 사서함이 있지만 라이선스가 없는 사용자도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-133">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="79da5-134">이러한 사용자를 구체적으로 추적하기 위해 Exchange 사서함 또는 보관 사서함이 있는 라이선스가 없는 사용자 **필터를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-134">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="79da5-135">이 보기의 결과에는 Exchange 보관함이 있지만 라이선스가 없는 사용자도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-135">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="79da5-136">Exchange 사서함 또는 보관 사서함이 있는 **라이선스가 없는 사용자** Exchange Online에서 만들어지며 Exchange 사서함이 있지만 Microsoft 365 라이선스가 할당되지 않은 사용자 계정을 표시하려면 이 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="79da5-137">이 필터의 결과에는 Exchange 보관함이 있는 사용자나 Exchange 보관함이 할당된 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="79da5-138">**Exchange 사서함이** 있는 라이선스가 없는 사용자는 다음 경우 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="79da5-139">사서함이 최근에 공유에서  사용자로  변환된 경우 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="79da5-140">사서함이 최근에 Microsoft 365로 마이그레이션 했지만 라이선스가 할당되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="79da5-141">사서함이 PowerShell을 사용하여 만들어지며 라이선스가 할당되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="79da5-142">사용자에 대해 cmdlet을 New-RemoteMailbox 새 사서함이 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="79da5-143">2,000명 이상의 사용자를 반환하는 사용자 지정 보기를 만드는 경우 결과 사용자 목록이 정렬되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="79da5-144">이 경우 검색 상자를 사용하여 사용자를 찾거나 사용자 지정 보기를 편집하여 검색을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="79da5-145">사용자 지정 사용자 보기 만들기</span><span class="sxs-lookup"><span data-stu-id="79da5-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79da5-146">관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">사용자로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79da5-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="79da5-147">활성 **사용자 페이지에서** 필터를 **선택하고** 새 필터 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="79da5-148">사용자 **지정 필터 페이지에서** 필터의 이름을 입력하고 사용자 지정 필터에 대한 조건을 선택한 다음 추가 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="79da5-149">이제 사용자 지정 보기가 필터 드롭다운 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79da5-150">관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">사용자로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79da5-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="79da5-151">활성 **사용자 페이지에서** 보기를 **선택하고** 사용자 지정 보기 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="79da5-152">사용자 **지정 보기 페이지에서** 필터의 이름을 입력하고 사용자 지정 필터에 대한 조건을 선택한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="79da5-153">이제 사용자 지정 보기가 필터 드롭다운 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="79da5-154">관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">사용자로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79da5-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="79da5-155">활성 **사용자 페이지에서** 보기를 **선택하고** 사용자 지정 보기 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="79da5-156">사용자 **지정 보기 페이지에서** 필터의 이름을 입력하고 사용자 지정 필터에 대한 조건을 선택한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="79da5-157">이제 사용자 지정 보기가 필터 드롭다운 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="79da5-158">사용자 지정 사용자 보기 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="79da5-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79da5-159">관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">사용자로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79da5-159">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="79da5-160">활성 **사용자 페이지에서** **필터를** 선택하고 변경할 필터를 선택한 다음 필터 **편집 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="79da5-161">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="79da5-162">사용자 **지정 필터 페이지에서** 필요한 정보를 편집한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="79da5-163">또는 필터를 삭제하려면 페이지 아래쪽에서 삭제를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79da5-164">관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">사용자로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79da5-164">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="79da5-165">활성 **사용자 페이지에서** 보기 **를** 선택하고 변경할 필터를 선택한 다음 이 보기 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="79da5-166">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="79da5-167">사용자 **지정 보기 페이지에서** 필요한 정보를 편집한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="79da5-168">또는 필터를 삭제하려면 페이지 아래쪽에서 사용자 지정 보기 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79da5-169">관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">사용자로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79da5-169">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="79da5-170">활성 **사용자 페이지에서** 보기 **를** 선택하고 변경할 필터를 선택한 다음 이 보기 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="79da5-171">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79da5-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="79da5-172">사용자 **지정 보기 페이지에서** 필요한 정보를 편집한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="79da5-173">또는 필터를 삭제하려면 페이지 아래쪽에서 사용자 지정 보기 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79da5-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     
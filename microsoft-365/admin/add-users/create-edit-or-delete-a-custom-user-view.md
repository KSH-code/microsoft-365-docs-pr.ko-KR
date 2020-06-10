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
description: 필터를 사용 하 여 Microsoft 365에서 사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하는 방법을 알아봅니다.
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664577"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="b0236-103">사용자 지정 사용자 보기 만들기, 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="b0236-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="b0236-104">Microsoft 365 비즈니스 에디션 구독의 전역 또는 사용자 관리 관리자 인 경우 사용자 지정 사용자 보기를 만들어 특정 사용자 하위 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="b0236-105">이러한 보기는 표준 보기 집합에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="b0236-106">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제할 수 있으며, 만든 사용자 지정 보기는 모든 관리자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="b0236-107">관리 센터의 사용자 지정 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="b0236-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="b0236-108">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하면 변경 내용이 회사의 모든 관리자 **가 사용자** 페이지로 이동할 때 표시 되는 **필터** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="b0236-109">최대 50 개의 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="b0236-110">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하면 변경 내용이 회사의 모든 관리자 **가 사용자** 페이지로 이동할 때 표시 되는 **보기** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="b0236-111">최대 50 개의 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="b0236-112">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하면 변경 내용이 회사의 모든 관리자 **가 사용자** 페이지로 이동할 때 표시 되는 **보기** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="b0236-113">최대 50 개의 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="b0236-114">표준 사용자 보기는 기본적으로 **필터** 드롭다운 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="b0236-115">표준 필터에는 **모든 사용자**, **허가 된 사용자**, **게스트 사용자**, **로그인 허용**, **로그인 차단 됨**, **허가**되지 않은 사용자, **오류**, **청구 관리자**, **전역 관리자**, **헬프데스크 관리자**, **서비스 관리자**및 **사용자 관리 관리자**가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="b0236-116">표준 보기는 편집 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="b0236-117">표준 보기에 대해 주의 해야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="b0236-118">일부 표준 보기에는 목록에 사용자가 2000 명 이상인 경우 정렬 되지 않은 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-118">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="b0236-119">이 목록에서 특정 사용자를 찾으려면 검색 상자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-119">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="b0236-120">Microsoft에서 microsoft 365을 구입 하지 않은 경우 **청구 관리자** 는 표준 보기 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="b0236-121">자세한 내용은 [관리 역할 지정](assign-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0236-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="b0236-122">사용자 지정 사용자 보기에 대 한 필터 선택</span><span class="sxs-lookup"><span data-stu-id="b0236-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="b0236-123">**사용자 지정 필터** 창에서 사용자 지정 보기를 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="b0236-124">필터 옵션을 여러 개 선택 하는 경우 선택한 모든 조건과 일치 하는 사용자가 포함 된 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="b0236-125">다음은 캐나다에 거주 하는 특정 도메인의 모든 사용자를 표시 하는 "캐나다 사용자" 라는 사용자 지정 보기를 만드는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="b0236-126">**A-도메인** 조직에 대해 여러 도메인을 사용 하는 경우 사용할 수 있는 도메인의 드롭다운 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="b0236-127">**B-로그인 상태** 허용 또는 차단 되는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="b0236-128">**C-위치** 국가 드롭다운 목록에서 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="b0236-129">**D-할당 된 제품 라이선스** 조직에서 사용할 수 있는 라이선스의 드롭다운 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="b0236-130">이 필터를 사용 하 여 선택한 라이선스가 할당 된 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="b0236-131">사용자에 게 추가 라이선스가 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="b0236-132">부서, 구/군/시, 시/도, 국가 또는 지역, 직책 등 조직에서 사용 되는 추가 사용자 프로필 정보를 기준으로 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="b0236-133">**기타 조건:**</span><span class="sxs-lookup"><span data-stu-id="b0236-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="b0236-134">**사용자만 동기화** 사용자의 정품 인증 여부에 관계 없이 로컬 Active Directory와 동기화 된 모든 사용자를 표시 하려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="b0236-135">**오류가 있는 사용자** 프로 비전 오류가 발생할 수 있는 사용자를 표시 하려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="b0236-136">**라이선스가 없는 사용자** 라이선스가 할당 되지 않은 모든 사용자를 찾으려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-136">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="b0236-137">이 보기의 결과에는 Exchange 사서함이 있지만 라이선스가 없는 사용자도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-137">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="b0236-138">해당 사용자를 추적 하려면 **Exchange 사서함 이나 보관 함과 함께**사용 되지 않는 필터 사용자로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-138">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="b0236-139">이 보기의 결과에는 Exchange 보관 함이 있지만 라이선스가 없는 사용자도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-139">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="b0236-140">**Exchange 사서함 또는 보관 함이 있는 허가** 되지 않은 사용자 Exchange Online에서 만들어졌으며 Exchange 사서함이 있지만 Microsoft 365 라이선스가 할당 되지 않은 사용자 계정을 표시 하려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="b0236-141">이 필터의 결과에는 Exchange 보관 사서함이 있거나 할당 된 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="b0236-142">**Exchange 사서함이 있는 허가** 되지 않은 사용자 필터는 다음과 같은 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="b0236-143">최근에 사서함이 **공유** 에서 **사용자** 로 변환 되었으며 라이선스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="b0236-144">최근에 Microsoft 365로 사서함이 마이그레이션 되었지만 라이선스가 할당 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="b0236-145">PowerShell을 사용 하 여 사서함을 만들었으며 라이선스가 할당 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="b0236-146">New-remotemailbox cmdlet을 사용 하 여 온-프레미스로 만든 새 사서함이 사용자에 대해 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="b0236-147">2000 명 이상의 사용자를 반환 하는 사용자 지정 보기를 만드는 경우 결과 사용자 목록이 정렬 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="b0236-148">이 경우 검색 상자를 사용 하 여 사용자를 찾거나 사용자 지정 보기를 편집 하 여 검색 내용을 구체화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="b0236-149">사용자 지정 사용자 보기 만들기</span><span class="sxs-lookup"><span data-stu-id="b0236-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b0236-150">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a>로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="b0236-151">**활성 사용자** 페이지에서 **필터** 를 선택 하 고 **새 필터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="b0236-152">**사용자 지정 필터** 페이지에서 필터의 이름을 입력 하 고 사용자 지정 필터의 조건을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="b0236-153">이제 사용자 지정 보기가 필터의 드롭다운 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b0236-154">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a>로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="b0236-155">**활성 사용자** 페이지에서 **보기** 를 선택 하 고 **사용자 지정 보기 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="b0236-156">**사용자 지정 보기** 페이지에서 필터의 이름을 입력 하 고 사용자 지정 필터의 조건을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="b0236-157">이제 사용자 지정 보기가 필터의 드롭다운 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="b0236-158">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a>로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-158">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="b0236-159">**활성 사용자** 페이지에서 **보기** 를 선택 하 고 **사용자 지정 보기 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="b0236-160">**사용자 지정 보기** 페이지에서 필터의 이름을 입력 하 고 사용자 지정 필터의 조건을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="b0236-161">이제 사용자 지정 보기가 필터의 드롭다운 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="b0236-162">사용자 지정 사용자 보기 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="b0236-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b0236-163">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a>로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-163">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="b0236-164">**활성 사용자** 페이지에서 **필터**를 선택 하 고 변경 하려는 필터를 선택한 다음 **필터 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b0236-165">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="b0236-166">**사용자 지정 필터** 페이지에서 필요에 따라 정보를 편집한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="b0236-167">또는 필터를 삭제 하려면 페이지 아래쪽에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b0236-168">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a>로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-168">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="b0236-169">**활성 사용자** 페이지에서 **보기**를 선택 하 고 변경 하려는 필터를 선택한 다음 **이 보기 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b0236-170">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="b0236-171">**사용자 지정 보기** 페이지에서 필요에 따라 정보를 편집 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="b0236-172">또는 필터를 삭제 하려면 페이지 아래쪽에서 **사용자 지정 보기 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b0236-173">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a>로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-173">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="b0236-174">**활성 사용자** 페이지에서 **보기**를 선택 하 고 변경 하려는 필터를 선택한 다음 **이 보기 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b0236-175">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="b0236-176">**사용자 지정 보기** 페이지에서 필요에 따라 정보를 편집 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="b0236-177">또는 필터를 삭제 하려면 페이지 아래쪽에서 **사용자 지정 보기 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0236-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     
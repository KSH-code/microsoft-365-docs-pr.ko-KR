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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: 필터를 사용 하 여 Microsoft 365에서 사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하는 방법을 알아봅니다.
ms.openlocfilehash: 94a9ad7de8bc8e0692d97fda56200cf668b1e5f8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617263"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="477ab-103">Office 365에서 사용자 지정 사용자 보기 만들기, 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="477ab-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="477ab-104">Office 365의 전역 또는 사용자 관리 관리자 인 경우 사용자 지정 사용자 보기를 만들어 특정 사용자 하위 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="477ab-105">이러한 보기는 Office 365와 함께 제공 되는 표준 보기 집합에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="477ab-106">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제할 수 있으며, 만든 사용자 지정 보기는 모든 관리자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="477ab-107">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="477ab-108">관리 센터의 사용자 지정 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="477ab-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="477ab-109">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하면 변경 내용이 회사의 모든 관리자 **가 사용자** 페이지로 이동할 때 표시 되는 **필터** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="477ab-110">최대 50 개의 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="477ab-111">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하면 변경 내용이 회사의 모든 관리자 **가 사용자** 페이지로 이동할 때 표시 되는 **보기** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="477ab-112">최대 50 개의 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="477ab-113">사용자 지정 사용자 보기를 만들거나 편집 하거나 삭제 하면 변경 내용이 회사의 모든 관리자 **가 사용자** 페이지로 이동할 때 표시 되는 **보기** 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="477ab-114">최대 50 개의 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="477ab-115">표준 사용자 보기는 기본적으로 **필터** 드롭다운 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="477ab-116">표준 필터에는 **모든 사용자**, **허가 된 사용자**, **게스트 사용자**, **로그인 허용**, **로그인 차단 됨**, **허가**되지 않은 사용자, **오류**, **청구 관리자**, **전역 관리자**, **헬프데스크 관리자**, **서비스 관리자**및 **사용자 관리 관리자**가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="477ab-117">표준 보기는 편집 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="477ab-118">표준 보기에 대해 주의 해야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="477ab-119">일부 표준 보기에는 목록에 사용자가 2000 명 이상인 경우 정렬 되지 않은 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-119">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="477ab-120">이 목록에서 특정 사용자를 찾으려면 검색 상자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-120">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="477ab-121">Microsoft에서 microsoft 365을 구입 하지 않은 경우 **청구 관리자** 는 표준 보기 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-121">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="477ab-122">자세한 내용은 [관리 역할 지정](assign-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="477ab-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="477ab-123">사용자 지정 사용자 보기에 대 한 필터 선택</span><span class="sxs-lookup"><span data-stu-id="477ab-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="477ab-124">**사용자 지정 필터** 창에서 사용자 지정 보기를 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="477ab-125">필터 옵션을 여러 개 선택 하는 경우 선택한 모든 조건과 일치 하는 사용자가 포함 된 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="477ab-126">다음은 캐나다에 거주 하는 특정 도메인의 모든 사용자를 표시 하는 "캐나다 사용자" 라는 사용자 지정 보기를 만드는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="477ab-127">**A-도메인** 조직에 대해 여러 도메인을 사용 하는 경우 사용할 수 있는 도메인의 드롭다운 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="477ab-128">**B-로그인 상태** 허용 또는 차단 되는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="477ab-129">**C-위치** 국가 드롭다운 목록에서 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="477ab-130">**D-할당 된 제품 라이선스** 조직에서 사용할 수 있는 라이선스의 드롭다운 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="477ab-131">이 필터를 사용 하 여 선택한 라이선스가 할당 된 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="477ab-132">사용자에 게 추가 라이선스가 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="477ab-133">부서, 구/군/시, 시/도, 국가 또는 지역, 직책 등 조직에서 사용 되는 추가 사용자 프로필 정보를 기준으로 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="477ab-134">**기타 조건:**</span><span class="sxs-lookup"><span data-stu-id="477ab-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="477ab-135">**사용자만 동기화** 사용자의 정품 인증 여부에 관계 없이 로컬 Active Directory와 동기화 된 모든 사용자를 표시 하려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="477ab-136">**오류가 있는 사용자** 프로 비전 오류가 발생할 수 있는 사용자를 표시 하려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="477ab-137">**라이선스가 없는 사용자** 라이선스가 할당 되지 않은 모든 사용자를 찾으려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-137">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="477ab-138">이 보기의 결과에는 Exchange 사서함이 있지만 라이선스가 없는 사용자도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-138">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="477ab-139">해당 사용자를 추적 하려면 **Exchange 사서함 이나 보관 함과 함께**사용 되지 않는 필터 사용자로 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-139">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="477ab-140">이 보기의 결과에는 Exchange 보관 함이 있지만 라이선스가 없는 사용자도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-140">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="477ab-141">**Exchange 사서함 또는 보관 함이 있는 허가** 되지 않은 사용자 Exchange Online에서 만들어졌으며 Exchange 사서함이 있지만 Microsoft 365 라이선스가 할당 되지 않은 사용자 계정을 표시 하려면이 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="477ab-142">이 필터의 결과에는 Exchange 보관 사서함이 있거나 할당 된 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="477ab-143">**Exchange 사서함이 있는 허가** 되지 않은 사용자 필터는 다음과 같은 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-143">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="477ab-144">최근에 사서함이 **공유** 에서 **사용자** 로 변환 되었으며 라이선스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-144">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="477ab-145">최근에 Microsoft 365로 사서함이 마이그레이션 되었지만 라이선스가 할당 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-145">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="477ab-146">PowerShell을 사용 하 여 사서함을 만들었으며 라이선스가 할당 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-146">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="477ab-147">New-remotemailbox cmdlet을 사용 하 여 온-프레미스로 만든 새 사서함이 사용자에 대해 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-147">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="477ab-148">2000 명 이상의 사용자를 반환 하는 사용자 지정 보기를 만드는 경우 결과 사용자 목록이 정렬 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-148">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="477ab-149">이 경우 검색 상자를 사용 하 여 사용자를 찾거나 사용자 지정 보기를 편집 하 여 검색 내용을 구체화 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-149">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="477ab-150">사용자 지정 사용자 보기 만들기</span><span class="sxs-lookup"><span data-stu-id="477ab-150">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="477ab-151">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="477ab-152">**활성 사용자** 페이지에서 **필터** 를 선택 하 고 **새 필터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-152">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="477ab-153">**사용자 지정 필터** 페이지에서 필터의 이름을 입력 하 고 사용자 지정 필터의 조건을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-153">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="477ab-154">이제 사용자 지정 보기가 필터의 드롭다운 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-154">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="477ab-155">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="477ab-156">**활성 사용자** 페이지에서 **보기** 를 선택 하 고 **사용자 지정 보기 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-156">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="477ab-157">**사용자 지정 보기** 페이지에서 필터의 이름을 입력 하 고 사용자 지정 필터의 조건을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-157">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="477ab-158">이제 사용자 지정 보기가 필터의 드롭다운 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-158">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="477ab-159">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="477ab-160">**활성 사용자** 페이지에서 **보기** 를 선택 하 고 **사용자 지정 보기 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-160">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="477ab-161">**사용자 지정 보기** 페이지에서 필터의 이름을 입력 하 고 사용자 지정 필터의 조건을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-161">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="477ab-162">이제 사용자 지정 보기가 필터의 드롭다운 목록에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-162">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="477ab-163">사용자 지정 사용자 보기 편집 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="477ab-163">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="477ab-164">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="477ab-165">**활성 사용자** 페이지에서 **필터**를 선택 하 고 변경 하려는 필터를 선택한 다음 **필터 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-165">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="477ab-166">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="477ab-167">**사용자 지정 필터** 페이지에서 필요에 따라 정보를 편집한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-167">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="477ab-168">또는 필터를 삭제 하려면 페이지 아래쪽에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-168">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="477ab-169">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="477ab-170">**활성 사용자** 페이지에서 **보기**를 선택 하 고 변경 하려는 필터를 선택한 다음 **이 보기 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="477ab-171">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="477ab-172">**사용자 지정 보기** 페이지에서 필요에 따라 정보를 편집 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="477ab-173">또는 필터를 삭제 하려면 페이지 아래쪽에서 **사용자 지정 보기 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="477ab-174">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="477ab-175">**활성 사용자** 페이지에서 **보기**를 선택 하 고 변경 하려는 필터를 선택한 다음 **이 보기 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-175">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="477ab-176">사용자 지정 보기만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-176">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="477ab-177">**사용자 지정 보기** 페이지에서 필요에 따라 정보를 편집 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-177">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="477ab-178">또는 필터를 삭제 하려면 페이지 아래쪽에서 **사용자 지정 보기 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="477ab-178">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     
---
title: 격리된 SharePoint Online 팀 사이트 관리
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 격리된 SharePoint Online 팀 사이트를 관리하고, 새 사용자 및 그룹을 추가하고, 사용자 및 그룹을 제거하고, 사용자 지정 권한이 있는 문서 하위 하위폴더를 만들 수 있습니다.
ms.openlocfilehash: 1e244738071b434efd09e8fd700462bbef7e116a
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616767"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="7402c-103">격리된 SharePoint Online 팀 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="7402c-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="7402c-104">**요약:** 다음 절차에 따라 격리된 SharePoint Online 팀 사이트를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="7402c-105">이 문서에서는 격리된 SharePoint Online 팀 사이트에 대한 일반적인 관리 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="7402c-106">새 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-106">Add a new user</span></span>

<span data-ttu-id="7402c-107">새 사용자가 사이트에 참가할 때 사이트의 참가 수준을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="7402c-108">관리: 사이트 관리자 액세스 그룹에 새 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-108">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="7402c-109">활성 공동 작업: 사이트 구성원 액세스 그룹에 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-109">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="7402c-110">보기: 사이트 뷰어 액세스 그룹에 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-110">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="7402c-111">AD DS(Active Directory 도메인 서비스)를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에 적절한 사용자를 추가하고 구독과의 동기화를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="7402c-112">Microsoft 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 Microsoft PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="7402c-113">Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에 적절한 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="7402c-114">PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7402c-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="7402c-115">UPN(사용자 계정 이름)을 사용하여 액세스 그룹에 사용자 계정을 추가하려면 다음 PowerShell 명령 블록을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7402c-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="7402c-116">표시 이름을 사용하여 액세스 그룹에 사용자 계정을 추가하려면 다음 PowerShell 명령 블록을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7402c-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="7402c-117">새 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-117">Add a new group</span></span>

<span data-ttu-id="7402c-118">전체 그룹에 대한 액세스를 추가하려면 사이트에 있는 그룹의 모든 구성원의 참가 수준을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="7402c-119">관리: 사이트 관리자 액세스 그룹에 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-119">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="7402c-120">활성 공동 작업: 사이트 구성원 액세스 그룹에 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-120">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="7402c-121">보기: 사이트 뷰어 액세스 그룹에 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="7402c-121">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="7402c-122">AD DS를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 그룹에 적절한 그룹을 추가하고 구독과의 동기화를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="7402c-123">Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="7402c-124">Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에 적절한 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="7402c-125">PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7402c-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="7402c-126">그런 다음 다음 PowerShell 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-126">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="7402c-127">사용자 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-127">Remove a user</span></span>

<span data-ttu-id="7402c-128">사이트에서 다른 사람의 액세스 권한을 제거해야 하는 경우 사이트 참여에 따라 현재 구성원으로 있는 액세스 그룹에서 해당 액세스 권한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="7402c-129">관리: 사이트 관리자 액세스 그룹에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-129">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="7402c-130">활성 공동 작업: 사이트 구성원 액세스 그룹에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-130">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="7402c-131">보기: 사이트 뷰어 액세스 그룹에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-131">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="7402c-132">AD DS를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에서 해당 사용자를 제거하고 구독과의 동기화를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="7402c-133">Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="7402c-134">Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에서 해당 사용자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="7402c-135">PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7402c-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="7402c-136">UPN이 있는 액세스 그룹에서 사용자 계정을 제거하려면 다음 PowerShell 명령 블록을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7402c-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="7402c-137">표시 이름이 있는 액세스 그룹에서 사용자 계정을 제거하려면 다음 PowerShell 명령 블록을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7402c-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="7402c-138">그룹 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-138">Remove a group</span></span>

<span data-ttu-id="7402c-139">전체 그룹에 대한 액세스를 제거하려면 사이트 참가에 따라 현재 구성원으로 있는 액세스 그룹에서 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="7402c-140">관리: 사이트 관리자 액세스 그룹에서 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-140">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="7402c-141">활성 공동 작업: 사이트 구성원 액세스 그룹에서 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-141">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="7402c-142">보기: 사이트 뷰어 액세스 그룹에서 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="7402c-142">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="7402c-143">Windows Server Active Directory를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에서 해당 그룹을 제거하고 구독과의 동기화를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="7402c-144">Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="7402c-145">Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에서 해당 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="7402c-146">PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7402c-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="7402c-147">표시 이름을 사용하여 액세스 그룹에서 그룹을 제거하려면 다음 PowerShell 명령 블록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="7402c-148">사용자 지정 권한이 있는 문서 하위폴더 만들기</span><span class="sxs-lookup"><span data-stu-id="7402c-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="7402c-149">경우에 따라 격리된 사이트 내에서 작업하는 일부 작업자는 공동 작업을 위해 보다 개인 장소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="7402c-150">SharePoint Online 사이트의 경우 사이트의 문서 폴더에 하위 폴더를 만들고 사용자 지정 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="7402c-151">사용 권한이 없는 하위에는 하위폴더가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-151">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="7402c-152">사용자 지정 권한이 있는 문서 하위폴더를 만들하려면 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-152">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="7402c-153">사이트에 대한 관리자 액세스 그룹의 구성원인 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="7402c-154">도움을 받으려면 [Microsoft 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7402c-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="7402c-155">격리된 팀 사이트로 이동하여 **문서를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-155">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="7402c-156">사용자 지정 권한이 있는 하위 폴더가 포함될 문서 폴더로 찾아 폴더를 만든 다음 열어 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="7402c-157">**공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-157">Click **Share**.</span></span>

5. <span data-ttu-id="7402c-158">고급 **사용자와 공유를 > 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-158">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="7402c-159">사용 **권한 상속 중지를 클릭한** 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="7402c-160">**공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-160">Click **Share**.</span></span>

8. <span data-ttu-id="7402c-161">고급 **사용자와 공유를 > 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-161">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="7402c-162">고급 **사용자와 공유 > 권한 > 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="7402c-163">사용 권한 페이지에서 목록의 **\<site name> 구성원을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-163">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="7402c-164">구성원 **\<site name> 페이지에서** 사이트 구성원 액세스 그룹 옆의 확인 표시를 선택하고 작업을 **클릭한** 다음 그룹에서 사용자 **제거를** 클릭한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="7402c-165">이 하위폴더에 특정 구성원을 추가하려면 새 구성원을 > **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-165">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="7402c-166">공유 **대화** 상자에서 하위 폴더의 파일에 공동 작업을 할 수 있는 사용자 계정의 이름을 입력하고 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7402c-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="7402c-167">웹 페이지를 새로 고쳐 새 결과를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-167">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="7402c-168">왼쪽  탐색의 그룹 아래에서 **\<site name> 방문자** 그룹을 클릭하고 11-14단계를 사용하여 하위 폴더의 파일을 볼 수 있는 사용자 계정 집합을 지정합니다(필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="7402c-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="7402c-169">왼쪽  탐색의 그룹 아래에서 **\<site name> Owners** 그룹을 클릭하고 11-14단계를 사용하여 하위폴더에서 사용 권한을 관리할 수 있는 사용자 계정 집합을 지정합니다(필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="7402c-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="7402c-170">브라우저에서 **사용자 및 그룹** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7402c-170">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="7402c-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7402c-171">See Also</span></span>

[<span data-ttu-id="7402c-172">격리된 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="7402c-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="7402c-173">격리된 SharePoint Online 팀 사이트 디자인</span><span class="sxs-lookup"><span data-stu-id="7402c-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="7402c-174">격리된 SharePoint Online 팀 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="7402c-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)

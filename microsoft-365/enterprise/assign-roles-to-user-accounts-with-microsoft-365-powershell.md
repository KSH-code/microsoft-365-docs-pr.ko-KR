---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정에 역할 할당
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 이 문서에서는 Microsoft 365 용 PowerShell을 빠르고 쉽게 사용 하 여 사용자 계정에 관리자 역할을 할당 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754201"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="1cd28-103">PowerShell을 사용 하 여 Microsoft 365 사용자 계정에 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="1cd28-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="1cd28-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="1cd28-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1cd28-105">Microsoft 365 용 PowerShell을 사용 하 여 사용자 계정에 쉽게 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="1cd28-106">Microsoft 365 관리 센터를 사용 하 여 사용자 계정에  [관리자 역할을 할당](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="1cd28-107">추가 리소스 목록은 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1cd28-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1cd28-108">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="1cd28-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1cd28-109">먼저 전역 관리자 계정을 사용 하 여 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="1cd28-110">다음으로, 역할에 추가 하려는 사용자 계정의 로그인 이름 (예: fredsm \@ contoso.com)을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="1cd28-111">이를 UPN (사용자 계정 이름)이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="1cd28-112">다음으로, 역할 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-112">Next, determine the name of the role.</span></span> <span data-ttu-id="1cd28-113">[Azure Active Directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cd28-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="1cd28-114">이 문서의 참고 사항에 주의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1cd28-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="1cd28-115">Azure AD (Active Directory) PowerShell의 일부 역할 이름이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="1cd28-116">예를 들어 Microsoft 365 관리 센터의 *Sharepoint 관리자* 역할은 Azure AD PowerShell의 *sharepoint 서비스 관리자* 입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="1cd28-117">다음으로, 로그인 및 역할 이름을 입력 하 고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="1cd28-118">다음은 *belindan \@ contoso.com* 계정에 SharePoint 서비스 관리자 역할을 할당 하는 완성 된 명령 집합의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="1cd28-119">특정 관리자 역할의 사용자 이름 목록을 표시 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1cd28-120">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="1cd28-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1cd28-121">먼저 전역 관리자 계정을 사용 하 여 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="1cd28-122">단일 역할 변경의 경우</span><span class="sxs-lookup"><span data-stu-id="1cd28-122">For a single role change</span></span>

<span data-ttu-id="1cd28-123">사용자 계정을 지정 하는 가장 일반적인 방법은 해당 표시 이름 또는 전자 메일 이름을 사용 하 여 로그인 이름 또는 UPN (사용자 계정 이름)이 라고도 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="1cd28-124">사용자 계정의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="1cd28-124">Display names of user accounts</span></span>

<span data-ttu-id="1cd28-125">사용자 계정의 표시 이름으로 작업 하는 데 사용 되는 경우 다음 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="1cd28-126">구성 하려는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="1cd28-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="1cd28-127">사용자 계정을 지정 하려면 해당 표시 이름을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="1cd28-128">계정의 전체 목록을 보려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="1cd28-129">이 명령은 표시 이름별로 정렬 된 사용자 계정의 표시 이름을 한 번에 하나씩 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="1cd28-130">**Where** cmdlet을 사용 하 여 목록을 더 작은 집합으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="1cd28-131">아래 예제를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="1cd28-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="1cd28-132">PowerShell Core에서는 이름에 *Msol* 이 포함 된 Windows powershell 모듈 및 cmdlet에 대 한 Microsoft Azure Active Directory 모듈을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1cd28-133">Windows PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="1cd28-134">이 명령은 표시 이름이 "John"으로 시작 하는 사용자 계정만 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="1cd28-135">할당 하려는 역할</span><span class="sxs-lookup"><span data-stu-id="1cd28-135">The role you want to assign</span></span>
    
    <span data-ttu-id="1cd28-136">사용자 계정에 할당할 수 있는 사용 가능한 관리자 역할 목록을 표시 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1cd28-137">계정의 표시 이름과 역할 이름을 확인 한 후에는 다음 명령을 사용 하 여 계정에 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="1cd28-138">메모장에 명령을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="1cd28-139">*$DispName* 및 *$roleName* 변수에 대해 설명 텍스트를 해당 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="1cd28-140">문자를 제거 \< and > 하 되 따옴표는 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="1cd28-141">수정 된 줄을 Windows PowerShell 용 Microsoft Azure Active Directory 모듈 창에 붙여 넣어 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="1cd28-142">또는 Windows PowerShell ISE (통합 스크립트 환경)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="1cd28-143">다음은 완성 된 명령 집합의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="1cd28-144">사용자 계정의 로그인 이름</span><span class="sxs-lookup"><span data-stu-id="1cd28-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="1cd28-145">사용자 계정의 로그인 이름 또는 Upn으로 작업 하는 데 사용 되는 경우 다음 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="1cd28-146">사용자 계정의 UPN</span><span class="sxs-lookup"><span data-stu-id="1cd28-146">The user account's UPN</span></span>
    
    <span data-ttu-id="1cd28-147">UPN을 모르는 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="1cd28-148">이 명령은 UPN에 따라 정렬 된 사용자 계정의 UPN을 한 번에 하나씩 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="1cd28-149">**Where** cmdlet을 사용 하 여 목록을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="1cd28-150">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="1cd28-151">이 명령은 표시 이름이 "John"으로 시작 하는 사용자 계정만 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="1cd28-152">할당 하려는 역할</span><span class="sxs-lookup"><span data-stu-id="1cd28-152">The role you want to assign</span></span>
    
    <span data-ttu-id="1cd28-153">사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1cd28-154">계정의 UPN과 역할 이름을 받은 후에는 다음 명령을 사용 하 여 계정에 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="1cd28-155">명령을 복사 하 여 메모장에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="1cd28-156">**$UpnName** 및 **$roleName** 변수</span><span class="sxs-lookup"><span data-stu-id="1cd28-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="1cd28-157">설명 텍스트를 해당 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-157">Replace the description text with their values.</span></span> <span data-ttu-id="1cd28-158">문자를 제거 \< and > 하 되 따옴표는 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="1cd28-159">수정 된 줄을 Windows PowerShell 용 Microsoft Azure Active Directory 모듈 창에 붙여 넣어 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="1cd28-160">또는 Windows PowerShell ISE를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="1cd28-161">다음은 완성 된 명령 집합의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="1cd28-162">여러 역할 변경</span><span class="sxs-lookup"><span data-stu-id="1cd28-162">Multiple role changes</span></span>

<span data-ttu-id="1cd28-163">여러 역할 변경의 경우 다음 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="1cd28-164">구성 하려는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="1cd28-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="1cd28-165">이전 섹션의 방법을 사용 하 여 표시 이름 또는 Upn 집합을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="1cd28-166">각 사용자 계정에 할당 하려는 역할</span><span class="sxs-lookup"><span data-stu-id="1cd28-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="1cd28-167">사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1cd28-168">다음으로 표시 이름이 나 UPN 및 role name 필드가 있는 CSV (쉼표로 구분 된 값) 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="1cd28-169">Microsoft Excel에서이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="1cd28-170">다음은 표시 이름에 대 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="1cd28-171">다음으로, CSV 파일의 위치를 입력 하 고 PowerShell 명령 프롬프트에서 결과 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="1cd28-172">Upn의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="1cd28-173">다음으로, CSV 파일의 위치를 입력 하 고 PowerShell 명령 프롬프트에서 결과 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd28-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="1cd28-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cd28-174">See also</span></span>

- [<span data-ttu-id="1cd28-175">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="1cd28-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1cd28-176">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="1cd28-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1cd28-177">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="1cd28-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

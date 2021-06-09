---
title: PowerShell을 Microsoft 365 사용자 계정에 역할 할당
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
description: 이 문서에서는 PowerShell을 사용하여 사용자 계정에 관리자 역할을 Microsoft 365 방법을 알아보습니다.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905383"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="99305-103">PowerShell을 통해 사용자 Microsoft 365 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="99305-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="99305-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="99305-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="99305-105">PowerShell을 사용하여 사용자 계정에 역할을 쉽게 할당할 수 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99305-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="99305-106">Microsoft 365 관리 [](../admin/add-users/assign-admin-roles.md) 센터를 통해 사용자 계정에 관리자 역할을 할당하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="99305-107">추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="99305-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="99305-108">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="99305-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="99305-109">먼저 전역 관리자 계정을 사용하여 Microsoft 365 [테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="99305-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="99305-110">그런 다음 역할에 추가할 사용자 계정의 로그인 이름(예: fredsm \@ contoso.com)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="99305-111">이를 UPN(사용자 계정 이름)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="99305-112">그런 다음 역할의 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-112">Next, determine the name of the role.</span></span> <span data-ttu-id="99305-113">에서 [관리자 역할 권한을 Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="99305-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="99305-114">이 문서의 메모에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="99305-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="99305-115">일부 역할 이름은 Azure AD Azure Active Directory PowerShell과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="99305-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="99305-116">예를 들어 SharePoint *관리* 센터의 Microsoft 365 관리자 역할은 Azure AD PowerShell의 SharePoint *서비스* 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="99305-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="99305-117">그런 다음 로그인 및 역할 이름을 입력하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
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

<span data-ttu-id="99305-118">다음은 SharePoint 서비스 관리자 역할을 *belindan \@* contoso.com 명령 집합의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="99305-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
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

<span data-ttu-id="99305-119">특정 관리자 역할의 사용자 이름 목록을 표시하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="99305-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="99305-120">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="99305-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="99305-121">먼저 전역 관리자 계정을 사용하여 Microsoft 365 [테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="99305-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="99305-122">단일 역할 변경의 경우</span><span class="sxs-lookup"><span data-stu-id="99305-122">For a single role change</span></span>

<span data-ttu-id="99305-123">사용자 계정을 지정하는 가장 일반적인 방법은 표시 이름 또는 해당 전자 메일 이름(로그인 이름 또는 UPN(사용자 계정 이름)이라고도 하는)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99305-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="99305-124">사용자 계정의 이름 표시</span><span class="sxs-lookup"><span data-stu-id="99305-124">Display names of user accounts</span></span>

<span data-ttu-id="99305-125">사용자 계정의 표시 이름을 사용하는 경우 다음 정보를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="99305-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="99305-126">구성할 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="99305-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="99305-127">사용자 계정을 지정하려면 해당 표시 이름을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="99305-128">계정의 전체 목록을 표시하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="99305-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="99305-129">이 명령은 사용자 계정의 표시 이름을 표시 이름별로 정렬하여 한 화면씩 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="99305-130">**Where** cmdlet을 사용하여 목록을 더 작은 집합으로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="99305-131">아래 예제를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="99305-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="99305-132">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="99305-133">Windows PowerShell에서 이러한 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="99305-134">이 명령은 표시 이름이 "John"으로 시작하는 사용자 계정만 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="99305-135">할당할 역할</span><span class="sxs-lookup"><span data-stu-id="99305-135">The role you want to assign</span></span>
    
    <span data-ttu-id="99305-136">사용자 계정에 할당할 수 있는 사용 가능한 관리자 역할 목록을 표시하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="99305-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="99305-137">계정의 표시 이름과 역할 이름을 확인한 후 다음 명령을 사용하여 계정에 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="99305-138">명령을 명령에 붙여 메모장.</span><span class="sxs-lookup"><span data-stu-id="99305-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="99305-139">$dispName *$roleName* *변수의* 경우 설명 텍스트를 해당 값으로 바 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="99305-140">문자를 \< and > 제거하 고 인용 부호를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="99305-141">수정된 줄을 실행하기 위해 Microsoft Azure Active Directory 모듈에 Windows PowerShell 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="99305-142">또는 ISE(통합 스크립트 Windows PowerShell)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="99305-143">완성된 명령 집합의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="99305-144">사용자 계정의 로그인 이름</span><span class="sxs-lookup"><span data-stu-id="99305-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="99305-145">사용자 계정의 로그인 이름 또는 UPNS로 작업하는 데 사용되는 경우 다음 정보를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="99305-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="99305-146">사용자 계정의 UPN</span><span class="sxs-lookup"><span data-stu-id="99305-146">The user account's UPN</span></span>
    
    <span data-ttu-id="99305-147">UPN을 모르는 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="99305-148">이 명령은 사용자 계정의 UPN을 UPN별로 정렬하여 한 화면씩 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="99305-149">Where cmdlet을 **사용하여** 목록을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="99305-150">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="99305-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="99305-151">이 명령은 표시 이름이 "John"으로 시작하는 사용자 계정만 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="99305-152">할당할 역할</span><span class="sxs-lookup"><span data-stu-id="99305-152">The role you want to assign</span></span>
    
    <span data-ttu-id="99305-153">사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="99305-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="99305-154">계정의 UPN과 역할 이름을 지정한 후 다음 명령을 사용하여 계정에 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="99305-155">명령을 복사하여 명령에 붙여 메모장.</span><span class="sxs-lookup"><span data-stu-id="99305-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="99305-156">변수 **및 $upnName** **$roleName.**</span><span class="sxs-lookup"><span data-stu-id="99305-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="99305-157">설명 텍스트를 해당 값으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-157">Replace the description text with their values.</span></span> <span data-ttu-id="99305-158">문자를 \< and > 제거하 고 인용 부호를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="99305-159">수정된 줄을 실행하기 위해 Microsoft Azure Active Directory 모듈에 Windows PowerShell 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="99305-160">또는 ISE를 사용하여 WINDOWS POWERSHELL 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="99305-161">완성된 명령 집합의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="99305-162">여러 역할 변경</span><span class="sxs-lookup"><span data-stu-id="99305-162">Multiple role changes</span></span>

<span data-ttu-id="99305-163">여러 역할 변경의 경우 다음 정보를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="99305-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="99305-164">구성할 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="99305-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="99305-165">이전 섹션의 메서드를 사용하여 표시 이름 또는 UPNS 집합을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="99305-166">각 사용자 계정에 할당할 역할</span><span class="sxs-lookup"><span data-stu-id="99305-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="99305-167">사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="99305-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="99305-168">그런 다음 표시 이름 또는 UPN 및 역할 이름 필드가 있는 CSV(콤보로 구분된 값) 텍스트 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="99305-169">이 작업을 쉽게 할 수 있는 Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="99305-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="99305-170">표시 이름의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="99305-171">그런 다음 CSV 파일의 위치를 입력하고 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="99305-172">UPNS의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99305-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="99305-173">그런 다음 CSV 파일의 위치를 입력하고 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99305-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="99305-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99305-174">See also</span></span>

- [<span data-ttu-id="99305-175">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="99305-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="99305-176">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="99305-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="99305-177">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="99305-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
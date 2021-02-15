---
title: PowerShell을 사용하여 보안 그룹 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: PowerShell을 사용하여 보안 그룹을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073230"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="4230e-103">PowerShell을 사용하여 보안 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="4230e-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="4230e-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="4230e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4230e-105">Microsoft 365 관리 센터 대신 Microsoft 365용 PowerShell을 사용하여 보안 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="4230e-106">이 문서에서는 보안 그룹 목록, 만들기, 변경 및 제거에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="4230e-107">이 문서의 명령 블록에 변수 값을 지정해야 하는 경우 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="4230e-108">명령 블록을 클립보드에 복사하여 메모장 또는 PowerShell ISE(통합 스크립트 환경)에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="4230e-109">변수 값을 입력하고 "<" 및 ">" 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="4230e-110">PowerShell 창 또는 PowerShell ISE에서 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="4230e-111">PowerShell을 사용하여 그룹 [구성원을](maintain-group-membership-with-microsoft-365-powershell.md) 관리하기 위해 보안 그룹 구성원 유지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4230e-112">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="4230e-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4230e-113">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="4230e-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="4230e-114">그룹 나열</span><span class="sxs-lookup"><span data-stu-id="4230e-114">List your groups</span></span>

<span data-ttu-id="4230e-115">이 명령을 사용하여 모든 그룹을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="4230e-116">다음 명령을 사용하여 특정 그룹의 설정을 표시 이름으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="4230e-117">새 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="4230e-117">Create a new group</span></span>

<span data-ttu-id="4230e-118">이 명령을 사용하여 새 보안 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="4230e-119">그룹의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="4230e-119">Change the settings on a group</span></span>

<span data-ttu-id="4230e-120">다음 명령을 사용하여 그룹의 설정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="4230e-121">그런 다음 [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) 문서를 사용하여 설정을 변경하는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="4230e-122">보안 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="4230e-122">Remove a security group</span></span>

<span data-ttu-id="4230e-123">다음 명령을 사용하여 보안 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="4230e-124">보안 그룹의 소유자 관리</span><span class="sxs-lookup"><span data-stu-id="4230e-124">Manage the owners of a security group</span></span>

<span data-ttu-id="4230e-125">다음 명령을 사용하여 보안 그룹의 현재 소유자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="4230e-126">다음 명령을 사용하여 UPN(사용자 계정 **이름)으로** 사용자 계정을 보안 그룹의 현재 소유자에게 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="4230e-127">다음 명령을 사용하여 표시 이름으로 사용자  계정을 보안 그룹의 현재 소유자에게 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="4230e-128">다음 명령을 사용하여 **UPN을** 통해 보안 그룹의 현재 소유자에게 사용자 계정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="4230e-129">다음 명령을 사용하여 보안 그룹의 현재  소유자에게 표시 이름으로 사용자 계정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4230e-130">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="4230e-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4230e-131">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="4230e-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="4230e-132">그룹 나열</span><span class="sxs-lookup"><span data-stu-id="4230e-132">List your groups</span></span>

<span data-ttu-id="4230e-133">이 명령을 사용하여 모든 그룹을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="4230e-134">다음 명령을 사용하여 특정 그룹의 설정을 표시 이름으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="4230e-135">새 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="4230e-135">Create a new group</span></span>

<span data-ttu-id="4230e-136">이 명령을 사용하여 새 보안 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="4230e-137">그룹의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="4230e-137">Change the settings on a group</span></span>

<span data-ttu-id="4230e-138">다음 명령을 사용하여 그룹의 설정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="4230e-139">그런 다음 [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) 문서를 사용하여 설정을 변경하는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="4230e-140">보안 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="4230e-140">Remove a security group</span></span>

<span data-ttu-id="4230e-141">다음 명령을 사용하여 보안 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4230e-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="4230e-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4230e-142">See also</span></span>

[<span data-ttu-id="4230e-143">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="4230e-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4230e-144">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="4230e-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4230e-145">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="4230e-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)


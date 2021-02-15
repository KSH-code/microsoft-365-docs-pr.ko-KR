---
title: PowerShell을 통해 보안 그룹 구성원 유지 관리
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell을 사용하여 Microsoft 365 그룹의 구성원 자격을 유지하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: b47f501c9726e1d4dcb2e9d61108224db0408b8e
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073064"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="d55ea-103">PowerShell을 통해 보안 그룹 구성원 유지 관리</span><span class="sxs-lookup"><span data-stu-id="d55ea-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="d55ea-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d55ea-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d55ea-105">Microsoft 365 관리 센터 대신 Microsoft 365용 PowerShell을 사용하여 Microsoft 365에서 보안 그룹 구성원을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="d55ea-106">[Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) 관리 센터를 통해 Microsoft 365 그룹 구성원을 유지 관리하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="d55ea-107">추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="d55ea-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d55ea-108">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="d55ea-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="d55ea-109">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="d55ea-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="d55ea-110">사용자 계정을 그룹의 구성원으로 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="d55ea-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="d55ea-111">**UPN으로** 사용자 계정을 추가하려면 사용자 계정 UPN(사용자 계정 이름)(예: belindan@contoso.com) 및 보안 그룹 표시 이름을 입력하고 "<" 및 ">" 문자를 제거한 다음 PowerShell 창 또는 PowerShell ISE(통합 스크립트 환경)에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-112">표시 이름으로 사용자 계정을 추가하려면 사용자 계정 표시 이름(예: Belinda Newman)과 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-113">**UPN으로** 사용자 계정을 제거하려면 사용자 계정 UPN(예: belindan@contoso.com) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-114">표시 이름으로 사용자 계정을 제거하려면 사용자 계정 표시 이름(예: Belinda Newman)과 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="d55ea-115">그룹의 구성원으로 그룹 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="d55ea-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="d55ea-116">보안 그룹은 다른 그룹을 구성원으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="d55ea-117">그러나 Microsoft 365 그룹은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="d55ea-118">이 섹션에는 보안 그룹에 대한 그룹만 추가하거나 제거하는 PowerShell 명령이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="d55ea-119">표시 이름으로 그룹을 추가하기 위해 추가할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-120">표시 이름으로 그룹을 제거하려면 제거할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d55ea-121">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="d55ea-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d55ea-122">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d55ea-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="d55ea-123">사용자 계정을 그룹의 구성원으로 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="d55ea-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="d55ea-124">**UPN으로** 사용자 계정을 추가하려면 사용자 계정 UPN(사용자 계정 이름)(예: belindan@contoso.com)과 그룹 표시 이름을 입력하고 "<" 및 ">" 문자를 제거한 다음 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-125">표시 이름으로 사용자 계정을 추가하려면 사용자 계정 표시 이름(예: Belinda Newman)과 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-126">**UPN으로** 사용자 계정을 제거하려면 사용자 계정 UPN(예: belindan@contoso.com) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d55ea-127">표시 이름으로 사용자 계정을 제거하려면 사용자 계정 표시 이름(예: Belinda Newman)과 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="d55ea-128">그룹의 구성원으로 그룹 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="d55ea-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="d55ea-129">보안 그룹은 다른 그룹을 구성원으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="d55ea-130">그러나 Microsoft 365 그룹은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="d55ea-131">이 섹션에는 보안 그룹에 대한 그룹만 추가하거나 제거하는 PowerShell 명령이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="d55ea-132">표시 이름으로 그룹을 추가하기 위해 추가할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="d55ea-133">표시 이름으로 그룹을 제거하려면 제거할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d55ea-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="d55ea-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d55ea-134">See also</span></span>

[<span data-ttu-id="d55ea-135">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="d55ea-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d55ea-136">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="d55ea-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d55ea-137">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="d55ea-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)


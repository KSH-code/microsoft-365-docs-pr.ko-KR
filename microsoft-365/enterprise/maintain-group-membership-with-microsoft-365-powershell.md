---
title: PowerShell을 사용 하 여 Microsoft 365 그룹 구성원 유지 관리
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell을 사용 하 여 Microsoft 365 그룹의 멤버 자격을 유지 하는 방법을 알아봅니다.
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235633"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="6b07a-103">PowerShell을 사용 하 여 Microsoft 365 그룹 구성원 유지 관리</span><span class="sxs-lookup"><span data-stu-id="6b07a-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="6b07a-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="6b07a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6b07a-105">Microsoft 365 관리 센터 대신 microsoft 365 용 PowerShell을 사용 하 여 Microsoft 365의 그룹 구성원 자격을 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="6b07a-106">사용자 계정 및 그룹 이름을 지정 하 여 실행 가능한 PowerShell 명령을 생성 하려면이 [그룹 유지 관리 Microsoft Excel 통합 문서](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

>[!Note]
><span data-ttu-id="6b07a-107">Microsoft 365 관리 센터를 사용 하 여 [microsoft 365 그룹 구성원을 유지 관리 하는 방법을 알아봅니다](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) .</span><span class="sxs-lookup"><span data-stu-id="6b07a-107">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="6b07a-108">추가 리소스 목록은 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b07a-108">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6b07a-109">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="6b07a-109">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="6b07a-110">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="6b07a-111">사용자 계정을 그룹의 구성원으로 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6b07a-111">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="6b07a-112">**Upn을 기준으로 사용자 계정을 추가 하려면**Upn (사용자 계정 이름)을 입력 하 고 (예: belindan@contoso.com), 그룹 표시 이름을 "<" 및 ">" 문자를 제거 하 고 powershell 창 또는 powershell ISE (통합 스크립트 환경)에서 이러한 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-112">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-113">**표시 이름으로 사용자 계정을 추가 하려면**사용자 계정 표시 이름 (예: Belinda newman)과 그룹 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-113">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-114">UPN을 사용 하 **여 사용자 계정을 제거 하려면**사용자 계정 UPN (예: belindan@contoso.com)과 그룹 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-114">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-115">**표시 이름으로 사용자 계정을 제거 하려면**사용자 계정 표시 이름 (예: Belinda newman)과 그룹 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-115">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="6b07a-116">그룹 구성원으로 그룹 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6b07a-116">Add or remove groups as members of a group</span></span>

<span data-ttu-id="6b07a-117">보안 그룹은 다른 그룹을 구성원으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-117">Security groups can contain other groups as members.</span></span> <span data-ttu-id="6b07a-118">그러나 Microsoft 365 그룹은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-118">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="6b07a-119">이 섹션에는 보안 그룹에 대 한 그룹만 추가 하거나 제거 하기 위한 PowerShell 명령이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-119">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="6b07a-120">**표시 이름별로 그룹을 추가 하려면**추가할 그룹의 표시 이름을 입력 하 고 구성원 그룹을 포함할 그룹의 표시 이름을 채운 다음 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-120">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-121">**표시 이름으로 그룹을 제거 하려면**제거할 그룹의 표시 이름과 구성원 그룹을 포함 하는 그룹의 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-121">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6b07a-122">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="6b07a-122">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6b07a-123">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-123">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="6b07a-124">사용자 계정을 그룹의 구성원으로 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6b07a-124">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="6b07a-125">**Upn을 기준으로 사용자 계정을 추가 하려면**Upn (사용자 계정 이름)을 입력 하 고 (예: belindan@contoso.com), 그룹 표시 이름을 "<" 및 ">" 문자를 제거 하 고 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-125">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-126">**표시 이름으로 사용자 계정을 추가 하려면**사용자 계정 표시 이름 (예: Belinda newman)과 그룹 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-126">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-127">UPN을 사용 하 **여 사용자 계정을 제거 하려면**사용자 계정 UPN (예: belindan@contoso.com)과 그룹 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-127">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="6b07a-128">**표시 이름으로 사용자 계정을 제거 하려면**사용자 계정 표시 이름 (예: Belinda newman)과 그룹 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-128">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="6b07a-129">그룹 구성원으로 그룹 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6b07a-129">Add or remove groups as members of a group</span></span>

<span data-ttu-id="6b07a-130">보안 그룹은 다른 그룹을 구성원으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-130">Security groups can contain other groups as members.</span></span> <span data-ttu-id="6b07a-131">그러나 Microsoft 365 그룹은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-131">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="6b07a-132">이 섹션에는 보안 그룹에 대 한 그룹만 추가 하거나 제거 하기 위한 PowerShell 명령이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-132">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="6b07a-133">**표시 이름별로 그룹을 추가 하려면**추가할 그룹의 표시 이름을 입력 하 고 구성원 그룹을 포함할 그룹의 표시 이름을 채운 다음 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-133">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="6b07a-134">**표시 이름으로 그룹을 제거 하려면**제거할 그룹의 표시 이름과 구성원 그룹을 포함 하는 그룹의 표시 이름을 입력 하 고 powershell 창 또는 powershell ISE에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b07a-134">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="6b07a-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b07a-135">See also</span></span>

[<span data-ttu-id="6b07a-136">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="6b07a-136">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6b07a-137">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="6b07a-137">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6b07a-138">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="6b07a-138">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)


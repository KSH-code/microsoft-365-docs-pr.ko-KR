---
title: PowerShell을 통해 보안 그룹 구성원 유지 관리
ms.author: kvice
author: kelleyvice-msft
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
description: PowerShell을 사용하여 그룹에서 구성원을 유지 관리하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 0a66db0748c50d296ff9d26969ae8b3caa7f310f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212572"
---
# <a name="maintain-security-group-membership-with-powershell"></a>PowerShell을 통해 보안 그룹 구성원 유지 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

보안 그룹 구성원 자격을 Microsoft 365 PowerShell을 사용하여 Microsoft 365 관리 센터 그룹 구성원 자격을 Microsoft 365. 

>[!Note]
>[그룹 구성원 자격을 Microsoft 365 방법을](../admin/create-groups/add-or-remove-members-from-groups.md) Microsoft 365 관리 센터. 추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기
먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>사용자 계정을 그룹의 구성원으로 추가 또는 제거

**UPN으로** 사용자 계정을 추가하려면 사용자 계정 UPN(사용자 계정 이름)(예: belindan@contoso.com) 및 보안 그룹 표시 이름을 입력하고 "<" 및 ">" 문자를 제거한 다음 PowerShell 창 또는 PowerShell ISE(통합 스크립트 환경)에서 다음 명령을 실행합니다.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**표시 이름으로** 사용자 계정을 추가하려면 사용자 계정 표시 이름(예: Belinda Newman) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**UPN으로** 사용자 계정을 제거하려면 사용자 계정 UPN(예: belindan@contoso.com) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**표시 이름으로** 사용자 계정을 제거하려면 사용자 계정 표시 이름(예: Belinda Newman) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>그룹의 구성원으로 그룹 추가 또는 제거

보안 그룹은 다른 그룹을 구성원으로 포함할 수 있습니다. 그러나 Microsoft 365 그룹은 사용할 수 없습니다. 이 섹션에는 보안 그룹에 대한 그룹만 추가하거나 제거하는 PowerShell 명령이 포함되어 있습니다.

표시 이름으로 그룹을 추가하기 위해 추가할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

표시 이름으로 그룹을 제거하려면 제거할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>사용자 계정을 그룹의 구성원으로 추가 또는 제거

**UPN으로** 사용자 계정을 추가하려면 사용자 계정 UPN(사용자 계정 이름)(예: belindan@contoso.com) 및 그룹 표시 이름을 입력하고 "<" 및 ">" 문자를 제거한 다음 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**표시 이름으로** 사용자 계정을 추가하려면 사용자 계정 표시 이름(예: Belinda Newman) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**UPN으로** 사용자 계정을 제거하려면 사용자 계정 UPN(예: belindan@contoso.com) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**표시 이름으로** 사용자 계정을 제거하려면 사용자 계정 표시 이름(예: Belinda Newman) 및 그룹 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>그룹의 구성원으로 그룹 추가 또는 제거

보안 그룹은 다른 그룹을 구성원으로 포함할 수 있습니다. 그러나 Microsoft 365 그룹은 사용할 수 없습니다. 이 섹션에는 보안 그룹에 대한 그룹만 추가하거나 제거하는 PowerShell 명령이 포함되어 있습니다.

표시 이름으로 그룹을 추가하기 위해 추가할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

표시 이름으로 그룹을 제거하려면 제거할 그룹의 표시 이름과 구성원 그룹을 포함할 그룹의 표시 이름을 입력하고 PowerShell 창 또는 PowerShell ISE에서 이러한 명령을 실행합니다.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
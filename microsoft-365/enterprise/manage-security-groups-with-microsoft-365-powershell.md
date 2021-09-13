---
title: PowerShell을 사용하여 보안 그룹 관리
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
description: PowerShell을 사용하여 보안 그룹을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: e9842585fbb88711c0efa6e515ca8b54c124338e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220936"
---
# <a name="manage-security-groups-with-powershell"></a>PowerShell을 사용하여 보안 그룹 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

보안 그룹을 관리하는 Microsoft 365 대신 PowerShell을 Microsoft 365 관리 센터 수 있습니다. 

이 문서에서는 보안 그룹 목록, 만들기, 변경 및 제거에 대해 설명하고 있습니다. 

이 문서의 명령 블록에 변수 값을 지정해야 하는 경우 다음 단계를 사용합니다.

1. 명령 블록을 클립보드에 복사하여 메모장 또는 PowerShell ISE(통합 스크립트 환경)에 붙여 넣습니다.
2. 변수 값을 입력하고 "<" 및 ">" 문자를 제거합니다.
3. PowerShell 창 또는 PowerShell ISE에서 명령을 실행합니다.

PowerShell을 사용하여 그룹 [구성원을](maintain-group-membership-with-microsoft-365-powershell.md) 관리하기 위해 보안 그룹 구성원 유지를 참조합니다.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="list-your-groups"></a>그룹 나열

이 명령을 사용하여 모든 그룹을 나열합니다.

```powershell
Get-AzureADGroup
```
다음 명령을 사용하여 표시 이름으로 특정 그룹의 설정을 표시합니다.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>새 그룹 만들기

이 명령을 사용하여 새 보안 그룹을 만들 수 있습니다.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>그룹의 설정 변경

다음 명령을 사용하여 그룹의 설정을 표시합니다.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

그런 다음 [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) 문서를 사용하여 설정을 변경하는 방법을 결정할 수 있습니다.

### <a name="remove-a-security-group"></a>보안 그룹 제거

다음 명령을 사용하여 보안 그룹을 제거합니다.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>보안 그룹의 소유자 관리

다음 명령을 사용하여 보안 그룹의 현재 소유자를 표시합니다.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
다음 명령을 사용하여 **UPN(사용자** 계정 이름)으로 사용자 계정을 보안 그룹의 현재 소유자에게 추가합니다.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
다음 명령을 사용하여 표시 이름으로 사용자  계정을 보안 그룹의 현재 소유자에게 추가합니다.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
다음 명령을 사용하여 **UPN을** 통해 보안 그룹의 현재 소유자에게 사용자 계정을 제거합니다.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

다음 명령을 사용하여 보안 그룹의 현재  소유자에게 표시 이름으로 사용자 계정을 제거합니다.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="list-your-groups"></a>그룹 나열

이 명령을 사용하여 모든 그룹을 나열합니다.

```powershell
Get-MsolGroup
```
다음 명령을 사용하여 표시 이름으로 특정 그룹의 설정을 표시합니다.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>새 그룹 만들기

이 명령을 사용하여 새 보안 그룹을 만들 수 있습니다.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>그룹의 설정 변경

다음 명령을 사용하여 그룹의 설정을 표시합니다.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

그런 다음 [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) 문서를 사용하여 설정을 변경하는 방법을 결정할 수 있습니다.

### <a name="remove-a-security-group"></a>보안 그룹 제거

다음 명령을 사용하여 보안 그룹을 제거합니다.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
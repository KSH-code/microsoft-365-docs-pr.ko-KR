---
title: PowerShell을 사용 하 여 보안 그룹 관리
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
description: PowerShell을 사용 하 여 보안 그룹을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073230"
---
# <a name="manage-security-groups-with-powershell"></a>PowerShell을 사용 하 여 보안 그룹 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터 대신 Microsoft 365 용 PowerShell을 사용 하 여 보안 그룹을 관리할 수 있습니다. 

이 문서에서는 보안 그룹 나열, 만들기, 변경 및 제거에 대해 설명 합니다. 

이 문서의 명령 블록에서 변수 값을 지정 해야 하는 경우 다음 단계를 사용 합니다.

1. 명령 블록을 클립보드에 복사 하 고 메모장 이나 ISE (PowerShell 통합 스크립트 환경)에 붙여넣습니다.
2. 변수 값을 입력 하 고 "<" 및 ">" 문자를 제거 합니다.
3. PowerShell 창 또는 PowerShell ISE에서 명령을 실행 합니다.

PowerShell을 사용 하 여 그룹 구성원 자격을 관리 하려면 [보안 그룹 구성원 유지 관리](maintain-group-membership-with-microsoft-365-powershell.md) 를 참조 하세요.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.

### <a name="list-your-groups"></a>그룹 나열

모든 그룹의 목록을 표시 하려면이 명령을 사용 합니다.

```powershell
Get-AzureADGroup
```
이러한 명령을 사용 하 여 표시 이름별로 특정 그룹의 설정을 표시 합니다.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>새 그룹 만들기

이 명령을 사용 하 여 새 보안 그룹을 만듭니다.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>그룹의 설정 변경

이러한 명령을 사용 하 여 그룹의 설정을 표시 합니다.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

그런 다음 [AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) 문서를 사용 하 여 설정을 변경 하는 방법을 결정 합니다.

### <a name="remove-a-security-group"></a>보안 그룹 제거

다음 명령을 사용 하 여 보안 그룹을 제거 합니다.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>보안 그룹의 소유자 관리

다음 명령을 사용 하 여 보안 그룹의 현재 소유자를 표시 합니다.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
이러한 명령을 사용 하 여 보안 그룹의 현재 소유자에 게 **UPN (사용자 계정 이름)** 을 기준으로 사용자 계정을 추가 합니다.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
다음 명령을 사용 하 여 보안 그룹의 현재 소유자에 게 **표시 이름별** 로 사용자 계정을 추가 합니다.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
다음 명령을 사용 하 여 보안 그룹의 현재 소유자에 대 한 **UPN** 을 가진 사용자 계정을 제거 합니다.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

다음 명령을 사용 하 여 보안 그룹의 현재 소유자에 게 **표시 이름** 으로 사용자 계정을 제거 합니다.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.

### <a name="list-your-groups"></a>그룹 나열

모든 그룹의 목록을 표시 하려면이 명령을 사용 합니다.

```powershell
Get-MsolGroup
```
이러한 명령을 사용 하 여 표시 이름별로 특정 그룹의 설정을 표시 합니다.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>새 그룹 만들기

이 명령을 사용 하 여 새 보안 그룹을 만듭니다.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>그룹의 설정 변경

이러한 명령을 사용 하 여 그룹의 설정을 표시 합니다.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

그런 다음 [remove-msolgroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) 문서를 사용 하 여 설정을 변경 하는 방법을 결정 합니다.

### <a name="remove-a-security-group"></a>보안 그룹 제거

다음 명령을 사용 하 여 보안 그룹을 제거 합니다.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)


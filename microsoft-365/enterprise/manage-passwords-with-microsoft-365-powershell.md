---
title: PowerShell을 사용 하 여 암호 관리
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
description: PowerShell을 사용 하 여 암호를 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073215"
---
# <a name="manage-passwords-with-powershell"></a>PowerShell을 사용 하 여 암호 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터 대신 microsoft 365 용 PowerShell을 사용 하 여 Microsoft 365의 암호를 관리할 수 있습니다. 

이 문서의 명령 블록에서 변수 값을 지정 해야 하는 경우 다음 단계를 사용 합니다.

1. 명령 블록을 클립보드에 복사 하 고 메모장 이나 ISE (PowerShell 통합 스크립트 환경)에 붙여넣습니다.
2. 변수 값을 입력 하 고 "<" 및 ">" 문자를 제거 합니다.
3. PowerShell 창 또는 PowerShell ISE에서 명령을 실행 합니다.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.

### <a name="set-a-password"></a>암호 설정

이러한 명령을 사용 하 여 사용자 계정에 대 한 암호를 지정 합니다.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>사용자가 자신의 암호를 강제로 변경 하도록 지정

이러한 명령을 사용 하 여 암호를 설정 하 고 사용자가 새 암호를 강제로 변경 하도록 합니다.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

이러한 명령을 사용 하 여 암호를 설정 하 고 사용자가 다음에 로그인 할 때 새 암호를 강제로 변경 하도록 합니다.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.

### <a name="set-a-password"></a>암호 설정

이러한 명령을 사용 하 여 사용자 계정에 대 한 암호를 지정 합니다.

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>사용자가 자신의 암호를 강제로 변경 하도록 지정

이러한 명령을 사용 하 여 사용자가 자신의 암호를 강제로 변경 하도록 합니다.

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)


---
title: PowerShell을 사용하여 암호 관리
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
description: PowerShell을 사용하여 암호를 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 40091d7add7f7adf9c560a90c00ad22e6c333c60
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220939"
---
# <a name="manage-passwords-with-powershell"></a>PowerShell을 사용하여 암호 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

PowerShell을 사용하여 Microsoft 365 암호를 관리할 Microsoft 365 관리 센터 수 Microsoft 365. 

이 문서의 명령 블록에 변수 값을 지정해야 하는 경우 다음 단계를 사용합니다.

1. 명령 블록을 클립보드에 복사하여 메모장 또는 PowerShell ISE(통합 스크립트 환경)에 붙여 넣습니다.
2. 변수 값을 입력하고 "<" 및 ">" 문자를 제거합니다.
3. PowerShell 창 또는 PowerShell ISE에서 명령을 실행합니다.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="set-a-password"></a>암호 설정

다음 명령을 사용하여 사용자 계정의 암호를 지정합니다.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>사용자가 강제로 암호를 변경하도록 합니다.

다음 명령을 사용하여 암호를 설정하고 사용자가 새 암호를 변경하도록 합니다.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

다음 명령을 사용하여 암호를 설정하고 다음에 로그인할 때 사용자가 새 암호를 변경하도록 합니다.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="set-a-password"></a>암호 설정

다음 명령을 사용하여 사용자 계정의 암호를 지정합니다.

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>사용자가 강제로 암호를 변경하도록 합니다.

다음 명령을 사용하여 사용자가 암호를 강제로 변경하도록 합니다.

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)


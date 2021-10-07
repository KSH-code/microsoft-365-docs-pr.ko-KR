---
title: PowerShell을 Microsoft 365 사용자 계정 삭제
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: PowerShell에서 다른 모듈을 사용하여 사용자 계정을 삭제하는 Microsoft 365 방법을 알아보습니다.
ms.openlocfilehash: dc1e5c53f2d356f0585da5a0a5285b9af28dc8f0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171918"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 Microsoft 365 사용자 계정 삭제

PowerShell을 사용하여 사용자 Microsoft 365 복원할 수 있습니다.

>[!Note]
>다음을 사용하여 사용자 [계정을](../admin/add-users/restore-user.md) 복원하는 방법을 Microsoft 365 관리 센터.
>
>추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](/admin)
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

연결한 후 다음 구문을 사용하여 개별 사용자 계정을 제거합니다.
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

이 예제에서는 사용자 계정 *fabricec 을 \@ litwareinc.com.*
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **Remove-AzureADUser** cmdlet의 *-ObjectID* 매개 변수는 계정의 로그인 이름(사용자 계정 이름 또는 계정의 개체 ID)을 허용합니다.
  
사용자 이름을 기준으로 계정 이름을 표시하려면 다음 명령을 사용합니다.
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 예에서는 *사용자 Caleb Sills의 계정 이름을 표시합니다.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

사용자 표시 이름을 기준으로 계정을 제거하려면 다음 명령을 사용합니다.
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

Microsoft Azure Active Directory Module을 통해 사용자 계정을 Windows PowerShell 계정은 영구적으로 삭제되지 않습니다. 30 일 이내에 삭제 한 사용자 계정은 복원할 수 있습니다.

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

사용자 계정을 삭제 하려면 다음 구문을 사용 합니다.
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다. Windows PowerShell에서 이러한 cmdlet을 실행합니다.
>

이 예에서는 의 사용자 계정을 *BelindaN@litwareinc.com.*
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

30 일 유예 기간 동안 삭제 된 사용자 계정을 복원 하려면 다음 구문을 사용 합니다.
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

이 예에서는 삭제된 계정 *BelindaN \@* 을 litwareinc.com.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> 복원할 수 있는 삭제된 사용자 목록을 보려면 다음 명령을 실행 합니다.
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> 사용자 계정의 원본 사용자 계정 이름이 다른 계정에서 사용된 경우에, 사용자 계정을 복원할 때 다른 사용자 계정 이름을 지정하려면 _UserPrincipalName_ 대신에 _NewUserPrincipalName_ 매개 변수를 사용합니다.


## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
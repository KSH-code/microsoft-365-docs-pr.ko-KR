---
title: PowerShell을 Microsoft 365 사용자 계정 차단
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: PowerShell을 사용하여 특정 계정에 대한 액세스를 차단하고 차단을 Microsoft 365 방법
ms.openlocfilehash: fd9eba96b09a73b2fb6e87b30096dbf8186caceb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189699"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 Microsoft 365 사용자 계정 차단

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 계정에 대한 액세스를 차단하면 모든 사용자가 계정을 사용하여 로그인하고 조직에 있는 서비스 및 데이터에 액세스할 Microsoft 365 없습니다. PowerShell을 사용하여 개별 또는 여러 사용자 계정에 대한 액세스를 차단할 수 있습니다.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="block-access-to-individual-user-accounts"></a>개별 사용자 계정에 대한 액세스 차단

다음 구문을 사용하여 개별 사용자 계정을 차단합니다.

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> **Set-AzureAD** cmdlet의 *-ObjectID* 매개 변수는 계정 로그인 이름(사용자 계정 이름)이나 계정의 개체 ID를 허용합니다.

이 예에서는 의 사용자 계정에 대한 액세스를 *fabricec@litwareinc.com.*

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

사용자 계정을 차단 해제하려면 다음 명령을 실행합니다.

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

사용자의 표시 이름을 기준으로 사용자 계정 UPN을 표시하려면 다음 명령을 사용하세요.

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

이 예에서는 사용자  *Caleb Sills의* 사용자 계정 UPN을 표시합니다.

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

사용자의 표시 이름을 기준으로 계정을 차단하려면 다음 명령을 사용하세요.

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

사용자 계정의 차단 상태를 확인하려면 다음 명령을 사용하세요.

```powershell
Get-AzureADUser  -ObjectID <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>여러 사용자 계정 차단

여러 사용자 계정에 대한 액세스를 차단하려면 각 줄에 계정 로그인 이름이 하나씩 포함된 텍스트 파일을 만들면 됩니다.

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

다음 명령에서 예제 텍스트 파일은 *C:\My Documents\Accounts.txt.* 이 파일 이름을 텍스트 파일의 경로와 파일 이름으로 바니다.

텍스트 파일에 나열 된 계정에 대 한 액세스를 차단 하려면 다음 명령을 실행 합니다.

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

텍스트 파일에 나열된 계정의 차단을 해제하기 위해 다음 명령을 실행합니다.

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="block-individual-user-accounts"></a>개별 사용자 계정 차단

다음 구문을 사용하여 개별 사용자 계정에 대한 액세스를 차단합니다.

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core는 이름에 *Msol이* Microsoft Azure Active Directory cmdlet을 Windows PowerShell 모듈용 Windows PowerShell 모듈을 지원하지 않습니다. 이러한 cmdlet은 해당 cmdlet에서 실행해야 Windows PowerShell.

이 예에서는 사용자 계정 fabricec 및 에 대한 액세스를 *\@ litwareinc.com.*

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

사용자 계정 차단 해제 하려면 다음 명령을 실행 합니다.

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

사용자 계정의 차단 상태를 확인하려면 다음 명령을 실행합니다.

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>여러 사용자 계정에 대한 액세스 차단

먼저, 각 줄에 계정이 하나씩 포함된 텍스트 파일을 만들어야 합니다.

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

다음 명령에서 예제 텍스트 파일은 *C:\My Documents\Accounts.txt.* 이 파일 이름을 텍스트 파일의 경로와 파일 이름으로 바니다.

텍스트 파일에 나열된 계정에 대한 액세스를 차단하기 위해 다음 명령을 실행합니다.

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
텍스트 파일에 나열 된 계정 차단 해제 하려면 다음 명령을 실행 합니다.

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)

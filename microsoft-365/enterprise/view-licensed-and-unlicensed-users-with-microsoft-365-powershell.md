---
title: PowerShell을 사용 하 Microsoft 365 및 허가되지 않은 사용자 보기
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: 이 문서에서는 PowerShell을 사용하여 사용자 계정의 라이선스 및 허가되지 않은 Microsoft 365 방법을 설명합니다.
ms.openlocfilehash: 015cb63fd692131d77799fe30fc94c6214bb01d3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208208"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>PowerShell을 사용 하 Microsoft 365 및 허가되지 않은 사용자 보기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 조직의 사용자 계정에는 조직에서 사용할 수 있는 라이선스 계획에서 할당된 사용 가능한 라이선스의 일부, 전체 또는 전혀 할당되지 않을 수 있습니다. PowerShell을 사용하여 조직에서 Microsoft 365 허가되지 않은 사용자를 빠르게 찾을 수 있습니다.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 
라이선스 계획(라이선스가 없는 사용자)이 할당되지 않은 조직의 모든 사용자 계정 목록을 확인하도록 다음 명령을 실행합니다.
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

라이선스 계획(사용이 허가된 사용자)이 할당된 조직의 모든 사용자 계정 목록을 확인한 후 다음 명령을 실행합니다.
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>구독의 모든 사용자를 나열하려면 명령을 `Get-AzureAdUser -All $true` 사용하세요.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

조직의 모든 사용자 계정 및 해당 라이선스 상태 목록을 확인하도록 PowerShell에서 다음 명령을 실행합니다.
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

조직의 모든 허가 되지 않은 사용자 계정 목록을 보려면 다음 명령을 실행 합니다.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

전체 목록을 보려면 다음 명령을 실행 하 여 조직에 있는 사용자 계정의 라이센스:
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)

---
title: 개별 사용자 암호가 만료되지 않도록 설정
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell을 사용 하 여 일부 개별 사용자 암호가 만료 되지 않도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 3d5d65f687a5ed02e0e20ff77482f7bef5b6b695
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173499"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>개별 사용자 암호가 만료되지 않도록 설정

## <a name="set-the-password-expiration-policy-for-your-organization"></a>조직의 암호 만료 정책 설정

1. 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">설정</a> 페이지로 이동 합니다.
2. 설정 페이지 맨 위에서 **보안 & 개인 정보**를 선택 합니다.
3. **암호 만료 정책**을 선택합니다. 
4. 암호가 만료 되지 않도록 설정 되어 있는 경우 **사용자 암호가 일 후에 만료 되도록 설정**옆의 확인란을 클릭 합니다. 암호가 만료 될 때 까지의 기간 (일)을 지정 하는 옵션을 사용할 수 있습니다.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>개별 사용자에 대 한 암호 만료 정책 설정

Microsoft 클라우드 서비스에 대 한 전역 관리자는 [Graph 용 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 을 사용 하 여 특정 사용자에 대해 암호가 만료 되지 않도록 설정할 수 있습니다. [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet을 사용 하 여 만료 되지 않은 구성을 제거 하거나 만료 되지 않도록 설정 된 사용자 암호를 확인할 수도 있습니다.

이 가이드는 id 및 디렉터리 서비스에 대 한 Azure AD도 사용 하는 Intune 및 Microsoft 365 같은 다른 공급자에 적용 됩니다. 정책에서 변경 가능한 유일한 부분은 암호 만료입니다.

Graph 용 Azure AD PowerShell에 대 한 자세한 내용은 [Azure Active Directory PowerShell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)를 참조 하세요.

> [!NOTE]
> 디렉터리 동기화를 통해 동기화 되지 않은 사용자 계정의 암호만 만료 되지 않도록 구성할 수 있습니다. 디렉터리 동기화에 대 한 자세한 내용은 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)를 참조 하십시오.

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>암호에 대 한 만료 정책을 확인 하는 방법

AzureAD 모듈의 AzureADUser 명령에 대 한 자세한 내용은 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)를 참조 문서를 참조 하세요.

다음 명령 중 하나를 실행 합니다.

- 단일 사용자의 암호가 만료 되지 않도록 설정 되어 있는지 확인 하려면 UPN (예: *user@contoso.onmicrosoft.com*) 또는 확인 하려는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    예제:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- 모든 사용자에 대 한 **암호 사용 기간 제한 없음** 설정을 보려면 다음 cmdlet을 실행 합니다.

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 이름이 **ReportPasswordNeverExpires** 인 현재 사용자의 바탕 화면에서 PasswordNeverExpires가 있는 모든 사용자의 보고서를 html로 가져오려면

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- PasswordNeverExpires 이름이 **ReportPasswordNeverExpires** 인 현재 사용자의 데스크톱에서 csv에 있는 모든 사용자에 대 한 보고서를 가져오려면

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>암호가 만료 되도록 설정

다음 명령 중 하나를 실행 합니다.

- 암호가 만료 되도록 한 명의 사용자에 대 한 암호를 설정 하려면 UPN 또는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 조직의 모든 사용자에 대 한 암호를 설정 하 여 만료 되도록 하려면 다음 cmdlet을 사용 합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>암호가 만료 되지 않도록 설정

다음 명령 중 하나를 실행 합니다.

- 한 사용자의 암호가 만료 되지 않도록 설정 하려면 사용자의 UPN 또는 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 조직의 모든 사용자에 대 한 암호가 만료 되지 않도록 설정 하려면 다음 cmdlet을 실행 합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> 특성에 따라 `-PasswordPolicies DisablePasswordExpiration` 암호를 여전히 age로 설정 합니다. `pwdLastSet` 사용자 암호가 만료 되지 않도록 설정 하 고 90 일을 경과 하면 암호가 만료 됩니다. `pwdLastSet` 특성을 기반으로 만료 `-PasswordPolicies None`를 변경 하면 다음에 로그인 할 때 사용자가 해당 90 `pwdLastSet` 암호를 변경 해야 합니다. 이 변경으로 인해 많은 사용자에 게 영향을 줄 수 있습니다.

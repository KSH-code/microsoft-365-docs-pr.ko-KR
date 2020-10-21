---
title: 개별 사용자 암호가 만료되지 않도록 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell을 사용 하 여 일부 개별 사용자 암호가 만료 되지 않도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 9497dfb5793ddbfc3d6845ec1efba91ad972ea38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646658"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>개별 사용자 암호가 만료되지 않도록 설정

이 문서에서는 개별 사용자의 암호가 만료 되지 않도록 설정 하는 방법에 대해 설명 합니다. PowerShell을 사용 하 여 이러한 단계를 완료 해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다. 이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다. [관리자 계정의 새로운 기능](../admin-overview/admin-overview.md) 

이 단계를 수행 하려면 [전역 관리자 또는 암호 관리자](about-admin-roles.md) 여야 합니다.

Microsoft 클라우드 서비스에 대 한 전역 관리자는 [Graph 용 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 을 사용 하 여 특정 사용자에 대해 암호가 만료 되지 않도록 설정할 수 있습니다. [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet을 사용 하 여 만료 되지 않은 구성을 제거 하거나 만료 되지 않도록 설정 된 사용자 암호를 확인할 수도 있습니다.

이 가이드는 id 및 디렉터리 서비스에 대 한 Azure AD도 사용 하는 Intune 및 Microsoft 365 같은 다른 공급자에 적용 됩니다. 정책에서 변경 가능한 유일한 부분은 암호 만료입니다.

> [!NOTE]
> 디렉터리 동기화를 통해 동기화 되지 않은 사용자 계정의 암호만 만료 되지 않도록 구성할 수 있습니다. 디렉터리 동기화에 대 한 자세한 내용은 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)를 참조 하십시오.

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>암호에 대 한 만료 정책을 확인 하는 방법

AzureAD 모듈의 Get-AzureADUser 명령에 대 한 자세한 내용은 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)참조 문서를 참조 하세요.

다음 명령 중 하나를 실행합니다.

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

- 이름이 **ReportPasswordNeverExpires.html** 인 현재 사용자의 데스크톱에서 Html로 PasswordNeverExpires가 있는 모든 사용자의 보고서를 가져오려면

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 이름이 **ReportPasswordNeverExpires.csv** 인 현재 사용자의 데스크톱에서 CSV에 PasswordNeverExpires이 있는 모든 사용자의 보고서를 가져오려면

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 조직의 모든 사용자에 대 한 암호가 만료 되지 않도록 설정 하려면 다음 cmdlet을 실행 합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a>암호가 만료 되도록 설정

다음 명령 중 하나를 실행합니다.

- 암호가 만료 되도록 한 명의 사용자에 대 한 암호를 설정 하려면 UPN 또는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 조직의 모든 사용자에 대 한 암호를 설정 하 여 만료 되도록 하려면 다음 cmdlet을 사용 합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> 매개 변수를 사용 하 여 구성 된 사용자 계정은 `-PasswordPolicies DisablePasswordExpiration` 사용자 계정 특성에 따라 여전히 age로 설정 `pwdLastSet` 됩니다. 예를 들어 사용자 암호가 만료 되지 않도록 설정 하 고 90 일이 하 이면 암호가 만료 됨을 유지 합니다. `pwdLastSet`사용자 계정 특성을 기반으로 매개 변수를 사용 하 여 구성 된 사용자 계정에 대해 `-PasswordPolicies None` , `pwdLastSet` 90 일 보다 오래 된 모든 암호는 사용자가 다음에 로그인 할 때 변경 해야 합니다. 이 변경으로 인해 많은 사용자에 게 영향을 줄 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)

[암호 초기화](../add-users/reset-passwords.md)
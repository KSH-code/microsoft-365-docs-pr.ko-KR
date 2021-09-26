---
title: 사용자 암호를 만료 기한 제한 없음으로 설정
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Microsoft 365 사용하여 일부 개별 사용자 암호를 만료하지 못하도록 설정하려면 Windows PowerShell.
ms.openlocfilehash: 8574571564ddfd98e5a5cfe7c232353e0d82f85c
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775303"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>사용자 암호를 만료 기한 제한 없음으로 설정

이 문서에서는 개별 사용자의 암호가 만료되지 못하도록 설정하는 방법을 설명합니다. PowerShell을 사용하여 이러한 단계를 완료해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다. 이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다. [관리자 계정의 새로운 기능](../../business-video/admin-center-overview.md)

이러한 단계를 [수행하려면](about-admin-roles.md) 전역 관리자 또는 암호 관리자 되어야 합니다.

Microsoft 클라우드 서비스의 전역 관리자는 Azure Active Directory [PowerShell을](/powershell/azure/active-directory/install-adv2) 사용하여 특정 Graph 암호를 만료하지 못하도록 설정할 수 있습니다. [AzureAD](/powershell/module/Azuread) cmdlet을 사용하여 만료되지 않는 구성을 제거하거나 만료되지 않는 것으로 설정된 사용자 암호를 볼 수도 있습니다.

이 가이드는 Id 및 디렉터리 서비스에 대해 Azure AD를 Microsoft 365 Intune 및 Microsoft 365 같은 다른 공급자에 적용됩니다. 암호 만료는 변경할 수 있는 정책의 유일한 부분입니다.


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>만료 정책에서 암호를 검사하는 방법

AzureAD 모듈의 Get-AzureADUser 명령에 대한 자세한 내용은 참조 문서 [Get-AzureADUser를 참조하세요.](/powershell/module/Azuread/Get-AzureADUser)

다음 명령 중 하나를 실행합니다.

- 단일 사용자의 암호가 만료되지 않는 것으로 설정되어 있는 경우 확인하려는 사용자의 UPN(예: user@contoso.onmicrosoft.com) 또는 사용자 ID를 사용하여 다음 cmdlet을 *실행합니다.*

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

- 모든 사용자에 **대한 암호** 사용 기간 만료 안 기간 설정 확인을 위해 다음 cmdlet을 실행합니다.

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 이름이 같은 현재 사용자의 바탕 화면에서 Html로 PasswordNeverExpires를 사용하는 모든 사용자에 대한  **보고서를ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- 이름이 같은 현재 사용자의 바탕 화면에서 CSV에 PasswordNeverExpires가 있는 모든 사용자에 대한 **보고서를ReportPasswordNeverExpires.csv**

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

- 조직의 모든 사용자의 암호를 만료하지 못하게 설정하기 위해 다음 cmdlet을 실행합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> 매개 변수로 구성된 `-PasswordPolicies DisablePasswordExpiration` 사용자 계정은 특성에 따라 계속 남아 `pwdLastSet` 있습니다. 특성에 따라 만료를 로 변경하는 경우 `pwdLastSet` pwdLastSet이 90일보다 오래된 모든 암호는 사용자가 다음에 로그인할 때 해당 암호를 변경해야 `-PasswordPolicies None` 합니다. 이 변경은 많은 수의 사용자에게 영향을 줄 수 있습니다.

### <a name="set-a-password-to-expire"></a>암호가 만료될 수 있습니다.

다음 명령 중 하나를 실행합니다.

- 암호가 만료될 수 있도록 한 사용자의 암호를 설정하기 위해 사용자의 UPN 또는 사용자 ID를 사용하여 다음 cmdlet을 실행합니다.

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 조직에 있는 모든 사용자의 암호를 만료할 수 있도록 설정하기 위해 다음 cmdlet을 사용하세요.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>관련 콘텐츠

[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)(문서)\
[암호 다시 설정](../add-users/reset-passwords.md)(문서)\
[조직의 암호 만료 정책](../manage/set-password-expiration-policy.md) 설정(문서)

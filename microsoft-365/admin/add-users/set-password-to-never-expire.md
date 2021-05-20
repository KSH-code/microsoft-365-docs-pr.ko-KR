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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Microsoft 365 관리자 계정에 로그인하여 Windows PowerShell 사용하여 만료되지 않는 일부 개별 사용자 암호를 설정합니다.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571928"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>사용자 암호를 만료 기한 제한 없음으로 설정

이 문서에서는 개별 사용자가 만료되지 않도록 암호를 설정하는 방법을 설명합니다. PowerShell을 사용하여 이러한 단계를 완료해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다. 이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다. [관리자 계정의 새로운 기능](../../business-video/admin-center-overview.md) 

이러한 단계를 수행하려면 [전역 관리자 또는 암호 관리자여야](about-admin-roles.md) 합니다.

Microsoft 클라우드 서비스의 글로벌 관리자는 [Azure Active Directory PowerShell을](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 사용하여 Graph 위해 특정 사용자에 대해 만료되지 않도록 암호를 설정할 수 있습니다. [AzureAD](/powershell/module/Azuread) cmdlet을 사용하여 만료되지 않은 구성을 제거하거나 만료되지 않는 사용자 암호를 확인할 수도 있습니다.

이 가이드는 Intune 및 Microsoft 365 같은 다른 공급자에 적용되며, ID 및 디렉터리 서비스에 대한 Azure AD에도 의존합니다. 암호 만료는 변경할 수 있는 정책의 유일한 부분입니다.

> [!NOTE]
> 디렉터리 동기화를 통해 동기화되지 않은 사용자 계정의 암호만 만료되지 않도록 구성할 수 있습니다. 디렉터리 동기화에 대한 자세한 내용은 [Azure AD를 커넥트 AD를](/azure/active-directory/connect/active-directory-aadconnect)참조하십시오.

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>만료 정책을 암호로 확인하는 방법

AzureAD 모듈의 Get-AzureADUser 명령에 대한 자세한 내용은 참조 문서 [Get-AzureADUser를](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)참조하십시오.

다음 명령 중 하나를 실행합니다.

- 단일 사용자의 암호가 만료되지 않도록 설정되어 있는지 확인하려면 UPN(예: *user@contoso.onmicrosoft.com)* 또는 확인하려는 사용자의 사용자 ID를 사용하여 다음 cmdlet을 실행합니다.

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

- 모든 사용자에 대해 **암호가 설정이 만료되지 않도록** 하려면 다음 cmdlet을 실행합니다.

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- PasswordNever를 가진 모든 사용자의 보고서를 얻으려면 현재 사용자의 바탕 화면에 html로  **ReportPasswordNeverExpires.htm만료됩니다.**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- PasswordNever를 가진 모든 사용자의 보고서를 얻으려면 **ReportPasswordNeverExpires.csv**

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

- 조직의 모든 사용자의 암호를 만료되지 않도록 설정하려면 다음 cmdlet을 실행합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> 특성에 따라 매개 변수로 구성된 사용자 계정은 `-PasswordPolicies DisablePasswordExpiration` 여전히 세로 나이를 `pwdLastSet` 사용합니다. 특성에 따라 `pwdLastSet` 만료를 `-PasswordPolicies None` 90일 이상 이전pdLastSet이 있는 모든 암호는 사용자가 다음에 로그인할 때 변경해야 합니다. 이 변경 사항은 많은 수의 사용자에게 영향을 줄 수 있습니다.

### <a name="set-a-password-to-expire"></a>만료되는 암호 설정

다음 명령 중 하나를 실행합니다.

- 암호가 만료되도록 한 사용자의 암호를 설정하려면 UPN 또는 사용자의 사용자 ID를 사용하여 다음 cmdlet을 실행합니다.

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 조직의 모든 사용자의 암호를 만료되도록 설정하려면 다음 cmdlet을 사용합니다.

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>관련 콘텐츠

[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)(문서)

[암호 다시 설정](../add-users/reset-passwords.md)(문서)
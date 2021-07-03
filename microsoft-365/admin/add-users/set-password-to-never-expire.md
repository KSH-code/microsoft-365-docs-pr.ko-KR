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
description: Microsoft 365 사용하여 일부 개별 사용자 암호를 만료하지 못하도록 설정하려면 Windows PowerShell.
ms.openlocfilehash: a0b247f4b736ecccab57398e1e7131f0a06a2958
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286276"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="559da-103">사용자 암호를 만료 기한 제한 없음으로 설정</span><span class="sxs-lookup"><span data-stu-id="559da-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="559da-104">이 문서에서는 개별 사용자의 암호가 만료되지 못하도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="559da-105">PowerShell을 사용하여 이러한 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="559da-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="559da-106">Before you begin</span></span>

<span data-ttu-id="559da-107">회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="559da-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="559da-108">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="559da-109">[관리자 계정의 새로운 기능](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="559da-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="559da-110">이러한 단계를 [수행하려면](about-admin-roles.md) 전역 관리자 또는 암호 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="559da-111">Microsoft 클라우드 서비스의 전역 관리자는 Azure Active Directory [PowerShell을](/powershell/azure/active-directory/install-adv2) 사용하여 특정 Graph 암호를 만료하지 못하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="559da-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="559da-112">[AzureAD](/powershell/module/Azuread) cmdlet을 사용하여 만료되지 않는 구성을 제거하거나 만료되지 않는 것으로 설정된 사용자 암호를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="559da-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="559da-113">이 가이드는 Id 및 디렉터리 서비스에 대해 Azure AD를 Microsoft 365 Intune 및 Microsoft 365 같은 다른 공급자에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="559da-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="559da-114">암호 만료는 변경할 수 있는 정책의 유일한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="559da-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="559da-115">디렉터리 동기화를 통해 동기화되지 않은 사용자 계정의 암호만 만료되지되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="559da-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="559da-116">디렉터리 동기화에 대한 자세한 내용은 Azure [AD를 커넥트 AD를 참조하세요.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="559da-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="559da-117">만료 정책에서 암호를 검사하는 방법</span><span class="sxs-lookup"><span data-stu-id="559da-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="559da-118">AzureAD 모듈의 Get-AzureADUser 명령에 대한 자세한 내용은 참조 문서 [Get-AzureADUser를 참조하세요.](/powershell/module/Azuread/Get-AzureADUser)</span><span class="sxs-lookup"><span data-stu-id="559da-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).</span></span>

<span data-ttu-id="559da-119">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-119">Run one of the following commands:</span></span>

- <span data-ttu-id="559da-120">단일 사용자의 암호가 만료되지 않는 것으로 설정되어 있는 경우 확인하려는 사용자의 UPN(예: user@contoso.onmicrosoft.com) 또는 사용자 ID를 사용하여 다음 cmdlet을 *실행합니다.*</span><span class="sxs-lookup"><span data-stu-id="559da-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="559da-121">예제:</span><span class="sxs-lookup"><span data-stu-id="559da-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

- <span data-ttu-id="559da-122">모든 사용자에 **대한 암호** 사용 기간 만료 안 기간 설정 확인을 위해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="559da-123">이름이 l인 현재 사용자의 바탕 화면에서 Html로 PasswordNeverExpires를 사용하는 모든 사용자에  **대한ReportPasswordNeverExpires.htm**</span><span class="sxs-lookup"><span data-stu-id="559da-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- <span data-ttu-id="559da-124">이름이 같은 현재 사용자의 바탕 화면에서 CSV에 PasswordNeverExpires가 있는 모든 사용자에 대한 **보고서를ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="559da-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="559da-125">조직의 모든 사용자의 암호를 만료하지 못하게 설정하기 위해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="559da-126">매개 변수로 구성된 `-PasswordPolicies DisablePasswordExpiration` 사용자 계정은 특성에 따라 계속 남아 `pwdLastSet` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="559da-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="559da-127">특성에 따라 만료를 로 변경하는 경우 `pwdLastSet` pwdLastSet이 90일보다 오래된 모든 암호는 사용자가 다음에 로그인할 때 해당 암호를 변경해야 `-PasswordPolicies None` 합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="559da-128">이 변경은 많은 수의 사용자에게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="559da-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="559da-129">암호가 만료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="559da-129">Set a password to expire</span></span>

<span data-ttu-id="559da-130">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-130">Run one of the following commands:</span></span>

- <span data-ttu-id="559da-131">암호가 만료될 수 있도록 한 사용자의 암호를 설정하기 위해 사용자의 UPN 또는 사용자 ID를 사용하여 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="559da-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="559da-132">조직에 있는 모든 사용자의 암호를 만료할 수 있도록 설정하기 위해 다음 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="559da-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="559da-133">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="559da-133">Related content</span></span>

<span data-ttu-id="559da-134">[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="559da-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="559da-135">[암호 다시 설정](../add-users/reset-passwords.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="559da-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="559da-136">[조직의 암호 만료 정책](../manage/set-password-expiration-policy.md) 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="559da-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>
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
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="c7c55-103">사용자 암호를 만료 기한 제한 없음으로 설정</span><span class="sxs-lookup"><span data-stu-id="c7c55-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="c7c55-104">이 문서에서는 개별 사용자가 만료되지 않도록 암호를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="c7c55-105">PowerShell을 사용하여 이러한 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c7c55-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c7c55-106">Before you begin</span></span>

<span data-ttu-id="c7c55-107">회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="c7c55-108">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="c7c55-109">[관리자 계정의 새로운 기능](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c7c55-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="c7c55-110">이러한 단계를 수행하려면 [전역 관리자 또는 암호 관리자여야](about-admin-roles.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="c7c55-111">Microsoft 클라우드 서비스의 글로벌 관리자는 [Azure Active Directory PowerShell을](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 사용하여 Graph 위해 특정 사용자에 대해 만료되지 않도록 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="c7c55-112">[AzureAD](/powershell/module/Azuread) cmdlet을 사용하여 만료되지 않은 구성을 제거하거나 만료되지 않는 사용자 암호를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="c7c55-113">이 가이드는 Intune 및 Microsoft 365 같은 다른 공급자에 적용되며, ID 및 디렉터리 서비스에 대한 Azure AD에도 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="c7c55-114">암호 만료는 변경할 수 있는 정책의 유일한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="c7c55-115">디렉터리 동기화를 통해 동기화되지 않은 사용자 계정의 암호만 만료되지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="c7c55-116">디렉터리 동기화에 대한 자세한 내용은 [Azure AD를 커넥트 AD를](/azure/active-directory/connect/active-directory-aadconnect)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7c55-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="c7c55-117">만료 정책을 암호로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="c7c55-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="c7c55-118">AzureAD 모듈의 Get-AzureADUser 명령에 대한 자세한 내용은 참조 문서 [Get-AzureADUser를](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7c55-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="c7c55-119">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-119">Run one of the following commands:</span></span>

- <span data-ttu-id="c7c55-120">단일 사용자의 암호가 만료되지 않도록 설정되어 있는지 확인하려면 UPN(예: *user@contoso.onmicrosoft.com)* 또는 확인하려는 사용자의 사용자 ID를 사용하여 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="c7c55-121">예제:</span><span class="sxs-lookup"><span data-stu-id="c7c55-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="c7c55-122">모든 사용자에 대해 **암호가 설정이 만료되지 않도록** 하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="c7c55-123">PasswordNever를 가진 모든 사용자의 보고서를 얻으려면 현재 사용자의 바탕 화면에 html로  **ReportPasswordNeverExpires.htm만료됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c7c55-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="c7c55-124">PasswordNever를 가진 모든 사용자의 보고서를 얻으려면 **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="c7c55-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="c7c55-125">조직의 모든 사용자의 암호를 만료되지 않도록 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="c7c55-126">특성에 따라 매개 변수로 구성된 사용자 계정은 `-PasswordPolicies DisablePasswordExpiration` 여전히 세로 나이를 `pwdLastSet` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="c7c55-127">특성에 따라 `pwdLastSet` 만료를 `-PasswordPolicies None` 90일 이상 이전pdLastSet이 있는 모든 암호는 사용자가 다음에 로그인할 때 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="c7c55-128">이 변경 사항은 많은 수의 사용자에게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="c7c55-129">만료되는 암호 설정</span><span class="sxs-lookup"><span data-stu-id="c7c55-129">Set a password to expire</span></span>

<span data-ttu-id="c7c55-130">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-130">Run one of the following commands:</span></span>

- <span data-ttu-id="c7c55-131">암호가 만료되도록 한 사용자의 암호를 설정하려면 UPN 또는 사용자의 사용자 ID를 사용하여 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="c7c55-132">조직의 모든 사용자의 암호를 만료되도록 설정하려면 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c55-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="c7c55-133">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="c7c55-133">Related content</span></span>

<span data-ttu-id="c7c55-134">[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="c7c55-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="c7c55-135">[암호 다시 설정](../add-users/reset-passwords.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="c7c55-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>
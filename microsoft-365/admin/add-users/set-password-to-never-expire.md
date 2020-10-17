---
title: 개별 사용자 암호가 만료되지 않도록 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell을 사용 하 여 일부 개별 사용자 암호가 만료 되지 않도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580919"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="f6701-103">개별 사용자 암호가 만료되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f6701-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="f6701-104">이 문서에서는 개별 사용자의 암호가 만료 되지 않도록 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="f6701-105">PowerShell을 사용 하 여 이러한 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f6701-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="f6701-106">Before you begin</span></span>

<span data-ttu-id="f6701-107">회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f6701-108">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="f6701-109">[관리자 계정의 새로운 기능](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f6701-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="f6701-110">이 단계를 수행 하려면 [전역 관리자 또는 암호 관리자](about-admin-roles.md) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="f6701-111">Microsoft 클라우드 서비스에 대 한 전역 관리자는 [Graph 용 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 을 사용 하 여 특정 사용자에 대해 암호가 만료 되지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="f6701-112">[AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet을 사용 하 여 만료 되지 않은 구성을 제거 하거나 만료 되지 않도록 설정 된 사용자 암호를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="f6701-113">이 가이드는 id 및 디렉터리 서비스에 대 한 Azure AD도 사용 하는 Intune 및 Microsoft 365 같은 다른 공급자에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="f6701-114">정책에서 변경 가능한 유일한 부분은 암호 만료입니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="f6701-115">디렉터리 동기화를 통해 동기화 되지 않은 사용자 계정의 암호만 만료 되지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="f6701-116">디렉터리 동기화에 대 한 자세한 내용은 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6701-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="f6701-117">암호에 대 한 만료 정책을 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="f6701-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="f6701-118">AzureAD 모듈의 Get-AzureADUser 명령에 대 한 자세한 내용은 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)참조 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6701-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="f6701-119">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-119">Run one of the following commands:</span></span>

- <span data-ttu-id="f6701-120">단일 사용자의 암호가 만료 되지 않도록 설정 되어 있는지 확인 하려면 UPN (예: *user@contoso.onmicrosoft.com*) 또는 확인 하려는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="f6701-121">예제:</span><span class="sxs-lookup"><span data-stu-id="f6701-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="f6701-122">모든 사용자에 대 한 **암호 사용 기간 제한 없음** 설정을 보려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="f6701-123">이름이 **ReportPasswordNeverExpires.html** 인 현재 사용자의 데스크톱에서 Html로 PasswordNeverExpires가 있는 모든 사용자의 보고서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="f6701-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="f6701-124">이름이 **ReportPasswordNeverExpires.csv** 인 현재 사용자의 데스크톱에서 CSV에 PasswordNeverExpires이 있는 모든 사용자의 보고서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="f6701-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="f6701-125">조직의 모든 사용자에 대 한 암호가 만료 되지 않도록 설정 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="f6701-126">암호가 만료 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="f6701-126">Set a password to expire</span></span>

<span data-ttu-id="f6701-127">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-127">Run one of the following commands:</span></span>

- <span data-ttu-id="f6701-128">암호가 만료 되도록 한 명의 사용자에 대 한 암호를 설정 하려면 UPN 또는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="f6701-129">조직의 모든 사용자에 대 한 암호를 설정 하 여 만료 되도록 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="f6701-130">매개 변수를 사용 하 여 구성 된 사용자 계정은 `-PasswordPolicies DisablePasswordExpiration` 사용자 계정 특성에 따라 여전히 age로 설정 `pwdLastSet` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="f6701-131">예를 들어 사용자 암호가 만료 되지 않도록 설정 하 고 90 일이 하 이면 암호가 만료 됨을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="f6701-132">`pwdLastSet`사용자 계정 특성을 기반으로 매개 변수를 사용 하 여 구성 된 사용자 계정에 대해 `-PasswordPolicies None` , `pwdLastSet` 90 일 보다 오래 된 모든 암호는 사용자가 다음에 로그인 할 때 변경 해야 합니다. 이 변경으로 인해 많은 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6701-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="f6701-133">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f6701-133">Related content</span></span>

[<span data-ttu-id="f6701-134">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="f6701-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="f6701-135">암호 초기화</span><span class="sxs-lookup"><span data-stu-id="f6701-135">Reset passwords</span></span>](../add-users/reset-passwords.md)
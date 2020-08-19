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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell을 사용 하 여 일부 개별 사용자 암호가 만료 되지 않도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804211"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="de385-103">개별 사용자 암호가 만료되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="de385-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="de385-104">조직의 암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="de385-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="de385-105">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">설정</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="de385-106">설정 페이지 맨 위에서 **보안 & 개인 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="de385-107">**암호 만료 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="de385-108">암호가 만료 되지 않도록 설정 되어 있는 경우 **사용자 암호가 일 후에 만료 되도록 설정**옆의 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="de385-109">암호가 만료 될 때 까지의 기간 (일)을 지정 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de385-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="de385-110">개별 사용자에 대 한 암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="de385-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="de385-111">Microsoft 클라우드 서비스에 대 한 전역 관리자는 [Graph 용 Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 을 사용 하 여 특정 사용자에 대해 암호가 만료 되지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de385-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="de385-112">[AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet을 사용 하 여 만료 되지 않은 구성을 제거 하거나 만료 되지 않도록 설정 된 사용자 암호를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de385-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="de385-113">이 가이드는 id 및 디렉터리 서비스에 대 한 Azure AD도 사용 하는 Intune 및 Microsoft 365 같은 다른 공급자에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de385-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="de385-114">정책에서 변경 가능한 유일한 부분은 암호 만료입니다.</span><span class="sxs-lookup"><span data-stu-id="de385-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="de385-115">Graph 용 Azure AD PowerShell에 대 한 자세한 내용은 [Azure Active Directory PowerShell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de385-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="de385-116">디렉터리 동기화를 통해 동기화 되지 않은 사용자 계정의 암호만 만료 되지 않도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de385-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="de385-117">디렉터리 동기화에 대 한 자세한 내용은 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="de385-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="de385-118">암호에 대 한 만료 정책을 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="de385-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="de385-119">AzureAD 모듈의 AzureADUser 명령에 대 한 자세한 내용은 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)를 참조 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de385-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="de385-120">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-120">Run one of the following commands:</span></span>

- <span data-ttu-id="de385-121">단일 사용자의 암호가 만료 되지 않도록 설정 되어 있는지 확인 하려면 UPN (예: *user@contoso.onmicrosoft.com*) 또는 확인 하려는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="de385-122">예제:</span><span class="sxs-lookup"><span data-stu-id="de385-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="de385-123">모든 사용자에 대 한 **암호 사용 기간 제한 없음** 설정을 보려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="de385-124">이름이 **ReportPasswordNeverExpires.html** 인 현재 사용자의 데스크톱에서 Html로 PasswordNeverExpires가 있는 모든 사용자의 보고서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="de385-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="de385-125">이름이 **ReportPasswordNeverExpires.csv** 인 현재 사용자의 데스크톱에서 CSV에 PasswordNeverExpires이 있는 모든 사용자의 보고서를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="de385-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="de385-126">암호가 만료 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="de385-126">Set a password to expire</span></span>

<span data-ttu-id="de385-127">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-127">Run one of the following commands:</span></span>

- <span data-ttu-id="de385-128">암호가 만료 되도록 한 명의 사용자에 대 한 암호를 설정 하려면 UPN 또는 사용자의 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="de385-129">조직의 모든 사용자에 대 한 암호를 설정 하 여 만료 되도록 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="de385-130">암호가 만료 되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="de385-130">Set a password to never expire</span></span>

<span data-ttu-id="de385-131">다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-131">Run one of the following commands:</span></span>

- <span data-ttu-id="de385-132">한 사용자의 암호가 만료 되지 않도록 설정 하려면 사용자의 UPN 또는 사용자 ID를 사용 하 여 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="de385-133">조직의 모든 사용자에 대 한 암호가 만료 되지 않도록 설정 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="de385-134">매개 변수를 사용 하 여 구성 된 사용자 계정은 `-PasswordPolicies DisablePasswordExpiration` 사용자 계정 특성에 따라 여전히 age로 설정 `pwdLastSet` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de385-134">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="de385-135">예를 들어 사용자 암호가 만료 되지 않도록 설정 하 고 90 일이 하 이면 암호가 만료 됨을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="de385-135">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="de385-136">`pwdLastSet`사용자 계정 특성을 기반으로 매개 변수를 사용 하 여 구성 된 사용자 계정에 대해 `-PasswordPolicies None` , `pwdLastSet` 90 일 보다 오래 된 모든 암호는 사용자가 다음에 로그인 할 때 변경 해야 합니다. 이 변경으로 인해 많은 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de385-136">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

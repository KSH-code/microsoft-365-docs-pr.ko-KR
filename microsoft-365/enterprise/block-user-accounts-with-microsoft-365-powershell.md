---
title: PowerShell을 Microsoft 365 사용자 계정 차단
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287224"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="ca15d-103">PowerShell을 Microsoft 365 사용자 계정 차단</span><span class="sxs-lookup"><span data-stu-id="ca15d-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="ca15d-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ca15d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ca15d-105">Microsoft 365 계정에 대한 액세스를 차단하면 모든 사용자가 계정을 사용하여 로그인하고 조직에 있는 서비스 및 데이터에 액세스할 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="ca15d-106">PowerShell을 사용하여 개별 또는 여러 사용자 계정에 대한 액세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ca15d-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="ca15d-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ca15d-108">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ca15d-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="ca15d-109">개별 사용자 계정에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="ca15d-109">Block access to individual user accounts</span></span>

<span data-ttu-id="ca15d-110">다음 구문을 사용하여 개별 사용자 계정을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-110">Use the following syntax to block an individual user account:</span></span>

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="ca15d-111">**Set-AzureAD** cmdlet의 *-ObjectID* 매개 변수는 계정 로그인 이름(사용자 계정 이름)이나 계정의 개체 ID를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>

<span data-ttu-id="ca15d-112">이 예에서는 의 사용자 계정에 대한 액세스를 *fabricec@litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="ca15d-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="ca15d-113">사용자 계정을 차단 해제하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-113">To unblock this user account, run the following command:</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="ca15d-114">사용자의 표시 이름을 기준으로 사용자 계정 UPN을 표시하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ca15d-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="ca15d-115">이 예에서는 사용자  *Caleb Sills의* 사용자 계정 UPN을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ca15d-116">사용자의 표시 이름을 기준으로 계정을 차단하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ca15d-116">To block an account based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="ca15d-117">사용자 계정의 차단 상태를 확인하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ca15d-117">To check the blocked status of a user account use the following command:</span></span>

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="ca15d-118">여러 사용자 계정 차단</span><span class="sxs-lookup"><span data-stu-id="ca15d-118">Block multiple user accounts</span></span>

<span data-ttu-id="ca15d-119">여러 사용자 계정에 대한 액세스를 차단하려면 각 줄에 계정 로그인 이름이 하나씩 포함된 텍스트 파일을 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="ca15d-120">다음 명령에서 예제 텍스트 파일은 *C:\My Documents\Accounts.txt.*</span><span class="sxs-lookup"><span data-stu-id="ca15d-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="ca15d-121">이 파일 이름을 텍스트 파일의 경로와 파일 이름으로 바니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-121">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="ca15d-122">텍스트 파일에 나열 된 계정에 대 한 액세스를 차단 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-122">To block access to the accounts listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

<span data-ttu-id="ca15d-123">텍스트 파일에 나열된 계정의 차단을 해제하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ca15d-124">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="ca15d-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ca15d-125">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ca15d-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="block-individual-user-accounts"></a><span data-ttu-id="ca15d-126">개별 사용자 계정 차단</span><span class="sxs-lookup"><span data-stu-id="ca15d-126">Block individual user accounts</span></span>

<span data-ttu-id="ca15d-127">다음 구문을 사용하여 개별 사용자 계정에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-127">Use the following syntax to block access for an individual user account:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="ca15d-128">PowerShell Core는 이름에 *Msol이* Microsoft Azure Active Directory cmdlet을 Windows PowerShell 모듈용 Windows PowerShell 모듈을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="ca15d-129">이러한 cmdlet은 해당 cmdlet에서 실행해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca15d-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="ca15d-130">이 예에서는 사용자 계정 fabricec 및 에 대한 액세스를 *\@ litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="ca15d-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="ca15d-131">사용자 계정 차단 해제 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-131">To unblock the user account, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="ca15d-132">사용자 계정의 차단 상태를 확인하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-132">To check the blocked status of a user account run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="ca15d-133">여러 사용자 계정에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="ca15d-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="ca15d-134">먼저, 각 줄에 계정이 하나씩 포함된 텍스트 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-134">First, create a text file that contains one account on each line like this:</span></span>

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="ca15d-135">다음 명령에서 예제 텍스트 파일은 *C:\My Documents\Accounts.txt.*</span><span class="sxs-lookup"><span data-stu-id="ca15d-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="ca15d-136">이 파일 이름을 텍스트 파일의 경로와 파일 이름으로 바니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-136">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="ca15d-137">텍스트 파일에 나열된 계정에 대한 액세스를 차단하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="ca15d-138">텍스트 파일에 나열 된 계정 차단 해제 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca15d-138">To unblock the accounts listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="ca15d-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca15d-139">See also</span></span>

[<span data-ttu-id="ca15d-140">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="ca15d-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="ca15d-141">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="ca15d-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="ca15d-142">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="ca15d-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

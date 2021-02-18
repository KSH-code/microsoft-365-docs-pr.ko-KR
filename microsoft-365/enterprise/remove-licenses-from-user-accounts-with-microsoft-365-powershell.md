---
title: PowerShell을 사용하여 사용자 계정에서 Microsoft 365 라이선스 제거
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: PowerShell을 사용하여 이전에 사용자에게 할당된 Microsoft 365 라이선스를 제거하는 방법을 설명 합니다.
ms.openlocfilehash: 8ae7ca1013e26a60f16177f2dab7ced4cc8b97a8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289596"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="a326a-103">PowerShell을 사용하여 사용자 계정에서 Microsoft 365 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="a326a-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="a326a-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="a326a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="a326a-105">Microsoft 365 관리 [센터를](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) 사용하여 사용자 계정에서 라이선스를 제거하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-105">[Learn how to remove licenses from user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="a326a-106">추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="a326a-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a326a-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="a326a-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a326a-108">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="a326a-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="a326a-109">다음으로, 이 명령을 사용하여 테넌트의 라이선스 계획을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="a326a-110">다음으로 라이선스를 제거할 계정의 로그인 이름을 UPN(사용자 계정 이름)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="a326a-111">마지막으로 사용자 로그인 및 라이선스 계획 이름을 지정하고 ,"<" 및 ">" 문자를 제거한 다음 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="a326a-112">특정 사용자 계정에 대한 모든 라이선스를 제거하려면 사용자 로그인 이름을 지정하고 "<" 및 ">" 문자를 제거한 다음 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a326a-113">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="a326a-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a326a-114">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a326a-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="a326a-115">라이센스 계획 (**AccountSkuID**) 조직에 대 한 정보는 다음 항목을 참조.</span><span class="sxs-lookup"><span data-stu-id="a326a-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="a326a-116">PowerShell을 통해 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="a326a-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="a326a-117">PowerShell을 통해 계정 라이선스 및 서비스 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a326a-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="a326a-118">_-All_ 매개 변수를 사용하지 않고 **Get-MsolUser** cmdlet을 사용하는 경우 처음 500개의 계정만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="a326a-119">사용자 계정에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="a326a-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="a326a-120">기존 사용자 계정에서 라이센스를 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="a326a-121">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="a326a-122">이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="a326a-123">이 예에서는 사용자 계정에서 **litwareinc:ENTERPRISEPACK(Office** 365 Enterprise E3) 라이선스를 BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a326a-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="a326a-124">이 cmdlet을 사용하여 취소된 라이선스에서 사용자를 `Set-MsolUserLicense` 예약 *취소할* 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="a326a-125">Microsoft 365 관리 센터의 각 사용자 계정에 대해 개별적으로 이 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="a326a-126">기존 라이선스 사용자 그룹에서 모든 라이선스를 제거하려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="a326a-127">**기존 계정 특성을 기준으로 계정 필터링** 이 작업을 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="a326a-128">이 예에서는 미국 판매 부서의 모든 사용자 계정에서 모든 라이선스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="a326a-129">**특정 라이선스에 대해 특정 계정 목록 사용** 이 작업을 수행하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="a326a-130">만들고 다음과 같이 각 줄에 한 계정에 포함 된 텍스트 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="a326a-131">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="a326a-132">이 예에서는 텍스트 파일 C:\My Documents\Accounts.txt에 정의된 사용자 계정에서 **litwareinc:ENTERPRISEPACK(Office** 365 Enterprise E3) 라이선스를 Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="a326a-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="a326a-133">모든 기존 사용자 계정에서 모든 라이선스를 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="a326a-134">라이선스를 회수하는 또 다른 방법은 사용자 계정을 삭제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a326a-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="a326a-135">자세한 내용은 PowerShell을 통해 사용자 계정 삭제 및 [복원을 참조하세요.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a326a-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a326a-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a326a-136">See also</span></span>

[<span data-ttu-id="a326a-137">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="a326a-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a326a-138">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="a326a-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a326a-139">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="a326a-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)


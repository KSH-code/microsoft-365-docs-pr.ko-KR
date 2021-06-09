---
title: PowerShell을 Microsoft 365 계정 라이선스 및 서비스 세부 정보 보기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: PowerShell을 사용하여 사용자에게 할당된 Microsoft 365 서비스를 확인하는 방법에 대해 설명
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692881"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="14d96-103">PowerShell을 Microsoft 365 계정 라이선스 및 서비스 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="14d96-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="14d96-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="14d96-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="14d96-105">Microsoft 365 라이선스 계획(SKUS 또는 Microsoft 365 계획이라고도 하는 라이선스)을 통해 사용자는 해당 계획에 대해 정의된 Microsoft 365 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="14d96-106">그러나 사용자는 현재 할당된 라이선스에서 사용할 수 있는 모든 서비스에 액세스하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="14d96-107">PowerShell을 사용하여 사용자 Microsoft 365 서비스 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="14d96-108">라이선스 계획, 라이선스 및 서비스에 대한 자세한 내용은 PowerShell을 통해 라이선스 및 서비스 [보기를 참조하세요.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="14d96-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="14d96-109">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="14d96-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="14d96-110">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="14d96-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="14d96-111">다음으로, 이 명령을 사용하여 테넌트에 대한 라이선스 계획을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="14d96-112">다음 명령을 사용하여 각 라이선스 계획에서 사용할 수 있는 서비스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-112">Use these commands to list the services that are available in each licensing plan.</span></span>

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

<span data-ttu-id="14d96-113">다음 명령을 사용하여 사용자 계정에 할당된 라이선스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="14d96-114">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="14d96-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="14d96-115">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="14d96-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="14d96-116">다음으로, 이 명령을 실행하여 조직에서 사용할 수 있는 라이선스 계획을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="14d96-117">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="14d96-118">이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="14d96-119">그런 다음 이 명령을 실행하여 각 라이선스 계획에서 사용할 수 있는 서비스와 서비스가 나열되는 순서(인덱스 번호)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="14d96-120">이 명령을 사용하여 사용자에게 할당된 라이선스와 라이선스가 나열되는 순서(인덱스 번호)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="14d96-121">사용자 계정에 대한 서비스를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="14d96-121">To view services for a user account</span></span>

<span data-ttu-id="14d96-122">사용자가 액세스할 수 있는 Microsoft 365 모든 서비스 보기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="14d96-123">이 예에서는 사용자가 액세스할 수 있는 BelindaN@litwareinc.com 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="14d96-124">사용자의 계정에 할당된 모든 라이선스와 관련된 서비스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="14d96-125">이 예제에서는 사용자 BelindaN@litwareinc.com이 계정에 할당된 첫 번째 라이선스(인덱스 번호: 0)에서 액세스할 수 있는 서비스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="14d96-126">여러 라이선스가 할당된 사용자에 대한 모든 서비스를 보고 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d96-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a><span data-ttu-id="14d96-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14d96-127">See also</span></span>

[<span data-ttu-id="14d96-128">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="14d96-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="14d96-129">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="14d96-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="14d96-130">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="14d96-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

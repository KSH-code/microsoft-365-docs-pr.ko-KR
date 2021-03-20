---
title: PowerShell을 통해 사용자 계정에 Microsoft 365 라이선스 할당
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: 이 문서에서는 PowerShell을 사용하여 라이선스가 없는 사용자에게 Microsoft 365 라이선스를 할당하는 방법을 학습합니다.
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905467"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="3e007-103">PowerShell을 통해 사용자 계정에 Microsoft 365 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="3e007-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="3e007-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="3e007-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3e007-105">사용자는 계정에 라이선스 계획의 라이선스가 할당될 때까지 Microsoft 365 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="3e007-106">PowerShell을 사용하여 라이선스가 없는 계정에 라이선스를 신속하게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="3e007-107">먼저 사용자 계정에 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="3e007-108">위치를 지정하는 것은 [Microsoft 365](../admin/add-users/add-users.md)관리 센터에서 새 사용자 계정을 만드는 데 필요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="3e007-109">기본적으로는 사내 Active Directory 도메인 서비스에서 동기화된 계정의 위치가 지정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="3e007-110">다음에서 이러한 계정의 위치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="3e007-111">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="3e007-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="3e007-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e007-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="3e007-113">[Azure Portal(Active](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **Directory**  >  **Users** > 사용자 계정> **연락처** 정보 국가  >    >  또는 지역)입니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="3e007-114">[](../admin/manage/assign-licenses-to-users.md) Microsoft 365 관리 센터를 통해 사용자 계정에 라이선스를 할당하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="3e007-115">추가 리소스 목록은 사용자 및 그룹 [관리를 참조하세요.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="3e007-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3e007-116">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="3e007-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3e007-117">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="3e007-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="3e007-118">다음으로, 이 명령을 사용하여 테넌트에 대한 라이선스 계획을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3e007-119">그런 다음 라이선스를 추가할 계정의 로그인 이름을 UPN(사용자 계정 이름)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="3e007-120">그런 다음 사용자 계정에 사용 위치가 할당되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="3e007-121">할당된 사용 위치가 없는 경우 다음 명령을 사용하여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="3e007-122">마지막으로 사용자 로그인 이름 및 라이선스 계획 이름을 지정하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3e007-123">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="3e007-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3e007-124">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3e007-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="3e007-125">명령을 실행하여 조직의 각 계획에서 사용 가능한 라이선스 계획 및 사용 가능한 라이선스 수를 `Get-MsolAccountSku` 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="3e007-126">각 계획에서 사용 가능한 라이선스 수는 **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits입니다.**</span><span class="sxs-lookup"><span data-stu-id="3e007-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="3e007-127">라이선스 계획, 라이선스 및 서비스에 대한 자세한 내용은 PowerShell을 통해 라이선스 및 서비스 [보기를 참조하세요.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3e007-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="3e007-128">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="3e007-129">이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="3e007-130">조직에서 라이선스가 없는 계정을 찾으면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="3e007-131">**UsageLocation** 속성이 유효한 ISO 3166-1 alpha-2 국가 코드로 설정된 사용자 계정에만 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="3e007-132">예를 들어 미국은 미국, 프랑스의 경우 FR입니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="3e007-133">일부 Microsoft 365 서비스는 특정 국가에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="3e007-134">자세한 내용은 라이선스 제한 [정보를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="3e007-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="3e007-135">**UsageLocation** 값이 없는 계정을 찾으면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="3e007-136">계정에 **UsageLocation** 값을 설정하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="3e007-137">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="3e007-138">**-All** 매개 변수를 사용하지 않고 **Get-MsolUser** cmdlet을 사용하는 경우 처음 500개의 계정만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="3e007-139">사용자 계정에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="3e007-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="3e007-140">사용자에게 라이선스를 할당하기 위해 PowerShell에서 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="3e007-141">이 예에서는 **litwareinc:ENTERPRISEPACK(Office** 365 Enterprise E3) 라이선스 계획의 라이선스를 라이선스가 허가되지 않은 사용자 **belindan에 \@** litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3e007-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="3e007-142">라이선스가 없는 모든 사용자에게 라이선스를 할당하기 위해 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="3e007-143">동일한 라이센스 제도에서 여러 라이센스 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="3e007-144">반환 하는 순서 대로 사용자에 게 라이선스 할당 된 충분 한 사용 가능한 라이센스를 설정 하지 않은 경우는 **Get-MsolUser** cmdlet 사용 가능한 라이센스가 실행 될 때까지.</span><span class="sxs-lookup"><span data-stu-id="3e007-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="3e007-145">이 예에서는 라이선스가 없는 모든 사용자에게 **litwareinc:ENTERPRISEPACK(Office** 365 Enterprise E3) 라이선스 계획의 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="3e007-146">이 예에서는 미국 판매 부서의 허가되지 않은 사용자에게 동일한 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3e007-147">Azure Active Directory PowerShell for Graph 모듈을 사용하여 사용자를 다른 구독(라이선스 계획)으로 이동</span><span class="sxs-lookup"><span data-stu-id="3e007-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3e007-148">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="3e007-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="3e007-149">그런 다음 구독을 전환할 사용자 계정의 로그인 이름을 UPN(사용자 계정 이름)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="3e007-150">다음으로 이 명령을 사용하여 테넌트의 구독(라이선스 계획)을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3e007-151">다음으로 사용자 계정이 현재 있는 구독을 다음 명령을 사용하여 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="3e007-152">사용자가 현재 있는 구독(FROM 구독) 및 사용자가 이동 중인 구독(TO 구독)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="3e007-153">마지막으로 TO 및 FROM 구독 이름(SKU 부분 번호)을 지정하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="3e007-154">다음 명령을 사용하여 사용자 계정의 구독 변경을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e007-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="3e007-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e007-155">See also</span></span>

[<span data-ttu-id="3e007-156">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="3e007-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3e007-157">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="3e007-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3e007-158">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="3e007-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
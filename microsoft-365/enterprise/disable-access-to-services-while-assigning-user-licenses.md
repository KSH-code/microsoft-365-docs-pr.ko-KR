---
title: 사용자 라이선스를 할당하는 동안 Microsoft 365 서비스에 대한 액세스 사용 안 하도록 설정
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: PowerShell을 사용하여 사용자 계정에 라이선스를 할당하고 특정 서비스 계획을 동시에 사용하지 않도록 설정하는 방법을 Microsoft 365.
ms.openlocfilehash: 7486968f6f4822047a1697ee1e05129277fd11a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929435"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="8740f-103">사용자 라이선스를 할당하는 동안 Microsoft 365 서비스에 대한 액세스 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8740f-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="8740f-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="8740f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8740f-105">Microsoft 365 구독에는 개별 서비스에 대한 서비스 계획이 함께 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="8740f-106">Microsoft 365 사용자에게 라이선스를 할당할 때 특정 계획을 사용하지 않도록 설정해야 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="8740f-107">이 문서의 지침에 따라 개별 사용자 계정 또는 여러 사용자 계정에 대해 PowerShell을 사용하여 특정 서비스 계획을 사용하지 Microsoft 365 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8740f-108">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="8740f-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8740f-109">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="8740f-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="8740f-110">다음으로, 이 명령을 사용하여 테넌트에 대한 라이선스 계획을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="8740f-111">그런 다음 라이선스를 추가할 계정의 로그인 이름을 UPN(사용자 계정 이름)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="8740f-112">그런 다음 사용하도록 설정할 서비스 목록을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="8740f-113">라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="8740f-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="8740f-114">아래 명령 블록의 경우 사용자 계정의 사용자 계정 이름, SKU 부분 번호 및 서비스 계획 목록을 입력하여 설명 텍스트와 문자를 사용하도록 설정하고 \< and > 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="8740f-115">그런 다음 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8740f-116">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="8740f-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8740f-117">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="8740f-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="8740f-118">다음으로, 다음 명령을 실행하여 현재 구독을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="8740f-119">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="8740f-120">이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="8740f-121">명령 표시에서  `Get-MsolAccountSku` 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="8740f-122">**AccountSkuId는** 조직의 \<OrganizationName> 구독(형식)입니다. \<Subscription></span><span class="sxs-lookup"><span data-stu-id="8740f-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="8740f-123">는 조직에 등록할 때 제공한 Microsoft 365 \<OrganizationName> 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="8740f-124">값은 \<Subscription> 특정 구독에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="8740f-125">예를 들어 litwareinc:ENTERPRISEPACK의 경우 조직 이름은 litwareinc, 구독 이름은 ENTERPRISEPACK(Office 365 Enterprise E3)입니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="8740f-126">**ActiveUnits는** 구독을 위해 구입한 라이선스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="8740f-127">**WarningUnits는** 갱신하지 않은 구독의 라이선스 수로, 30일 유예 기간 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="8740f-128">**ConsumedUnits는** 구독에 대해 사용자에게 할당한 라이선스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="8740f-129">라이선스를 부여할 사용자가 Microsoft 365 구독의 AccountSkuId를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="8740f-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="8740f-130">또한 할당할 수 있는 라이선스가 충분한지 **확인(ActiveUnits에서 ConsumedUnits 빼기).** </span><span class="sxs-lookup"><span data-stu-id="8740f-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="8740f-131">다음으로, 다음 명령을 실행하여 모든 구독에서 사용할 수 있는 Microsoft 365 서비스 계획에 대한 세부 정보를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="8740f-132">이 명령이 표시되어 있는 경우 사용자에게 라이선스를 할당할 때 사용하지 않도록 설정할 서비스 계획을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="8740f-133">다음은 서비스 계획 및 해당 서비스 계획의 일부 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="8740f-134">다음 표에는 서비스 Microsoft 365 가장 일반적인 서비스에 대한 이름 및 서비스 계획이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="8740f-135">서비스 계획 목록이 다를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="8740f-136">**서비스 계획**</span><span class="sxs-lookup"><span data-stu-id="8740f-136">**Service plan**</span></span>|<span data-ttu-id="8740f-137">**설명**</span><span class="sxs-lookup"><span data-stu-id="8740f-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="8740f-138">Sway</span><span class="sxs-lookup"><span data-stu-id="8740f-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="8740f-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8740f-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="8740f-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="8740f-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="8740f-141">RMS(Azure 권한 관리)</span><span class="sxs-lookup"><span data-stu-id="8740f-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="8740f-142">*엔터프라이즈용 Microsoft 365 앱(이전에는 Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="8740f-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="8740f-143">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="8740f-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="8740f-144">Office</span><span class="sxs-lookup"><span data-stu-id="8740f-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="8740f-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8740f-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="8740f-146">Exchange Online 계획 2</span><span class="sxs-lookup"><span data-stu-id="8740f-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="8740f-147">라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="8740f-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="8740f-148">이제 사용하지 않도록 설정할 AccountSkuId 및 서비스 계획이 준비되어 있습니다. 개별 사용자 또는 여러 사용자에 대해 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="8740f-149">단일 사용자의 경우</span><span class="sxs-lookup"><span data-stu-id="8740f-149">For a single user</span></span>

<span data-ttu-id="8740f-150">단일 사용자의 경우 사용자 계정의 사용자 계정 이름, AccountSkuId 및 서비스 계획 목록을 입력하여 설명 텍스트와 문자를 사용하지 않도록 설정하고 \< and > 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="8740f-151">그런 다음 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="8740f-152">다음은 belindan@contoso.com 계정, contoso:ENTERPRISEPACK 라이선스에 대한 명령 블록의 예입니다. 사용하지 않도록 설정할 서비스 계획은 RMS_S_ENTERPRISE, SWAY, INTUNE_O365 및 YAMMER_ENTERPRISE.</span><span class="sxs-lookup"><span data-stu-id="8740f-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="8740f-153">여러 사용자의 경우</span><span class="sxs-lookup"><span data-stu-id="8740f-153">For multiple users</span></span>

<span data-ttu-id="8740f-154">여러 사용자에 대해 이 관리 작업을 수행하기 위해 UserPrincipalName 및 UsageLocation 필드가 포함된 CSV(콤보로 구분된 값) 텍스트 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="8740f-155">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-155">Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="8740f-156">다음으로, 입력 및 출력 CSV 파일의 위치, 계정 SKU ID 및 사용하지 않도록 설정할 서비스 계획 목록을 입력한 다음 PowerShell 명령 프롬프트에서 결과 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="8740f-157">이 PowerShell 명령 블록:</span><span class="sxs-lookup"><span data-stu-id="8740f-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="8740f-158">각 사용자의 사용자 계정 이름을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="8740f-159">사용자 지정된 라이선스를 각 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="8740f-160">처리된 모든 사용자와 함께 CSV 파일을 만들고 라이선스 상태를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8740f-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8740f-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8740f-161">See also</span></span>

[<span data-ttu-id="8740f-162">PowerShell을 Microsoft 365 서비스에 액세스하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8740f-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8740f-163">PowerShell을 통해 Sway에 액세스하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8740f-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8740f-164">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="8740f-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8740f-165">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="8740f-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
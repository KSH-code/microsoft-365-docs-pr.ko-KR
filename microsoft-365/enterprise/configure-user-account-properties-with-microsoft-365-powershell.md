---
title: PowerShell을 Microsoft 365 사용자 계정 속성 구성
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: PowerShell을 사용하여 Microsoft 365 테넌트에서 개별 또는 여러 사용자 계정의 속성을 Microsoft 365 있습니다.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911087"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="18b7f-103">PowerShell을 Microsoft 365 사용자 계정 속성 구성</span><span class="sxs-lookup"><span data-stu-id="18b7f-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="18b7f-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="18b7f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="18b7f-105">Microsoft 365 관리 센터를 사용하여 테넌트의 사용자 계정에 대한 속성을 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="18b7f-106">PowerShell에서 이 작업을 할 수도 있습니다. 또한 관리 센터에서 할 수 없는 다른 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="18b7f-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="18b7f-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="18b7f-108">Azure Active Directory PowerShell에서 Graph 계정에 대한 속성을 구성하기 위해 [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet을 사용하여 설정하거나 변경할 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="18b7f-109">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="18b7f-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="18b7f-110">특정 사용자 계정의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="18b7f-110">Change properties for a specific user account</span></span>

<span data-ttu-id="18b7f-111">*-ObjectID* 매개 변수를 사용하여 계정을 식별하고 추가 매개 변수를 사용하여 특정 속성을 설정하거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="18b7f-112">가장 일반적인 매개 변수 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="18b7f-113">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="18b7f-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="18b7f-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="18b7f-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="18b7f-117">-Surname " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="18b7f-118">-Mobile \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="18b7f-119">-JobTitle \<job title> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="18b7f-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="18b7f-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="18b7f-122">-City \<city name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="18b7f-123">-State \<state name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="18b7f-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="18b7f-125">-Country \<country name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="18b7f-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="18b7f-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="18b7f-128">ISO 3166-1 알파-2(A2) 두 글자 국가 또는 지역 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="18b7f-129">추가 매개 변수는 [Set-AzureADUser 를 참조하세요.](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="18b7f-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="18b7f-130">사용자 계정에 라이선스를 할당하려면 먼저 사용 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="18b7f-131">사용자 계정에 대한 사용자 계정 이름을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="18b7f-132">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="18b7f-133">사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-134">사용자 계정 이름 목록을 사전순(Sort **UserPrincipalName)으로** 정렬하고 다음 명령()으로 전송합니다. **|**</span><span class="sxs-lookup"><span data-stu-id="18b7f-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-135">각 계정에 대한 사용자 계정 이름 속성만 표시합니다(**UserPrincipalName 선택).**</span><span class="sxs-lookup"><span data-stu-id="18b7f-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="18b7f-136">한 화면으로 한 화면 표시(**추가).**</span><span class="sxs-lookup"><span data-stu-id="18b7f-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="18b7f-137">표시 이름(이름 및 성)을 기반으로 계정의 사용자 계정 이름을 표시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="18b7f-138">변수를 *$userName* 입력하고 문자를 \< and > 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="18b7f-139">이 예에서는 표시 이름이 *Caleb Sills인* 사용자 계정의 사용자 계정 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="18b7f-140">$upn *변수를* 사용하면 표시 이름에 따라 개별 계정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="18b7f-141">다음은 *Belinda Newman의* 사용 위치를 프랑스로 설정하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="18b7f-142">그러나 사용자 계정 이름 대신 표시 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="18b7f-143">모든 사용자 계정의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="18b7f-143">Change properties for all user accounts</span></span>

<span data-ttu-id="18b7f-144">모든 사용자에 대한 속성을 변경하기 위해 **Get-AzureADUser** 및 **Set-AzureADUser** cmdlet을 조합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="18b7f-145">다음 예에서는 모든 사용자의 사용 위치를 프랑스로 *변경합니다.*</span><span class="sxs-lookup"><span data-stu-id="18b7f-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="18b7f-146">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="18b7f-147">사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령( )으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-148">사용자 위치를 **프랑스(Set-AzureADUser -UsageLocation "FR")로 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="18b7f-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="18b7f-149">특정 사용자 계정 집합의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="18b7f-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="18b7f-150">특정 사용자 계정 집합의 속성을 변경하기 위해 **Get-AzureADUser,** **Where** 및 **Set-AzureADUser** cmdlet의 조합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="18b7f-151">다음 예에서는 회계 부서의 모든 사용자에 대한 사용 위치를 *프랑스로 변경합니다.*</span><span class="sxs-lookup"><span data-stu-id="18b7f-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="18b7f-152">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="18b7f-153">사용자 **계정(Get-AzureADUser**)에 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="18b7f-154">*Department* 속성이 "Accounting"(여기서 {$_)으로 설정된 모든 사용자 **계정을 찾아야 합니다. Department -eq "Accounting"}**) 및 다음 명령()에 결과 정보를 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-155">사용자 위치를 **프랑스(Set-AzureADUser -UsageLocation "FR")로 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="18b7f-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="18b7f-156">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="18b7f-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="18b7f-157">Microsoft Azure Active Directory Module을 사용하여 사용자 계정에 대한 속성을 Windows PowerShell **Set-MsolUser** cmdlet을 사용하여 설정하거나 변경할 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="18b7f-158">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="18b7f-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="18b7f-159">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="18b7f-160">Windows PowerShell에서 이러한 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="18b7f-161">특정 사용자 계정의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="18b7f-161">Change properties for a specific user account</span></span>

<span data-ttu-id="18b7f-162">특정 사용자 계정에 대한 속성을 구성하려면 [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet을 사용하여 설정하거나 변경할 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="18b7f-163">*-UserPrincipalName* 매개 변수를 사용하여 계정을 식별하고 추가 매개 변수를 사용하여 특정 속성을 설정하거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="18b7f-164">다음은 가장 일반적인 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="18b7f-165">-City \<city name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="18b7f-166">-Country \<country name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="18b7f-167">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="18b7f-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="18b7f-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="18b7f-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="18b7f-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="18b7f-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="18b7f-173">-Office \<office location> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="18b7f-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="18b7f-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="18b7f-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="18b7f-177">-State \<state name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="18b7f-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="18b7f-179">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="18b7f-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="18b7f-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="18b7f-181">ISO 3166-1 알파-2(A2) 두 글자 국가 또는 지역 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="18b7f-182">추가 매개 변수는 [Set-MsolUser 를 참조합니다.](/previous-versions/azure/dn194136(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="18b7f-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="18b7f-183">모든 사용자의 사용자 계정 이름을 확인하도록 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="18b7f-184">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="18b7f-185">사용자 계정에 대한 모든 **정보(Get-MsolUser)를** 사용하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-186">사용자 계정 이름 목록을 사전순(Sort **UserPrincipalName)으로** 정렬하고 다음 명령()으로 전송합니다. **|**</span><span class="sxs-lookup"><span data-stu-id="18b7f-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-187">각 계정에 대한 사용자 계정 이름 속성만 표시합니다(**UserPrincipalName 선택).**</span><span class="sxs-lookup"><span data-stu-id="18b7f-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="18b7f-188">한 화면으로 한 화면 표시(**추가).**</span><span class="sxs-lookup"><span data-stu-id="18b7f-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="18b7f-189">표시 이름(이름 및 성)을 기반으로 계정의 사용자 계정 이름을 표시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="18b7f-190">변수를 *$userName* 입력하고 문자를 \< and > 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="18b7f-191">이 예에서는 Caleb Sills라는 사용자의 사용자 계정 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="18b7f-192">$upn *변수를* 사용하면 표시 이름에 따라 개별 계정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="18b7f-193">다음은 *Belinda Newman의* 사용 위치를 프랑스로 설정하고 사용자 계정 이름 대신 표시 이름을 지정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="18b7f-194">모든 사용자 계정의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="18b7f-194">Change properties for all user accounts</span></span>

<span data-ttu-id="18b7f-195">모든 사용자에 대한 속성을 변경하기 위해 **Get-MsolUser 및 Set-MsolUser** cmdlet의 조합을 사용 합니다. </span><span class="sxs-lookup"><span data-stu-id="18b7f-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="18b7f-196">다음 예에서는 모든 사용자의 사용 위치를 프랑스로 *변경합니다.*</span><span class="sxs-lookup"><span data-stu-id="18b7f-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="18b7f-197">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="18b7f-198">사용자 계정의 모든 **정보(Get-MsolUser)를** 사용하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-199">사용자 위치를 **프랑스(Set-MsolUser -UsageLocation "FR")로 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="18b7f-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="18b7f-200">특정 사용자 계정 집합의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="18b7f-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="18b7f-201">특정 사용자 계정 집합의 속성을 변경하기 위해 **Get-MsolUser,** **Where** 및 **Set-MsolUser** cmdlet의 조합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="18b7f-202">다음 예에서는 회계 부서의 모든 사용자에 대한 사용 위치를 *프랑스로 변경합니다.*</span><span class="sxs-lookup"><span data-stu-id="18b7f-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="18b7f-203">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="18b7f-204">사용자 계정의 모든 **정보(Get-MsolUser)를** 사용하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-205">*Department* 속성이 "Accounting"(여기서 {$_)으로 설정된 모든 **사용자 계정을 찾아야 합니다. Department -eq "Accounting"}**) 및 다음 명령()에 결과 정보를 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="18b7f-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="18b7f-206">사용자 위치를 **프랑스(Set-MsolUser -UsageLocation "FR")로 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="18b7f-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="18b7f-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18b7f-207">See also</span></span>

[<span data-ttu-id="18b7f-208">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="18b7f-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="18b7f-209">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="18b7f-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="18b7f-210">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="18b7f-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
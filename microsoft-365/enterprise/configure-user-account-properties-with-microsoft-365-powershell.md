---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정 속성 구성
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
description: Microsoft 365 용 PowerShell을 사용 하 여 Microsoft 365 테 넌 트에서 개별 또는 여러 사용자 계정에 대 한 속성을 구성 합니다.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754331"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="bdce0-103">PowerShell을 사용 하 여 Microsoft 365 사용자 계정 속성 구성</span><span class="sxs-lookup"><span data-stu-id="bdce0-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="bdce0-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="bdce0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bdce0-105">Microsoft 365 관리 센터를 사용 하 여 Microsoft 365 테 넌 트의 사용자 계정에 대 한 속성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="bdce0-106">또한 PowerShell에서이 작업을 수행할 수도 있고 관리 센터에서 수행할 수 없는 다른 작업도 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="bdce0-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="bdce0-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="bdce0-108">Graph 모듈에 대 한 Azure Active Directory PowerShell의 사용자 계정에 대 한 속성을 구성 하려면 [**AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet을 사용 하 고 설정 하거나 변경할 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="bdce0-109">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="bdce0-110">특정 사용자 계정에 대 한 속성 변경</span><span class="sxs-lookup"><span data-stu-id="bdce0-110">Change properties for a specific user account</span></span>

<span data-ttu-id="bdce0-111">*-ObjectID* 매개 변수를 사용 하 여 계정을 식별 하 고 추가 매개 변수를 사용 하 여 특정 속성을 설정 하거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="bdce0-112">다음은 가장 일반적인 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="bdce0-113">-부서 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="bdce0-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="bdce0-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="bdce0-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="bdce0-117">-성 " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="bdce0-118">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="bdce0-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="bdce0-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="bdce0-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="bdce0-122">-구/군/시 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="bdce0-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="bdce0-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="bdce0-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="bdce0-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="bdce0-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="bdce0-128">ISO 3166-1 alpha-2 (A2) 두 자리 국가 또는 지역 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="bdce0-129">추가 매개 변수에 대 한 자세한 내용은 [AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bdce0-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="bdce0-130">사용자 계정에 라이선스를 할당 하려면 사용 위치를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="bdce0-131">사용자 계정의 사용자 계정 이름을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="bdce0-132">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="bdce0-133">사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-134">사용자 계정 이름 목록을 사전순 (**Sort UserPrincipalName**)으로 정렬 하 고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-135">각 계정에 대해 사용자 계정 이름 속성을 표시 합니다 (**UserPrincipalName 선택**).</span><span class="sxs-lookup"><span data-stu-id="bdce0-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="bdce0-136">한**화면을 한**번에 한 화면씩 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="bdce0-137">표시 이름 (이름과 성)을 기준으로 계정의 사용자 계정 이름을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="bdce0-138">*$UserName* 변수를 채우고 해당 문자를 제거 합니다 \< and > .</span><span class="sxs-lookup"><span data-stu-id="bdce0-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bdce0-139">이 예에서는 표시 이름이 *Caleb 창턱*인 사용자 계정에 대 한 사용자 보안 주체 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bdce0-140">*$Upn* 변수를 사용 하 여 개별 계정을 표시 이름에 따라 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="bdce0-141">다음은 *Belinda Newman*의 사용 위치를 프랑스로 설정 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="bdce0-142">하지만 사용자 계정 이름이 아닌 표시 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="bdce0-143">모든 사용자 계정에 대 한 속성 변경</span><span class="sxs-lookup"><span data-stu-id="bdce0-143">Change properties for all user accounts</span></span>

<span data-ttu-id="bdce0-144">모든 사용자에 대 한 속성을 변경 하려면 **AzureADUser** 및 **AzureADUser** cmdlet을 조합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="bdce0-145">다음은 모든 사용자의 사용 위치를 *프랑스*로 변경 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="bdce0-146">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="bdce0-147">사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 전송 **|** 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-148">사용자 위치를 프랑스 (**AzureADUser-UsageLocation "FR"**)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="bdce0-149">특정 사용자 계정 집합의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="bdce0-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="bdce0-150">특정 사용자 계정 집합의 속성을 변경 하려면 **AzureADUser**, **Where**및 **AzureADUser** cmdlet을 조합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="bdce0-151">다음 예에서는 회계 부서에 있는 모든 사용자의 사용 위치를 *프랑스*로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="bdce0-152">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="bdce0-153">사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="bdce0-154">*부서* 속성이 "회계"로 설정 된 모든 사용자 계정을 찾습니다 (**여기서 {$ _. 부서-eq "Accounting"}**)를 사용 하 고 결과 정보를 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-155">사용자 위치를 프랑스 (**AzureADUser-UsageLocation "FR"**)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="bdce0-156">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="bdce0-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="bdce0-157">Windows PowerShell 용 Microsoft Azure Active Directory 모듈을 사용 하 여 사용자 계정에 대 한 속성을 구성 하려면 **get-msoluser** cmdlet을 사용 하 고 설정 하거나 변경할 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="bdce0-158">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="bdce0-159">PowerShell Core에서는 이름에 *Msol* 이 포함 된 Windows powershell 모듈 및 cmdlet에 대 한 Microsoft Azure Active Directory 모듈을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="bdce0-160">Windows PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="bdce0-161">특정 사용자 계정에 대 한 속성 변경</span><span class="sxs-lookup"><span data-stu-id="bdce0-161">Change properties for a specific user account</span></span>

<span data-ttu-id="bdce0-162">특정 사용자 계정에 대 한 속성을 구성 하려면 [**get-msoluser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet을 사용 하 고 설정 하거나 변경할 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bdce0-163">*-UserPrincipalName* 매개 변수를 사용 하 여 계정을 식별 하 고 추가 매개 변수를 사용 하 여 특정 속성을 설정 하거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="bdce0-164">가장 일반적인 매개 변수 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="bdce0-165">-구/군/시 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="bdce0-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="bdce0-167">-부서 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="bdce0-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="bdce0-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="bdce0-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="bdce0-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="bdce0-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="bdce0-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="bdce0-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="bdce0-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="bdce0-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="bdce0-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="bdce0-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="bdce0-179">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="bdce0-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="bdce0-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="bdce0-181">ISO 3166-1 alpha-2 (A2) 두 자리 국가 또는 지역 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="bdce0-182">추가 매개 변수에 대 한 자세한 내용은 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bdce0-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="bdce0-183">모든 사용자의 사용자 계정 이름을 보려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="bdce0-184">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="bdce0-185">사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-186">사용자 계정 이름 목록을 사전순 (**Sort UserPrincipalName**)으로 정렬 하 고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-187">각 계정에 대해 사용자 계정 이름 속성을 표시 합니다 (**UserPrincipalName 선택**).</span><span class="sxs-lookup"><span data-stu-id="bdce0-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="bdce0-188">한**화면을 한**번에 한 화면씩 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="bdce0-189">표시 이름 (이름과 성)을 기준으로 계정의 사용자 계정 이름을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="bdce0-190">*$UserName* 변수를 채우고 해당 문자를 제거 \< and > 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bdce0-191">이 예제에서는 Caleb 창턱 라는 사용자에 대 한 사용자 계정 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bdce0-192">*$Upn* 변수를 사용 하 여 개별 계정을 표시 이름에 따라 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="bdce0-193">다음은 *Belinda Newman*의 사용 위치를 *프랑스*로 설정 하지만 사용자 계정 이름이 아닌 표시 이름을 지정 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="bdce0-194">모든 사용자 계정에 대 한 속성 변경</span><span class="sxs-lookup"><span data-stu-id="bdce0-194">Change properties for all user accounts</span></span>

<span data-ttu-id="bdce0-195">모든 사용자에 대 한 속성을 변경 하려면 **get-msoluser** 및 **get-msoluser** cmdlet을 조합 하 여 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="bdce0-196">다음은 모든 사용자의 사용 위치를 *프랑스*로 변경 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="bdce0-197">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="bdce0-198">사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-199">사용자 위치를 프랑스 (**get-msoluser-UsageLocation "FR"**)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="bdce0-200">특정 사용자 계정 집합의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="bdce0-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="bdce0-201">특정 사용자 계정 집합의 속성을 변경 하려면 **get-msoluser**, **Where**및 **get-msoluser** cmdlet을 조합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="bdce0-202">다음 예에서는 회계 부서에 있는 모든 사용자의 사용 위치를 *프랑스*로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="bdce0-203">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="bdce0-204">사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="bdce0-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-205">*부서* 속성이 "회계"로 설정 된 모든 사용자 계정을 찾습니다 (**여기서 {$ _. 부서-eq "Accounting"}**)를 사용 하 고 결과 정보를 다음 명령 ( **|** )으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="bdce0-206">사용자 위치를 프랑스 (**get-msoluser-UsageLocation "FR"**)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdce0-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="bdce0-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdce0-207">See also</span></span>

[<span data-ttu-id="bdce0-208">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="bdce0-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bdce0-209">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="bdce0-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bdce0-210">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="bdce0-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

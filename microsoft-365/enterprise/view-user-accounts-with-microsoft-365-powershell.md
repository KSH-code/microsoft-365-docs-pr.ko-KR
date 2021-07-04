---
title: PowerShell을 Microsoft 365 사용자 계정 보기
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: PowerShell을 통해 다양한 방식으로 Microsoft 365 사용자 계정을 보거나, 나열하거나, 표시하는 방법을 학습합니다.
ms.openlocfilehash: 77219fb89430ed257ef2a68a7b24bf9ebac715b2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290174"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="94d60-103">PowerShell을 Microsoft 365 사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="94d60-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="94d60-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94d60-105">를 사용하여 Microsoft 365 관리 센터 테넌트의 계정을 볼 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="94d60-106">PowerShell for Microsoft 365 이 기능을 사용할 수 있지만 추가 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="94d60-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="94d60-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="94d60-108">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="94d60-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="94d60-109">모든 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-109">View all accounts</span></span>

<span data-ttu-id="94d60-110">전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="94d60-111">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="94d60-112">특정 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-112">View a specific account</span></span>

<span data-ttu-id="94d60-113">특정 사용자 계정을 표시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="94d60-114">UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 계정 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="94d60-115">"<" 및 ">" 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="94d60-116">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="94d60-117">특정 계정에 대한 추가 속성 값 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-117">View additional property values for a specific account</span></span>

<span data-ttu-id="94d60-118">기본적으로 **Get-AzureADUser** cmdlet은 계정의 *ObjectID,* *DisplayName* 및 *UserPrincipalName* 속성만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="94d60-119">표시할 속성에 대해 보다 선택적으로 선택하려면 **Get-AzureADUser**  cmdlet과 함께 Select cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="94d60-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="94d60-120">두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Azure Active Directory PowerShell에 Graph 명령의 결과를 받아 다음 명령으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="94d60-121">다음은 모든 사용자 계정에 대한 *DisplayName,* *Department* 및 *UsageLocation을* 표시하는 예제 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="94d60-122">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="94d60-123">사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="94d60-124">사용자 계정 이름, 부서 및 사용 위치만 표시합니다(**DisplayName, Department, UsageLocation 선택).**</span><span class="sxs-lookup"><span data-stu-id="94d60-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="94d60-125">특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(\*)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="94d60-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="94d60-126">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="94d60-127">다른 예로 다음 명령을 실행하여 특정 사용자 계정의 사용 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="94d60-128">계정 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-128">View account synchronization status</span></span>

<span data-ttu-id="94d60-129">사용자 계정에는 다음 두 가지 원본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="94d60-130">Windows Server Active Directory(AD)는 사내 AD에서 클라우드로 동기화되는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="94d60-131">Azure Active Directory(Azure AD) AD 계정을 사용하여 클라우드에서 직접 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="94d60-132">다음 명령은 *DirSyncEnabled* 특성이 True로 설정된 모든 사용자를 하게 PowerShell에 *지시합니다.*</span><span class="sxs-lookup"><span data-stu-id="94d60-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="94d60-133">이를 사용하여 사내 AD에서 동기화하는 계정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="94d60-134">다음 명령은 *DirSyncEnabled* 특성이 False로 설정된 모든 사용자를 얻게 PowerShell에 *지시합니다.*</span><span class="sxs-lookup"><span data-stu-id="94d60-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="94d60-135">클라우드 전용 계정을 찾는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="94d60-136">공통 속성을 기반으로 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-136">View accounts based on a common property</span></span>

<span data-ttu-id="94d60-137">표시할 계정 목록에 대해 보다 선택적으로 사용하려면 **Where** cmdlet을 **Get-AzureADUser** cmdlet과 함께 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="94d60-138">두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Azure Active Directory PowerShell에 Graph 명령의 결과를 받아 다음 명령으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="94d60-139">다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예제 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="94d60-140">이 명령은 다음 Azure Active Directory PowerShell에 Graph 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="94d60-141">사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="94d60-142">미지정 사용 위치가 있는 모든 사용자 **계정(Where {$ \_ 을 찾아야 합니다. UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="94d60-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="94d60-143">중괄호 안의 명령은 PowerShell에 UsageLocation 사용자 계정 속성이 있는 계정 집합만 찾게 **$ \_ 합니다. UsageLocation**)이 지정되지 않았습니다(**-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="94d60-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="94d60-144">**UsageLocation 속성은** 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="94d60-145">특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(\*)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="94d60-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="94d60-146">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="94d60-147">예를 들어 **City는** 사용자 계정 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="94d60-148">다음 명령을 사용하여 런던에 거주하는 모든 사용자의 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="94d60-149">이 예제의 **Where** cmdlet에 대한 구문은 **Where {$ \_ 입니다.**</span><span class="sxs-lookup"><span data-stu-id="94d60-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="94d60-150">[사용자 계정 속성 이름] [비교 연산자] [value] **}**.> [비교 연산자]는 **-eq가** 같음, **-ne이면** 같지 않습니다. **-lt는** 보다 작음, -gt이면 보다 크면 **-gt입니다.**</span><span class="sxs-lookup"><span data-stu-id="94d60-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="94d60-151">[value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="94d60-152">자세한 내용은 Where 를 [참조하세요.](/powershell/module/microsoft.powershell.core/where-object)</span><span class="sxs-lookup"><span data-stu-id="94d60-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="94d60-153">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="94d60-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="94d60-154">먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="94d60-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="94d60-155">모든 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-155">View all accounts</span></span>

<span data-ttu-id="94d60-156">전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="94d60-157">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="94d60-158">Windows PowerShell에서 이러한 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="94d60-159">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="94d60-160">**Get-msoluser** cmdlet에도 매개 변수 집합이 있어 표시된 사용자 계정 집합을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="94d60-161">예를 들어 허가되지 않은 사용자(Microsoft 365 서비스에 대한 사용이 허가되지 않은 사용자)의 목록에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="94d60-162">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="94d60-163">표시되는 사용자 계정 집합을 필터링하는 추가 매개 변수에 대한 자세한 내용은 [Get-MsolUser 를 참조하세요.](/previous-versions/azure/dn194133(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="94d60-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="94d60-164">특정 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-164">View a specific account</span></span>

<span data-ttu-id="94d60-165">특정 사용자 계정을 표시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="94d60-166">UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="94d60-167">"<" 및 ">" 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="94d60-168">공통 속성을 기반으로 계정 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-168">View accounts based on a common property</span></span>

<span data-ttu-id="94d60-169">표시할 계정 목록에 대해 보다 선택적으로 사용하려면 **Where** cmdlet을 **Get-MsolUser** cmdlet과 함께 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="94d60-170">두 cmdlet을 결합하기 위해 PowerShell에 한 명령의 결과를 받아 다음 명령으로 보내라고 알려주는 "파이프" 문자("|")를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="94d60-171">다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="94d60-172">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="94d60-173">사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="94d60-174">미지정 사용 위치가 있는 모든 사용자 **계정(Where {$ \_ 을 찾아야 합니다. UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="94d60-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="94d60-175">중괄호 안의 명령은 PowerShell에 UsageLocation 사용자 계정 속성이 있는 계정 집합만 찾게 **$ \_ 합니다. UsageLocation**)이 지정되지 않았습니다(**-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="94d60-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="94d60-176">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="94d60-177">*UsageLocation 속성은* 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="94d60-178">사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(\*)를 사용하여 특정 사용자 계정에 대한 모든 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="94d60-179">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="94d60-180">예를 들어 *City는* 사용자 계정 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="94d60-181">다음 명령을 사용하여 런던에 거주하는 사용자의 모든 사용자 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="94d60-182">이 예제의 **Where** cmdlet에 대한 구문은 **Where {$ \_ 입니다.**</span><span class="sxs-lookup"><span data-stu-id="94d60-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="94d60-183">[사용자 계정 속성 이름] [비교 연산자] [value] **}**.</span><span class="sxs-lookup"><span data-stu-id="94d60-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="94d60-184">[비교 연산자]는 **-eq가** 같음, **-ne이면** 같지 않습니다. **-lt는** 보다 작음, -gt 보다 크면 **-gt입니다.**</span><span class="sxs-lookup"><span data-stu-id="94d60-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="94d60-185">[value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="94d60-186">자세한 내용은 Where 를 [참조하세요.](/powershell/module/microsoft.powershell.core/where-object)</span><span class="sxs-lookup"><span data-stu-id="94d60-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>
  
<span data-ttu-id="94d60-187">사용자 계정의 차단 상태를 확인하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="94d60-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="94d60-188">계정에 대한 추가 속성 값 보기</span><span class="sxs-lookup"><span data-stu-id="94d60-188">View additional property values for accounts</span></span>

<span data-ttu-id="94d60-189">기본적으로 **Get-MsolUser** cmdlet은 사용자 계정의 다음 세 가지 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="94d60-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="94d60-190">UserPrincipalName</span></span>

- <span data-ttu-id="94d60-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="94d60-191">DisplayName</span></span>

- <span data-ttu-id="94d60-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="94d60-192">isLicensed</span></span>

<span data-ttu-id="94d60-193">사용자가 작업하는 부서 및 Microsoft 365 서비스를 사용하는 국가/지역과 같은 추가 속성이 필요한 경우 **Get-MsolUser를** **Select** cmdlet과 함께 실행하여 사용자 계정 속성 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="94d60-194">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="94d60-195">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="94d60-196">사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령( )으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="94d60-197">사용자 계정 이름, 부서 및 사용 위치만 표시합니다(**DisplayName, Department, UsageLocation 선택).**</span><span class="sxs-lookup"><span data-stu-id="94d60-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="94d60-198">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="94d60-199">Select  cmdlet을 사용하면 표시할 속성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="94d60-200">특정 사용자 계정에 대한 모든 속성을 표시하려면 와일드카드 문자(\*)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="94d60-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="94d60-201">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="94d60-202">표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="94d60-203">다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예제 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="94d60-204">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="94d60-205">사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령( )으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="94d60-206">미지정 사용 위치가 있는 모든 사용자 **계정(Where {$ \_ 을 찾아야 합니다. UsageLocation -eq $Null}**) 및 다음 명령()에 결과 정보를 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="94d60-207">중괄호 안의 명령은 PowerShell에 UsageLocation 사용자 계정 속성이 있는 계정 집합만 찾게 **$ \_ 합니다. UsageLocation**)이 지정되지 않았습니다(**-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="94d60-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="94d60-208">사용자 계정 이름, 부서 및 사용 위치만 표시합니다(**DisplayName, Department, UsageLocation 선택).**</span><span class="sxs-lookup"><span data-stu-id="94d60-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="94d60-209">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="94d60-210">디렉터리 동기화를 사용하여 Microsoft 365 사용자를 만들고 관리하는 경우 Microsoft 365 로컬 계정을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="94d60-211">다음 예제에서는 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-211">The following example assumes that:</span></span>

- <span data-ttu-id="94d60-212">Azure AD 커넥트 ObjectGUID의 기본 원본 앵커를 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="94d60-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="94d60-213">원본 앵커 구성에 대한 자세한 내용은 [Azure AD 커넥트: 디자인 개념을 참조하세요.](/azure/active-directory/hybrid/plan-connect-design-concepts)</span><span class="sxs-lookup"><span data-stu-id="94d60-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="94d60-214">PowerShell용 Active Directory 도메인 서비스 모듈이 [설치되었습니다(RSAT 도구 참조).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)</span><span class="sxs-lookup"><span data-stu-id="94d60-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="94d60-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94d60-215">See also</span></span>

[<span data-ttu-id="94d60-216">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="94d60-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="94d60-217">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="94d60-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="94d60-218">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="94d60-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
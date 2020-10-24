---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정 보기
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
description: PowerShell을 사용 하 여 다양 한 방식으로 Microsoft 365 사용자 계정을 보거나, 나열 하거나, 표시 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754075"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="c8d37-103">PowerShell을 사용 하 여 Microsoft 365 사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="c8d37-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c8d37-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c8d37-105">Microsoft 365 관리 센터를 사용 하 여 Microsoft 365 테 넌 트에 대 한 계정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="c8d37-106">Microsoft 365 용 PowerShell을 사용 하도록 설정 하지만 추가 기능도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c8d37-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="c8d37-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c8d37-108">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="c8d37-109">모든 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-109">View all accounts</span></span>

<span data-ttu-id="c8d37-110">사용자 계정의 전체 목록을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="c8d37-111">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="c8d37-112">특정 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-112">View a specific account</span></span>

<span data-ttu-id="c8d37-113">특정 사용자 계정을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="c8d37-114">UPN (사용자 계정 이름)이 라고도 하는 사용자 계정의 로그인 계정 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="c8d37-115">"<" 및 ">" 문자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="c8d37-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="c8d37-117">특정 계정에 대 한 추가 속성 값 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-117">View additional property values for a specific account</span></span>

<span data-ttu-id="c8d37-118">기본적으로 **AzureADUser** cmdlet은 계정의 *ObjectID*, *DisplayName*및 *UserPrincipalName* 속성만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="c8d37-119">표시할 속성을 보다 신중 하 게 선택 하려면 **AzureADUser** cmdlet과 함께 **Select** cmdlet을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8d37-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="c8d37-120">두 cmdlet을 결합 하기 위해 Azure Active Directory PowerShell에는 그래프를 나타내는 "|" 문자를 사용 하 여 하나의 명령에 대 한 결과를 가져오고 다음 명령으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="c8d37-121">다음은 모든 사용자 계정에 대해 *DisplayName*, *학과*및 *UsageLocation* 를 표시 하는 명령 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="c8d37-122">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c8d37-123">사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="c8d37-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="c8d37-124">사용자 계정 이름, 부서 및 사용 위치만 표시 합니다 (**DisplayName, 학과, UsageLocation 선택**).</span><span class="sxs-lookup"><span data-stu-id="c8d37-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="c8d37-125">특정 사용자 계정에 대 한 모든 속성을 보려면 **Select** cmdlet 및 와일드 카드 문자 (\*)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="c8d37-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="c8d37-127">또 다른 예로, 다음 명령을 실행 하 여 특정 사용자 계정의 사용 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="c8d37-128">계정 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-128">View account synchronization status</span></span>

<span data-ttu-id="c8d37-129">사용자 계정에는 다음과 같은 두 가지 원본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="c8d37-130">Windows Server AD (Active Directory)-온-프레미스 AD에서 클라우드로 동기화 되는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="c8d37-131">Azure AD (Active Directory) AD 계정 (클라우드에서 직접 만들어짐)</span><span class="sxs-lookup"><span data-stu-id="c8d37-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="c8d37-132">다음 명령은 *Dirsyncenabled* 특성이 *True*로 설정 된 모든 사용자를 가져오기 위해 PowerShell에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="c8d37-133">이를 사용 하 여 온-프레미스 AD와 동기화 되는 계정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="c8d37-134">다음 명령은 *Dirsyncenabled* 특성이 *False*로 설정 된 모든 사용자를 가져오기 위해 PowerShell에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="c8d37-135">이를 사용 하 여 클라우드 전용 계정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="c8d37-136">공통 속성을 기준으로 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-136">View accounts based on a common property</span></span>

<span data-ttu-id="c8d37-137">표시할 계정 목록을 보다 신중 하 게 선택 하려면 **Where** Cmdlet을 **AzureADUser** cmdlet과 함께 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="c8d37-138">두 cmdlet을 결합 하기 위해 Azure Active Directory PowerShell에는 그래프를 나타내는 "|" 문자를 사용 하 여 하나의 명령에 대 한 결과를 가져오고 다음 명령으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="c8d37-139">다음은 사용 위치가 지정 되지 않은 사용자 계정만 표시 하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="c8d37-140">이 명령은 다음과 같은 그래프에 Azure Active Directory PowerShell을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="c8d37-141">사용자 계정 (**AzureADUser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="c8d37-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="c8d37-142">사용 위치 (**여기서 {$)가 지정 되지 않은 모든 사용자 계정을 찾습니다 \_ . UsageLocation-eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="c8d37-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="c8d37-143">중괄호 내에서이 명령은 PowerShell에 UsageLocation 사용자 계정 속성 (을 사용 하는 경우에만 해당 계정 집합을 찾습니다\*\* $ \_ . UsageLocation**)이 지정 되지 않았습니다 (**-eq $Null\*\*).</span><span class="sxs-lookup"><span data-stu-id="c8d37-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="c8d37-144">**UsageLocation** 속성은 사용자 계정에 연결 된 여러 속성 중 하나에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="c8d37-145">특정 사용자 계정에 대 한 모든 속성을 표시 하려면 **Select** cmdlet 및 와일드 카드 문자 (\*)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="c8d37-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="c8d37-147">예를 들어 **도시명** 은 사용자 계정 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="c8d37-148">다음 명령을 사용 하 여 London에 거주 하는 모든 사용자의 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="c8d37-149">이러한 예의 **where** cmdlet에 대 한 구문은 여기에 해당 합니다 \*\* \_ .\*\*</span><span class="sxs-lookup"><span data-stu-id="c8d37-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="c8d37-150">[사용자 계정 속성 이름] [비교 연산자] 가치 **}**. > [비교 연산자]는 equals의 경우- **eq** , **-ne** = 같지 않음,-a = 부등호, **-lt** for a,- **gt** = 보다 작음, 기타 보다 작거나 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="c8d37-151">[값]은 일반적으로 문자열 (문자, 숫자 및 기타 문자의 시퀀스), 숫자 값 또는 **$Null** 지정 되지 않음에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="c8d37-152">자세한 내용은 [위치](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8d37-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c8d37-153">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="c8d37-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c8d37-154">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="c8d37-155">모든 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-155">View all accounts</span></span>

<span data-ttu-id="c8d37-156">사용자 계정의 전체 목록을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="c8d37-157">PowerShell Core에서는 이름에 *Msol* 이 포함 된 Windows powershell 모듈 및 cmdlet에 대 한 Microsoft Azure Active Directory 모듈을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c8d37-158">Windows PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="c8d37-159">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="c8d37-160">**Get-msoluser** cmdlet에도 매개 변수 집합이 있어 표시된 사용자 계정 집합을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="c8d37-161">예를 들어 라이선스가 없는 사용자 목록 (Microsoft 365에 추가 되었지만 아직 어떤 서비스를 사용 하도록 허가 되지 않은 사용자)의 경우에는 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="c8d37-162">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="c8d37-163">표시 되는 사용자 계정 집합을 필터링 하기 위한 추가 매개 변수에 대 한 자세한 내용은 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8d37-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="c8d37-164">특정 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-164">View a specific account</span></span>

<span data-ttu-id="c8d37-165">특정 사용자 계정을 표시 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="c8d37-166">UPN (사용자 계정 이름)이 라고도 하는 사용자 계정의 로그인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="c8d37-167">"<" 및 ">" 문자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="c8d37-168">공통 속성을 기준으로 계정 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-168">View accounts based on a common property</span></span>

<span data-ttu-id="c8d37-169">표시할 계정 목록을 보다 신중 하 게 선택 하려면 **Where** Cmdlet을 **get-msoluser** cmdlet과 함께 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="c8d37-170">두 cmdlet을 결합 하려면 "파이프" 문자 ("|")를 사용 하 여 PowerShell에 한 명령의 결과를 가져오고 다음 명령에 전송 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="c8d37-171">다음은 사용 위치가 지정 되지 않은 사용자 계정만 표시 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="c8d37-172">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c8d37-173">사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="c8d37-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="c8d37-174">사용 위치 (**여기서 {$)가 지정 되지 않은 모든 사용자 계정을 찾습니다. \_ UsageLocation-eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="c8d37-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="c8d37-175">중괄호 내에서이 명령은 PowerShell에 UsageLocation 사용자 계정 속성 (을 사용 하는 경우에만 사용 되는 계정 집합을 찾습니다\*\* $ \_ . UsageLocation**)이 지정 되지 않았습니다 (**-eq $Null\*\*).</span><span class="sxs-lookup"><span data-stu-id="c8d37-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="c8d37-176">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="c8d37-177">*UsageLocation* 속성은 사용자 계정에 연결 된 여러 속성 중 하나에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="c8d37-178">사용자 계정에 대 한 모든 속성을 보려면 **Select** cmdlet 및 와일드 카드 문자 (\*)를 사용 하 여 특정 사용자 계정에 대해 모두 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="c8d37-179">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="c8d37-180">예를 들어 *도시명* 은 사용자 계정 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="c8d37-181">다음 명령을 사용 하 여 London에 거주 하는 사용자에 대 한 모든 사용자 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="c8d37-182">이러한 예의 **where** cmdlet에 대 한 구문은 여기에 해당 합니다 \*\* \_ .\*\*</span><span class="sxs-lookup"><span data-stu-id="c8d37-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="c8d37-183">[사용자 계정 속성 이름] [비교 연산자] 가치 **}**.</span><span class="sxs-lookup"><span data-stu-id="c8d37-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="c8d37-184">[비교 연산자]는 equals의 경우- **eq** , **-ne** : 같지 않음,-a = 부등호, **-** a = 보다 작음,- **gt** for = 및 기타입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="c8d37-185">[값]은 일반적으로 문자열 (문자, 숫자 및 기타 문자의 시퀀스), 숫자 값 또는 **$Null** 지정 되지 않음에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="c8d37-186">자세한 내용은 [위치](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8d37-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="c8d37-187">사용자 계정의 차단 상태를 확인 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="c8d37-188">계정의 추가 속성 값 보기</span><span class="sxs-lookup"><span data-stu-id="c8d37-188">View additional property values for accounts</span></span>

<span data-ttu-id="c8d37-189">기본적으로 **get-msoluser** cmdlet은 다음과 같은 세 가지 사용자 계정 속성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="c8d37-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="c8d37-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="c8d37-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c8d37-191">DisplayName</span></span>
    
- <span data-ttu-id="c8d37-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="c8d37-192">isLicensed</span></span>
    
<span data-ttu-id="c8d37-193">사용자가 근무 하는 부서와 Microsoft 365 서비스를 사용 하는 국가/지역이 같은 추가 속성이 필요한 경우 **get-msoluser** 를 **Select** cmdlet과 함께 실행 하 여 사용자 계정 속성 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="c8d37-194">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="c8d37-195">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c8d37-196">사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 전송 **|** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="c8d37-197">사용자 계정 이름, 부서 및 사용 위치만 표시 합니다 (**DisplayName, 학과, UsageLocation 선택**).</span><span class="sxs-lookup"><span data-stu-id="c8d37-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="c8d37-198">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="c8d37-199">**Select** cmdlet을 사용 하 여 표시할 속성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="c8d37-200">특정 사용자 계정에 대 한 모든 속성을 표시 하려면 와일드 카드 문자 (\*)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="c8d37-201">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="c8d37-202">표시할 계정 목록에 대해 보다 신중 하 게 선택 하려면 **Where** cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="c8d37-203">다음은 사용 위치가 지정 되지 않은 사용자 계정만 표시 하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="c8d37-204">이 명령은 PowerShell에 다음을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c8d37-205">사용자 계정 (**get-msoluser**)에 대 한 모든 정보를 가져오고 다음 명령 ()으로 전송 **|** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="c8d37-206">사용 위치 (**여기서 {$)가 지정 되지 않은 모든 사용자 계정을 찾습니다. \_ UsageLocation-eq $Null}**)를 만들고 결과 정보를 다음 명령 ()로 보냅니다 **|** .</span><span class="sxs-lookup"><span data-stu-id="c8d37-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="c8d37-207">중괄호 내에서이 명령은 PowerShell에 UsageLocation 사용자 계정 속성 (을 사용 하는 경우에만 해당 계정 집합을 찾습니다\*\* $ \_ . UsageLocation**)이 지정 되지 않았습니다 (**-eq $Null\*\*).</span><span class="sxs-lookup"><span data-stu-id="c8d37-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="c8d37-208">사용자 계정 이름, 부서 및 사용 위치만 표시 합니다 (**DisplayName, 학과, UsageLocation 선택**).</span><span class="sxs-lookup"><span data-stu-id="c8d37-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="c8d37-209">다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="c8d37-210">디렉터리 동기화를 사용 하 여 Microsoft 365 사용자를 만들고 관리 하는 경우 Microsoft 365 사용자가 투영 된 로컬 계정을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="c8d37-211">다음 예제에서는 다음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-211">The following example assumes that:</span></span>

- <span data-ttu-id="c8d37-212">Azure AD Connect는 ObjectGUID의 기본 원본 앵커를 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d37-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="c8d37-213">원본 앵커를 구성 하는 방법에 대 한 자세한 내용은 [AZURE AD Connect: Design 개념도](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8d37-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="c8d37-214">PowerShell 용 Active Directory 도메인 서비스 모듈이 설치 되었습니다 ( [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)참조).</span><span class="sxs-lookup"><span data-stu-id="c8d37-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="c8d37-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8d37-215">See also</span></span>

[<span data-ttu-id="c8d37-216">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="c8d37-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c8d37-217">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="c8d37-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c8d37-218">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="c8d37-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

---
title: PowerShell을 통해 Microsoft 365 사용자 계정 보기
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
description: PowerShell을 통해 다양한 방식으로 Microsoft 365 사용자 계정을 보거나, 나열하거나, 표시하는 방법을 자세히 알아보는 방법을 배워야 합니다.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754075"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="ad0a1-103">PowerShell을 통해 Microsoft 365 사용자 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="ad0a1-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ad0a1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ad0a1-105">Microsoft 365 관리 센터를 사용하여 Microsoft 365 테넌트의 계정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="ad0a1-106">Microsoft 365용 PowerShell에서는 이 기능을 사용할 수 있지만 추가 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ad0a1-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ad0a1-108">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ad0a1-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="ad0a1-109">모든 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-109">View all accounts</span></span>

<span data-ttu-id="ad0a1-110">전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="ad0a1-111">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="ad0a1-112">특정 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-112">View a specific account</span></span>

<span data-ttu-id="ad0a1-113">특정 사용자 계정을 표시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="ad0a1-114">UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 계정 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="ad0a1-115">"<" 및 ">" 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="ad0a1-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="ad0a1-117">특정 계정에 대한 추가 속성 값 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-117">View additional property values for a specific account</span></span>

<span data-ttu-id="ad0a1-118">기본적으로 **Get-AzureADUser** cmdlet은 계정의 *ObjectID,* *DisplayName* 및 *UserPrincipalName* 속성만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="ad0a1-119">표시할 속성에 대해 보다 선택적으로 선택하려면 **Get-AzureADUser**  cmdlet과 함께 Select cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="ad0a1-120">두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Graph용 Azure Active Directory PowerShell에 한 명령의 결과를 받아 다음 명령으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="ad0a1-121">다음은 모든 사용자 계정에 대한 *DisplayName,* *Department* 및 *UsageLocation을* 표시하는 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="ad0a1-122">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ad0a1-123">사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="ad0a1-124">사용자 계정 이름, 부서 및 사용 **위치(DisplayName, Department, UsageLocation 선택)만 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="ad0a1-125">특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet과 와일드카드 문자(\*)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="ad0a1-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="ad0a1-127">다른 예로, 다음 명령을 실행하여 특정 사용자 계정의 사용 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="ad0a1-128">계정 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-128">View account synchronization status</span></span>

<span data-ttu-id="ad0a1-129">사용자 계정에는 다음 두 가지 원본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="ad0a1-130">Windows Server AD(Active Directory) - 클라우드로의 동기화 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="ad0a1-131">클라우드에서 직접 생성되는 Azure AD(Azure Active Directory) AD 계정</span><span class="sxs-lookup"><span data-stu-id="ad0a1-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="ad0a1-132">다음 명령은 *DirSyncEnabled* 특성이 True로 설정된 모든 사용자를 PowerShell에 *지시합니다.*</span><span class="sxs-lookup"><span data-stu-id="ad0a1-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="ad0a1-133">이 계정을 사용하여 이 계정을 사용하여 On-premise AD에서 동기화하는 계정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="ad0a1-134">다음 명령은 *DirSyncEnabled* 특성이 False로 설정된 모든 사용자를 PowerShell에 *지시합니다.*</span><span class="sxs-lookup"><span data-stu-id="ad0a1-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="ad0a1-135">이 계정을 사용하여 클라우드 전용 계정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="ad0a1-136">공통 속성을 기반으로 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-136">View accounts based on a common property</span></span>

<span data-ttu-id="ad0a1-137">표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 **Get-AzureADUser** cmdlet과 함께 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="ad0a1-138">두 cmdlet을 결합하기 위해 "파이프" 문자("|")를 사용하여 Graph용 Azure Active Directory PowerShell에 한 명령의 결과를 받아 다음 명령으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="ad0a1-139">다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="ad0a1-140">이 명령은 Graph용 Azure Active Directory PowerShell에 다음을 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="ad0a1-141">사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ad0a1-142">미지정 사용 위치(Where {$)가 있는 모든 사용자 **계정을 찾아야 \_ 합니다. UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="ad0a1-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="ad0a1-143">중괄호 안에 있는 명령은 UsageLocation 사용자 계정 속성(.**$ \_ UsageLocation**)이 지정되지 **않았습니다(-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="ad0a1-144">**UsageLocation 속성은** 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="ad0a1-145">특정 사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet과 와일드카드 문자(\*)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="ad0a1-146">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="ad0a1-147">예를 들어 **City는** 사용자 계정 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="ad0a1-148">다음 명령을 사용하여 런던에 거주하는 모든 사용자의 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="ad0a1-149">이 예제의 **Where** cmdlet 구문은 **Where {$ \_ 입니다.**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="ad0a1-150">[사용자 계정 속성 이름] [비교 연산자] [value] **}**.> [비교 연산자]는 **-eq이고,** 같지 않은 경우 **-ne,** **-lt이면 -lt,** 보다 크면 **-gt입니다.**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="ad0a1-151">[value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="ad0a1-152">자세한 내용은 [Where를 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="ad0a1-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ad0a1-153">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ad0a1-154">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ad0a1-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="ad0a1-155">모든 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-155">View all accounts</span></span>

<span data-ttu-id="ad0a1-156">전체 사용자 계정 목록을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="ad0a1-157">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="ad0a1-158">Windows PowerShell에서 이러한 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="ad0a1-159">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="ad0a1-160">**Get-msoluser** cmdlet에도 매개 변수 집합이 있어 표시된 사용자 계정 집합을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="ad0a1-161">예를 들어 허가되지 않은 사용자(Microsoft 365에 추가했지만 서비스를 사용할 수 있는 라이선스가 아직 부여되지 않은 사용자)의 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="ad0a1-162">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="ad0a1-163">표시되는 사용자 계정 집합을 필터링하는 추가 매개 변수에 대한 자세한 내용은 [Get-MsolUser를 참조하십시오.](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="ad0a1-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="ad0a1-164">특정 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-164">View a specific account</span></span>

<span data-ttu-id="ad0a1-165">특정 사용자 계정을 표시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="ad0a1-166">UPN(사용자 계정 이름)이라고도 하는 사용자 계정의 로그인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="ad0a1-167">"<" 및 ">" 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="ad0a1-168">공통 속성을 기반으로 계정 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-168">View accounts based on a common property</span></span>

<span data-ttu-id="ad0a1-169">표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 **Get-MsolUser** cmdlet과 함께 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="ad0a1-170">두 cmdlet을 결합하기 위해 PowerShell에 한 명령의 결과를 받아 다음 명령으로 보내라고 하는 "파이프" 문자("|")를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="ad0a1-171">다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="ad0a1-172">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ad0a1-173">사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ad0a1-174">미지정 사용 위치(Where {$)가 있는 모든 **사용자 계정을 찾아야 \_ 합니다. UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="ad0a1-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="ad0a1-175">중괄호 안에 있는 명령은 UsageLocation 사용자 계정 속성(.**$ \_ UsageLocation**)이 지정되지 **않았습니다(-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="ad0a1-176">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="ad0a1-177">*UsageLocation 속성은* 사용자 계정과 연결된 여러 속성 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="ad0a1-178">사용자 계정에 대한 모든 속성을 표시하려면 **Select** cmdlet 및 와일드카드 문자(\*)를 사용하여 특정 사용자 계정에 대한 모든 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="ad0a1-179">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="ad0a1-180">예를 들어 *City는* 사용자 계정 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="ad0a1-181">다음 명령을 사용하여 런던에 거주하는 사용자의 모든 사용자 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="ad0a1-182">이 예제의 **Where** cmdlet 구문은 **Where {$ \_ 입니다.**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="ad0a1-183">[사용자 계정 속성 이름] [비교 연산자] [value] **}**.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="ad0a1-184">[비교 연산자]는 **-eq(같음)** - **ne이면** 같음, **-lt는** 작음, **-gt는** 보다 크면 등입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="ad0a1-185">[value]는 일반적으로 문자열(문자, 숫자 및 기타 문자 시퀀스), 숫자 값  또는 지정되지 않은 $Null 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="ad0a1-186">자세한 내용은 [Where를 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="ad0a1-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="ad0a1-187">사용자 계정의 차단된 상태를 확인하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="ad0a1-188">계정에 대한 추가 속성 값 보기</span><span class="sxs-lookup"><span data-stu-id="ad0a1-188">View additional property values for accounts</span></span>

<span data-ttu-id="ad0a1-189">기본적으로 **Get-MsolUser** cmdlet은 사용자 계정의 다음 세 가지 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="ad0a1-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="ad0a1-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="ad0a1-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ad0a1-191">DisplayName</span></span>
    
- <span data-ttu-id="ad0a1-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="ad0a1-192">isLicensed</span></span>
    
<span data-ttu-id="ad0a1-193">사용자가 작업하는 부서, Microsoft 365 서비스를 사용하는 국가/지역 등의 추가 속성이 필요한 경우 Select cmdlet과 함께  **Get-MsolUser를** 실행하여 사용자 계정 속성 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="ad0a1-194">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="ad0a1-195">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ad0a1-196">사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ad0a1-197">사용자 계정 이름, 부서 및 사용 **위치(DisplayName, Department, UsageLocation 선택)만 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="ad0a1-198">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="ad0a1-199">Select  cmdlet을 사용하면 표시할 속성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="ad0a1-200">특정 사용자 계정에 대한 모든 속성을 표시하려면 와일드카드 문자(\*)를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="ad0a1-201">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="ad0a1-202">표시할 계정 목록에 대해 보다 선택적으로 선택하려면 **Where** cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="ad0a1-203">다음은 지정되지 않은 사용 위치가 있는 사용자 계정만 표시하는 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="ad0a1-204">이 명령은 PowerShell에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ad0a1-205">사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ad0a1-206">미지정 사용 위치(Where {$)가 있는 모든 **사용자 계정을 찾아야 \_ 합니다. UsageLocation -eq $Null}를** 사용하여 다음 명령()에 결과 정보를 **|** 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="ad0a1-207">중괄호 안에 있는 명령은 UsageLocation 사용자 계정 속성(.**$ \_ UsageLocation**)이 지정되지 **않았습니다(-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="ad0a1-208">사용자 계정 이름, 부서 및 사용 **위치(DisplayName, Department, UsageLocation 선택)만 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="ad0a1-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="ad0a1-209">다음 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="ad0a1-210">디렉터리 동기화를 사용하여 Microsoft 365 사용자를 만들고 관리하는 경우 Microsoft 365 사용자가 프로젝트된 로컬 계정을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="ad0a1-211">다음 예제에서는 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-211">The following example assumes that:</span></span>

- <span data-ttu-id="ad0a1-212">Azure AD Connect는 ObjectGUID의 기본 원본 앵커를 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0a1-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="ad0a1-213">원본 앵커 구성에 대한 자세한 내용은 [Azure AD Connect: 디자인 개념을 참조하세요.](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)</span><span class="sxs-lookup"><span data-stu-id="ad0a1-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="ad0a1-214">PowerShell용 Active Directory 도메인 서비스 모듈이 [설치되었습니다(RSAT 도구 참조).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)</span><span class="sxs-lookup"><span data-stu-id="ad0a1-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="ad0a1-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad0a1-215">See also</span></span>

[<span data-ttu-id="ad0a1-216">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="ad0a1-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ad0a1-217">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="ad0a1-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ad0a1-218">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="ad0a1-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

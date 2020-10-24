---
title: Microsoft 365 용 PowerShell을 사용해야 하는 이유
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: '요약: 일부 경우에는 필요한 경우 PowerShell을 사용 하 여 Microsoft 365을 관리 해야 하는 이유를 파악 합니다.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754109"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="195da-103">Microsoft 365 용 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="195da-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="195da-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="195da-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="195da-105">Microsoft 365 관리 센터를 사용 하 여 Microsoft 365 사용자 계정 및 라이선스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="195da-106">Exchange Online, 팀, SharePoint Online 등의 Microsoft 365 서비스를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="195da-107">대신 PowerShell을 사용 하 여 이러한 서비스를 관리 하는 경우에는 속도, 자동화 및 추가 기능에 대 한 명령줄 및 스크립팅 언어 환경을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="195da-108">이 문서에서는 PowerShell을 사용 하 여 Microsoft 365를 관리 하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="195da-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="195da-109">Microsoft 365 관리 센터에서 볼 수 없는 추가 정보 표시</span><span class="sxs-lookup"><span data-stu-id="195da-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="195da-110">PowerShell로 가능한 기능 및 설정 구성</span><span class="sxs-lookup"><span data-stu-id="195da-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="195da-111">대량 작업 수행</span><span class="sxs-lookup"><span data-stu-id="195da-111">Do bulk operations</span></span>
    
- <span data-ttu-id="195da-112">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="195da-112">Filter data</span></span>
    
- <span data-ttu-id="195da-113">데이터 인쇄 또는 저장</span><span class="sxs-lookup"><span data-stu-id="195da-113">Print or save data</span></span>
    
- <span data-ttu-id="195da-114">서비스 간 관리</span><span class="sxs-lookup"><span data-stu-id="195da-114">Manage across services</span></span>
    
<span data-ttu-id="195da-115">Microsoft 365에 대 한 PowerShell은 windows 기반 서비스 및 플랫폼에 대 한 명령줄 환경인 Windows PowerShell에 대 한 모듈 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="195da-116">이 환경에서는 추가 모듈을 사용 하 여 확장할 수 있는 명령 셸 언어를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="195da-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="195da-117">이를 통해 단순 하거나 복잡 한 명령이 나 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="195da-118">예를 들어 Microsoft 365 용 PowerShell 모듈을 설치 하 고 Microsoft 365 구독에 연결 하 고 나면 다음 명령을 실행 하 여 Microsoft Exchange Online에 대 한 모든 사용자 사서함을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="195da-119">Microsoft 365 관리 센터를 사용 하 여 사서함 목록을 가져올 수도 있지만 모든 웹 앱에 대 한 모든 사이트에 대 한 모든 목록의 항목을 계산 하기가 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="195da-120">Microsoft 365 용 PowerShell은 microsoft 365 관리를 지원 하기 위한 것으로, 마이크로소프트 365 관리 센터를 대체 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="195da-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="195da-121">Microsoft 365 용 PowerShell을 통해서만 수행할 수 있는 몇 가지 구성 프로시저가 있으므로 관리자는 Microsoft 365 PowerShell을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="195da-122">이러한 경우 다음 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="195da-123">Microsoft 365 용 PowerShell 모듈 (각 관리자 컴퓨터에 대해 한 번만 수행)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="195da-124">Microsoft 365 구독에 연결 (각 PowerShell 세션에 대해 한 번)</span><span class="sxs-lookup"><span data-stu-id="195da-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="195da-125">Microsoft 365 명령에 필요한 PowerShell을 실행 하는 데 필요한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="195da-126">Microsoft 365 명령에 대해 PowerShell을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="195da-127">이러한 기본 기술을 이해 **하 고 나면 mailbox 명령을 사용** 하 여 사서함 사용자를 나열할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="195da-128">또한 앞에서 설명한 명령과 같은 새 명령을 만들어 모든 웹 앱에 대 한 모든 사이트의 모든 목록에 포함 된 모든 항목의 수를 계산 하는 방법에 대해서도 이해할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="195da-129">Microsoft 및 관리자 커뮤니티는 필요에 따라 이러한 작업을 도와줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="195da-130">Microsoft 365 용 PowerShell을 사용 하면 Microsoft 365 관리 센터에서 볼 수 없는 정보를 드러낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="195da-131">Microsoft 365 관리 센터에는 여러 가지 유용한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="195da-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="195da-132">그러나 Microsoft 365에서 사용자, 라이선스, 사서함 및 사이트에 대해 저장 하는 모든 가능한 정보는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="195da-133">다음은 Microsoft 365 관리 센터의 *사용자 및 그룹* 에 대 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 관리 센터의 사용자 및 그룹 표시 예제입니다.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="195da-135">이 보기에서는 많은 경우에 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="195da-136">그러나 더 많은 정보가 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-136">However, there are times when you need more.</span></span> <span data-ttu-id="195da-137">예를 들어 Microsoft 365 라이선스 (및 사용자가 사용할 수 있는 Microsoft 365 기능)는 일부 사용자의 지리적 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="195da-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="195da-138">미국에 거주 하는 사용자에 게 확장할 수 있는 정책 및 기능은 인도 또는 벨기에에서 사용자에 게 확장할 수 있는 것과 같지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="195da-139">Microsoft 365 관리 센터에서 다음 단계를 수행 하 여 사용자의 지리적 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="195da-140">사용자의 **표시 이름** 을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="195da-141">사용자 속성 표시 창에서 **세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="195da-142">세부 정보 표시에서 **추가 세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="195da-143">다음과 같이 제목 **국가 또는 지역을**찾습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 관리 센터의 사용자에 대 한 지역 정보 예제입니다.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="195da-145">사용자의 표시 이름과 지역을 종이에 적어 두거나 복사한 다음 메모장에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="195da-146">각 사용자에 대해 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="195da-147">사용자 수가 많은 경우이 프로세스는 지루한 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="195da-148">Microsoft 365 용 PowerShell을 사용 하 여 다음 명령을 사용 하 여 모든 사용자에 대해이 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="195da-149">PowerShell Core는 Windows PowerShell 모듈에 대 한 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="195da-150">이러한 cmdlet은 Windows PowerShell에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="195da-151">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="195da-152">이 PowerShell 명령을 해석 하면 다음과 같습니다. 현재 Microsoft 365 구독 (**AzureADUser**)의 모든 사용자를 가져오고 각 사용자의 이름과 위치만 표시 합니다 (**DisplayName, UsageLocation 선택**).</span><span class="sxs-lookup"><span data-stu-id="195da-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="195da-153">PowerShell for Microsoft 365는 명령 셸 언어를 지원 하므로 **AzureADUser** 명령에 의해 얻은 정보를 보다 세부적으로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="195da-154">예를 들어 이러한 사용자를 위치에 따라 정렬 하 고 모든 브라질 사용자와 모든 미국 사용자를 함께 그룹화 하는 등의 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="195da-155">명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="195da-156">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="195da-157">이 PowerShell 명령을 사용 하는 경우에는 현재 Microsoft 365 구독의 모든 사용자를 가져오고, 각 사용자의 이름과 위치만 표시 하 고, 위치에 따라 먼저 정렬 한 다음 이름 (**Sort UsageLocation, DisplayName**)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="195da-158">추가 필터링을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-158">You can also use additional filtering.</span></span> <span data-ttu-id="195da-159">예를 들어 브라질 사용자에 대한 정보만 표시하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="195da-160">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="195da-161">이 PowerShell 명령을 해석 하면 다음과 같습니다. 현재 Microsoft 365 구독에서 위치가 브라질 인 모든 사용자 가져오기 (**여기서 {$ \_ . UsageLocation-eq "BR"}**)를 선택한 다음 각 사용자의 이름과 위치를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="195da-162">**대규모 도메인에 대 한 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="195da-162">**A note about large domains**</span></span>
  
<span data-ttu-id="195da-163">사용자 수가 수십 명 이상인 대규모 도메인을 사용 하는 경우이 문서에 나와 있는 몇 가지 예를 시도해도 제한을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="195da-164">컴퓨팅 파워 및 사용 가능한 네트워크 대역폭과 같은 요소를 기반으로 한 번에 너무 많은 작업을 수행 하려고 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="195da-165">대규모 조직에서는 이러한 PowerShell 작업 중 일부를 두 개의 명령으로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="195da-166">예를 들어 다음 명령은 모든 사용자 계정을 반환 하 고 각각의 이름과 위치를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="195da-167">소규모 도메인에서는 이 명령을 사용해도 아무런 문제가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-167">That works great for smaller domains.</span></span> <span data-ttu-id="195da-168">그러나 대규모 조직에서는 사용자 계정 정보를 변수에 저장 하는 명령, 그리고 필요한 정보를 표시 하는 두 개의 명령으로 해당 작업을 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="195da-169">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="195da-170">이 PowerShell 명령 집합을 해석 하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="195da-171">현재 Microsoft 365 구독의 모든 사용자를 가져오고이 정보를 $x (**$x = AzureADUser**) 라는 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="195da-172">*$X*변수의 내용을 표시 하지만 각 사용자의 이름과 위치만 포함 합니다 (**$x | DisplayName, UsageLocation)을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="195da-173">Microsoft 365에는 Microsoft 365 용 PowerShell을 사용 하 여 구성할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="195da-174">Microsoft 365 관리 센터는 대부분의 환경에 적용 되는 일반적인 유용한 관리 작업에 대 한 액세스를 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="195da-175">즉, Microsoft 365 관리 센터는 일반적인 관리자가 가장 일반적인 관리 작업을 수행할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="195da-176">하지만 관리 센터에서는 몇 가지 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="195da-177">예를 들어 비즈니스용 Skype 온라인 관리 센터에서는 사용자 지정 모임 초대를 만들기 위한 몇 가지 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![비즈니스용 Skype Online 관리 센터에 표시된 사용자 지정 모임 초대 예제입니다.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="195da-179">이러한 설정을 사용하여 모임 초대를 전문적으로 개인 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="195da-180">하지만 모임 구성 설정은 단순히 사용자 지정 모임 초대를 만드는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="195da-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="195da-181">예를 들어 모임에서는 기본적으로 다음과 같은 설정이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="195da-182">익명 사용자가 각 모임에 자동으로 입장할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="195da-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="195da-183">참석자가 모임을 기록하도록 설정</span><span class="sxs-lookup"><span data-stu-id="195da-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="195da-184">조직의 모든 사용자가 모임 참가 시 발표자로 지정되도록 설정</span><span class="sxs-lookup"><span data-stu-id="195da-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="195da-185">이러한 설정은 비즈니스용 Skype 온라인 관리 센터에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="195da-186">이러한 항목은 Microsoft 365 용 PowerShell에서 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="195da-187">다음은 이러한 세 가지 설정을 사용 하지 않도록 설정 하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="195da-188">이 명령을 실행 하려면 [비즈니스용 Skype Online PowerShell 모듈 ](https://www.microsoft.com/download/details.aspx?id=39366)을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="195da-189">이 PowerShell 명령을 해석 하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="195da-190">새 비즈니스용 Skype Online 모임에 대 한 설정 (**get-csmeetingconfiguration**)에서 익명 사용자가 모임에 자동으로 입장할 수 있도록 허용 (**-AdmitAnonymousUsersByDefault $False**)을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="195da-191">참석자가 모임을 기록 하는 기능을 사용 하지 않도록 설정 (**-AllowConferenceRecording $False**) 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="195da-192">조직의 모든 사용자를 발표자 (**-designateaspresenter "없음"**)로 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="195da-193">이러한 기본 설정을 복원 하려면 (옵션을 사용 하도록 설정) 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="195da-194">또한 관리자가 Microsoft 365 명령에 대해 PowerShell을 실행 하는 방법을 알고 있어야 하는 비슷한 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="195da-195">Microsoft 365 용 PowerShell은 대량 작업에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="195da-196">Microsoft 365 관리 센터와 같은 시각적 인터페이스는 작업을 한 번 수행할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="195da-197">예를 들어 하나의 사용자 계정을 사용 하지 않도록 설정 해야 하는 경우 관리 센터를 사용 하 여 확인란을 빠르게 찾아서 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="195da-198">이렇게 하면 PowerShell에서 비슷한 작업을 수행 하는 것 보다 더 쉽게 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="195da-199">그러나 많은 항목을 변경 해야 하는 경우 또는 다른 항목을 많이 선택 해야 하는 경우에는 Microsoft 365 관리 센터가 가장 적합 한 도구가 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="195da-200">예를 들어 수천 개의 전화 번호에 대 한 접두사를 변경 하거나 모든 SharePoint Online 사이트에서 특정 사용자 *Ken Myer* 을 제거 해야 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="195da-201">Microsoft 365 관리 센터에서이 작업을 수행 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="195da-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="195da-202">마지막 예제에서는 수백 개의 SharePoint Online 사이트가 있고, Ken 구 지 후가 구성원 인 경우를 모르는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="195da-203">Microsoft 365 관리 센터에서 시작한 다음 각 사이트에 대해이 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="195da-204">사이트의 **URL** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="195da-205">**사이트 모음 속성** 상자에서 **웹 사이트 주소** 링크를 선택 하 여 사이트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="195da-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="195da-206">사이트에서 **공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="195da-207">**공유** 대화 상자에서 사이트에 대 한 사용 권한이 있는 모든 사용자를 표시 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![SharePoint Online 관리 센터에서 SharePoint Online 사이트의 구성원을 보는 예제입니다.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="195da-209">**공유** 대화 상자에서 **고급**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="195da-210">사용자 목록을 아래로 스크롤하여 Ken Myer (사이트에 대 한 사용 권한을 갖고 있다고 가정)을 찾아 선택한 다음 **사용자 권한 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="195da-211">이 작업은 수백 개의 사이트에서 시간이 *오래* 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="195da-212">다른 방법은 Microsoft 365 PowerShell에 대해 다음 명령을 실행 하 여 모든 사이트에서 Ken Myer를 제거 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="195da-213">이 명령을 사용 하려면 [SharePoint Online PowerShell 모듈](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="195da-214">이 PowerShell 명령을 사용 하는 경우에는 현재 Microsoft 365 구독 (**get-sposite**) 및 각 사이트에 대해 모든 SharePoint 사이트 가져오기 Ken에 액세스할 수 있는 사용자 목록 (**ForEach {Remove-Spouser-site $)에서이를 제거 \_ 합니다. Url-LoginName "kenmyer \@ litwareinc.com"}**)</span><span class="sxs-lookup"><span data-stu-id="195da-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="195da-215">Microsoft 365는 모든 사이트에서 Ken 구 지 후를 제거 하는 것에 대 한 액세스 권한이 없는 것을 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="195da-216">따라서 결과에 액세스할 수 없는 사이트의 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="195da-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="195da-217">이 명령에 대 한 추가 조건을 사용 하 여 로그인 목록에 있는 사이트 에서만 Ken 구 지 후을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="195da-218">그러나 반환 되는 오류로 인해 사이트 자체가 손상 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="195da-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="195da-219">이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다 (Microsoft 365 관리 센터를 사용 하는 시간이 아님).</span><span class="sxs-lookup"><span data-stu-id="195da-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="195da-220">다른 대량 작업 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-220">Here's another bulk operation example.</span></span> <span data-ttu-id="195da-221">다음 명령을 사용 하 여 *Bonnie Kearney*, 새 SharePoint 관리자를 조직의 모든 사이트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="195da-222">이 PowerShell 명령에 대 한 해석은 현재 Microsoft 365 구독에 있는 모든 SharePoint 사이트를 가져오고 각 사이트에 대해 Bonnie Kearney access를 허용 합니다 (**ForEach {Add-SPOUser-site $ \_ ). Url-LoginName "bkearney \@ litwareinc.com"-Group "Members"}**)</span><span class="sxs-lookup"><span data-stu-id="195da-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="195da-223">Microsoft 365 용 PowerShell은 데이터를 필터링 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="195da-224">Microsoft 365 관리 센터에서는 정보를 대상으로 지정 된 하위 집합을 쉽게 찾을 수 있도록 데이터를 필터링 하는 여러 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="195da-225">예를 들어 Exchange에서는 사용자 사서함의 사실상 모든 속성을 기준으로 쉽게 필터링을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="195da-226">예를 들어 Bloomington의 구/군/시에 거주 하는 모든 사용자의 사서함 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Bloomington의 구/군/시에 거주 하는 모든 사용자의 사서함 목록에 대해 Microsoft 365 관리 센터에서 고급 검색을 수행 하는 방법의 예입니다.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="195da-228">Exchange 관리 센터에서도 필터 기준을 조합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="195da-229">예를 들어 Bloomington에 살고 있고 재무 부서에서 근무 하는 모든 사용자의 사서함을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="195da-230">그러나 Exchange 관리 센터에서 수행할 수 있는 작업에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="195da-231">예를 들어 Bloomington *또는* San Diego에 거주 하는 사용자의 사서함 이나 Bloomington에 살고 있지 않은 모든 사용자의 사서함을 쉽게 찾을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="195da-232">다음 PowerShell for Microsoft 365 명령을 사용 하 여 Bloomington 또는 San Diego에 거주 하는 모든 사용자에 대 한 사서함 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="195da-233">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="195da-234">이 PowerShell 명령을 해석 하면 다음과 같습니다. San Diego 또는 Bloomington (**여기서 {$)의 도시에 사서함이 있는 현재 Microsoft 365 구독의 모든 사용자를 가져옵니다. \_ RecipientTypeDetails-eq "UserMailbox" and ($ \_ . 도시-eq "San Diego"- \_ 또는 $ City-eq "Bloomington")}**)를 선택 하 고 각각의 이름과 구/군/시 (**DisplayName, city**)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="195da-235">다음은 Bloomington를 제외한 임의의 위치에 거주 하는 사용자의 모든 사서함을 나열 하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="195da-236">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="195da-237">이 PowerShell 명령을 해석 하면 다음이 제공 됩니다. Bloomington (**여기서 {$)의 도시에 없는 사서함이 있는 현재 Microsoft 365 구독의 모든 사용자를 가져옵니다. \_ RecipientTypeDetails-eq "UserMailbox"- \_ 및 $ City-ne "Bloomington"}**)를 선택한 다음 각각에 대 한 이름과 구/군/시를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="195da-238">와일드 카드 사용</span><span class="sxs-lookup"><span data-stu-id="195da-238">Use wildcards</span></span>

<span data-ttu-id="195da-239">또한 PowerShell 필터에서 와일드 카드 문자를 사용 하 여 이름의 일부를 일치 시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="195da-240">예를 들어 사용자 계정을 찾고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="195da-241">사용자의 성이 *Anderson* 또는 *Henderson* 또는 *jorgenson*일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="195da-242">검색 도구를 사용 하 고 다음과 같은 세 가지 다른 검색을 수행 하 여 Microsoft 365 관리 센터에서 해당 사용자에 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="195da-243">*Anderson*  에 대해,</span><span class="sxs-lookup"><span data-stu-id="195da-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="195da-244">*Henderson*  에 대해,</span><span class="sxs-lookup"><span data-stu-id="195da-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="195da-245">*Jorgenson*  에 대해</span><span class="sxs-lookup"><span data-stu-id="195da-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="195da-246">이 세 가지 이름이 모두 "son"으로 끝나는 것 이므로 PowerShell을 통해 이름이 "son"으로 끝나는 모든 사용자를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="195da-247">명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="195da-248">이 PowerShell 명령을 사용 하는 경우에는 현재 Microsoft 365 구독의 모든 사용자를 가져오고, 마지막 이름이 "son" (**-filter ' {LastName \* "} '**)으로 끝나는 사용자만 나열 하는 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="195da-249">는 \* 사용자의 성에 있는 문자 집합을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="195da-250">Microsoft 365 용 PowerShell을 사용 하면 데이터를 쉽게 인쇄 하거나 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="195da-251">Microsoft 365 관리 센터를 사용 하 여 데이터 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="195da-252">다음은 비즈니스용 Skype 온라인을 사용 하도록 설정 된 사용자 목록을 표시 하는 비즈니스용 Skype Online 관리 센터의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![비즈니스용 Skype Online을 사용하도록 설정된 사용자 목록을 표시하는 비즈니스용 Skype Online 관리 센터 예제입니다.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="195da-254">해당 정보를 파일에 저장 하려면 문서 또는 Microsoft Excel 워크시트에 붙여 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="195da-255">어떤 경우 든 추가 서식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-255">Either case might require additional formatting.</span></span> <span data-ttu-id="195da-256">또한 Microsoft 365 관리 센터에서 표시 된 목록을 직접 인쇄 하는 방법을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="195da-257">다행히 PowerShell을 사용 하 여 목록을 표시할 뿐만 아니라 쉽게 Excel로 가져올 수 있는 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="195da-258">다음은 비즈니스용 Skype Online 사용자 데이터를 쉼표로 구분 된 값 (CSV) 파일에 저장 하 고 Excel 워크시트에서 표로 쉽게 가져올 수 있도록 하는 명령 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="195da-259">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-259">Here's an example of the results:</span></span>
  
![쉼표로 구분 된 값 파일에 저장 된 비즈니스용 Skype Online 사용자 데이터를 Excel 워크시트로 가져온 테이블의 예입니다.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="195da-261">이 PowerShell 명령을 해석 하면 다음과 같습니다. 현재 Microsoft 365 구독 (**get-csonlineuser**)에서 비즈니스용 Skype 온라인 사용자를 모두 가져옵니다. 사용자 이름, UPN 및 위치 (**DisplayName, UserPrincipalName, UsageLocation 선택**)를 가져옵니다. 그런 다음 C: \\ logs \\SfBUsers.csv (**내보내기-csv-Path "c: \\ Logs \\SfBUsers.csv"-NOTYPEINFORMATION**) 라는 CSV 파일에 해당 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="195da-262">옵션을 사용 하 여이 목록을 XML 파일 또는 HTML 페이지로 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="195da-263">실제로 추가 PowerShell 명령을 사용 하 여 원하는 사용자 지정 서식과 함께 Excel 파일로 직접 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="195da-264">목록을 표시 하는 PowerShell 명령의 출력을 Windows의 기본 프린터로 직접 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="195da-265">명령 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="195da-266">인쇄된 문서의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-266">Here's what your printed document will look like:</span></span>
  
![Windows의 기본 프린터로 직접 전송 되는 PowerShell 명령 출력의 인쇄 된 문서 예제입니다.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="195da-268">이 PowerShell 명령을 해석 하면 다음과 같습니다. 현재 Microsoft 365 구독에서 비즈니스용 Skype 온라인 사용자를 모두 가져옵니다. 사용자 이름, UPN 및 위치만 가져옵니다. 를 선택한 다음 해당 정보를 기본 Windows 프린터 (**외부 프린터**)로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="195da-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="195da-269">문서를 인쇄 하면 PowerShell 명령 창에 표시 되는 것과 같은 간단한 서식이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="195da-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="195da-270">하드 카피를 가져오려면 |을 추가 하세요. \*\* 외부-프린터\*\* 를 명령 끝까지 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="195da-271">Microsoft 365 용 PowerShell을 사용 하면 서버 제품에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="195da-272">Microsoft 365 구성 요소는 함께 작동 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="195da-273">예를 들어 Microsoft 365에 새 사용자를 추가 하 고 사용자의 부서 및 전화 번호로 이러한 정보를 지정 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="195da-274">이 정보는 Microsoft 365 서비스 (비즈니스용 Skype Online, Exchange 또는 SharePoint)에서 사용자 정보에 액세스할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="195da-275">그러나 이러한 방식은 제품군 전체에 적용되는 일반적인 정보에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="195da-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="195da-276">사용자의 Exchange 사서함에 대 한 정보와 같은 제품별 정보는 대개 제품군 전체에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="195da-277">예를 들어 사용자의 사서함이 사용 하도록 설정 되었는지 여부에 대 한 정보는 Exchange 관리 센터 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="195da-278">모든 사용자에 대해 다음 정보를 표시하는 보고서를 만들려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="195da-279">사용자의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="195da-279">The user's display name</span></span>
    
- <span data-ttu-id="195da-280">사용자에 게 Microsoft 365에 대 한 라이선스가 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="195da-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="195da-281">사용자의 Exchange 사서함이 사용하도록 설정되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="195da-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="195da-282">사용자가 비즈니스용 Skype 온라인을 사용할 수 있도록 설정되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="195da-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="195da-283">이러한 보고서는 Microsoft 365 관리 센터에서 쉽게 작성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="195da-284">대신 Excel 워크시트와 같은 정보를 저장할 별도의 문서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="195da-285">그런 다음 Microsoft 365 관리 센터에서 모든 사용자 이름 및 라이선스 정보를 가져오고, Exchange 관리 센터에서 사서함 정보를 가져오고, 비즈니스용 skype Online 관리 센터에서 비즈니스용 Skype Online 정보를 얻고, 해당 정보를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="195da-286">다른 방법은 PowerShell 스크립트를 사용 하 여 보고서를 컴파일하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="195da-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="195da-287">다음 예제 스크립트는이 문서에서 지금까지 살펴본 명령 보다 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="195da-288">그러나 PowerShell을 사용 하 여 정보 보기를 만드는 것이 어려운 경우에는이를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="195da-289">필요한 목록을 컴파일하고 표시 하는 스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="195da-290">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="195da-291">이 PowerShell 스크립트를 해석 하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="195da-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="195da-292">현재 Microsoft 365 구독의 모든 사용자를 가져오고 해당 정보를 *$x* (**$x = AzureADUser**) 라는 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="195da-293">$X 변수의 모든 사용자에 대해 실행 되는 루프를 시작 합니다 (**foreach ($x의 $i**)).</span><span class="sxs-lookup"><span data-stu-id="195da-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="195da-294">*$Y* 라는 변수를 정의 하 고이 변수에 사용자의 사서함 정보를 저장 합니다 (**$y = Get-Mailbox-$i Identity UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="195da-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="195da-295">이름이 *IsMailBoxEnabled*인 사용자 정보에 새 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="195da-296">사용자 사서함의 IsMailBoxEnabled 속성 값으로 설정 합니다 (**$i | Add-Member-MemberType IsMailBoxEnabled-value $y. IsMailBoxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="195da-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="195da-297">*$Y*라는 변수를 정의 하 고이 변수에 사용자의 비즈니스용 Skype Online 정보를 저장 합니다 (**$y = Get-CsOnlineUser-$i Identity UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="195da-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="195da-298">이름이 *EnabledForSfB*인 사용자 정보에 새 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="195da-299">사용자의 비즈니스용 Skype Online 정보에 대 한 Enabled 속성의 값으로 설정 합니다 (**$i | Add-Member-MemberType EnabledForSfB-Name-value $y. 사용**).</span><span class="sxs-lookup"><span data-stu-id="195da-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="195da-300">사용자의 목록을 표시 하 되 해당 이름은 사용이 허가 되었는지 여부와 사서함을 사용 하도록 설정 되어 있는지 여부를 나타내는 새 속성 두 개와 온라인 비즈니스용 Skype에 대해 사용 하도록 설정 되었는지 여부와 같은 새로운 속성이 포함 되어 있습니다 (**$x | DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="195da-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="195da-301">참고 항목</span><span class="sxs-lookup"><span data-stu-id="195da-301">See also</span></span>

[<span data-ttu-id="195da-302">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="195da-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="195da-303">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="195da-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="195da-304">Microsoft 365에서 Windows PowerShell을 사용하여 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="195da-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

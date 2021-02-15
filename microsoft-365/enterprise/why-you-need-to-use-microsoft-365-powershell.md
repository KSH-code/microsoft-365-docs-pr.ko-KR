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
description: '요약: PowerShell을 사용하여 Microsoft 365를 관리해야 하는 이유를 이해합니다. 경우에 따라 더 효율적일 수도 있으며, 필요한 경우도 있습니다.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754109"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="9b353-103">Microsoft 365 용 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="9b353-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="9b353-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="9b353-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9b353-105">Microsoft 365 관리 센터를 사용하여 Microsoft 365 사용자 계정 및 라이선스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="9b353-106">Exchange Online, Teams 및 SharePoint Online과 같은 Microsoft 365 서비스를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="9b353-107">대신 PowerShell을 사용하여 이러한 서비스를 관리하는 경우 명령줄 및 스크립팅 언어 환경을 사용하여 속도, 자동화 및 추가 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="9b353-108">이 문서에서는 PowerShell을 사용하여 Microsoft 365를 관리하는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="9b353-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="9b353-109">Microsoft 365 관리 센터에서 볼 수 없는 추가 정보 표시</span><span class="sxs-lookup"><span data-stu-id="9b353-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="9b353-110">PowerShell에서만 가능한 기능 및 설정 구성</span><span class="sxs-lookup"><span data-stu-id="9b353-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="9b353-111">대량 작업 수행</span><span class="sxs-lookup"><span data-stu-id="9b353-111">Do bulk operations</span></span>
    
- <span data-ttu-id="9b353-112">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="9b353-112">Filter data</span></span>
    
- <span data-ttu-id="9b353-113">데이터 인쇄 또는 저장</span><span class="sxs-lookup"><span data-stu-id="9b353-113">Print or save data</span></span>
    
- <span data-ttu-id="9b353-114">여러 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="9b353-114">Manage across services</span></span>
    
<span data-ttu-id="9b353-115">Microsoft 365용 PowerShell은 Windows 기반 서비스 및 플랫폼을 위한 명령줄 환경인 Windows PowerShell 모듈 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="9b353-116">이 환경에서는 추가 모듈을 사용하여 확장할 수 있는 명령 셸 언어를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="9b353-117">간단한 명령이나 복잡한 명령이나 스크립트를 실행할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="9b353-118">예를 들어 Microsoft 365 모듈용 PowerShell을 설치하고 Microsoft 365 구독에 연결한 후 다음 명령을 실행하여 해당 모듈의 모든 사용자 사서함을 Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9b353-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="9b353-119">Microsoft 365 관리 센터를 사용하여 사서함 목록을 얻을 수도 있지만 모든 웹앱에 대한 모든 사이트의 모든 목록에서 항목을 계산하는 것은 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="9b353-120">Microsoft 365용 PowerShell은 Microsoft 365 관리 센터를 대체하지 말고 Microsoft 365를 관리하는 데 도움이 하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="9b353-121">Microsoft 365 명령에 대해 PowerShell을 통해서만 수행될 수 있는 몇 가지 구성 절차가 있기 때문에 관리자는 Microsoft 365용 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="9b353-122">이러한 경우 다음 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="9b353-123">Microsoft 365 모듈용 PowerShell을 설치합니다(각 관리자 컴퓨터에 대해 한 번만 수행).</span><span class="sxs-lookup"><span data-stu-id="9b353-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="9b353-124">Microsoft 365 구독에 연결합니다(각 PowerShell 세션에 대해 한 번).</span><span class="sxs-lookup"><span data-stu-id="9b353-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="9b353-125">Microsoft 365 명령에 필요한 PowerShell을 실행하는 데 필요한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="9b353-126">Microsoft 365 명령에 대해 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="9b353-127">이러한 기본 기술을 학습한 후 **Get-Mailbox** 명령을 사용하여 사서함 사용자를 나열할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="9b353-128">또한 모든 웹앱에 대한 모든 사이트의 모든 목록에 있는 모든 항목의 개수를 계산하기 위해 이전에 인용한 명령과 같은 새 명령을 만드는 방법을 이해할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="9b353-129">Microsoft와 관리자 커뮤니티는 필요한 경우 이러한 작업을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="9b353-130">Microsoft 365용 PowerShell은 Microsoft 365 관리 센터에서 볼 수 없는 정보를 공개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="9b353-131">Microsoft 365 관리 센터에는 많은 유용한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="9b353-132">그러나 Microsoft 365에서 사용자, 라이선스, 사서함 및 사이트에 대해 저장하는 가능한 모든 정보는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="9b353-133">Microsoft 365  관리 센터의 사용자 및 그룹에 대한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 관리 센터의 사용자 및 그룹 표시 예](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="9b353-135">이 보기는 많은 경우에 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="9b353-136">그러나 더 많은 정보가 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-136">However, there are times when you need more.</span></span> <span data-ttu-id="9b353-137">예를 들어 Microsoft 365 라이선싱(및 사용자가 사용할 수 있는 Microsoft 365 기능)은 사용자의 지리적 위치에 따라 부분적으로 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="9b353-138">미국에 거주하는 사용자에게 확장할 수 있는 정책 및 기능은 인도나 벨기에의 사용자로 확장할 수 있는 정책과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="9b353-139">Microsoft 365 관리 센터에서 다음 단계에 따라 사용자의 지리적 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="9b353-140">사용자의 **표시 이름** 을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="9b353-141">사용자 속성 표시 창에서 세부 **정보를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="9b353-142">세부 정보 표시에서 추가 **세부 정보를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="9b353-143">제목 국가 또는 지역을 찾을 때까지 **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 관리 센터의 사용자에 대한 지역 정보의 예](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="9b353-145">사용자의 표시 이름과 지역을 종이에 적어 두거나 복사한 다음 메모장에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="9b353-146">각 사용자에 대해 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="9b353-147">사용자가 많은 경우 이 프로세스는 지저분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="9b353-148">Microsoft 365용 PowerShell을 사용하면 다음 명령을 사용하여 모든 사용자에 대해 이 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="9b353-149">PowerShell Core는 이름에 *Msol이* 있는 Windows PowerShell 및 cmdlet용 Microsoft Azure Active Directory 모듈을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="9b353-150">이러한 cmdlet은 해당 cmdlet에서 실행해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b353-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="9b353-151">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="9b353-152">이 PowerShell 명령을 해석하면 다음이 있습니다. 현재 Microsoft 365 구독의 모든 사용자를 **다운로드(Get-AzureADUser)하지만** 각 사용자의 이름과 위치만 **표시합니다(DisplayName 선택, UsageLocation** 선택).</span><span class="sxs-lookup"><span data-stu-id="9b353-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="9b353-153">Microsoft 365용 PowerShell은 명령 셸 언어를 지원하기 때문에 **Get-AzureADUser** 명령으로 얻은 정보를 추가로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="9b353-154">예를 들어 이러한 사용자를 위치별로 정렬하여 모든 브라질 사용자, 모든 미국 사용자를 함께 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="9b353-155">명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="9b353-156">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="9b353-157">이 PowerShell 명령을 해석하면: 현재 Microsoft 365 구독의 모든 사용자를 되지만 각 사용자의 이름과 위치만 표시하고 먼저 위치별로 정렬한 다음 **이름(Sort UsageLocation, DisplayName)을** 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="9b353-158">추가 필터링을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-158">You can also use additional filtering.</span></span> <span data-ttu-id="9b353-159">예를 들어 브라질 사용자에 대한 정보만 표시하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="9b353-160">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="9b353-161">이 PowerShell 명령을 해석하면 다음이 있습니다. 현재 Microsoft 365 구독의 모든 사용자를 해당 위치가 **브라질(Where {$ ) 으로 해석합니다. \_ UsageLocation -eq "BR"}**)을 입력한 다음 각 사용자의 이름과 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="9b353-162">**큰 도메인에 대한 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="9b353-162">**A note about large domains**</span></span>
  
<span data-ttu-id="9b353-163">사용자가 수만 명인 큰 도메인이 있는 경우 이 문서에 설명된 예제 중 일부를 시도하면 스로틀이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="9b353-164">컴퓨팅 전원 및 사용 가능한 네트워크 대역폭과 같은 요인에 따라 한 때 너무 많은 작업을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="9b353-165">대규모 조직에서는 이러한 PowerShell 작업 중 일부를 두 개의 명령으로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="9b353-166">예를 들어 다음 명령은 모든 사용자 계정을 반환하고 각 계정의 이름과 위치를 보여줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="9b353-167">소규모 도메인에서는 이 명령을 사용해도 아무런 문제가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-167">That works great for smaller domains.</span></span> <span data-ttu-id="9b353-168">그러나 대규모 조직에서는 해당 작업을 두 개의 명령, 즉 사용자 계정 정보를 변수에 저장하는 명령과 필요한 정보를 표시하는 명령으로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="9b353-169">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="9b353-170">이 PowerShell 명령 집합을 해석하는 것은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="9b353-171">현재 Microsoft 365 구독의 모든 사용자를 다운로드하고 정보를 $x($x **= Get-AzureADUser)라는 변수에 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="9b353-172">변수의 내용을 $x 각 사용자의 이름과 위치만 **포함합니다($x | DisplayName, UsageLocation을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="9b353-173">Microsoft 365에는 Microsoft 365용 PowerShell로만 구성할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="9b353-174">Microsoft 365 관리 센터는 대부분의 환경에 적용되는 일반적이고 유용한 관리 작업에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="9b353-175">즉, Microsoft 365 관리 센터는 일반적인 관리자가 가장 일반적인 관리 작업을 수행할 수 있도록 디자인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="9b353-176">그러나 관리 센터에서 수행할 수 없는 몇 가지 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="9b353-177">예를 들어 비즈니스용 Skype Online 관리 센터에서는 사용자 지정 모임 초대를 만들기 위한 몇 가지 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![비즈니스용 Skype Online 관리 센터에 표시된 사용자 지정 모임 초대 예제입니다.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="9b353-179">이러한 설정을 사용하여 모임 초대를 전문적으로 개인 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="9b353-180">그러나 모임 구성 설정에는 단순히 사용자 지정 모임 초대를 만드는 것 이상이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="9b353-181">예를 들어 모임에서는 기본적으로 다음과 같은 설정이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="9b353-182">익명 사용자가 각 모임에 자동으로 입장할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="9b353-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="9b353-183">참석자가 모임을 기록하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9b353-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="9b353-184">조직의 모든 사용자가 모임 참가 시 발표자로 지정되도록 설정</span><span class="sxs-lookup"><span data-stu-id="9b353-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="9b353-185">이러한 설정은 비즈니스용 Skype Online 관리 센터에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="9b353-186">Microsoft 365용 PowerShell에서 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="9b353-187">다음은 이러한 세 가지 설정을 사용하지 않도록 설정하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="9b353-188">이 명령을 실행하려면 비즈니스용 [Skype Online PowerShell 모듈을 설치해야 합니다. ](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="9b353-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="9b353-189">이 PowerShell 명령을 해석하는 것은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="9b353-190">새 비즈니스용 Skype Online 모임 **설정(Set-CsMeetingConfiguration)에서** 익명 사용자가 모임에 자동 입장할 수 있도록 허용하지 않도록 **설정(-AdmitAnonymousUsersByDefault $False).**</span><span class="sxs-lookup"><span data-stu-id="9b353-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="9b353-191">참석자에 모임을 기록할 수 있는 기능을 사용하지 않도록 **설정(-AllowConferenceRecording $False).**</span><span class="sxs-lookup"><span data-stu-id="9b353-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="9b353-192">조직의 모든 사용자를 **발표자(-DesignateAsPresenter "없음")로 지정하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="9b353-193">이러한 기본 설정을 복원하려면(옵션을 사용하도록 설정) 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="9b353-194">다른 유사한 시나리오도 있습니다. 따라서 관리자가 Microsoft 365 명령에 대해 PowerShell을 실행하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="9b353-195">Microsoft 365용 PowerShell은 대량 작업에 매우 잘 사용</span><span class="sxs-lookup"><span data-stu-id="9b353-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="9b353-196">Microsoft 365 관리 센터와 같은 시각적 인터페이스는 단일 작업을 할 때 가장 유용한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="9b353-197">예를 들어 사용자 계정 하나를 사용하지 않도록 설정해야 하는 경우 관리 센터를 사용하여 확인란을 빠르게 찾아 선택을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="9b353-198">이 작업은 PowerShell에서 유사한 작업을 수행하는 것보다 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="9b353-199">그러나 대규모 작업 내에서 많은 것 또는 일부 선택된 것을 변경해야 하는 경우 Microsoft 365 관리 센터가 최상의 도구가 아 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="9b353-200">예를 들어 수천 개의 전화 번호에 대한 prefix를 변경하거나 모든 SharePoint Online 사이트에서 특정 사용자 *Ken Myer를* 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="9b353-201">Microsoft 365 관리 센터에서는 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="9b353-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="9b353-202">마지막 예제에서는 SharePoint Online 사이트가 수백 개 있으며 Ken Meyer가 구성원으로 있는 사이트를 모르는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="9b353-203">Microsoft 365 관리 센터에서 시작한 다음 각 사이트에 대해 다음 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="9b353-204">사이트의 **URL을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="9b353-205">사이트 **모음 속성 상자에서** 사이트를 **열 웹** 사이트 주소 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="9b353-206">사이트에서 공유를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="9b353-207">공유 **대화** 상자에서 사이트에 대한 사용 권한이 있는 모든 사용자를 표시하는 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![SharePoint Online 관리 센터에서 SharePoint Online 사이트의 구성원을 보는 예제입니다.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="9b353-209">공유 대상 **대화** 상자에서 고급을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="9b353-210">사용자 목록을 아래로 스크롤하여 Ken Myer를 찾아 선택한 다음(사이트에 대한 사용 권한이 있는 경우) 사용자 권한 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="9b353-211">수백 개의 *사이트에는* 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="9b353-212">또는 Microsoft 365용 PowerShell에서 다음 명령을 실행하여 모든 사이트에서 Ken Myer를 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="9b353-213">이 명령을 사용하려면 [SharePoint Online PowerShell 모듈을 설치해야 합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="9b353-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="9b353-214">이 PowerShell 명령을 해석하면: 현재 Microsoft 365 **구독(Get-SPOSite)의** 모든 SharePoint 사이트를 다운로드하고 각 사이트에 대해 액세스할 수 있는 사용자 목록에서 Ken **Meyer를 제거합니다(ForEach {Remove-SPOUser -Site $ \_ ). Url -LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="9b353-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="9b353-215">Microsoft 365에 액세스 권한이 없는 사이트를 포함하여 모든 사이트에서 Ken Meyer를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="9b353-216">따라서 결과에는 액세스 권한이 없는 사이트에 대한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="9b353-217">이 명령에서 추가 조건을 사용하여 로그인 목록에 Ken Meyer가 있는 사이트에서만 Ken Meyer를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="9b353-218">그러나 반환되는 오류는 사이트 자체에 해를 입히지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="9b353-219">이 명령은 Microsoft 365 관리 센터를 통해 작업하는 시간이 아니라 수백 개의 사이트에 대해 실행하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="9b353-220">다음은 다른 대량 작업 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-220">Here's another bulk operation example.</span></span> <span data-ttu-id="9b353-221">다음 명령을 사용하여 새 SharePoint 관리자인 *Bonnie Kearney를* 조직의 모든 사이트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="9b353-222">이 PowerShell 명령을 해석하면: 현재 Microsoft 365 구독의 모든 SharePoint 사이트를 다운로드하고 각 사이트에 대해 사이트의 구성원 그룹에 로그인 이름을 추가하여 Bonnie Kearney 액세스를 **허용합니다(ForEach {Add-SPOUser -Site $ \_ ). Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="9b353-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="9b353-223">Microsoft 365용 PowerShell은 데이터를 필터링하는 데 매우 능동적입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="9b353-224">Microsoft 365 관리 센터에서는 데이터를 필터링하여 대상 정보 하위 집합을 쉽게 찾을 수 있는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="9b353-225">예를 들어 Exchange에서는 사용자 사서함의 사실상 모든 속성을 기준으로 쉽게 필터링을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="9b353-226">예를 들어 Bloomington에 거주하는 모든 사용자의 사서함 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Microsoft 365 관리 센터에서 Bloomington에 거주하는 모든 사용자의 사서함 목록에 대한 고급 검색을 수행한 예입니다.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="9b353-228">Exchange 관리 센터에서도 필터 기준을 조합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="9b353-229">예를 들어 Bloomington에 거주하고 Finance 부서에서 일하는 모든 사용자에 대한 사서함을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="9b353-230">그러나 Exchange 관리 센터에서 할 수 있는 작업을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="9b353-231">예를 들어 Bloomington이나 San Diego에 거주하는 사용자 사서함이나  Bloomington에 거주하지 않는 모든 사용자에 대한 사서함을 쉽게 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="9b353-232">다음 Microsoft 365용 PowerShell 명령을 사용하여 Bloomington 또는 San Diego에 거주하는 모든 사용자에 대한 사서함 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="9b353-233">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="9b353-234">이 PowerShell 명령을 해석하면 다음이 적용됩니다. San Diego 또는 Bloomington(Where **{$ . \_ RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . City -eq "San Diego" -or $ \_ . City -eq "Bloomington")}** 을 입력한 다음 각 구/시의 이름과 구/시(Select **DisplayName, City)를 표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="9b353-235">Bloomington을 제외한 모든 곳에 거주하는 사람에 대한 모든 사서함을 나열하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="9b353-236">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="9b353-237">이 PowerShell 명령을 해석하면 다음이 적용됩니다. Bloomington에 사서함이 없는 현재 Microsoft 365 구독의 모든 **사용자(Where {$ \_ ). RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**) 각 구/시의 이름과 구/시를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="9b353-238">와일드카드 사용</span><span class="sxs-lookup"><span data-stu-id="9b353-238">Use wildcards</span></span>

<span data-ttu-id="9b353-239">PowerShell 필터에서 와일드카드 문자를 사용하여 이름의 일부와 일치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="9b353-240">예를 들어 사용자 계정을 찾고 있는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="9b353-241">사용자의 성은 *Anderson* 또는 *Henderson* 또는 *Jorgenson입니다.*</span><span class="sxs-lookup"><span data-stu-id="9b353-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="9b353-242">검색 도구를 사용하고 세 가지 다른 검색을 수행하여 Microsoft 365 관리 센터에서 해당 사용자를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="9b353-243">*Anderson*  에 대해,</span><span class="sxs-lookup"><span data-stu-id="9b353-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="9b353-244">*Henderson*  에 대해,</span><span class="sxs-lookup"><span data-stu-id="9b353-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="9b353-245">*Jorgenson*  에 대해</span><span class="sxs-lookup"><span data-stu-id="9b353-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="9b353-246">이 세 이름은 모두 "son"으로 끝나기 때문에 PowerShell에 이름이 "son"으로 끝나는 모든 사용자를 표시하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="9b353-247">명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="9b353-248">이 PowerShell 명령을 해석하면: 현재 Microsoft 365 구독의 모든 사용자를 되지만 성으로 끝나는 사용자만 나열하는 필터를 **사용하세요(-Filter '{LastName -like " \* son"}'**).</span><span class="sxs-lookup"><span data-stu-id="9b353-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="9b353-249">이 문자는 모든 문자 집합을 대칭합니다. 이 문자는 사용자의 \* 성에 있는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="9b353-250">Microsoft 365용 PowerShell을 사용하면 데이터를 쉽게 인쇄하거나 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="9b353-251">Microsoft 365 관리 센터에서는 데이터 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="9b353-252">비즈니스용 Skype Online에 대해 사용하도록 설정된 사용자 목록을 표시하는 비즈니스용 Skype Online 관리 센터의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![비즈니스용 Skype Online을 사용하도록 설정된 사용자 목록을 표시하는 비즈니스용 Skype Online 관리 센터 예제입니다.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="9b353-254">이 정보를 파일에 저장하려면 문서나 Microsoft Excel 워크시트에 붙여 넣아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="9b353-255">두 경우 모두 추가 서식이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-255">Either case might require additional formatting.</span></span> <span data-ttu-id="9b353-256">또한 Microsoft 365 관리 센터에서는 표시된 목록을 직접 인쇄할 수 있는 방법을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="9b353-257">다행히 PowerShell을 사용하여 목록을 표시할 뿐만 아니라 Excel로 쉽게 가져올 수 있는 파일에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="9b353-258">다음은 비즈니스용 Skype Online 사용자 데이터를 콤보로 구분된 값(CSV) 파일에 저장하는 예제 명령으로, Excel 워크시트의 표로 쉽게 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="9b353-259">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-259">Here's an example of the results:</span></span>
  
![콤보로 구분된 값 파일에 저장된 비즈니스용 Skype Online 사용자 데이터에 대한 Excel 워크시트로 가져온 테이블의 예입니다.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="9b353-261">이 PowerShell 명령을 해석하면 다음을 실행합니다. 현재 Microsoft 365 구독의 모든 비즈니스용 Skype Online 사용자 **다운로드(Get-CsOnlineUser**); 사용자 이름, UPN 및 **위치(Select DisplayName, UserPrincipalName, UsageLocation**); 그런 다음 C: \\ Logs \\ **SfBUsers.csv(Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation)라는** CSV 파일에 해당 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="9b353-262">옵션을 사용하여 이 목록을 XML 파일 또는 HTML 페이지로 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="9b353-263">실제로 추가 PowerShell 명령을 사용하면 원하는 사용자 지정 서식을 사용하여 Excel 파일로 직접 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="9b353-264">Windows의 기본 프린터에 직접 목록을 표시하는 PowerShell 명령의 출력을 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="9b353-265">명령의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="9b353-266">인쇄된 문서의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-266">Here's what your printed document will look like:</span></span>
  
![PowerShell 명령의 출력이 Windows의 기본 프린터로 직접 전송된 인쇄 문서의 예입니다.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="9b353-268">이 PowerShell 명령을 해석하면 다음을 실행합니다. 현재 Microsoft 365 구독의 모든 비즈니스용 Skype Online 사용자를 다운로드합니다. 사용자 이름, UPN 및 위치만 얻습니다. 그런 다음 기본 Windows 프린터(Out-Printer)로 해당 **정보를 전송합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="9b353-269">인쇄된 문서의 서식은 PowerShell 명령 창의 표시 서식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="9b353-270">하드 카피를 얻기 위해 해당 복사본을 **추가하기만 | 명령 끝에서** 프린터로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="9b353-271">Microsoft 365용 PowerShell을 사용하여 여러 서버 제품을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="9b353-272">Microsoft 365를 구성하는 구성 요소는 함께 작동하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="9b353-273">예를 들어 Microsoft 365에 새 사용자를 추가하고 사용자의 부서 및 전화 번호와 같은 정보를 지정하는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="9b353-274">이 정보는 비즈니스용 Skype Online, Exchange 또는 SharePoint와 같은 Microsoft 365 서비스에서 사용자 정보에 액세스하는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="9b353-275">그러나 이러한 방식은 제품군 전체에 적용되는 일반적인 정보에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="9b353-276">사용자의 Exchange 사서함에 대한 정보와 같은 제품별 정보는 일반적으로 제품군 전체에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="9b353-277">예를 들어 사용자의 사서함을 사용할 수 있는지 여부에 대한 정보는 Exchange 관리 센터에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="9b353-278">모든 사용자에 대해 다음 정보를 표시하는 보고서를 만들려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="9b353-279">사용자의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="9b353-279">The user's display name</span></span>
    
- <span data-ttu-id="9b353-280">사용자에게 Microsoft 365 라이선스가 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="9b353-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="9b353-281">사용자의 Exchange 사서함이 사용하도록 설정되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="9b353-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="9b353-282">사용자가 비즈니스용 Skype 온라인을 사용할 수 있도록 설정되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="9b353-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="9b353-283">Microsoft 365 관리 센터에서는 이러한 보고서를 쉽게 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9b353-284">대신 Excel 워크시트와 같은 정보를 저장할 별도의 문서를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="9b353-285">그런 다음 Microsoft 365 관리 센터에서 모든 사용자 이름 및 라이선스 정보를 다운로드하고, Exchange 관리 센터에서 사서함 정보를 다운로드하고, 비즈니스용 Skype Online 관리 센터에서 비즈니스용 Skype Online 정보를 확인한 다음 해당 정보를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="9b353-286">대신 PowerShell 스크립트를 사용하여 보고서를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="9b353-287">다음 예제 스크립트는 이 문서에서 지금까지 설명한 명령보다 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="9b353-288">그러나 PowerShell을 사용하여 다른 보기를 만들기 어려운 정보 보기를 만들 수 있는 가능성을 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="9b353-289">다음은 필요한 목록을 컴파일하고 표시하는 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="9b353-290">결과의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="9b353-291">이 PowerShell 스크립트를 해석하는 것은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="9b353-292">현재 Microsoft 365 구독의 모든 사용자를 다운로드하고 정보를 $x($x  **= Get-AzureADUser)라는 변수에 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="9b353-293">변수의 모든 사용자에 대해 실행되는 루프를 **$x(foreach($i)$x).**</span><span class="sxs-lookup"><span data-stu-id="9b353-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="9b353-294">이름이 $y  변수를 정의하고 사용자의 사서함 정보를 해당 변수에 저장합니다(**$y = Get-Mailbox -Identity $i.UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="9b353-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="9b353-295">*IsMailBoxEnabled라는* 사용자 정보에 새 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="9b353-296">사용자 사서함의 IsMailBoxEnabled 속성 **값($i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled)으로** 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b353-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="9b353-297">$y 변수를 정의하고 사용자의 비즈니스용 Skype Online 정보를 저장합니다($y **= Get-CsOnlineUser -Identity $i.UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="9b353-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="9b353-298">*EnabledForSfB라는* 사용자 정보에 새 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="9b353-299">사용자의 비즈니스용 Skype Online **정보($i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled)의** Enabled 속성 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b353-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="9b353-300">사용자 목록을 표시하지만 이름, 사용이 허가 여부, 사서함을 사용할 수 있는지 여부와 비즈니스용 Skype Online을 사용할 수 있는지 여부를 나타내는 두 가지 새 속성만 포함합니다($x |**DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b353-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b353-301">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b353-301">See also</span></span>

[<span data-ttu-id="9b353-302">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="9b353-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9b353-303">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="9b353-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9b353-304">Microsoft 365에서 Windows PowerShell을 사용하여 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="9b353-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

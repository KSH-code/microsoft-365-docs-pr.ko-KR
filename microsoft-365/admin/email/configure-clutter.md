---
title: 조직에 대한 클러터 구성
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'PowerShell을 사용하여 조직의 전체 또는 특정 사용자에 대해 클러터 기능을 사용하도록 설정하거나 사용하지 않도록 Exchange 방법을 학습합니다. '
ms.openlocfilehash: 91098047bdf2ab8190283990bdc6b0292e3e57ba
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393982"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="eabe5-103">조직에 대한 클러터 구성</span><span class="sxs-lookup"><span data-stu-id="eabe5-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="eabe5-104">[포커스가 있는 받은 편지함이](../setup/configure-focused-inbox.md) 클러터를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="eabe5-105">자세한 정보: 집중 받은 편지함 및 클러터에 대한 [계획에 대한 업데이트](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="eabe5-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="eabe5-106">관리자는 관리 팀에서 클러터 기능을 관리해야 할 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eabe5-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="eabe5-107">조직의 사용자에 대해 클러터 기능을 설정/해제하려면 PowerShell을 사용하여 Exchange 합니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="eabe5-108">(개인은 다음 지침에 따라 켜기/끄기: 에서 [클러터 끄기/켜기](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)Outlook.</span><span class="sxs-lookup"><span data-stu-id="eabe5-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="eabe5-109">PowerShell 사용에 대한 자세한 내용은 [PowerShell을](/powershell/exchange/exchange-online-powershell) Exchange Online 커넥트 [Exchange Online PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 사용하여 Exchange 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="eabe5-110">PowerShell을 사용하여 서비스 관리자 역할에 Exchange 계정이 Exchange Online 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="eabe5-111">PowerShell을 사용하여 Exchange 켜기</span><span class="sxs-lookup"><span data-stu-id="eabe5-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="eabe5-112">[Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet을 실행하여 사서함에 대해 클러터를 수동으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="eabe5-113">[Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="eabe5-114">Allie Bellew라는 단일 사용자에 대해 클러터 켜기</span><span class="sxs-lookup"><span data-stu-id="eabe5-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="eabe5-115">PowerShell을 사용하여 Exchange 끄기</span><span class="sxs-lookup"><span data-stu-id="eabe5-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="eabe5-116">[Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet을 실행하여 사서함에 대해 수동으로 클러터를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="eabe5-117">[Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="eabe5-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="eabe5-118">Allie Bellew라는 단일 사용자에 대해 클러터를 끄는 경우:</span><span class="sxs-lookup"><span data-stu-id="eabe5-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="eabe5-119">PowerShell을 사용하여 사용자를 대량으로 만드는 경우 각 사용자의 사서함에 [대해 Set-Clutter를](/powershell/module/exchange/set-clutter) 실행하여 클러터를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="eabe5-120">클러터 켜기/끄기 스위치는 웹용 Outlook?</span><span class="sxs-lookup"><span data-stu-id="eabe5-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="eabe5-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="eabe5-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="eabe5-122">관리자는 PowerShell을 사용하여 클러터를 다시 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="eabe5-123">이 완료되면 집중 받은 편지함이 꺼지며 클러터가 다시 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="eabe5-124">**구독과 함께 웹용 Outlook 사용하는 Microsoft 365 Business Premium:**</span><span class="sxs-lookup"><span data-stu-id="eabe5-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="eabe5-125">사용자가 현재 클러터를 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="eabe5-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="eabe5-126">클러터 설정 표시</span><span class="sxs-lookup"><span data-stu-id="eabe5-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="eabe5-127">사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="eabe5-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="eabe5-128">클러터 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="eabe5-129">클러터나 포커스가 있는 받은 편지함이 모두 사용하도록 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="eabe5-130">클러터와 포커스가 있는 받은 편지함은 모두 사용자의 메일 메시지에 옵션으로 설정</span><span class="sxs-lookup"><span data-stu-id="eabe5-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="eabe5-131">**Outlook.com을 사용하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="eabe5-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="eabe5-132">사용자가 현재 클러터를 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="eabe5-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="eabe5-133">클러터 설정 표시</span><span class="sxs-lookup"><span data-stu-id="eabe5-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="eabe5-134">사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="eabe5-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="eabe5-135">클러터 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="eabe5-136">클러터나 포커스가 있는 받은 편지함이 모두 사용하도록 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="eabe5-137">클러터와 포커스가 있는 받은 편지함은 모두 사용자의 메일 메시지에 옵션으로 설정</span><span class="sxs-lookup"><span data-stu-id="eabe5-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="eabe5-138">사용자가 과거의 특정 시점에서 중점 받은 편지함을 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="eabe5-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="eabe5-139">클러터 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="eabe5-140">그렇지 않으면</span><span class="sxs-lookup"><span data-stu-id="eabe5-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="eabe5-141">클러터 설정이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eabe5-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="eabe5-142">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="eabe5-142">Related content</span></span>

<span data-ttu-id="eabe5-143">[낮은 우선 순위의](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) 메시지를 낮은 우선 순위로 정렬하는 데 낮은 우선 순위 Outlook(문서)</span><span class="sxs-lookup"><span data-stu-id="eabe5-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="eabe5-144">[낮은 우선 순위의 메시지를 OWA에서](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) 정렬하는 낮은 우선 순위 메일(문서)</span><span class="sxs-lookup"><span data-stu-id="eabe5-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)</span></span>\
<span data-ttu-id="eabe5-145">[클러터를 끄는](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) Outlook(문서)</span><span class="sxs-lookup"><span data-stu-id="eabe5-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>

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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Exchange PowerShell을 사용하여 조직의 모든 또는 특정 사용자에 대해 클러터 기능을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 학습합니다. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780280"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="77abe-103">조직에 대한 클러터 구성</span><span class="sxs-lookup"><span data-stu-id="77abe-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="77abe-104">[포커스가 있는 받은 편지함은](../setup/configure-focused-inbox.md) 클러터를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="77abe-105">자세한 정보: 집중 받은 편지함 및 클러터에 대한 [계획에 대한 업데이트](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="77abe-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="77abe-106">관리자는 Microsoft 365의 클러터 기능을 관리해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="77abe-107">조직의 사용자에 대해 클러터 기능을 설정/해제하려면 Exchange PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="77abe-108">(개인은 다음 지침에 따라 이를 켜고 끄기: [Outlook에서 클러터를 끄고 켜기.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="77abe-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="77abe-109">Exchange [Online에서 PowerShell을](https://go.microsoft.com/fwlink/?LinkID=402831) 사용하고 [Exchange Online PowerShell에](https://go.microsoft.com/fwlink/?LinkID=722415) 연결하여 Exchange PowerShell 사용에 대한 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77abe-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="77abe-110">적어도 Exchange 서비스 관리자 역할과 PowerShell을 사용하여 Exchange Online에 연결하는 기능을 제공하는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="77abe-111">Exchange PowerShell을 사용하여 클러터 켜기</span><span class="sxs-lookup"><span data-stu-id="77abe-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="77abe-112">[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet을 실행하여 사서함에 대해 클러터를 수동으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="77abe-113">[Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="77abe-114">Allie Bellew라는 단일 사용자에 대해 클러터 켜기</span><span class="sxs-lookup"><span data-stu-id="77abe-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="77abe-115">Exchange PowerShell을 사용하여 클러터 끄기</span><span class="sxs-lookup"><span data-stu-id="77abe-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="77abe-116">[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet을 실행하여 사서함에 대해 수동으로 클러터를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="77abe-117">[Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행하여 조직의 사서함에 대한 클러터 설정을 볼 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="77abe-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="77abe-118">Allie Bellew라는 단일 사용자에 대한 클러터를 끄는 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="77abe-119">PowerShell을 사용하여 사용자를 대량으로 만드는 경우 각 사용자의 사서함에 [대해 Set-Clutter를](https://go.microsoft.com/fwlink/?LinkID=834446) 실행하여 클러터를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="77abe-120">클러터 켜기/끄기 스위치는 웹용 Outlook의 사용자에게 언제 표시하나요?</span><span class="sxs-lookup"><span data-stu-id="77abe-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="77abe-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="77abe-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="77abe-122">관리자는 Exchange PowerShell을 사용하여 클러터를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="77abe-123">이 완료되면 포커스가 있는 받은 편지함이 꺼지며 클러터가 다시 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="77abe-124">**웹용 Outlook을 Microsoft 365 Business Premium 구독과 함께 사용하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="77abe-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="77abe-125">사용자가 현재 클러터를 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="77abe-126">클러터 설정 표시</span><span class="sxs-lookup"><span data-stu-id="77abe-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="77abe-127">사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="77abe-128">클러터 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="77abe-129">클러터나 포커스가 있는 받은 편지함을 모두 사용할 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="77abe-130">클러터와 포커스가 있는 받은 편지함이 사용자의 메일 설정에 옵션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="77abe-131">**다음을 사용하는 Outlook.com.**</span><span class="sxs-lookup"><span data-stu-id="77abe-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="77abe-132">사용자가 현재 클러터를 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="77abe-133">클러터 설정 표시</span><span class="sxs-lookup"><span data-stu-id="77abe-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="77abe-134">사용자가 현재 중점 받은 편지함을 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="77abe-135">클러터 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="77abe-136">클러터나 포커스가 있는 받은 편지함을 모두 사용할 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="77abe-137">클러터와 포커스가 있는 받은 편지함이 사용자의 메일 설정에 옵션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="77abe-138">사용자가 과거에 특정 시점에 중점 받은 편지함을 사용하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="77abe-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="77abe-139">클러터 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="77abe-140">그렇지 않으면</span><span class="sxs-lookup"><span data-stu-id="77abe-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="77abe-141">클러터 설정이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="77abe-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="77abe-142">관련 문서</span><span class="sxs-lookup"><span data-stu-id="77abe-142">Related articles</span></span>
<span data-ttu-id="77abe-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="77abe-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="77abe-144">낮은 우선 순위의 메시지를 Outlook에서 정렬하는 낮은 우선 순위 메일 사용</span><span class="sxs-lookup"><span data-stu-id="77abe-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="77abe-145">낮은 우선 순위 메시지를 OWA에서 정렬하는 낮은 우선 순위 메일 사용</span><span class="sxs-lookup"><span data-stu-id="77abe-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="77abe-146">Outlook에서 클러터 끄기</span><span class="sxs-lookup"><span data-stu-id="77abe-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    


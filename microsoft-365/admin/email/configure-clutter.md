---
title: 조직에 대 한 복잡 한 구성
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
description: 'Exchange PowerShell을 사용 하 여 조직의 모든 또는 특정 사용자에 대해 낮은 우선 순위 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 069cf7569ebb3654e979100291f6754693b24def
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400139"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="14d95-103">조직에 대 한 복잡 한 구성</span><span class="sxs-lookup"><span data-stu-id="14d95-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="14d95-104">[중요 받은 편지함](../setup/configure-focused-inbox.md) 에서 낮은 우선 순위를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="14d95-105">자세한 내용은 [중요 받은 편지함에 대 한 업데이트 및 낮은 계획에 대 한 요금제](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448) 를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="14d95-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="14d95-106">관리자는 Microsoft 365에서 낮은 우선 순위 기능을 관리 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="14d95-107">조직의 사용자에 대해 낮은 우선 순위 기능을 설정/해제 하려면 Exchange PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="14d95-108">사용자는 다음 [지침을 사용](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)하 여이 기능을 설정/해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="14d95-109">Exchange PowerShell 사용에 대 한 자세한 내용은 [Exchange online에서 PowerShell을 사용](https://go.microsoft.com/fwlink/?LinkID=402831) 하 고 Exchange [Online PowerShell에 연결](https://go.microsoft.com/fwlink/?LinkID=722415) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14d95-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="14d95-110">적어도 Exchange 서비스 관리자 역할을 가진 계정 및 PowerShell을 사용 하 여 Exchange Online에 연결 하는 기능이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="14d95-111">Exchange PowerShell을 사용 하 여 정리 기능 설정</span><span class="sxs-lookup"><span data-stu-id="14d95-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="14d95-112">[낮은 우선 순위](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet을 실행 하 여 사서함에 대해 복잡 한 방법을 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="14d95-113">[낮은 우선 순위](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행 하 여 조직의 사서함에 대 한 낮은 수준의 설정을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="14d95-114">Allie 라는 단일 사용자에 대해 정리 기능을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="14d95-115">Exchange PowerShell을 사용 하 여 정리 기능 해제</span><span class="sxs-lookup"><span data-stu-id="14d95-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="14d95-116">[낮은](https://go.microsoft.com/fwlink/?LinkID=834446) 우선 순위 cmdlet을 실행 하 여 사서함에 대해 복잡 한 방법을 수동으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="14d95-117">[낮은 우선 순위](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet을 실행 하 여 조직의 사서함에 대 한 **낮은** 수준의 설정을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="14d95-118">Allie 라는 단일 사용자에 대해 혼란을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="14d95-119">PowerShell을 사용 하 여 사용자를 대량으로 만드는 경우에는 각 사용자의 사서함에 대해 [설정 된 복잡 한 설정을](https://go.microsoft.com/fwlink/?LinkID=834446) 실행 하 여 혼란을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="14d95-120">웹에서 Outlook의 사용자에 게 간편 하 게 설정/해제 스위치가 표시 되는 경우</span><span class="sxs-lookup"><span data-stu-id="14d95-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="14d95-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="14d95-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="14d95-122">관리자는 Exchange PowerShell을 사용 하 여 혼란을 다시 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="14d95-123">이 작업이 완료 되 면 중요 받은 편지함이 꺼지고 깔끔하게 다시 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="14d95-124">**Microsoft 365 Business Premium 구독을 사용 하 여 웹에서 Outlook을 사용 하는 경우 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="14d95-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="14d95-125">현재 사용자가 낮은 사용을 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="14d95-126">낮은 우선 순위 설정 표시</span><span class="sxs-lookup"><span data-stu-id="14d95-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="14d95-127">사용자에 게 현재 중요 받은 편지함을 사용 하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="14d95-128">낮은 우선 순위 설정이 나타나지 않음</span><span class="sxs-lookup"><span data-stu-id="14d95-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="14d95-129">불필요 한 받은 편지함이 사용 하도록 설정 되어 있지 않은 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="14d95-130">사용자의 메일 설정에서 낮은 우선 순위 및 중요 받은 편지함 모두 옵션으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="14d95-131">**Outlook.com을 사용 하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="14d95-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="14d95-132">현재 사용자가 낮은 사용을 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="14d95-133">낮은 우선 순위 설정 표시</span><span class="sxs-lookup"><span data-stu-id="14d95-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="14d95-134">사용자에 게 현재 중요 받은 편지함을 사용 하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="14d95-135">낮은 우선 순위 설정이 나타나지 않음</span><span class="sxs-lookup"><span data-stu-id="14d95-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="14d95-136">불필요 한 받은 편지함이 사용 하도록 설정 되어 있지 않은 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="14d95-137">사용자의 메일 설정에서 낮은 우선 순위 및 중요 받은 편지함 모두 옵션으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="14d95-138">사용자가 이전의 특정 시점에 중요 받은 편지함을 사용 하도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="14d95-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="14d95-139">낮은 우선 순위 설정이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="14d95-140">방법</span><span class="sxs-lookup"><span data-stu-id="14d95-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="14d95-141">낮은 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="14d95-142">관련 문서</span><span class="sxs-lookup"><span data-stu-id="14d95-142">Related articles</span></span>
<span data-ttu-id="14d95-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="14d95-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="14d95-144">간단 하 게 Outlook에서 낮은 우선 순위 메시지 정렬</span><span class="sxs-lookup"><span data-stu-id="14d95-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="14d95-145">간단 하 게 OWA에서 낮은 우선 순위의 메시지 정렬</span><span class="sxs-lookup"><span data-stu-id="14d95-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="14d95-146">Outlook에서 혼란을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="14d95-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    


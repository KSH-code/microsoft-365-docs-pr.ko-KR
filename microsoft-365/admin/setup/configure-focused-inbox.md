---
title: 조직의 모든 사용자에 대해 중요 받은 편지함 구성
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: '조직의 모든 사용자나 특정 사용자에 대해 중요 받은 편지함을 구성하는 방법을 알아봅니다. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779932"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="57328-103">조직의 모든 사용자에 대해 중요 받은 편지함 구성</span><span class="sxs-lookup"><span data-stu-id="57328-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="57328-104">회사의 모든 사용자에 대해 전자 메일 작동 방법을 구성해야 하는 경우 이 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57328-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="57328-105">이 문서에서는 해당 비즈니스에 맞게 이러한 구성을 사용자 지정하거나 끄는 방법을 설명하고 [자주하는 질문](#faq-for-focused-inbox)에 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="57328-106">자신의 중요 받은 편지함을 끄려면 [중요 받은 편지함 끄기](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57328-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  
   
<span data-ttu-id="57328-107">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view.</span><span class="sxs-lookup"><span data-stu-id="57328-107">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view.</span></span> <span data-ttu-id="57328-108">You can also control whether users in your organization see the Focused Inbox in their mailbox.</span><span class="sxs-lookup"><span data-stu-id="57328-108">You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="57328-109">조직의 중요 받은 편지함 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="57328-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="57328-110">PowerShell을 사용하여 조직의 모든 사용자에 대해 중요 받은 편지함을 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="57328-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="57328-111">이 작업을 Microsoft 365 관리 센터에서 수행하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="57328-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="57328-112">저희 엔지니어링 팀에 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="57328-112">Let our Engineering team know.</span></span> <span data-ttu-id="57328-113">**[여기에서 투표하세요!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="57328-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="57328-114">**중요 받은 편지함을 끄는 방법**</span><span class="sxs-lookup"><span data-stu-id="57328-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="57328-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span><span class="sxs-lookup"><span data-stu-id="57328-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span></span> <span data-ttu-id="57328-116">However, it doesn't block the availability of the feature for your users.</span><span class="sxs-lookup"><span data-stu-id="57328-116">However, it doesn't block the availability of the feature for your users.</span></span> <span data-ttu-id="57328-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span><span class="sxs-lookup"><span data-stu-id="57328-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="57328-118">[원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="57328-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="57328-119">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="57328-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="57328-120">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="57328-120">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="57328-121">
            \*\*Get-OrganizationConfig\*\* cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="57328-122">**FocusedInboxOn** 을 찾아 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![중요 받은 편지함 상태에서의 PowerShell 응답.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="57328-124">다음 cmdlet을 실행하여 중요 받은 편지함을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="57328-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="57328-125">**Get-OrganizationConfig** cmdlet을 다시 실행하면 FocusedInboxOn이 $false로 설정되며, 이는 중요 받은 편지함이 꺼졌음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="57328-126">**중요 받은 편지함을 켜는 방법:**</span><span class="sxs-lookup"><span data-stu-id="57328-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="57328-127">위의 5단계에서 다음 cmdlet을 실행하여 중요 받은 편지함을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="57328-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="57328-128">중요 받은 편지함을 켜면 사용자에게 어떻게 표시되나요? </span><span class="sxs-lookup"><span data-stu-id="57328-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="57328-129">Your users will see the Focused view only after they close and restart Outlook.</span><span class="sxs-lookup"><span data-stu-id="57328-129">Your users will see the Focused view only after they close and restart Outlook.</span></span> <span data-ttu-id="57328-130">When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="57328-130">When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![사용자가 처음으로 웹용 Outlook을 열 때 중요 받은 편지함의 이미지입니다.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="57328-132">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature.</span><span class="sxs-lookup"><span data-stu-id="57328-132">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature.</span></span> <span data-ttu-id="57328-133">If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one.</span><span class="sxs-lookup"><span data-stu-id="57328-133">If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one.</span></span> <span data-ttu-id="57328-134">The tip looks like this:</span><span class="sxs-lookup"><span data-stu-id="57328-134">The tip looks like this:</span></span>
  
![중요 받은 편지함이 사용자에게 배포되고 Outlook을 다시 열었을 때 중요 받은 편지함이 어떻게 표시되는지를 보여 주는 이미지](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="57328-136">When a user decides to start using Focused Inbox, Clutter gets disabled automatically.</span><span class="sxs-lookup"><span data-stu-id="57328-136">When a user decides to start using Focused Inbox, Clutter gets disabled automatically.</span></span> <span data-ttu-id="57328-137">The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span><span class="sxs-lookup"><span data-stu-id="57328-137">The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="57328-138">특정 사용자에 대해 중요 받은 편지함 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="57328-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="57328-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span><span class="sxs-lookup"><span data-stu-id="57328-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="57328-140">However, it doesn't block the availability of the feature to him.</span><span class="sxs-lookup"><span data-stu-id="57328-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="57328-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span><span class="sxs-lookup"><span data-stu-id="57328-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="57328-142">[원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="57328-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="57328-143">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="57328-143">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="57328-144">To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span><span class="sxs-lookup"><span data-stu-id="57328-144">To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="57328-145">**Get-FocusedInbox** cmdlet을 실행합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57328-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="57328-146">FocusedInboxOn을 찾아 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![중요 받은 편지함 상태에서의 PowerShell 응답.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="57328-148">다음 cmdlet을 실행하여 중요 받은 편지함을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="57328-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="57328-149">또는 다음 cmdlet을 실행하여 중요 받은 편지함을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="57328-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="57328-150">UI를 사용하여 전자 메일 메시지를 모든 사용자의 중요 보기로 보내도록 전송 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57328-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="57328-151"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="57328-152">**메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="57328-153">![EAC 아이콘 추가](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)를 선택한 다음 **새 규칙 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="57328-154">새 규칙 만들기가 완료되면 **저장** 을 선택하여 해당 규칙을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="57328-155">다음 이미지는 "급여 부서"의 모든 메시지가 중요 받은 편지함으로 배달되는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57328-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![focusedinbox 급여](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="57328-157">PowerShell을 사용하여 전자 메일 메시지를 모든 사용자의 중요 보기로 보내도록 전송 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57328-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="57328-158">[원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="57328-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="57328-159">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="57328-159">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="57328-160">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="57328-160">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="57328-161">예를 들어 다음 명령을 실행하여 "급여 부서"의 모든 메시지가 중요 받은 편지함으로 배달되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57328-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="57328-162">이 예제에서 "X-MS-Exchange-Organization-BypassFocusedInbox" 및 "true" 모두 대소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="57328-163">또한 중요 받은 편지함은 낮은 우선 순위 메일을 바이패스하는 X-헤더를 준수하므로 낮은 우선 순위 메일에서 이 설정을 사용하는 경우 중요 받은 편지함에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57328-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="57328-164">자세한 구문 및 매개변수 정보 [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57328-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="57328-165">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="57328-165">How do you know this worked?</span></span>

<span data-ttu-id="57328-166">전자 메일 메시지 헤더를 확인하여 중요 받은 편지함 전송 규칙 바이패스로 인해 받은 편지함으로 전자 메일 메시지가 도착하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57328-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="57328-167">중요 받은 편지함 전송 규칙이 적용된 조직의 사서함에서 전자 메일 메시지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="57328-168">메시지에 스탬프 처리된 헤더를 확인하고 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 헤더를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="57328-169">이는 바이패스가 작동 중임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="57328-169">This means the bypass is working.</span></span> <span data-ttu-id="57328-170">헤더 정보를 찾는 방법에 대한 정보는 [전자 메일 메시지에 대한 인터넷 헤더 정보 확인](https://go.microsoft.com/fwlink/p/?LinkId=822530) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57328-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="57328-171">낮은 우선 순위 메일 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="57328-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="57328-172">We've received reports that Clutter suddenly stopped working for some users.</span><span class="sxs-lookup"><span data-stu-id="57328-172">We've received reports that Clutter suddenly stopped working for some users.</span></span> <span data-ttu-id="57328-173">If this happens, you can enable it again for specific users.</span><span class="sxs-lookup"><span data-stu-id="57328-173">If this happens, you can enable it again for specific users.</span></span> <span data-ttu-id="57328-174">See [Configure Clutter for your organization](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="57328-174">See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="57328-175">중요 받은 편지함에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="57328-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="57328-176">다음은 중요 받은 편지함에 대한 질문과 대답입니다.</span><span class="sxs-lookup"><span data-stu-id="57328-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="57328-177">조직에서 중요 받은 편지함 배포 방법을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="57328-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="57328-178">Yes.</span><span class="sxs-lookup"><span data-stu-id="57328-178">Yes.</span></span> <span data-ttu-id="57328-179">You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users.</span><span class="sxs-lookup"><span data-stu-id="57328-179">You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users.</span></span> <span data-ttu-id="57328-180">See above.</span><span class="sxs-lookup"><span data-stu-id="57328-180">See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="57328-181">중요 받은 편지함은 Office 2016 클라이언트에서만 사용할 수 있는 기능인가요?</span><span class="sxs-lookup"><span data-stu-id="57328-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="57328-182">예, Office 2016을 이용하는 사용자만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="57328-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="57328-183">이 기능은 Outlook 2013 또는 이전 버전에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57328-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="57328-184">Outlook에서 중요 받은 편지함 변경 사항을 적용하려면 시간이 얼마나 걸리나요?</span><span class="sxs-lookup"><span data-stu-id="57328-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="57328-185">중요 받은 편지함을 켜거나 끄고 난 후 사용자가 Outlook을 닫았다가 다시 시작하면 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57328-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="57328-186">중요 받은 편지함을 켜면 낮은 우선 순위 메일은 어떻게 나요?</span><span class="sxs-lookup"><span data-stu-id="57328-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="57328-187">After switching, you'll no longer receive less actionable email in the Clutter folder.</span><span class="sxs-lookup"><span data-stu-id="57328-187">After switching, you'll no longer receive less actionable email in the Clutter folder.</span></span> <span data-ttu-id="57328-188">Instead, email will be split between the Focused and Other tabs in your inbox.</span><span class="sxs-lookup"><span data-stu-id="57328-188">Instead, email will be split between the Focused and Other tabs in your inbox.</span></span> <span data-ttu-id="57328-189">The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other.</span><span class="sxs-lookup"><span data-stu-id="57328-189">The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other.</span></span> <span data-ttu-id="57328-190">Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span><span class="sxs-lookup"><span data-stu-id="57328-190">Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="57328-191">Microsoft MVP인 [Tony Redmond](https://www.petri.com/author/tony-redmond)의 다음 게시물을 확인해 보세요. [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365)(Office 365 내에서 중요 받은 편지함이 낮은 우선 순위 메일을 대체하는 방법)</span><span class="sxs-lookup"><span data-stu-id="57328-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="57328-192">낮은 우선 순위 메일의 사용자를 유지할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="57328-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="57328-193">낮은 우선 순위 메일 및 중요 받은 편지함 사용에 대한 Microsoft의 권장 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="57328-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="57328-194">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now.</span><span class="sxs-lookup"><span data-stu-id="57328-194">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now.</span></span> <span data-ttu-id="57328-195">To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span><span class="sxs-lookup"><span data-stu-id="57328-195">To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="57328-196">모든 사용자가 중요 받은 편지함으로 이동하려는 경우 일반 사용자에 대해 낮은 우선 순위 메일을 사용하지 않도록 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="57328-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="57328-197">No.</span><span class="sxs-lookup"><span data-stu-id="57328-197">No.</span></span> <span data-ttu-id="57328-198">It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet.</span><span class="sxs-lookup"><span data-stu-id="57328-198">It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet.</span></span> <span data-ttu-id="57328-199">However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="57328-199">However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox.</span></span> <span data-ttu-id="57328-200">It's therefore best not to disable Clutter until the upgraded clients are available.</span><span class="sxs-lookup"><span data-stu-id="57328-200">It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="57328-201">중요 받은 편지함 관리를 위해 두 가지 cmdlet이 있는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="57328-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="57328-202">중요 받은 편지함과 연관된 상태는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57328-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="57328-203">**조직 수준**: 중요 받은 편지함 상태 및 연관된 마지막 업데이트 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="57328-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="57328-204">**사서함 수준​​**: 중요 받은 편지함 상태 및 연관된 마지막 업데이트 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="57328-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="57328-205">Outlook에서 이러한 두 가지 상태로 중요 받은 편지함 환경 표시를 결정하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="57328-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="57328-206">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp.</span><span class="sxs-lookup"><span data-stu-id="57328-206">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp.</span></span> <span data-ttu-id="57328-207">By default, both time stamps are "null" and in this case, the feature is enabled.</span><span class="sxs-lookup"><span data-stu-id="57328-207">By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="57328-208">조직에서 중요 받은 편지함을 껐는데 Get-FocusedInbox cmdlet에서 “true”를 반환하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="57328-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="57328-209">There are two cmdlets for controlling Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="57328-209">There are two cmdlets for controlling Focused Inbox.</span></span> <span data-ttu-id="57328-210">When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature.</span><span class="sxs-lookup"><span data-stu-id="57328-210">When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature.</span></span> <span data-ttu-id="57328-211">The experience in Outlook is chosen based on which cmdlet state was last modified.</span><span class="sxs-lookup"><span data-stu-id="57328-211">The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="57328-212">스크립트를 실행하여 중요 받은 편지함을 설정한 사용자를 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="57328-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="57328-213">No, and this is by design.</span><span class="sxs-lookup"><span data-stu-id="57328-213">No, and this is by design.</span></span> <span data-ttu-id="57328-214">Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience.</span><span class="sxs-lookup"><span data-stu-id="57328-214">Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience.</span></span> <span data-ttu-id="57328-215">It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span><span class="sxs-lookup"><span data-stu-id="57328-215">It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>

---
title: 조직의 모든 사용자에 대해 중요 받은 편지함 구성
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: 비즈니스 내 모든 사용자의 전자 메일 설정 구성 책임을 맡고 있다면 이 문서에서 사용자의 중요 받은 편지함 구성 방법에 대해 알아보세요.
ms.openlocfilehash: ddd0886988072139a199bfc3f6e8adbbf25ad58b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623704"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="561bb-103">조직의 모든 사용자에 대해 중요 받은 편지함 구성</span><span class="sxs-lookup"><span data-stu-id="561bb-103">Configure Focused Inbox for everyone in your organization</span></span>

<span data-ttu-id="561bb-104">회사의 모든 사용자에 대해 전자 메일 작동 방법을 구성해야 하는 경우 이 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="561bb-105">이 문서에서는 해당 비즈니스에 맞게 이러한 구성을 사용자 지정하거나 끄는 방법을 설명하고 [자주하는 질문](#faq-for-focused-inbox)에 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>

<span data-ttu-id="561bb-106">자신의 중요 받은 편지함을 끄려면 [중요 받은 편지함 끄기](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  

<span data-ttu-id="561bb-p102">사용자가 예를 들어 HR 또는 급여로부터 비즈니스 관련 전자 메일 메시지를 받을 수 있도록 하려면 이러한 메시지가 중요 보기로 오도록 중요 받은 편지함을 구성할 수 있습니다. 사서함에서 중요 받은 편지함이 조직의 사용자에게 표시되도록 할 것인지를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="561bb-109">조직의 중요 받은 편지함 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="561bb-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="561bb-110">PowerShell을 사용하여 조직의 모든 사용자에 대해 중요 받은 편지함을 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="561bb-111">이 작업을 Microsoft 365 관리 센터에서 수행하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="561bb-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="561bb-112">저희 엔지니어링 팀에 알려 주세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-112">Let our Engineering team know.</span></span> <span data-ttu-id="561bb-113">**[여기에서 투표하세요!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="561bb-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
<span data-ttu-id="561bb-114">**중요 받은 편지함을 끄는 방법**</span><span class="sxs-lookup"><span data-stu-id="561bb-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="561bb-p104">다음 PowerShell 예제는 조직의 중요 받은 편지함을 **끕니다**. 하지만 이렇게 해도 사용자의 기능 사용 가능성은 차단되지 않습니다. 사용자가 원하는 경우 각 클라이언트에서 중요 받은 편지함을 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="561bb-118">[원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="561bb-118">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="561bb-p105">이 절차를 수행하려면 사용 권한이 할당된 상태여야 합니다. 필요한 사용 권한을 확인하려면 [메시징 정책 및 규정 준수 권한](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help)의 "전송 규칙" 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span></span>

3. <span data-ttu-id="561bb-121">
            \*\*Get-OrganizationConfig\*\* cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 

    ```powershell
    Get-OrganizationConfig
    ```

4. <span data-ttu-id="561bb-122">**FocusedInboxOn** 을 찾아 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 

    ![중요 받은 편지함 상태에서의 PowerShell 응답.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="561bb-124">다음 cmdlet을 실행하여 중요 받은 편지함을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-124">Run the following cmdlet to turn Focused Inbox off.</span></span>

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. <span data-ttu-id="561bb-125">**Get-OrganizationConfig** cmdlet을 다시 실행하면 FocusedInboxOn이 $false로 설정되며, 이는 중요 받은 편지함이 꺼졌음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 

<span data-ttu-id="561bb-126">**중요 받은 편지함을 켜는 방법:**</span><span class="sxs-lookup"><span data-stu-id="561bb-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="561bb-127">위의 5단계에서 다음 cmdlet을 실행하여 중요 받은 편지함을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="561bb-128">중요 받은 편지함을 켜면 사용자에게 어떻게 표시되나요? </span><span class="sxs-lookup"><span data-stu-id="561bb-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="561bb-p106">Outlook을 닫았다가 다시 시작해야 중요 보기가 사용자에게 표시됩니다. Outlook을 다시 시작하면 Outlook 사용자 인터페이스에 새 중요 받은 편지함을 사용하기 위한 옵션을 제공하는 팁이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![사용자가 처음으로 웹용 Outlook을 열 때 중요 받은 편지함의 이미지입니다.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="561bb-p107&quot;>낮은 우선 순위 메일에서 중요 받은 편지함으로 전환하는 경우 사용자가 이를 사용하도록 설정할지(&quot;사용해 보기") 또는 이 기능을 해제할지를 결정할 수 있습니다. 여러(지원되는) 클라이언트가 있는 경우 사용자는 각각에서 개별적으로 중요 받은 편지함을 사용하거나 사용하지 않도록 설정할 수 있습니다. 팁은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![중요 받은 편지함이 사용자에게 배포되고 Outlook을 다시 열었을 때 중요 받은 편지함이 어떻게 표시되는지를 보여 주는 이미지](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="561bb-p108">사용자가 중요 받은 편지함을 사용하기로 결정하면 낮은 우선 순위 메일이 자동으로 사용하지 않도록 설정됩니다. 낮은 우선 순위 메일 폴더는 사용자가 이름을 바꾸거나 삭제할 수 있는 표준 폴더로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="561bb-138">특정 사용자에 대해 중요 받은 편지함 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="561bb-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="561bb-139">이 예제에서는 Contoso 조직의 Tim Matthews에 대해 중요 받은 편지함을 **끕니다**.</span><span class="sxs-lookup"><span data-stu-id="561bb-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="561bb-140">하지만 이렇게 해도 Tim Matthews의 기능 사용 가능성은 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="561bb-141">원한다면 각 클라이언트에 대한 중요 받은 편지함을 다시 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-141">If he wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="561bb-142">[원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="561bb-142">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="561bb-p110">이 절차를 수행하려면 사용 권한이 할당된 상태여야 합니다. 필요한 사용 권한을 확인하려면 Messaging policy and compliance permissions(메시징 정책 및 규정 준수 권한) 항목에서 “Transport rules”(전송 규칙) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>

3. <span data-ttu-id="561bb-145">**Get-FocusedInbox** cmdlet을 실행합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. <span data-ttu-id="561bb-146">FocusedInboxOn을 찾아 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-146">Look for FocusedInboxOn to view its current setting:</span></span>

    ![중요 받은 편지함 상태에서의 PowerShell 응답.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="561bb-148">다음 cmdlet를 실행하여 중요 받은 편지함을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-148">Run the following cmdlet to turn off Focused Inbox:</span></span>

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    <span data-ttu-id="561bb-149">또는 다음 cmdlet을 실행하여 중요 받은 편지함을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-149">OR, run the following cmdlet to turn it on:</span></span>

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="561bb-150">UI를 사용하여 전자 메일 메시지를 모든 사용자의 중요 보기로 보내도록 전송 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="561bb-151"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="561bb-152">**메일 흐름** \> **규칙** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="561bb-153">![EAC 아이콘 추가](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)를 선택한 다음 **새 규칙 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 

3. <span data-ttu-id="561bb-154">새 규칙 만들기가 완료되면 **저장** 을 선택하여 해당 규칙을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-154">After you're done creating the new rule, select **Save** to start the rule.</span></span>

    <span data-ttu-id="561bb-155">다음 이미지는 "급여 부서"의 모든 메시지가 중요 받은 편지함으로 배달되는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>

    ![focusedinbox 급여](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > <span data-ttu-id="561bb-157">이 예제에서 메시지 헤더 값 텍스트는 **X-MS-Exchange-Organization-BypassFocusedInbox** 입니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-157">The message header value text in this example is, **X-MS-Exchange-Organization-BypassFocusedInbox**.</span></span>
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="561bb-158">PowerShell을 사용하여 전자 메일 메시지를 모든 사용자의 중요 보기로 보내도록 전송 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-158">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="561bb-159">[원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="561bb-159">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="561bb-p112">이 절차를 수행하려면 사용 권한이 할당된 상태여야 합니다. 필요한 사용 권한을 확인하려면 [메시징 정책 및 규정 준수 권한](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help)의 "전송 규칙" 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span></span>

3. <span data-ttu-id="561bb-162">예를 들어 다음 명령을 실행하여 "급여 부서"의 모든 메시지가 중요 받은 편지함으로 배달되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-162">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> <span data-ttu-id="561bb-163">이 예제에서 "X-MS-Exchange-Organization-BypassFocusedInbox" 및 "true" 모두 대소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-163">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="561bb-164">또한 중요 받은 편지함은 낮은 우선 순위 메일을 바이패스하는 X-헤더를 준수하므로 낮은 우선 순위 메일에서 이 설정을 사용하는 경우 중요 받은 편지함에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-164">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="561bb-165">자세한 구문 및 매개변수 정보 [New-TransportRule](/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-165">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="561bb-166">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-166">How do you know this worked?</span></span>

<span data-ttu-id="561bb-167">전자 메일 메시지 헤더를 확인하여 중요 받은 편지함 전송 규칙 바이패스로 인해 받은 편지함으로 전자 메일 메시지가 도착하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-167">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="561bb-168">중요 받은 편지함 전송 규칙이 적용된 조직의 사서함에서 전자 메일 메시지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-168">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="561bb-169">메시지에 스탬프 처리된 헤더를 확인하고 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 헤더를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-169">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="561bb-170">이는 바이패스가 작동 중임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-170">This means the bypass is working.</span></span> <span data-ttu-id="561bb-171">헤더 정보를 찾는 방법에 대한 정보는 [전자 메일 메시지에 대한 인터넷 헤더 정보 확인](https://go.microsoft.com/fwlink/p/?LinkId=822530) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-171">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span>

### <a name="what-will-the-user-see"></a><span data-ttu-id="561bb-172">사용자에게는 어떻게 표시되나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-172">What will the user see?</span></span>

<span data-ttu-id="561bb-173">메일 흐름 규칙이 제대로 설정됐다면 재정의 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-173">If a transport rule is in place, a notification will be shown for the override.</span></span> <span data-ttu-id="561bb-174">웹용 Outlook의 경우 “항상 기타 받은 편지함으로 이동”이 사용하지 않게 설정되고 도구 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-174">Outlook on the web will disable the "Always move to Other" and show a tooltip.</span></span> <span data-ttu-id="561bb-175">데스크톱 Outlook 클라이언트의 경우 “항상 기타 받은 편지함으로 이동” 선택이 허용되며 대화 팝업 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-175">Outlook clients on desktop will allow selection for "Always move to Other" and will pop up a dialog.</span></span>

## <a name="turn-onoff-clutter"></a><span data-ttu-id="561bb-176">낮은 우선 순위 메일 켜기/끄기</span><span class="sxs-lookup"><span data-stu-id="561bb-176">Turn on/off Clutter</span></span>

<span data-ttu-id="561bb-p116">일부 사용자에서 낮은 우선 순위 메일이 갑자기 작동 중지되었다는 보고를 받았습니다. 이 경우 특정 사용자에 대해 낮은 우선 순위 메일을 다시 사용하도록 설정할 수 있습니다. [조직에 대한 낮은 우선 순위 메일 구성](../email/configure-clutter.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-p116">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>

## <a name="faq-for-focused-inbox"></a><span data-ttu-id="561bb-180">중요 받은 편지함에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="561bb-180">FAQ for Focused Inbox</span></span>

<span data-ttu-id="561bb-181">다음은 중요 받은 편지함에 대한 질문과 대답입니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-181">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span>

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="561bb-182">조직에서 중요 받은 편지함 배포 방법을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-182">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="561bb-p117">예. 전체 조직에 대해 중요 받은 편지함을 켜거나 끌 수도 있고 지정된 사용자에 대해 켜거나 끌 수도 있습니다. 위 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="561bb-p117">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="561bb-186">중요 받은 편지함은 Office 2016 클라이언트에서만 사용할 수 있는 기능인가요?</span><span class="sxs-lookup"><span data-stu-id="561bb-186">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="561bb-p118">예, Office 2016을 사용하는 사용자만 영향을 받습니다. 이 기능은 Outlook 2013 또는 이전 버전에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p118">Yes, only users with Office 2016 are affected. The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="561bb-189">Outlook에서 중요 받은 편지함 변경 사항을 적용하려면 시간이 얼마나 걸리나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-189">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="561bb-190">중요 받은 편지함을 켜거나 끄고 난 후 사용자가 Outlook을 닫았다가 다시 시작하면 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-190">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="561bb-191">중요 받은 편지함을 켜면 낮은 우선 순위 메일은 어떻게 나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-191">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="561bb-p119">전환한 다음 낮은 우선 순위 메일 폴더로 더 이상 덜 실행 가능한 전자 메일이 수신되지 않습니다. 그 대신 전자 메일이 받은 편지함의 중요 및 기타 탭으로 수신됩니다. 중요 받은 편지함에는 낮은 우선 순위 메일 폴더로 항목을 이동하던 동일한 알고리즘이 적용됩니다. 즉, 낮은 우선 순위 메일로 이동되도록 설정된 모든 전자 메일이 이제는 기타로 이동됩니다. 이미 낮은 우선 순위 메일 폴더에 포함된 메시지는 사용자가 삭제하거나 이동할 때까지 해당 폴더에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p119">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="561bb-196">Microsoft MVP인 [Tony Redmond](https://www.petri.com/author/tony-redmond)의 다음 게시물을 확인해 보세요. [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365)(Office 365 내에서 중요 받은 편지함이 낮은 우선 순위 메일을 대체하는 방법)</span><span class="sxs-lookup"><span data-stu-id="561bb-196">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="561bb-p120">낮은 우선 순위 메일의 사용자를 유지할 수 있나요? 낮은 우선 순위 메일 및 중요 받은 편지함 사용에 대한 Microsoft의 권장 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="561bb-p120">Can I keep users on Clutter? What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="561bb-p121">예, 낮은 우선 순위 메일의 사용자를 유지하고 중요 받은 편지함을 사용하지 않도록 설정할 수 있습니다. 하지만 결국 낮은 우선 순위 메일이 중요 받은 편지함으로 완전히 대체되므로 Microsoft에서는 지금 바로 중요 받은 편지함으로 이동하는 것을 권장합니다. Exchange Online에서 낮은 우선 순위 메일을 사용하는 경우에 대해 자세히 알아보려면 다음 블로그 게시물을 참조하세요. [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)(중요 받은 편지함에 대한 업데이트 및 낮은 우선 순위 메일에 대한 우리의 계획)</span><span class="sxs-lookup"><span data-stu-id="561bb-p121">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="561bb-201">모든 사용자가 중요 받은 편지함으로 이동하려는 경우 일반 사용자에 대해 낮은 우선 순위 메일을 사용하지 않도록 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-201">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="561bb-p122">아니요. Set-Clutter cmdlet을 실행하여 명시적으로 사서함에 대해 낮은 우선 순위 메일을 사용하지 않도록 설정할 수 있습니다. 그러나 이렇게 하면 이전에 낮은 우선 순위 메일 폴더로 리디렉션된 메시지는 해당 받은 편지함에 그대로 유지되며 중요 받은 편지함을 지원하는 버전으로 해당 클라이언트가 업그레이드될 때까지 이들 메시지를 처리해야 한다는 메시지가 사서함 소유자에게 표시됩니다. 따라서 업그레이드된 클라이언트를 사용할 수 있을 때까지 낮은 우선 순위 메일을 사용하지 않도록 설정하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p122">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="561bb-206">중요 받은 편지함 관리를 위해 두 가지 cmdlet이 있는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="561bb-206">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="561bb-207">중요 받은 편지함과 연관된 상태는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-207">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="561bb-208">**조직 수준**: 중요 받은 편지함 상태 및 연관된 마지막 업데이트 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-208">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span>

- <span data-ttu-id="561bb-209">**사서함 수준​​**: 중요 받은 편지함 상태 및 연관된 마지막 업데이트 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-209">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="561bb-210">Outlook에서 이러한 두 가지 상태로 중요 받은 편지함 환경 표시를 결정하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="561bb-210">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="561bb-p123">Outlook은 최신 타임스탬프가 있는 cmdlet을 선택하여 환경 표시를 결정합니다. 기본적으로 두 타임스탬프 모두 “null”이며 이런 경우에는 이 기능이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p123">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="561bb-213">조직에서 중요 받은 편지함을 껐는데 Get-FocusedInbox cmdlet에서 “true”를 반환하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="561bb-213">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="561bb-p124">중요 받은 편지함을 제어하는 cmdlet은 두 가지입니다. 사서함에 대해 Get-FocusedInbox를 실행하면 이 기능의 사서함 수준 상태를 반환합니다. Outlook의 환경은 마지막으로 수정된 cmdlet 상태를 기반으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p124">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="561bb-217">스크립트를 실행하여 중요 받은 편지함을 설정한 사용자를 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="561bb-217">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="561bb-p125">아니요. 불가능하도록 설계되어 있습니다. 중요 받은 편지함 사용 여부는 클라이언트 쪽 설정이므로 cmdlet에서는 사용자의 사서함을 클라이언트 환경에 사용할 수 있는지만 알려 줄 수 있습니다. 동시에 어떤 클라이언트에서는 사용하도록 설정하고 어떤 클라이언트에서는 사용하지 않도록 설정할 수도 있습니다. 예를 들어 Outlook 앱과 Outlook 모바일에서는 사용하지만 웹용 Outlook에서는 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="561bb-p125">No, and this is by design. Focused Inbox enablement is a client-side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>

## <a name="related-content"></a><span data-ttu-id="561bb-221">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="561bb-221">Related content</span></span>

<span data-ttu-id="561bb-222">[조직에 대한 낮은 우선 순위 메일 구성](../email/configure-clutter.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="561bb-222">[Configure Clutter for your organization](../email/configure-clutter.md) (article)</span></span>\
<span data-ttu-id="561bb-223">[공유 사서함 설정 구성](../email/configure-a-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="561bb-223">[Configure shared mailbox settings](../email/configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="561bb-224">[서명 및 고지 사항 만들기](create-signatures-and-disclaimers.md)(비디오)</span><span class="sxs-lookup"><span data-stu-id="561bb-224">[Create signatures and disclaimers](create-signatures-and-disclaimers.md) (video)</span></span>

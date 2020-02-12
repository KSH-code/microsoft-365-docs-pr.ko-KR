---
title: Exchange Online에서 최종 사용자 스팸 알림 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 회사 전체의 기본 스팸 필터 정책 또는 도메인에 적용 되는 사용자 지정 스팸 필터 정책에 대 한 최종 사용자 스팸 알림을 구성할 수 있습니다.
ms.openlocfilehash: f7ef916eea8d9c926f53ef073874dfb299cb92f8
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957393"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="a0d1c-103">Exchange Online에서 최종 사용자 스팸 알림 구성</span><span class="sxs-lookup"><span data-stu-id="a0d1c-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0d1c-104">이 항목은 클라우드 호스트 사서함을 보호 하는 Exchange Online 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="a0d1c-105">EOP (Exchange Online Protection) 온-프레미스 사서함을 보호 하는 독립 실행형 고객은 [EOP에서 최종 사용자 스팸 알림 구성](configure-end-user-spam-notifications-in-eop.md)항목을 대신 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="a0d1c-106">회사 전체의 기본 스팸 필터 정책 또는 사용자 지정 스팸 필터 정책에 대 한 최종 사용자 스팸 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="a0d1c-107">최종 사용자 스팸 알림 메시지를 사용 하도록 설정 하면 사용자가 격리 된 스팸, 대량 및 피싱 메시지를 직접 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="a0d1c-p103">최종 사용자 스팸 알림에는 사용자가 구성한 기간(1일부터 15일 사이의 값을 지정할 수 있음)에 최종 사용자가 받은, 스팸으로 격리된 모든 메시지의 목록이 포함됩니다. 알림 메시지를 작성하는 언어도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="a0d1c-110">최종 사용자는 알림 메시지를 받은 후 다음 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="a0d1c-111">Office 365에서 수신 거부 목록에 보낸 사람을 추가 하려는 경우 **보낸 사람을 차단** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="a0d1c-112">메시지가 스팸으로 아니면 Office 365에서 사서함으로 메시지를 보내도록 하려면 **릴리스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="a0d1c-113">Preview 또는 Release와 같은 다른 작업을 수행 하려는 경우 보안 & 준수 센터 내의 격리 포털로 이동 하는 방법을 **검토** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a0d1c-114">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="a0d1c-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="a0d1c-115">예상 완료 시간: 2분</span><span class="sxs-lookup"><span data-stu-id="a0d1c-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="a0d1c-116">이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="a0d1c-117">필요한 사용 권한을 확인 하려면 [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) 항목에서 "스팸 방지" 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="a0d1c-118">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="a0d1c-119">EAC를 통해 최종 사용자 스팸 알림 구성</span><span class="sxs-lookup"><span data-stu-id="a0d1c-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="a0d1c-120">EAC (Exchange 관리 센터)에서 **보호** \> **스팸 필터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="a0d1c-121">최종 사용자 스팸 알림을 사용 하도록 설정 하려는 스팸 필터 정책을 선택 합니다 (기본적으로 사용 하지 않도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="a0d1c-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="a0d1c-122">정책 요약 정보가 표시되는 오른쪽 창에서 **최종 사용자 스팸 알림 구성** 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="a0d1c-123">이후 표시되는 대화 상자에서 다음 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="a0d1c-p105">**최종 사용자 스팸 알림 사용** 해당 정책에 대한 최종 사용자 스팸 알림을 사용하도록 설정하려면 이 확인란을 선택합니다. 그러나 반대로 해당 정책이 사용하도록 설정되어 있으면 이 확인란을 선택 취소하여 해당 정책에 대한 최종 사용자 스팸 알림을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="a0d1c-p106">**최종 사용자 스팸 알림을 매번(매일) 전송** 최종 사용자 스팸 알림의 전송 빈도를 지정합니다. 기본값은 3일입니다. 1일부터 15일 사이의 값을 지정할 수 있습니다. 예를 들어 7일을 지정하면 스팸 격리 사서함으로 전송되는 대신 지난 7일 이내에 해당 사용자에게 보내려고 했던 모든 메시지의 목록이 알림에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="a0d1c-130">**알림 언어** 드롭다운 목록을 사용하여 이 정책의 최종 사용자 스팸 알림에 작성할 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="a0d1c-131">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-131">Click **Save**.</span></span> <span data-ttu-id="a0d1c-132">최종 사용자 스팸 알림 설정을 비롯 한 스팸 필터 정책 설정에 대 한 요약이 오른쪽 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="a0d1c-133">최종 사용자 스팸 알림은 사용 하도록 설정 된 스팸 필터 정책에 대해서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="a0d1c-134">>  최종 사용자 스팸 알림은 하루에 한 번만 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="a0d1c-135">특정 고객에 대한 알림 배달 시간을 보장하거나 구성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="a0d1c-136">**팁:** 최종 사용자 스팸 알림을 완전히 구현 하기 전에 제한 된 사용자 집합에 전송 하 여 테스트 하려면 사용자가 거주 하는 도메인에 대 한 최종 사용자 스팸 알림을 사용 하도록 설정 하는 사용자 지정 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="a0d1c-137">그런 다음 EAC의 **메일 흐름 \> 규칙**에서 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들어 알림을 수신 하려는 사용자에 대 한 예외와 함께 quarantine@messaging.microsoft.com (알림을 보내는 전자 메일 주소)에서 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="a0d1c-138">다음 그림은 Contoso.com 도메인의 두 사용자(SaraD 및 AlexD)에 대한 예외를 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![최종 사용자 스팸 알림을 테스트할 전송 규칙](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="a0d1c-140">SCC를 사용 하 여 최종 사용자 스팸 알림 구성</span><span class="sxs-lookup"><span data-stu-id="a0d1c-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="a0d1c-141">또한 SCC (보안 및 준수 센터)를 사용 하 여 최종 사용자 스팸 알림을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="a0d1c-142">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="a0d1c-142">Follow these steps:</span></span>

1. <span data-ttu-id="a0d1c-143">보안 및 준수 센터를 열고 **스팸 방지** https://protection.office.com/antispam를 위한 **위협 관리** \> **정책** \> 으로 이동 하거나 직접 링크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="a0d1c-144">최종 사용자 스팸 알림을 사용 하도록 설정 하려는 스팸 필터 정책 옆의 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="a0d1c-145">**최종 사용자 스팸 알림 구성** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="a0d1c-146">이후 표시되는 대화 상자에서 다음 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="a0d1c-p111">**최종 사용자 스팸 알림 사용** 해당 정책에 대한 최종 사용자 스팸 알림을 사용하도록 설정하려면 이 확인란을 선택합니다. 그러나 반대로 해당 정책이 사용하도록 설정되어 있으면 이 확인란을 선택 취소하여 해당 정책에 대한 최종 사용자 스팸 알림을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-p111">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="a0d1c-p112">**최종 사용자 스팸 알림을 매번(매일) 전송** 최종 사용자 스팸 알림의 전송 빈도를 지정합니다. 기본값은 3일입니다. 1일부터 15일 사이의 값을 지정할 수 있습니다. 예를 들어 7일을 지정하면 스팸 격리 사서함으로 전송되는 대신 지난 7일 이내에 해당 사용자에게 보내려고 했던 모든 메시지의 목록이 알림에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-p112">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="a0d1c-153">**알림 언어** 드롭다운 목록을 사용하여 이 정책의 최종 사용자 스팸 알림에 작성할 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="a0d1c-154">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-154">Click **Save**.</span></span> <span data-ttu-id="a0d1c-155">최종 사용자 스팸 알림 설정을 비롯 한 스팸 필터 정책 설정에 대 한 요약이 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d1c-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a0d1c-156">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="a0d1c-156">For more information</span></span>

[<span data-ttu-id="a0d1c-157">스팸 필터 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a0d1c-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  

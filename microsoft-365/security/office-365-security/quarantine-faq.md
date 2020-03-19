---
title: 격리 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Office 365의 격리에 대 한 질문과 대답
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856908"
---
# <a name="quarantine-faq-in-office-365"></a><span data-ttu-id="45ce2-103">Office 365의 격리 FAQ</span><span class="sxs-lookup"><span data-stu-id="45ce2-103">Quarantine FAQ in Office 365</span></span>

<span data-ttu-id="45ce2-104">이 항목에서는 Exchange Online 사서함이 없는 Exchange Online 또는 독립 실행형 EOP (Exchange Online Protection) 고객의 사서함을 포함 하는 Office 365 고객의 격리에 대 한 질문과 대답을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-104">This topic provides frequently asked questions and answers about quarantine for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="45ce2-105">Q: 맬웨어로부터 격리 된 메시지는 어떻게 관리 하나요?</span><span class="sxs-lookup"><span data-stu-id="45ce2-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="45ce2-106">관리자만이 맬웨어로 격리 된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="45ce2-107">자세한 내용은 [Office 365에서 격리 된 메시지 및 파일 관리로 관리자](manage-quarantined-messages-and-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce2-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="45ce2-108">Q: 스팸을 격리 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="45ce2-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="45ce2-109">대답.</span><span class="sxs-lookup"><span data-stu-id="45ce2-109">A.</span></span> <span data-ttu-id="45ce2-110">기본적으로 스팸 필터링을 통해 스팸으로 분류 되는 메시지는 사용자의 사서함에 배달 되 고 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="45ce2-111">그러나 스팸 또는 대량 전자 메일 메시지를 격리 하도록 스팸 방지 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="45ce2-112">자세한 내용은 [Office 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce2-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="45ce2-113">Q: 사용자에 게 격리에 대 한 액세스 권한을 부여 하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="45ce2-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="45ce2-114">대답.</span><span class="sxs-lookup"><span data-stu-id="45ce2-114">A.</span></span> <span data-ttu-id="45ce2-115">격리에서 자체 메시지에 액세스 하려면 사용자에 게 유효한 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="45ce2-116">독립 실행형 EOP 사용자가 EOP (디렉터리 동기화를 통해 수동으로 만들어지거나 만들어짐)에서 메일 사용자로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="45ce2-117">독립 실행형 EOP 환경에서 사용자를 관리 하는 방법에 대 한 자세한 내용은 [Manage mail users IN EOP](manage-mail-users-in-eop.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45ce2-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="45ce2-118">Q: 사용자가 격리에서 액세스할 수 있는 메시지는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="45ce2-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="45ce2-119">대답.</span><span class="sxs-lookup"><span data-stu-id="45ce2-119">A.</span></span> <span data-ttu-id="45ce2-120">사용자는 스팸, 대량 전자 메일에 액세스할 수 있으며, 2020 년 4 월에 해당 하 여 받는 사람 인 피싱 메시지가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="45ce2-121">최종 사용자는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 **호스트 된 격리 작업으로 메시지를 배달 하** 여 격리 된 맬웨어, 높은 신뢰도 피싱 또는 격리 되어 있는 메시지에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="45ce2-122">격리 된 메시지에 액세스 하는 사용자에 대 한 자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce2-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="45ce2-123">Q: 메시지가 격리에 보관 되는 기간</span><span class="sxs-lookup"><span data-stu-id="45ce2-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="45ce2-124">대답.</span><span class="sxs-lookup"><span data-stu-id="45ce2-124">A.</span></span> <span data-ttu-id="45ce2-125">스팸 방지 정책을 사용 하 여 스팸, 피싱 및 대량 전자 메일 메시지가 격리에 보관 되는 기간을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="45ce2-126">기본값은 30 일 이며 최대값 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="45ce2-127">자세한 내용은 [Office 365에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45ce2-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="45ce2-128">메일 흐름 규칙 작업에 의해 격리 된 메시지에 대해 **호스팅된 격리로**메시지를 배달 하면 메시지가 30 일 동안 격리 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="45ce2-129">이 기간을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-129">You can't configure this duration.</span></span>

<span data-ttu-id="45ce2-130">기간이 만료 되 면 메시지가 삭제 되며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="45ce2-131">Q: 한 번에 두 개 이상의 격리 된 메시지를 릴리스 또는 보고할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="45ce2-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="45ce2-132">대답.</span><span class="sxs-lookup"><span data-stu-id="45ce2-132">A.</span></span> <span data-ttu-id="45ce2-133">보안 & 준수 센터에서는 메시지를 한 번에 최대 100 개까지 선택 하 고 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="45ce2-134">관리자는 Exchange Online PowerShell 또는 독립 실행형 Exchange Online Protection PowerShell의 [get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) 및 [Release get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet을 사용 하 여 격리 된 메시지를 검색 하 고 일괄적으로 해제 하며, 가양성을 허위에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="45ce2-135">Q: 격리 된 메시지를 검색할 때 와일드 카드를 지원 하나요?</span><span class="sxs-lookup"><span data-stu-id="45ce2-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="45ce2-136">특정 도메인에 대해 격리된 메시지를 검색할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="45ce2-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="45ce2-137">대답.</span><span class="sxs-lookup"><span data-stu-id="45ce2-137">A.</span></span> <span data-ttu-id="45ce2-138">보안 & 준수 센터에서는 와일드 카드가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="45ce2-139">예를 들어 보낸 사람을 검색할 때는 전체 전자 메일 주소를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="45ce2-140">그러나 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 와일드 카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="45ce2-141">예를 들어 contoso.com 도메인의 모든 보낸 사람 으로부터 격리 된 메시지를 찾으려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="45ce2-142">그런 다음 다음 명령을 실행 하 여 원래 받는 사람 모두에 게 해당 메시지를 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

<span data-ttu-id="45ce2-143">메시지를 해제 한 후에는 다시 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-143">After you release a message, you can't release it again.</span></span>

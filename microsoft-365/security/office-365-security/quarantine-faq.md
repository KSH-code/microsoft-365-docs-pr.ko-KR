---
title: 격리된 메시지 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 격리된 메시지에 대한 질문과 대답을 볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826792"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="d9173-103">격리된 메시지 FAQ</span><span class="sxs-lookup"><span data-stu-id="d9173-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="d9173-104">이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 대해 격리된 전자 메일 메시지에 대한 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="d9173-105">스팸 방지 보호 기능에 대한 질문과 대답은 스팸 [방지 보호 FAQ를 참조하세요.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="d9173-106">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 [방지 보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="d9173-107">스푸핑 방지 보호 기능에 대한 질문과 대답은 [스푸핑 방지 보호 기능 FAQ를 참조하세요.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="d9173-108">맬웨어에 대해 격리된 메시지를 관리하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d9173-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="d9173-109">관리자만 맬웨어에 대해 격리된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="d9173-110">자세한 내용은 [격리된 메시지 및 파일관리를 관리자로 관리하여 참조하세요.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="d9173-111">스팸을 격리하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d9173-111">How do I quarantine spam?</span></span>

<span data-ttu-id="d9173-112">기본적으로 스팸 또는 스팸 필터링을 통해 스팸으로 분류된 대량 전자 메일로 분류된 메시지는 사용자의 사서함에 배달되며 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="d9173-113">그러나 스팸 이나 대량 전자 메일 메시지를 격리하도록 스팸 방지 정책을 만들고 구성할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="d9173-114">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9173-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="d9173-115">사용자에게 격리 액세스 권한을 어떻게 부여하나요?</span><span class="sxs-lookup"><span data-stu-id="d9173-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="d9173-116">사용자가 격리된 메시지에 액세스하려면 유효한 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="d9173-117">독립 실행형 EOP를 사용하려면 사용자가 EOP에서 메일 사용자로 표현됩니다(디렉터리 동기화를 통해 수동으로 만들거나 만듭니다).</span><span class="sxs-lookup"><span data-stu-id="d9173-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="d9173-118">독립 실행형 EOP 환경에서 사용자를 관리하는 방법에 대한 자세한 내용은 EOP에서 [메일 사용자 관리를 참조하세요.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="d9173-119">최종 사용자가 격리에 액세스할 수 있는 메시지는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d9173-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="d9173-120">사용자는 스팸, 대량 전자 메일 및 (2020년 4월을 바를 대상으로) 피싱 메시지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="d9173-121">최종 사용자가 메일 흐름 규칙(전송 규칙이라고도 함)에서 호스트된 격리 작업으로 인해 격리된 맬웨어, 높은 신뢰도 **Deliver the message to the hosted quarantine** 피싱 또는 격리된 메시지에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d9173-122">격리된 메시지에 액세스하는 사용자에 대한 자세한 내용은 격리된 메시지 찾기 및 [해제를 사용자로 받습니다.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="d9173-123">메시지는 어떻게 격리에 보존됩니까?</span><span class="sxs-lookup"><span data-stu-id="d9173-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="d9173-124">스팸 방지 정책을 사용하여 스팸, 피싱 및 대량 전자 메일 메시지가 격리에 보관되는 시간을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="d9173-125">기본값은 30일이며 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="d9173-126">자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d9173-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="d9173-127">메일 흐름 규칙 동작에 의해 격리된 메시지의 경우 메시지가 호스팅된 **격리로**배달된 메시지의 경우 메시지가 30일 동안 격리에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="d9173-128">이 기간은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-128">You can't configure this duration.</span></span>

<span data-ttu-id="d9173-129">해당 기간이 만료되면 메시지가 삭제되며 복구할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="d9173-130">한 번에 2개 이상의 격리된 메시지를 해제하거나 보고할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d9173-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="d9173-131">보안 설정 & 목록에서 최대 100개 메시지를 클릭하고 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="d9173-132">관리자는 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell의 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 및 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet을 사용하여 격리된 메시지를 대량으로 찾아 릴리스하고 가양성을 대량으로 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="d9173-133">격리된 메시지 검색 시 와일드카드가 지원됩니까?</span><span class="sxs-lookup"><span data-stu-id="d9173-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="d9173-134">특정 도메인에 대해 격리된 메시지를 검색할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d9173-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="d9173-135">와일드카드는 보안 및 준수 센터에서 & 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="d9173-136">예를 들어 보낸 사람을 검색할 때는 전체 전자 메일 주소를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="d9173-137">그렇지만 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 와일드카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="d9173-138">예를 들어 다음 명령을 사용하여 도메인 나의 모든 보낸 사람으로부터 스팸 격리된 메시지를 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d9173-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="d9173-139">그런 다음 아래 명령을 실행하여 해당 메시지를 원래 받는 사람 모두로 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="d9173-140">메시지를 해제한 후에는 다시 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-140">After you release a message, you can't release it again.</span></span>

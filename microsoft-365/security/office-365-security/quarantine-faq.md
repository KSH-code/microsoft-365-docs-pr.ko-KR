---
title: Quarantined messages FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 EOP(Exchange Online Protection)에서 자주 묻는 질문과 대답을 볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: abd2304e83d2814cab55d13312535bd94308d8be
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032604"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="9bb1e-103">Quarantined messages FAQ</span><span class="sxs-lookup"><span data-stu-id="9bb1e-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9bb1e-104">이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 대해 자주 묻는 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="9bb1e-105">스팸 방지 보호에 대한 질문과 대답은 스팸 방지 보호 [FAQ를 참조하세요.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="9bb1e-106">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 방지 [보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="9bb1e-107">스푸핑 방지 보호에 대한 질문과 대답은 스푸핑 방지 보호 [FAQ를 참조하세요.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="9bb1e-108">맬웨어에 대해 고지된 메시지는 어떻게 관리하나요?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="9bb1e-109">관리자만 맬웨어에 대해 고지된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="9bb1e-110">자세한 내용은 관리자로 [quarantined messages and files를 참조하십시오.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="9bb1e-111">스팸을 어떻게 차단하나요?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-111">How do I quarantine spam?</span></span>

<span data-ttu-id="9bb1e-112">기본적으로 스팸 필터링을 통해 스팸 또는 대량 전자 메일로 분류된 메시지는 사용자의 사서함으로 배달되어 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="9bb1e-113">그러나 스팸 또는 대량 전자 메일 메시지를 대신 차단하도록 스팸 방지 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="9bb1e-114">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="9bb1e-115">사용자에게 검지 액세스 권한을 부여하는 방법</span><span class="sxs-lookup"><span data-stu-id="9bb1e-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="9bb1e-116">사용자는 자신의 메시지에 액세스하려면 유효한 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="9bb1e-117">독립 실행형 EOP를 사용하려면 사용자가 EOP에서 메일 사용자로 표시됩니다(디렉터리 동기화를 통해 수동으로 만들거나 생성).</span><span class="sxs-lookup"><span data-stu-id="9bb1e-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="9bb1e-118">독립 실행형 EOP 환경에서 사용자를 관리하는 데 대한 자세한 내용은 [EOP에서 메일 사용자 관리를 참조하십시오.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="9bb1e-119">최종 사용자가 어떤 메시지에 액세스하여 액세스할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="9bb1e-120">사용자는 스팸, 대량 전자 메일 및 받는 사람인 피싱 메시지(2020년 4월 현재)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="9bb1e-121">최종 사용자는 메일 흐름 규칙(전송 규칙)에서 호스트된 차단 작업으로 메시지를 배달하여 고지된 맬웨어, 높은 신뢰도 피싱 또는 메시지에 액세스할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="9bb1e-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="9bb1e-122">Quarantined Messages에 액세스하는 사용자에 대한 자세한 내용은 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="9bb1e-123">메시지가 얼마나 오래 보관하나요?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="9bb1e-124">스팸 방지 정책을 사용하여 스팸, 피싱 및 대량 전자 메일 메시지가 보관된 기간을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="9bb1e-125">기본값은 최대 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="9bb1e-126">자세한 내용은 EOP에서 스팸 방지 [정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9bb1e-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="9bb1e-127">메일 흐름 규칙 동작에 의해 검리된 메시지의 경우 메시지를 호스팅된 검지로 배달하면 메시지는 30일 동안 보관됩니다. </span><span class="sxs-lookup"><span data-stu-id="9bb1e-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="9bb1e-128">이 기간은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-128">You can't configure this duration.</span></span>

<span data-ttu-id="9bb1e-129">기간이 만료되면 메시지가 삭제되고 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="9bb1e-130">한 번에 2개 이상의 격리된 메시지를 해제하거나 보고할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="9bb1e-131">보안 & 준수 센터에서 한에 최대 100개 메시지를 선택하고 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="9bb1e-132">관리자는 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 및 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet을 사용하여 대량으로 독립 실행형 메시지를 찾아서 릴리스하고 가짓 긍정을 대량으로 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="9bb1e-133">격리된 메시지 검색 시 와일드카드가 지원됩니까?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="9bb1e-134">특정 도메인에 대해 격리된 메시지를 검색할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="9bb1e-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="9bb1e-135">와일드카드는 보안 및 준수 센터에서 & 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="9bb1e-136">예를 들어 보낸 사람 검색 시 전체 전자 메일 주소를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="9bb1e-137">그러나 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 와일드카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="9bb1e-138">예를 들어 다음 PowerShell 코드를 메모장에 복사하고 파일을 쉽게 찾을 수 있는 위치에 .ps1로 저장합니다(예: C:\Data\QuarantineRelease.ps1.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-138">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="9bb1e-139">그런 다음 Exchange [Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 또는 [Exchange Online Protection PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)연결한 후 다음 명령을 실행하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-139">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="9bb1e-140">스크립트는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-140">The script does the following actions:</span></span>

- <span data-ttu-id="9bb1e-141">fabrikam 도메인의 모든 보낸 사람으로부터 스팸으로 스팸으로 차단된 미해제 메시지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-141">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="9bb1e-142">최대 결과 수는 50,000개(결과 1000페이지 50개)입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-142">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="9bb1e-143">결과를 CSV 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-143">Save the results to a CSV file.</span></span>
- <span data-ttu-id="9bb1e-144">일치하는 메시지를 원래 받는 사람에게 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-144">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="9bb1e-145">메시지를 릴리스한 후 다시 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb1e-145">After you release a message, you can't release it again.</span></span>

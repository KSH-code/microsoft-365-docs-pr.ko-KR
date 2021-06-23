---
title: Microsoft에 스팸, 스팸이 아닌 메시지 및 피싱 메시지 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 관리자는 분석을 위해 Microsoft에 좋은 메시지와 잘못된 메시지와 파일을 보고하는 다양한 방법에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082819"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="508bf-103">Microsoft에 메시지와 파일 보고</span><span class="sxs-lookup"><span data-stu-id="508bf-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="508bf-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="508bf-104">**Applies to**</span></span>
- [<span data-ttu-id="508bf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="508bf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="508bf-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="508bf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="508bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="508bf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="508bf-108">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection)에 사서함이 있는 Exchange Online 조직에서는 사용자와 관리자 모두 Microsoft에 전자 메일 메시지와 파일을 보고하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="508bf-109">메서드</span><span class="sxs-lookup"><span data-stu-id="508bf-109">Method</span></span>|<span data-ttu-id="508bf-110">설명</span><span class="sxs-lookup"><span data-stu-id="508bf-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="508bf-111">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="508bf-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="508bf-112">사서함이 있는 조직의 관리자에게 권장되는 보고 Exchange Online(독립 실행형 EOP에서는 사용할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="508bf-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="508bf-113">보고서 메시지 또는 피싱 보고 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="508bf-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="508bf-114">Outlook 및 웹용 Outlook(이전의 Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="508bf-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="508bf-115">구독에 따라 사용자가 추가 기능으로 보고한 메시지는 [관리](admin-submission.md)제출 포털, 자동화된 조사 및 [응답(AIR)](air-view-investigation-results.md)결과, [사용자가](view-email-security-reports.md#user-reported-messages-report)보고한 메시지 보고서 및 탐색기 에서 사용할 수 [있습니다.](threat-explorer-views.md#email--submissions)</span><span class="sxs-lookup"><span data-stu-id="508bf-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="508bf-116">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="508bf-117">자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="508bf-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="508bf-118">Outlook에서 가양성 및 가음성 보고</span><span class="sxs-lookup"><span data-stu-id="508bf-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="508bf-119">보고서 메시지 기능을 사용하여 가음성(차단되거나 정크 폴더로 전송된 양호한 전자 메일) 및 거짓 부정(받은 편지함으로 배달된 원치 않는 전자 메일 또는 피싱)을 Exchange Online Protection(EOP)에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="508bf-120">분석을 위해 Microsoft에 수동으로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="508bf-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="508bf-121">스팸 및 피싱이 아닌 스팸에 대해 특정 Microsoft 전자 메일 주소로 첨부된 메시지를 수동으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="508bf-122">메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인</span><span class="sxs-lookup"><span data-stu-id="508bf-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="508bf-123">사용자가 분석을 위해 Microsoft에 메시지를 보고할 때 이를 알 수 있는 메일 흐름 규칙(전송 규칙)을 만드는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="508bf-124">분석을 위해 Microsoft에 맬웨어 및 맬웨어가 아닌 제출</span><span class="sxs-lookup"><span data-stu-id="508bf-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="508bf-125">사이트 Microsoft 보안 인텔리전스 사용하여 첨부 파일 및 기타 파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="508bf-126">스팸 또는 피싱 메시지가 배달되지 않고 검리된 경우 사용자는 검색 포털의 Quarantine에서 Microsoft에 메시지를 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="508bf-127">자세한 내용은 [Find and release quarantined messages as a user in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="508bf-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="508bf-128">Microsoft로 전송되는 데이터는 북미 데이터 센터의 Office 365 규정 준수 경계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="508bf-129">이 데이터는 엔지니어링 팀의 분석가가 필터의 효율성을 개선하는 데 도움을 주며 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="508bf-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

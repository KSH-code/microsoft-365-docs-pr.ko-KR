---
title: 분석을 위해 Microsoft에 수동으로 메시지 전송
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 관리자와 최종 사용자는 분석을 위해 Microsoft에 전자 메일 메시지(잘못된 메일 또는 잘못된 메일로 표시된 양호한 메일)를 Microsoft에 전자 메일로 전송하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3a02c710472a996245a38d996ff4485efd1748
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624028"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="f844e-103">분석을 위해 Microsoft에 수동으로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="f844e-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f844e-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f844e-104">**Applies to**</span></span>
- [<span data-ttu-id="f844e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f844e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f844e-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f844e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f844e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f844e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f844e-108">사서함이 있는 조직의 관리자인 Exchange Online 보안 및 준수 센터의 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f844e-109">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f844e-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f844e-110">조직의 사용자가 받은 편지함에서 정크 메시지(스팸) 또는 피싱 메시지를 받거나 정크 메일로 표시되어 합법적인 전자 메일 메시지를 받지 못하면 좌절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="f844e-111">스팸 필터의 정확도를 더 정확하게 조정하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="f844e-112">사용자와 사용자는 분석을 위해 가음성(나쁜 것으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 메일 허용) 및 피싱 메시지를 Microsoft에 제출하여 이 프로세스를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="f844e-113">수신하는 제출의 양이 높기 때문에 분석에 대한 모든 요청에 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="f844e-114">Microsoft에 거짓 부정 제출</span><span class="sxs-lookup"><span data-stu-id="f844e-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f844e-115">다음 절차에 따라 거짓 부정을 보고하는 대신 웹 Outlook Outlook(이전의 Outlook Web App)의 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="f844e-116">이러한 도구를 설치하고 사용하는 방법에 대한 자세한 내용은 [보고서](enable-the-report-message-add-in.md) 메시지 추가 기능 사용 및 피싱 보고서 추가 기능 사용을 [참조하세요.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f844e-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f844e-117">스팸 필터링을 통과하여 스팸 또는 피싱으로 식별된 메시지를 받은 경우 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀에 적절하게 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="f844e-118">분석가가 메시지를 검토하고 분류 기준을 충족하는 경우 서비스 전체 필터에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="f844e-119">다음 받는 사람 중 하나를 사용하여 비어 있는 새 전자 메일 메시지를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="f844e-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="f844e-120">**정크**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f844e-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="f844e-121">**피싱**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f844e-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="f844e-122">정크 또는 피싱 메시지를 새 메시지로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="f844e-123">이렇게 하면 정크 또는 피싱 메시지가 새 메시지의 첨부 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="f844e-124">메시지 헤더를 검사할 수 있도록 원본 메시지가 필요하여 메시지의 내용을 복사하여 붙여 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f844e-125">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f844e-126">모든 메시지가 피싱 메시지 또는 정크 메일 메시지와 같은 유형으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="f844e-127">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="f844e-128">첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(웹 Outlook 형식의 기본 형식) 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="f844e-129">완료되면 보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f844e-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f844e-130">관리자는 스팸으로 오인되는 특정 메시지를 차단하는 여러 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="f844e-131">자세한 내용은 [EOP에서 차단된 보낸 사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f844e-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="f844e-132">Microsoft에 가짓 긍정 제출</span><span class="sxs-lookup"><span data-stu-id="f844e-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f844e-133">다음 절차에 따라 가짓 긍정을 보고하는 대신 웹 Outlook Outlook(이전의 Outlook Web App)의 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="f844e-134">이러한 도구를 설치하고 사용하는 방법에 대한 자세한 내용은 [보고서](enable-the-report-message-add-in.md) 메시지 추가 기능 사용 및 피싱 보고서 추가 기능 사용을 [참조하세요.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f844e-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f844e-135">메시지가 스팸으로 잘못 식별된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f844e-136">분석가가 메시지를 평가하고 분석 결과에 따라 메시지 통과를 허용하도록 서비스 전체 필터를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="f844e-137">받는 사람으로 새 비어 있는 전자 `not_junk@office365.microsoft.com` 메일 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="f844e-138">잘못 확인된 메시지를 새 메시지로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="f844e-139">이렇게 하면 잘못 확인된 메시지가 새 메시지의 첨부 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="f844e-140">메시지 헤더를 검사할 수 있도록 원본 메시지가 필요하여 메시지의 내용을 복사하여 붙여 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f844e-141">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f844e-142">모든 메시지가 피싱 메시지 또는 정크 메일 메시지와 같은 유형으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="f844e-143">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="f844e-144">첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(웹 Outlook 형식의 기본 형식) 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="f844e-145">완료되면 보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f844e-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f844e-146">관리자는 특정 메시지가 스팸 필터링을 건너뛸 수 있도록 여러 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="f844e-147">자세한 내용은 EOP에서 수신이 가능한 보낸 사람 [목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f844e-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="f844e-148">Microsoft에 전송되는 데이터는 어디에 저장되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="f844e-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="f844e-149">데이터는 북미 데이터 센터의 Office 365 규정 준수 경계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="f844e-150">이 데이터는 엔지니어링 팀의 분석가가 필터의 효율성을 개선하는 데 도움을 주며 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f844e-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="f844e-151">Microsoft에 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="f844e-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="f844e-152">자세한 내용은 메일 흐름 규칙을 사용하여 Microsoft에 보고하는 사용자 [확인을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f844e-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>

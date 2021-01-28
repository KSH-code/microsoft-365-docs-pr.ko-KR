---
title: 분석을 위해 Microsoft에 수동으로 메시지 제출
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
description: 관리자와 최종 사용자는 분석을 위해 Microsoft에 전자 메일 메시지(나쁜 메일 또는 잘못된 메일로 표시된 좋은 메일)를 전자 메일로 전송하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5d3b7a51c39b85af8a6fae84f525da6d806789c
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029587"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="f5bb2-103">분석을 위해 Microsoft에 수동으로 메시지 제출</span><span class="sxs-lookup"><span data-stu-id="f5bb2-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f5bb2-104">Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터에서 제출 포털을 & 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f5bb2-105">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 [Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f5bb2-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f5bb2-106">조직의 사용자가 받은 편지함에서 정크 메시지(스팸) 또는 피싱 메시지를 받거나 정크 메일로 표시되어 합법적인 전자 메일 메시지를 받지 못하면 좌절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="f5bb2-107">스팸 필터의 정확도를 개선하기 위해 지속적으로 미세 조정하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="f5bb2-108">사용자와 사용자는 분석을 위해 가음성(양호한 전자 메일), 거짓 부정(잘못된 메일 허용) 및 피싱 메시지를 Microsoft에 제출하여 이 프로세스를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="f5bb2-109">수신하는 제출의 양이 높기 때문에 분석에 대한 모든 요청에 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="f5bb2-110">Microsoft에 거짓 부정 제출</span><span class="sxs-lookup"><span data-stu-id="f5bb2-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f5bb2-111">다음 절차에 따라 거짓 부정을 보고하는 대신 Outlook 및 웹용 Outlook(이전의 Outlook Web App)에서 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="f5bb2-112">이러한 도구를 설치하고 사용하는 방법에 대한 [](enable-the-report-message-add-in.md) 자세한 내용은 보고서 메시지 추가 기능을 사용하도록 설정하고 보고서 피싱 추가 기능을 사용하도록 [설정하십시오.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f5bb2-112">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f5bb2-113">스팸 필터링을 통과하여 스팸 또는 피싱으로 식별된 메시지를 받은 경우 해당 메시지를 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀으로 적절하게 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="f5bb2-114">분석가가 메시지를 검토하고 분류 기준을 충족하는 경우 서비스 전체 필터에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="f5bb2-115">다음 받는 사람 중 하나를 사용하여 비어 있는 새 전자 메일 메시지를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="f5bb2-116">**정크**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f5bb2-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="f5bb2-117">**피싱**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f5bb2-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="f5bb2-118">정크 또는 피싱 메시지를 끌어서 새 메시지에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="f5bb2-119">이렇게 하면 정크 또는 피싱 메시지가 새 메시지의 첨부 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="f5bb2-120">메시지의 내용을 복사하여 붙여 넣거나 메시지를 전달하지 않습니다(메시지 헤더를 검사할 수 있도록 원본 메시지가 필요).</span><span class="sxs-lookup"><span data-stu-id="f5bb2-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f5bb2-121">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f5bb2-122">모든 메시지가 피싱 메시지 또는 정크 메일 메시지와 같은 유형으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="f5bb2-123">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="f5bb2-124">첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(기본 웹용 Outlook 형식) 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="f5bb2-125">완료되면 보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5bb2-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f5bb2-126">관리자는 스팸으로 오인되는 특정 메시지를 차단하는 여러 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="f5bb2-127">자세한 내용은 [EOP에서 차단된 보낸 사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f5bb2-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="f5bb2-128">Microsoft에 가짓 긍정 제출</span><span class="sxs-lookup"><span data-stu-id="f5bb2-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f5bb2-129">다음 절차에 따라 가짓 긍정을 보고하는 대신 Outlook 및 웹용 Outlook(이전의 Outlook Web App)에서 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="f5bb2-130">이러한 도구를 설치하고 사용하는 방법에 대한 [](enable-the-report-message-add-in.md) 자세한 내용은 보고서 메시지 추가 기능을 사용하도록 설정하고 보고서 피싱 추가 기능을 사용하도록 [설정하십시오.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f5bb2-130">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="f5bb2-131">메시지가 스팸으로 잘못 식별된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f5bb2-132">분석가가 메시지를 평가하고 분석 결과에 따라 메시지 통과를 허용하도록 서비스 전체 필터를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="f5bb2-133">받는 사람으로 비어 있는 새 전자 메일 `not_junk@office365.microsoft.com` 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="f5bb2-134">잘못 확인된 메시지를 끌어서 새 메시지에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="f5bb2-135">그러면 잘못 확인된 메시지가 새 메시지의 첨부 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="f5bb2-136">메시지의 내용을 복사하여 붙여 넣거나 메시지를 전달하지 않습니다(메시지 헤더를 검사할 수 있도록 원본 메시지가 필요).</span><span class="sxs-lookup"><span data-stu-id="f5bb2-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f5bb2-137">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f5bb2-138">모든 메시지가 피싱 메시지 또는 정크 메일 메시지와 같은 유형으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="f5bb2-139">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="f5bb2-140">첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(기본 웹용 Outlook 형식) 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="f5bb2-141">완료되면 보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5bb2-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f5bb2-142">관리자는 특정 메시지가 스팸 필터링을 건너뛸 수 있도록 여러 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="f5bb2-143">자세한 내용은 [EOP에서 수신이 가능한 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f5bb2-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="f5bb2-144">Microsoft로 전송되는 데이터는 어디에 저장되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="f5bb2-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="f5bb2-145">데이터는 북미 데이터 센터의 Office 365 규정 준수 경계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="f5bb2-146">이 데이터는 엔지니어링 팀의 분석가가 필터의 효율성을 높이기 위해 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="f5bb2-147">Microsoft에 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="f5bb2-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="f5bb2-148">자세한 내용은 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고하는 사항을 [참조하세요.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f5bb2-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>

---
title: 분석을 위해 Microsoft에 수동으로 메시지 제출
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 관리자 및 최종 사용자는 분석을 위해 Microsoft에 전자 메일 메시지(배지 또는 배지가 허용되지 않은 메일로 표시)를 Microsoft에 알아내세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f00f8399164a84d2cb9dae0c4c416b73dfb0dc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827812"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="45b2c-103">분석을 위해 Microsoft에 수동으로 메시지 제출</span><span class="sxs-lookup"><span data-stu-id="45b2c-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="45b2c-104">Exchange Online 사서함이 있는 조직의 관리자는 보안 그룹 규정 준수 센터의 전송 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="45b2c-105">자세한 내용은 [관리자 제출 사용을 참조하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="45b2c-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="45b2c-106">조직 내 사용자의 받은 편지함에 정크 메시지(스팸)나 피싱 메시지가 수신되거나 합법적 전자 메일 메시지가 정크 메일로 표시되어 수신되지 않는 경우 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="45b2c-107">Microsoft는 스팸 필터의 정확도를 지속적으로 미세 테스트하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="45b2c-108">가양성(좋은 전자 메일), 가양성(허용되지 않은 메일) 및 분석을 위해 Microsoft에 피싱 메시지를 제출하여 이 프로세스를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="45b2c-109">수신되는 많은 양의 제출 때문에 분석 요청은 모두 응답하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="45b2c-110">Microsoft에 거짓 부정 제출</span><span class="sxs-lookup"><span data-stu-id="45b2c-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="45b2c-111">다음 절차를 사용하여 거짓 부정을 보고하는 대신, 웹용 Outlook 및 웹 Outlook(이전하의 Outlook Web App)의 사용자는 Microsoft Outlook용 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="45b2c-112">이 도구를 설치하고 사용하는 방법에 대한 자세한 내용은 보고서 [메시지 추가 기능을 사용하도록 설정을 참조하십시오.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="45b2c-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="45b2c-113">스팸 또는 피싱으로 식별되어야 하는 스팸 필터링을 통과하는 메시지를 받은 경우 적절한 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀으로 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="45b2c-114">그런 다음, 작업자가 메시지를 검토한 다음 분류 조건을 충족하는 경우 서비스 전체 필터에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="45b2c-115">다음 받는 사람 중 하나로 비어 있는 새 전자 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="45b2c-116">**정크 크리스:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="45b2c-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="45b2c-117">**피싱**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="45b2c-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="45b2c-118">정크 또는 피싱 메시지를 새 메시지로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="45b2c-119">이렇게 하면 정크 또는 피싱 메시지가 새 메시지에 첨부 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="45b2c-120">메시지 헤더를 검사할 수 있도록 원본 메시지가 필요하기 위해 원본 메시지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="45b2c-121">새 메시지에서 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="45b2c-122">모든 메시지가 피싱 메시지나 정크 메일 메시지와 같은 유형이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="45b2c-123">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="45b2c-124">첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(기본 Outlook 형식) 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="45b2c-125">**보내기**: 1단계.com</span><span class="sxs-lookup"><span data-stu-id="45b2c-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="45b2c-126">관리자는 스팸으로 이런 방식으로 누락되는 특정 메시지를 차단하는 몇 가지 방법을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="45b2c-127">자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기를 참조하십시오.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="45b2c-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="45b2c-128">Microsoft에 가양성 제출</span><span class="sxs-lookup"><span data-stu-id="45b2c-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="45b2c-129">다음 절차를 통해 가양성을 보고하는 대신 Outlook 및 웹용 Outlook 사용자는 Microsoft Outlook용 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="45b2c-130">이 도구를 설치하고 사용하는 방법에 대한 자세한 내용은 보고서 [메시지 추가 기능을 사용하도록 설정을 참조하십시오.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="45b2c-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="45b2c-131">메시지가 스팸으로 잘못 식별된 경우 Microsoft 스팸 분석 팀으로 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="45b2c-132">분석가는 메시지를 평가하고 분석 결과에 따라 서비스 전체 필터가 조정되어 메시지 통과를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="45b2c-133">다음과 같이 받는 사람으로 새 빈 전자 `not_junk@office365.microsoft.com` 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="45b2c-134">확인되지 않은 메시지를 끌어다 놓는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="45b2c-135">이렇게 하면 잘못 식별된 메시지가 새 메시지에 첨부 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="45b2c-136">메시지 헤더를 검사할 수 있도록 원본 메시지가 필요하기 위해 원본 메시지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="45b2c-137">새 메시지에서 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="45b2c-138">모든 메시지가 피싱 메시지나 정크 메일 메시지와 같은 유형이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="45b2c-139">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="45b2c-140">첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(기본 Outlook 형식) 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="45b2c-141">**보내기**: 1단계.com</span><span class="sxs-lookup"><span data-stu-id="45b2c-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="45b2c-142">관리자는 특정 메시지가 스팸 필터링을 건너뛰도록 허용하는 여러 가지 방법을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b2c-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="45b2c-143">자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="45b2c-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="45b2c-144">Microsoft에 보고된 메시지 복사본을 수신할 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="45b2c-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="45b2c-145">자세한 내용은 메일 흐름 [규칙을 사용하여 사용자가 Microsoft에 보고한 내용을 확인합니다.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="45b2c-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>

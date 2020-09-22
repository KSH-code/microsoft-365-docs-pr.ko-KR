---
title: 분석을 위해 Microsoft에 수동으로 메시지 전송
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
description: 관리자 및 최종 사용자는 분석을 위해 Microsoft에 전자 메일 메시지 (잘못 되었거나 잘못 된 메일을 허용 하는 것으로 표시 된 좋은 메일)를 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6673dc7e7ac263ea9f734c002d0ffac410fadc07
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202206"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="c1785-103">분석을 위해 Microsoft에 수동으로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="c1785-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c1785-104">Exchange Online 사서함을 사용 하는 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c1785-105">자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1785-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c1785-106">조직의 사용자가 받은 편지함에서 정크 메시지 (스팸) 나 피싱 메시지를 받거나, 정크로 표시 되어 합법적인 전자 메일 메시지를 받지 못하는 경우에는 혼란을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="c1785-107">Microsoft는 스팸 필터를 보다 정확 하 게 미세 조정 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="c1785-108">귀하와 사용자는 가양성 (잘못 된 것으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 메일 허용), 분석을 위해 Microsoft에 피싱 메시지를 제출 하 여이 프로세스를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="c1785-109">수신 되는 전송 양이 많기 때문에 분석을 위해 모든 요청에 응답 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="c1785-110">Microsoft에 거짓 네거티브 전송</span><span class="sxs-lookup"><span data-stu-id="c1785-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="c1785-111">다음 절차를 사용 하 여 거짓 네거티브를 보고 하는 대신 Outlook 및 웹용 Outlook (이전의 Outlook Web App)에 있는 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="c1785-112">이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1785-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c1785-113">스팸 또는 피싱으로 식별 되어야 하는 스팸 필터링을 통해 전달 된 메시지를 수신 하는 경우 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀에 적절 하 게 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="c1785-114">분석가는 메시지를 검토 하 고 해당 메시지가 분류 기준을 충족 하는 경우 서비스 전체 필터에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="c1785-115">다음 받는 사람 중 하 나와의 비어 있는 새 전자 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="c1785-116">**정크 메일**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="c1785-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="c1785-117">**피싱**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="c1785-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="c1785-118">정크 또는 피싱 메시지를 새 메시지에 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="c1785-119">이렇게 하면 정크 또는 피싱 메시지가 새 메시지에 첨부 파일로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="c1785-120">메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).</span><span class="sxs-lookup"><span data-stu-id="c1785-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="c1785-121">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="c1785-122">모든 메시지의 유형 (피싱 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="c1785-123">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="c1785-124">첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="c1785-125">작업이 완료 되 면 **보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="c1785-126">관리자는 스팸으로 잘못 식별 되어는 특정 메시지를 차단 하는 여러 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="c1785-127">자세한 내용은 [EOP에서 차단 된 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1785-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="c1785-128">Microsoft에 가양성 제출</span><span class="sxs-lookup"><span data-stu-id="c1785-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="c1785-129">다음 절차를 사용 하 여 가양성을 보고 하는 대신 Outlook 및 웹용 Outlook의 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="c1785-130">이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1785-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c1785-131">메시지가 스팸으로 잘못 식별 된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="c1785-132">분석가는 메시지를 평가 하 고, 분석 결과에 따라, 서비스 전체 필터를 통해 메시지를 통과 하도록 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="c1785-133">받는 사람이 다음과 같은 비어 있는 새 전자 메일 메시지를 만듭니다 `not_junk@office365.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="c1785-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="c1785-134">잘못 식별 되어 메시지를 끌어서 새 메시지에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="c1785-135">이렇게 하면 잘못 식별 되어 메시지가 새 메시지에 첨부 파일로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="c1785-136">메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).</span><span class="sxs-lookup"><span data-stu-id="c1785-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="c1785-137">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="c1785-138">모든 메시지의 유형 (피싱 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="c1785-139">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="c1785-140">첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="c1785-141">작업이 완료 되 면 **보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="c1785-142">관리자는 특정 메시지에서 스팸 필터링을 건너뛰는 여러 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1785-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="c1785-143">자세한 내용은 [EOP에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1785-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="c1785-144">Microsoft에 보고 되는 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="c1785-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="c1785-145">자세한 내용은 [메일 흐름 규칙을 사용 하 여 사용자가 Microsoft에 보고 하는 항목 보기](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1785-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>

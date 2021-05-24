---
title: Outlook에서 가양성 및 가음성 보고
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 보고서 메시지 기능을 사용하여 가짓 긍정 및 Outlook 보고하는 방법을 배워야 합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f8c4fc327bfd467cdd1d0043c454e222e84125c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625116"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="03a83-103">Outlook에서 가양성 및 가음성 보고</span><span class="sxs-lookup"><span data-stu-id="03a83-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="03a83-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="03a83-104">**Applies to**</span></span>
- [<span data-ttu-id="03a83-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="03a83-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="03a83-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="03a83-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="03a83-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03a83-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="03a83-108">사서함이 있는 Microsoft 365 조직의 관리자인 Exchange Online 보안 및 준수 센터의 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="03a83-109">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="03a83-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="03a83-110">하이브리드 최신 인증을 사용하는 Microsoft 365 Exchange Online 사서함이 있는 Microsoft 365 조직에서는 가음성(차단되거나 정크 폴더로 전송된 양호한 전자 메일) 및 거짓 부정(받은 편지함으로 배달된 원치 않는 전자 메일 또는 피싱)을 EOP(Exchange Online Protection)에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03a83-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="03a83-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="03a83-112">최상의 사용자 제출 환경을 위해 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03a83-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="03a83-113">이 추가 기능의 작동 방식은 Outlook, iOS, Android 및 데스크톱 등 모든 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="03a83-114">사서함이 있는 조직의 관리자인 Exchange Online 보안 및 준수 센터의 & 포털을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03a83-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="03a83-115">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="03a83-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="03a83-116">메시지를 Microsoft로 직접 보내거나 지정한 사서함 또는 둘 다로 보내도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="03a83-117">자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="03a83-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="03a83-118">보고서 메시지 또는 피싱 보고 추가 기능을 보고하고 사용하도록 설정하는 방법에 대한 자세한 내용은 [Enable the Report Message or the Report Phishing add-ins을 참조하십시오.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="03a83-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="03a83-119">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="03a83-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="03a83-120">보고서 메시지 기능 사용</span><span class="sxs-lookup"><span data-stu-id="03a83-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="03a83-121">정크 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="03a83-121">Report junk and phishing messages</span></span>

<span data-ttu-id="03a83-122">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법을 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="03a83-123">선택한 **메시지의** 오른쪽 위에 있는 추가 작업 줄임표를  클릭하고 드롭다운 메뉴에서 메시지  보고를 클릭한 다음 정크 또는 피싱 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03a83-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03a83-124">![보고서 메시지 - 추가 작업](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="03a83-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03a83-125">![보고서 메시지 - 정크 및 피싱](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="03a83-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="03a83-126">선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="03a83-127">스팸으로 보고된 경우 정크 메일 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="03a83-128">피싱으로 보고된 경우 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-128">Deleted if it was reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="03a83-129">정크 메일이 아닌 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="03a83-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="03a83-130">선택한 **메시지의** 오른쪽 위 모서리에 있는 추가 작업 줄임표를 클릭하고 드롭다운 메뉴에서 메시지 보고를 클릭한 다음 정크 메일 아님 **을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="03a83-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03a83-131">![보고서 메시지 - 추가 작업](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="03a83-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03a83-132">![보고서 메시지 - 정크 메일 아님](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="03a83-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="03a83-133">선택한 메시지가 분석을 위해 Microsoft로 전송되어 받은 편지함 또는 기타 지정된 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="03a83-134">보고된 메시지 보기 및 검토</span><span class="sxs-lookup"><span data-stu-id="03a83-134">View and review reported messages</span></span>

<span data-ttu-id="03a83-135">사용자가 Microsoft에 보고하는 메시지를 검토할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="03a83-136">관리 제출 포털을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03a83-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="03a83-137">자세한 내용은 [Microsoft에 대한 사용자 제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="03a83-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="03a83-138">메일 흐름 규칙(전송 규칙)을 만들어 보고된 메시지의 복사본을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="03a83-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="03a83-139">자세한 내용은 메일 흐름 규칙을 사용하여 Microsoft에 보고하는 사용자 [확인을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="03a83-139">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>

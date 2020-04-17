---
title: 분석을 위해 Microsoft에 수동으로 메시지 전송
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '귀하와 사용자는 분석을 위해 Microsoft에 허위 네거티브 및 가양성 스팸 메시지를 제출할 수 있습니다. '
ms.openlocfilehash: 77807f710743d98dc2e1564f804b6a67add67def
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529052"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="5d030-103">분석을 위해 Microsoft에 수동으로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="5d030-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="5d030-104">Exchange Online 사서함을 사용 하는 Office 365 조직의 관리자는 Office 365 보안 & 준수 센터의 전송 포털을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="5d030-105">자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d030-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="5d030-106">조직의 사용자가 받은 편지함에서 정크 메시지 (스팸) 나 피싱 메시지를 받거나, 정크로 표시 되어 합법적인 전자 메일 메시지를 받지 못하는 경우에는 혼란을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="5d030-107">Microsoft는 스팸 필터를 보다 정확 하 게 미세 조정 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="5d030-108">귀하와 사용자는 가양성 (잘못 된 것으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 메일 허용), 분석을 위해 Microsoft에 피싱 메시지를 제출 하 여이 프로세스를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="5d030-109">수신 되는 전송 양이 많기 때문에 분석을 위해 모든 요청에 응답 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="5d030-110">Microsoft에 거짓 네거티브 전송</span><span class="sxs-lookup"><span data-stu-id="5d030-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="5d030-111">다음 절차를 사용 하 여 거짓 네거티브를 보고 하는 대신 Outlook 및 웹용 Outlook (이전의 Outlook Web App)에 있는 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="5d030-112">이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d030-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="5d030-113">스팸 또는 피싱으로 식별 되어야 하는 스팸 필터링을 통해 전달 된 메시지를 수신 하는 경우 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀에 적절 하 게 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="5d030-114">분석가는 메시지를 검토 하 고 해당 메시지가 분류 기준을 충족 하는 경우 서비스 전체 필터에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="5d030-115">다음 받는 사람 중 하 나와의 비어 있는 새 전자 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="5d030-116">**정크 메일**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="5d030-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="5d030-117">**피싱**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="5d030-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="5d030-118">정크 또는 피싱 메시지를 새 메시지에 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="5d030-119">이렇게 하면 정크 또는 피싱 메시지가 새 메시지에 첨부 파일로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="5d030-120">메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).</span><span class="sxs-lookup"><span data-stu-id="5d030-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="5d030-121">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="5d030-122">모든 메시지의 유형 (피싱 사기 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="5d030-123">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="5d030-124">첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="5d030-125">작업이 완료 되 면 **보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="5d030-126">관리자는 스팸으로 잘못 식별 되어는 특정 메시지를 차단 하는 여러 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="5d030-127">자세한 내용은 [Office 365에서 차단 된 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d030-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="5d030-128">Microsoft에 가양성 제출</span><span class="sxs-lookup"><span data-stu-id="5d030-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="5d030-129">다음 절차를 사용 하 여 가양성을 보고 하는 대신 Outlook 및 웹용 Outlook의 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="5d030-130">이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d030-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="5d030-131">메시지가 스팸으로 잘못 식별 된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="5d030-132">분석가는 메시지를 평가 하 고, 분석 결과에 따라, 서비스 전체 필터를 통해 메시지를 통과 하도록 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="5d030-133">받는 사람이 다음과 같은 비어 있는 `not_junk@office365.microsoft.com` 새 전자 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="5d030-134">잘못 식별 되어 메시지를 끌어서 새 메시지에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="5d030-135">이렇게 하면 잘못 식별 되어 메시지가 새 메시지에 첨부 파일로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="5d030-136">메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).</span><span class="sxs-lookup"><span data-stu-id="5d030-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="5d030-137">새 메시지에 여러 메시지를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="5d030-138">모든 메시지의 유형 (피싱 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="5d030-139">새 메시지의 본문은 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="5d030-140">첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="5d030-141">작업이 완료 되 면 **보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="5d030-142">관리자는 특정 메시지에서 스팸 필터링을 건너뛰는 여러 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="5d030-143">자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d030-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="5d030-144">Microsoft에 보고 되는 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="5d030-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="5d030-145">이 항목에서 설명 하는 방법을 사용 하 여 Microsoft에 보고 되는 전자 메일 메시지를 찾는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있으며, 이러한 보고 된 메시지의 복사본을 받도록 숨은 참조 받는 사람을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="5d030-146">EAC (Exchange 관리 센터) 및 PowerShell (Office 365 고객을 위한 Exchange Online PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다. 독립 실행형 EOP 고객을 위한 Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d030-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5d030-147">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="5d030-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5d030-148">이러한 절차를 수행 하려면 먼저 Exchange Online에서 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="5d030-149">특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="5d030-150">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d030-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="5d030-151">Exchange Online에서 EAC를 열려면 exchange [online의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d030-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="5d030-152">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d030-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5d030-153">Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d030-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5d030-154">Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d030-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="5d030-155">Exchange Online의 메일 흐름 규칙 (전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="5d030-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="5d030-156">메일 흐름 규칙 조건 및 예외 (조건자)가 Exchange Online에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="5d030-157">Exchange Online의 메일 흐름 규칙 동작</span><span class="sxs-lookup"><span data-stu-id="5d030-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="5d030-158">EAC를 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="5d030-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="5d030-159">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="5d030-160">![](../../media/ITPro-EAC-AddIcon.png) 추가 **아이콘 추가를 클릭 한** 다음 **새 규칙 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="5d030-161">**새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="5d030-162">**이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="5d030-163">예를 들어 숨은 참조 메시지는 Microsoft에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="5d030-164">**기타 옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-164">Click **More Options**.</span></span>

   - <span data-ttu-id="5d030-165">다음 **의** **경우에이 규칙 적용**: \> 표시 **되는 단어** **또는 구 지정** 대화 상자에 다음 값 중 하나를 입력 하 고 추가 아이콘](../../media/ITPro-EAC-AddIcon.png) **추가** ![를 클릭 한 다음 모든 값을 입력할 때까지 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="5d030-166">항목을 편집 하려면 선택 하 고 편집](../../media/ITPro-EAC-EditIcon.png)아이콘 **편집** ![을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="5d030-167">항목을 제거 하려면 선택 하 고 제거](../../media/ITPro-EAC-DeleteIcon.png)아이콘 **제거** ![를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="5d030-168">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="5d030-169">**다음을 수행**합니다. \> **숨은 참조 상자에** **받는 사람 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="5d030-170">대화 상자가 나타나면 추가 하려는 받는 사람을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="5d030-171">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="5d030-172">규칙을 감사 하 고 규칙을 테스트 하며 특정 기간 동안 규칙을 활성화 하 고 기타 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="5d030-173">규칙을 적용 하기 전에 테스트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="5d030-174">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="5d030-175">PowerShell을 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="5d030-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="5d030-176">이 예에서는이 항목에 설명 된 방법을 사용 하 여 Microsoft에 보고 되는 전자 메일 메시지를 찾아서 사용자 laura@contoso.com 및 julia@contoso.com를 숨은 참조 받는 사람으로 추가 하는 숨은 참조 메시지 라는 이름의 새 메일 흐름 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="5d030-177">자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d030-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5d030-178">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="5d030-178">How do you know this worked?</span></span>

<span data-ttu-id="5d030-179">보고 된 메시지의 복사본을 수신 하도록 메일 흐름 규칙을 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="5d030-180">EAC에서 **메일 흐름** \> **규칙** \> 을 선택 하 고 편집 아이콘 **Edit** ![](../../media/ITPro-EAC-EditIcon.png)편집 \> 을 클릭 한 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="5d030-181">PowerShell에서 다음 명령을 실행 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="5d030-182">보고 전자 메일 주소 중 하나로 테스트 메시지를 보내 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d030-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>

---
title: iOS 및 Android용 Outlook에서 정크 메일 및 피싱 메일 보고
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 iOS 및 Android용 Outlook에서 정크 메일이 아닌 기본 제공 정크 및 피싱 전자 메일 보고 옵션에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d702ab1d97c07c3e38430a9a7beff5f14db7b60a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029283"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="fd1df-103">Exchange Online에서 iOS 및 Android용 Outlook에서 정크 메일 및 피싱 메일 보고</span><span class="sxs-lookup"><span data-stu-id="fd1df-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fd1df-104">하이브리드 최신 인증을 사용하는 Microsoft 365 조직 또는 하이브리드 [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)최신 인증을 사용하는 Microsoft 365 조직에서는 iOS 및 Android용 Outlook의 기본 제공 보고 옵션을 사용하여 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 EOP(Exchange Online Protection)에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fd1df-105">시작하기 전에 알아야 할 것</span><span class="sxs-lookup"><span data-stu-id="fd1df-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="fd1df-106">Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터에서 제출 포털을 & 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="fd1df-107">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 [Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="fd1df-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="fd1df-108">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="fd1df-109">자세한 내용은 사용자 제출 정책을 [참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="fd1df-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="fd1df-110">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="fd1df-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd1df-111">사용자 제출 정책에서 Outlook에 대해 정크 메일 보고를 사용하지 않도록 설정하면 정크 또는 피싱 메시지가 정크 폴더로 이동하고 관리자 또는 Microsoft에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="fd1df-112">iOS 및 Android용 Outlook에서 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="fd1df-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="fd1df-113">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더의 경우 다음 단계를 사용하여 iOS 및 Android에 대한 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="fd1df-114">하나 이상의 메시지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-114">Select one or more messages.</span></span>
2. <span data-ttu-id="fd1df-115">오른쪽 위 모서리에서 세 개의 세로 점을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="fd1df-116">작업 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-116">The action menu opens.</span></span>

   ![작업 메뉴에서 정크 메일 또는 피싱 메일 보고](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="fd1df-118">정크 **보고를** 탭한 다음 정크 또는 피싱을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="fd1df-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![정크 메일 또는 피싱 메일 보고](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="fd1df-120">나타나는 대화 상자에서 보고서 또는  감사 **없음을 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fd1df-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="fd1df-121">아니요를 선택하면 정크 메일  폴더로 정크 메일을 입력하면 피싱 메시지를  지우기 폴더로 이동합니다. </span><span class="sxs-lookup"><span data-stu-id="fd1df-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="fd1df-122">보고서를 **선택하여** 메시지 복사본도 Microsoft에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![정크 메일 또는 피싱 전자 메일 보고 옵션 보고](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="fd1df-124">마음이 바뀌면 나타나는 알림 **메시지에서** 취소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="fd1df-125">메시지가 받은 편지함 폴더에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="fd1df-126">iOS 및 Android용 Outlook의 정크 폴더에서 스팸이 아닌 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="fd1df-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="fd1df-127">정크 폴더에서 다음 단계를 사용하여 스팸 가긍정을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="fd1df-128">하나 이상의 메시지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-128">Select one or more messages.</span></span>
2. <span data-ttu-id="fd1df-129">오른쪽 위 모서리에서 세 개의 세로 점을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="fd1df-130">작업 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-130">The action menu opens.</span></span>

   ![작업 메뉴에서 정크 메일 아님 보고](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="fd1df-132">정크 **아님을 탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd1df-132">Tap **Not junk**.</span></span>

<span data-ttu-id="fd1df-133">알림 메시지는 전자 메일이 받은 편지함으로 이동된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="fd1df-134">마음이 바뀌면 알림 **메시지에서** 취소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="fd1df-135">전자 메일은 정크 폴더에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1df-135">The email remains in the Junk folder.</span></span>

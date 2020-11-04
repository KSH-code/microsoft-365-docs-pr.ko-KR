---
title: IOS 및 Android 용 Outlook에서 정크 및 피싱 전자 메일 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 iOS 및 Android 용 Outlook에서 기본적으로 제공 되는 정크 메일, 정크 메일이 아닌 경우 및 피싱 메일로 보고 옵션에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 1c842ac5349f9c2804c637fa4c5598b06e8f489f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877294"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="44a2e-103">Exchange Online에서 iOS 및 Android 용 Outlook에서 정크 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="44a2e-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="44a2e-104">Exchange Online 또는 온-프레미스 사서함의 사서함을 포함 하는 Microsoft 365 조직에서 [하이브리드 최신 인증](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)을 사용 하는 경우 Outlook에서 IOS 및 Android 용 기본 제공 보고 옵션을 사용 하 여 가양성 (스팸으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 전자 메일 허용), EOP (Exchange Online Protection)로의 피싱 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44a2e-105">시작 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="44a2e-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="44a2e-106">Exchange Online 사서함을 사용 하는 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="44a2e-107">자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44a2e-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="44a2e-108">보고 된 메시지가 사용자가 지정한 사서함으로 복사 되거나 리디렉션되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="44a2e-109">자세한 내용은 [사용자 전송 정책을](user-submission.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44a2e-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="44a2e-110">Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="44a2e-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="44a2e-111">사용자 전송 정책에서 정크 메일 보고 기능을 Outlook에서 사용 하지 않도록 설정한 경우 정크 또는 피싱 메시지가 정크 폴더로 이동 되 고 관리자 또는 Microsoft에 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="44a2e-112">IOS 및 Android 용 Outlook에서 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="44a2e-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="44a2e-113">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더의 메시지에 대해 iOS 및 Android의 스팸 및 피싱 메시지를 보고 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="44a2e-114">하나 이상의 메시지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-114">Select one or more messages.</span></span>
2. <span data-ttu-id="44a2e-115">오른쪽 위 모서리에 있는 3 개의 세로 점을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="44a2e-116">동작 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-116">The action menu opens.</span></span>

   ![작업 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="44a2e-118">**정크 메일 보고** 를 누른 다음 **정크** 또는 **피싱** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![정크 또는 피싱 전자 메일 보고](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="44a2e-120">대화 상자가 나타나면 **보고서** 를 선택 하거나 **아니요/아니요** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="44a2e-121">**아니요 아니요** 를 선택 하면 **정크** 메일 폴더로 메시지가 이동 하는 경우 **피싱** 메일로 보낸 메시지는 지운 편지함 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-121">On selecting **No Thanks** , if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="44a2e-122">**보고서** 를 선택 하 여 메시지의 복사본을 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![정크 또는 피싱 전자 메일 보고 옵션 보고](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="44a2e-124">생각이 변경 되 면 표시 되는 toast 알림에서 **실행 취소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="44a2e-125">메시지가 받은 편지함 폴더에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="44a2e-126">IOS 및 Android 용 Outlook의 정크 폴더에서 스팸이 아닌 메시지 신고</span><span class="sxs-lookup"><span data-stu-id="44a2e-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="44a2e-127">정크 폴더에서 다음 단계를 사용 하 여 스팸이 가양성을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="44a2e-128">하나 이상의 메시지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-128">Select one or more messages.</span></span>
2. <span data-ttu-id="44a2e-129">오른쪽 위 모서리에 있는 3 개의 세로 점을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="44a2e-130">동작 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-130">The action menu opens.</span></span>

   ![작업 메뉴에서 정크 메일 아님으로 보고](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="44a2e-132">**정크 메일 아님으로** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-132">Tap **Not junk**.</span></span>

<span data-ttu-id="44a2e-133">전자 메일이 받은 편지 함으로 이동 되었음을 알리는 알림 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="44a2e-134">생각이 변경 되 면 toast 알림에서 **실행 취소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="44a2e-135">전자 메일이 정크 폴더에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44a2e-135">The email remains in the Junk folder.</span></span>

---
title: iOS 및 Android용 Outlook에서 정크 및 피싱 전자 메일 보고
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
description: 관리자는 iOS 및 Android용 Outlook에서 정크 메일이 아닌 기본 제공 정크 및 피싱 전자 메일 보고 옵션에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509329"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="c118d-103">Exchange Online에서 iOS 및 Android용 Outlook에서 정크 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="c118d-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c118d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="c118d-104">**Applies to**</span></span>
- [<span data-ttu-id="c118d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c118d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c118d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="c118d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c118d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c118d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c118d-108">Exchange Online 또는 하이브리드 최신 인증을 사용하는 사서함이 있는 Microsoft [](../../enterprise/hybrid-modern-auth-overview.md)365 조직에서는 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 EOP(Exchange Online Protection)에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c118d-109">시작하기 전에 알아야 할 것</span><span class="sxs-lookup"><span data-stu-id="c118d-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="c118d-110">최상의 사용자 제출 환경을 위해 보고서 메시지 및 피싱 보고 추가 기능을 사용하는 것이 좋습니다. 자세한 [내용은 보고서 메시지](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) 추가 기능 사용 및 [피싱](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) 보고서 추가 기능 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c118d-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="c118d-111">Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터에서 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c118d-112">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c118d-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="c118d-113">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c118d-114">자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c118d-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c118d-115">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c118d-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c118d-116">사용자 제출 정책에서 Outlook에 대해 정크 메일 보고를 사용하지 않도록 설정하면 정크 또는 피싱 메시지가 정크 폴더로 이동하고 관리자 또는 Microsoft에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c118d-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

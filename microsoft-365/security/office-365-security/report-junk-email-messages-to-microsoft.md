---
title: Microsoft에 스팸, 스팸 아님 및 피싱 메시지 보고
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Microsoft Office Outlook용 Microsoft 정크 메일 보고 추가 기능은 정크 메일 메시지를 보고하는 다양한 방법을 제공합니다.
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033665"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="ee56c-103">Microsoft에 메시지 및 파일 보고</span><span class="sxs-lookup"><span data-stu-id="ee56c-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="ee56c-104">Office 365의 사용자 및 관리자 Exchange online의 사서함이 있는 조직 또는 Exchange Online 사서함이 없는 EOP (독립 실행형 Exchange Online Protection) 조직에서 전자 메일 메시지를 제출할 수 있는 여러 가지 방법을 통해 메시지를 보고 하 고 파일을 Microsoft에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="ee56c-105">**방법**</span><span class="sxs-lookup"><span data-stu-id="ee56c-105">**Method**</span></span>|<span data-ttu-id="ee56c-106">**설명**</span><span class="sxs-lookup"><span data-stu-id="ee56c-106">**Description**</span></span>|
|[<span data-ttu-id="ee56c-107">관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, Url 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="ee56c-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="ee56c-108">이는 Exchange Online 사서함을 사용 하는 조직의 관리자에 게 권장 되는 보고 방법으로, 독립 실행형 EOP에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="ee56c-109">Office 365에서 보고서 메시지 추가 기능을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ee56c-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="ee56c-110">Outlook, Mac 용 Outlook 및 웹용 Outlook에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="ee56c-111">이 추가 기능을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="ee56c-112">라이선스에 따라 보고 된 메시지는 [사용자가 보고 한 메시지 보고서](view-email-security-reports.md#user-reported-messages-report) 및 [위협 탐색기](threat-explorer-views.md#email--submissions)의 [자동 조사 및 응답 (AIR) 결과](air-view-investigation-results.md)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="ee56c-113">Office 365에서 Microsoft Outlook 용 정크 메일 보고 추가 기능 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="ee56c-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="ee56c-114">Outlook 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="ee56c-115">Office 365에서 웹용 Outlook에 정크 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="ee56c-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="ee56c-116">Exchange Online 사서함이 있는 조직에 대해 웹용 Outlook에서 기본 제공 되는 기능 (독립 실행형 EOP에서 사용할 수 없음)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="ee56c-117">분석을 위해 맬웨어 및 비 맬웨어를 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="ee56c-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="ee56c-118">Microsoft 보안 인텔리전스 사이트를 사용 하 여 첨부 파일 및 기타 파일을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="ee56c-119">스팸 또는 피싱 메시지가 배달 되지 않고 격리 된 경우 사용자는 Office 365 보안 & 준수 센터의 격리 포털에서 Microsoft로 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee56c-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ee56c-120">자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee56c-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>
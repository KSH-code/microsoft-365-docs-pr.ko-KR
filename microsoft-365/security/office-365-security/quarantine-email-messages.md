---
title: Office 365 전자 메일 메시지 격리
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: 스팸, 대량, 피싱 메일 및 맬웨어로 필터링 된 받는 전자 메일 메시지를 나중에 검토할 수 있도록 Office 365에서 받는 전자 메일 메시지에 대 한 격리를 설정할 수 있습니다.
ms.openlocfilehash: f7669f69abb711d71362057f2019b0dd7e30443b
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021854"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="91fa4-103">Office 365 전자 메일 메시지 격리</span><span class="sxs-lookup"><span data-stu-id="91fa4-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="91fa4-104">전자 메일 365 메시지에 대해 격리를 설정 하 여 스팸, 대량 메일, 피싱 메일, 맬웨어를 포함 하는 메일 및 지정 된 메일 흐름 규칙 (trasport 규칙이 라고도 함)과 일치 하는 메일을 나중에 유지할 수 있습니다. 검토.</span><span class="sxs-lookup"><span data-stu-id="91fa4-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="91fa4-105">기본적으로 피싱, 맬웨어 및 메일 흐름 규칙에 따라 필터링 된 메시지는 격리로 전송 되 고, 스팸 및 대량 메일으로 필터링 된 메시지는 받는 사람의 정크 메일 폴더로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="91fa4-106">관리자는 스팸 필터 정책 (콘텐츠 필터 정책이 라고도 함)을 설정 하 여 스팸 및 대량 메일 메시지를 격리에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="91fa4-107">자세한 내용은 [스팸 필터 정책 구성을](configure-your-spam-filter-policies.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91fa4-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="91fa4-108">사용자와 관리자가 격리 된 메시지를 사용 하 여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="91fa4-109">사용자는 격리에서 필터링 된 메시지를 사용 하 여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="91fa4-110">관리자는 모든 사용자에 대해 격리 된 메시지를 검색 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="91fa4-111">높은 신뢰도 피싱 메일 흐름 규칙 작업에 의해 격리 된 메시지 및 메시지는 관리자 격리 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="91fa4-112">사용자는 자신의 피싱, 스팸 및 대량 메일 메시지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa4-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="91fa4-113">격리 된 메시지 작업에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="91fa4-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="91fa4-114">관리자로 격리 된 메시지 관리</span><span class="sxs-lookup"><span data-stu-id="91fa4-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="91fa4-115">사용자로 격리된 메시지 찾기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="91fa4-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="91fa4-116">사용자 스팸 알림을 사용 하 여 스팸 격리 된 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="91fa4-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="91fa4-117">격리 FAQ</span><span class="sxs-lookup"><span data-stu-id="91fa4-117">Quarantine FAQ</span></span>](quarantine-faq.md)

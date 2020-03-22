---
title: Office 365의 격리
f1.keywords:
- NOCSH
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
description: Office 365에서 격리를 통해 위험할 수도 있고 원치 않는 메시지를 저장할 수 있습니다. 관리자 및 최종 사용자가 격리에 액세스할 수 있습니다.
ms.openlocfilehash: 29f9fcbed83e9019118bb8b37c19cad1199c4c45
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895302"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="33f79-104">Office 365의 격리</span><span class="sxs-lookup"><span data-stu-id="33f79-104">Quarantine in Office 365</span></span>

<span data-ttu-id="33f79-105">Exchange online 사서함이 없는 Office 365 고객이 나 독립 실행형 EOP (Exchange Online Protection) 고객의 경우에는 격리를 사용 하 여 위험할 수도 있고 원치 않는 메시지를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="33f79-106">맬웨어를 포함 하 *는 첨부 파일이 있는 경우* 맬웨어 방지 정책은 메시지를 자동으로 격리 합니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="33f79-107">자세한 내용은 [Office 365에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33f79-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="33f79-108">기본적으로 스팸 방지 정책은 피싱 메시지를 격리 하 고 사용자의 정크 메일 폴더에 스팸 및 대량 전자 메일 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="33f79-109">그러나 스팸 방지 정책을 만들고 사용자 지정 하 여 스팸을 격리 하 고 대량 전자 메일 메시지를 격리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="33f79-110">자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33f79-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="33f79-111">사용자와 관리자가 격리 된 메시지를 사용 하 여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="33f79-112">관리자는 모든 사용자에 대해 격리 된 모든 유형의 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="33f79-113">관리자만이 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 결과로 격리 된 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="33f79-114">자세한 내용은 [Office 365에서 격리 된 메시지 및 파일 관리로 관리자](manage-quarantined-messages-and-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33f79-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="33f79-115">사용자는 메시지가 스팸으로, 대량 전자 메일 또는 (4 월, 2020) 피싱 메일로 격리 된 경우 받는 사람 인 격리 된 메시지를 사용 하 여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="33f79-116">자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33f79-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="33f79-117">사용자가 격리 된 자체 피싱 메시지를 관리 하지 못하도록 하기 위해 관리자는 스팸 방지 정책에서 **피싱 전자 메일** 필터링 결과에 대해 다른 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="33f79-118">자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33f79-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="33f79-119">관리자 및 사용자는 차단 되는 Microsoft에 가양성을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33f79-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="33f79-120">격리에 대 한 자세한 내용은 [격리 FAQ](quarantine-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33f79-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

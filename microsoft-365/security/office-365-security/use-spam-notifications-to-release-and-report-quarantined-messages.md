---
title: Office 36의 최종 사용자 스팸 알림
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 관리자가 스팸 방지 정책에서 최종 사용자 스팸 알림을 사용 하도록 설정 하면 메시지 받는 사람은 격리 된 메시지에 대 한 정기적인 알림을 받게 됩니다.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895062"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="6f5ae-103">Office 365의 최종 사용자 스팸 알림</span><span class="sxs-lookup"><span data-stu-id="6f5ae-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="6f5ae-104">격리는 Exchange Online 사서함이 있는 Office 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="6f5ae-105">자세한 내용은 [Office 365의 격리](quarantine-email-messages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="6f5ae-106">기본적으로 스팸 방지 정책에서는 최종 사용자 스팸 알림이 사용 되지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="6f5ae-107">관리자가 [최종 사용자 스팸 알림을 사용 하도록 설정](configure-your-spam-filter-policies.md)하면 메시지를 받는 사람에 게 스팸으로, 대량 전자 메일로, 또는 (4 월, 2020) 피싱 메일로 격리 된 메시지에 대 한 주기적인 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="6f5ae-108">2019 년 10 월에 격리 된 메시지를 최종 사용자 스팸 알림에서 직접 해제 하는 기능이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="6f5ae-109">대신 사용자가 Office 365 보안 & 준수 센터에서 직접 또는 알림에서 **검토** 를 클릭 하 여 격리 된 메시지를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="6f5ae-110">자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="6f5ae-111">높은 신뢰도의 피싱, 맬웨어 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)으로 격리 된 메시지는 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="6f5ae-112">자세한 내용은 [Office 365에서 격리 된 메시지 및 파일 관리로 관리자](manage-quarantined-messages-and-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-112">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="6f5ae-113">최종 사용자 스팸 알림에는 격리 된 각 메시지에 대 한 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="6f5ae-114">**보낸 사람**: 격리 된 메시지의 보내기 이름과 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="6f5ae-115">**제목**: 격리 된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="6f5ae-116">**Date**: 메시지가 격리 된 날짜와 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="6f5ae-117">**보낸 사람 차단**:이 링크를 클릭 하 여 수신 거부 목록에 보낸 사람을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="6f5ae-118">**검토**: 보안 & 준수 센터의 격리를 클릭 하 여 격리 된 메시지를 해제, 삭제 또는 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5ae-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)

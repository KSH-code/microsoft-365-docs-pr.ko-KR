---
title: Microsoft 365의 최종 사용자 스팸 알림
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)에서 격리 된 메시지에 대 한 최종 사용자 스팸 알림에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600300"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="2b15c-103">사용자 스팸 알림을 사용 하 여 격리 된 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="2b15c-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2b15c-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="2b15c-105">자세한 내용은 [EOP에서 격리 된 메시지](quarantine-email-messages.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b15c-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="2b15c-106">기본적으로 스팸 방지 정책에서는 최종 사용자 스팸 알림이 사용 되지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="2b15c-107">관리자가 [최종 사용자 스팸 알림을 사용](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)하도록 설정 하면 받는 사람 (automapping을 사용 하는 공유 사서함 포함)은 스팸으로, 대량 전자 메일로, 또는 (4 월 2020) 피싱 메일로 격리 된 메시지에 대 한 주기적인 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="2b15c-108">공유 사서함의 경우에는 공유 사서함에 대 한 FullAccess 권한이 부여 된 사용자만 최종 사용자 스팸 알림을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="2b15c-109">자세한 내용은 [EAC를 사용 하 여 공유 사서함 위임 편집](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b15c-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="2b15c-110">최종 사용자 스팸 알림은 그룹에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="2b15c-111">높은 신뢰도의 피싱, 맬웨어 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)으로 격리 된 메시지는 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="2b15c-112">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b15c-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="2b15c-113">최종 사용자 스팸 알림에는 격리 된 각 메시지에 대 한 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="2b15c-114">**보낸 사람**: 격리 된 메시지의 보내기 이름과 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="2b15c-115">**제목**: 격리 된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="2b15c-116">**Date**: 메시지가 격리 된 날짜와 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="2b15c-117">**보낸 사람 차단**:이 링크를 클릭 하 여 수신 거부 목록에 보낸 사람을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="2b15c-118">자세한 내용은 [메일 보낸 사람 차단을](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b15c-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="2b15c-119">**Release**: 스팸 (피싱 아님) 메시지의 경우 보안 & 준수 센터를 격리 하지 않고 여기에서 메시지를 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="2b15c-120">**검토**: 보안 & 준수 센터에서 격리로 이동 하려면이 링크를 클릭 합니다 (메시지가 격리 된 이유에 따라 다름). 격리 된 메시지를 확인, 해제, 삭제 또는 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="2b15c-121">자세한 내용은 [EOP의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b15c-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="2b15c-123">차단 된 보낸 사람은 여전히 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-123">A blocked sender can still send you mail.</span></span> <span data-ttu-id="2b15c-124">이 보낸 사람이 사서함에 게 보내는 모든 메시지는 즉시 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-124">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="2b15c-125">다음에이 사람이 보낸 메시지는 정크 메일 폴더 또는 최종 사용자 격리로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-125">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="2b15c-126">이러한 메시지를 격리 하는 대신 도착 시 삭제 하려면 [메일 흐름 규칙](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (전송 규칙이 라고도 함)을 사용 하 여 도착 시 메시지를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b15c-126">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>

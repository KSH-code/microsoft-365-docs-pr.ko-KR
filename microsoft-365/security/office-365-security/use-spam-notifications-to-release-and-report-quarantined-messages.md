---
title: 2013의 최종 사용자 스팸 Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 관리자는 EOP(2016년 8월 2일)의 최종 사용자 스팸 알림에 대해 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71f2a33ad83f94895c396f92c18753bfca7f2905
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933170"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="47322-103">사용자 스팸 알림을 사용하여 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="47322-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="47322-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="47322-104">**Applies to**</span></span>
- [<span data-ttu-id="47322-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="47322-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="47322-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="47322-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="47322-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47322-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="47322-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="47322-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="47322-109">자세한 내용은 [EOP에서 Quarantined messages를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="47322-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="47322-110">기본적으로 최종 사용자 스팸 알림은 스팸 방지 정책에서 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="47322-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="47322-111">관리자가 최종 [](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)사용자 스팸 알림을 사용하도록 설정하면 받는 사람(자동 응용 프로그램을 사용하는 공유 사서함 포함)은 스팸, 대량 전자 메일 또는 (2020년 4월부터) 피싱으로 스팸으로 차단된 메시지에 대한 주기적인 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47322-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="47322-112">공유 사서함의 경우 최종 사용자 스팸 알림은 공유 사서함에 대한 FullAccess 권한이 부여된 사용자에 한해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="47322-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="47322-113">자세한 내용은 EAC를 사용하여 공유 사서함 위임 [편집을 참조하세요.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="47322-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="47322-114">최종 사용자 스팸 알림은 그룹에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47322-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="47322-115">높은 신뢰도 피싱, 맬웨어 또는 메일 흐름 규칙(전송 규칙)에 의해서만 차단된 메시지는 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47322-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="47322-116">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47322-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="47322-117">최종 사용자 스팸 알림에는 각 고지된 메시지에 대한 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47322-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="47322-118">**보낸 사람:** 고지된 메시지의 보낸 사람 이름 및 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="47322-118">**Sender**: The send name and email address of the quarantined message.</span></span>
- <span data-ttu-id="47322-119">**제목:** 고지된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="47322-119">**Subject**: The subject line text of the quarantined message.</span></span>
- <span data-ttu-id="47322-120">**날짜:** 메시지가 중단된 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="47322-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>
- <span data-ttu-id="47322-121">**보낸 사람 차단:** 이 링크를 클릭하여 사서함의 수신 차단된 보낸 사람 목록에 보낸 사람이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="47322-121">**Block Sender**: Click this link to add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="47322-122">자세한 내용은 [메일 보낸 사람 차단](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47322-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>
- <span data-ttu-id="47322-123">**릴리스:** 스팸(피싱이 아닌) 메시지의 경우 2016년 10월 2일 릴리스된 Defender 포털을 Microsoft 365 있습니다. </span><span class="sxs-lookup"><span data-stu-id="47322-123">**Release**: For spam (not phishing) messages, you can release the message here without going to **Quarantine** the Microsoft 365 Defender portal.</span></span>
- <span data-ttu-id="47322-124">**검토:** 이 링크를 클릭하여  Microsoft 365 Defender 포털에서 메시지를 보거나, 릴리스하고, 삭제하거나, 보고할 수 있는 Microsoft 365 Defender 포털에서 이 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47322-124">**Review**: Click this link to go to **Quarantine** in the Microsoft 365 Defender portal, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="47322-125">자세한 내용은 EOP에서 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="47322-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="47322-127">수신이 차단된 보낸 사람이 여전히 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47322-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="47322-128">이 보낸 사람이 사서함으로 보내는 모든 메시지는 즉시 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="47322-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="47322-129">이 보낸 사람이 보낸 향후 메시지는 정크 메일 폴더 또는 최종 사용자 검지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="47322-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="47322-130">도착 시 이러한 메시지를 두지 않고 삭제하려면 메일 흐름 규칙(전송 규칙)을 사용하여 도착 시 메시지를 삭제합니다. [](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="47322-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>

---
title: Microsoft 365의 최종 사용자 스팸 알림
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
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 격리 된 메시지에 대 한 최종 사용자 스팸 알림에 대해 설명 합니다.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035001"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="810e6-103">사용자 스팸 알림을 사용 하 여 격리 된 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="810e6-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="810e6-104">격리는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="810e6-105">자세한 내용은 [Office 365의 격리](quarantine-email-messages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="810e6-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="810e6-106">기본적으로 스팸 방지 정책에서는 최종 사용자 스팸 알림이 사용 되지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="810e6-107">관리자가 [최종 사용자 스팸 알림을 사용 하도록 설정](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)하면 받는 사람에 게 스팸으로, 대량 전자 메일로, 또는 (4 월, 2020) 피싱 메일로 격리 된 메시지에 대 한 주기적인 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="810e6-108">높은 신뢰도의 피싱, 맬웨어 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)으로 격리 된 메시지는 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="810e6-109">자세한 내용은 [Office 365에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="810e6-109">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="810e6-110">최종 사용자 스팸 알림에는 격리 된 각 메시지에 대 한 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="810e6-111">**보낸 사람**: 격리 된 메시지의 보내기 이름과 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="810e6-112">**제목**: 격리 된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="810e6-113">**Date**: 메시지가 격리 된 날짜와 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="810e6-114">**보낸 사람 차단**:이 링크를 클릭 하 여 수신 거부 목록에 보낸 사람을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="810e6-115">자세한 내용은 [Outlook에서 메일 보낸 사람 차단을](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="810e6-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="810e6-116">**Release**: 스팸 (피싱 아님) 메시지의 경우 보안 & 준수 센터를 격리 하지 않고 여기에서 메시지를 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="810e6-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="810e6-117">**검토**: 보안 & 준수 센터에서 격리로 이동 하려면이 링크를 클릭 합니다 (격리 된 메시지를 해제, 삭제 또는 보고할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="810e6-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="810e6-118">자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="810e6-118">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)

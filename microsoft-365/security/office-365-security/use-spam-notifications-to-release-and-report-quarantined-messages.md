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
description: 관리자는 EOP(Exchange Online Protection)에서 격리된 메시지에 대한 최종 사용자 스팸 알림을 통해 해당 알림을 학습할 수 있습니다.
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827364"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="a3da0-103">사용자 스팸 알림을 사용하여 격리된 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="a3da0-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="a3da0-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="a3da0-105">자세한 내용은 [EOP에서 격리된 메시지를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a3da0-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a3da0-106">기본적으로 최종 사용자 스팸 알림은 스팸 방지 정책에서 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="a3da0-107">관리자가 [최종 사용자 스팸 알림을 사용하도록](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)설정하면, automapping이 사용하도록 설정된 공유 사서함 포함)은 스팸, 대량 전자 메일 또는 (2020년 4월부터) 피싱으로 격리된 메시지에 대해 정기적으로 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="a3da0-108">공유 사서함의 경우 최종 사용자 스팸 알림은 공유 사서함에 대한 FullAccess 권한이 부여된 사용자에 한하여 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="a3da0-109">자세한 내용은 [EAC를 사용하여 공유 사서함 위임 편집을 참조하십시오.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="a3da0-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="a3da0-110">최종 사용자 스팸 알림은 그룹에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da0-111">신뢰도가 높은 피싱, 맬웨어 또는 메일 흐름 규칙(전송 규칙이라고도 함)에 의해 격리된 메시지는 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="a3da0-112">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3da0-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="a3da0-113">최종 사용자 스팸 알림에는 격리된 각 메시지에 대한 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="a3da0-114">**보낸**사람: 격리된 메시지의 보내는 이름 및 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="a3da0-115">**제목:** 격리된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="a3da0-116">**날짜:** 메시지가 격리된 날짜와 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="a3da0-117">**차단 -** 보낸 사람을 수신 거부 목록에 추가 하려면 이 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="a3da0-118">자세한 내용은 메일 보낸 [사람 차단 항목을 참조하세요.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="a3da0-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="a3da0-119">**릴리스:** 스팸(피싱 아지 않은) 메시지의 경우 보안 및 준수 센터로 이동하지 않고도 여기에 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="a3da0-120">**검토:** 이 링크를 클릭하여 보안 & 준수 센터에서 격리로 이동합니다. 여기서 메시지가 격리된 이유에 따라(격리된 메시지를 보고, 릴리스, 삭제 또는 보고) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3da0-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="a3da0-121">자세한 내용은 [EOP에서 사용자로 격리된 메시지 찾기 및 릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="a3da0-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)

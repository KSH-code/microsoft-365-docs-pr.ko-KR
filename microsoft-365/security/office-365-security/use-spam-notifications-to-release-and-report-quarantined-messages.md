---
title: Office 365에서 사용자 스팸 알림을 사용하여 격리된 메시지 릴리스 및 보고
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
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
description: 관리자가 사용자에 게 알림을 사용 하도록 설정 하는 경우 사서함에 전송 된 메시지를 스팸, 대량 또는 피싱 메시지로 식별 하는 알림 메시지가 표시 됩니다. 알림을 받은 후에는 메시지를 해제 하거나 보고할 수 있습니다.
ms.openlocfilehash: 4cf592f0aec948c3c8f6383cf288fb32ac644cd6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971366"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="f6567-104">Office 365에서 사용자 스팸 알림을 사용하여 격리된 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="f6567-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="f6567-105">관리자가 사용자에 대 한 스팸 알림을 사용 하도록 설정 하는 경우 사서함으로 주소가 지정 되어 스팸으로 식별 되 고 대신 격리 된 메시지를 나열 하는 알림 메시지가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="f6567-106">관리자가이 기능을 사용 하도록 설정 하려는 경우에는 [기본 스팸 방지 정책을 수정](configure-your-spam-filter-policies.md)하는 경우 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="f6567-107">수신 되는 메시지에는 스팸 격리 된 메시지의 수와 목록에 있는 마지막 메시지의 날짜와 시간 (utc (Universal 협정 세계시))이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="f6567-108">이 목록에는 각 메시지에 대 한 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="f6567-109">**보낸 사람** 격리 된 메시지의 보내기 이름 및 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="f6567-110">**제목** 격리된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="f6567-111">**날짜** 메시지가 격리된 날짜와 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="f6567-112">격리 된 메시지를 사용 하 여 수행할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="f6567-113">Office 365에서 수신 거부 목록에 보낸 사람을 추가 하려는 경우 **보낸 사람을 차단** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="f6567-114">Preview 또는 Release와 같은 다른 작업을 수행 하려는 경우 보안 및 준수 센터 내의 격리 포털로 이동 하는 방법을 **검토** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="f6567-115">다음에 대해 숙지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-115">Be aware of the following:</span></span>

- <span data-ttu-id="f6567-116">메일 흐름 규칙과 일치 하기 때문에 격리 된 메시지는 사용자 격리 된 메시지에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-116">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="f6567-117">스팸 격리된 메시지만 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-117">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="f6567-118">메시지를 릴리스하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6567-118">You can only release a message and report it as a false positive (not junk) once.</span></span>

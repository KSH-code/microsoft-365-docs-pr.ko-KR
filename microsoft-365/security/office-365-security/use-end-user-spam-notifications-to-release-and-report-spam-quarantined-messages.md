---
title: 최종 사용자 스팸 알림을 사용하여 스팸으로 격리된 메시지 릴리스 및 보고
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: '격리 된 전자 메일에 대 한 관리자 로부터 최종 사용자 스팸 알림 메시지를 보는 사용자는 메시지에 대해 이러한 작업을 수행할 수 있습니다. '
ms.openlocfilehash: 5c113e186a0469714829592437698ddb1185a141
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971416"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="24b02-103">최종 사용자 스팸 알림을 사용하여 스팸으로 격리된 메시지 릴리스 및 보고</span><span class="sxs-lookup"><span data-stu-id="24b02-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="24b02-p101">관리자가 최종 사용자 스팸 알림을 사용하도록 설정하는 경우 사서함으로 전송되지 않고 스팸으로 식별되어 격리된 메시지 목록이 포함된 알림 메시지를 수신하게 됩니다. 이 메시지에는 스팸 격리된 여러 메시지가 나열되어 있으며, 이 목록에는 마지막 메시지의 날짜와 시간(UTC(Universal Coordinated Time))이 포함됩니다. 이 목록에서 각 메시지에 대한 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="24b02-107">**보낸 사람**: 격리 된 메시지의 보낸 사람 이름과 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-107">**Sender**: The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="24b02-108">**제목**: 격리 된 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-108">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="24b02-109">**Date**: 메시지가 격리 된 날짜와 시간 (UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-109">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="24b02-110">**크기**: 격리 된 메시지의 크기 (kb)입니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-110">**Size**: The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="24b02-111">각 메시지에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-111">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="24b02-112">**받은 편지함에 릴리스**:이 링크를 클릭 하면 메시지를 볼 수 있는 받은 편지 함으로 메시지가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-112">**Release to Inbox**: Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="24b02-113">**정크 메일 아님으로 보고**:이 링크를 클릭 하면 분석을 위해 Microsoft에 메시지 복사본이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-113">**Report as Not Junk**: Clicking this link sends a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="24b02-114">스팸 팀은 메시지를 평가 및 분석하고 분석 결과에 따라 메시지 통과를 허용하도록 스팸 방지 필터 규칙을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-114">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="24b02-115">메일 흐름 규칙 (a) 일치로 인해 격리 된 메시지는 최종 사용자 스팸 격리 메시지에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-115">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="24b02-116">스팸 격리된 메시지만 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-116">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="24b02-117">메시지를 릴리스하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b02-117">You can only release a message and report it as a false positive (not junk) once.</span></span>

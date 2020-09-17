---
title: 자동 전달 메시지 인사이트
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에 있는 자동 전달 메시지 보고서에 대해 알아볼 수 있습니다.
ms.openlocfilehash: e9e3a0159671dd4ce62f4fa0b07b7162807fe0e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949859"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="f79d4-103">보안 & 준수 센터에 대 한 자동 전달 메시지 이해</span><span class="sxs-lookup"><span data-stu-id="f79d4-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="f79d4-104">[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **자동 전달 메시지** 이해 조직에서 외부 도메인의 받는 사람에 게 자동으로 전달 되는 메시지에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f79d4-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![보안 & 준수 센터에서 메시지 위젯 자동 전달](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="f79d4-106">자동 전달 메시지 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f79d4-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="f79d4-107">위젯의 메시지 수를 클릭 하면 자동 전달 메시지에 대 한 자세한 내용을 보여주는 플라이 아웃 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f79d4-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="f79d4-108">**전달 메서드를 사용 하 여 메시지 자동 전달**:</span><span class="sxs-lookup"><span data-stu-id="f79d4-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="f79d4-109">**메일 흐름 규칙에 따라**</span><span class="sxs-lookup"><span data-stu-id="f79d4-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="f79d4-110">**받은 편지함 규칙에 따라**</span><span class="sxs-lookup"><span data-stu-id="f79d4-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="f79d4-111">**SMTP 전달**</span><span class="sxs-lookup"><span data-stu-id="f79d4-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="f79d4-112">자세한 내용은 [전달 보고서](view-mail-flow-reports.md#forwarding-report) 에 대 한 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f79d4-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="f79d4-113">**도메인 및 사용자가 자동으로 메시지를 전달 하는**경우:</span><span class="sxs-lookup"><span data-stu-id="f79d4-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="f79d4-114">**다음에 전달 된 상위 5 개 도메인**</span><span class="sxs-lookup"><span data-stu-id="f79d4-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="f79d4-115">**새 도메인 (지난 주)**</span><span class="sxs-lookup"><span data-stu-id="f79d4-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="f79d4-116">**상위 5 개 사용자 전달**</span><span class="sxs-lookup"><span data-stu-id="f79d4-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="f79d4-117">**새 사용자 (지난 주)**</span><span class="sxs-lookup"><span data-stu-id="f79d4-117">**New users (last week)**</span></span>
  - <span data-ttu-id="f79d4-118">자세한 내용은 [전달 수정 보고서](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 에 대 한 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f79d4-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![보안 & 준수 센터의 자동 전달 메시지 보고서에 대 한 세부 정보 플라이 아웃](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="f79d4-120">인사이트</span><span class="sxs-lookup"><span data-stu-id="f79d4-120">Insights</span></span>

<span data-ttu-id="f79d4-121">보고서 데이터를 기반으로 두 개의 정보가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f79d4-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="f79d4-122">전자 메일을 전달 하는 새 사용자</span><span class="sxs-lookup"><span data-stu-id="f79d4-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="f79d4-123">전달 되는 새 도메인 전자 메일</span><span class="sxs-lookup"><span data-stu-id="f79d4-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="f79d4-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f79d4-124">See also</span></span>

<span data-ttu-id="f79d4-125">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f79d4-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

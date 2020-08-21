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
description: 관리자는 준수 센터의 메일 흐름 대시보드에서 자동 전달 메시지 보고서에 대해 & 수 있습니다.
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827030"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="58823-103">규정 준수 센터의 & 메시지 자동 전달 메시지 정보</span><span class="sxs-lookup"><span data-stu-id="58823-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="58823-104">보안 **& 준수 센터의** 메일 흐름 [Mail flow dashboard](mail-flow-insights-v2.md) 대시보드에서 자동으로 전달된 메시지 정보는 조직에서 외부 도메인에 있는 받는 사람에게 자동으로 전달되는 메시지에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="58823-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Security-Forwarded messages Widget in the Security & Center](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="58823-106">자동 전달 메시지 세부 정보</span><span class="sxs-lookup"><span data-stu-id="58823-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="58823-107">위에서 메시지 수를 클릭하면 자동으로 전달된 메시지에 대한 자세한 내용이 표시된 플라이아웃 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58823-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="58823-108">**전달 방법을 사용하여 자동 전달된 메시지:**</span><span class="sxs-lookup"><span data-stu-id="58823-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="58823-109">**메일 흐름 규칙에 의해**</span><span class="sxs-lookup"><span data-stu-id="58823-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="58823-110">**받은 편지함 규칙**</span><span class="sxs-lookup"><span data-stu-id="58823-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="58823-111">**SMTP 전달으로**</span><span class="sxs-lookup"><span data-stu-id="58823-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="58823-112">자세한 내용을 [보려면 전달 보고서의](view-mail-flow-reports.md#forwarding-report) 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="58823-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="58823-113">**도메인 및 사용자별 자동 전달 메시지:**</span><span class="sxs-lookup"><span data-stu-id="58823-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="58823-114">**전달되는 상위 5개 도메인**</span><span class="sxs-lookup"><span data-stu-id="58823-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="58823-115">**새 도메인(지난 주)**</span><span class="sxs-lookup"><span data-stu-id="58823-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="58823-116">**상위 5 전달 사용자**</span><span class="sxs-lookup"><span data-stu-id="58823-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="58823-117">**새 사용자(지난 주)**</span><span class="sxs-lookup"><span data-stu-id="58823-117">**New users (last week)**</span></span>
  - <span data-ttu-id="58823-118">자세한 [내용을 보려면 전달 수정 보고서의](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="58823-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![보안 및 준수 센터의 자동 전달 메시지 보고서에 대한 세부 & 플라이아웃](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="58823-120">인사이트</span><span class="sxs-lookup"><span data-stu-id="58823-120">Insights</span></span>

<span data-ttu-id="58823-121">보고서 데이터를 기반으로 다음과 같은 두 인사이트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58823-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="58823-122">새 사용자 전달 전자 메일</span><span class="sxs-lookup"><span data-stu-id="58823-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="58823-123">전달되는 새 도메인</span><span class="sxs-lookup"><span data-stu-id="58823-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="58823-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58823-124">See also</span></span>

<span data-ttu-id="58823-125">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="58823-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

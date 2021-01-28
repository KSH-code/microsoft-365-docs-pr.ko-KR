---
title: 자동 전달 메시지 인사이트
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 자동 전달된 메시지 & 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029945"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="8d6b1-103">보안 및 준수 센터의 & 전달된 메시지 정보</span><span class="sxs-lookup"><span data-stu-id="8d6b1-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8d6b1-104">Security  [&](https://protection.office.com) 준수 센터의 메일 [](mail-flow-insights-v2.md) 흐름 대시보드에서 자동 전달된 메시지 정보에는 조직에서 외부 도메인의 받는 사람에게 자동으로 전달되는 메시지에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6b1-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![보안 및 준수 센터의 & 메시지 위젯](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="8d6b1-106">자동 전달된 메시지 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8d6b1-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="8d6b1-107">위젯에서 메시지 수를 클릭하면 자동 전달된 메시지에 대한 자세한 정보를 표시하는 플라이아웃 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8d6b1-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="8d6b1-108">전달 방법을 사용하여 자동 **전달된 메시지:**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="8d6b1-109">**메일 흐름 규칙**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="8d6b1-110">**받은 편지함 규칙**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="8d6b1-111">**SMTP 전달:** 이 방법은 사서함에 대한 전자 메일 전달 구성에 설명된 바와 같이 관리자가 사서함에 대해 구성할 수 있는 자동 [전달을 나타냅니다.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="8d6b1-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="8d6b1-112">자세한 내용은 [전달 보고서에](view-mail-flow-reports.md#forwarding-report) 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6b1-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="8d6b1-113">**도메인 및 사용자에 의해 자동 전달된 메시지:**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="8d6b1-114">**상위 5개 도메인으로 전달**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="8d6b1-115">**새 도메인(지난 주)**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="8d6b1-116">**상위 5명 전달 사용자**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="8d6b1-117">**새 사용자(지난 주)**</span><span class="sxs-lookup"><span data-stu-id="8d6b1-117">**New users (last week)**</span></span>
  - <span data-ttu-id="8d6b1-118">자세한 내용은 전달 수정 [보고서에](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6b1-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![보안 및 준수 센터의 자동 전달된 메시지 보고서에 대한 & 플라이아웃](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="8d6b1-120">인사이트</span><span class="sxs-lookup"><span data-stu-id="8d6b1-120">Insights</span></span>

<span data-ttu-id="8d6b1-121">보고서 데이터를 기반으로 두 가지 인사이트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6b1-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="8d6b1-122">전자 메일을 전달하는 새 사용자</span><span class="sxs-lookup"><span data-stu-id="8d6b1-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="8d6b1-123">전자 메일로 전달되는 새 도메인</span><span class="sxs-lookup"><span data-stu-id="8d6b1-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="8d6b1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d6b1-124">See also</span></span>

<span data-ttu-id="8d6b1-125">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="8d6b1-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

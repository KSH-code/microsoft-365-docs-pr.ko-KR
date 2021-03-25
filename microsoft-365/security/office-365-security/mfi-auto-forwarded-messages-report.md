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
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206406"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="11ae1-103">보안 및 준수 센터의 & 전달된 메시지 정보</span><span class="sxs-lookup"><span data-stu-id="11ae1-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="11ae1-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="11ae1-104">**Applies to**</span></span>
- [<span data-ttu-id="11ae1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="11ae1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="11ae1-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="11ae1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="11ae1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11ae1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="11ae1-108">Security  & [Compliance Center의](https://protection.office.com) 메일 [](mail-flow-insights-v2.md) 흐름 대시보드에 있는 자동 전달 메시지 인사이트에는 조직에서 외부 도메인의 받는 사람에게 자동으로 전달되는 메시지에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ae1-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![보안 및 준수 센터의 자동 전달 & 위젯](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="11ae1-110">자동 전달된 메시지 세부 정보</span><span class="sxs-lookup"><span data-stu-id="11ae1-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="11ae1-111">위젯에서 메시지 수를 클릭하면 자동 전달된 메시지에 대한 자세한 정보를 표시하는 플라이아웃 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="11ae1-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="11ae1-112">**전달 방법을 사용하여 자동 전달된 메시지:**</span><span class="sxs-lookup"><span data-stu-id="11ae1-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="11ae1-113">**메일 흐름 규칙**</span><span class="sxs-lookup"><span data-stu-id="11ae1-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="11ae1-114">**받은 편지함 규칙**</span><span class="sxs-lookup"><span data-stu-id="11ae1-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="11ae1-115">**SMTP 전달:** 이 방법은 사서함에 대한 전자 메일 전달 구성에 설명된 바와 같이 관리자가 사서함에 대해 구성할 수 있는 자동 전달을 [나타냅니다.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="11ae1-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="11ae1-116">자세한 내용은 [전달 보고서에](view-mail-flow-reports.md#forwarding-report) 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="11ae1-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="11ae1-117">**도메인 및 사용자에 의해 자동 전달된 메시지:**</span><span class="sxs-lookup"><span data-stu-id="11ae1-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="11ae1-118">**상위 5개 도메인으로 전달**</span><span class="sxs-lookup"><span data-stu-id="11ae1-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="11ae1-119">**새 도메인(지난 주)**</span><span class="sxs-lookup"><span data-stu-id="11ae1-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="11ae1-120">**상위 5개 전달 사용자**</span><span class="sxs-lookup"><span data-stu-id="11ae1-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="11ae1-121">**새 사용자(지난 주)**</span><span class="sxs-lookup"><span data-stu-id="11ae1-121">**New users (last week)**</span></span>
  - <span data-ttu-id="11ae1-122">자세한 내용은 [전달](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 수정 내용 보고서에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="11ae1-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![보안 및 준수 센터의 자동 전달된 메시지 보고서에 대한 & 플라이아웃](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="11ae1-124">인사이트</span><span class="sxs-lookup"><span data-stu-id="11ae1-124">Insights</span></span>

<span data-ttu-id="11ae1-125">보고서 데이터를 기반으로 두 가지 인사이트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ae1-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="11ae1-126">전자 메일을 전달하는 새 사용자</span><span class="sxs-lookup"><span data-stu-id="11ae1-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="11ae1-127">전자 메일로 전달되는 새 도메인</span><span class="sxs-lookup"><span data-stu-id="11ae1-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="11ae1-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11ae1-128">See also</span></span>

<span data-ttu-id="11ae1-129">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="11ae1-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
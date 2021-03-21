---
title: 전자 메일 인사이트가 전달되는 새 도메인
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: '& 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 새 도메인이 전달되는 전자 메일 정보를 사용하여 사용자가 전달되지 않은 외부 도메인으로 메시지를 전달하는 경우를 조사하는 방법을 배울 수 있습니다.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929351"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="bdc08-103">보안 및 준수 센터에서 전달되는 새 & 정보</span><span class="sxs-lookup"><span data-stu-id="bdc08-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bdc08-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="bdc08-104">**Applies to**</span></span>
- [<span data-ttu-id="bdc08-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bdc08-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bdc08-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="bdc08-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bdc08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdc08-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bdc08-108">특정 도메인의 외부 받는 사람에게 전자 메일 메시지를 전달해야 하는 유효한 비즈니스 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc08-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="bdc08-109">그러나 조직의 사용자가 갑자기 조직의 어느 누구도 (새 도메인)에게 메시지를 전달한 적 없는 도메인에 메시지를 전달하기 시작하면 의심스러우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdc08-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="bdc08-110">이 조건은 사용자 계정이 손상된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc08-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="bdc08-111">계정이 손상된 것으로 의심되는 경우 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="bdc08-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="bdc08-112">Security **&** Compliance [Center에서](https://protection.office.com) 전달되는 새 도메인은 조직의 사용자가 메시지를 새 도메인으로 전달할 때 사용자에게 이를 통보합니다.</span><span class="sxs-lookup"><span data-stu-id="bdc08-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="bdc08-113">이 인사이트는 문제가 검색된 경우만 표시되고 전달 보고서 페이지에 [표시됩니다.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="bdc08-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![전자 메일 인사이트가 전달되는 새 도메인](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="bdc08-115">위젯을 클릭하면 전달 보고서에 대한 링크를 포함하여 전달된 메시지에 대한 자세한 정보를 찾을 수 있는 플라이아웃이 [나타납니다.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="bdc08-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![전자 메일 인사이트를 전달하는 새 도메인을 클릭한 후 나타나는 세부 정보 플라이아웃](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="bdc08-117">또한 ( 보고서 대시보드 또는 **)의** 상위 인사이트 및 추천 영역에 있는 모든 정보 보기를 클릭한 & 세부 정보 페이지로 이동될 **수도**  \>  <https://protection.office.com/insightdashboard> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc08-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="bdc08-118">외부 도메인으로 자동 메시지 전달을 방지하려면 일부 또는 모든 외부 도메인에 대해 원격 도메인을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bdc08-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="bdc08-119">자세한 내용은 [Exchange Online에서 원격 도메인 관리를 참조하세요.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="bdc08-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bdc08-120">관련 주제</span><span class="sxs-lookup"><span data-stu-id="bdc08-120">Related topics</span></span>

<span data-ttu-id="bdc08-121">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="bdc08-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
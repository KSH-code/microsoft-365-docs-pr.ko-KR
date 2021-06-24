---
title: Microsoft 365 Defender 포털의 메시지 추적
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Microsoft 365 Defender 포털의 메시지 추적 링크를 사용하여 메시지에 대해 어떻게 Microsoft 365 Defender 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108130"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2a836-103">Microsoft 365 Defender 포털의 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="2a836-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2a836-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="2a836-104">**Applies to**</span></span>
- [<span data-ttu-id="2a836-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2a836-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2a836-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="2a836-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2a836-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a836-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2a836-108">Microsoft 365 Defender 포털의 메시지 추적은 조직을 통과하는 전자 메일 메시지를 Exchange Online 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="2a836-109">서비스에서 메시지를 수신, 거부, 지연 또는 배달할지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="2a836-110">또한 최종 상태에 도달하기 전에 메시지에 대해 수행된 작업도 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="2a836-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="2a836-111">메시지 추적의 정보를 사용하여 메시지에 대해 진행된 문제에 대한 사용자 질문에 효율적으로 답변하고, 메일 흐름 문제를 해결하고, 정책 변경의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="2a836-112">Microsoft 365 Defender 포털의 메시지 추적은 Exchange 관리 센터의 메시지 추적을 통과하는 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="2a836-113">자세한 내용은 최신 관리 센터의 메시지 [Exchange 참조하세요.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="2a836-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2a836-114">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2a836-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2a836-115">메시지 추적을 사용하려면 조직 **관리,** 준수  관리 또는 지원 센터 역할  **Exchange Online** 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="2a836-116">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a836-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="2a836-117">**참고:** Microsoft 365 관리 센터 역할의 해당 Azure Active Directory 구성원 자격은 사용자에게 Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="2a836-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2a836-118">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a836-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="2a836-119">메시지 추적 결과에 표시되는 최대 메시지 수는 선택한 보고서 유형에 따라 다릅니다(자세한 [](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 내용은 보고서 유형 선택 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="2a836-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="2a836-120">PowerShell 또는 Exchange Online 독립 실행형 EOP PowerShell의 [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet은 결과에 모든 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="2a836-121">메시지 추적 열기</span><span class="sxs-lookup"><span data-stu-id="2a836-121">Open message trace</span></span>

<span data-ttu-id="2a836-122">in the Microsoft 365 Defender portal ( <https://security.microsoft.com> ) go to Email & **collaboration** Exchange \> **message trace**.</span><span class="sxs-lookup"><span data-stu-id="2a836-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="2a836-123">또는 메시지 추적 페이지로 직접 이동하기 위해 를 <https://admin.exchange.microsoft.com/#/messagetrace> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2a836-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="2a836-124">이때 EAC의 메시지 추적이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2a836-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="2a836-125">자세한 내용은 최신 관리 센터의 메시지 [Exchange 참조하세요.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="2a836-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

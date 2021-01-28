---
title: 발생할 수 있는 메일 루프 인사이트 수정
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 가능한 메일 루프 수정 정보를 사용하여 조직에서 메일 루프를 식별하고 & 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029897"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="4c165-103">보안 및 준수 센터에서 가능한 메일 루프 & 수정</span><span class="sxs-lookup"><span data-stu-id="4c165-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4c165-104">메일 루프는 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="4c165-105">시스템 리소스를 낭비합니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-105">They waste system resources.</span></span>
- <span data-ttu-id="4c165-106">조직의 메일 볼륨 할당량을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="4c165-107">NDRs 또는 반송 메시지라고도 하는 배달 못지 않은 보고서가 원본 메시지 보낸 사람에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="4c165-108">보안 **및** 준수 센터의  메일 흐름 대시보드에서 권장 영역의 가능한 메일 루프 수정 정보에서는 조직에서 메일 루프가 [감지되면](https://protection.office.com) & 통보합니다. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4c165-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="4c165-109">이 인사이트는 조건이 검색된 후에만 나타납니다(메일 루프가 없는 경우 인사이트를 볼 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="4c165-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![메일 흐름 대시보드의 권장 영역에 있는 느린 메일 흐름 규칙 정보 수정](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="4c165-111">위젯에서 **세부** 정보 보기를 클릭하면 자세한 정보가 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="4c165-112">**도메인**</span><span class="sxs-lookup"><span data-stu-id="4c165-112">**Domain**</span></span>
- <span data-ttu-id="4c165-113">**메시지 수:** 샘플 메시지  보기를 클릭하여 루프의 영향을 받은 메시지 샘플에 대한 메시지 추적 결과를 볼 수 있습니다. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="4c165-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="4c165-114">**도메인 유형**" 예: Authoritative 또는 Non-authoritative.</span><span class="sxs-lookup"><span data-stu-id="4c165-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="4c165-115">**MX 레코드:** 도메인에 대한  MX 레코드의 **호스트(메일** 서버) 및 우선 순위 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="4c165-116">**루프** 이유 **및** 해결 방법: 가장 일반적인 메일 루프 시나리오를 식별하고 루프를 해결하기 위한 권장 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c165-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![가능한 메일 루프 수정 정보에서 세부 정보 보기를 클릭한 후 나타나는 세부 정보 플라이아웃](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="4c165-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c165-118">See also</span></span>

<span data-ttu-id="4c165-119">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4c165-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

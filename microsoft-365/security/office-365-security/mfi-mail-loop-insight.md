---
title: 발생할 수 있는 메일 루프 인사이트 수정
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드를 사용 하 여 조직의 메일 루프를 식별 하 고 수정 하는 데 사용할 수 있는 메일 루프 이해 문제를 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920571"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="d32c1-103">보안 & 준수 센터에서 가능한 메일 루프 통찰력 수정</span><span class="sxs-lookup"><span data-stu-id="d32c1-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d32c1-104">다음 이유 때문에 메일 루프가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="d32c1-105">시스템 리소스가 낭비 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-105">They waste system resources.</span></span>
- <span data-ttu-id="d32c1-106">조직의 메일 볼륨 할당량을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="d32c1-107">배달 못 함 보고서 (Ndr 또는 바운스 메시지)를 원본 메시지 보낸 사람에 게 혼동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="d32c1-108">[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **권장 사용자** 영역에서 추천 **가능한 메일 루프** 통찰력은 조직에서 메일 루프가 검색 되 면 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="d32c1-109">이 통찰력은 조건이 감지 된 후에만 표시 됩니다 (메일 루프가 없는 경우에는 통찰력을 볼 수 없음).</span><span class="sxs-lookup"><span data-stu-id="d32c1-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![메일 흐름 대시보드의 권장 사용자 영역에서 느린 메일 흐름 규칙 통찰력을 수정 합니다.](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="d32c1-111">위젯에 대 한 **세부 정보 보기** 를 클릭 하면 추가 정보가 포함 된 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="d32c1-112">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d32c1-112">**Domain**</span></span>
- <span data-ttu-id="d32c1-113">**메시지 수** : **예제 메시지 보기** 를 클릭 하 여 루프의 영향을 받는 메시지의 예제에 대 한 [메시지 추적](message-trace-scc.md) 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="d32c1-114">**도메인 유형** "(예: 정식 또는 신뢰할 수 없음)입니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="d32c1-115">**Mx 레코드** : 도메인의 mx 레코드에 대 한 호스트 ( **메일 서버** ) 및 **우선 순위** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="d32c1-116">**반복 이유와** **해결 방법** : 가장 일반적인 메일 루프 시나리오를 식별 하 고 루프를 수정 하기 위한 권장 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d32c1-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![수정 가능한 메일 루프 통찰력에 대 한 세부 정보 보기를 클릭 한 후에 표시 되는 세부 정보](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="d32c1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d32c1-118">See also</span></span>

<span data-ttu-id="d32c1-119">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d32c1-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

---
title: 느린 메일 흐름 규칙 인사이트 수정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 규칙 검사 기능을 사용하여 조직에서 비효율적이거나 유효하지 않은 메일 흐름 규칙(전송 규칙이라고도 함)을 식별하고 수정하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826884"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="14ecf-103">준수 센터에서 보안 전자 메일 흐름 규칙 정보를 & 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

<span data-ttu-id="14ecf-104">비효율적인 메일 흐름 규칙(전송 규칙이라고도 함)이 조직의 메일 흐름 지연으로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="14ecf-105">이 정보에서는 조직의 메일 흐름에 영향을 미치는 메일 흐름 규칙을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="14ecf-106">이러한 유형의 규칙의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="14ecf-107">대규모 그룹의 **구성원인** 조건</span><span class="sxs-lookup"><span data-stu-id="14ecf-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="14ecf-108">복잡한 정규식(regex) 패턴 일치를 사용하는 조건</span><span class="sxs-lookup"><span data-stu-id="14ecf-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="14ecf-109">첨부 파일에서 콘텐츠 확인을 사용하는 조건</span><span class="sxs-lookup"><span data-stu-id="14ecf-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="14ecf-110">보안 & **규정 준수 센터의 메일 흐름** 대시보드에서 **추천한** 메일 흐름 규칙 정보는 너무 오래 걸리는 경우 이를 알리는 메일 흐름 규칙을 제공합니다. [Mail flow dashboard](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="14ecf-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="14ecf-111">이 인사이트는 조건이 감지된 후에만 나타납니다(메일 루프가 없는 경우 사용자가 정보를 볼 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="14ecf-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="14ecf-112">이 알림을 사용하면 메일 흐름 지연을 줄이는 데 도움이 되는 메일 흐름 규칙을 식별하고 미세 치는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![메일 흐름 대시보드의 인용에 대한 권장 사항의 느린 메일 흐름 규칙 정보를 해결합니다.](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="14ecf-114">위로에서 **세부 정보 보기를** 클릭하면 다음과 같은 정보가 포함된 플라이아웃이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="14ecf-115">**규칙:** 요약 위로 가리키면 규칙의 모든 조건, 예외 및 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="14ecf-116">요약을 클릭하여 EAC(Exchange 관리 센터)에서 규칙을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="14ecf-117">**평가된 메시지 수**: 예제 [message trace](message-trace-scc.md) **메시지를 보려면 샘플 메시지를 클릭하면** 규칙의 영향을 받는 메시지 샘플에 대한 메시지 추적 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="14ecf-118">**각 메시지에 사용된 평균 시간**</span><span class="sxs-lookup"><span data-stu-id="14ecf-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="14ecf-119">**메시지에 소요된 중간값:** 상한절절과 반을 이시간 데이터의 절반 분리하는 중간값입니다.</span><span class="sxs-lookup"><span data-stu-id="14ecf-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![속도가 느린 메일 흐름 규칙 정보 수정을 클릭하여 표시되는 세부 정보 플라이아웃](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="14ecf-121">Exchange Online의 메일 흐름 규칙의 조건 및 예외에 대한 자세한 내용은 Exchange Online의 메일 흐름 규칙 조건 및 [예외(조건자)를 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="14ecf-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="14ecf-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="14ecf-122">Related topics</span></span>

<span data-ttu-id="14ecf-123">메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="14ecf-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

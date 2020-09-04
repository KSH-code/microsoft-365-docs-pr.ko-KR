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
description: 관리자는 보안 & 준수 센터에서 문제 해결을 사용 하 여 조직에서 비효율적인 메일 흐름 규칙 (전송 규칙이 라고도 함)을 식별 하 고 수정 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: c933a6816c82161d0f4a6199ff1a339dd8a10eae
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357347"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="c9a38-103">보안 & 준수 센터의 메일 흐름 규칙에 대 한 자세한 정보를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

<span data-ttu-id="c9a38-104">비효율적인 메일 흐름 규칙 (전송 규칙이 라고도 함)은 조직에 대 한 메일 흐름 지연을 야기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="c9a38-105">이 통찰력은 조직의 메일 흐름에 영향을 주는 메일 흐름 규칙을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="c9a38-106">이러한 규칙 유형의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="c9a38-107">이를 사용 하는 조건은 대규모 그룹 **의 구성원** 입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="c9a38-108">정규식 (regex) 패턴 일치를 사용 하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="c9a38-109">첨부 파일에서 콘텐츠 검사를 사용 하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="c9a38-110">[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **권장 사항에 대 한** **수정 메일 흐름 규칙** 에 대 한 자세한 정보는 메일 흐름 규칙을 완료 하는 데 시간이 너무 오래 걸려 사용자에 게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="c9a38-111">이 통찰력은 조건이 감지 된 후에만 표시 됩니다 (메일 루프가 없는 경우에는 통찰력을 볼 수 없음).</span><span class="sxs-lookup"><span data-stu-id="c9a38-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="c9a38-112">이 알림을 사용 하면 메일 흐름 규칙을 식별 하 고 미세 조정 하 여 메일 흐름 지연을 줄이는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![메일 흐름 대시보드의 권장 사용자 영역에서 느린 메일 흐름 규칙 통찰력을 수정 합니다.](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="c9a38-114">위젯에 대 한 **세부 정보 보기** 를 클릭 하면 추가 정보가 포함 된 플라이 아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="c9a38-115">**규칙**: 요약을 마우스로 가리키면 규칙의 모든 조건, 예외 및 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="c9a38-116">요약을 클릭 하 여 Exchange 관리 센터 (EAC)에서 규칙을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="c9a38-117">**평가 된 메시지 수**: **예제 메시지 보기** 를 클릭 하 여 규칙의 영향을 받는 메시지의 예제에 대 한 [메시지 추적](message-trace-scc.md) 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="c9a38-118">**각 메시지에 소요 된 평균 시간**</span><span class="sxs-lookup"><span data-stu-id="c9a38-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="c9a38-119">**평균 메시지에 소요 된 시간**: 데이터의 하한값에서 위쪽을 구분 하는 가운데 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a38-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![문제 해결에 대 한 세부 정보 보기를 클릭 한 후 표시 되는 세부 정보 플라이 인 느린 메일 흐름 규칙 이해](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="c9a38-121">Exchange Online의 메일 흐름 규칙에 대 한 조건 및 예외에 대 한 자세한 내용은 [Exchange online의 메일 흐름 규칙 조건 및 예외 (조건자)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9a38-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9a38-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c9a38-122">Related topics</span></span>

<span data-ttu-id="c9a38-123">메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9a38-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

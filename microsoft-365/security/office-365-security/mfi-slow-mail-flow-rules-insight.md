---
title: 느린 메일 흐름 규칙 인사이트 수정
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 및 준수 센터의 느린 메일 흐름 규칙 수정 인사이트를 사용하여 조직에서 비효율적이거나 손상된 메일 흐름 규칙(전송 규칙)을 식별하고 수정하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205292"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="0ff4f-103">보안 및 준수 센터에서 느린 메일 흐름 규칙 & 수정</span><span class="sxs-lookup"><span data-stu-id="0ff4f-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ff4f-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="0ff4f-104">**Applies to**</span></span>
- [<span data-ttu-id="0ff4f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ff4f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ff4f-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="0ff4f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ff4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ff4f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0ff4f-108">비효율적인 메일 흐름 규칙(전송 규칙)은 조직의 메일 흐름 지연으로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="0ff4f-109">이 인사이트는 조직의 메일 흐름에 영향을 미치는 메일 흐름 규칙을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="0ff4f-110">이러한 유형의 규칙의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="0ff4f-111">사용하는 **조건은 큰 그룹의** 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="0ff4f-112">복잡한 정규식(regex) 패턴 일치를 사용하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="0ff4f-113">첨부 파일에서 콘텐츠 체크 인을 사용하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="0ff4f-114">The **Fix slow mail flow rules insight** in the Recommended **area** of the Mail [flow](mail-flow-insights-v2.md) dashboard in the Security & [Compliance Center에서는](https://protection.office.com) 메일 흐름 규칙이 완료되는 데 너무 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="0ff4f-115">이 인사이트는 조건이 검색된 후에만 나타납니다(메일 루프가 없는 경우 인사이트를 볼 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="0ff4f-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="0ff4f-116">이 알림을 사용하여 메일 흐름 규칙을 식별하고 세부 조정하여 메일 흐름 지연을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![메일 흐름 대시보드의 권장 영역의 느린 메일 흐름 규칙 인사이트 수정](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="0ff4f-118">위젯에서 세부 **정보** 보기를 클릭하면 추가 정보가 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="0ff4f-119">**규칙:** 요약 위에 마우스를 여 규칙의 모든 조건, 예외 및 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="0ff4f-120">요약을 클릭하여 EAC(Exchange 관리 센터)에서 규칙을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="0ff4f-121">**평가된** 메시지 수: 샘플  메시지 보기를 클릭하여 [](message-trace-scc.md) 규칙의 영향을 받은 메시지의 샘플에 대한 메시지 추적 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="0ff4f-122">**각 메시지에 소요된 평균 시간**</span><span class="sxs-lookup"><span data-stu-id="0ff4f-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="0ff4f-123">**메시지에 소요된** 중간 시간: 시간 데이터의 하한값과 상한값을 구분하는 중간 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff4f-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![느린 메일 흐름 규칙 수정 정보에서 세부 정보 보기를 클릭한 후 나타나는 세부 정보 플라이아웃](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="0ff4f-125">메일 흐름 규칙의 조건 및 예외에 대한 자세한 내용은 Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)를 [참조하세요.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="0ff4f-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ff4f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ff4f-126">See also</span></span>

<span data-ttu-id="0ff4f-127">메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="0ff4f-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
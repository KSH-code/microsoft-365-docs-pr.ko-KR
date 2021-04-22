---
title: 위협 및 취약성 관리의 노출 점수
description: 위협 및 취약성 관리 노출 점수는 조직이 사이버 보안 위협에 얼마나 취약한지 반영합니다.
keywords: 노출 점수, 끝점 노출 점수용 Microsoft Defender, Endpoint tvm 노출 점수용 Microsoft Defender, 조직 노출 점수, tvm 조직 노출 점수, 위협 및 취약성 관리, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934108"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="b5aa1-104">노출 점수 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="b5aa1-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5aa1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b5aa1-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5aa1-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5aa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b5aa1-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="b5aa1-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b5aa1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5aa1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b5aa1-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b5aa1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5aa1-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="b5aa1-111">노출 점수는 Microsoft Defender 보안 센터의 위협 및 취약성 관리 대시보드에 표시됩니다. [](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b5aa1-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="b5aa1-112">이는 조직이 사이버 보안 위협에 얼마나 취약한지 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="b5aa1-113">노출 점수가 낮을 경우 장치가 악용에 덜 취약하다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="b5aa1-114">조직의 보안 상태와 관련한 높은 수준의 조치를 신속하게 이해하고 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="b5aa1-115">현재 상태를 개선하기 위해 조사 또는 조치가 필요한 영역을 감지하고 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="b5aa1-116">보안 노력이 미치는 영향에 대해 동료 및 관리와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="b5aa1-117">이 카드는 시간 경과에 따라 노출 점수 추세에 대한 높은 수준의 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="b5aa1-118">차트의 모든 스파이크는 더 조사할 수 있는 높은 사이버 보안 위협 노출을 시각적으로 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![노출 점수 카드](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="b5aa1-120">작동 방식</span><span class="sxs-lookup"><span data-stu-id="b5aa1-120">How it works</span></span>

<span data-ttu-id="b5aa1-121">노출 점수는 다음 수준으로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="b5aa1-122">0-29: 노출 점수가 낮음</span><span class="sxs-lookup"><span data-stu-id="b5aa1-122">0–29: low exposure score</span></span>
- <span data-ttu-id="b5aa1-123">30-69: 중간 노출 점수</span><span class="sxs-lookup"><span data-stu-id="b5aa1-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="b5aa1-124">70~100: 높은 노출 점수</span><span class="sxs-lookup"><span data-stu-id="b5aa1-124">70–100: high exposure score</span></span>

<span data-ttu-id="b5aa1-125">우선 순위가 높은 보안 권장 사항에 [](tvm-security-recommendation.md) 따라 문제를 수정하여 노출 점수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="b5aa1-126">각 소프트웨어에는 권장 사항으로 변환하고 조직에 대한 위험에 따라 우선 순위가 지정되는 약점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5aa1-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="b5aa1-127">위협 및 취약성 노출 줄이기</span><span class="sxs-lookup"><span data-stu-id="b5aa1-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="b5aa1-128">보안 권장 사항을 수정하여 위협 및 [취약성 노출을 줄입니다.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="b5aa1-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="b5aa1-129">위협 및 취약성 관리 대시보드에서 볼 수 있는 최상위 보안 권장 사항을 수정하여 노출 점수에 가장 많은 영향을 [미치게 합니다.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b5aa1-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5aa1-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b5aa1-130">Related topics</span></span>

- [<span data-ttu-id="b5aa1-131">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="b5aa1-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b5aa1-132">장치용 Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="b5aa1-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="b5aa1-133">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="b5aa1-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="b5aa1-134">이벤트 타임라인</span><span class="sxs-lookup"><span data-stu-id="b5aa1-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)

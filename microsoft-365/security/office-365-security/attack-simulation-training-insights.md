---
title: 공격 시뮬레이션 교육 활용
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft 365 Defender 포털의 공격 시뮬레이션 교육이 직원에게 어떤 영향을 주는지 알아보고 시뮬레이션 및 교육 결과를 통해 통찰력을 얻을 수 있습니다.
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878379"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="c2320-103">공격 시뮬레이션 교육 활용</span><span class="sxs-lookup"><span data-stu-id="c2320-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="c2320-104">**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c2320-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="c2320-105">공격 시뮬레이션 교육 내에서 Microsoft는 직원이 진행한 시뮬레이션 및 교육 결과를 기반으로 하는 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-105">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="c2320-106">이러한 인사이트를 통해 직원의 위협 준비 진행 상황을 계속 파악하고 다음 단계를 권장하여 직원과 환경을 공격에 대비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-106">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="c2320-107">당사는 사용할 수 있는 인사이트를 확장하기 위해 지속적으로 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-107">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="c2320-108">동작 영향 및 권장 작업은 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-108">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="c2320-109">시작을 위해 Microsoft 365 Defender 포털에서 공격 시뮬레이션 [교육을 진행합니다.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="c2320-109">To start, head over to [Attack simulation training in the Microsoft 365 Defender portal](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="c2320-110">손상율에 대한 동작 영향</span><span class="sxs-lookup"><span data-stu-id="c2320-110">Behavior impact on compromise rate</span></span>

<span data-ttu-id="c2320-111">공격 **시뮬레이션** 교육의 개요 탭에서 손상율 **카드에 대한 동작 영향을 확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-111">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="c2320-112">이 카드는 직원이 예측된 손상률과 달리 실행한 시뮬레이션을 어떻게 **처리하고 있는지 보여줍니다.**</span><span class="sxs-lookup"><span data-stu-id="c2320-112">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="c2320-113">이러한 정보를 사용하여 동일한 직원 그룹에 대해 여러 시뮬레이션을 실행하여 직원 위협 준비의 진행 상황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-113">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="c2320-114">그래프에서 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-114">In the graph you can see:</span></span>

- <span data-ttu-id="c2320-115">**공격 시뮬레이션 교육을** 사용하는 다른 Microsoft 365 테넌트에서 동일한 유형의 페이로드를 사용하는 시뮬레이션의 평균 손상률을 반영하는 예측된 손상률입니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-115">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="c2320-116">**실제 손상률은** 시뮬레이션에 대해 떨어졌다는 직원의 백분율을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-116">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="c2320-117">또한 공격으로 손상된 실제 직원 수와 예측된 손상율의 `<number> less susceptible to phishing` 차이를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-117">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="c2320-118">이러한 직원 수는 향후 유사한 공격으로 손상될 가능성이 낮아지지만 예측된 손상률과는 달리 직원의 전반적인적인 영향을 `<percent%> better than predicted rate` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-118">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c2320-119">![공격 시뮬레이션 교육 개요에 대한 동작 영향 카드](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="c2320-119">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="c2320-120">더 자세한 보고서를 보려면 시뮬레이션 및 교육 관련 보고서 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c2320-120">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="c2320-121">이 보고서는 시뮬레이션 자체의 추가 컨텍스트와 동일한 정보를 제공합니다(예: 시뮬레이션 기술 및 대상이 지정된 총 사용자).</span><span class="sxs-lookup"><span data-stu-id="c2320-121">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="c2320-122">권장 작업</span><span class="sxs-lookup"><span data-stu-id="c2320-122">Recommended actions</span></span>

<span data-ttu-id="c2320-123">시뮬레이션 [ **탭에서**](https://security.microsoft.com/attacksimulator?viewid=simulations)시뮬레이션을 선택하면 추천 작업 섹션이 있는 시뮬레이션 세부 **정보로 이동됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c2320-123">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="c2320-124">권장 작업 섹션에서는 Microsoft 보안 점수에서 사용할 수 있는 권장 [사항을 자세히 설명합니다.](../defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="c2320-124">The recommended actions section details recommendations as available in [Microsoft Secure Score](../defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="c2320-125">이러한 권장 사항은 시뮬레이션에 사용되는 페이로드를 기반으로 하여 직원과 환경을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-125">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="c2320-126">각 개선 작업을 클릭하면 세부 정보로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2320-126">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c2320-127">![공격 시뮬레이션 교육에 대한 권장 작업 섹션](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="c2320-127">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="c2320-128">관련 링크</span><span class="sxs-lookup"><span data-stu-id="c2320-128">Related Links</span></span>

[<span data-ttu-id="c2320-129">공격의 신나는 교육 사용 시작</span><span class="sxs-lookup"><span data-stu-id="c2320-129">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="c2320-130">피싱 공격 시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="c2320-130">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="c2320-131">사용자 교육을 위한 페이로드 만들기</span><span class="sxs-lookup"><span data-stu-id="c2320-131">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)

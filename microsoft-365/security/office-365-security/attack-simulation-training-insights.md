---
title: 공격 시뮬레이션 교육 활용
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft 365 Defender 포털의 공격 시뮬레이션 교육이 직원에게 미치는 영향을 알아보고 시뮬레이션 및 교육 결과를 통해 정보를 얻을 수 있습니다.
ms.technology: mdo
ms.openlocfilehash: 9376ef78ef6349bbd595ec0c48fccd394e0cd869
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154356"
---
# <a name="gain-insights-through-attack-simulation-training"></a>공격 시뮬레이션 교육 활용

**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)

공격 시뮬레이션 교육 내에서 Microsoft는 직원이 진행한 시뮬레이션 및 교육 결과를 기반으로 하는 인사이트를 제공합니다. 이러한 인사이트를 통해 직원의 위협 준비 진행 상황을 계속 파악하고 다음 단계를 권장하여 직원과 환경을 공격에 대비할 수 있습니다.

당사는 사용할 수 있는 인사이트를 확장하기 위해 지속적으로 작업하고 있습니다. 동작 영향 및 권장 작업은 현재 사용할 수 있습니다. 시작을 위해 Microsoft 365 Defender 포털에서 공격 시뮬레이션 [교육을 진행합니다.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>손상율에 대한 동작 영향

공격 **시뮬레이션** 교육의 개요 탭에서 손상율 **카드에 대한 동작 영향을 확인할 수** 있습니다. 이 카드는 직원이 예측된 손상률과 달리 실행한 시뮬레이션을 어떻게 **처리하고 있는지 보여줍니다.** 이러한 정보를 사용하여 동일한 직원 그룹에 대해 여러 시뮬레이션을 실행하여 직원 위협 준비의 진행 상황을 추적할 수 있습니다.

그래프에서 다음을 볼 수 있습니다.

- **공격 시뮬레이션 교육을** 사용하는 다른 Microsoft 365 테넌트에서 동일한 유형의 페이로드를 사용하는 시뮬레이션의 평균 손상률을 반영하는 예측된 손상률입니다.
- **실제 손상률은** 시뮬레이션에 대해 떨어졌다는 직원의 백분율을 반영합니다.

또한 공격으로 손상된 실제 직원 수와 예측된 손상율의 `<number> less susceptible to phishing` 차이를 반영합니다. 이러한 직원 수는 향후 유사한 공격으로 손상될 가능성이 낮아지지만 예측된 손상률과는 달리 직원의 전반적인적인 영향을 `<percent%> better than predicted rate` 나타냅니다.

> [!div class="mx-imgBorder"]
> ![공격 시뮬레이션 교육 개요에 대한 동작 영향 카드입니다.](../../media/attack-sim-preview-behavior-impact-card.png)

더 자세한 보고서를 보려면 시뮬레이션 및 교육 관련 보고서 **보기를 클릭합니다.** 이 보고서는 시뮬레이션 자체의 추가 컨텍스트와 동일한 정보를 제공합니다(예: 시뮬레이션 기술 및 대상이 지정된 총 사용자).

## <a name="recommended-actions"></a>권장 작업

시뮬레이션 [ **탭에서**](https://security.microsoft.com/attacksimulator?viewid=simulations)시뮬레이션을 선택하면 추천 작업 섹션이 있는 시뮬레이션 세부 **정보로 이동됩니다.**

권장 작업 섹션에서는 Microsoft 보안 점수에서 사용할 수 있는 권장 [사항을 자세히 설명합니다.](../defender/microsoft-secure-score.md) 이러한 권장 사항은 시뮬레이션에 사용되는 페이로드를 기반으로 하여 직원과 환경을 보호하는 데 도움이 됩니다. 각 개선 작업을 클릭하면 세부 정보로 작업할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![공격 시뮬레이션 교육에 대한 권장 작업 섹션](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>관련 링크

[공격의 신나는 교육 사용 시작](attack-simulation-training-get-started.md)

[피싱 공격 시뮬레이션 만들기](attack-simulation-training.md)

[사용자 교육을 위한 페이로드 만들기](attack-simulation-training-payloads.md)

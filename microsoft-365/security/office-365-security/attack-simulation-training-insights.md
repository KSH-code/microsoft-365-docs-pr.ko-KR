---
title: 공격 시뮬레이션 교육 활용
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365 보안 센터의 공격 시뮬레이션 교육을 통해 직원에 게 어떤 영향을 주는지, 그리고 시뮬레이션 및 교육 결과를 통해 통찰력을 얻을 방법을 알아봅니다.
ms.openlocfilehash: 6a8ee15f14475a1cebb169ab49bdb0f490c81345
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357354"
---
# <a name="gain-insights-through-attack-simulation-training"></a>공격 시뮬레이션 교육 활용

Microsoft는 Attack 시뮬레이션이 진행 되는 동안 시뮬레이션이 발생 한 결과를 기반으로 정보를 제공 합니다. 이러한 통찰력은 직원 들이 위협 준비를 진행 하 고 있는지를 알려 주고, 직원을 보다 잘 준비 하 고 공격 환경을 개선 하기 위한 다음 단계를 권장 합니다.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

현재는 사용할 수 있는 정보를 확장 하는 작업을 진행 중 이며 동작 영향 및 권장 조치를 지금 사용할 수 있습니다.
먼저 [Microsoft 365 보안 센터에서 공격 시뮬레이션 교육](https://security.microsoft.com/attacksimulator?viewid=overview)을 시작 합니다.

## <a name="behavior-impact-on-compromise-rate"></a>작동 속도에 미치는 영향

공격 시뮬레이션 학습 **개요** 탭에서 손상 된 카드 **에 미치는 영향** 을 확인할 수 있습니다. 이 카드는 예상 되는 **공격 속도** 와 대조적으로 시뮬레이션을 통해 직원이 처리 한 방법을 보여 줍니다. 이러한 정보를 활용 하 여 동일한 직원 그룹에 대해 여러 시뮬레이션을 실행 하 여 직원 위협 준비 상태를 추적할 수 있습니다.

그래프에서 다음을 확인할 수 있습니다.

- 모든 테 넌 트에서 공격 시뮬레이션 훈련을 사용 하 여 시뮬레이션에 대 한 평균 침해 속도를 반영 하는 **예상 침해 속도** 입니다.
- **실제 손상 비율은** 시뮬레이션에 대 한 직원의 비율을 반영 합니다.

또한 `<number> less susceptible to phishing` 공격에 의해 손상 된 실제 직원 수와 예상 되는 손상 률 간의 차이를 반영 합니다. 이 직원 수는 나중에 유사한 공격에 의해 손상 될 가능성이 낮고, 예상 되는 `<percent%> better than predicted rate` 손상 률과 대비 하 여 직원의 전반적인 전체적인 정도를 나타냅니다.

> [!div class="mx-imgBorder"]
> ![동작 영향 카드 공격 시뮬레이션 교육 개요](../../media/attack-sim-preview-behavior-impact-card.png)

보다 자세한 보고서를 보려면 시뮬레이션 기술 및 전체 사용자를 대상으로 하는 것과 같이 시뮬레이션 자체의 추가 컨텍스트와 함께 동일한 정보를 제공 하는 시뮬레이션 **및 교육 efficacy 보고서 보기** 를 클릭 합니다.

## <a name="recommended-actions"></a>권장 작업

시뮬레이션 [ **Simulations** 탭](https://security.microsoft.com/attacksimulator?viewid=simulations)에서 시뮬레이션을 선택 하면 시뮬레이션 세부 정보로 이동 됩니다. 여기서는 **권장 작업** 섹션을 찾습니다.

권장 작업 섹션에는 [Microsoft 보안 점수](../mtp/microsoft-secure-score.md)에서 제공 되는 권장 사항에 대 한 정보가 나와 있습니다. 이러한 권장 사항은 시뮬레이션에 사용 되는 페이로드를 기반으로 하며 직원과 환경을 보호 하는 데 도움이 됩니다. 각 향상 작업을 클릭 하면 세부 정보로 이동 됩니다.

> [!div class="mx-imgBorder"]
> ![공격 시뮬레이션 교육에 대 한 권장 조치 섹션](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>관련 링크

**Attack 시뮬레이터** [는 피싱 공격 시뮬레이션을 만들고](attack-simulation-training.md) [사용자에 게 교육을 위한 페이로드를 만듭니다](attack-simulation-training-payloads.md) .

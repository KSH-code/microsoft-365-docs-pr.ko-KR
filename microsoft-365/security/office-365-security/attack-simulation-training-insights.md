---
title: 공격 시뮬레이션 교육 활용
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft 365 보안 센터의 공격 시뮬레이션 교육이 직원에게 미치는 영향과 시뮬레이션 및 교육 결과에 대한 정보를 얻을 수 있습니다.
ms.openlocfilehash: baff6032f295b2b49b4f2ec9280fb465d47b8dc3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877143"
---
# <a name="gain-insights-through-attack-simulation-training"></a>공격 시뮬레이션 교육 활용

공격 시뮬레이션 교육 내에서 Microsoft는 직원이 진행한 시뮬레이션 및 교육 결과를 기반으로 정보를 제공합니다. 이러한 인사이트를 통해 직원의 위협 준비 진행 상황을 계속 파악하고 직원과 환경을 공격에 대비하기 위한 다음 단계를 권장할 수 있습니다.

당사는 지속적으로 사용할 수 있는 인사이트를 확장하기 위해 작업 중입니다. 동작 영향 및 권장 작업은 현재 사용할 수 있습니다. 시작을 위해 Microsoft 365 보안 센터에서 공격 [시뮬레이션 교육을 진행합니다.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>손상율에 대한 동작 영향

공격 **시뮬레이션** 교육의 개요 탭에서 손상율 카드에 대한 동작 **영향을 찾을 수** 있습니다. 이 카드는 직원이 예측한 손상률과 대조적으로 실행한 시뮬레이션을 처리한 **방법을 보여줍니다.** 이러한 정보를 사용하여 동일한 직원 그룹에 대해 여러 시뮬레이션을 실행하여 직원 위협 준비의 진행 상황을 추적할 수 있습니다.

그래프에서 다음을 볼 수 있습니다.

- **공격 시뮬레이션 교육을** 사용하는 다른 Microsoft 365 테넌트에서 동일한 유형의 페이로드를 사용하는 시뮬레이션의 평균 손상률을 반영하는 예측된 손상률입니다.
- **실제 손상률은** 시뮬레이션에 대해 떨어졌다는 직원의 비율을 반영합니다.

또한 공격으로 손상된 실제 직원 수와 예측한 손상율의 `<number> less susceptible to phishing` 차이를 반영합니다. 이 수의 직원은 향후 유사한 공격으로 손상될 가능성이 낮아지지만 예상 손상률과는 대조적으로 직원들이 전반적으로 어떻게 `<percent%> better than predicted rate` 나타냈는가를 나타냅니다.

> [!div class="mx-imgBorder"]
> ![공격 시뮬레이션 교육 개요에 대한 동작 영향 카드](../../media/attack-sim-preview-behavior-impact-card.png)

자세한 보고서를 보려면 시뮬레이션 및 교육 관련 보고서 **보기를 클릭합니다.** 이 보고서는 시뮬레이션 자체의 추가 컨텍스트(예: 시뮬레이션 기술 및 대상이 지정한 총 사용자)와 동일한 정보를 제공합니다.

## <a name="recommended-actions"></a>권장 작업

시뮬레이션 [ **탭에서**](https://security.microsoft.com/attacksimulator?viewid=simulations)시뮬레이션을 선택하면 추천 작업 섹션이 있는 시뮬레이션 세부 정보로 **이동됩니다.**

권장 작업 섹션에서는 Microsoft 보안 점수에서 사용할 수 있는 권장 [사항을 자세히 설명합니다.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 이러한 권장 사항은 시뮬레이션에 사용된 페이로드를 기반으로 하여 직원과 환경을 보호하는 데 도움이 됩니다. 각 개선 작업을 클릭하면 세부 정보를 확인하게 됩니다.

> [!div class="mx-imgBorder"]
> ![공격 시뮬레이션 교육에 대한 권장 작업 섹션](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>관련 링크

[공격 시뮬레이션 교육 사용 시작](attack-simulation-training-get-started.md)

[피싱 공격 시뮬레이션 만들기](attack-simulation-training.md)

[사용자 교육을 위한 페이로드 만들기](attack-simulation-training-payloads.md)

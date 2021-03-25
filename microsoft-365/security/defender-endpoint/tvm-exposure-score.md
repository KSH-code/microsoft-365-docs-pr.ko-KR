---
title: 위협 및 취약성 관리의 노출 점수
description: 위협 및 취약성 관리 노출 점수는 조직이 사이버 보안 위협에 얼마나 취약한지 반영합니다.
keywords: 노출 점수, mdatp 노출 점수, mdatp tvm 노출 점수, 조직 노출 점수, tvm 조직 노출 점수, 위협 및 취약성 관리, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cc7abd678d6f2d317d02c4ed2b8028e7e270b055
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076487"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>노출 점수 - 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약점 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

노출 점수는 Microsoft Defender 보안 센터의 위협 및 취약성 관리 대시보드에 표시됩니다. [](tvm-dashboard-insights.md) 이는 조직이 사이버 보안 위협에 얼마나 취약한지 반영합니다. 노출 점수가 낮을 경우 장치가 악용에 덜 취약하다는 의미입니다.

- 조직의 보안 상태와 관련한 높은 수준의 조치를 신속하게 이해하고 식별합니다.
- 현재 상태를 개선하기 위해 조사 또는 조치가 필요한 영역을 감지하고 대응합니다.
- 보안 노력이 미치는 영향에 대해 동료 및 관리와 통신합니다.

이 카드는 시간 경과에 따라 노출 점수 추세에 대한 높은 수준의 보기를 제공합니다. 차트의 모든 스파이크는 더 조사할 수 있는 높은 사이버 보안 위협 노출을 시각적으로 표시하는 것입니다.

![노출 점수 카드](images/tvm_exp_score.png)

## <a name="how-it-works"></a>작동 방식

노출 점수는 다음 수준으로 세분화됩니다.

- 0-29: 노출 점수가 낮음
- 30-69: 중간 노출 점수
- 70~100: 높은 노출 점수

우선 순위가 높은 보안 권장 사항에 [](tvm-security-recommendation.md) 따라 문제를 수정하여 노출 점수를 줄일 수 있습니다. 각 소프트웨어에는 권장 사항으로 변환하고 조직에 대한 위험에 따라 우선 순위가 지정되는 약점이 있습니다.

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>위협 및 취약성 노출 줄이기

보안 권장 사항을 수정하여 위협 및 [취약성 노출을 줄입니다.](tvm-security-recommendation.md) 위협 및 취약성 관리 대시보드에서 볼 수 있는 최상위 보안 권장 사항을 수정하여 노출 점수에 가장 많은 영향을 [미치게 합니다.](tvm-dashboard-insights.md)

## <a name="related-topics"></a>관련 항목

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [장치용 Microsoft 보안 점수](tvm-microsoft-secure-score-devices.md)
- [보안 권장 사항](tvm-security-recommendation.md)
- [이벤트 타임라인](threat-and-vuln-mgt-event-timeline.md)

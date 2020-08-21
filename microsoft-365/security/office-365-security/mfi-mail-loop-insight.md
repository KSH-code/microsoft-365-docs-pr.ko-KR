---
title: 발생할 수 있는 메일 루프 인사이트 수정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 해결 가능한 메일 루프 정보를 사용하여 조직에서 메일 루프를 식별하고 해결하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826956"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>보안 및 준수 센터의 가능한 메일 & 문제 해결

메일 루프는 시스템 리소스를 요구하고, 조직의 메일 볼륨 할당량을 소비한 다음 NDR 또는 반송 메시지라고도 하는 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)를 전송하기 때문에 나량입니다.

보안 & **규정 준수 센터의 메일** 흐름 대시보드 에서 **발생하는 메일** 루프의 가능한 메일 루프 수정 목록은 조직에서 메일 루프가 탐지될 때 알리도록 알리도록 합니다. [Mail flow dashboard](mail-flow-insights-v2.md) 이 인사이트는 조건이 감지된 후에만 나타납니다(메일 루프가 없는 경우 사용자가 정보를 볼 수 없습니다).

![메일 흐름 대시보드의 인용에 대한 권장 사항의 느린 메일 흐름 규칙 정보를 해결합니다.](../../media/mfi-fix-possible-mail-loop.png)

위로에서 **세부 정보 보기를** 클릭하면 다음과 같은 정보가 포함된 플라이아웃이 표시됩니다.

- **도메인**
- **메시지 수:** 예제 메시지 **보기를 클릭하면 루프의** [영향을](message-trace-scc.md) 받는 메시지 샘플에 대한 메시지 추적 결과를 확인할 수 있습니다.
- **도메인 유형**"신뢰할 수 있는 도메인 또는 신뢰할 수 없는 도메인".
- **MX 레코드:** 도메인의**MX 레코드의 호스트(메일** **서버)** 및 우선 순위 값입니다.
- **루프 이유** **및 해결**방법: 가장 일반적인 메일 루프 시나리오를 식별하고 루프를 해결하기 위한 권장 작업(가능한 경우)을 제공합니다.

![Fix possible mail 루프 정보 수정(Fix possible mail 루프 정보) 정보 보기를 클릭하면 표시되는 플라이아웃](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)

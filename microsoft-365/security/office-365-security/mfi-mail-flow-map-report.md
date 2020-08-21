---
title: 메일 흐름 지도
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 메일 흐름 맵을 사용하여 커넥터를 사용하고 커넥터를 사용하지 않고 조직에서 메일 흐름을 이동하는 방법을 시각화하고 추적할 수 있습니다.
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827004"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>보안 도메인 준수 센터의 & 흐름 맵

보안 **및 준수 센터의** [메일 흐름 대시보드](mail-flow-insights-v2.md) &에 있는 메일 흐름 맵은 조직전체에서 메일이 수행되는 방식을 통한 정보를 제공합니다. 이 정보를 사용하여 패턴을 알아보고 필요에 따라 문제를 해결할 수 있습니다.

![보안 그룹 준수 센터의 메일 흐름 대시보드에서 위단계 & 위위로 맵정](../../media/mfi-mail-flow-map-widget.png)

기본적으로 위소에서는 *Sankey* 다이어그램이라고 하는 차트에서 이전 날의 메일 흐름 패턴을 보여 줍니다. 왼쪽 화살표와 오른쪽 ![ 화살표를 ](../../media/scc-left-arrow.png) 사용하여 다양한 일간의 ![ ](../../media/scc-right-arrow.png) 정보를 표시할 수 있습니다. 각 색은 다른 인바운드 또는 아웃바운드 커넥터를 통한(또는 커넥터 사용 금지)를 통해서의 메일 흐름을 나타냅니다. 특정 한 종류에 전화를 가리면 해당 유형의 커넥터에 대해 메시지 수가 표시됩니다.

## <a name="report-view-for-the-mail-flow-map"></a>메일 흐름 맵에 대한 보고서 보기

메일 흐름 맵 **위로를 클릭하면** 메일 흐름 맵 **보고서로 이동합니다.**

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **데이터 표시: 기본적으로**위작업의 더 큰 보기입니다. 특정 한 종류에 전화를 가리면 해당 유형의 커넥터에 대해 메시지 수가 표시됩니다.

  ![메일 흐름 맵 보고서의 개요 보기](../../media/mfi-mail-flow-map-report-overview.png)

- **데이터 표시: 세부 정보:** 이 보기는 커넥터 및 대상 도메인에 대한 세부 정보를 표시합니다. 맨 위에 있는 보낸 사람 및 받는 사람 도메인이 나열되고 나머지는 다른 사람에 **게 있습니다.** 특정 색및 구역에 커서를 두면 메시지 수가 표시됩니다.

  ![메일 흐름 맵 보고서의 세부 정보 보기](../../media/mfi-mail-flow-map-report-detail.png)

보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

특정 날짜 범위에 대한 보고서에 대한 정보를 한 명 이상의 받는 사람에게 전자 메일로 보내려면 요청 을 **클릭합니다.**

관련 인사이트가 사용 가능한 경우 메일 흐름 맵 아래에 표시됩니다(예: [수정 가능한 메일 루프 정보 정보](mfi-mail-loop-insight.md)확인).

## <a name="details-table-view-for-the-mail-flow-map"></a>메일 흐름 맵의 세부 정보 표 보기

보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.

- **날짜**
- **범주**
- **커넥터/타사 서비스 공급자**
- **보낸 사람/받는 사람 도메인**
- **메시지 수**

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

행을 선택하는 경우 다음과 유사한 세부 정보가 플라이아웃에 표시됩니다.

![메일 흐름 맵의 세부 정보 표에서 세부 정보 플라이아웃](../../media/mfi-mail-flow-map-view-details-table-details.png)

특정 날짜 범위에 대한 보고서에 대한 정보를 한 명 이상의 받는 사람에게 전자 메일로 보내려면 요청 을 **클릭합니다.**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)

---
title: 메일 흐름 지도
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 메일 흐름 맵을 사용 하 여 커넥터를 통해 메일을 주고 받지 않는 커넥터를 사용 하는 방법을 시각화 하 고 추적 하는 방법을 알아봅니다.
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877768"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>보안 & 준수 센터의 메일 흐름 맵

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[보안 & 준수 센터](https://protection.office.com) 의 메일 흐름 [대시보드의](mail-flow-insights-v2.md) **메일 흐름 맵은** 조직에서 메일이 흐르는 방식에 대 한 통찰력을 제공 합니다. 이 정보를 사용 하 여 패턴을 파악 하 고, 상황을 식별 하 고, 문제가 발생 하면 문제를 해결할 수 있습니다.

![보안 & 준수 센터의 메일 흐름 대시보드의 메일 흐름 맵 위젯](../../media/mfi-mail-flow-map-widget.png)

기본적으로 위젯은 *Sankey* 다이어그램 이라고 하는 차트에서 이전 날짜의 메일 흐름 패턴을 보여 줍니다. 왼쪽 화살표 ![ 왼쪽 화살표 ](../../media/scc-left-arrow.png) 및 오른쪽 화살표 오른쪽 화살표를 사용 ![ 하 여 ](../../media/scc-right-arrow.png) 다른 요일의 정보를 표시할 수 있습니다. 각각의 다른 색은 다른 인바운드 또는 아웃 바운드 커넥터 (또는 커넥터를 사용 하지 않고)에 대 한 메일 흐름을 나타냅니다. 특정 색을 가리키면 해당 연결선 종류에 대 한 메시지 수가 표시 됩니다.

## <a name="report-view-for-the-mail-flow-map"></a>메일 흐름 맵의 보고서 보기

**메일 흐름 맵** 위젯을 클릭 하면 **메일 흐름 맵** 보고서로 이동 합니다.

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **데이터 표시: 개요** :이는 기본적으로 더 큰 위젯의 보기입니다. 특정 색을 가리키면 해당 연결선 종류에 대 한 메시지 수가 표시 됩니다.

  ![메일 흐름 맵 보고서의 개요 보기](../../media/mfi-mail-flow-map-report-overview.png)

- **데이터 표시: 세부** 정보:이 보기에는 커넥터 및 대상 도메인에 대 한 세부 정보가 표시 됩니다. 상위 보낸 사람 및 받는 사람 도메인이 나열 되 고 나머지는 **다른 사용자에 게** 추가 됩니다. 특정 색과 섹션을 가리키면 메시지 수가 표시 됩니다.

  ![메일 흐름 맵 보고서의 세부 정보 보기](../../media/mfi-mail-flow-map-report-detail.png)

보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.

특정 날짜 범위에 대 한 보고서를 한 명 이상의 받는 사람에 게 전자 메일로 전송 하려면 **다운로드 요청** 을 클릭 합니다.

사용 가능한 경우 메일 흐름 맵 (예: [가능한 메일 루프 통찰력 파악](mfi-mail-loop-insight.md))에 관련 정보가 표시 됩니다.

## <a name="details-table-view-for-the-mail-flow-map"></a>메일 흐름 맵에 대 한 세부 정보 표 보기

보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.

- **날짜**
- **범주**
- **커넥터/타사 서비스 공급자**
- **보낸 사람/받는 사람 도메인**
- **메시지 수**

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜** 와 함께 날짜 범위를 지정할 수 있습니다.

행을 선택 하는 경우 플라이 아웃에 다음과 유사한 세부 정보가 표시 됩니다.

![메일 흐름 맵의 세부 정보 테이블에서의 정보 플라이 아웃](../../media/mfi-mail-flow-map-view-details-table-details.png)

특정 날짜 범위에 대 한 보고서를 한 명 이상의 받는 사람에 게 전자 메일로 전송 하려면 **다운로드 요청** 을 클릭 합니다.

보고서 보기로 돌아가려면 **보고서 보기** 를 클릭 합니다.

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.

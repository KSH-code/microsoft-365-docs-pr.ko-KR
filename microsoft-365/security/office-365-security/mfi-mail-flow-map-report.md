---
title: 메일 흐름 지도
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 메일 흐름 맵을 사용하여 커넥터를 사용하지 않고도 조직에서 & 흐름을 시각화하고 추적하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bdde117d8984db3a71624ab48a6ed88ba8367054
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192342"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>보안 및 준수 센터의 & 흐름 맵

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

보안 **및** 준수 [](mail-flow-insights-v2.md) 센터의 메일 [](https://protection.office.com) 흐름 대시보드에 있는 메일 흐름 & 조직을 통해 메일이 흐르는 방식에 대한 정보를 제공합니다. 이 정보를 사용하여 패턴을 학습하고, 오류를 식별하고, 발생할 때 문제를 해결할 수 있습니다.

![보안 및 준수 센터의 메일 흐름 대시보드에 있는 메일 흐름 & 위젯입니다.](../../media/mfi-mail-flow-map-widget.png)

기본적으로 위젯에는 전날의 메일 흐름 패턴이 Sankey 다이어그램으로 알려진 *차트에* 표시됩니다. 왼쪽 화살표 왼쪽 ![ 화살표를 사용할 수 있습니다.](../../media/scc-left-arrow.png) 오른쪽 화살표를 사용하여 다른 일의 ![ ](../../media/scc-right-arrow.png) 정보를 표시하는 오른쪽 화살표 각 색은 서로 다른 인바운드 또는 아웃바운드 커넥터를 통해(또는 커넥터를 사용하지 않고) 메일 흐름을 나타내며, 특정 색 위에 마우스를 대면 해당 유형의 커넥터에 대한 메시지 수가 표시됩니다.

## <a name="report-view-for-the-mail-flow-map"></a>메일 흐름 맵에 대한 보고서 보기

메일 흐름 맵 **위젯을** 클릭하면 메일 흐름 지도 **보고서로 표시됩니다.**

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **데이터 표시: 개요:** 이 보기는 기본적으로 위젯의 더 큰 보기입니다. 특정 색 위에 마우스를 대면 해당 유형의 커넥터에 대한 메시지 수가 표시됩니다.

  ![메일 흐름 지도 보고서의 개요 보기입니다.](../../media/mfi-mail-flow-map-report-overview.png)

- **데이터 표시: 세부 정보:** 이 보기에는 커넥터 및 대상 도메인에 대한 세부 정보가 표시됩니다. 최상위 보낸 사람 및 받는 사람 도메인이 나열되어 나머지는 기타 에 **추가됩니다.** 특정 색과 섹션 위에 마우스를 대면 메시지 수가 표시됩니다.

  ![메일 흐름 지도 보고서의 세부 정보 보기입니다.](../../media/mfi-mail-flow-map-report-detail.png)

보고서 보기에서 **필터를** 클릭하면 시작 날짜 및  종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**

사용 가능한 경우 메일 흐름 맵 아래에 관련 인사이트가 [표시됩니다(예: Fix possible mail loop insight).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>메일 흐름 맵에 대한 세부 정보 테이블 보기

보고서 보기에서 **세부** 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.

- **날짜**
- **범주**
- **커넥터/타사 서비스 공급자**
- **보낸 사람/받는 사람 도메인**
- **메시지 수**

세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

행을 선택하면 플라이아웃에 유사한 세부 정보가 표시됩니다.

![메일 흐름 맵의 세부 정보 표에서 플라이아웃 세부 정보](../../media/mfi-mail-flow-map-view-details-table-details.png)

특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**

보고서 보기로 돌아가려면 보고서 **보기 를 클릭합니다.**

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)

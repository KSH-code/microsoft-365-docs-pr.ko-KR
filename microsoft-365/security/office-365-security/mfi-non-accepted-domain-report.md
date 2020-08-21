---
title: 메일 흐름 대시보드의 비허용 도메인 보고서
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 허용되지 않는 도메인 보고서를 사용하여 Microsoft 365에 보낸 사람의 도메인이 구성되지 않은 온-프레미스 조직에서 메시지를 모니터링하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826944"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>보안 도메인 준수 센터의 비허용 & 보고서

보안 & **준수 센터의 메일** 흐름 [대시보드에](mail-flow-insights-v2.md) 있는 비허용 도메인 보고서에는 보낸 사람의 도메인이 Microsoft 365 조직에서 허용 도메인으로 구성되지 않은 경우 온-프레미스 전자 메일 조직의 메시지에 대한 정보가 표시됩니다.

Microsoft 365는 이러한 메시지의 의도가 악의적임을 보여 주기 위한 데이터가 있는 경우 이러한 메시지를 제한할 수 있습니다. 따라서 문제가 발생하는 일을 이해하고 해당 문제를 해결하는 데 반드시 중요합니다.

![보안 흐름 대시보드의 보안 및 준수 센터의 메일 흐름 대시보드에 허용되지 & 위과](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>비허용 도메인 보고서에 대한 보고서 보기

비허용 도메인 **위산에서 차트를 클릭하면** 허용되지 않는 도메인 **보고서로 가게 됩니다.**

기본적으로 영향을 받는 모든 커넥터의 활동이 표시됩니다. 데이터 **표시를 클릭하면**드롭다운이 있는 특정 커넥터를 선택할 수 있습니다.

차트에서 데이터 요소(일)를 가리치치면 커넥터의 총 메시지 개수가 표시됩니다.

![비허용 도메인 보고서의 보고서 보기](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>비허용 도메인 보고서의 세부 정보 표 보기

보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.

- **날짜**
- **인바운드 커넥터 이름**
- **보낸 사람 도메인**
- **메시지 수**
- **샘플 메시지:** 영향을 받는 메시지 샘플의 메시지 ID

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

특정 날짜 범위에 대한 보고서에 대한 정보를 한 명 이상의 받는 사람에게 전자 메일로 보내려면 요청 을 **클릭합니다.**

표에서 행을 선택하면 다음 정보와 함께 플라이아웃이 나타납니다.

- **날짜**
- **인바운드 커넥터 이름**
- **보낸 사람 도메인**
- **메시지 수**
- **샘플 메시지**: 샘플 메시지를 **표시하면 영향을** 받는 [메시지 샘플의](message-trace-scc.md) 메시지 추적 결과를 볼 수 있습니다.

![비허용 도메인 보고서의 세부 정보 표 보기에서 행을 선택한 후 세부 정보 플라이아웃](../../media/mfi-non-accepted-domain-report-details-flyout.png)

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)

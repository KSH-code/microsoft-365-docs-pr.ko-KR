---
title: 메일 흐름 대시보드의 배달 못 함 보고서
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 배달 못 함 정보 보고서를 사용 하 여 조직의 보낸 사람에 대 한 Ndr 또는 바운스 메시지 라고도 하는 배달 못함 보고서에서 가장 자주 발생 하는 오류 코드를 모니터링 하는 방법을 알아봅니다.
ms.openlocfilehash: d45382ab5c7e0d0a73487740544f20b9c25a3ad1
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577435"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>보안 & 준수 센터의 배달 못 함 보고서

보안 & 준수 센터의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **배달 못 함 보고서** 에는 조직 내 사용자에 대 한 ndr (배달 또는 바운스 메시지가 라고도 하는)에서 가장 많이 발생 한 오류 코드가 표시 됩니다. 이 보고서는 전자 메일 배달 문제를 해결할 수 있도록 Ndr의 세부 정보를 표시 합니다.

![보안 & 준수 센터의 메일 흐름 대시보드의 배달 못 함 보고서 위젯](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>배달 못 함 보고서에 대 한 보고서 보기

**배달 못 함 보고서** 위젯을 클릭 하면 **배달 못 함 보고서**로 이동 합니다.

기본적으로 모든 오류 코드에 대 한 활동이 표시 됩니다. **데이터 표시**를 클릭 하면 드롭다운에서 특정 오류 코드를 선택할 수 있습니다.

차트의 특정 날짜에 특정 색 (오류 코드)을 가리키면 해당 오류에 대 한 총 메시지 수가 표시 됩니다.

![허용 되지 않는 도메인 보고서의 보고서 보기](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>배달 못 함 보고서에 대 한 세부 정보 테이블 보기

보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.

- **날짜**
- **배달 못 함 보고서 코드**
- **개수**
- **예제 메시지**: 영향을 받는 메시지의 예제 메시지 id입니다.

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

특정 날짜 범위에 대 한 보고서를 한 명 이상의 받는 사람에 게 전자 메일로 전송 하려면 **다운로드 요청**을 클릭 합니다.

테이블에서 행을 선택 하면 다음 정보와 함께 플라이 아웃이 나타납니다.

- **날짜**
- **배달 못 함 보고서 코드**: 링크를 클릭 하 여 특정 오류 코드에 대 한 원인 및 솔루션에 대 한 자세한 정보를 확인할 수 있습니다.
- **개수**
- **예제 메시지**: **예제 메시지 보기** 를 클릭 하 여 영향을 받는 메시지의 예제에 대 한 [메시지 추적](message-trace-scc.md) 결과를 볼 수 있습니다.

![배달 못 함 보고서의 세부 정보 테이블 보기에서 행을 선택한 후의 세부 정보 플라이 아웃](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.

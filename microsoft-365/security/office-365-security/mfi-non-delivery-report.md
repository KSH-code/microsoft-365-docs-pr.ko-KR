---
title: 메일 흐름 대시보드의 배달되지 않은 보고서
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에서 배달되지 않는 세부 정보 보고서를 사용하여 조직의 보낸 사람으로부터 배달되지 않는 보고서(NDR 또는 반송 메시지라고도 알려)에서 가장 자주 발생하는 오류 코드를 모니터링하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 00efa42dbe9f3ca119d407c74d3711d99d6c0d5c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154389"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>보안 및 준수 센터의 배달 & 보고서

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

보안  & 준수 센터의 메일 흐름 [](https://protection.office.com) 대시보드에 있는 배달되지 않은 보고서에는 조직의 사용자에 대해 배달되지 않는 보고서(NDR 또는 반송 메시지라고도 알려)에서 가장 많이 발생하는 오류 코드가 표시됩니다. [](mail-flow-insights-v2.md) 이 보고서에는 전자 메일 배달 문제를 해결할 수 있도록 NDRS의 세부 정보가 표시되어 있습니다.

![보안 및 준수 센터의 메일 흐름 대시보드에서 배달 & 위젯입니다.](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>배달되지 않은 보고서에 대한 보고서 보기

배달하지 **않는** 보고서 위젯을 클릭하면 배달 수 없는 **보고서로 전송됩니다.**

기본적으로 모든 오류 코드에 대한 활동이 표시됩니다. 에 대한 **데이터 표시를** 클릭하면 드롭다운에서 특정 오류 코드를 선택할 수 있습니다.

차트에서 특정 일에 특정 색(오류 코드)을 마우스로 마우스로 대면 오류에 대한 총 메시지 수가 표시됩니다.

![허용되지 않는 도메인 보고서의 보고서 보기입니다.](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>배달되지 않은 보고서에 대한 세부 정보 테이블 보기

보고서 보기에서 **세부** 정보 표 보기를 클릭하면 다음 정보가 표시됩니다.

- **날짜**
- **배달되지 않는 보고서 코드**
- **개수**
- **샘플 메시지:** 영향을 받는 메시지 샘플의 메시지 ID입니다.

세부 정보 테이블 보기에서 **필터를** 클릭하면 시작 날짜  및 종료 날짜로 날짜 범위를 **지정할 수 있습니다.**

특정 날짜 범위에 대한 보고서를 한명 이상의 받는 사람에게 전자 메일로 보내려면 다운로드 **요청을 클릭합니다.**

표에서 행을 선택하면 다음과 같은 정보가 있는 플라이아웃이 나타납니다.

- **날짜**
- **배달 못 한 보고서 코드:** 링크를 클릭하여 특정 오류 코드의 원인 및 해결 방법과 원인에 대한 자세한 정보를 찾을 수 있습니다.
- **개수**
- **샘플 메시지:** 샘플  메시지 보기를 클릭하여 [](message-trace-scc.md) 영향을 받는 메시지의 샘플에 대한 메시지 추적 결과를 볼 수 있습니다.

![세부 정보 테이블 보기에서 배달하지 않는 보고서의 행을 선택한 후 플라이아웃에 대한 세부 정보입니다.](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)

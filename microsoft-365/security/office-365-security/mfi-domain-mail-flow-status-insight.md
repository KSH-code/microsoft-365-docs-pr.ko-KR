---
title: 메일 흐름 대시보드의 최상위 도메인 메일 흐름 상태 정보
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
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 최상위 도메인 메일 흐름 상태 정보를 사용하여 MX 레코드와 & 메일 흐름 문제를 해결하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4ed59e31cd21826eebf306e566610d54635f0c4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174210"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>보안 및 준수 센터의 & 메일 흐름 상태 정보

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

보안 **및** 준수 센터의 [](mail-flow-insights-v2.md) 메일 흐름 대시보드에서 최상위 도메인 & 상태 [정보를](https://protection.office.com) 통해 조직의 현재 메일 흐름 상태를 확인할 수 있습니다.

이 인사이트는 메일 흐름 문제가 발생하는 도메인을 식별하고 ***문제를 해결하는 데 도움이*** 됩니다. 예를 들어 도메인이 만료되었거나 도메인에 잘못된 MX 레코드가 있기 때문에 도메인에서 외부 전자 메일을 받을 수 없습니다.

![보안 및 준수 센터의 메일 흐름 대시보드에 있는 & 흐름 상태 위젯입니다.](../../media/mfi-top-domain-mail-flow-status-widget.png)

위젯에서 **세부 정보** 보기를 클릭하면  각 도메인의 상태에 대한 자세한 정보가 표시하는 도메인 상태 플라이아웃이 나타납니다.

- **도메인**
- **이전 MX 레코드**
- **현재 MX 레코드**
- **전자 메일 수신 상태**
- **도메인 상태:** 녹색 확인 표시는 위젯을 클릭할 때 현재 MX 레코드가 레코드에 있는 값과 일치하고 도메인이 지난 2시간 동안 전자 메일을 수신한 경우를 나타냅니다.

  빨간색 X는 MX 레코드가 변경되고 도메인이 지난 6시간 동안 전자 메일을 받지 않은 경우를 나타냅니다. 이는 도메인이 만료되었거나 MX 레코드가 잘못 업데이트된 것일 수 있습니다. 도메인 등록 기관 또는 DNS 호스팅 서비스에 확인하여 도메인이 만료되었거나 도메인의 MX 레코드가 올바르지 않은지 확인할 수 있습니다.

더 보기를 **클릭하여** 더 많은 도메인에 대한 동일한 정보를 볼 수 있습니다.

![최상위 도메인 메일 흐름 상태 정보의 플라이아웃 세부 정보](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)

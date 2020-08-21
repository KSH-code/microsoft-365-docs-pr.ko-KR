---
title: 메일 흐름 대시보드의 아웃바운드 및 인바운드 메일 흐름 분석
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 관리자는 보안 그룹 준수 센터의 메일 흐름 대시보드에서 아웃바운드 및 인바운드 메일 흐름 정보에 대해 알아& 있습니다.
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826896"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>보안 센터의 아웃바운드 및 인바운드 & 흐름

보안 **& 준수 센터의 메일 흐름** 대시보드에서의 아웃바운드 및 인바운드 메일 흐름 인사이트는 커넥터 [보고서의](view-mail-flow-reports.md#connector-report) 정보와 이전 TLS 개요 보고서의 **정보를 한 위치에** 통합합니다. [Mail flow dashboard](mail-flow-insights-v2.md)

위리에는 조직으로 메시지를 배달하고 조직에서 메시지를 배달할 때 연결에 사용되는 TLS 암호화가 표시됩니다. 다른 전자 메일 서비스에서 설정하는 연결은 TLS에서 모두 제공하는 연결에 의해 암호화됩니다. 위장은 메일 흐름의 지난 주에 대한 스냅숏을 제공합니다.

![준수 센터의 보안 흐름 대시보드에서 아웃바운드 및 인바운드 & 위예로 인바운드 및 인바운드 메일 흐름 위유](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

위리수의 정보는 Microsoft 365의 커넥터 및 TLS 메시지 보호와 관련되어 있습니다. 자세한 내용은 아래 항목을 참조하세요.

- [커넥터를 사용하여 메일 흐름 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online에서 전자 메일 연결 보안을 위해 TLS를 사용하는 방법](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Microsoft 365의 암호화에 대한 기술 관련 세부 정보](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>전송 중 보호된 메시지(TLS에 의해)

위의 **보기를 클릭하면** **TLS로** 보호되는 메시지 플라이아웃에 TLS(조직으로 들어오고 나가는 메시지) 에지 가로채기가 나타납니다.

![전송 중으로 보호되는 메시지는 아웃바운드 및 인바운드 전자 메일 위와 같이 표시됩니다.](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

현재 TLS 1.2는 Microsoft 365에서 제공하는 가장 안전한 TLS 버전입니다. 종종 규정 준수 감사에 사용되는 TLS 암호화를 알고야 합니다. 대부분의 원본 및 대상 전자 메일 서버와 직접적인 관계가 없는 경우(이를 소유하지 않을 것이며 Microsoft에서는 아무것도 제공하지 않음) 이러한 서버에서 사용되는 TLS 암호화를 개선할 수 있는 많은 옵션이 없습니다.

그렇지만 커넥터를 [사용하여 전자 메일 서버와](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) Microsoft 365 간에 전송되는 메시지에 대해 최적의 TLS 보호를 사용할 수 있도록 할 수 있습니다. Microsoft 365와 자체 전자 메일 서버 또는 파트너에 속한 자체 전자 메일 서버 간의 메일 흐름은 일반 메시지보다 훨씬 중요하고 민감한 경우가 므로 추가 보안과 보안을 해당 메시지에 적용하는 것이 좋습니다.

사용자 고유의 전자 메일 서버를 업그레이드하거나 수정하여 사용 중이될 TLS 암호화를 개선하거나 파트너에게 도달하여 동일한 작업을 수행할 수 있습니다. 커넥터 **보고서에는** Microsoft 365 커넥터를 사용하는 메시지에 대한 메일 흐름 볼륨과 TLS 암호화가 모두 표시됩니다.

커넥터 보고서 **링크를 클릭하여** 커넥터 보고서로 이동할 [수 있습니다.](view-mail-flow-reports.md#connector-report) 연결된 조건이 검색되면 커넥터 보고서 페이지에서 다음 **정보를** 사용할 수 있습니다.

- **중요한 TLS1.0 메일 흐름이 표시되는 인바운드 파트너 커넥터**
- **중요한 TLS1.0 메일 흐름이 표시된 인바운드 온-프레미스 커넥터**

TLS 1.0 연결의 경우, Microsoft 365에서 더 이상 TLS 1.0 지원이 더 이상 사용되지 않는 경우 발생하는 문제를 피하려면 실제로 전자 메일 서버 또는 파트너의 서버를 업그레이드하거나 수정해야 합니다.

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)

---
title: 메일 흐름 대시보드의 아웃바운드 및 인바운드 메일 흐름 인사이트
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 아웃바운드 및 인바운드 메일 흐름 & 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071231"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>보안 및 준수 센터의 아웃바운드 및 & 흐름 정보

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Security  & Compliance [Center의](https://protection.office.com) 메일 [](mail-flow-insights-v2.md) 흐름 대시보드에 있는 아웃바운드 및 인바운드 [](view-mail-flow-reports.md#connector-report) 메일 흐름 인사이트는 커넥터 보고서와 이전 **TLS** 개요 보고서의 정보를 한 장소에 결합합니다.

위젯에는 조직과 메시지를 배달할 때 연결에 사용되는 TLS 암호화가 표시됩니다. 다른 전자 메일 서비스와 설정한 연결은 양측에서 TLS를 제공하는 경우 TLS로 암호화됩니다. 위젯은 메일 흐름의 마지막 주에 대한 스냅숏을 제공합니다.

![보안 및 준수 센터의 메일 흐름 대시보드에 있는 아웃바운드 & 및 인바운드 메일 흐름 위젯](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

위젯의 정보는 Microsoft 365의 커넥터 및 TLS 메시지 보호와 관련이 있습니다. 자세한 내용은 다음 항목을 참조하세요.

- [커넥터를 사용하여 메일 흐름 구성](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Office 365의 전자 메일 연결 보안을 위해 Exchange Online에서 TLS를 사용하는 방법](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Microsoft 365의 암호화에 대한 기술 참조 세부 정보](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>전송 중(TLS로 보호된 메시지)

위젯에서  세부 정보 보기를 클릭하면 **TLS(전송** 중 메시지 보호) 플라이아웃에 조직에서 들어오고 나가는 메시지에 대한 TLS 보호가 표시됩니다.

![아웃바운드 및 인바운드 전자 메일 위젯에서 세부 정보 보기를 클릭한 후 나타나는 전송 중(TLS로 보호된 메시지) 플라이아웃](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

현재 TLS 1.2는 Microsoft 365에서 제공하는 가장 안전한 버전의 TLS입니다. 준수 감사에 사용되는 TLS 암호화를 알아야 하는 경우가 종종 있습니다. 대부분의 원본 및 대상 전자 메일 서버와 직접적인 관계가 없는 것일 수 있으므로(소유하지도 아니고 Microsoft도 해당 서버와는 관계가 없습니다). 따라서 이러한 서버에서 사용되는 TLS 암호화를 개선할 수 있는 옵션이 많지 않습니다.

그러나 커넥터를 [](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 사용하여 전자 메일 서버와 Microsoft 365 간에 전송되는 메시지에 대해 사용 가능한 최상의 TLS 보호를 보장할 수 있습니다. Microsoft 365와 파트너에 속한 자체 전자 메일 서버 또는 서버 간의 메일 흐름은 보통 일반 메시지보다 더 중요하고 민감하기 때문에 이러한 메시지에 보안 및 보안 강화를 적용하는 것이 좋습니다.

사용되고 있는 TLS 암호화를 개선하기 위해 자체 전자 메일 서버를 업그레이드하거나 수정하거나 파트너에게 연락하여 동일한 작업을 할 수 있습니다. 커넥터 **보고서에는** Microsoft 365 커넥터를 사용하는 메시지에 대한 메일 흐름 볼륨과 TLS 암호화가 모두 표시됩니다.

커넥터 보고서 **링크를** 클릭하여 커넥터 [보고서로 이동하면 됩니다.](view-mail-flow-reports.md#connector-report) 연결된 조건이 검색된 경우  커넥터 보고서 페이지에서 다음 정보를 사용할 수 있습니다.

- **중요한 TLS1.0 메일 흐름이 있는 인바운드 파트너 커넥터**
- **인바운드 OnPremises 커넥터에 중요한 TLS1.0 메일 흐름이 표시**

TLS 1.0 연결의 경우 Microsoft 365에서 TLS 1.0 지원이 더 이상 사용되지 않는 경우 문제를 방지하려면 실제로 전자 메일 서버 또는 파트너의 서버를 업그레이드하거나 수정해야 합니다.

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
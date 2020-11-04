---
title: 메일 흐름 대시보드의 아웃 바운드 및 인바운드 메일 흐름 이해
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에 있는 아웃 바운드 및 인바운드 메일 흐름에 대해 알아볼 수 있습니다.
ms.openlocfilehash: cff7c3a14b62475903729f4528652f192c2da09f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877672"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>보안 & 준수 센터의 아웃 바운드 및 인바운드 메일 흐름 이해

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Security & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드에](mail-flow-insights-v2.md) 있는 **아웃 바운드 및 인바운드 메일 흐름** 에 대 한 정보는 [커넥터 보고서](view-mail-flow-reports.md#connector-report) 와 이전 **TLS 개요 보고서** 의 정보가 한 곳에 결합 됩니다.

위젯은 조직에서 메시지를 배달할 때 연결에 사용 되는 TLS 암호화를 표시 합니다. 두 쪽에서 모두 TLS를 제공 하는 경우 다른 전자 메일 서비스와 함께 설정 되는 연결은 TLS에 의해 암호화 됩니다. 이 위젯은 메일 흐름의 마지막 주에 대 한 스냅숏을 제공 합니다.

![보안 & 준수 센터의 메일 흐름 대시보드의 아웃 바운드 및 인바운드 메일 흐름 위젯](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

위젯의 정보는 커넥터 및 Microsoft 365의 TLS 메시지 보호와 관련이 있습니다. 자세한 내용은 다음 항목을 참조 하십시오.

- [커넥터를 사용 하 여 메일 흐름 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online이 TLS를 사용 하 여 전자 메일 연결을 보호 하는 방법](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Microsoft 365의 암호화에 대 한 기술 참조 세부 정보](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>메시지가 전송 중에 보호 됨 (TLS에서)

위젯에 대 한 **세부 정보 보기** 를 클릭 하면 **전송 (TLS에서) 플라이 아웃에서 보호 된 메시지가** 조직에 들어오고 나가는 메시지에 대 한 TLS 보호 기능을 표시 합니다.

![아웃 바운드 및 인바운드 전자 메일 위젯에 대 한 세부 정보 보기를 클릭 하면 표시 되는 전송 (TLS에 의해) 플라이 아웃을 통해 보호 된 메시지](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

현재 TLS 1.2은 Microsoft 365에서 제공 하는 가장 안전한 버전의 TLS입니다. 준수 감사에 사용 되는 TLS 암호화를 알아야 하는 경우가 많습니다. 대부분의 원본 및 대상 전자 메일 서버 (사용자가 소유 하지 않으며 Microsoft는 사용 하지 않음)와 직접 관계가 없을 수도 있으므로 이러한 서버에서 사용한 TLS 암호화를 향상 시킬 수 있는 여러 옵션이 없습니다.

그러나 [커넥터](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 를 사용 하 여 전자 메일 서버와 Microsoft 365 간에 전송 되는 메시지에 대 한 최선의 사용 가능 TLS 보호를 보장할 수 있습니다. Microsoft 365와 자체 전자 메일 서버 또는 파트너에 속하는 서버 간의 메일 흐름은 일반적으로 일반 메시지 보다 중요 하 고 중요 하며 이러한 메시지에는 추가 보안 및 감시를 적용 하는 것이 좋습니다.

자체 전자 메일 서버를 업그레이드 하거나 수정 하 여 사용 중인 TLS 암호화를 개선 하거나, 파트너에 게 연락 하 여 동일한 작업을 수행 하도록 할 수 있습니다. **커넥터 보고서** 에는 Microsoft 365 커넥터를 사용 하는 메시지에 대 한 메일 흐름 볼륨과 TLS 암호화가 모두 표시 됩니다.

**커넥터 보고서** 링크를 클릭 하 여 [커넥터 보고서](view-mail-flow-reports.md#connector-report)로 이동할 수 있습니다. 연결 된 조건이 검색 된 경우 **커넥터 보고서** 페이지에서 다음 정보를 확인할 수 있습니다.

- **인바운드 파트너 커넥터 중요 TLS 1.0 메일 흐름 보기**
- **인바운드 OnPremises 커넥터 중요 TLS 1.0 메일 흐름 보기**

TLS 1.0 연결의 경우 Microsoft 365에서 TLS 1.0 지원이 더 이상 사용 되지 않는 경우 문제를 방지 하기 위해 전자 메일 서버 또는 파트너의 서버를 업그레이드 하거나 수정 해야 합니다.

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.

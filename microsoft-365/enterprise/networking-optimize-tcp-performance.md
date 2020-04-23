---
title: 5단계 - 클라이언트 Microsoft 365 서비스 성능 최적화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 성능 향상을 위해 TCP 설정 및 Microsoft 365 서비스를 구성합니다.
ms.openlocfilehash: 2db35f67ff19998b8a70742ec8fa24cb8d517c5d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631468"
---
# <a name="step-5-optimize-client-and-microsoft-365-service-performance"></a>5단계 - 클라이언트 Microsoft 365 서비스 성능 최적화

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![1단계-네트워킹](../media/deploy-foundation-infrastructure/networking_icon-small.png)

클라이언트 장치와 Microsoft 365 서비스 간에 TCP(전송 제어 프로토콜)가 작동하는 방식을 세밀하게 조정하여 성능을 개선할 수 있습니다.

클라이언트 장치의 경우 클라이언트 장치에서 다음 TCP 설정을 변경하여 TCP 성능을 최적화할 수 있습니다.

- [TCP 창 배율](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/) - 클라이언트 장치에서 승인을 받지 않아도 추가 데이터를 보낼 수 있도록 변경합니다.
- [TCP 유휴 시간](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/) - 클라이언트 장치에서 열려 있는 연결을 보다 효율적으로 처리할 수 있도록 변경합니다.
- [TCP 최대 세그먼트 크기](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/) - 클라이언트 장치에서 패킷 데이터의 최대 블록을 보낼 수 있도록 변경합니다.
- [TCP 선택적 승인](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/) - 클라이언트 장치에서 받은 데이터를 보다 효율적으로 승인할 수 있도록 변경합니다.

Microsoft 365 서비스의 경우 다음 추가 리소스를 참조하여 성능을 최적화하세요.

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [비즈니스용 Skype Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Online의 Project Web App](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step5)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

[네트워킹 인프라 종료 조건](networking-exit-criteria.md)

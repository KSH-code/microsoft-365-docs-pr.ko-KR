---
title: '5단계: 클라이언트 Office 365 서비스 성능 최적화'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 성능 향상을 위해 TCP 설정 및 Office 365 서비스를 구성합니다.
ms.openlocfilehash: 40f99f1b50a324af0650382de165dcfd3df97b0c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869925"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>5단계: 클라이언트 Office 365 서비스 성능 최적화

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

클라이언트 장치와 Office 365 서비스 간에 TCP(전송 제어 프로토콜)가 작동하는 방식을 세밀하게 조정하여 성능을 개선 수 있습니다.

클라이언트 장치의 경우 클라이언트 장치에서 다음 TCP 설정을 변경하여 TCP 성능을 최적화할 수 있습니다.

- [TCP 창 배율](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/) - 클라이언트 장치에서 승인을 받지 않아도 추가 데이터를 보낼 수 있도록 변경합니다.
- [TCP 유휴 시간](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/) - 클라이언트 장치에서 열려 있는 연결을 보다 효율적으로 처리할 수 있도록 변경합니다.
- [TCP 최대 세그먼트 크기](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/) - 클라이언트 장치에서 패킷 데이터의 최대 블록을 보낼 수 있도록 변경합니다.
- [TCP 선택적 승인](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/) - 클라이언트 장치에서 받은 데이터를 보다 효율적으로 승인할 수 있도록 변경합니다.

Office 365 서비스의 경우 다음 추가 리소스를 참조하여 성능을 최적화하세요.

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [비즈니스용 Skype Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step5)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

[네트워킹 인프라 종료 조건](networking-exit-criteria.md)

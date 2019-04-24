---
title: '4단계: URL 및 IP 주소 변경 계획'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291327"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>4단계: URL 및 IP 주소 변경 계획

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>이 단계를 수행하려면 먼저 [3단계](networking-configure-proxies-firewalls.md)를 완료해야 합니다. 3단계를 수행하지 않은 경우 [5단계](networking-optimize-tcp-performance.md)로 건너뛸 수 있습니다.
>

전역 Microsoft 365 네트워크에서 사용하는 URL 및 IP 주소는 시간에 따라 변경되므로 이러한 끝점에 대한 업데이트를 계획해야 합니다. 예를 들어 다음을 사용하여 보안 경계 장치를 다시 구성해야 할 수 있습니다.

- 방해 없는 처리가 필요한 새로운 서비스에 대한 새 URL
- 중단된 서비스에 대한 URL 제거
- 인터넷상의 새로운 Microsoft 네트워크 위치 및 서버에 대한 새 IP 주소 범위 
- 다양한 서비스에 대한 IP 주소 범위 변경

끝점 변경 구현 계획을 수립하는 방법에 대한 자세한 내용은 [Office 365 끝점 관리 - 통합](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) 및 [Office 365 끝점 관리 - 프록시](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)를 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step4)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[클라이언트 및 Office 365 서비스 성능 최적화](networking-optimize-tcp-performance.md)|

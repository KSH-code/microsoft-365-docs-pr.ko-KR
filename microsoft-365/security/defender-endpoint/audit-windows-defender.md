---
title: 감사 모드에서 끝점용 Microsoft Defender 기능이 어떻게 작동 하는지 테스트
description: 감사 모드를 사용하면 끝점용 Microsoft Defender가 디바이스를 사용하도록 설정한 경우 어떻게 보호하는지 볼 수 있습니다.
keywords: exploit guard, 감사, 감사, 모드, 사용, 비활성화, 테스트, 데모, 평가, 랩
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075391"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>감사 모드에서 끝점용 Microsoft Defender 기능이 어떻게 작동 하는지 테스트

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


감사 모드에서 공격 표면 감소 규칙, 악용 보호, 네트워크 보호 및 제어된 폴더 액세스를 사용하도록 설정할 수 있습니다. 감사 모드를 사용하면 기능을 사용하도록  설정한 경우 어떤 일이 일어나는지 기록을 볼 수 있습니다.

조직에서 기능이 어떻게 작동할지 테스트할 때 감사 모드를 사용하도록 설정할 수 있습니다. 이렇게 하면 업무용 앱이 영향을 받지 않는지 확인하게 됩니다. 또한 특정 기간 동안 의심스러운 파일 수정 시도의 수를 알 수 있습니다.

이 기능은 앱, 스크립트 또는 파일이 수정되는 것을 차단하거나 차단하지 않습니다. 그러나 Windows 이벤트 로그는 기능이 완전히 활성화된 것 같은 이벤트를 기록합니다. 감사 모드를 사용하면 이벤트 로그를 검토하여 기능이 활성화된 경우 기능에 미칠 영향을 볼 수 있습니다.

감사된 항목을 찾으면 Applications **and Services**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational으로 이동하십시오.**

끝점용 Defender를 사용하여 각 이벤트, 특히 공격 표면 감소 규칙을 조사하는 데 더 많은 세부 정보를 얻을 수 있습니다. Endpoint용 Defender 콘솔을 사용하면 경고 타임라인 및 조사 시나리오의 일부로 문제를 [조사할 수 있습니다.](investigate-alerts.md)

그룹 정책, PowerShell 및 CSP(구성 서비스 공급자)를 사용하여 감사 모드를 사용하도록 설정할 수 있습니다.

> [!TIP]
> 또한 Windows Defender Testground 웹 사이트를 방문하여 [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 작동을 확인하고 작동 방법을 확인할 수 있습니다.

 **감사 옵션** | **감사 모드를 사용하도록 설정하는 방법** | **이벤트를 보는 방법**
|---------|---------|---------|
| 감사는 모든 이벤트에 적용됩니다. | [제어된 폴더 액세스 사용](enable-controlled-folders.md) | [제어된 폴더 액세스 이벤트](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| 감사는 개별 규칙에 적용됩니다. | [공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md) | [공격 표면 감소 규칙 이벤트](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| 감사는 모든 이벤트에 적용됩니다. | [네트워크 보호 사용](enable-network-protection.md) | [네트워크 보호 이벤트](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| 감사는 개별 완화에 적용됩니다. | [Exploit Protection 사용](enable-exploit-protection.md) | [Exploit Protection 이벤트](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>관련 항목

* [악용으로부터 장치 보호](exploit-protection.md)
* [공격 표면 감소 규칙을 사용하여 공격 표면 감소](attack-surface-reduction.md)
* [네트워크 보호](network-protection.md)
* [중요한 폴더 보호](controlled-folders.md)

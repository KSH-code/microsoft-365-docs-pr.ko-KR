---
title: 공격 표면 감소 기능 구성
description: 공격 Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell cmdlet 및 그룹 정책을 사용하여 공격 표면 감소를 구성합니다.
keywords: asr, 공격 표면 감소, windows defender, microsoft defender, 바이러스 백신, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: f604bbee94fc1b3fea7396d7e20266b120388765
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53590986"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>공격 표면 감소 기능 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Endpoint용 Defender에는 여러 공격 표면 감소 기능이 포함되어 있습니다. 자세한 내용은 공격 표면 감소 [기능 개요를 참조하세요.](overview-attack-surface-reduction.md) 사용자 환경에서 공격 표면 감소를 구성하기 위해 다음 단계를 수행합니다.

1. [에 대해](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)하드웨어 기반 Microsoft Edge.

2. 응용 프로그램 제어를 사용하도록 설정

   1. 기본 정책은 Windows. 예제 [기본 정책 을 참조합니다.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)
   2. 응용 [Windows Defender 디자인 가이드를 참조하세요.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)
   3. [WDAC(응용 Windows Defender) 정책 배포를 참조합니다.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)

3. [제어된 폴더 액세스를 사용하도록 설정 .](enable-controlled-folders.md)

4. [네트워크 보호 켜기.](enable-network-protection.md)

5. [Exploit Protection을 사용하도록 설정](enable-exploit-protection.md).

6. [공격 표면 축소 규칙을 구성합니다.](enable-attack-surface-reduction.md)

7. 네트워크 방화벽을 설치합니다.

   1. 고급 보안이 [있는 Windows Defender 방화벽에 대한 개요를 얻습니다.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. 방화벽 Windows Defender 디자인 [가이드를](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) 사용하여 방화벽 정책을 디자인할 방법을 결정할 수 있습니다.
   3. 고급 [Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) 방화벽 배포 가이드를 사용하여 조직의 방화벽을 설정할 수 있습니다.

> [!TIP]
> 대부분의 경우 공격 표면 감소 기능을 구성할 때 다음 여러 방법 중에서 선택할 수 있습니다.

> - Microsoft Endpoint Manager(현재 Microsoft Intune 및 Microsoft Endpoint Configuration Manager)
> - 그룹 정책
> - PowerShell cmdlet

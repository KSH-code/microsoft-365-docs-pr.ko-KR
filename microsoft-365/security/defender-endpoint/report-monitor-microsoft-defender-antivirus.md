---
title: 보호 기능 모니터링 및 Microsoft Defender 바이러스 백신 보고
description: Configuration Manager 또는 SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 보고서를 사용하며 PowerShell 및 WMI를 사용하여 Microsoft Defender AV를 모니터링합니다.
keywords: siem, monitor, report, Microsoft Defender AV
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 34b5718bb80b1af629edcd18ecc6771fc7a0c8f8
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60884040"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에 대한 보고

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 Windows 10, Windows 11, Windows Server 2019, Windows Server 2022 및 Windows Server 2016. Microsoft Defender 바이러스 백신 Microsoft Defender for Endpoint의 차세대 보호 기능입니다. 차세대 보호는 전자 메일, 앱, 클라우드 및 웹에서 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협으로부터 장치를 보호하는 데 도움이 됩니다.

이 Microsoft Defender 바이러스 백신 보호 상태 및 경고를 검토하기 위한 몇 가지 옵션이 있습니다. 전자 메일 알림을 Microsoft Endpoint Manager [모니터링하거나 Microsoft Defender 바이러스 백신](/configmgr/protect/deploy-use/monitor-endpoint-protection) [수 있습니다.](/configmgr/protect/deploy-use/endpoint-configure-alerts) 또는 를 사용하여 보호를 모니터링할 [Microsoft Intune.](/intune/introduction-intune)

타사 SIEM(보안 정보 및 이벤트 관리) 서버가 있는 경우 클라이언트 이벤트 를 사용할 [Windows Defender 있습니다.](/windows/win32/events/windows-events)

Windows 이벤트는 SAM(보안 계정 관리자) 이벤트(보안 계정[](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)관리자) 이벤트(에 대해 [](/windows/device-security/auditing/security-auditing-overview) 향상된 Windows 10 보안 감사 항목 참조) 및 Windows Defender 이벤트를 포함하여 여러 보안 [이벤트 원본으로 구성됩니다.](troubleshoot-microsoft-defender-antivirus.md)

이러한 이벤트는 이벤트 수집기 를 사용하여 중앙에서 Windows [수 있습니다.](/windows/win32/wec/windows-event-collector) 종종 SIEM 서버에는 Windows 대한 커넥터가 있어 SIEM 서버의 모든 보안 이벤트를 상관 관계화할 수 있습니다.

[Log Analytics의 맬웨어](/azure/log-analytics/log-analytics-malware)평가 솔루션을 사용하여 맬웨어 이벤트를 모니터링할 수도 있습니다.

PowerShell, WMI 또는 Microsoft Azure 모니터링 또는 확인은 (배포, 관리 및 보고 옵션 표)를 [참조하세요.](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="see-also"></a>참고 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)

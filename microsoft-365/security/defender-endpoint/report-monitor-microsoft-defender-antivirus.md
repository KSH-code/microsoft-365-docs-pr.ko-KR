---
title: 보호 기능 모니터링 및 Microsoft Defender 바이러스 백신 보고
description: Configuration Manager 또는 SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 보고서를 사용하며 PowerShell 및 WMI를 사용하여 Microsoft Defender AV를 모니터링합니다.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 91891af35def83f21b3db8c7e8fa4b320bef563c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220324"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에 대한 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 Windows 10 Server 2019 및 Windows 기본 제공 Windows Server 2016. Microsoft Defender 바이러스 백신 Microsoft Defender for Endpoint의 차세대 보호 기능입니다. 차세대 보호는 전자 메일, 앱, 클라우드 및 웹에서 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협으로부터 장치를 보호하는 데 도움이 됩니다.

이 Microsoft Defender 바이러스 백신 보호 상태 및 경고를 검토하기 위한 몇 가지 옵션이 있습니다. 전자 메일 알림을 Microsoft Endpoint Manager [모니터링하거나 Microsoft Defender 바이러스 백신](/configmgr/protect/deploy-use/monitor-endpoint-protection) [수 있습니다.](/configmgr/protect/deploy-use/endpoint-configure-alerts) 또는 를 사용하여 보호를 모니터링할 [Microsoft Intune.](/intune/introduction-intune)  

Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite에는 보호 업데이트 및 실시간 보호 설정을 비롯한 주요 Microsoft Defender 바이러스 백신 문제를 보고하는 업데이트 준수 추가 기능도 있습니다.

타사 SIEM(보안 정보 및 이벤트 관리) 서버가 있는 경우 클라이언트 이벤트 를 사용할 [Windows Defender 있습니다.](/windows/win32/events/windows-events) 

Windows 이벤트는 SAM(보안 계정 관리자) 이벤트(보안 계정[](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)관리자) 이벤트(에 대해 [](/windows/device-security/auditing/security-auditing-overview) 향상된 Windows 10 보안 감사 항목 참조) 및 Windows Defender 이벤트를 포함하여 여러 보안 [이벤트 원본으로 구성됩니다.](troubleshoot-microsoft-defender-antivirus.md) 

이러한 이벤트는 이벤트 수집기 를 사용하여 중앙에서 Windows [수 있습니다.](/windows/win32/wec/windows-event-collector) 종종 SIEM 서버에는 Windows 대한 커넥터가 있어 SIEM 서버의 모든 보안 이벤트를 상관 관계화할 수 있습니다. 

[Log Analytics의 맬웨어](/azure/log-analytics/log-analytics-malware)평가 솔루션을 사용하여 맬웨어 이벤트를 모니터링할 수도 있습니다.

PowerShell, WMI 또는 Microsoft Azure 모니터링 또는 확인은 (배포, 관리 및 보고 옵션 표)를 [참조하세요.](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)
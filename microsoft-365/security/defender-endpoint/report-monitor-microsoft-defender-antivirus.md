---
title: Microsoft Defender 바이러스 백신 보호 모니터링 및 보고
description: Configuration Manager 또는 SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 보고서를 사용하며 PowerShell 및 WMI를 사용하여 Microsoft Defender AV를 모니터링합니다.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269591"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에 대한 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신은 Windows 10, Windows Server 2019 및 Windows Server 2016에 기본 제공되어 있습니다. Microsoft Defender 바이러스 백신은 끝점용 Microsoft Defender의 차세대 보호 기능입니다. 차세대 보호는 전자 메일, 앱, 클라우드 및 웹에서 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협으로부터 장치를 보호하는 데 도움이 됩니다.

Microsoft Defender 바이러스 백신을 사용하면 보호 상태 및 경고를 검토할 수 있는 몇 가지 옵션이 있습니다. Microsoft Endpoint Manager를 사용하여 [Microsoft Defender 바이러스 백신을 모니터링하거나](/configmgr/protect/deploy-use/monitor-endpoint-protection) 전자 메일 [경고를 만들 수 있습니다.](/configmgr/protect/deploy-use/endpoint-configure-alerts) 또는 [Microsoft Intune을 사용하여 보호를 모니터링할 수 있습니다.](/intune/introduction-intune)  

Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite에는 보호 업데이트 및 실시간 보호 설정을 포함하여 주요 Microsoft Defender 바이러스 백신 문제를 보고하는 업데이트 준수 추가 기능도 있습니다.

타사 SIEM(보안 정보 및 이벤트 관리) 서버가 있는 경우 클라이언트 이벤트를 Windows Defender [있습니다.](/windows/win32/events/windows-events) 

Windows 이벤트는 SAM(Security Account Manager) 이벤트(Windows[10에](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)대해 향상된 보안 [](/windows/device-security/auditing/security-auditing-overview) 계정 관리자) 및 보안 감사 항목 참조) 및 Windows Defender 이벤트를 포함하여 여러 보안 [이벤트 원본으로 구성됩니다.](troubleshoot-microsoft-defender-antivirus.md) 

이러한 이벤트는 Windows 이벤트 수집기 를 사용하여 [중앙에서 집계할 수 있습니다.](/windows/win32/wec/windows-event-collector) 종종 SIEM 서버에는 Windows 이벤트에 대한 커넥터가 있어 SIEM 서버의 모든 보안 이벤트를 상관 관계화할 수 있습니다. 

[Log Analytics의 맬웨어](/azure/log-analytics/log-analytics-malware)평가 솔루션을 사용하여 맬웨어 이벤트를 모니터링할 수도 있습니다.

PowerShell, WMI 또는 Microsoft Azure의 상태를 모니터링하거나 확인하는 데 대한 자세한 내용은 (배포, 관리 및 보고 [옵션 표)를 참조하세요.](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 바이러스 백신 배포](deploy-manage-report-microsoft-defender-antivirus.md)
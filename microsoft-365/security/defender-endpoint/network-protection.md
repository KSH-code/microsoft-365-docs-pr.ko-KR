---
title: 네트워크 보호를 사용하여 잘못된 사이트에 대한 연결 방지
description: 사용자가 알려진 악성 및 의심스러운 네트워크 주소에 액세스하지 못하게 하여 네트워크 보호
keywords: 네트워크 보호, 악용, 악성 웹 사이트, ip, 도메인, 도메인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection: M365-security-compliance
ms.openlocfilehash: a00fa0c255156f17f579889e8a399c52d126a6f8
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661601"
---
# <a name="protect-your-network"></a>네트워크 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>네트워크 보호 개요

네트워크 보호는 인터넷 기반 이벤트로부터 장치를 보호하는 데 도움이 됩니다. 네트워크 보호는 공격 표면 감소 기능입니다. 이를 통해 직원이 응용 프로그램을 통해 위험한 도메인에 액세스하지 못하게 할 수 있습니다. 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅하는 도메인은 위험으로 간주됩니다. 네트워크 보호는 신뢰도 [Microsoft Defender SmartScreen(도메인](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 또는 호스트 이름 기반)에 연결하려고 하는 모든 아웃바운드 HTTP 트래픽을 차단하기 위해 네트워크 보호 범위를 확장합니다.

네트워크 보호는 웹 보호의 [보호를](web-protection-overview.md) 운영 체제 수준으로 확장합니다. 이 기능은 지원되는 다른 브라우저 및 비 브라우저 응용 프로그램에 Edge의 웹 보호 기능을 제공합니다. 또한 네트워크 보호는 끝점 감지 및 응답과 함께 사용될 경우 IOC(손상 표시기)를 표시하고 [차단합니다.](overview-endpoint-detection-response.md) 예를 들어 네트워크 보호는 [](manage-indicators.md) 특정 도메인 또는 호스트 이름을 차단하는 데 사용할 수 있는 사용자 지정 표시기에서 작동합니다.

> [!TIP]
> 네트워크 보호가 작동하는 방법을 demo.wd.microsoft.com Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) testground 사이트를 참조하세요.

## <a name="requirements-for-network-protection"></a>네트워크 보호 요구 사항

네트워크 보호를 사용하려면 Windows 10 Pro Enterprise 및 Microsoft Defender 바이러스 백신 보호가 필요합니다.

<br>

****

|Windows 버전|Microsoft Defender 바이러스 백신|
|---|---|
|Windows 10 버전 1709 이상 <p> Windows 서버 1803 이상|[Microsoft Defender 바이러스 백신 보호](configure-real-time-protection-microsoft-defender-antivirus.md) 및 클라우드 [제공](enable-cloud-protection-microsoft-defender-antivirus.md) 보호를 사용하도록 설정해야 합니다.|
|

서비스를 사용하도록 설정한 후 서비스와 장치(끝점이라고도 하는) 간의 연결을 허용하도록 네트워크 또는 방화벽을 구성해야 할 수 있습니다.

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>네트워크 보호 구성

네트워크 보호를 사용하도록 설정하는 방법에 대한 자세한 내용은 네트워크 보호 사용 **[을 참조하세요.](enable-network-protection.md)** 그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.

## <a name="viewing-network-protection-events"></a>네트워크 보호 이벤트 보기

네트워크 보호는 Exploit Protection 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 차단하는 [끝점용 Microsoft Defender와](microsoft-defender-endpoint.md) [가장 잘 작동합니다.](investigate-alerts.md)

네트워크 보호가 연결을 차단하면 알림 센터에서 알림이 표시됩니다. 보안 운영 팀은 조직의 [세부](customize-attack-surface-reduction.md#customize-the-notification) 정보 및 연락처 정보로 알림을 사용자 지정할 수 있습니다. 또한 모니터링할 특정 기술에 맞게 개별 공격 표면 감소 규칙을 사용하도록 설정하고 사용자 정의할 수 있습니다.

감사 모드를 [사용하여](audit-windows-defender.md) 네트워크 보호가 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가할 수도 있습니다.

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>사이트 포털에서 네트워크 보호 Microsoft 365 Defender 검토

끝점용 Microsoft Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 [차단합니다.](investigate-alerts.md) 경고 큐의 Microsoft 365 Defender 포털( )에서 또는 고급 헌팅을 사용하여 이러한 세부 정보를 볼 [https://security.microsoft.com](https://security.microsoft.com) [수 있습니다.](advanced-hunting-overview.md) [](review-alerts.md) 감사 모드를 사용하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 네트워크 보호 설정이 사용하도록 설정된 경우 환경에 어떤 영향을 주는지 볼 수 있습니다.

고급 헌팅에 대한 예제 쿼리는 다음과 같습니다.

```kusto
DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked', 'ConnectionSuccess')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>이벤트 뷰어에서 Windows 이벤트 검토

Windows 로그를 검토하여 네트워크 보호가 악성 IP 또는 도메인에 대한 액세스를 차단(또는 감사)할 때 생성되는 이벤트를 볼 수 있습니다.

1. [XML을 직접 복사합니다.](event-views.md)

2. **확인** 을 선택합니다.

이 절차에서는 네트워크 보호와 관련된 다음 이벤트만 표시하기 위해 필터를 지정하는 사용자 지정 보기를 만듭니다.

<br>

****

|이벤트 ID|설명|
|---|---|
|5007|설정이 변경될 때의 이벤트|
|1125|감사 모드에서 네트워크 보호가 발생 하는 경우 이벤트|
|1126|차단 모드에서 네트워크 보호가 발생하면 이벤트|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>네트워크 보호 및 TCP 3차원 핸드세이크

네트워크 보호를 사용하면 [TCP/IP를](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip)통해 3차원 핸드세이크가 완료된 후 사이트에 대한 액세스를 허용할지 또는 차단할지 여부를 결정하게 됩니다. 따라서 사이트가 네트워크 보호에 의해 차단되는 경우 사이트가 실제로 차단된 경우에도 Microsoft 365 Defender 포털에 작업 유형이 `ConnectionSuccess` `NetworkConnectionEvents` 표시될 수 있습니다. `NetworkConnectionEvents` 네트워크 보호가 아닌 TCP 계층에서 보고됩니다. 3차원 핸드세이크가 완료되면 네트워크 보호를 통해 사이트에 대한 액세스가 허용되거나 차단됩니다.

작동 방식의 예는 다음과 같습니다.

1. 사용자가 디바이스의 웹 사이트에 액세스하려고 시도하는 경우를 가정해 가정합니다. 사이트는 위험한 도메인에서 호스팅될 수 있으며 네트워크 보호에 의해 차단됩니다.  

2. TCP/IP를 통한 3차원 핸드세이크 작업이 완료되기 전에 작업이 기록되어 로 `NetworkConnectionEvents` `ActionType` `ConnectionSuccess` 나열됩니다. 그러나 3차원 핸드세이크 프로세스가 완료되는 즉시 네트워크 보호가 사이트에 대한 액세스를 차단합니다. 이 모든 상황이 매우 빠르게 진행됩니다. 와 유사한 프로세스는 [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 3차원 핸드세이크가 완료되면 결정이 완료된 후 사이트에 대한 액세스가 차단되거나 허용됩니다.

3. Microsoft 365 Defender 포털에서 경고가 경고 큐에 [나열됩니다.](alerts-queue.md) 해당 경고의 세부 정보에는 및 를 모두 `NetworkConnectionEvents` `AlertEvents` 포함합니다. ActionType이 인 항목도 있는 경우에도 사이트가 차단된 `NetworkConnectionEvents` `ConnectionSuccess` 것입니다.

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>다중 세션을 Windows 가상 데스크톱에 Windows 10 Enterprise 고려 사항

다중 사용자 특성으로 인해 Windows 10 Enterprise 다음에 유의해야 합니다.

1. 네트워크 보호는 장치 전체 기능으로, 특정 사용자 세션을 대상으로 할 수 없습니다.

2. 웹 콘텐츠 필터링 정책도 장치 전체에 적용됩니다.

3. 사용자 그룹을 구분해야 하는 경우 가상 데스크톱 호스트 풀과 할당을 Windows 만드는 것이 좋습니다.

4. 감사 모드에서 네트워크 보호를 테스트하여 롤아웃하기 전에 해당 동작을 평가합니다.

5. 사용자 수 또는 다중 사용자 세션 수가 많은 경우 배포의 크기 조정을 고려합니다.

### <a name="alternative-option-for-network-protection"></a>네트워크 보호를 위한 대체 옵션

Azure의 Windows 데스크톱에서 사용되는 Windows 10 Enterprise 세션 1909 이상의 경우 다음 방법을 사용하여 Microsoft Edge 네트워크 보호를 사용할 수 있습니다.

1. 네트워크 [보호 켜기 및](enable-network-protection.md) 지침에 따라 정책을 적용합니다.

2. 다음 PowerShell 명령을 실행합니다. `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>네트워크 보호 문제 해결

네트워크 보호가 실행되는 환경으로 인해 Microsoft는 운영 체제 프록시 설정을 검색하지 못하게 될 수 있습니다. 경우에 따라 네트워크 보호 클라이언트가 클라우드 서비스에 연결하지 못할 수 있습니다. 연결 문제를 해결하려면 E5 라이선스가 있는 고객은 다음 레지스트리 키 중 하나를 구성해야 합니다.

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>참고 항목

- [네트워크 보호 |](evaluate-network-protection.md) 기능의 작동 방식과 일반적으로 만들어지게 될 이벤트를 보여줄 수 있는 빠른 시나리오를 진행합니다.
- [네트워크 보호 기능](enable-network-protection.md) | 그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.
- [웹에서 공격 표면 감소 기능 Microsoft Intune](/mem/intune/protect/endpoint-security-asr-policy)

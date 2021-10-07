---
title: 장치 검색에 자주 묻는 질문
description: 장치 검색에 대한 FAQ(질문과 대답)에 대한 답변 찾기
keywords: 장치 검색, 검색, 수동, 사전, 네트워크, 표시 여부, 서버, Workstation, 온보드, 관리되지 않는 장치
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7af22cf31c8ad8cad4640d99737bc359e0ab6d2c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192910"
---
# <a name="device-discovery-frequently-asked-questions"></a>장치 검색에 자주 묻는 질문

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

장치 검색에 대한 FAQ(질문과 대답)에 대한 답변을 제공합니다.

## <a name="what-is-basic-discovery-mode"></a>기본 검색 모드란?
이 모드를 사용하면 모든 끝점용 Microsoft Defender 온보딩 장치에서 네트워크 데이터를 수집하고 인접한 장치를 검색할 수 있습니다. 온보드 엔드포인트는 네트워크에서 수동적으로 이벤트를 수집하고 해당 끝점에서 장치 정보를 추출합니다. 네트워크 트래픽이 시작되지 않습니다. 온보드 엔드포인트는 단순히 온보더된 장치에서 볼 수 있는 모든 네트워크 트래픽에서 데이터를 추출합니다. 네트워크에서 관리되지 않는 장치를 나열하는 데 사용되는 데이터입니다.

## <a name="can-i-disable-basic-discovery"></a>기본 검색을 사용하지 않도록 설정할 수 있나요?
고급 기능 페이지를 통해 장치 검색을 해제할 [수](advanced-features.md) 있습니다. 그러나 네트워크에서 관리되지 않는 장치에 대한 가시성을 잃게 됩니다. 검색이 SenseNDR.exe 관계없이 온보드 장치에서 계속 실행됩니다. 

## <a name="what-is-standard-discovery-mode"></a>표준 검색 모드란?
 이 모드 끝점에서 끝점용 Microsoft Defender에 온보딩된 끝점은 네트워크에서 관찰된 장치를 적극적으로 프로브하여 수집된 데이터를 보강할 수 있습니다(네트워크 트래픽의 미미한 양). 이 모드는 신뢰할 수 있고 뛰어난 장치 인벤토리를 구축하는 데 매우 권장됩니다. 이 모드를 사용하지 않도록 선택하고 기본 검색 모드를 선택하면 네트워크에서 관리되지 않는 끝점만 볼 수 있습니다.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>표준 검색을 수행하는 장치를 제어할 수 있나요?
 표준 검색을 수행하는 데 사용되는 장치 목록을 사용자 지정할 수 있습니다. 이 기능을 지원하는 모든 온보드 디바이스에서 Standard 검색을 사용하도록 설정하거나(현재 Windows 10 장치만 해당) 장치 태그를 지정하여 장치의 하위 집합 또는 하위 집합을 선택할 수 있습니다. 이 경우 다른 모든 장치는 기본 검색만 실행하도록 구성됩니다. 구성은 장치 검색 설정 페이지에서 사용할 수 있습니다.

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>관리되지 않는 장치를 장치 인벤토리 목록에서 제외할 수 있나요?
예, 장치 인벤토리 목록에서 관리되지 않는 장치를 제외하는 필터를 적용할 수 있습니다. API 쿼리의 등록 상태 열을 사용하여 관리되지 않는 장치를 필터링할 수도 있습니다. 


## <a name="which-onboarded-devices-can-perform-discovery"></a>검색을 수행할 수 있는 온보드 장치는 무엇입니까?
 Windows 10 버전 1809 이상에서 실행되는 온보드 장치는 검색을 수행할 수 있습니다. 이때 서버가 검색을 수행할 수 없습니다.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>온보드 장치가 홈 네트워크 또는 공용 액세스 지점에 연결되어 있는 경우 어떻게 하나요?
 검색 엔진은 회사 네트워크에서 수신되는 네트워크 이벤트와 회사 네트워크 외부에서 수신되는 네트워크 이벤트를 구분합니다. 모든 테넌트 클라이언트에서 네트워크 식별자를 상호 연결하면 개인 네트워크와 회사 네트워크에서 받은 이벤트 간에 이벤트가 차별화됩니다. 예를 들어 조직의 대부분의 장치가 동일한 기본 게이트웨이와 DHCP 서버 주소를 사용하여 동일한 네트워크 이름에 연결된다고 보고하는 경우 이 네트워크가 회사 네트워크일 가능성이 높다고 가정할 수 있습니다. 개인 네트워크 장치는 인벤토리에 나열되지 않을 뿐만 아니라 적극적으로 프로브되지 않습니다.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>어떤 프로토콜을 캡처하고 분석하나요?
 기본적으로 Windows 10 버전 1809 이상에서 실행되는 모든 온보드 장치는 ARP, CDP, DHCP, DHCPv6, IP(헤더), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP(SYN 헤더), UDP(헤더), WSD 프로토콜을 캡처하고 분석합니다.

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>표준 검색에서 활성 프로비전에 어떤 프로토콜을 사용하나요?
 장치가 표준 검색을 실행하도록 구성된 경우 노출된 서비스는 ARP, FTP, HTTP, HTTPS, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL, RPC, mDNS, DHCP, AFP, CrestonCIP, IphoneSync, WinRM, VNC, SLP

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>표준 검색을 사용하여 대상이 프로브되지 못하게 제외하는 방법
 네트워크에 적극적으로 프로브하지 말아야 하는 장치가 있는 경우 제외 목록을 정의하여 검사하지 못하게 할 수도 있습니다. 구성은 장치 검색 설정 페이지에서 사용할 수 있습니다.

## <a name="can-i-exclude-devices-from-being-discovered"></a>장치가 검색되지 못하게 제외할 수 있나요?
 장치 검색에서는 수동 방법을 사용하여 네트워크에서 장치를 검색할 때 회사 네트워크의 온보드 장치와 통신하는 모든 장치를 검색하여 인벤토리에 나열할 수 있습니다. 장치를 활성 프로비전에서만 제외할 수 있습니다.

## <a name="how-frequent-is-the-active-probing"></a>활성 프로비전은 얼마나 자주 하나요?
 기존 정보가 최신 상태(일반적으로 3주 동안 한 번 프로브되지는 않는다)를 확인하여 장치 특성의 변경이 관찰될 때 장치가 적극적으로 프로브됩니다.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>보안 도구에서 시작된 UnicastScanner.ps1 포트 검색 활동에 대해 경고가 발생했습니다. 어떻게 해야 합니까?
 활성 프로비전 스크립트는 Microsoft에서 서명하며 안전합니다. 제외 목록에 다음 경로를 추가할 수 있습니다. `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps1`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Standard 검색 활성 프로브에서 생성되는 트래픽의 양은 무엇입니까?
 활성 프로비전은 모든 프로비전 시도 시 온보드 장치와 프로브 장치 간에 최대 50Kb의 트래픽을 생성할 수 있습니다.

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>장치 인벤토리에 "온보드할 수 있는" 장치와 대시보드 타일의 "온보더할 장치" 수가 불일치하는 이유는 무엇입니까?
장치 인벤토리의 "온보딩할 수 있습니다." 아래에 나열된 장치 수, "끝점용 Microsoft Defender에 온보딩" 보안 권장 및 "온보딩할 장치" 대시보드 위젯의 수가 다를 수 있습니다.

 보안 권장 및 대시보드 위젯은 네트워크에서 안정된 디바이스에 사용됩니다. 비정기 장치, 게스트 장치 및 기타 제외 이 아이디어는 조직의 전체 보안 점수를 의미하는 영구 장치에 권장하는 것입니다.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>찾은 관리되지 않는 장치를 온보드할 수 있나요?
 예. 네트워크에서 관리되지 않는 끝점은 네트워크에 취약성 및 위험을 도입합니다. 서비스를 온보더링하면 서비스에 대한 보안 가시성을 강화할 수 있습니다. 

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>관리되지 않는 장치 상태는 항상 "활성"입니다. 그 이유는 무엇입니까?
일시적으로 관리되지 않는 장치 상태는 실제 상태와 관계없이 장치 인벤토리의 표준 보존 기간 동안 "활성"입니다.


## <a name="does-standard-discovery-look-like-malicious-network-activity"></a>표준 검색은 악성 네트워크 활동처럼 보이나요?
표준 검색을 고려할 때 프로비전의 의미와 특히 보안 도구에서 이러한 활동이 악의적인 것으로 의심할 수 있는지 궁금할 수 있습니다. 다음 하위 섹션에서는 거의 모든 경우에 조직에서 표준 검색 사용에 대해 걱정할 것이 없는 이유를 설명합니다.  

### <a name="probing-is-distributed-across-all-windows-devices-on-the-network"></a>Probing은 네트워크의 모든 Windows 디바이스에 배포됩니다.
일반적으로 소수의 손상된 장치에서 전체 네트워크를 검색하는 악의적인 활동과는 반대로, 끝점의 Standard 검색 프로비전에 대한 Microsoft Defender는 온보딩된 모든 Windows 장치에서 시작되어 활동이 양성 및 변이적이지 않습니다. 프로비전은 네트워크에서 지원되는 모든 온보드 장치 간의 프로비전 시도의 균형을 조정하기 위해 클라우드에서 중앙에서 관리됩니다.  

### <a name="active-probing-generates-negligible-amount-of-extra-traffic"></a>활성 프로비전은 무시할 수 있는 양의 추가 트래픽을 생성합니다.
관리되지 않는 장치는 일반적으로 3주 동안 한 번만 프로브가 생성되고 50KB 미만의 트래픽이 생성됩니다. 악의적인 활동은 일반적으로 반복적인 높은 차단 시도와 경우에 따라 네트워크 모니터링 도구에서 변칙으로 식별될 수 있는 상당한 양의 네트워크 트래픽을 생성하는 데이터 유출을 포함합니다. 

### <a name="your-windows-device-already-runs-active-discovery"></a>사용자 Windows 이미 활성 검색을 실행하고 있습니다.
네트워크의 끝점 간에 보다 쉬운 "플러그 앤 플레이" 환경과 파일 공유를 위해 Windows 장치, 끝점 및 프린터를 찾기 위해 활성 검색 기능이 Windows 운영 체제에 포함되어 있습니다. 모바일 장치, 네트워크 장비 및 인벤토리 응용 프로그램에서는 몇 가지 이름을 지정하기 위해 유사한 기능이 구현됩니다.  

표준 검색에서는 동일한 검색 방법을 사용하여 디바이스를 식별하고 네트워크의 모든 디바이스에 대한 통합된 Microsoft 365 Defender 있습니다. 예를 들어 표준 검색은 네트워크에서 사용 가능한 프린터를 나열하는 Windows 네트워크의 가까운 끝점을 식별합니다. 

네트워크 보안 및 모니터링 도구는 네트워크의 장치에서 수행한 활동과는 관대합니다. 

### <a name="only-unmanaged-devices-are-being-probed"></a>관리되지 않는 장치만 프로브되고 있습니다.
장치 검색 기능은 네트워크에서 관리되지 않는 장치만 검색하고 식별하기 위해 구축되었습니다. 즉, 끝점용 Microsoft Defender로 이미 온보딩된 이전에 검색된 디바이스는 프로브되지 않습니다. 

### <a name="you-can-exclude-network-lures-from-active-probing"></a>활성 프로비전에서 네트워크 Lures를 제외할 수 있습니다.
표준 검색은 활성 프로비전에서 장치 또는 범위(서브넷)를 제외할 수 있습니다. 네트워크 Lures가 배포된 경우 장치 검색 설정을 사용하여 IP 주소 또는 서브넷(IP 주소 범위)에 따라 제외를 정의할 수 있습니다. 이러한 제외를 정의하면 이러한 디바이스가 적극적으로 프로브되지 않도록 하여 경고가 표시되지 않습니다. 이러한 디바이스는 수동 메서드만 사용하여 검색됩니다(기본 검색 모드와 유사).

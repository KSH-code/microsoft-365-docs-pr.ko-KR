---
title: 위협 방지(Windows 10)
description: 엔드포인트용 Microsoft Defender는 예방적 보호, 침해 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다.
keywords: 위협 방지, 끝점용 Microsoft Defender, 공격 표면 감소, 차세대 보호, 끝점 감지 및 대응, 자동화된 조사 및 대응, Microsoft 위협 전문가, 장치용 Microsoft 보안 점수, 고급 헌팅, 사이버 위협 헌팅, 웹 위협 방지
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 6ada32650a01f3303a9c3c9011f5465dab5f5184
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206880"
---
# <a name="threat-protection"></a>위협 방지

[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)는 예방적 보호, 침해 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. Endpoint용 Defender는 사이버 위협으로부터 끝점을 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하며, 보안 입장을 개선합니다.

> [!TIP]
> 사용자가 클라우드 서비스 및 사내 응용 프로그램에 쉽게 액세스할 수 있도록 지원하고 모든 장치에 대한 최신 관리 기능을 사용할 수 있습니다. 자세한 내용은 원격 인력 [보호를 참조하세요.](/enterprise-mobility-security/remote-work/) 

<center><h2>엔드포인트용 Microsoft Defender</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>위협 & 취약성 관리</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>공격 표면 감소</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>차세대 보호</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>엔드포인트 감지 및 대응</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>자동 조사 및 수정</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft 위협 전문가</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>중앙 집중식 구성 및 관리, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4obJq]

**[위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)**<br>
이 기본 제공 기능은 엔드포인트 취약성 및 잘못된 구성의 발견, 우선 순위 지정 및 수정에 판도를 바꾸는 위험 기반 접근 방식을 사용합니다.

- [위협 & 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [시작](tvm-prerequisites.md)
- [보안 설정 액세스](tvm-dashboard-insights.md)
- [보안 자세 개선 및 위험 감소](tvm-security-recommendation.md)
- [장치의 취약성 이해](tvm-software-inventory.md)

<a name="asr"></a>

**[공격 표면 감소](overview-attack-surface-reduction.md)**<br>
공격 표면 감소 기능 집합은 스택의 첫 번째 방어 선을 제공합니다. 구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되었는지 확인하여 이러한 기능 집합은 공격 및 악용을 저항합니다.

- [하드웨어 기반의 고리](overview-hardware-based-isolation.md)
- [응용 프로그램 제어](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [장치 제어](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [악용 방지](exploit-protection.md)
- [네트워크 보호,](network-protection.md) [웹 보호](web-protection-overview.md)
- [제어된 폴더 액세스](controlled-folders.md)
- [네트워크 방화벽](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [공격 표면 감소 규칙](attack-surface-reduction.md)

<a name="ngp"></a>

**[차세대 보호](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
네트워크의 보안 경계를 더욱 강화하기 위해 엔드포인트용 Microsoft Defender는 모든 유형의 새로운 위협을 포착하도록 설계된 차세대 보호 기능을 사용합니다.

- [동작 모니터링](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [클라우드 기반 보호](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [기계 학습](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL 보호](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [자동화된 샌드박스 서비스](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[엔드포인트 감지 및 대응](overview-endpoint-detection-response.md)**<br>
끝점 감지 및 대응 기능은 침입 시도 및 활성 위반을 감지, 조사 및 대응하기 위해 사용됩니다. 고급 헌팅을 사용하면 위반을 사전 예방적으로 찾고 사용자 지정 검색을 만들 수 있는 쿼리 기반 위협 헌팅 도구가 있습니다.

- [경고](alerts-queue.md)
- [기록 끝점 데이터](investigate-machines.md#timeline)
- [응답 오케스트레이션](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [포렌식 컬렉션](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [위협 인텔리전스](threat-indicator-concepts.md)
- [고급 검색 및 분석 서비스](respond-file-alerts.md#deep-analysis)
- [지능형 헌팅](advanced-hunting-overview.md)
    - [사용자 지정 검색](overview-custom-detections.md)

<a name="ai"></a>

**[자동 조사 및 수정](automated-investigations.md)**<br>
Microsoft Defender for Endpoint는 고급 공격에 빠르게 대응할 뿐만 아니라 대규모로 경고 볼륨을 분당 줄이는 데 도움이 되는 자동 조사 및 수정 기능을 제공합니다.

- [자동 조사 및 수정](automated-investigations.md)
- [자동화된 조사의 세부 정보 및 결과 보기](auto-investigation-action-center.md)
- [수정 조치 보기 및 승인](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft 위협 전문가](microsoft-threat-experts.md)**<br>
끝점용 Microsoft Defender의 새로운 관리되는 위협 헌팅 서비스는 사전 헌팅, 우선 순위 지정 및 추가 컨텍스트 및 인사이트를 제공합니다. Microsoft 위협 전문가 SOC(보안 운영 센터)를 통해 위협을 빠르고 정확하게 식별하고 대응할 수 있습니다.

- [대상 공격 알림](microsoft-threat-experts.md)
- [전문가가 요구하는 경우](microsoft-threat-experts.md)
- [관리 Microsoft 365 Defender 헌팅 서비스 구성](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[중앙 집중식 구성 및 관리, API](management-apis.md)**<br>
엔드포인트용 Microsoft Defender를 기존 워크플로에 통합합니다.
- [온보딩](onboard-configure.md)
- [API 및 SIEM 통합](configure-siem.md)
- [노출된 API](apis-intro.md)
- [역할 기반 액세스 컨트롤(RBAC)](rbac.md)
- [보고 및 추세](threat-protection-reports.md)

<a name="integration"></a>
**[Microsoft 솔루션과의 통합](threat-protection-integration.md)** <br>
 끝점용 Microsoft Defender는 다음을 비롯한 다양한 Microsoft 솔루션과 직접 통합됩니다.
- Intune
- Office 365용 Microsoft Defender
- ID용 Microsoft Defender
- Azure Defender
- 비즈니스용 Skype
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Microsoft 365 Defender Microsoft Defender for Endpoint 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 구성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다.

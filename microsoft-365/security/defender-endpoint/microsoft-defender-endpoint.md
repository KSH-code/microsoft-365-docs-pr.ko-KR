---
title: 끝점용 Microsoft Defender
description: 끝점용 Microsoft Defender는 고급 영구 위협을 방어하는 데 도움이 되는 엔터프라이즈 끝점 보안 플랫폼입니다.
keywords: 끝점용 Microsoft Defender 소개, Microsoft Defender Advanced Threat Protection 소개, 끝점용 Microsoft Defender 소개, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 컴퓨터 동작 센서, 클라우드 보안, 분석, 위협 인텔리전스, 공격 표면 감소, 차세대 보호, 자동화된 조사 및 수정, Microsoft 위협 전문가, 보안 점수, 고급 헌팅, Microsoft 위협 방지, 사이버 위협 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: adc7d780c1af73d8cb4fe229720ac2ed74f90251
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861830"
---
# <a name="microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Windows 10 Enterprise Edition 기능에 대한 자세한 내용은 [Windows 10 Enterprise Edition 을 참조하세요.](https://www.microsoft.com/WindowsForBusiness/buy)

끝점용 Microsoft Defender는 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하도록 설계된 엔터프라이즈 끝점 보안 플랫폼입니다.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Endpoint용 Defender는 Windows 10에 기본 제공되는 다음과 같은 기술 조합과 Microsoft의 강력한 클라우드 서비스를 사용 합니다.

-   **끝점** 동작 센서: Windows 10에 포함된 이러한 센서는 운영 체제에서 동작 신호를 수집하고 처리하고 이 센서 데이터를 끝점용 Microsoft Defender의 격리된 개인 클라우드 인스턴스로 전송합니다.


-   **클라우드 보안 분석:** Windows 에코시스템, 엔터프라이즈 클라우드 제품(예: Office 365) 및 온라인 자산에서 빅 데이터, 장치 학습 및 고유한 Microsoft 광학을 활용하여 행동 신호를 고급 위협에 대한 인사이트, 탐지 및 권장 대응으로 변환합니다.

-   **위협** 인텔리전스: Microsoft 헌터, 보안 팀에서 생성하고 파트너가 제공하는 위협 인텔리전스를 통해 위협 인텔리전스를 통해 엔드포인트용 Defender가 공격자 도구, 기술 및 절차를 식별하고 수집된 센서 데이터에서 관찰될 때 경고를 생성할 수 있습니다.

<center><h2>끝점용 Microsoft Defender</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>위협 & 취약성 관리</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>공격 표면 감소</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>차세대 보호</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>끝점 검색 및 응답</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>자동화된 조사 및 수정</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 위협 전문가</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>중앙 집중식 구성 및 관리, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 위협 방지</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Endpoint용 Defender의 최신 향상된 기능: [끝점용 Microsoft Defender의 새로운 기능에 대해 자세히 알아보습니다.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
> - Endpoint용 Microsoft Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 입증했습니다. 읽기: [MITRE ATT의 인사이트&CK 기반 평가.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

<a name="tvm"></a>

**[위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)**<br>
이 기본 제공 기능은 게임이 변화하는 위험 기반 접근 방식을 사용하여 끝점 취약성 및 잘못 구성을 검색, 우선 순위 지정 및 수정합니다. 

<a name="asr"></a>

**[공격 표면 감소](overview-attack-surface-reduction.md)**<br>
공격 표면 감소 기능 집합은 스택의 첫 번째 방어 라인을 제공합니다. 구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되었는지 확인하여 공격 및 악용을 저항합니다. 이 기능 집합에는 [악성](network-protection.md) IP [](web-protection-overview.md)주소, 도메인 및 URL에 대한 액세스를 규제하는 네트워크 보호 및 웹 보호도 포함됩니다. 

<a name="ngp"></a>

**[차세대 보호](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
네트워크의 보안 경계를 더욱 강화하기 위해 끝점용 Microsoft Defender는 모든 유형의 새로운 위협을 감지하도록 설계된 차세대 보호를 사용했습니다.

<a name="edr"></a>

**[엔드포인트 검색 및 대응](overview-endpoint-detection-response.md)**<br>
끝점 감지 및 대응 기능은 처음 두 보안 기조를 지난 고급 위협을 감지, 조사 및 대응하기 위해 사용됩니다. [고급 헌팅은](advanced-hunting-overview.md) 위반을 사전 예방적으로 찾고 사용자 지정 검색을 만들 수 있는 쿼리 기반 위협 헌팅 도구를 제공합니다.

<a name="ai"></a>

**[자동화된 조사 및 수정](automated-investigations.md)**<br>
엔드포인트용 Microsoft Defender는 고급 공격에 신속하게 대응할 수 있는 기능과 함께 대규모로 경고 볼륨을 분당 줄이는 데 도움이 되는 자동 조사 및 수정 기능을 제공합니다. 

<a name="ss"></a>

**[장치용 Microsoft Secure Score](tvm-microsoft-secure-score-devices.md)**<br>

Endpoint용 Defender에는 엔터프라이즈 네트워크의 보안 상태를 동적으로 평가하고 보호되지 않는 시스템을 식별하고 조직의 전반적인 보안을 향상시키는 권장 조치를 취하는 데 도움이 되는 장치에 대한 Microsoft 보안 점수가 포함되어 있습니다.

<a name="mte"></a>

**[Microsoft 위협 전문가](microsoft-threat-experts.md)**<br>
Endpoint용 Microsoft Defender for Endpoint의 새로운 관리되는 위협 헌팅 서비스는 사전 헌팅, 우선 순위 지정 및 추가 컨텍스트 및 정보를 제공하여 SOC(보안 운영 센터)가 위협을 빠르고 정확하게 식별하고 대응할 수 있도록 합니다.

>[!IMPORTANT]
>끝점용 Defender 고객은 Microsoft 위협 전문가 관리 위협 헌팅 서비스를 신청하여 사전 대상 공격 알림을 받고 필요할 때 전문가와 공동 작업을 해야 합니다. 전문가가 추가 기능 서비스입니다. 대상 공격 알림은 Microsoft 위협 전문가 관리 위협 헌팅 서비스에 수락된 후 항상 포함됩니다.<p>
><p>아직 등록하지 않았고 해당 이점을 경험하고자 <b></b> > <b></b> > <b></b> 하는 경우 설정 일반 고급 기능 > <b>Microsoft 위협</b> 전문가로 이동하여 적용할 수 있습니다. 일단 수락되면 대상 공격 알림의 이점을 얻을 수 있으며, 90일의 전문가 평가판을 시작할 수 있습니다. Microsoft 담당자에게 문의하여 전체 전문가 관련 전문가 구독을 받을 수 있습니다.

<a name="apis"></a>

**[중앙 집중식 구성 및 관리, API](management-apis.md)**<br>
끝점용 Microsoft Defender를 기존 워크플로에 통합합니다.

<a name="mtp"></a>

**[Microsoft 솔루션과의 통합](threat-protection-integration.md)** <br>
Endpoint용 Defender는 다음을 비롯한 다양한 Microsoft 솔루션과 직접 통합됩니다.
- Azure Security Center
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- ID용 Microsoft Defender
- Microsoft Defender for Office
- 비즈니스용 Skype

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Microsoft 365 Defender를 통해 Endpoint용 Defender 및 다양한 Microsoft 보안 솔루션은 기본적으로 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 형성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다.


## <a name="related-topic"></a>관련 항목
[Microsoft Defender for Endpoint는 정교한 위협을 감지하는 데 도움이 됩니다.](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)

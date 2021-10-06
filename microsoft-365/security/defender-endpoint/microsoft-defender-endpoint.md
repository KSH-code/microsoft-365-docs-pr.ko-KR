---
title: 엔드포인트용 Microsoft Defender
description: 엔드포인트용 Microsoft Defender는 지능형 지속적 위협으로부터 방어하는 데 도움이 되는 엔터프라이즈 끝점 보안 플랫폼입니다.
keywords: 엔드포인트용 Microsoft Defender 소개, 엔드포인트용 Microsoft Defender 소개, 사이버 보안, 지능형 지속적 위협, 엔터프라이즈 보안, 컴퓨터 동작 센서, 클라우드 보안, 분석, 위협 인텔리전스, 공격 표면 감소, 차세대 보호, 자동화된 조사 및 수정, Microsoft 위협 전문가, 보안 점수, 고급 헌팅, Microsoft 365 Defender, 사이버 위협 헌팅
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Priority
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e87c13b8d5b4afe2dc14664b680900f7b30b3d02
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124556"
---
# <a name="microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

엔드포인트용 Microsoft Defender는 엔터프라이즈 네트워크가 지능형 위협을 방지, 감지, 조사 및 대응할 수 있도록 설계된 엔터프라이즈 엔드포인트 보안 플랫폼입니다.

> [!TIP]
> 곧 엔드포인트용 Microsoft Defender가 두 가지 플랜으로 제공될 예정입니다. 이 문서에서는 엔드포인트용 Microsoft Defender 플랜 2에 포함된 기능에 대해 설명합니다. [엔드포인트용 Microsoft Defender 플랜 1(미리 보기) 및 플랜 2](defender-endpoint-plan-1-2.md)에 대해 자세히 알아봅니다.
> 

<p><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

엔드포인트용 Microsoft Defender는 Windows 10 및 Microsoft의 강력한 클라우드 서비스에 기본 제공되는 다음과 같은 기술 조합을 사용합니다.

- **엔드포인트 동작 센서**: Windows 10에 포함된 이 센서는 운영체제에서 동작 신호를 수집 및 처리하고 이 센서 데이터를 엔드포인트용 Microsoft Defender의 격리된 프라이빗 클라우드 인스턴스로 보냅니다.

- **클라우드 보안 분석**. 빅데이터, 장치 학습 및 Windows 생태계 전반의 Microsoft 광학, 엔터프라이즈 클라우드 제품(Office 365 등) 및 온라인 자산을 활용하여 행태 신호를 고급 위협에 대한 정보, 감지 그리고 권장 대응 조치로 전환합니다.

- **위협 인텔리전스**. Microsoft 헌터 및 보안 팀이 생성하고 파트너가 제공하는 위협 인텔리전스로 강화된 위협 인텔리전스는 엔드포인트용 Microsoft Defender를 사용하여 공격자의 도구, 기술 및 절차를 식별하고 수집된 센서 데이터가 관찰되면 경고를 생성합니다.

<center><h2>엔드포인트용 Microsoft Defender</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>위협 및 취약성 관리</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>공격 표면 감소</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>차세대 보호</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>엔드포인트 감지 및 대응</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>자동 조사 및 수정</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 위협 전문가</b></a></center></td>
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

<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0]

> [!TIP]
>
> - 엔드포인트용 Microsoft Defender의 최신 개선 사항: [엔드포인트용 Microsoft Defender의 새로운 기능](whats-new-in-microsoft-defender-atp.md)에 대해 알아보세요.
> - 엔드포인트용 Microsoft Defender는 최근 MITRE 평가에서 업계 최고의 광학 및 감지 기능을 시연했습니다. [MITRE ATT&CK 기반 평가 인사이트](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)를 읽어보세요.

<a name="tvm"></a>

**[위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)**

이 기본 제공 기능은 엔드포인트 취약성 및 잘못된 구성의 발견, 우선 순위 지정 및 수정에 판도를 바꾸는 위험 기반 접근 방식을 사용합니다.

<a name="asr"></a>

**[공격 표면 감소](overview-attack-surface-reduction.md)**

공격 표면 감소 기능 집합은 스택의 첫 번째 방어선을 제공합니다. 구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되어 공격과 악용에 저항할 수 있습니다. 이 기능 집합에는 악성 IP 주소, 도메인 및 URL에 대한 액세스를 규제하는 [네트워크 보호](network-protection.md) 및 [웹 보호](web-protection-overview.md)도 포함됩니다.

<a name="ngp"></a>

**[차세대 보호](next-generation-protection.md)**

네트워크의 보안 경계를 더욱 강화하기 위해 엔드포인트용 Microsoft Defender는 모든 유형의 새로운 위협을 포착하도록 설계된 차세대 보호 기능을 사용합니다.

<a name="edr"></a>

**[엔드포인트 감지 및 대응](overview-endpoint-detection-response.md)**

엔드포인트 탐지 및 대응 기능은 처음 두 가지 보안 기둥을 통과했을 수 있는 지능형 위협을 탐지, 조사 및 대응하기 위해 배치됩니다. [고급 헌팅](advanced-hunting-overview.md)은 침해를 사전에 찾고 맞춤 탐지를 생성할 수 있는 쿼리 기반 위협 헌팅 도구를 제공합니다.

<a name="ai"></a>

**[자동 조사 및 수정](automated-investigations.md)**

지능형 공격에 신속하게 대응할 수 있는 기능과 더불어 엔드포인트용 Microsoft Defender는 규모에 따라 몇 분 만에 경고 볼륨을 줄이는 데 도움이 되는 자동 조사 및 수정 기능을 제공합니다.

<a name="ss"></a>

**[디바이스용 Microsoft Secure Score](tvm-microsoft-secure-score-devices.md)**

엔드포인트용 Microsoft Defender에는 기업 네트워크의 보안 상태를 동적으로 평가하고, 보호되지 않는 시스템을 식별하고, 조직의 전체 보안을 개선하기 위한 권장 조치를 취하는 데 도움이 되는 디바이스용 Microsoft Secure Score가 포함되어 있습니다.

<a name="mte"></a>

**[Microsoft 위협 전문가](microsoft-threat-experts.md)**

엔드포인트용 Microsoft Defender의 새로운 관리형 위협 헌팅 서비스는 사전 예방적 사냥, 우선 순위 지정, 추가 컨텍스트 및 인사이트를 제공하여 보안 운영 센터(SOC)가 위협을 빠르고 정확하게 식별하고 대응할 수 있도록 합니다.

> [!IMPORTANT]
> 엔드포인트용 Microsoft Defender 고객은 Microsoft 위협 전문가 관리형 위협 사냥 서비스를 신청하여 사전 예방적 표적 공격 알림을 받고 필요에 따라 전문가와 협력해야 합니다. Experts on Demand는 추가 기능 서비스입니다. 표적 공격 알림은 Microsoft 위협 전문가가 관리하는 위협 추적 서비스에 동의한 후에 항상 포함됩니다.
>
> 아직 등록하지 않았지만 혜택을 경험하려면 **설정** \> **일반** \> **고급 기능** \> **Microsoft 위협 전문가** 로 이동하여 신청하세요. 수락되고 나면 표적 공격 알림의 혜택을 받고 Experts on Demand의 90일 평가판을 시작할 수 있습니다. 전체 Experts on Demand 구독을 받으려면 Microsoft 담당자에게 문의하세요.

<a name="apis"></a>

**[중앙 집중식 구성 및 관리, API](management-apis.md)**

엔드포인트용 Microsoft Defender를 기존 워크플로에 통합합니다.

<a name="mtp"></a>

**[Microsoft 솔루션과 통합](threat-protection-integration.md)**

엔드포인트용 Microsoft Defender는 다음을 포함한 다양한 Microsoft 솔루션과 직접 통합됩니다.

- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Office 365용 Microsoft Defender
- 비즈니스용 Skype

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**

Microsoft 365 Defender를 통해 엔드포인트용 Microsoft Defender 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 이메일 및 애플리케이션 전반에 기본적으로 통합되어 정교한 공격을 탐지, 방지, 조사하고 자동으로 대응하는 통합된 침해 전후 엔터프라이즈 방어 제품군을 형성합니다.


## <a name="training-for-security-analysts"></a>보안 분석가를 위한 교육

Microsoft Learn의 이 학습 경로를 통해 엔드포인트용 Defender와 조직의 엔드포인트(장치 및 시스템) 전반에서 위협을 예방, 감지, 조사 및 대응하는 데 Defender가 어떻게 도움이 되는지 이해할 수 있습니다.

|교육:|Microsoft 365 Defender를 통한 사이버 공격 감지 및 대응|
|---|---|
|![Microsoft 365 Defender 교육 아이콘입니다.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|엔드포인트용 Defender는 단일 통합 플랫폼에서 취약성 관리, 엔드포인트 보호, 엔드포인트 검색 및 대응, 모바일 위협 방어 및 관리형 서비스를 제공하는 엔드포인트 보안 솔루션입니다.<p> 2시간 25분 - 학습 경로 - 9개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/paths/defender-endpoint-fundamentals/)


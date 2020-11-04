---
title: Microsoft 365에서 네트워크 보안 위협 방지 배포
description: Microsoft 365 E5에서 threat protection services 및 IT 네트워크 보안 기능을 배포 하는 방법을 알아봅니다.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 1bf06c605290dc94f64da6c2aabca3683c234c9a
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906754"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Microsoft 365에서 위협 보호 기능 배포

[맬웨어](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)및 [fileless 위협과](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)같은 복잡 한 고 사이버 공격 일반적으로 발생 합니다. 기업에서는 자신 및 고객을 효과적인 IT 네트워크 보안 기능으로 보호 해야 합니다. 이러한 공격은 금융 woes에 대 한 신뢰 손실, 비즈니스 침입 중단 시간 등 조직에 대 한 주요 문제를 발생 시킬 수 있습니다. 위협 으로부터 보호 하는 것은 중요 하지만 조직의 시간, 노력 및 리소스에 집중할 위치를 결정 하는 것은 어려울 수 있습니다. 

Microsoft 보안 솔루션은 제품 및 서비스에 기본적으로 제공 됩니다. 자동화 및 기계 학습 기능을 통해 적절 한 항목의 주소가 지정 되도록 보안 팀의 부하를 줄일 수 있습니다. Microsoft 네트워크 보안 솔루션의 장점은 [지능형 보안 그래프](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)에서 매일 처리 되는 신호의 trillions를 기반으로 구축 됩니다. Microsoft 365 보안 솔루션에는 전자 메일, 데이터, 장치 및 id를 통해 신호를 함께 제공 하 여 조직에 대 한 고급 위협 요소를 칠하는 솔루션인 [microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)가 포함 되어 있습니다.


이 비디오를 시청하고 배포 프로세스에 대한 개요를 확인하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

이 문서를 위협 보호 솔루션을 구현 하기 위한 가이드로 사용 하십시오.

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5의 위협 보호

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 를 사용 하면 적응, 기본 제공 인텔리전스를 사용 하 여 조직을 보호할 수 있습니다. Microsoft 365 E5의 위협 보호 기능을 사용 하 여 온-프레미스 및 클라우드 환경에서 advanced threat, 손상 된 id 및 악의적인 작업을 검색 하 고 조사할 수 있습니다.

Microsoft 365 E5에서는 위협 보호 기능이 기본적으로 통합 되어 있습니다. 각 기능에서 제공 하는 신호를 통해 위협 감지 및 대응을 위한 전체 기능을 추가할 수 있습니다. 통합 된 기능 집합은 Microsoft 제품이 아닌 제품을 실행 하는 것과 비교 하 여 조직 (특히 다중 국내 조직)에 대 한 최상의 보호를 제공 합니다. 다음 그림에서는이 문서에서 설명 하는 Microsoft 365 E5의 위협 보호 서비스와 기능을 보여 줍니다.

![Microsoft 365 Defender 개요](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Office 365 기능에 대 한 Defender를 배포 하는 즉시 Microsoft 365 Defender를 켜면 신호 및 데이터를 한 곳에 표시할 수 있습니다. 

![Microsoft 365 Defender 대시보드의 개념 그림](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

다음 그림에서는 이러한 개별 기능을 배포 하기 위한 권장 경로를 보여 줍니다. 

![M365 위협 방지 신호](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|솔루션/기능  |설명  |
|---------|---------|
|다단계 인증 및 조건부 액세스     |손상 된 id 및 장치 로부터 보호 합니다. 기초 이기 때문에이 보호로 시작 합니다. 이 지침에서 권장 하는 구성은 필수 구성 요소로 Azure AD Id 보호를 포함 합니다.     |
|ID용 Microsoft Defender     |  온-프레미스 Active Directory를 활용 하는 클라우드 기반 보안 솔루션은 고급 위협, 손상 된 id 및 조직에서 보낸 악의적인 참가자 작업을 식별, 감지 및 조사 하기 위한 신호입니다. Microsoft Defender를 사용 하 여 온-프레미스 및 클라우드 인프라를 보호 하 고, 종속성 이나 필수 구성 요소가 없으므로 즉각적인 혜택을 얻을 수 있으므로 다음에 주력 합니다.       | 
|Microsoft Defender for Office 365     | 전자 메일 메시지, 링크 (Url) 및 공동 작업 도구를 통해 야기 되는 악의적인 위협 으로부터 조직을 보호 합니다. 맬웨어, 피싱, 스푸핑 및 기타 공격 유형에 대 한 보호 변경 제어, incumbent 시스템에서 설정 마이그레이션 및 기타 고려 사항을 배포 하는 데 시간이 오래 걸릴 수 있으므로 Office 365 용 Microsoft Defender를 구성 하는 것이 좋습니다. <br><br>참고: 모든 Office 365 구독 (Exchange Online Protection)에 포함 된 위협 방지 기능을 구성 해야 합니다.       |
|엔드포인트용 Microsoft Defender    | Advanced 위협을 방지, 감지, 조사 및 대응 하는 데 도움이 되는 endpoint protection 플랫폼입니다.  끝점에 대 한 Defender를 배포 하는 데 시간이 오래 걸릴 수 있지만 구성 작업은 다른 기능과 동시에 수행 될 수 있습니다.   |
|Microsoft Cloud App Security     |   검색, 조사 및 거 버 넌 스에 대 한 클라우드 액세스 보안 브로커 Microsoft Cloud App Security를 초기에 사용 하도록 설정 하 여 데이터 및 통찰력 수집을 시작할 수 있습니다. SaaS 앱에 대 한 정보 및 기타 타게 팅 보호를 구현 하려면 계획이 필요 하며 더 많은 시간이 걸릴 수 있습니다.       | 

> [!TIP]
> 여러 보안 팀이 포함 된 조직은 이러한 기능을 동시에 구현할 수 있습니다.

## <a name="deploy-your-threat-protection-solution"></a>위협 방지 솔루션 배포

조직이 최대한 보호 되도록 하려면 다음 단계를 포함 하는 보안 솔루션을 설정 하 고 배포 합니다.

1. [다단계 인증 및 조건부 액세스 정책 설정](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Id에 대 한 Microsoft Defender 구성](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender 켜기](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Office 365에 대 한 Defender 구성](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [끝점에 대 한 Microsoft Defender 구성](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Microsoft Cloud App Security 구성](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [상태 모니터링 및 작업 수행](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [사용자 교육](deploy-threat-protection-configure.md#step-8-train-users)

위협 방지 기능은 동시에 구성할 수 있으므로 서로 다른 서비스를 담당 하는 여러 네트워크 보안 팀이 있는 경우에는 동시에 조직의 보호 기능을 구성할 수 있습니다. 다음 다이어그램에서는 위협 방지 기능을 배포 하기 위한 높은 수준의 프로세스를 보여 줍니다. 

![위협 보호 기능 배포 프로세스](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 

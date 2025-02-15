---
title: Microsoft 365 Enterprise 리소스 계획 - 사이버 보안 아키텍처
description: Microsoft의 사이버 보안 설계자인 Kozeta Garrett의 microsoft Enterprise 아키텍처의 보안 문제를 극복하는 방법을 알아보세요.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: fcbf4ea9d3f43d0ce005265c4c40572ea3f846a4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162065"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>설계자 한 의 관점에서 볼 수 있는 보안 허점을 다분화할 수 있습니다.

이 문서에서 Microsoft의 사이버 보안 [설계자인 Kozeta Garrett는](https://www.linkedin.com/in/kozeta-garrett-53013a6/)기업 조직에서 발생하는 가장 큰 보안 문제를 설명하고 이러한 문제를 해결하기 위한 접근 방법을 권장합니다.

## <a name="about-the-author"></a>만든 이 정보

![Kozeta Garrett 사진.](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

클라우드 보안 설계자 역할을 할 때 여러 조직과 협력하여 Microsoft 365 및 Azure로 마이그레이션하는 고객을 위한 보안 아키텍처를 디자인 및 구현하고, 엔터프라이즈 보안 솔루션을 개발하고, 비즈니스 탄력을 위한 보안 아키텍처와 문화를 혁신하는 데 중점을 두는 전략적 및 기술 지침을 제공했습니다. 내 경험에는 인시던트 감지 및 대응, 맬웨어 분석, 침투 테스트, IT 보안 및 방어 환경 개선 권장이 포함됩니다. 현대화 노력을 포함하여 보안을 비즈니스에 대한 지원으로 이르게 하는 선행 변환에 매우 열정을 가지고 있습니다.

최근 COVID-19 상황에도 불구하고 지난 몇 년 동안 보안 현대화 생각을 채택한 조직이 어떻게 안전한 방식으로 원격으로 계속 작동할 수 있는 좋은 위치에 있는지 가장 만족스러운 일입니다. 안타깝게도 이러한 상황은 이 즉각적인 요구에 부재 중이지 않은 일부 고객에 대한 기상 통화로도 사용되었습니다. 많은 조직에서는 이러한 비정상적인 상황에서 작동할 수 있도록 빠르게 현대화하고 누적된 IT 보안 부채를 해지하고 밤사이 보안 상황을 개선해야 하다는 사실에 인식하고 있습니다.

다행히 Microsoft는 조직이 보안 자세를 빠르게 강화하는 데 도움이 되는 몇 가지 멋진 리소스를 큐레이트했습니다. 이러한 리소스 외에도 이러한 난제들을 해결해나가길 바라서 매일 고객과 직면한 상위 과제를 공유하고자 합니다.

현재 워싱턴 DC의 수도와 가까운 북부 버지니아에 거주하고 있습니다. 실행, 자전거, 운동, 운동 등 모든 형태의 아웃도어 활동과 연습을 좋아합니다. 이들을 막기 위해 많은 식사, 미식가, 여행도 즐길 수 있습니다.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>클라우드 채택 시작 시 보안 팀과 파트너 됩니다.

먼저 조직의 팀이 시작부터 조율하는 것이 얼마나 중요한지 강조할 수 없습니다. 보안 팀은 클라우드 채택 및 디자인 초기 단계에서 중요한 파트너로 수용되어야 합니다. 즉, 보안 팀이 비즈니스에 추가된 기능(예: 보안 모바일 장치의 훌륭한 사용자 환경, 모든 기능 응용 프로그램 또는 제한된 기능의 전자 메일 및 생산성 응용 프로그램 이상으로 회사 데이터에 가치 생성)을 위한 것뿐만 아니라 새 보안 및 이전 보안 문제를 해결하는 데 도움이 되는 저장소, AI 및 컴퓨팅 분석 기능을 활용하기 위해 클라우드 채택에 온보딩하게 됩니다. 보안 팀이 성공하려면 사람(문화), 프로세스(교육) 및 기술을 포함하여 이 전환의 모든 측면을 관리하는 데 포함되어야 합니다. 또한 SOC(보안 운영 센터)의 최신화 및 지속적인 개선에 투자를 의미하기도 합니다. 디지털 변환이 안전하게 수행되도록 보안 전략을 비즈니스 전략 및 환경 추세에 맞게 조정합니다. 이 기능이 잘 수행된 경우 조직은 비즈니스, IT 및 보안 변경을 포함하여 변경 내용에 더 빠르게 적응할 수 있는 기능을 개발합니다.

고객의 방문이 가장 두드러진 것은 운영과 SOC 팀 간의 실제 파트너 관계가 없는 경우입니다. 운영 팀이 클라우드 도입 마감일을 압박하고 요구하는 동안 보안 팀이 포괄적인 보안 전략을 수립하고 계획하기 위해 프로세스 초기에 항상 포함되는 것은 아닙니다. 여기에는 서로 다른 클라우드 구성 요소와 구성 요소를 프레미스에 통합하는 과정이 포함됩니다. 이러한 파트너 관계 부족은 특정 구성 요소에 대한 컨트롤을 구현하기 위해 사일로에서 작업하는 것처럼 보이는 여러 팀으로 이어지며 구현, 문제 해결 및 통합이 더 복잡해집니다.

이러한 요구 사항을 충족하는 고객은 운영 및 거버넌스와 보안 및 위험 관리 팀 간의 좋은 파트너 관계를 통해 하이브리드 클라우드 워크로드를 보호하기 위한 보안 전략과 요구 사항을 재구성합니다. 사이버 보안 거버넌스, 위험 및 규정 준수 요구 사항에 따라 최종 보안 목표와 결과(데이터 보호 및 시스템 및 서비스 가용성)에 집중합니다. 이러한 조직은 운영 및 거버넌스 팀과 SOC 간의 초기 단계 파트너 관계를 개발하며, 이는 보안 디자인 접근 방식에 중요하고 투자 가치를 극대화합니다.

## <a name="build-a-modern-identity-based-security-perimeter"></a>최신(ID 기반) 보안 경계 구축

그런 다음 Zero Trust 아키텍처 접근 방식을 채택합니다. 이는 최신 ID 기반 보안 경계를 구축하는 것부터 시작합니다. 모든 액세스 시도(프레미스 또는 클라우드)가 확인될 때까지 신뢰할 수 없는 것으로 취급되는 보안 아키텍처를 디자인합니다. "절대 신뢰하지 말고 항상 확인"합니다. 이 디자인 방식은 보안 및 생산성을 향상할 뿐만 아니라 사용자가 모든 장치 유형으로 어디에서나 작업할 수 있도록 합니다. 사용자 위험 수준에 Microsoft 365 중요한 리소스에 대한 액세스를 제어하는 동시에 사용자의 ID를 보호하는 데 도움이 되는 정교한 클라우드 컨트롤입니다.

권장되는 구성은 ID 및 장치 액세스 [구성을 참조하세요.](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="transition-security-controls-to-the-cloud"></a>보안 컨트롤을 클라우드로 전환

많은 보안 팀은 여전히 "네트워크 경계 보안"을 유지 관리하고 클라우드 솔루션에 대한 프레미스 보안 도구 및 제어를 "강제"하는 등 모든 프레미스 세계를 위해 구축된 기존 보안 모범 사례를 사용하고 있습니다. 이러한 컨트롤은 클라우드용으로 설계되지 않은 것이고, 비효율적이며, 최신 클라우드 기능의 채택을 방해합니다. 네트워크 경계 보안 접근 방식에 대해 작동되는 프로세스 및 도구는 비효율적이고 클라우드 기능에 방해가 될 수 있으며, 최신 및 자동화된 보안 기능을 활용하는 데는 허용되지 않는 것으로 입증되었습니다.

방어 전략을 클라우드 관리 보호, 자동화된 조사 및 수정, 자동화된 펜 테스트, 보호용 Defender 및 인시던트 분석으로 전환하여 이 Office 365 수 있습니다. 최신 장치 관리 솔루션을 사용하는 고객은 스마트폰, 개인용 컴퓨터, 노트북 또는 태블릿 등 모든 디바이스에서 자동화된 관리, 표준화된 패치, 바이러스 백신, 정책 적용 및 응용 프로그램 보호를 구현했습니다. 따라서 VPN, Microsoft SCCM(Microsoft System Center Configuration Manager 및 Active Directory 그룹 정책이 필요하지 않습니다. 이 정책은 조건부 액세스 정책과 결합되어 강력한 제어 및 가시성을 제공하며 사용자의 운영 위치와 관계없이 리소스에 대한 액세스를 간소화합니다.

## <a name="strive-for-best-together-security-tools"></a>'함께 최상의' 보안 도구에 대한 노력

또 다른 고객이 보안 도구에 대한 '최상의' 접근 방식을 취하고 있는 것으로 볼 수 있습니다. 새로운 보안 요구를 해결하기 위해 '최고의' 지점 솔루션을 지속적으로 계층화하면 엔터프라이즈 보안이 중단됩니다. 최상의 의도를 조차 경우에도 대부분의 환경의 도구는 비용이 너무 많이 들고 복잡해지기 때문에 통합되지 않습니다. 그러면 팀에서 처리할 수 있는 것보다 더 많은 경고가 표시될 때 가시성의 간격이 생성됩니다. 또한 새 도구에서 SecOps 팀을 다시 제약하는 것은 지속적인 과제가 됩니다.

'단순성은 더 낫습니다' 접근 방식도 보안에 사용할 수 있습니다. '최고의 최고의' 도구를 사용하는 대신, 기본적으로 함께 작동하는 도구로 '최상의 함께' 전략을 채택하여 이 허더링을 해결합니다. Microsoft 보안 기능은 응용 프로그램, 사용자 및 클라우드에 걸쳐 있는 통합 위협 방지 기능을 통해 전체 조직을 보호합니다. 통합을 통해 조직은 공격자가 진입하고 공격을 신속하게 해결하여 더 탄력적으로 위험을 줄일 수 있습니다.

## <a name="balance-security-with-functionality"></a>보안과 기능 균형 조정

사이버 보안 배경과 경험이 길기 때문에 가장 안전한 구성부터 시작하여 조직이 운영 및 보안 요구에 따라 보안 구성을 완화할 수 있도록 하는 것이 좋습니다. 그러나 이 경우 기능이 손실되어 사용자 환경이 열악할 수 있습니다. 많은 조직에서 학습한 것 처럼, 보안이 사용자에게 너무 어렵면 관리되지 않는 클라우드 서비스를 사용하는 등 사용자와 함께 작업할 수 있는 방법을 찾을 수 있습니다. 수락하기 어려운 일로, 정교한 기능 보안 균형을 달성해야 하다는 것을 깨달아야 합니다.

사용자가 작업을 완료하는 데 필요한 모든 작업을 수행하게 될 것"을 실현하는 조직은 "섀도 IT 기고자"는 격투할 가치가 없다고 인정합니다. 섀도 IT와 업무에 승인되지 않은 SaaS 응용 프로그램을 사용할 때 IT 직원이 가장 큰 가해자인 것으로 인식하고 있습니다. 억지하지 않고 사용을 장려하고 생성될 수 있는 위험 노출을 완화하는 데 중점을 두기 위해 전략을 전환했습니다. 이러한 조직의 보안 팀은 모든 것이 역방향 프록시 또는 VPN을 통해 차단, 기록 및 전송된다고 주장하지 않습니다. 대신 이러한 보안 팀은 중요한 데이터와 중요한 데이터가 잘못된 당사자 또는 악의적인 앱에 노출되지 못하게 보호하기 위한 노력을 두 번 더 강화합니다. 데이터 무결성을 보호하기 위해 작업합니다. 암호화, 보안 다단계 인증, 자동화된 위험 및 규정 준수, CASB(Cloud App Security Broker) 기능을 비롯한 고급 클라우드 정보 보호 기능을 완전히 활용하고 있으며, 여러 플랫폼에서 보호된 공유를 허용하고 지원하기도 합니다. 섀도 IT를 창의성, 생산성 및 공동 작업으로 전환하여 비즈니스가 경쟁 우위를 확보할 수 있도록 합니다.

## <a name="adopt-a-methodical-approach"></a>방법 채택

산업에 관계없이 여러 조직에서 클라우드 보안을 구현하는 데 겪은 대부분의 문제는 매우 유사합니다. 무엇보다도 특정 기능과 기능에 대한 다양한 문서가 제공되어 있는 반면, 조직 수준에서 해당 기능에 적용되는 기능, 보안 기능이 겹치는 위치 및 기능이 통합되는 방식에 대한 혼란이 있습니다. 또한 기본으로 미리 구성된 보안 기능 및 조직에서 구성해야 하는 보안 기능에 대한 불확실성 수준도 있습니다. 또한 SOC 팀은 안타깝게도 조직이 이미 진행하고 있는 신속한 클라우드 채택 및 디지털 변환을 준비하는 데 필요한 예산 할당에 전체 노출, 교육 또는 예산 할당이 없습니다.

이러한 문제를 쉽게 쉽게 해소할 수 있도록 Microsoft는 보안 전략 및 구현에 대한 시스템적인 접근 방식을 하도록 설계된 몇 가지 리소스를 큐레이터에 추가했습니다.

|리소스   |추가 정보  |
|---------|---------|
|[보안팀의 재택 근무 지원용 최상위 작업](../security/top-security-tasks-for-remote-work.md)      | 대부분 재택근무 인력을 갑자기 지원하고 있는 경우 이 문서는 보안을 빠르게 강화하는 데 도움이 됩니다. 여기에는 라이선스 계획에 따라 권장되는 상위 작업이 포함됩니다.    |
|[Microsoft 365 비즈니스 의사 결정권자에 대한 보안](../security/Microsoft-365-security-for-bdm.md)    | 보다 포괄적인 계획을 세우는 데 시간이 있는 경우 이 문서에는 공격 표면에 따라 우선 순위가 Microsoft 365 권장 사항이 포함되어 있습니다. 라이선스 및 영역(예: ID, 위협 방지 및 모니터링)을 정렬하는 데 사용할 수 있는 스프레드시트와 함께 제공될 수 있습니다.  |
|[Microsoft 보안 아키텍처 권장 사항](/security/compass/compass)    | 보안 설계자인 경우 ID, 네트워킹 및 보안 운영을 포함하여 분야별로 구성한 보안 권장 사항을 확인합니다.   |
|[Microsoft 보안 운영 권장 사항](/security/compass/security-operations-videos-and-decks)|SOC(보안 운영 센터) 설정 및 실행에 대한 Microsoft 권장 사항 학습 |
|[CISO(최고 정보 보안 책임자) 워크숍 교육](/security/ciso-workshop/ciso-workshop)   | 클라우드 보안을 잘 아는 경우 이 일련의 비디오를 놓치지 마세요.        |
|[docs.security.com/security](/security/)    | 보안 전략 및 아키텍처에 대한 Microsoft의 기술 지침입니다.        |
| | |

이러한 모든 리소스는 시작 지점으로 사용 하도록 설계 하 고 조직의 요구에 맞게 조정 됩니다.
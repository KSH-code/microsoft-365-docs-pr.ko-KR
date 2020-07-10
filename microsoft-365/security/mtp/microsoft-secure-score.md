---
title: Microsoft Secure Score
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 보안 환경을 개선 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094801"
---
# <a name="microsoft-secure-score"></a>Microsoft 보안 점수

Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다. 이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.

보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다. Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.

보안 점수가 조직에 도움이 됩니다.  

* 조직의 보안 환경의 현재 상태를 보고 합니다.
* 검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.  
* 벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.

조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다. 이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>작업 방법

권장 되는 보안 기능을 구성 하 고, 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하거나, 대체 문제를 해결 하기 위한 사항이 제공 됩니다. 일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다. 개선 작업 중 하나를 규정 하지 않으려는 경우 위험 또는 남은 위험을 수락 하도록 선택할 수 있습니다.

라이선스에 관계 없이 향상 된 가능한 전체 기능을 제공 하 여 보안 모범 사례를 이해 하 고 점수를 높일 수 있습니다. 절대 보안 상태는 조직이 소유한 제품 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수를 통해 표시 됩니다. 보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.

점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다. 또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.

### <a name="key-scenarios"></a>주요 시나리오

- [현재 점수 확인](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [점수를 사용자와 같은 조직에 비교](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [개선 작업 보기 및 작업 계획 결정](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [조사 하거나 구현 하기 위한 워크플로 시작](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 보안 센터 및 ServiceNow 통합](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>개선 작업의 점수를 획득 하는 방법

각 향상 작업은 10 점 이내에 가치가 있습니다. 대부분은 이진 방식으로 점수가 지정 되며, 새 정책 만들기 또는 특정 설정을 사용 하는 것과 같은 개선 작업을 구현 하는 경우에는 점수가 100% 인 점수를 얻을 수 있습니다. 다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다. 예를 들어, 향상 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 10 점을 확보 하 고 100 명의 총 사용자 50만 보호 하는 경우에는 5 개 점수 (50 protected/100 total * 10 max points = 5 포인트의 부분적인 점수)가 제공 됩니다.

### <a name="products-included-in-secure-score"></a>안전한 점수에 포함 된 제품

현재 Microsoft 365 (Exchange Online 포함), Azure AD, Microsoft Defender ATP, Azure ATP 및 Cloud App Security에 대 한 권장 사항이 있습니다. 다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다. 권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다. 또한 제 3 자 또는 다른 완화 조치로 인 한 향상 작업을 표시할 수도 있습니다.

### <a name="security-defaults"></a>보안 기본값

Microsoft 보안 점수에는 [Azure Active Directory에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업이 업데이트 되었으며, 일반적인 공격에 대 한 미리 구성 된 보안 설정을 사용 하 여 조직을 보다 쉽게 보호할 수 있습니다.

보안 기본값을 설정 하면 다음과 같은 개선 작업에 대 한 전체 점수가 부여 됩니다.

- 모든 사용자가 보안 액세스에 대 한 다단계 인증을 완료할 수 있는지 확인 (9 포인트)
- 관리 역할에 대 한 MFA 필요 (10 포인트)
- 정책을 사용 하 여 레거시 인증을 차단 합니다 (7 포인트).

>[!IMPORTANT]
>보안 기본값에는 "로그인 위험 정책" 및 "사용자 위험 정책" 개선 작업에 비슷한 보안 기능을 제공 하는 보안 기능이 포함 되어 있습니다. 보안 기본값에서 이러한 정책을 설정 하는 대신, 상태를 "대안 완화"로 업데이트 하는 것이 좋습니다.

## <a name="required-permissions"></a>필요한 사용 권한

Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.

### <a name="read-and-write-roles"></a>읽기 및 쓰기 역할

읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다. 또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.

* 전역 관리자
* 보안 관리자
* Exchange 관리자
* SharePoint 관리자
* 계정 관리자

### <a name="read-only-roles"></a>읽기 전용 역할

읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.

* 헬프데스크 관리자
* 사용자 관리자
* 서비스 관리자
* 보안 읽기 권한자
* 보안 운영자
* 전역 읽기 권한자

## <a name="risk-awareness"></a>위험 인식

Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다. 대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다. 보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.

## <a name="whats-new"></a>어떠한 새로운 기능이 있나요? 

Microsoft 보안 점수가 보안 상태를 보다 효율적으로 대표 하도록 하기 위해 몇 가지 사항을 변경 했습니다. 계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md)제공 되는 기능을 참조 하세요.

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Id 보안 점수 및 그래프 API와 호환 되지 않는 문제

최신 버전의 Microsoft 보안 점수에서는 향상 된 점수 매기기 모델이 출시 되었습니다. 이러한 변경으로 인해 보안 환경을 보다 유연 하 고 정확 하 게 확인할 수 있습니다. 그러나 이러한 업데이트는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않습니다.

보안 성과를 식별 하 고 Graph API가 새 점수 매기기 모델을 채택 합니다. 그때까지 고객은 Microsoft 보안 점수, Id 보안 점수 및 그래프 API에서 보고 하는 점수의 차이를 볼 수 있습니다. 이로 인해 불편을 끼쳐 드려서 죄송 하며, 향후 이러한 환경이 더 높은 호환성을 유지 하기 위해 노력 하 고 있습니다.

### <a name="updated-improvement-actions"></a>업데이트 된 개선 작업

- Azure Active Directory 개선 작업 추가 됨
- Azure Advanced Threat Protection 개선 작업 추가
- Microsoft Defender ATP [위협 & 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 보안 권장 사항에 대 한 지원
    - 이제 TVM에서 제공 하는 모든 릴리스된 보안 권장 사항을 사용할 수 있습니다.

### <a name="updated-interface-and-functionality"></a>업데이트 된 인터페이스 및 기능

* CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기
* 점수를 추적 하 고 벤치 마크 위한 새로운 방법
* 점수 재발에 대 한 추적 및 이해 향상
* 개선 작업 필터링, 태그, 검색 및 그룹화
* 점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리
* 더 많은 내용을 확인해 보세요.

### <a name="june-2020"></a>2020년 6월

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 제거 됨

* 공격 표면 축소 규칙 켜기

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 추가

* 하위 프로세스를 만들지 못하도록 Adobe Reader 차단
* 랜 섬 웨어에 대 한 고급 보호 사용
* 모든 Office 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단
* Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 못하도록 차단
* 다운로드 한 실행 가능한 콘텐츠를 실행 하는 JavaScript 또는 VBScript 차단
* 잠재적으로 난독 처리 된 스크립트의 실행 차단
* 전자 메일 클라이언트 및 webmail에서 실행 가능한 콘텐츠 차단
* Office 통신 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단
* 신뢰할 수 없으며 USB에서 실행 되는 서명 되지 않은 프로세스 차단
* WMI 이벤트 구독을 통해 지 속성 차단
* Office 응용 프로그램에서 다른 프로세스에 코드를 주입 하지 못하도록 차단
* 실행 파일이 전파, 연령 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 이상 실행 되지 않도록 차단
* PSExec 및 WMI 명령에서 시작 되는 프로세스 만들기 차단
* Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 자격 증명 가로채기 차단
* Office 매크로에서 Win32 API 호출 차단

## <a name="we-want-to-hear-from-you"></a>사용자의 의견을 듣고 싶습니다.

문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오. 당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.

## <a name="related-resources"></a>관련 리소스

- [보안 환경을 표시 합니다.](microsoft-secure-score-improvement-actions.md)
- [Microsoft 보안 점수 기록 및 목표를 충족 하는 추적](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)

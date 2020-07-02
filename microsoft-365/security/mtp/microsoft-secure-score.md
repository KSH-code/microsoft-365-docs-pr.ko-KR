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
ms.openlocfilehash: 57e18d68f6f33482fec3880b56ccad52c719a6d9
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023406"
---
# <a name="microsoft-secure-score"></a>Microsoft 보안 점수

Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다. 이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.

보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다. Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.

보안 점수가 조직에 도움이 됩니다.  

* 조직의 보안 환경의 현재 상태를 보고 합니다.
* 검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.  
* 벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.

조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다. 이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.

## <a name="how-it-works"></a>작업 방법

권장 되는 보안 기능을 구성 하 고, 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하거나, 대체 문제를 해결 하기 위한 사항이 제공 됩니다. 일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다. 개선 작업 중 하나를 규정 하지 않으려는 경우 위험 또는 남은 위험을 수락 하도록 선택할 수 있습니다.

라이선스에 관계 없이 향상 된 가능한 전체 기능을 제공 하 여 보안 모범 사례를 이해 하 고 점수를 높일 수 있습니다. 절대 보안 상태는 조직이 소유한 제품 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수를 통해 표시 됩니다. 보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.

점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다. 또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.

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

## <a name="gain-visibility-into-your-security-posture"></a>보안 환경을 표시 합니다.

필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.

* Id (Azure AD 계정 & 역할)
* 데이터 (Microsoft Information Protection)
* 장치 ( [구성 점수](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)라고 알려진 MICROSOFT Defender ATP)
* 앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱
* 인프라 (지금은 향상 작업 없음)

>[!NOTE]
>Microsoft 보안 점수가 최근 릴리스에서는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않는 향상 된 점수 매기기 모델이 출시 되었습니다. [자세히 보기](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간의 점수가 분할 되는 방식과 사용할 수 있는 지점을 볼 수 있습니다. 개요 페이지는 또한 전체 점수에 대 한 모든 보기, 벤치 마크 비교를 사용한 보안 점수의 역사적 추세 및 점수를 높이기 위해 수행할 수 있는 향상 작업의 우선 순위를 지정 하는 위치를 제공 합니다.

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="take-action-to-improve-your-score"></a>점수를 개선 하기 위한 조치 수행

**향상 작업** 탭에는 가능한 공격 지를 확인 하는 보안 권장 사항과 함께 해당 상태 (주소, 계획 된 위험, 허용 됨, 제 3 자가 해결 됨, 대안 완화 및 완료 됨)가 함께 표시 됩니다. 모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.  

### <a name="ranking"></a>순서

순위는 달성할 수 있는 남은 점수, 구현 난이도, 사용자 영향 및 복잡도를 기반으로 합니다. 가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.

### <a name="view-improvement-action-details"></a>향상 작업 세부 정보 보기

특정 향상 작업을 선택 하면 전체 페이지 플라이 아웃이 나타납니다.  

![향상 작업 플라이 아웃 예 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *그림 2: 개선 작업 플라이 아웃 예제*

이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.

* **관리** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다. 그런 다음 동작이 가치 있는 점수를 얻게 되며 플라이 아웃 됩니다. 점수는 일반적으로 업데이트 하는 데 약 24 시간이 소요 됩니다.

* **공유** 를 선택 하 여 개선 작업에 대 한 직접 링크를 복사 하거나, 전자 메일, microsoft 팀, Microsoft Planner 또는 ServiceNow와 같은 링크를 공유할 플랫폼을 선택 합니다. ServiceNow를 선택 하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시 되는 변경 티켓을 만들 수 있습니다. 자세한 내용은 [Microsoft 365 보안 센터 및 ServiceNow 통합](tickets.md)을 참조 하세요.

### <a name="choose-an-improvement-action-status"></a>향상 작업 상태 선택

상태를 선택 하 고 향상 작업과 관련 된 메모를 기록 합니다. 선택할 수 있는 동상은 다음과 같습니다.

* **해결 방법** : 개선 작업이 필요한 지를 인식 하 고 미래에 특정 시점에 해결할 계획입니다. 이 상태는 부분적으로 검색 되었지만 완전히 완료 되지 않은 작업에도 적용 됩니다.
* **계획** 됨-개선 작업을 완료 하기 위한 구체적인 계획이 마련 되었습니다.
* **위험 수락** -보안이 항상 유용성과 균형을 유지 해야 하며, 환경에 대 한 모든 권장 사항이 적합 하지는 않습니다. 이 경우 위험 또는 남은 위험을 수락 하 고 개선 작업을 적용 하지 않도록 선택할 수 있습니다. 모든 점수를 제공 하는 것은 아니지만 해당 작업은 개선 작업 목록에 더 이상 표시 되지 않습니다. 언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.
* 타사 응용 프로그램 또는 소프트웨어 또는 내부 도구로 이미 향상 된 기능을 사용 하 여 타사에서 **확인** 하 고 **다른 완화 작업을 통해 해결** 되었습니다. 작업을 수행 하는 점수를 얻게 되므로 점수가 향상 되어 전반적인 보안 환경을 보다 효율적으로 반영할 수 있습니다. 타사 또는 내부 도구가 더 이상 해당 컨트롤을 커버 하지 않으면 다른 상태를 선택할 수 있습니다. 향상 작업이 이러한 상태 중 하나로 표시 되는 경우 Microsoft는 구현의 완성도를 명확 하 게 파악할 수 없습니다.

#### <a name="threat--vulnerability-management-improvement-actions"></a>위협 & 취약성 관리 개선 작업

"장치" 범주의 향상 작업을 수행 하는 경우 상태를 선택할 수 없습니다. 대신 [Microsoft Defender 보안 센터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 의 [tvm (& 취약성 관리) 보안 권장 사항을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 연결 하 여 조치를 취할 것입니다. 선택한 예외 및 작성 한 사유는 해당 포털에만 적용 되며 Microsoft 보안 점수 포털에는 표시 되지 않습니다.

#### <a name="completed-improvement-actions"></a>완료 된 개선 작업

향상 작업에 대 한 가능한 모든 점수를 얻은 후에는 개선 조치에 "완료 됨" 상태가 발생 합니다. 완료 된 개선 작업은 Microsoft 데이터를 통해 확인 되며 상태를 변경할 수 없습니다.

### <a name="assess-information-and-review-user-impact"></a>정보 평가 및 사용자 영향 검토

**살펴보기** 섹션에는 범주, 제품에 대해 보호할 수 있는 공격 및 제품이 설명 되어 있습니다.

**사용자 영향** 에 따라 개선 작업이 실행 되는 경우 사용자에 게 발생할 항목이 표시 되 고, **영향을 받는 사용자** 에 게는이를 표시할 사람이 표시 됩니다.

### <a name="implement-the-improvement-action"></a>개선 작업 구현

**구현** 섹션에서는 다음 단계에 따라 개선 작업을 완료 하기 위한 단계, 개선 작업의 현재 구현 상태 및 자세한 링크를 보여 줍니다.

필수 구성 요소는 개선 작업을 처리 하기 전에 완료 해야 하는 작업 또는 획득 해야 하는 모든 라이선스가 됩니다. 라이선스에 개선 작업을 완료 하 고 해당 라이선스가 필요한 사용자에 게 적용 되었는지 확인 합니다.  

## <a name="track-your-score-history-and-meet-goals"></a>점수 내역 추적 및 목표 달성

**기록** 탭에서 시간에 따른 조직의 점수 그래프를 볼 수 있습니다. 그래프 아래에 선택한 시간 범위에 적용 된 모든 작업 및 결과 점과 범주와 같은 해당 특성의 목록이 표시 됩니다. 날짜 범위를 사용자 지정 하 고 범주별로 필터링 할 수 있습니다.

**메트릭 & 추세** 탭에는 다양 한 그래프와 차트를 통해 추세를 보다 명확 하 게 표시 하 고 목표를 설정할 수 있습니다. 시각화의 전체 페이지에 대 한 날짜 범위를 설정할 수 있습니다. 시각화에는 다음이 포함 됩니다.

* **보안 점수 영역** — 조직의 목표 및 양호한 점수, 양호 및 불량 점수의 범위에 따라 사용자 지정 됩니다.
* **회귀 추세** -구성, 사용자 또는 장치 변경으로 인해 회귀 된 지점에 대 한 시간 표시 막대입니다.  
* **비교 추세** — 조직의 보안 점수가 다른 사람들과 비교 하는 방식입니다. 이 보기에는 비슷한 사용자 수를 갖는 조직의 점수 평균을 나타내는 줄과 설정할 수 있는 custom 비교 보기가 포함 될 수 있습니다.
* **위험 수락 추세** — "위험 수용 됨"으로 표시 된 개선 작업의 시간 표시 막대입니다.
* **점수 변경** -지정 된 날짜 범위에서 이후의 점수 변경과 함께 회귀 됨을 가리킵니다.

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


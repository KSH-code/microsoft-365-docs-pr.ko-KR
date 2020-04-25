---
title: Microsoft Secure Score
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
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
ms.openlocfilehash: 56c3187999d34ac6d84c1b3857053f82bb40b2a9
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804761"
---
# <a name="microsoft-secure-score"></a>Microsoft 보안 점수

Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다. 보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다. Microsoft 365 보안 센터의 중앙 집중식 대시보드를 통해 조직은 Microsoft 365 id, 데이터, 앱, 장치 및 인프라의 보안을 모니터링 하 고 작업할 수 있습니다.

보안 점수가 조직에 도움이 됩니다.

* 조직의 보안 환경의 현재 상태를 보고 합니다.
* 검색, 표시 유형, 지침 및 제어 기능을 제공 하 여 보안 환경을 개선 합니다.  
* 벤치 마크와 비교 하 여 Kpi (핵심 성과 지표)를 설정 합니다.

조직은 메트릭 및 추세의 견고한 시각화, 다른 Microsoft 제품과의 통합, 비슷한 조직과의 점수 비교에 대 한 액세스 권한을 얻습니다. 이 점수는 타사 솔루션에서 권장 작업을 해결 한 경우에도 반영 될 수 있습니다.

또한 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)를 통해 권장 사항 및 점수에 액세스할 수 있습니다. [보안 점수 리소스 종류](https://go.microsoft.com/fwlink/?linkid=2092996)에 대해 자세히 알아봅니다.

## <a name="how-it-works"></a>작동 방식

권장 되는 보안 기능을 구성 하 고, 보고서 보기와 같은 보안 관련 작업을 수행 하거나, 타사 응용 프로그램 또는 소프트웨어를 사용 하 여 개선 작업을 처리 하기 위한 사항이 제공 됩니다. 일부 향상 작업은 완전히 완료 된 경우에만 점수를 제공 하며 일부 장치 또는 사용자에 대해 완료 되 면 일부를 부분 포인트로 지정 합니다.

라이선스에 관계 없이 향상 된 가능한 전체 기능을 제공 하 여 보안 모범 사례를 이해 하 고 점수를 높일 수 있습니다. 절대 보안 상태는 조직이 소유한 제품 라이선스에 관계 없이 동일 하 게 유지 되는 보안 점수를 통해 표시 됩니다. 보안은 유용성과 균형을 유지 해야 하며 모든 권장 사항이 환경에 적합 한 것은 아닙니다.

점수가 실시간으로 업데이트 되어 시각화 및 향상 작업 페이지에 제공 된 정보를 반영 합니다. 또한 보안 점수가 매일 동기화 되어 각 작업에 대 한 시스템 데이터를 수신 합니다.

### <a name="how-improvement-actions-are-scored"></a>개선 작업의 점수를 획득 하는 방법

대부분은 이진 방식으로 점수가 지정 되며, 새 정책 만들기 또는 특정 설정을 사용 하는 것과 같은 개선 작업을 구현 하는 경우에는 점수가 100% 인 점수를 얻을 수 있습니다. 다른 향상 작업의 경우 점수는 전체 구성에 대 한 비율로 제공 됩니다. 예를 들어, 향상 된 작업에 다단계 인증을 사용 하 여 모든 사용자를 보호 하 여 30 점을 제공 하 고 총 사용자 수가 5 100 인 경우, 2 포인트 (5 개의 보호/100 총 * 30 최대 포인트 = 2 포인트)의 부분적인 점수가 부여 됩니다.

### <a name="products-included-in-secure-score"></a>안전한 점수에 포함 된 제품

현재에는 SharePoint Online, Exchange Online, 비즈니스용 OneDrive, Microsoft Information Protection 등, Azure AD 및 Cloud App Security를 포함 하기 위한 권장 사항이 있습니다. Azure ATP 및 Microsoft Defender ATP와 같은 다른 보안 제품에 대 한 권장 사항은 곧 제공 될 예정입니다. 권장 사항은 각 제품과 연결 된 모든 공격 표면을 다루지는 않지만 좋은 기준이 됩니다. 또한 개선 작업을 제 3 자에서 다룬 것으로 표시할 수도 있습니다.

## <a name="required-permissions"></a>필요한 사용 권한

Microsoft 보안 점수에 액세스할 수 있는 권한을 부여 하려면 Azure Active Directory에서 다음 역할 중 하나를 할당 받아야 합니다.

### <a name="read-and-write-roles"></a>읽기 및 쓰기 역할

읽기 및 쓰기 액세스를 사용 하 여 변경을 수행 하 고 보안 점수와 직접 상호 작용할 수 있습니다. 또한 다른 사용자에 게 읽기 전용 액세스 권한을 할당할 수 있습니다.

* 전역 관리자
* 보안 관리자
* Exchange 관리자
* SharePoint 관리자

### <a name="read-only-roles"></a>읽기 전용 역할

읽기 전용 액세스 권한을 사용 하면 향상 작업에 대 한 상태나 메모를 편집 하거나, 점수 영역을 편집 하거나, 사용자 지정 비교를 편집할 수 없습니다.

* 헬프데스크 관리자
* 사용자 관리자
* 서비스 관리자
* 보안 읽기 권한자
* 보안 운영자
* 전역 읽기 권한자

### <a name="graph-api"></a>Graph API

그래프 API에 액세스 하려면 역할 외에 다음 범위 중 하나를 사용 해야 합니다.

* SecurityEvents. All (읽기 전용 역할의 경우)
* SecurityEvents. All (read 및 write role 용)

## <a name="gain-visibility-into-your-security-posture"></a>보안 환경을 표시 합니다.

필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.

* Id (Azure AD 계정 & 역할)
* 데이터 (Microsoft Information Protection)
* 장치 (지금 향상 작업 없음)
* 앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱
* 인프라 (지금은 향상 작업 없음)

Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간의 점수가 분할 되는 방식과 사용할 수 있는 지점을 볼 수 있습니다. 개요 페이지는 또한 전체 점수에 대 한 모든 보기, 벤치 마크 비교를 사용한 보안 점수의 역사적 추세 및 점수를 높이기 위해 수행할 수 있는 향상 작업의 우선 순위를 지정 하는 위치를 제공 합니다.

![보안 점수 홈페이지](../../media/secure-score/homepage-original.png)
*그림 1: Microsoft 보안 점수 개요 페이지*

## <a name="take-action-to-improve-your-score"></a>점수를 개선 하기 위한 조치 수행

향상 작업 탭에는 가능한 공격 표면을 해당 상태 (완료 됨, 완료 되지 않음, 타사를 통해 확인 및 무시 됨)와 함께 표시 되는 보안 권장 사항이 나열 되어 있습니다. 모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.

### <a name="ranking"></a>순서

순위는 달성할 수 있는 남은 점수, 구현 난이도, 사용자 영향 및 복잡도를 기반으로 합니다. 가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.

### <a name="actions"></a>작업

Microsoft 보안 점수에 의해 [점수 없음] 레이블이 지정 된 작업은 추적 되지 않습니다. 계속 해 서 작업을 수행할 수는 있지만 작업이 완료 되 면 점수에 영향을 주지 않습니다. 향후 Microsoft 보안 점수에 따라 작업이 추적 되 고 이미 완료 된 경우 보안 점수가 자동으로 변경 됩니다.

특정 개선 작업을 선택 하면 플라이 아웃이 나타납니다. 이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.

1. **설정 보기** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다. 그리고 나 서 플라이 아웃 위쪽에 표시 되는 작업의 점수를 얻을 수 있습니다. 점수를 업데이트 하는 데 최대 24 시간이 걸릴 수 있습니다.

2. 타사 응용 프로그램 또는 소프트웨어에서 향상 된 기능을 이미 해결 했기 때문에 타사 **에서 문제 해결** 을 선택 합니다. 이 작업을 수행 하면 보안 점수가 전반적인 보안 상태를 보다 효율적으로 반영할 수 있도록 하는 것이 좋습니다. 제 3 자가 더 이상 해당 컨트롤을 커버 하지 않으면 개선 작업을 완료 되지 않은 것으로 표시할 수 있습니다. Microsoft는 개선 작업을 제 3 자까지 해결 된 것으로 표시 한 경우 점수 요구 사항이 충족 되었는지 여부를 확인할 수 없습니다.

3. 위험을 수락 하 고 개선 작업을 규정 하지 않기로 결정 했으므로 **무시** 를 선택 합니다. 개선 작업을 무시 하 고 나면 최대 보안 점수 점수가 감소 합니다. 언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.

![보안 점수 향상 작업 예제](../../media/secure-score/secure-score1x450.png)

*그림 2 & 3: 향상 작업 flyouts*

## <a name="monitor-improvements-over-time"></a>시간에 따른 모니터 향상

**기록** 탭에서 시간에 따른 조직의 점수 그래프를 볼 수 있습니다. 그래프 아래에 선택한 시간 범위에 적용 된 모든 작업 및 결과 점과 범주와 같은 해당 특성의 목록이 표시 됩니다. 날짜 범위를 사용자 지정 하 고 범주별로 필터링 할 수 있습니다.

## <a name="risk-awareness"></a>위험 인식

Microsoft 보안 점수는 시스템 구성, 사용자 동작 및 기타 보안 관련 측정값을 기반으로 한 보안 환경을 나타내는 수치 요약입니다. 시스템 또는 데이터를 얼마나 많이 침해 해야 하는지 절대 측정 한 것은 아닙니다. 대신 Microsoft 환경에서 보안 제어를 채택 하는 범위를 나타내므로 위반 위험을 상쇄 하는 데 도움이 될 수 있습니다. 보안 침해에의 한 온라인 서비스에는 전혀 문제가 되지 않으며 보안 점수가 보안상 침해에 대 한 보장으로 해석 되어서는 안 됩니다.

## <a name="whats-new"></a>어떠한 새로운 기능이 있나요?

Microsoft 보안 점수를 보안 상태를 보다 효율적으로 구성 하려면 몇 가지 사항을 변경 해야 합니다. 계획 된 변경 사항에 대 한 자세한 내용은 [Microsoft 보안 점수에서](microsoft-secure-score-whats-coming.md) 제공 되는 기능을 참조 하세요.

### <a name="april-21st-2020"></a>4 월 21 일 2020

#### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 하거나 보안 환경을 효과적으로 표현 하지 않습니다.

Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.

- 문서에 IRM 보호 적용
- 데이터 손실 방지 정책 적용

### <a name="january---march-2020"></a>1 월-2020 년 3 월

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Azure AD 개선 작업에 대 한 보안 기본값 지원

Microsoft 보안 점수는 [AZURE AD에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업을 업데이트 하 여 일반적인 공격에 대 한 미리 구성 된 보안 설정으로 조직을 보호 하는 데 도움이 됩니다.

이는 다음과 같은 개선 작업에 영향을 줍니다.

- 모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인
- 관리 역할에 대 한 MFA 필요
- 정책을 사용 하 여 레거시 인증 차단

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업을 제거 했거나 보안 환경을 효과적으로 표현 하지 않습니다.

Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.

- 비즈니스용 OneDrive에 사용자 문서 저장
- Office 365 ATP 안전한 첨부 파일 정책 설정
- Url을 확인 하기 위한 Office 365 안전한 링크 설정
- 사서함 위임 허용 안 함
- 사이트 및 문서에 대 한 익명 게스트 공유 링크 허용
- Cloud App Security Console 켜기
- 외부 공유 링크에 대 한 만료 시간 구성
- 감사 데이터 기록 켜기
- 위험한 및 비호환 섀도 IT 응용 프로그램 검색
- 사용 권한 검토 & 환경에 연결 된 위험한 OAuth 응용 프로그램 차단
- SharePoint online 문서 라이브러리에 대 한 버전 관리 설정
- 지난 30 일 동안 사용 되지 않은 계정 삭제/차단
- 전역 관리자를 5 명 미만으로 지정

#### <a name="removed-not-scored-improvement-actions"></a>"점수가 매겨지지 않음" 개선 작업 제거

보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다. 기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다. Microsoft 보안 점수는 모든 권장 사항에 따라 점수가 명확 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다. 점수를 획득 하지 않음 개선 조치를 측정할 수 없습니다.  

이러한 이유로 점수가 없는 모든 개선 작업은 제거 되었습니다. 해당 부분에 대 한 작업이 필요 하지 않습니다.

#### <a name="removed-device-improvement-actions"></a>장치 향상 작업 제거

개선 작업의 Microsoft 보안 점수 장치 범주를 평가한 후에는 해당 작업이 장치 구성 상태가 아니라 정책 상태를 평가 하는 것으로 확인 되었습니다. 구성은 보안에 직접적으로 연결 되므로 기존 장치 작업은 조직 상황을 완전히 나타내지 않고 결정 됩니다.  장치 보안 환경을 보다 완전 하 게 나타내기 위해 진단 데이터를 직접 사용 하는 권장 사항 집합을 제공 하는 작업을 수행 하는 중에 장치 범주에서 현재 작업을 제거 합니다.

제거 된 개선 작업은 다음과 같습니다.

- Microsoft Intune 모바일 장치 관리 사용
- Android 용 Microsoft Intune 준수 정책 만들기
- 비즈니스용 Android 용 Microsoft Intune 준수 정책 만들기
- Android 용 Microsoft Intune 앱 보호 정책 만들기
- IOS 용 Microsoft Intune 앱 보호 정책 만들기
- Microsoft Intune 준수 정책이 비규격으로 지정 된 장치 표시
- IOS 용 Microsoft Intune 준수 정책 만들기
- MacOS에 대 한 Microsoft Intune 준수 정책 만들기
- Windows 용 Microsoft Intune 준수 정책 만들기
- Android 용 Microsoft Intune 구성 프로필 만들기
- 비즈니스용 Android 용 Microsoft Intune 구성 프로필 만들기
- MacOS 용 Microsoft Intune 구성 프로필 만들기
- IOS 용 Microsoft Intune 구성 프로필 만들기
- Windows 용 Microsoft Intune 구성 프로필 만들기
- Microsoft Intune에서 향상 된 jailbreak 검색 사용
- 모든 장치에 패치를 적용 하 고 바이러스 백신 및 방화벽을 사용 하도록 설정 합니다.
- Microsoft Intune에 Windows Defender ATP 통합 사용
- Microsoft Intune Windows Information Protection 정책 만들기
- 모든 장치에 고급 보안 구성 필요
- 매주 차단 된 장치 보고서 검토

#### <a name="mfa-improvement-action-updates"></a>MFA 개선 작업 업데이트

비즈니스의 보안을 강화 하기 위해 기업에서 요구 하는 사항을 반영 하기 위해 Microsoft 보안 점수가 다단계 인증을 중심으로 하는 세 가지 향상 작업을 제거 하 고 2를 추가 했습니다.

제거 된 개선 작업:

- Multi-factor authentication에 대 한 모든 사용자 등록
- 모든 사용자에 대해 MFA 요구
- Azure AD 권한 있는 역할에 대해 MFA 필요

개선 작업 추가:

- 모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인
- 관리 역할에 대 한 MFA 필요

 이러한 새로운 향상 작업을 수행 하려면 디렉터리 전체에서 MFA (multi-factor authentication)에 대 한 사용자 또는 관리자를 등록 하 고 조직의 요구 사항에 맞는 적절 한 정책 집합을 설정 해야 합니다. 기본 목표는 모든 사용자와 관리자가 여러 요소 또는 위험 기반 id 확인 메시지를 사용 하 여 인증할 수 있도록 하는 데 유연성이 있습니다. 이는 범위 결정을 적용 하는 정책이 여러 개 있거나 Microsoft가 MFA를 위해 사용자를 challenge 해야 하는 경우를 결정할 수 있도록 보안 기본값 (16 월 여섯째 부분)을 설정 하는 형태입니다.

#### <a name="removed-review-improvement-actions"></a>"검토" 개선 작업 제거

보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다. 기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다. 한 Microsoft 보안 점수는 모든 권장 사항이 점수에 분명 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다. 검토 개선 작업은 다른 개선 작업과 같은 표준으로 측정 되지 않습니다.  

이러한 이유로 검토 흐름을 필요로 했던 모든 개선 작업이 일시적으로 제거 되었습니다. 해당 부분에 대 한 작업이 필요 하지 않습니다.

### <a name="preview-features"></a>미리 보기 기능

[Preview 릴리스에](microsoft-secure-score-preview.md)는 다음과 같은 기능이 포함 됩니다.

* CISO 팀장 수준 토론을 위한 모든 새 메트릭 및 추세 보기
* 점수를 추적 하 고 벤치 마크 위한 새로운 방법
* 점수 재발에 대 한 추적 및 모니터링 향상
* 개선 작업 필터링, 태그, 검색 및 그룹화
* 점수 예측 및 계획 된 작업을 사용 하 여 향후 목표를 향해 관리
* 포인트 시스템 단순화
* 더 많은 내용을 확인해 보세요.

## <a name="we-want-to-hear-from-you"></a>사용자의 의견을 듣고 싶습니다.

문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에서 게시할 때 알려주십시오. 당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.

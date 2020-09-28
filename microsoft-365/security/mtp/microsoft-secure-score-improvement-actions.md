---
title: Microsoft 보안 점수를 통해 보안 상황 평가
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수를 개선 하기 위한 조치를 취하는 방법에 대해 설명 합니다.
keywords: microsoft 보안 점수, 보안 점수, office 365 보안 점수, microsoft 보안 점수, microsoft 365 보안 센터, 개선 작업
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
ms.openlocfilehash: cb2aad70b8ba6ccd9075513b5f383ede42ebd6c0
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295131"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Microsoft 보안 점수를 사용 하 여 보안 상황 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 보안 점수는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다. 이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.

필요한 정보를 보다 신속 하 게 지원 하기 위해 Microsoft 개선 작업을 그룹으로 구성 합니다.

* Id (Azure Active Directory 계정 & 역할)
* 데이터 (Microsoft Information Protection)
* 장치 ( [장치에 대 한 Microsoft 보안 점수](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)라고 알려진 MICROSOFT Defender ATP)
* 앱 (Office 365 및 Microsoft Cloud App Security)을 포함 하는 전자 메일 및 클라우드 앱
* 인프라 (지금은 향상 작업 없음)

>[!NOTE]
>Microsoft 보안 점수가 최근 릴리스에서는 Microsoft 보안 점수가 Id 보안 점수 및 그래프 API와 일시적으로 호환 되지 않는 향상 된 점수 매기기 모델이 출시 되었습니다. [자세히 보기](microsoft-secure-score-whats-new.md)

Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간 점 분할 방식 및 사용 가능한 점수를 참조 하세요. 또한 전체 점수, 벤치 마크 비교가 포함 된 보안 점수의 역사적 추세, 점수를 높이기 위해 수행할 수 있는 우선 순위 지정 작업을 확인할 수 있습니다.

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>현재 점수 확인

현재 점수를 확인 하려면 Microsoft 보안 점수 개요 페이지로 이동 하 여 **보안 점수가**있는 타일을 확인 합니다. 점수는 총 가능한 점수에서 달성 한 점수와 함께 백분율로 표시 됩니다.

또한 점수 옆에 있는 **포함** 단추를 선택 하면 점수에 대 한 다양 한 보기를 선택할 수 있습니다. 이러한 서로 다른 점수 보기는 점수 타일 및 점 분석 차트의 그래프에 표시 됩니다.

다음과 같은 점수를 통해 전체 점수를 보기에 추가 하 여 전체 점수를 완벽 하 게 파악할 수 있습니다.

- **계획 된 점수**: 계획 된 작업이 완료 되 면 예상 점수 표시
- **현재 사용권 점수**: 현재 Microsoft 라이선스로 얻을 수 있는 점수를 표시 합니다.
- 실현 가능한 **점수**: Microsoft 라이선스 및 현재 위험 수용으로 달성 가능한 점수 표시

이 보기는 가능한 모든 점수 보기를 포함 했을 때의 모양입니다.

![계획 된 점수, 현재 라이선스 점수 및 달성 가능한 점수를 포함 하는 보안 점수](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>점수를 개선 하기 위한 조치 수행

**향상 작업** 탭에는 가능한 공격 표면을 해결 하는 보안 권장 사항이 나열 되어 있습니다. 또한 해당 상태 (주소, 계획 된 위험, 허용 됨, 타사를 통해 해결 됨, 대안 완화 및 완료 됨)가 포함 됩니다. 모든 개선 작업을 검색, 필터링 및 그룹화 할 수 있습니다.  

### <a name="ranking"></a>순서

순위는 달성 하기 위해 남은 점수, 구현 난이도, 사용자 영향 및 복잡도에 따라 결정 됩니다. 가장 높은 순위의 향상 작업에는 낮은 난이도, 사용자 영향 및 복잡도의 점수가 많이 남아 있습니다.

### <a name="view-improvement-action-details"></a>향상 작업 세부 정보 보기

특정 향상 작업을 선택 하면 전체 페이지 플라이 아웃이 나타납니다.  

![향상 작업 플라이 아웃 예 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *그림 2: 개선 작업 플라이 아웃 예제*

이 작업을 완료 하려면 몇 가지 옵션을 사용할 수 있습니다.

* **관리** 를 선택 하 여 구성 화면으로 이동 하 고 변경을 수행 합니다. 그런 다음 동작의 가치를 즉시 파악할 수 있습니다. 점수는 일반적으로 업데이트 하는 데 약 24 시간이 소요 됩니다.

* **공유** 를 선택 하 여 개선 작업에 대 한 직접 링크를 복사 합니다. 또한 전자 메일, Microsoft 팀, Microsoft Planner 또는 ServiceNow와 같이 링크를 공유 하는 플랫폼을 선택할 수 있습니다. ServiceNow를 선택 하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시 되는 변경 티켓을 만들 수 있습니다. 자세한 내용은 [Microsoft 365 보안 센터 및 ServiceNow 통합](tickets-security-center.md)을 참조 하세요.

### <a name="choose-an-improvement-action-status"></a>향상 작업 상태 선택

상태를 선택 하 고 향상 작업과 관련 된 메모를 기록 합니다.

- **해결 방법** -개선 작업이 필요 하다는 것을 인식 하 고 미래에 특정 시점에 해결할 계획을 세워야 합니다. 이 상태는 부분적으로 검색 되었지만 완전히 완료 되지 않은 작업에도 적용 됩니다.
- **계획** 됨-개선 작업을 완료 하기 위한 구체적인 계획을 수립 합니다.
- **위험 허용** -보안은 항상 유용성과 균형을 유지 해야 하며, 환경에 대 한 모든 권장 사항은 아닙니다. 이 경우 위험 또는 남은 위험을 수락 하 고 개선 작업을 적용 하지 않도록 선택할 수 있습니다. 모든 점수를 제공 하는 것은 아니지만 해당 작업은 향상 작업 목록에 더 이상 표시 되지 않습니다. 언제 든 지 기록에서이 작업을 보거나 실행 취소할 수 있습니다.
- 타사 응용 프로그램 또는 소프트웨어 또는 내부 도구를 통해 **제 3 자를 통해 확인** 되 고 **대체 완화 작업을 통해 해결** 되었습니다. 작업을 수행 하는 것이 가장 좋은 점수를 얻을 수 있으므로 점수가 사용자의 전체 보안 상태를 보다 잘 반영 합니다. 타사 또는 내부 도구가 더 이상 해당 컨트롤을 커버 하지 않으면 다른 상태를 선택할 수 있습니다. 향상 작업이 이러한 상태 중 하나로 표시 된 경우 Microsoft는 구현의 완성도를 명확 하 게 파악할 수 없습니다.

#### <a name="threat--vulnerability-management-improvement-actions"></a>위협 & 취약성 관리 개선 작업

"장치" 범주의 향상 작업에 대해 상태를 선택할 수 없습니다. 대신 [Microsoft Defender 보안 센터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 의 [tvm (& 취약성 관리) 보안 권장 사항을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 연결 하 여 조치를 취할 것입니다. 선택한 예외와 작성 한 사유는 해당 포털에 한정 됩니다. Microsoft 보안 점수 포털에 표시 되지 않습니다.

#### <a name="completed-improvement-actions"></a>완료 된 개선 작업

향상 작업에 대 한 가능한 모든 점수를 얻은 후에는 개선 조치에 "완료 됨" 상태가 발생 합니다. 완료 된 개선 작업은 Microsoft 데이터를 통해 확인 되며 상태를 변경할 수 없습니다.

### <a name="assess-information-and-review-user-impact"></a>정보 평가 및 사용자 영향 검토

이 **섹션에서 설명** 하는 부분은 범주, 보안을 통해 보호할 수 있는 공격 및 제품에 대 한 것입니다.

**사용자 영향** 에 따라 개선 작업이 실행 되는 경우 사용자에 게 발생할 항목이 표시 되 고, **영향을 받는 사용자** 에 게는이를 표시할 사람이 표시 됩니다.

### <a name="implement-the-improvement-action"></a>개선 작업 구현

**구현** 섹션에는 개선 작업을 완료 하기 위한 다음 단계, 개선 작업의 현재 구현 상태 및 자세한 링크를 보여 주는 모든 필수 구성 요소, 단계별 단계가 나와 있습니다.

필수 구성 요소에는 개선 작업을 처리 하기 전에 수행 해야 하는 모든 라이선스 또는 작업이 포함 됩니다. 라이선스에 개선 작업을 완료 하 고 해당 라이선스가 필요한 사용자에 게 적용 되었는지 확인 합니다.  

## <a name="we-want-to-hear-from-you"></a>사용자의 의견을 듣고 싶습니다.

문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에 게시 하 여 알려 주세요. 당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.

## <a name="related-resources"></a>관련 리소스

- [Microsoft 보안 점수 개요](microsoft-secure-score.md)
- [Microsoft 보안 점수 기록 및 목표를 충족 하는 추적](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
- [새로운 기능](microsoft-secure-score-whats-new.md)

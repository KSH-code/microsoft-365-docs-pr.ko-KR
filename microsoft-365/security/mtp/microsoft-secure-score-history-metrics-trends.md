---
title: Microsoft 보안 점수 기록 및 목표를 충족 하는 추적
description: Microsoft 보안 점수에 영향을 받은 활동에 대 한 정보를 습득 합니다. 추세를 파악 하 고 목표를 설정 합니다.
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
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769247"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Microsoft 보안 점수 기록 및 목표를 충족 하는 추적

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[Microsoft 보안 점수](microsoft-secure-score.md) 는 조직의 보안 상태를 측정 한 값으로, 더 많은 향상 작업이 수행 되었음을 나타냅니다. 이 도구 https://security.microsoft.com/securescore 는 [Microsoft 365 보안 센터](overview-security-center.md)에서 찾을 수 있습니다.

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>점수에 영향을 주는 활동에 대 한 통찰력 얻기

**기록** 탭에서 시간에 따른 조직의 점수를 그래프로 표시 합니다.

그래프 아래에는 선택한 시간 범위에 적용 된 모든 작업과 해당 속성 (예: 결과 점수 및 범주)의 목록이 나와 있습니다. 날짜 범위를 사용자 지정 하 고 범주별로 필터링 할 수 있습니다.

![활동 기록](../../media/secure-score/secure-score-history-activity.png)

활동에 연결 된 개선 작업을 선택 하면 전체 개선 작업 플라이 아웃이 나타납니다.

해당 하는 특정 개선 작업에 대 한 모든 기록을 보려면 플라이 아웃에서 기록 링크를 선택 합니다.

![향상 작업 기록](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>추세 검색 및 목표 설정

**메트릭 & 추세** 탭에는 다양 한 그래프와 차트를 통해 추세를 보다 명확 하 게 표시 하 고 목표를 설정할 수 있습니다. 시각화의 전체 페이지에 대 한 날짜 범위를 설정할 수 있습니다. 시각화에는 다음이 포함 됩니다.

* 조직의 목표에 따라 사용자 지정 되는 **보안 점수 영역** 및 불량 점수 범위에 대 한 정의
* **회귀 경향** -구성, 사용자 또는 장치 변경으로 인해 회귀 된 포인트의 시간 표시줄입니다.  
* **비교 추세** -조직의 보안 점수가 다른 사람들과의 시간 경과에 따라 어떻게 비교 되 고 있습니다. 이 보기에는 비슷한 사용자 수를 갖는 조직의 점수 평균을 나타내는 줄과 설정할 수 있는 custom 비교 보기가 포함 될 수 있습니다.
* **위험 수락 추세** -"위험 수용 됨"으로 표시 된 개선 작업의 시간 표시 막대입니다.
* **점수 변경** -지정 된 날짜 범위에서 이후의 점수 변경과 함께 회귀 된 점수 수입니다.

### <a name="compare-your-score-to-organizations-like-yours"></a>점수를 사용자와 같은 조직에 비교

점수가 비슷한 조직과 비교 되는 방식을 확인할 수 있는 두 가지 위치가 있습니다. 두 차트에서 **비교 관리** 를 선택 하 여 조직의 정보를 보고 편집할 수 있습니다. 산업, 조 직 크기, 라이선스 및 지역에 따라 사용자 지정 비교를 만들 수도 있습니다.

#### <a name="comparison-bar-chart"></a>비교 가로 막대형 차트

비교 표시줄 차트는 **개요** 탭입니다. 차트를 커서로 가리키면 점수 및 성과 점수를 볼 수 있습니다. 비교 데이터는 익명 이므로 어떤 다른 테 넌 트가 믹스에 있는지 정확히 알 수 없습니다.

![유사한 조직의 점수를 보여주는 막대 그래프](../../media/secure-score/secure-score-comparison-bar.png)

- 다른 테 넌 트 **와 같은 조직** : 즉, 다음 조건과 일치 하는 하나 이상의 테 넌 트를 비교 하는 경우를 제외 하 고는 사용자에 게 해당 하는 모든 초과 작업의 평균 점수가 제공 됩니다.
    1. 같은 업계
    2. 동일한 조직 크기
    3. 모든 지역
    4. 사용 된 Microsoft 제품은 80% 유사
    5. 영업 기회 (현재 라이선스로 얻을 수 있는 최대 점수)가 테 넌 트에서 20% 범위 안에 있습니다.

- **사용자 지정 비교** : 다음 조건에 따라 **비교 관리** 를 선택 하 여 먼저 설치 해야 합니다.
    1. 선택한 산업
    2. 선택한 조직 크기
    3. 선택한 지역
    4. 선택한 라이선스
    5. 사용 된 Microsoft 제품은 80% 유사
    6. 영업 기회 (현재 라이선스로 얻을 수 있는 최대 점수)가 테 넌 트에서 20% 범위 안에 있습니다.

선택 항목의 사용자 지정 선택을 선택 하지 않은 경우에는 비교할 수 있는 다른 테 넌 트 수가 5 명 미만이 면 "제한 된 데이터로 인해 사용할 수 없습니다."가 표시 됩니다.

#### <a name="comparison-trend"></a>비교 추세

**메트릭 & 추세** 탭에서 조직의 보안 점수가 다른 사람들과 어떻게 비교 하는지 확인 합니다.

![시간에 따른 유사한 조직의 점수를 보여주는 꺽은선형 그래프](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>사용자의 의견을 듣고 싶습니다.

문제가 있는 경우 [보안, 개인 정보 & 준수](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티에 게시 하 여 알려 주세요. 당사는 커뮤니티를 모니터링 하 고 도움이 될 것입니다.

## <a name="related-resources"></a>관련 리소스

- [Microsoft 보안 점수 개요](microsoft-secure-score.md)
- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
- [새로운 기능](microsoft-secure-score-whats-new.md)

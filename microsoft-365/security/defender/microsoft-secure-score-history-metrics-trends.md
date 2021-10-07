---
title: Microsoft 보안 점수 기록 추적 및 목표 충족
description: Microsoft 보안 점수에 영향을 주는 활동에 대한 인사이트를 얻습니다. 추세를 검색하고 목표를 설정할 수 있습니다.
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 Defender 포털, 개선 작업
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.technology: m365d
ms.openlocfilehash: d1f1c36eeaa010981ffd44ccad75e0d73a7159f6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162365"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Microsoft 보안 점수 기록 추적 및 목표 충족

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft 보안 점수는](microsoft-secure-score.md) 조직의 보안 자세를 측정한 것으로, 수치가 높을수록 개선 작업이 더 많이 수행되었음을 나타내고 있습니다. 이 사이트는 사이트 포털 https://security.microsoft.com/securescore [에서 Microsoft 365 Defender 있습니다.](overview-security-center.md)

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>점수에 영향을 주는 활동에 대한 인사이트 얻기

기록 탭에서 시간의 따라 조직의 점수 **그래프를** 시청합니다.

그래프 아래에는 선택한 시간 범위에서 수행된 모든 작업 및 해당 특성(예: 결과 점 및 범주)의 목록이 표시됩니다. 날짜 범위를 사용자 지정하고 범주별로 필터링할 수 있습니다.

![활동 기록.](../../media/secure-score/secure-score-history-activity.png)

활동과 관련된 개선 작업을 선택하면 전체 개선 작업 플라이아웃이 나타납니다.

특정 개선 작업의 모든 기록을 확인하려면 플라이아웃에서 사용 기록 링크를 선택합니다.

![개선 작업 기록.](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>추세 검색 및 목표 설정

메트릭 **&** 추세 탭에는 추세를 보다 쉽게 파악하고 목표를 설정할 수 있는 여러 그래프 및 차트가 있습니다. 시각화의 전체 페이지에 대한 날짜 범위를 설정할 수 있습니다. 시각화에는 다음이 포함됩니다.

* **보안 점수 영역** - 양호하고, 괜찮고, 불량 점수 범위에 대한 조직의 목표와 정의에 따라 사용자 지정됩니다.
* **회귀 추세** - 구성, 사용자 또는 장치 변경으로 인하여 회귀된 점의 시간 표시 막대입니다.  
* **비교 추세** - 조직의 보안 점수가 시간 경과에 따라 다른 사용자와 비교하는 방식입니다. 이 보기에는 사용자 수가 비슷한 조직의 점수 평균을 나타내는 줄과 설정할 수 있는 사용자 지정 비교 보기가 포함됩니다.
* **위험 수용 추세** - "위험 수락"으로 표시된 개선 작업의 시간 표시 막대
* **점수 변경** - 지정된 날짜 범위에서 달성한 점수, 점수 회귀 및 점수 변경 수입니다.

### <a name="compare-your-score-to-organizations-like-yours"></a>점수를 사용자와 같은 조직과 비교

점수가 사용자와 비슷한 조직과 어떻게 비교하는지 볼 수 있는 두 가지 위치가 있습니다. 두 차트에서 비교 관리를  선택하여 조직의 정보를 보고 편집할 수 있습니다. 또한 산업, 조직 크기, 라이선스 및 지역에 따라 사용자 지정 비교를 만들 수 있습니다.

#### <a name="comparison-bar-chart"></a>비교 막대형 차트

비교 막대 차트는 개요 **탭입니다.** 차트 위에 마우스를 놓고 점수와 점수를 볼 수 있습니다. 비교 데이터는 대문자이기 때문에 다른 테넌트가 혼합된 것으로 정확히 알 수 없습니다.

![비슷한 조직의 점수의 막대 그래프입니다.](../../media/secure-score/secure-score-comparison-bar.png)

- **사용자와 같은** 조직 : 다음 기준을 충족하는 다른 테넌트의 평균 점수(비교할 테넌트가 5개 이상 있는 경우)입니다.
    1. 동일한 산업
    2. 동일한 조직 크기
    3. 모든 지역
    4. 사용되는 Microsoft 제품은 80% 유사
    5. 테넌트의 20% 범위 내에서 기회(현재 라이선스로 달성할 수 있는 최대 점수)

- **사용자 지정** 비교 : 다음 기준에 따라 비교 관리를 선택하여 **설정해야** 합니다.
    1. 선택한 산업
    2. 선택한 조직 크기
    3. 선택한 지역
    4. 선택한 라이선스
    5. 사용되는 Microsoft 제품은 80% 유사
    6. 테넌트의 20% 범위 내에서 기회(현재 라이선스로 달성할 수 있는 최대 점수)

사용자 지정을 선택했지만 결과에 비교할 수 있는 다른 테넌트가 5개 미만인 경우 "제한된 데이터로 인해 사용할 수 없습니다."가 표시됩니다.

#### <a name="comparison-trend"></a>비교 추세

메트릭 & **추세** 탭에서 조직의 보안 점수가 시간 경과에 따라 다른 사용자와 어떻게 비교되는지 볼 수 있습니다.

![시간이 지난 비슷한 조직의 점수에 대한 선 그래프입니다.](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>의견을 보내 주세요.

문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 & [알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.

## <a name="related-resources"></a>관련 리소스

- [Microsoft 보안 점수 개요](microsoft-secure-score.md)
- [보안 상태 평가](microsoft-secure-score-improvement-actions.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
- [새로운 기능](microsoft-secure-score-whats-new.md)

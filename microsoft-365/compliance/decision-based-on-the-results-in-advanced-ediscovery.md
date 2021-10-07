---
title: 2013의 결과에 따라 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 사례 파일의 결정 탭에서 Advanced eDiscovery 파일 검토 집합의 올바른 크기를 결정하는 데 도움이 되는 데이터를 제공하는 방법을 확인합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32682690c6febac247d67e3b78f56d1f71b9a2fb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207358"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Advanced eDiscovery
  
관련성 모듈의 Advanced eDiscovery 결정 탭에서는 사례 파일 검토 집합의 크기를 결정하기 위한 의사 결정 지원 통계를 보고 사용할 수 있는 추가 정보를 제공합니다.
  
## <a name="using-the-decide-tab"></a>결정 탭 사용

![Relevance Decide.](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
이 탭에는 다음과 같은 구성 요소가 포함됩니다.
  
- **문제**: 여기에서 목록에서 관심 있는 문제를 선택할 수 있습니다.

- **검토 회수율:** 관련성 점수에 Advanced eDiscovery 검토를 비교합니다. 차트의 컷오프 지점은 검토할 파일의 백분율을 나타내며, 해당 백분율은 해당 점수에 매핑됩니다. 이 설정은 관련성 테스트 단계에서 컬링에 대한 내보내기 임계값으로 사용됩니다. 검토할 파일 수에 대한 기본 컷오프 지점은 회수와 정밀도 간의 균형이 최적의 지점입니다. 실제 컷오프 지점은 목표 및 비용 절차(%review) 및 위험(%회수율)에 따라 사용자가 결정해야 합니다. 슬라이더를 사용하여 컷오프 지점을 조정하고 검색할 관련 파일의 백분율을 조정할 때, 결정의 유효성을 검사하기 전에 그래프 및 매개 변수에 대한 영향을 볼 수 있습니다.

- **매개** 변수: 검토, 회수, 다음 관련성 및 총 비용 매개 변수는 전체 사례에 대한 컬렉션과 관련된 검토 집합과 관련된 누적 계산 통계입니다. 이러한 매개 변수에 대한 정의는 다음과 같습니다.

  - **검토:** 이 컷오프에 따라 검토할 파일의 백분율입니다.

  - **회수:** 검토 집합에 있는 관련 파일의 백분율입니다.

  - **다음 관련성:** 현재 검토 집합에 없는 다른 관련 파일을 검토하고 식별하기 위한 비용입니다.

  - **총 비용:** 사례 파일의 이 백분율을 검토하는 데 드는 비용입니다. 비용 매개 변수 설정은 사례 관리자가 설정할 수 있습니다.

  - **타당성** 점수로 배포: 왼쪽에 진한 회색 표시의 파일이 컷오프 점수 미만입니다. 도구 팁에는 전체 파일과 관련된 리뷰 파일 집합의 관련성 점수와 관련 백분율이 표시됩니다.

확장된 세부 정보 **창에** 세부 정보가 표시됩니다. 컬렉션 그림의 파일에는 비어 있거나 까다로워진 파일이 포함되어 있지 않습니다. 패밀리 파일 수치는 해당 패밀리의 일부로 계산된, 아직까지는 무관하게 로드되지 않은 파일을 나타내고 있습니다.

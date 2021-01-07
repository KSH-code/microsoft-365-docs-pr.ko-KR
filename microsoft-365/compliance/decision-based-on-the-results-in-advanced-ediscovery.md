---
title: Advanced eDiscovery의 결과에 따라 결정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Advanced eDiscovery의 결정 탭에서 사례 파일 검토 집합의 올바른 크기를 결정하는 데 도움이 되는 데이터를 제공하는 방법을 확인합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769153"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Advanced eDiscovery의 결과와의관성에 따라 결정
  
Advanced eDiscovery의 관련성 모듈에서 결정 탭은 사례 파일 검토 집합의 크기를 결정하는 데 결정 지원 통계를 보고 사용할 수 있는 추가 정보를 제공합니다.
  
## <a name="using-the-decide-tab"></a>결정 탭 사용

![관련성을 결정](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
이 탭에는 다음과 같은 구성 요소가 포함됩니다.
  
- **문제**: 여기에서 목록에서 관심 문제를 선택할 수 있습니다.

- **검토 회수율:** 관련성 점수에 따라 Advanced eDiscovery 검토를 비교합니다. 차트의 컷오프 지점은 검토할 파일의 백분율을 나타내며, 해당 점수에 매핑됩니다. 관련성 테스트 단계에서 컬링에 대한 내보내기 임계값으로 사용됩니다. 검토할 파일 수에 대한 기본 컷오프 지점은 회수 및 정밀도 사이의 균형이 최적 지점입니다. 실제 컷오프 지점은 목표와 비용의 상하(%review) 및 위험(%회수율)에 따라 사용자가 결정해야 합니다. 슬라이더를 사용하여 컷오프 지점을 조정하고, 검색할 관련 파일의 백분율을 조정할 때, 결정의 유효성을 검사하기 전에 그래프 및 매개 변수에 대한 영향을 볼 수 있습니다.

- **매개** 변수: 검토, 회수, 다음 관련 비용 및 총 비용 매개 변수는 전체 사례에 대한 컬렉션과 관련된 검토 집합과 관련된 누적 계산 통계입니다. 이러한 매개 변수에 대한 정의는 다음과 같습니다.

  - **검토:** 이 컷오프에 따라 검토할 파일의 백분율입니다.

  - **회수:** 검토 집합에 있는 관련 파일의 백분율입니다.

  - **다음 관련성:** 현재 검토 집합에 없는 다른 관련 파일을 검토하고 식별하는 데 드는 비용입니다.

  - **총 비용:** 사례 파일의 이 백분율을 검토하는 데 드는 비용입니다. 비용 매개 변수 설정은 사례 관리자가 설정할 수 있습니다.

  - **타당성** 점수로 분포: 왼쪽에 진한 회색 표시의 파일이 잘리기 점수 미만입니다. 도구 팁에는 전체 파일과 관련된 리뷰 파일 집합의 관련성 점수 및 관련 백분율이 표시됩니다.

확장된 **세부 정보 창에** 세부 정보가 표시됩니다. 컬렉션 그림의 파일에는 비어 있거나 까다로워진 파일이 포함되어 있지 않습니다. 패밀리 파일 수치는 해당 패밀리의 일부로 계산되는, 아직까지는 무관하게 로드되지 않은 파일을 나타내고 있습니다.

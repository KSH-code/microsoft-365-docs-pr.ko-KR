---
title: 검토 집합의 항목에 예측 점수 필터 적용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 예측 점수 필터를 사용하여 예측 코딩 모델이 관련성이 있는 것으로 예측된 항목을 표시합니다.
ms.openlocfilehash: 04d0881e36c28a70df58a1aa7b054c641dfeeb2a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200464"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>검토 집합에 예측 점수 필터 적용(미리 보기)

Advanced eDiscovery 예측 코딩 모델을 만들고 안정된 지점으로 교육한 후 예측 점수 필터를 적용하여 모델이 관련성이 없다고 결정한 검토 집합 항목을 표시할 수 있습니다. 모델을 만들 때 해당 예측 점수 필터도 만들어집니다. 이 필터를 사용하여 지정된 범위 내에서 예측 점수가 할당된 항목을 표시할 수 있습니다. 일반적으로 **0에서** **.5** 사이의 예측 점수는 모델이 예측한 항목과 관련이 없는 항목에 할당됩니다. **.5에서 1.0** 사이의 예측 점수가 할당된 항목은 모델이 예측한 관련 항목입니다. 

예측 점수 필터를 사용할 수 있는 두 가지 방법은 다음과 같습니다.

- 모델이 예측한 검토 집합의 항목 검토 우선 순위를 지정합니다.

- 모델이 예측한 리뷰 집합의 항목을 선회하는 것은 관련이 없습니다. 또는 예측 점수 필터를 사용하여 관련이 없는 항목의 검토의 우선 순위를 다시 지정할 수 있습니다.

## <a name="before-you-apply-a-prediction-score-filter"></a>예측 점수 필터를 적용하기 전에

- 해당 예측 점수 필터를 만들 수 있도록 예측 코딩 모델을 작성합니다.

- 교육 라운드 후에 예측 점수 필터를 적용할 수 있습니다. 그러나 여러 라운드를 수행한 후 또는 모델이 안정될 때까지 기다렸다가 예측 점수 필터를 사용할 수 있습니다.

## <a name="apply-a-prediction-score-filter"></a>예측 점수 필터 적용

1. 이 Microsoft 365 규정 준수 센터 사례를 Advanced eDiscovery 검토 집합 탭을 선택한  다음 검토 집합을 여는 경우

   ![필터를 클릭하여 필터 플라이아웃 페이지를 표시합니다.](..\media\PredictionScoreFilter0.png)   

   미리 로드된 기본 필터는 검토 집합 페이지 맨 위에 표시됩니다. 이러한 집합을 Any로 설정할 수 **있습니다.**

2. 필터를 클릭하여 **필터 플라이아웃** 페이지를 표시합니다. 

3. 분석 & **코딩 섹션을** 확장하여 필터 집합을 표시합니다.

      ![분석 및 예측 & 섹션의 예측 점수 필터입니다.](..\media\PredictionScoreFilter1.png)

   예측 점수 필터의 명명 규칙은 **예측 점수(모델 이름)입니다.** 예를 들어 Model **A라는** 모델의 예측 점수 필터 이름은 예측 **점수(모델 A)입니다.**

4. 사용할 예측 점수 필터를 선택하고 완료 를 **클릭합니다.**

5. 검토 집합 페이지에서 예측 점수 필터에 대한 드롭다운을 클릭하고 예측 점수 범위에 대한 최소값 및 최대값을 입력합니다. 예를 들어 다음 스크린샷에는 **.5에서 1.0** 사이의 예측 점수 **범위가 나와 있습니다.**

   ![예측 점수 필터의 최소값 및 최대값입니다.](..\media\PredictionScoreFilter2.png)

6. 필터 외부를 클릭하여 검토 집합에 필터를 자동으로 적용합니다.

  지정한 범위 내에서 예측 점수가 있는 문서 목록이 검토 집합 페이지에 표시됩니다. 

  > [!TIP]
  > 문서에 할당된 실제 예측 점수를 보려면 읽기  창에서 메타데이터 탭을 클릭할 수 있습니다. 검토 집합의 모든 모델에 대한 예측 점수는 **RelevanceScores** 메타데이터 속성에 표시됩니다.

## <a name="more-information"></a>추가 정보

- 필터 사용에 대한 자세한 내용은 검토 집합에서 콘텐츠 쿼리 및 [필터링을 참조하세요.](review-set-search.md)

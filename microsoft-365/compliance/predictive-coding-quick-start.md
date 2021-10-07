---
title: Advanced eDiscovery 예측 코딩 - 빠른 시작
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
description: 이 모듈에서 예측 코딩 모듈을 사용하는 방법을 Advanced eDiscovery. 이 문서에서는 예측 코딩을 사용하여 조사와 가장 관련이 있는 검토 집합의 콘텐츠를 식별하는 종단-종단 프로세스에 대해 설명합니다.
ms.openlocfilehash: 38607459057ff06a2ce74364b752130467deaddd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197596"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>빠른 시작: Advanced eDiscovery 예측 코딩(미리 보기)

이 문서에서는 이 문서에서 예측 코딩 사용을 위한 빠른 시작을 Advanced eDiscovery. Advanced eDiscovery 코딩 모듈은 Advanced eDiscovery 지능형 기계 학습 기능을 사용하여 검토할 콘텐츠의 양을 줄이는 데 도움이 됩니다. 예측 코딩을 사용하면 대량의 사례 콘텐츠를 검토에 우선 순위를 지정할 수 있는 관련 항목 집합으로 줄이고 선형화할 수 있습니다. 이 작업을 수행하기 위해 검토 집합에서 가장 관련성이 높은 항목의 검토 우선 순위를 지정하는 데 도움이 되는 자체 예측 코딩 모델을 만들고 교육할 수 있습니다.

다음은 예측 코딩 프로세스에 대한 간략한 개요입니다.

![예측 코딩을 위한 빠른 시작 프로세스입니다.](..\media\PredictiveCodingQuickStartProcess.png)

시작하기 위해 관련성 또는 관련성이 없는 항목 50개만 레이블을 지정하는 모델을 만들면 됩니다. 그러면 시스템은 이 교육을 사용하여 검토 집합의 모든 항목에 예측 점수를 적용합니다. 이렇게 하면 예측 점수에 따라 항목을 필터링할 수 있습니다. 이를 통해 가장 관련성 있는(또는 관련이 없는) 항목을 먼저 검토할 수 있습니다. 더 높은 정보 및 회수율을 사용하여 모델을 교육하려는 경우 모델이 안정화될 때까지 후속 교육 라운드에서 항목에 레이블을 지정하는 것을 계속할 수 있습니다. 모델이 안정화되면 최종 예측 필터를 적용하여 검토할 항목의 우선 순위를 지정할 수 있습니다.

예측 코딩에 대한 자세한 개요는 에서 예측 코딩에 대해 자세히 [Advanced eDiscovery.](predictive-coding-overview.md)

## <a name="step-1-create-a-new-predictive-coding-model"></a>1단계: 새로운 예측 코딩 모델 만들기

첫 번째 단계는 검토 집합에서 새로운 예측 코딩 모델을 만드는 것입니다.

1. 이 Microsoft 365 규정 준수 센터 사례를 Advanced eDiscovery 검토 집합 **탭을** 선택합니다.

2. 검토 집합을 열고 **분석** 예측 코딩 관리(미리  >  **보기)를 클릭합니다.**

   ![검토 집합에서 분석 드롭다운 메뉴를 클릭하여 예측 코딩 페이지로 이동합니다.](..\media\ManagePredictiveCoding.png)

3. 예측 코딩 **모델(미리 보기) 페이지에서** 새 모델을 **클릭합니다.**

4. 플라이아웃 페이지에서 모델의 이름과 선택적 설명을 입력합니다.

5. **저장을** 클릭하여 모델을 만들 수 있습니다.

   시스템에서 모델을 준비하는 데 몇 분 정도 걸립니다. 준비가 된 후 첫 번째 교육을 수행할 수 있습니다.

자세한 지침은 예측 코딩 모델 [만들기를 참조하세요.](predictive-coding-create-model.md)

## <a name="step-2-perform-the-first-training-round"></a>2단계: 첫 번째 교육 라운드 수행

모델을 만든 후의 다음 단계는 관련성 또는 관련성이 없는 항목에 레이블을 지정하여 첫 번째 교육 라운드를 완료하는 것입니다.

1. 검토 집합을 열고 **분석** 예측 코딩 관리(미리  >  **보기)를 클릭합니다.**

2. 예측 코딩 **모델(미리 보기)** 페이지에서 학습할 모델을 선택합니다.

3. 개요 **탭의** **1라운드에서** 다음 교육 **라운드 시작을 클릭합니다.**

   교육 **탭이** 표시되고 레이블을 지정하는 데 사용할 50개 항목이 포함되어 있습니다.

4. 각 문서를 검토한  다음  읽기 창 아래쪽의 관련성 또는 관련이 없는 단추를 선택하여 레이블을 지정합니다.

   ![각 문서에 관련성 또는 관련이 없는 것으로 레이블을 지정합니다.](..\media\TrainModel1.png)

5. 50개 항목에 모두 레이블을 지정한 후 마친 을 **클릭합니다.**

    시스템이 레이블 지정에서 "학습"하고 모델을 업데이트하는 데 몇 분 정도 걸립니다. 이 프로세스가 완료되면 모델에  대한 준비 상태가 예측 코딩 모델(미리 **보기) 페이지에** 표시됩니다.

자세한 지침은 예측 코딩 모델 [교육을 참조하세요.](predictive-coding-train-model.md)

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>3단계: 검토 집합의 항목에 예측 점수 필터 적용

한 번의 교육 라운드 임대를 수행한 후 검토 집합의 항목에 예측 점수 필터를 적용할 수 있습니다. 이렇게 하면 모델이 관련성이 있는 것으로 예측한 항목을 검토할 수 있습니다.   

1. 검토 집합을 열 수 있습니다.

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

자세한 지침은 검토 집합에 예측 [필터 적용을 참조하세요.](predictive-coding-apply-prediction-filter.md)

## <a name="step-4-perform-more-training-rounds"></a>4단계: 추가 교육 라운드 수행

더 많은 교육 라운드를 수행하여 검토 집합의 관련성 및 비관련 항목을 더 잘 예측하도록 모듈을 교육해야 합니다. 일반적으로 모델이 요구 사항을 충족하기에 충분히 안정화될 때까지 충분한 시간을 학습합니다.

자세한 내용은 추가 교육 [라운드 수행을 참조하세요.](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>5단계: 최종 예측 점수 필터를 적용하여 검토 우선 순위 지정

3단계의 지침을 반복하여 최종 예측 점수를 검토 집합에 적용하여 모든 교육 라운드를 완료하고 모델을 안정화한 후 관련 및 관련이 없는 항목의 검토 우선 순위를 지정합니다.

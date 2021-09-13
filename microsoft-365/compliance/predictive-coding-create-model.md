---
title: 2013에서 예측 코딩 모델 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 2013에서 예측 코딩 모델을 만드는 방법을 Advanced eDiscovery. 이 단계는 검토 집합에서 관련성 및 관련이 없는 콘텐츠를 식별하는 데 Advanced eDiscovery 기계 학습 기능을 사용하는 첫 번째 단계입니다.
ms.openlocfilehash: ed5092f2730ade5e349cec77e5c264e67d957927
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186092"
---
# <a name="create-a-predictive-coding-model-preview"></a>예측 코딩 모델 만들기(미리 보기)

가상화에서 예측 코딩의 기계 학습 기능을 사용하는 첫 번째 단계는 Advanced eDiscovery 코딩 모델을 만드는 것입니다. 모델을 만든 후 검토 집합에서 관련성 및 관련이 없는 콘텐츠를 식별하도록 학습할 수 있습니다.

예측 코딩 워크플로를 검토하기 위해 2013에서 예측 코딩에 [대해 Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>모델을 만들기 전에

- 예측 코딩 모델을 만들 수 있는 검토 집합에는 최소 2,000개 항목이 있어야 합니다.

- 모델을 만들기 전에 검토 집합에 모든 컬렉션을 커밋해야 합니다. 모델을 만든 후 검토 집합에 추가된 항목은 처리되지 않습니다. 모델에서 생성된 예측 점수가 할당되지 않습니다.

- 텍스트가 포함되지 않은 검토 집합의 항목은 모델에 의해 처리되거나 예측 점수가 할당되지 않습니다. 텍스트가 있는 항목은 컨트롤 집합 또는 교육 집합에 포함됩니다.

## <a name="create-a-model"></a>모델 만들기

1. 이 Microsoft 365 규정 준수 센터 사례를 Advanced eDiscovery 검토 집합 **탭을** 선택합니다.

2. 검토 집합을 열고 **분석** 예측 코딩 관리(미리  >  **보기)를 클릭합니다.**

   ![검토 집합에서 분석 드롭다운 메뉴를 클릭하여 예측 코딩 페이지로 이동합니다.](..\media\ManagePredictiveCoding.png)

3. 예측 코딩 **모델(미리 보기) 페이지에서** 새 모델을 **클릭합니다.**

4. 플라이아웃 페이지에서 모델의 이름과 선택적 설명을 입력합니다.

5. 원하는 경우 신뢰 수준 및 오류  여백과 관련된 고급 설정을 구성할 수 있습니다(플라이아웃 페이지에서 고급 옵션 클릭). 이러한 설정은 컨트롤 집합에 포함된 항목 수에 영향을 미치게 됩니다. 컨트롤 *집합은* 교육 프로세스 중에 모델이 교육 라운드 중에 수행하는 레이블이 있는 항목에 할당하는 예측 점수를 평가하는 데 사용됩니다. 조직에 문서 검토에 대한 신뢰 수준 및 오류의 여백에 대한 지침이 있는 경우 해당 상자에 지정합니다. 그렇지 않은 경우 기본 설정을 사용합니다.

6. **저장을** 클릭하여 모델을 만들 수 있습니다.

   시스템에서 모델을 준비하는 데 몇 분 정도 걸립니다. 준비가 된 후 첫 번째 교육을 수행할 수 있습니다.

## <a name="what-happens-after-you-create-a-model"></a>모델을 만든 후 발생하는 작업

모델을 만든 후 모델을 만들고 준비하는 동안 백그라운드에서 다음과 같은 상황이 발생합니다.

- 시스템은 컨트롤 집합에 대한 항목 수를 계산합니다. 이 크기는 검토 집합의 항목 수와 신뢰도 수준에 대한 설정 및 오류 여백을 기반으로 합니다. 컨트롤 집합의 항목은 임의로 선택되어 컨트롤 집합 항목으로 지정됩니다. 시스템에는 첫 번째 교육 라운드에 설정된 컨트롤 항목 10개가 포함됩니다.

- 시스템은 검토 집합에서 40개 항목을 임의로 선택하여 첫 번째 교육용 교육 집합에 포함됩니다. 따라서 첫 번째 교육에서는 레이블을 지정하기 위한 50개 항목( 교육 집합의 항목 40개 및 컨트롤 집합의 항목 10개)을 포함합니다.

## <a name="next-steps"></a>다음 단계

검토 집합에 대한 모델을 만든 후 다음 단계는 교육 라운드를 수행하여 조사와 관련된 콘텐츠를 식별하는 모델을 "교육"하는 것입니다. 자세한 내용은 예측 코딩 모델 [교육을 참조하세요.](predictive-coding-train-model.md)

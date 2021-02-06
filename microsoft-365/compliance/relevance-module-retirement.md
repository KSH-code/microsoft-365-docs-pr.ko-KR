---
title: Advanced eDiscovery에서와관성 모듈 사용 중지
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Advanced eDiscovery의 연결 모듈은 2021년 3월 10일에 사용 중지됩니다. 이 문서에서는 관련성 사용이 중지되기 전에 할 일에 대해 설명합니다. 특히 모델의 메타데이터를 유지할 수 있도록 일괄 계산을 실행하여 미완료 모델을 완료합니다.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122537"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Advanced eDiscovery에서 Relevance 모듈 사용 중지

2021년 3월 10일, Advanced eDiscovery에서 사용 중지됩니다. 이 사용 중지는 조직이 더 이상 관련성 모듈에 액세스할 수 없음(Advanced  >   eDiscovery 사례에서 검토 집합 관련성 관리로) 또는 기존 관련성 모델에 액세스할 수 없음을 의미합니다. 사용 중지되는 현재의 연결 모듈은 2021년 2분기 CY 2021의 새로운 예측 코딩 솔루션으로 대체됩니다. 이 새로운 기능을 통해 조직은 보다 쉽고 직관적인 워크플로에서 자체 예측 코딩 모델을 빌드할 수 있습니다.

예정된 사용 중지를 준비하기 위해 관련성 모듈을 사용하는 조직은 모든 기존 모델에 대해 일괄 계산을 실행하여 사용 중지 날짜 전에 모델의 출력을 내보내는 것이 좋습니다. 모델의 모든 관련성 점수는 해당 검토 집합에 영구적으로 저장되고 문서를 내보낼 때 액세스할 수 있습니다. 또한 해당 점수는 로드 파일에 메타데이터로 유지됩니다. 또한 관련성 점수에 따라 검토 집합의 콘텐츠를 필터링할 수 있으며 관련성 모델에 의해 생성되는 모든 메타데이터에 액세스할 수 있습니다.

## <a name="complete-unfinished-models"></a>완료되지 않은 모델 완료

미완료 관련성 모델의 경우 검토 집합의 문서에 모델을 적용할 수 있도록 평가, 교육 및 일괄 계산을 완료하십시오. 일괄 계산을 완료하면 관련성 모듈의 사용 중지 날짜 이후에 정보가 보존됩니다.

미완성 모델을 완료하는 단계는 다음과 같습니다.

1. 모델이 안정화되고 일괄 계산 준비가 될 때까지 모델을 교육합니다. 태그 [지정 및관련성 교육을 참조합니다.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   다음 스크린샷은 일괄 계산에 사용할 수 있는 모듈을 보여줍니다. 평가 및 교육이 완료된 후 다음 단계는 일괄 계산을 실행하는 것입니다.

   ![일괄 계산 준비가 완료된 모델의 스크린샷](../media/ReadyForBatchCalculation.png)

2. 일괄 처리 계산을 실행합니다. 일괄 [처리 계산 수행을 참조합니다.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. 일괄 계산이 성공적이지 확인 일괄 [계산 결과를 참조합니다.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)

미완료한 해당 모델 완료에 대한 도움말을 원할 경우 Microsoft 지원에 문의합니다.

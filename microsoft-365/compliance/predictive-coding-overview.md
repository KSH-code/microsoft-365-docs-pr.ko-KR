---
title: Advanced eDiscovery에 대한 예측 코딩 모듈(미리 보기)
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
description: Advanced eDiscovery의 새로운 예측 코딩 모듈은 기계 학습을 사용하여 검토 집합의 문서를 사례 또는 조사와 관련된 예측으로 분석합니다.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382976"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Advanced eDiscovery에 대한 예측 코딩 모듈(미리 보기)

Advanced eDiscovery의 새로운 예측 코딩 모듈을 사용하여 가장 관련성이 높은 문서로 시작하는 문서 검토의 우선 순위를 지정하는 모델을 만들고 빌드할 수 있습니다. 시작하기 위해 모델을 만들고 50개 문서만 레이블을 지정한 다음 모델 예측 점수로 문서를 필터링하여 관련성이 없는 문서를 검토할 수 있습니다.

다음은 워크플로에 대한 간략한 개요입니다.

1. 검토 집합에서 예측 코딩 모듈을 열 수 있습니다.

   ![검토에서 분석 드롭다운 목록을 클릭하여 예측 코딩 모듈로 이동](..\media\PredictiveCoding1.png)

2. 예측 **코딩** 모델 페이지에서 새 모델을  클릭하여 새 예측 코딩 모델을 만드십시오.

   ![새 모델 만들기](..\media\PredictiveCoding2.png)

3. 50개 이상의 문서를  관련성 또는 **관련성이 없는 문서로 레이블을 지정합니다.** 이 레이블 지정은 시스템을 교육하는 데 사용됩니다.

   ![관련이 있는 문서 또는 시스템 교육과 관련이 없는 문서 레이블 지정](..\media\PredictiveCoding3.png)

4. 모델에 **대한** 예측 점수 필터를 검토 집합에 적용합니다. 이렇게 하려면 다음을 수행합니다.

   1. 검토 집합에서 필터 를 **클릭합니다.**
   2. 필터 **플라이아웃** 페이지에서 **분석/ML 섹션을** 확장한 다음 적용할 모델에 대해 예측 점수 확인란을 선택합니다. 
   3. 예측 **점수 필터에서** 예측 점수를 지정합니다. 필터는 예측 점수와 일치하는 검토 집합의 문서를 표시합니다.

      ![문서를 필터링할 예측 점수 지정](..\media\PredictiveCoding4.png)

5. 모델의 성능, 상태 및 안정성을 모니터링합니다.

   ![모델의 성능, 상태 및 안정성 모니터링](..\media\PredictiveCoding5.png)

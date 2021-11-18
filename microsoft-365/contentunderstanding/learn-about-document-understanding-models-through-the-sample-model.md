---
title: Microsoft 365의 샘플 모델을 통해 문서 이해 모델을 SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 샘플 모델을 통해 문서 이해 모델에 대해 알아봅니다.
ms.openlocfilehash: 51eb92a2b6a511dd5b1340c9c435f63dd56299e5
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064430"
---
# <a name="learn-about-document-understanding-models-through-the-sample-model-in-microsoft-sharepoint-syntex"></a>Microsoft 365의 샘플 모델을 통해 문서 이해 모델을 SharePoint Syntex

SharePoint Syntex 모델을 만드는 방법을 보다 잘 이해할 수 있도록 검사하는 데 사용할 수 있는 샘플 모델을 제공합니다. 샘플 모델을 사용하여 분류자, 추출자 및 설명자와 같은 모델 구성 요소를 검토할 수도 있습니다. 샘플 파일을 사용하여 모델을 훈련 할 수도 있습니다.

## <a name="import-the-sample-model"></a>샘플 모델 가져오기

샘플 모델에 액세스 하려면 먼저 모델을 콘텐츠 센터로 가져와야 합니다.

1. 콘텐츠 센터에서 모델 목록을 보려면 **모델** 을 선택합니다.</br>
2. **모델** 페이지에서 **샘플 모델 가져오기** 를 선택합니다.</br>

    ![샘플 모델 가져오기.](../media/content-understanding/import-sample-model.png) </br>

3. 가져오기가 완료되면 **BenefitsChangeNotice** 모델 홈 페이지가 열립니다. 나중에 샘플 모델을 열어야 하는 경우 콘텐츠 센터의 모델 목록에서 이 작업을 수행할 수 있습니다. </br>

     ![샘플 홈 페이지.](../media/content-understanding/sample-home-page.png)</br>

샘플 모델 분석을 통해 모델을 구성하는 방법에 대한 이해를 할 수 있을 뿐만 아니라 작업 모델이 더 진행 되어 다음과 같은 작업을 수행하도록 할 수 있습니다.

- 다른 추출기 추가 예를 들어 *할인율* 을 추출 하는 항목을 추가합니다.
- 문서 라이브러리에 모델을 적용하고 교육 파일을 업로드 하여 모델이 파일을 분류하고 데이터를 추출하는 방법을 확인합니다.

## <a name="get-sample-models"></a>샘플 모델 사용

문서 이해 [모델의 다양한 사용 패턴을 SharePoint Syntex](https://github.com/pnp/syntex-samples)커뮤니티 샘플이 포함된 샘플 리포지토리의 샘플 리포지토리에 액세스할 수 있습니다. 이 리포지토리의 샘플에는 문서 이해 모델 파일과 모델을 학습하는 데 사용되는 파일이 모두 포함되어 있습니다. 가져온 후 이러한 모델을 사용하여 파일을 처리하고 분류자 및 추출기를 보고 편집할 수 있습니다.

## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)

[추출기 만들기](create-an-extractor.md)

[문서 이해 개요](document-understanding-overview.md)

[양식 처리 모델 만들기](create-a-form-processing-model.md)  

---
title: SharePoint Syntex에서 모델에 보존 레이블 적용
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
description: 2016년 8월 2일부로 하여금 모델에 보존 레이블을 적용하는 SharePoint Syntex.
ms.openlocfilehash: ed1df9a37f37bc23b11bb2d7ef24109340b253c9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195512"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>SharePoint Syntex에서 모델에 보존 레이블 적용

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Microsoft SharePoint Syntex의 모델에 [보존 레이블](../compliance/retention.md)을 쉽게 적용할 수 있습니다. 문서 이해 모델과 양식 처리 모델 모두에서 이 작업을 할 수 있습니다.

보존 레이블을 사용하여 모델이 식별하는 문서에 보존 설정을 적용할 수 있습니다.  예를 들어, 모델이 문서 라이브러리에 업로드된 *보험 통지* 문서를 식별할 뿐만 아니라, 지정된 기간 동안(예를 들어, 다음 5개월) 문서 라이브러리에서 이러한 문서를 삭제할 수 없도록 *비즈니스* 보존 태그를 적용합니다.

모델 홈페이지의 문서 설정을 통해 기존 보존 레이블을 모델에 적용할 수 있습니다. 

> [!Important]
> 문서 이해 모델에 적용하기 위해 보존 레이블을 사용하려면 [Microsoft 365 준수 센터에서 만들고 게시](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)해야 합니다.

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>문서 이해 모델에 보존 레이블 추가

1. 모델 홈페이지에서 **모델 설정** 을 선택합니다.</br>
2. **모델 설정** 의 **보안 및 준수** 섹션에서 **보존 레이블** 메뉴를 선택하여 모델에 적용 가능한 보존 레이블 목록을 확인합니다.</br>
 ![보존 레이블 메뉴.](../media/content-understanding/retention-labels-menu.png)</br> 
3. 모델에 적용할 보존 레이블을 선택하고 **저장** 을 선택 합니다.</br>

모델에 보존 레이블을 적용한 후, 다음에 적용할 수 있습니다.
- 새 문서 라이브러리
- 모델이 이미 적용된 문서 라이브러리
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>모델이 이미 적용된 문서 라이브러리에 보존 레이블 적용

문서 이해 모델이 이미 문서 라이브러리에 적용된 경우, 다음을 수행하여 보존 레이블 업데이트를 동기화하여 문서 라이브러리에 적용할 수 있습니다.</br>

1. 모델 홈페이지의 **이 모델을 사용하는 라이브러리** 섹션에서 보존 레이블 업데이트를 적용할 문서 라이브러리를 선택합니다. </br> 
2. **동기화** 를 선택합니다. </br>
 ![동기화 모델.](../media/content-understanding/sync-model.png)</br> 


업데이트를 적용한 후 모델에 동기화하면, 다음을 실행하여 이 업데이트가 적용되었는지 확인할 수 있습니다.

1. 컨텐츠 센터의 **이 모델이있는 라이브러리** 섹션에서 업데이트된 모델이 적용된 라이브러리를 클릭하세요. </br>
2. 문서 라이브러리 보기에서 정보 아이콘을 선택하여 모델 속성을 확인합니다.</br>  
3. **활성 모델** 목록에서 업데이트된 모델을 선택합니다.</br>
4. **보존 레이블** 섹션에서 적용된 보존 레이블의 이름이 나타납니다.</br>


문서 라이브러리의 모델 보기 페이지에서 새 **보존 레이블** 열이 표시됩니다.  모델이 해당 콘텐츠 유형에 속한 것으로 식별하는 파일을 분류 하고 라이브러리 보기에 나열하는 경우, 보존 레이블 열에 모델을 통해 적용된 보존 레이블 이름도 표시됩니다.


예를 들어, 모델이 식별하는 모든 *보험 통지* 문서에는 *비지니스* 보존 레이블도 적용되어 문서 라이브러리에서 5개월 동안 삭제되지 않습니다. 문서 라이브러리에서 파일을 삭제하려는 경우, 보존 레이블이 적용되었기 때문에 삭제가 허용되지 않는다는 오류가 표시됩니다.

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>양식 처리 모델에 보존 레이블을 추가하는 방법

> [!Important]
> 양식 처리 모델에 적용하기 위해 보존 레이블을 사용하려면 [Microsoft 365 준수 센터에서 만들고 게시](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)해야 합니다.

모델을 만들 때 양식 처리 모델에 보존 레이블을 적용하거나 기존 모델에 적용할 수 있습니다.

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>양식 처리 모델을 만들 때 보존 레이블을 추가하는 방법

1. [새 양식 처리 모델](./create-a-form-processing-model.md)을 만들 때 <b>고급 설정을 선택합니다.</b>
2. <b>고급 설정</b>의 <b>보존 레이블</b> 섹션에서 메뉴를 선택하고 모델을 적용하려는 보존 레이블을 선택합니다.</b>

 
     ![새 양식 처리 모델에 추가합니다.](../media/content-understanding/retention-label-forms.png)</br>

3.  나머지 모델 설정을 완료한 후 <b>만들기</b>를 선택하요 모델을 빌드합니다.

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>기존 양식 처리 모델에 보존 레이블을 추가하는 방법

기존 양식 처리 모델에 보존 레이블을 다양한 방법으로 추가할 수 있습니다.
- 문서 라이브러리의 자동화 메뉴를 통해
- 문서 라이브러리의 모델 활성화 설정을 통해 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>자동화 메뉴를 통해 기존 양식 처리 모델에 보존 레이블을 추가하는 방법

모델이 적용된 문서 라이브러리의 자동화 메뉴를 통해 소유한 기존 양식 처리 모델에 보존 레이블을 추가할 수 있습니다.


1. 양식 처리 모델이 적용된 문서 라이브러리에서 <b>자동화</b> 메뉴를 선택하고 <b>AI 작성기</b>를 선택한 다음 <b>양식 처리 모델 세부 정보 보기</b>를 선택합니다.

   ![메뉴 자동화.](../media/content-understanding/automate-menu.png)</br>

2. 모델 세부 정보의 <b>보존 레이블</b> 섹션에서 적용할 보존 레이블을 선택합니다.  그런 다음 <b>저장</b>을 선택합니다.

     ![기존 양식 처리 모델에 추가합니다.](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>활성 모델 설정에서 기존 양식 처리 모델에 보존 레이블을 추가하는 방법

모델이 적용된 문서 라이브러리의 모델 설정 활성화를 통해 소유한 기존 양식 처리 모델에 보존 레이블을 추가할 수 있습니다.

1. 모델이 적용된 SharePoint 문서 라이브러리에서 <b>활성 모델 보기</b> 아이콘을 선택하고 <b>활성 모델 보기</b>를 선택합니다.</b>

   ![활성 모델을 볼 수 있습니다.](../media/content-understanding/info-du.png)</br> 

2. <b>활성 모델</b>에서 보존 레이블을 적용할 양식 처리 모델을 선택합니다.

     ![모델 세부 정보.](../media/content-understanding/retention-label-model-details.png)</br> 


3. 모델 세부 정보의 <b>보존 레이블</b> 섹션에서 적용할 보존 레이블을 선택합니다.  그런 다음 <b>저장</b>을 선택합니다.

> [!NOTE]
> 모델 설정 창의 모델 소유자만 편집할 수 있습니다. 


## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)

[추출기 만들기](create-an-extractor.md)

[문서 이해 개요](document-understanding-overview.md)

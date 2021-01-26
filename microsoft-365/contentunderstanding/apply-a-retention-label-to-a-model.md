---
title: 문서 이해 모델에 보존 레이블 적용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 이 문서는 문서 이해 모델에 보존 레이블을 적용하는 방법에 대해 설명합니다.
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976558"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>문서 이해 모델에 보존 레이블 적용

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Microsoft SharePoint Syntex의 문서 이해 모델에 [보존 레이블](https://docs.microsoft.com/microsoft-365/compliance/retention)을 쉽게 적용할 수 있습니다.

보존 레이블을 사용하여 문서 이해 모델이 식별하는 문서에 보존 설정을 적용할 수 있습니다.  예를 들어, 모델이 문서 라이브러리에 업로드된 *보험 통지* 문서를 식별할 뿐만 아니라, 지정된 기간 동안(예를 들어, 다음 5개월) 문서 라이브러리에서 이러한 문서를 삭제할 수 없도록 *비즈니스* 보존 태그를 적용합니다.

모델 홈페이지의 문서 설정을 통해 기존 보존 레이블을 문서 이해 모델에 적용할 수 있습니다. 

> [!Important]
> 콘텐츠 이해 모델에 적용하기 위해 보존 레이블을 사용하려면 [Microsoft 365 준수 센터에서 만들고 게시](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)해야 합니다.

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>문서 이해 모델에 보존 레이블 추가

1. 모델 홈페이지에서 **모델 설정** 을 선택합니다.</br>
2. **모델 설정** 의 **보안 및 준수** 섹션에서 **보존 레이블** 메뉴를 선택하여 모델에 적용 가능한 보존 레이블 목록을 확인합니다.</br>
 ![보존 레이블 메뉴](../media/content-understanding/retention-labels-menu.png)</br> 
3. 모델에 적용할 보존 레이블을 선택하고 **저장** 을 선택 합니다.</br>

모델에 보존 레이블을 적용한 후, 다음에 적용할 수 있습니다.
- 새 문서 라이브러리
- 모델이 이미 적용된 문서 라이브러리
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>모델이 이미 적용된 문서 라이브러리에 보존 레이블 적용

문서 이해 모델이 이미 문서 라이브러리에 적용된 경우, 다음을 수행하여 보존 레이블 업데이트를 동기화하여 문서 라이브러리에 적용할 수 있습니다.</br>

1. 모델 홈페이지의 **이 모델을 사용하는 라이브러리** 섹션에서 보존 레이블 업데이트를 적용할 문서 라이브러리를 선택합니다. </br> 
2. **동기화** 를 선택합니다. </br>
 ![모델 동기화](../media/content-understanding/sync-model.png)</br> 


업데이트를 적용한 후 모델에 동기화하면, 다음을 실행하여 이 업데이트가 적용되었는지 확인할 수 있습니다.

1. 컨텐츠 센터의 **이 모델이있는 라이브러리** 섹션에서 업데이트된 모델이 적용된 라이브러리를 클릭하세요. </br>
2. 문서 라이브러리 보기에서 정보 아이콘을 선택하여 모델 속성을 확인합니다.</br>  
3. **활성 모델** 목록에서 업데이트된 모델을 선택합니다.</br>
4. **보존 레이블** 섹션에서 적용된 보존 레이블의 이름이 나타납니다.</br>


문서 라이브러리의 모델 보기 페이지에서 새 **보존 레이블** 열이 표시됩니다.  모델이 해당 콘텐츠 유형에 속한 것으로 식별하는 파일을 분류 하고 라이브러리 보기에 나열하는 경우, 보존 레이블 열에 모델을 통해 적용된 보존 레이블 이름도 표시됩니다.


예를 들어, 모델이 식별하는 모든 *보험 통지* 문서에는 *비지니스* 보존 레이블도 적용되어 문서 라이브러리에서 5개월 동안 삭제되지 않습니다. 문서 라이브러리에서 파일을 삭제하려는 경우, 보존 레이블이 적용되었기 때문에 삭제가 허용되지 않는다는 오류가 표시됩니다.

## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)

[추출자 만들기](create-an-extractor.md)

[문서 이해 개요](document-understanding-overview.md)



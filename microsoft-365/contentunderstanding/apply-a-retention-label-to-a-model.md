---
title: 문서에 보존 레이블 적용 모델 이해
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 이 문서에서는 문서에 보존 레이블을 적용 하는 방법을 설명 합니다.
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294926"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>문서에 보존 레이블 적용 모델 이해

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Microsoft SharePoint Syntex의 모델을 이해 하는 문서에 [보존 레이블을](https://docs.microsoft.com/microsoft-365/compliance/retention) 쉽게 적용할 수 있습니다.

보존 레이블을 사용 하면 문서에서 모델을 이해 하는 문서에 보존 설정을 적용할 수 있습니다.  예를 들어 모델이 문서 라이브러리에 업로드 되는 *보험 공지* 문서를 식별 하 고, 지정 된 기간 (예: 다음 5 개월) 동안 문서 라이브러리에서 이러한 문서를 삭제할 수 없도록 *비즈니스* 보존 태그를 적용 하려는 경우를 예로 들 수 있습니다.

모델의 홈 페이지에 있는 모델 설정을 통해 기존 보존 레이블을 문서에 대 한 이해 하기 위한 모델에 적용할 수 있습니다. 

> [!Important]
> 콘텐츠 이해 모델에 적용할 수 있는 보존 레이블을 [Microsoft 365 준수 센터에서 작성 하 고 게시](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)해야 합니다.

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>문서에 보존 레이블을 추가 하려면 모델 이해

1. 모델 홈 페이지에서 **모델 설정을**선택 합니다.</br>
2. **모델 설정**의 **보안 및 준수** 섹션에서 **보존 레이블** 메뉴를 선택 하 여 모델에 적용할 수 있는 보존 레이블 목록을 확인 합니다.</br>
 ![보존 레이블 메뉴](../media/content-understanding/retention-labels-menu.png)</br> 
3. 모델에 적용할 보존 레이블을 선택 하 고 **저장**을 선택 합니다.</br>

모델에 보존 레이블을 적용 한 후에는 다음에 적용할 수 있습니다.
- 새 문서 라이브러리
- 모델이 이미 적용 된 문서 라이브러리
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>모델이 이미 적용 된 문서 라이브러리에 보존 레이블 적용

문서 라이브러리에 모델 이해 모델이 이미 적용 되어 있는 경우 다음을 수행 하 여 보존 레이블 업데이트를 동기화 하 여 문서 라이브러리에 적용할 수 있습니다.</br>

1. 모델 홈 페이지의 **이 모델을 가진 라이브러리** 섹션에서 보존 레이블 업데이트를 적용할 문서 라이브러리를 선택 합니다. </br> 
2. **동기화**를 선택 합니다. </br>
 ![동기화 모델](../media/content-understanding/sync-model.png)</br> 


업데이트를 적용 하 고 모델에 동기화 한 후에는 다음을 수행 하 여 해당 업데이트가 적용 되었는지 확인할 수 있습니다.

1. 콘텐츠 센터의 **이 모델을 가진 라이브러리** 섹션에서 업데이트 된 모델이 적용 된 라이브러리를 클릭 합니다. </br>
2. 문서 라이브러리 보기에서 정보 아이콘을 선택 하 여 모델 속성을 확인 합니다.</br>  
3. **활성 모델** 목록에서 업데이트 된 모델을 선택 합니다.</br>
4. **보존 레이블** 섹션에 적용 된 보존 레이블의 이름이 표시 됩니다.</br>


문서 라이브러리의 모델 보기 페이지에 새 **보존 레이블** 열이 표시 됩니다.  모델에서 해당 콘텐츠 형식에 속하는 것으로 식별 되는 파일을 분류 하 여 라이브러리 보기에 나열 하면 보존 레이블 열에 모델을 통해 적용 된 보존 레이블의 이름도 표시 됩니다.


예를 들어 모델에서 식별 하는 모든 *보험 공지* 문서에는 *비즈니스* 보존 레이블도 적용 되므로 5 개월이 아닌 문서 라이브러리에서 삭제 되는 것을 방지할 수 있습니다. 문서 라이브러리에서 파일을 삭제 하려고 하면 적용 된 보존 레이블로 인해 허용 되지 않는 오류가 표시 됩니다.

## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)</br>
[추출기 만들기](create-an-extractor.md)</br>
[문서 이해 개요](document-understanding-overview.md)</br>
[양식 처리 모델 만들기](create-a-form-processing-model.md)  

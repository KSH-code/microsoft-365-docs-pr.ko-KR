---
title: 문서 라이브러리에 문서 이해 모델 적용 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: SharePoint 문서 라이브러리에 게시 된 모델을 적용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0658710704273ed04e9f2067413d1141773ef4aa
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612683"
---
# <a name="apply-a-document-understanding-model-preview"></a>문서 이해 모델 적용 (미리 보기)

> [!Note] 
> 이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

모델 이해 문서를 게시 한 후 Microsoft 365 테 넌 트에서 SharePoint 문서 라이브러리에이를 적용할 수 있습니다.

> [!Note]
> 액세스 권한이 있는 문서 라이브러리에만 모델을 적용할 수 있습니다.


## <a name="apply-your-model-to-a-document-library"></a>문서 라이브러리에 모델을 적용 합니다.

SharePoint 문서 라이브러리에 모델을 적용 하려면 다음을 수행 합니다.

1. 모델 홈 페이지의 **라이브러리에 모델 적용** 타일에서 **모델 게시**를 선택 합니다. 또는 **다음 모델** 의 라이브러리에서 **라이브러리 추가** 섹션을 선택할 수 있습니다. </br>

    ![라이브러리에 모델 추가](../media/content-understanding/apply-to-library.png)</br>

2. 그런 다음 모델을 적용 하려는 문서 라이브러리가 포함 된 SharePoint 사이트를 선택할 수 있습니다. 사이트가 목록에 표시 되지 않으면 검색 상자를 사용 하 여 해당 사이트를 찾습니다.</br>

    ![사이트 선택](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > 모델을 적용할 문서 라이브러리에 대 한 목록 사용 권한 *관리* 또는 *편집* 권한이 있어야 합니다.</br>

3. 사이트를 선택한 후에는 모델을 적용할 문서 라이브러리를 선택 해야 합니다. 이 예제에서는 *Contoso 사례 추적* 사이트에서 *문서* 문서 라이브러리를 선택 합니다.</br>

    ![문서 라이브러리 선택](../media/content-understanding/select-doc-library.png)</br>

4. 모델은 콘텐츠 형식에 연결 되기 때문에 라이브러리에 적용 하면 열로 표시 된 레이블이 추출한 레이블로 콘텐츠 형식에 대 한 보기가 생성 됩니다. 이 보기는 기본적으로 라이브러리의 기본 보기가 되며, **고급 설정을** 선택 하 고 **이 새 보기를 기본값으로**선택을 취소 하 여 기본 보기로 설정 하지 않도록 선택할 수도 있습니다.</br>

    ![라이브러리 보기](../media/content-understanding/library-view.png)</br>

5. 라이브러리에 모델을 적용 하려면 **추가** 를 선택 합니다. 
6. 모델 홈 페이지의 **이 모델을 가진 라이브러리** 섹션에 나열 된 SharePoint 사이트의 URL이 표시 됩니다.</br>

    ![라이브러리 보기](../media/content-understanding/selected-library.png)</br>

7. 문서 라이브러리로 이동 하 여 모델의 문서 라이브러리 보기에 있는지 확인 합니다. 문서 라이브러리 이름 옆에 있는 정보 단추를 선택 하면 모델이 문서 라이브러리에 적용 되었음을 알리는 메시지가 표시 됩니다.

    ![라이브러리 보기](../media/content-understanding/info-du.png)</br> 


문서 라이브러리에 모델을 적용 한 후에는 사이트에 문서 업로드를 시작 하 고 결과를 확인할 수 있습니다.

모델은 모델의 연결 된 콘텐츠 형식을 가진 모든 파일을 식별 하 고 보기에 나열 합니다. 모델에 추출기가 있으면 각 파일에서 추출 하는 데이터에 대 한 열이 보기에 표시 됩니다.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>문서 라이브러리에 이미 있는 파일에 모델 적용

적용 된 모델을 적용 한 후에 문서 라이브러리에 업로드 된 모든 파일을 처리 하는 동안에는 다음을 수행 하 여 모델을 적용 하기 전에 문서 라이브러리에 있던 파일에서 모델을 실행할 수도 있습니다.

1. 문서 라이브러리에서 모델에 따라 처리할 파일을 선택 합니다.
2. 파일을 선택한 후 **분류 및 추출** 이 문서 라이브러리 리본 메뉴에 표시 됩니다. **분류 및 압축 해제를**선택 합니다.
3. 선택한 파일이 처리할 큐에 추가 됩니다.

      ![분류 및 추출](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)</br>
[추출기 만들기](create-an-extractor.md)</br>
[문서 이해 개요](document-understanding-overview.md)</br>
[양식 처리 모델 만들기](create-a-form-processing-model.md)  





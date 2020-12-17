---
title: 문서 라이브러리에 문서 이해 모델 적용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SharePoint 문서 라이브러리에 게시된 모델을 적용하는 방법 알아보기
ms.openlocfilehash: 9c99ede49633b5ae70cbb67c30d83c111084df95
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701144"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint 구문에서 문서 이해 모델 적용

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

문서 이해 모델을 게시한 후, Microsoft 365 테넌트에서 하나 이상의 SharePoint 문서 라이브러리에 이를 적용할 수 있습니다.

> [!NOTE]
> 액세스할 수 있는 문서 라이브러리에만 모델을 적용할 수 있습니다.


## <a name="apply-your-model-to-a-document-library"></a>문서 라이브러리에 모델을 적용합니다.

SharePoint 문서 라이브러리에 모델 적용하기:

1. 모델 홈페이지의 **라이브러리에 모델 적용** 타일에서 **모델 게시** 를 선택합니다. 또는 **이 모델 라이브러리** 섹션에서 **+라이브러리 추가** 를 선택할 수 있습니다. </br>

    ![라이브러리에 모델 추가](../media/content-understanding/apply-to-library.png)</br>

2. 그런 다음, 모델을 적용하려는 문서 라이브러리가 포함된 SharePoint 사이트를 선택할 수 있습니다. 사이트가 목록에 표시되지 않는 경우, 검색 상자를 사용하여 찾습니다.</br>

    ![사이트 선택](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > 모델을 적용할 문서 라이브러리에 대한 *목록 관리* 권한 또는 *편집* 권한이 있어야 합니다.</br>

3. 사이트를 선택한 후, 모델을 적용할 문서 라이브러리를 선택합니다. 샘플에서 *Contoso 사례 추적* 사이트의 *Documents* 문서 라이브러리를 선택합니다.</br>

    ![문서 라이브러리 선택](../media/content-understanding/select-doc-library.png)</br>

4. 모델이 콘텐츠 유형에 연결되어 있으므로 라이브러리에 적용하면 추출한 레이블이 열로 표시되는 컨텐츠 유형 및 보기가 추가됩니다. 이 보기는 기본적으로 라이브러리의 기본 보기이지만, **고급 설정** 을 선택하고 **이 새 보기를 기본값으로 설정** 을 선택 취소하여 선택적으로 기본 보기가되지 않도록 선택할 수 있습니다.</br>

    ![라이브러리 보기](../media/content-understanding/library-view.png)</br>

5. 라이브러리에 모델을 적용하려면 **추가** 를 선택합니다. 
6. 모델 홈페이지의 **모델이있는 라이브러리** 섹션에서 나열된 SharePoint 사이트의 URL이 표시되어야 합니다.</br>

    ![선택된 라이브러리](../media/content-understanding/selected-library.png)</br>

7. 문서 라이브러리로 이동하여 모델의 문서 라이브러리 보기에 있는지 확인합니다. 문서 라이브러리 이름 옆에 있는 정보 단추를 선택하면 모델이 문서 라이브러리에 적용되었다는 메시지가 표시됩니다.

    ![정보 보기](../media/content-understanding/info-du.png)</br> 


문서 라이브러리에 모델을 적용한 후, 사이트에 문서 업로드를 시작하고 결과를 볼 수 있습니다.

모델은 모델에 연결된 콘텐츠 유형이 있는 모든 파일을 식별하고 보기에 나열합니다. 모델에 추출기가 있는 경우, 각 파일에서 추출하는 데이터에 대한 열이 보기에 표시됩니다.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>문서 라이브러리에 이미 있는 파일에 모델 적용

적용된 모델이 문서 라이브러리에 적용된 후 문서 라이브러리에 업로드 한 모든 파일을 처리하는 동안, 다음을 수행하여 모델이 적용되기 전에 문서 라이브러리에 이미 있는 파일에 대해 모델을 실행할 수도 있습니다.

1. 문서 라이브러리에서 모델이 처리하려는 파일을 선택합니다.
2. 파일을 선택한 후 **분류 및 추출** 이 문서 라이브러리 리본에 나타납니다. **분류 및 추출** 을 선택합니다.
3. 선택한 파일이 처리할 큐에 추가됩니다.

      ![분류 및 추출](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> 개별 파일을 라이브러리에 복사하여 모델에 적용할 수 있지만 폴더는 적용할 수 없습니다.

## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)

[추출기 만들기](create-an-extractor.md)

[문서 이해 개요](document-understanding-overview.md)



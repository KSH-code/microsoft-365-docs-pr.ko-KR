---
title: SharePoint Syntex 문서 이해 모델 REST API
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
ms.localizationpriority: high
description: SharePoint Syntex 문서 이해 모델 REST API의 개요입니다.
ms.openlocfilehash: 882dcdbe3561803d20d698e5d1510dd5232fbbe5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163376"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>SharePoint Syntex 문서 이해 모델 REST API

SharePoint REST 인터페이스를 사용하여 문서 이해 모델을 만들고, 모델을 하나 이상의 라이브러리에 적용하거나 제거하고, 모델에 대한 정보를 가져오거나 업데이트할 수 있습니다. 

SharePoint Online(및 SharePoint 2016 이상 온-프레미스) REST 서비스는 OData $batch 쿼리 옵션을 사용하여 여러 요청을 서비스에 대한 단일 호출로 결합하도록 지원합니다. 

코드 샘플에 대한 자세한 내용 및 링크를 보려면 [REST API를 사용하여 일괄 처리 요청](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)을 참조하세요.

## <a name="prerequisites"></a>필수 조건

시작하기 전에 다음 사항을 잘 알고 있는지 확인합니다.

- [SharePoint REST 서비스에 대해 알아보기](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [SharePoint REST 끝점을 사용하여 기본 작업 완료](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>REST 명령

다음 REST 명령을 Syntex 문서 이해 모델 작업에 사용할 수 있습니다.

- [모델 만들기](rest-createmodel-method.md) - 모델 및 관련 콘텐츠 형식을 만듭니다.
- [GetByUniqueId](rest-getbyuniqueid-method.md) – SharePoint Syntex 문서 이해 모델에 대한 정보를 가져오거나 업데이트합니다.
- [GetByTitle](rest-getbytitle-method.md) – 모델 제목을 사용하여 SharePoint Syntex 문서 이해 모델에 대한 정보를 가져오거나 업데이트합니다.
- [모델 적용](rest-applymodel-method.md) – 학습된 문서 이해 모델을 하나 이상의 라이브러리에 적용하거나 동기화합니다.
- [모델 및 라이브러리 정보 가져오기](rest-getmodelandlibraryinfo.md) – 모델 및 모델이 적용된 라이브러리에 대한 정보를 가져옵니다.
- [UpdateModelSettings](rest-updatemodelsettings-method.md) – SharePoint Syntex 문서 이해 모델에 대해 사용 가능한 모델 설정(관련 보존 레이블 및 모델 설명)을 업데이트합니다.
- [BatchDelete](rest-batchdelete-method.md) – 하나 이상의 라이브러리에서 적용된 문서 이해 모델을 제거합니다.
- [파일 분류 요청 만들기](rest-createclassificationrequest.md) – 적용된 모델을 사용하여 지정된 파일 또는 파일을 분류하는 요청을 만듭니다.
- [폴더 분류 요청 생성](rest-createclassificationrequest.md) - 적용된 모델을 사용하여 전체 폴더를 분류하는 요청을 생성합니다.

## <a name="scenarios"></a>시나리오

메서드 이름으로는 직관적이지 않은 다음 시나리오 예제를 확인합니다. 자세한 내용은 각 문서를 참조하세요.

모델 만들기 메서드는 모델 개체 및 관련 콘텐츠 형식만 만듭니다. 라이브러리에 적용하려면 먼저 콘텐츠 센터에서 모델을 학습시켜야 합니다.

모델 적용 메서드는 문서를 분류하고 선택적으로 추가 정보를 추출하도록 대상 라이브러리에서 모델을 구성하는 데 사용됩니다. 또한 이 API는 모델을 여러 라이브러리에 적용하는 일괄 처리를 지원합니다.

모델 제거 메서드는 이전에 적용된 하나 이상의 라이브러리에서 모델을 제거합니다. 모델을 삭제하려면 먼저 모델이 적용된 모든 라이브러리에서 제거되어야 합니다.


## <a name="see-also"></a>참고 항목

[문서 이해 개요](../document-understanding-overview.md)


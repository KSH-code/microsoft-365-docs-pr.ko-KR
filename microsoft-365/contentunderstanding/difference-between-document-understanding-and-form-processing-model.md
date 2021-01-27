---
title: 문서 이해와 양식 처리 모델의 차이
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
description: 문서 이해 모델과 양식 처리 모델의 주요 차이를 설명합니다.
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975880"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>문서 이해와 양식 처리 모델의 차이 


Microsoft SharePoint Syntex의 콘텐츠 이해를 통해 SharePoint 문서 라이브러리에 업로드되는 문서를 식별 및 분류하고 각 파일에서 관련 정보를 추출할 수 있습니다.  예를 들어 파일이 SharePoint 문서 라이브러리에 업로드되면 *구매 주문서* 로 식별된 모든 파일이 이와 같이 분류된 다음 사용자 지정 문서 라이브러리 보기에 표시됩니다. 또한 각 파일에서 특정 정보(예: *PO 번호* 및 *전체l*)를 가져와 문서 라이브러리 보기에 열로 표시할 수 있습니다. 

컨텐츠 이해를 통해 *모듈* 을(를) 생성하여 필요한 정보를 식별하고 추출할 수 있습니다. 모델은 검색, 비즈니스 프로세스, 컴플라이언스 등의 비즈니스 문제를 해결하는 데 도움이 되는 가치를 지니고 있습니다.

사용할 수 있는 두 가지 모델 유형은 다음과 같습니다.

- [문서 이해 모델](document-understanding-overview.md)
- [양식 처리 모델](form-processing-overview.md)

두 모델은 일반적으로 동일한 목적으로 사용되지만, 아래에 나열된 주요 차이점은 사용할 수 있는 모델에 영향을 미칩니다.

> [!NOTE]
> 양식 처리 및 문서 이해 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)를 참조하세요.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>구조화된 콘텐츠와 구조화되지 않은 콘텐츠 및 반구조화된 콘텐츠가 비교됩니다.

문서 이해 모델을 사용하여 편지나 계약서와 같은 비정형 문서로부터 추출하려는 텍스트 엔터티가 문서의 문장이나 특정 영역에 있는 데이터를 식별하고 추출합니다. 예를 들어, 비정형 문서는 다양한 방법으로 작성할 수 있는 계약 갱신 서한이 될 수 있습니다. 그러나 텍스트 문자열 *서비스 시작 날짜* 와 실제 날짜와 같은 정보는 각 계약 갱신 문서의 본문에 일관성 있게 존재합니다.

양식 처리 모델을 사용하여 파일을 식별하고 양식 또는 송장과 같은 구조화된 또는 반구조화된 문서에서 데이터를 추출합니다. 양식 처리 모델은 예제 문서에서 양식의 레이아웃을 이해하고 유사한 위치에서 추출해야 하는 데이터를 찾는 방법을 학습하도록 훈련되었습니다. 일반적으로 양식에는 엔터티가 동일한 위치에 있는 보다 구조화된 레이아웃(예: 세금 양식의 주민 등록 번호)을 가지고 있습니다.

> [!NOTE]
> 문서 이해 모델을 작성하거나 SharePoint 문서 라이브러리에 적용하려면 컨텐츠 센터 사이트에 대한 액세스 권한이 있어야 합니다. 


## <a name="where-models-are-created"></a>모델이 생성되는 위치

문서 이해 모델은 SharePoint 컨텐츠 센터 사이트에서 작성 및 관리됩니다. 

> [!NOTE]
> 입력 문서에 대한 자세한 내용은 [양식 처리 모델 요구 사항 및 제한](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)을(를) 참조하시기 바랍니다. 

양식 처리 모델은 PowerApp [AI Builder](https://docs.microsoft.com/ai-builder/overview)에서 만들어지지만, 생성은 SharePoint 문서 라이브러리에서 직접 시작됩니다. 사용자가 양식 처리 모델을 만들려면 문서 라이브러리에서 양식 처리 모델 생성을 사용하도록 설정해야 합니다. 관리자는 관리 설정을 이해하는 콘텐츠에서 양식 처리 모델 만들기를 사용하도록 설정할 수 있습니다. 양식 처리 모델은 PowerAutomate 흐름을 사용하여 파일을 문서 라이브러리에 업로드할 때 파일을 처리합니다.

문서 이해 모델을 생성할 때 SharePoint 컨텐츠 유형 갤러리에 저장되는 새 [SharePoint 컨텐츠 유형](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)을 생성합니다. 또는 필요한 경우 기존 콘텐츠 유형을 사용하여 모델을 정의할 수 있습니다.

양식 처리 모델도 새 [SharePoint 컨텐츠 유형](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)을 생성하고 SharePoint 컨텐츠 유형 갤러리에도 저장됩니다.

## <a name="where-they-can-be-applied"></a>적용할 수 있는 위치입니다.

액세스 권한이 있는 SharePoint 문서 라이브러리에 문서 이해 모델을 적용할 수 있습니다. 콘텐츠 센터를 사용하여 문서 이해 모델을 작성한 후 다른 문서 라이브러리에 적용합니다. 콘텐츠 센터는 문서 이해 모델의 사용 방법과 적용 위치를 보다 중앙에서 제어할 수 있도록 합니다. 또한 이 정보는 컨텐츠 센터로 롤업해야 합니다.

양식 처리 모델은 현재 사용자가 만든 SharePoint 문서 라이브러리에만 적용할 수 있습니다. 이렇게 하면 사이트에 대한 액세스 권한을 가진 라이선스 사용자가 양식 처리 모델을 만들 수 있습니다. 관리자가 SharePoint 문서 라이브러리에서 양식 처리를 사용하도록 설정해야 라이선스가 부여된 사용자가 사용할 수 있습니다.

 ## <a name="see-also"></a>참고 항목
[교육: AI 작성기를 사용하여 비즈니스 성과 개선](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[문서 이해 개요](document-understanding-overview.md)

[양식 처리 개요](form-processing-overview.md)

[SharePoint Syntex 소개](index.md)

---
title: 문서 이해 및 양식 처리 모델의 차이점 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 문서 이해 및 양식 처리 모델 간의 주요 차이점에 대해 설명 합니다.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537434"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>문서 이해 및 양식 처리 모델의 차이점 (미리 보기)

> [!Note] 
> 이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.

Project Cortex의 콘텐츠 이해를 통해 SharePoint 문서 라이브러리에 업로드 되는 문서를 식별 하 고 분류할 수 있을 뿐만 아니라 각 파일에서 관련 정보를 추출 하는 데 도움이 됩니다.  예를 들어 파일이 SharePoint 문서 라이브러리에 업로드 되 면 *구매 주문* 으로 식별 되는 모든 파일이 해당 파일을 표시 되는 사용자 지정 문서 라이브러리 보기에 표시 되는 것 처럼 분류 됩니다. 또한 각 파일 (예: *PO 번호* 및 *합계*)에서 특정 정보를 가져오고 문서 라이브러리 보기의 열에 표시할 수 있습니다. 


콘텐츠 이해를 통해 *모델* 을 만들어 필요한 정보를 식별 하 고 추출할 수 있습니다.  사용할 수 있는 모델에는 다음과 같은 두 가지 유형이 있습니다.

- [문서 이해 모델](document-understanding-overview.md)
- [양식 처리 모델](form-processing-overview.md)

일반적으로 동일한 용도로 두 모델을 모두 사용 하지만, 사용 하도록 선택할 수 있는 주요 차이점이 있습니다.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>구조적이 고 구조화 및 반구조적 콘텐츠

문서 이해 모델을 사용 하 여 추출할 텍스트 엔터티가 문서의 문장이 나 특정 영역에 위치할 수 있는 문자 또는 계약과 같은 구조화 되지 않은 문서에서 데이터를 식별 하 고 추출 합니다. 예를 들어, 구조화 되지 않은 문서는 다양 한 방식으로 작성할 수 있는 계약 갱신 문자임이 될 수 있습니다. 그러나 각 계약 갱신 문서의 본문에 일관 되 게 제공 되는 정보 (예: 텍스트 문자열 "서비스 시작 날짜"와 실제 날짜)가 여기에 해당 됩니다.   

양식 처리 모델을 사용 하 여 파일을 식별 하 고, 일반 키-값 쌍 (예 *: 10/1/2020*) * 또는 테이블 데이터를 사용할 수 있는 양식 또는 송장 등의 구조적 또는 반구조적 문서에서 데이터를 추출 합니다. 예를 들어 양식 처리를 위한 좋은 방법은 클라이언트에서 문서 레이아웃의 같은 영역에 있는 특정 필드에 대 한 정보 (예: *이름*, *전화 번호*, *전체 비용*등)를 제공 해야 하는 회사의 주문 요청 양식입니다.  세금 양식은 구조화 된 문서를 예로 들 수 있습니다. 

## <a name="where-they-are-created"></a>생성 위치

문서 이해 모델은 SharePoint 콘텐츠 센터 사이트에서 만들어지고 관리 됩니다. 콘텐츠 센터 사이트에 액세스 하 여 모델을 이해 하는 문서를 만들거나 SharePoint 문서 라이브러리에이를 적용 해야 합니다. 

모델을 이해 하는 문서를 만드는 경우 SharePoint 콘텐츠 형식 갤러리에 저장 되는 [sharepoint 콘텐츠 형식을](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) 새로 만듭니다. 필요한 경우 기존 콘텐츠 형식을 사용 하 여 모델을 정의할 수도 있습니다.

양식 처리 모델은 PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)에서 만들어지지만 SharePoint 문서 라이브러리에서 직접 만들 수 있습니다. 사용자가 양식 처리 모델을 만들기 위해 문서 라이브러리에서 양식 처리 모델 만들기를 사용 하도록 설정 해야 하 고 관리자가 관리자 설정 이해 콘텐츠를 통해이 작업을 수행할 수 있습니다. 양식 처리 모델에서는 파일을 문서 라이브러리에 업로드 한 경우이를 처리 하기 위해 PowerAutomate 흐름을 사용 합니다.

또한 양식 처리 모델은 SharePoint 콘텐츠 형식 갤러리에도 저장 되는 새 [SharePoint 콘텐츠 형식을](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)만듭니다.

## <a name="where-they-can-be-applied"></a>적용할 수 있는 위치

문서를 이해 하는 데 사용할 수 있는 다양 한 SharePoint 문서 라이브러리에이 모델을 적용할 수도 있습니다. 콘텐츠 센터를 사용 하 여 문서 이해 모델을 만들 수 있을 뿐만 아니라 다른 문서 라이브러리에도 적용할 수도 있습니다. 콘텐츠 센터를 통해 문서를 이해 하는 방법을 보다 중앙에서 제어할 수 있으며,이 정보는 콘텐츠 센터에 롤업 되기 때문입니다.

양식 처리 모델은 현재 만들어진 SharePoint 문서 라이브러리에만 적용할 수 있습니다. 이렇게 하면 사이트에 대 한 액세스 권한이 있는 라이선스가 부여 된 모든 사용자가 양식 처리 모델을 만들 수 있습니다.




 ## <a name="see-also"></a>참고 항목
[교육: AI Builder를 사용 하 여 비즈니스 성과 개선](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[분류자 만들기](create-a-classifier.md)</br>
[추출기 만들기](create-an-extractor.md)</br>
[문서 이해 모델 적용](apply-a-model.md)</br>
[양식 처리 모델 만들기](create-a-form-processing-model.md)</br>



  
  




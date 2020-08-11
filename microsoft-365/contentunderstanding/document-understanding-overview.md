---
title: 문서 이해 개요 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex에서 이해 하는 문서에 대 한 개요를 가져옵니다.
ms.openlocfilehash: bdebc8a8726a7b9a77eb9a1095f83e937cf36cb1
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612717"
---
# <a name="document-understanding-overview-preview"></a>문서 이해 개요 (미리 보기)
> [!Note] 
> 프로젝트 Cortex 현재 미리 보기에 있습니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

문서 이해에서는 AI 모델을 사용 하 여 파일 분류를 자동화 하 고 정보를 추출 합니다. 문자 또는 계약과 같은 구조화 되지 않은 문서에서 가장 잘 작동 합니다. 문서에는 구 또는 패턴을 기반으로 식별 가능한 텍스트가 있어야 합니다. 식별 된 텍스트는 파일 형식 (분류)과 추출할 대상 (추출기)을 모두 지정할 수 있습니다.

문서 이해 모델은 콘텐츠 센터 라는 유형의 SharePoint 사이트에서 만들어지고 관리 됩니다. SharePoint 문서 라이브러리에 적용 된 모델은 추출 된 정보를 저장할 열이 포함 된 콘텐츠 형식에 연결 됩니다. 만드는 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장 됩니다. 스키마를 사용 하기 위해 기존 콘텐츠 형식을 사용 하도록 선택할 수도 있습니다.

문서에 *분류자* 와 *추출기* 를 추가 하 여 다음 작업을 수행할 수 있습니다. 

- 분류자는 문서 라이브러리로 업로드 되는 문서를 식별 하 고 분류 하는 데 사용 됩니다. 예를 들어 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신* 문서를 식별 하기 위해 "교육" 할 수 있습니다. 계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의 합니다.

- 추출기이 문서에서 정보를 가져옵니다. 예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에 대해 각 계약 갱신 문서에 대 한 *서비스 시작 날짜* 와 *클라이언트* 도 표시 되는 열이 보기에 표시 됩니다. 

예제 파일을 사용 하 여 모델의 분류자 및 추출기을 훈련 하 고 테스트 합니다. 예제 파일에서는 파일에서 데이터를 식별 하 고 추출 하려고 할 때 확인할 대상의 모델 예를 제공 합니다. 예를 들어 회사에서 사용 하는 계약 갱신 문서의 예를 포함 하 여 계약 갱신 분류자 및 추출기을 교육 합니다. 예제 파일을 사용 하 여 모델의 효율성을 테스트할 수도 있습니다.

모델을 게시 한 후 콘텐츠 센터를 사용 하 여 액세스 권한이 있는 SharePoint 문서 라이브러리에 적용 합니다.  


## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)</br>
[추출기 만들기](create-an-extractor.md)</br>
[콘텐츠 센터 만들기](create-a-content-center.md) 
 [양식 처리 모델 만들기](create-a-form-processing-model.md)</br>
[모델 적용](apply-a-model.md)   
[문서 이해와 양식 처리 모델의 차이점](difference-between-document-understanding-and-form-processing-model.md)  
[양식 처리 개요](form-processing-overview.md)





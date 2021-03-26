---
title: 문서 이해 개요
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
description: Microsoft SharePoint 구문에서 문서 이해 개요 얻기
ms.openlocfilehash: 73e217e458fb9e1ccad8b64ffc81a6c9522a04f4
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222758"
---
# <a name="document-understanding-overview"></a>문서 이해 개요


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

문서 이해는 파일 분류와 정보 추출을 자동화 하기 위해 인공 지능(AI) 모델을 사용합니다. 편지나 계약서와 같이 구조화 되지 않은 문서에 가장 적합합니다. 이러한 문서에는 구문 또는 패턴을 기반으로 식별할 수 있는 텍스트가 있어야 합니다. 식별 된 텍스트는 파일 형식(분류자)과 추출 하려는 대상(추출자)을 지정합니다.

> [!NOTE]
> 문서 이해 시나리오 예제에 대한 자세한 내용은 [SharePoint Syntex 채택: 시작 가이드](./adoption-getstarted.md)를 참조하세요.

문서 이해 모델은 *콘텐츠 센터* 라는 SharePoint 사이트 형식에서 만들어지고 관리됩니다. SharePoint 문서 라이브러리에 적용 되는 경우 모델은 추출되는 정보를 저장하기 위한 열이 있는 콘텐츠 유형과 연결이 되어 있습니다. 사용자가 만든 콘텐츠 형식은 SharePoint 콘텐츠 형식 갤러리에 저장됩니다. 기존 콘텐츠 유형을 사용하여 해당 스키마를 사용하도록 선택할 수도 있습니다.

> [!NOTE]
> 읽기 전용 또는 봉인된 내용 유형은 업데이트할 수 없으므로 모델에서 사용할 수 없습니다.

문서 이해 모델에 *분류자* 및 *추출자* 를 추가하여 다음을 실행합니다. 

- 분류자는 문서 라이브러리에 업로드 되는 문서를 식별하고 분류하는 데 사용 됩니다. 예를 들어, 분류자는 라이브러리에 업로드 되는 모든 *계약 갱신* 을 식별하도록 “성향 습득” 할 수 있습니다. 계약 갱신 콘텐츠 형식은 사용자가 분류자를 만들 때 정의합니다.

- 추출자가 이 문서에서 정보를 가져옵니다. 예를 들어 문서 라이브러리에서 식별 된 모든 계약 갱신 문서에서 각 계약 갱신 문서에 대한 *서비스 시작 날짜* 및 *클라이언트* 를 보도록 사용자 보기의 열을 디스플레이 합니다. 

예제 파일을 사용하여 모델에서 분류자와 추출자를 성향 습득하고 테스트 할 수 있습니다. 예제 파일에서는 파일에서 데이터를 식별하고 추출하려고 할 때 검색할 항목의 모델 예제를 제공합니다. 예를 들어, 사용자의 회사가 사용하는 계약 갱신 문서 예제를 사용하여 계약 갱신 분류자와 추출자를 성향 습득 할 수 있습니다. 예제 파일을 사용하여 모델의 효율성을 테스트 할 수 있습니다.

모델을 게시 한 후 콘텐츠 센터를 사용하여 액세스 권한이 있는 모든 SharePoint 문서 라이브러리에 적용 합니다.  

### <a name="file-limitations"></a>파일 제한 사항

문서 이해 모델에서는 OCR(광학 인식) 기술을 사용하여 예제 파일이 있는 모델을 교육하고 문서 라이브러리의 파일에 대해 모델을 실행할 때 모두 PDF, 이미지 및 TIFF 파일을 스캔합니다.

Microsoft Office 텍스트 기반 파일과 OCR로 스캔한 파일(PDF, 이미지 또는 TIFF)과 관련하여 다음과 같은 차이점에 유의하세요.

- Office 파일: 교육 중 및 문서 라이브러리의 파일에 대해 실행할 때 64K자로 잘라냅니다.
- OCR로 스캔한 파일: 20페이지 제한이 있습니다.  

#### <a name="supported-file-types"></a>지원되는 파일 형식

문서 이해 모델에서는 다음 파일 형식을 지원합니다.

- doc
- docx
- eml
- heic
- heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)

[추출자 만들기](create-an-extractor.md)

[콘텐츠 센터 만들기](create-a-content-center.md)

[양식 처리 모델 만들기](create-a-form-processing-model.md)

[모델 적용](apply-a-model.md)   

[문서 이해와 양식 처리 모델의 차이](difference-between-document-understanding-and-form-processing-model.md)
  
[양식 처리 개요](form-processing-overview.md)

[SharePoint Syntex 접근성 모드](accessibility-mode.md)
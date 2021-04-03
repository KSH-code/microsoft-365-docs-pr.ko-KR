---
title: 검토 집합에서 문서 내보내기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 프레젠테이션 또는 외부 검토를 위해 고급 eDiscovery 검토 집합에서 콘텐츠를 선택하고 내보내는 방법을 학습합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581026"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Advanced eDiscovery의 검토 집합에서 문서 내보내기

내보내기 기능을 사용하면 Advanced eDiscovery의 검토 집합에서 문서를 내보낼 때 다운로드 패키지에 포함된 콘텐츠를 사용자 지정할 수 있습니다.

검토 집합에서 문서를 내보내는 경우:

1. Microsoft 365 규정 준수 센터에서 고급 eDiscovery  사례를 열고 검토 집합 탭을 선택한 다음 내보낼 검토 집합을 선택합니다.

2. 검토 집합에서 작업 **내보내기 를**  >  **클릭합니다.**

   내보내기 도구에는 내보내기 구성 설정이 있는 플라이아웃 페이지가 표시됩니다. 일부 옵션은 기본적으로 선택되지만 변경할 수 있습니다. 구성할 수 있는 내보내기 옵션에 대한 설명은 다음 섹션을 참조하세요.

   ![검토 집합에서 항목을 내보내기 위한 구성 옵션](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. 내보내기 구성 후 **내보내기** 를 클릭하여 내보내기 프로세스를 시작 합니다. 출력 옵션 섹션에서 선택한  옵션에 따라 직접 다운로드 또는 조직의 Azure Storage 계정으로 내보내기 파일에 액세스할 수 있습니다.

> [!NOTE]
> 내보내기 작업은 사례의 수명 동안 유지됩니다. 그러나 내보내기 작업이 완료된 후 30일 이내에 내보내기 작업에서 콘텐츠를 다운로드해야 합니다.

## <a name="export-options"></a>내보내기 옵션

다음 옵션을 사용하여 내보내기 구성을 구성합니다.

- **내보내기 이름:** 내보내기 작업의 이름입니다.

- **설명:** 설명을 추가할 수 있는 자유 텍스트 필드입니다.

- **다음 문서 내보내기**

  - **선택한 문서만:** 이 옵션은 현재 선택된 문서만 내보낼 수 있습니다.
  
  - **검토 집합의** 모든 문서: 이 옵션은 검토 집합의 모든 문서를 내보낼 수 있습니다.

- **메타 데이터**
  
  - **파일 로드:** 이 파일에는 각 파일에 대한 메타데이터가 포함되어 있습니다. 이 파일은 일반적으로 타사 eDiscovery 도구에서 분석할 수 있습니다. 포함된 필드에 대한 자세한 내용은 [Advanced eDiscovery의 문서 메타데이터 필드를 참조하세요.](document-metadata-fields-in-Advanced-eDiscovery.md)
  
  - **태그:** 태그 지정 정보를 선택하면 로드 파일에 포함됩니다.

- **콘텐츠**
  
  - **기본 파일:** 검토 집합에 문서의 기본 파일을 포함하려면 이 확인란을 선택합니다. 기본 파일을 내보내는 경우 채팅 대화 내보내기 방법에 대한 다음 옵션이 있습니다.
  
  - **대화 옵션**

    - **대화 파일:** 이 옵션은 재구성된 채팅 대화를 내보낼 수 있습니다. 이 형식은 기본 응용 프로그램에서 사용자에게 표시하는 모양과 같은 형식으로 대화를 제공합니다.

    - **개별 채팅 메시지:** 이 옵션은 Microsoft 365에 저장된 원래 대화 파일을 내보낼 수 있습니다.

- **옵션**

  - **텍스트 파일:**- 이 옵션에는 내보내기에서 추출된 네이티브 파일의 텍스트 버전이 포함됩니다.
  
  - **편집된** 네이티브를 변환된 PDF로 바꾸기: 검토 중에 편집된 PDF 파일이 생성되는 경우 이러한 파일을 내보낼 수 있습니다. 이 옵션을 선택하지 않은 경우, 편집된 기본 파일만 내보내거나 실제 변경이 포함된 PDF 파일을 내보내기 위해 이 옵션을 선택할 수 있습니다.

- **출력 옵션:** 내보낼 콘텐츠는 웹 브라우저를 통해 직접 다운로드할 수 있습니다. 또는 Azure Storage 계정으로 보낼 수 있습니다. 처음 두 옵션을 사용하면 직접 다운로드를 사용할 수 있습니다.
  
  - 느슨한 파일 및 PSTS(가능한 경우 전자 메일이 **PSTS에 추가)**: 파일은 기본 응용 프로그램에서 사용자가 볼 수 있는 원래 디렉터리 구조와 같은 형식으로 내보낼 수 있습니다.  자세한 내용은 느슨한 파일 및 [PST 내보내기](#loose-files-and-pst-export-structure) 구조 섹션을 참조하세요.
  
  - **압축된 디렉터리 구조:** 파일을 내보내고 다운로드에 포함됩니다.
  
  - **Azure Storage** 계정으로 내보낼 압축된 디렉터리 구조: 파일이 조직의 Azure Storage 계정으로 내보내기됩니다. 이 옵션의 경우 파일을 내보낼 Azure Storage 계정의 컨테이너 URL을 제공해야 합니다. Azure Storage 계정에 대한 SAS(공유 액세스 서명) 토큰도 제공해야 합니다. 자세한 내용은 검토 집합의 문서를 [Azure Storage 계정으로 내보내기를 참조하세요.](download-export-jobs.md)

다음 섹션에서는 느슨한 파일 및 압축된 디렉터리 구조 옵션에 대한 폴더 구조에 대해 설명합니다.

### <a name="loose-files-and-pst-export-structure"></a>느슨한 파일 및 PST 내보내기 구조

이 내보내기 옵션을 선택하면 내보낼 콘텐츠가 다음 구조로 구성됩니다.

- 루트 폴더: 이름이 ExportName.zip
  
  - Export_load_file.csv: 메타데이터 파일입니다.
  
  - Summary.csv: 내보내기 통계도 포함하는 요약 파일입니다.
  
  - Exchange: 이 폴더에는 Exchange의 모든 콘텐츠가 기본 파일 형식으로 포함되어 있습니다. 변환된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.
  
  - SharePoint: 이 폴더에는 SharePoint의 모든 기본 콘텐츠가 기본 파일 형식으로 포함되어 있습니다. 변환된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택한 경우 네이티브 파일은 재조정된 PDF로 대체됩니다.

### <a name="condensed-directory-structure"></a>압축된 디렉터리 구조

- 루트 폴더: 이 폴더의 이름은 ExportName.zip
  
  - Export_load_file.csv: 메타데이터 파일입니다.
  
  - Summary.txt: 내보내기 통계도 포함하는 요약 파일입니다.
  
  - NativeFiles: 이 폴더에는 내보낼 수 있는 모든 기본 파일이 포함되어 있습니다. 편집된 PDF 파일을 내보낼 경우 PST 파일에 저장되지 않습니다. 대신 별도의 폴더에 추가됩니다.
  
  - Error_files: 내보내기에 포함된 경우 이 폴더에 다음 오류 파일이 포함되어 있습니다.

    - ExtractionError: 상위 파일에서 제대로 추출되지 않은 파일의 사용 가능한 메타데이터가 포함된 CSV 파일입니다.

    - ProcessingError: 이 파일에는 처리 오류가 있는 문서 목록이 포함되어 있습니다. 이 콘텐츠는 항목 수준으로, 첨부 파일에서 처리 오류가 발생하는 경우 첨부 파일이 포함된 전자 메일 메시지가 이 폴더에 포함됩니다.
  
  - Extracted_text_files: 이 폴더에는 처리 시 생성된 추출된 텍스트 파일이 모두 포함되어 있습니다.

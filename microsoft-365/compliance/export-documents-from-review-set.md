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
description: 프레젠테이션 또는 외부 검토를 위해 검토 집합에서 콘텐츠를 선택 하 고 내보내는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 855f1b8fef7a1df6ed86f058b71e5027851b5f0d
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399182"
---
# <a name="export-documents-from-a-review-set"></a>검토 집합에서 문서 내보내기

내보내기를 사용 하면 다운로드 패키지에 포함 된 콘텐츠를 사용자 지정할 수 있습니다. 내보내기 도구에서는 다음과 같은 설정을 사용 하 여 구성 페이지를 제공 합니다.

![검토 집합에서 항목을 내보내기 위한 옵션](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>내보내기 옵션

- 내보내기 이름: 내보내기 작업의 이름입니다.

- 설명: 설명을 추가할 수 있는 자유 텍스트 필드입니다.

- 내보낼 문서:

  - 선택한 문서만-현재 선택 된 문서만 내보냅니다.
  
  - 검토 집합의 모든 문서-검토 집합의 모든 문서를 내보냅니다.

- 메타데이터
  
  - 파일 로드-이 파일에는 각 파일의 메타 데이터가 포함 됩니다. 포함 된 필드에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md) 를 참조 하십시오. 이 파일은 일반적으로 타사 eDiscovery 도구로 ingested 될 수 있습니다.
  
  - 태그-이 확인란이 선택 되 면 태그 정보가 로드 파일에 포함 됩니다.

- 콘텐츠
  
  - 네이티브 파일-네이티브 파일을 포함 하려면이 확인란을 선택 합니다.
  
  - 대화 옵션
    
    - 대화 파일-내보낸 채팅 메시지를 내보냅니다. 이 형식은 사용자가 네이티브 응용 프로그램에 표시 되는 것과 비슷한 형태의 대화를 제공 합니다.
    
    - 개별 채팅 메시지-Microsoft 365에 저장 되어 있는 원본 대화 파일을 내보냅니다.

- 옵션

  - 텍스트 파일-추출 된 텍스트 버전의 네이티브 파일을 포함 합니다.
  
  - 변환 된 Pdf로 redacted natives 교체-검토 중에 redacted PDF 파일이 생성 되는 경우 이러한 파일을 내보낼 수 있습니다. 이 옵션을 선택 하지 않으면 서 redacted 이었던 네이티브 파일만 내보내도록 선택 하거나, 실제 redactions 포함 된 PDF 파일을 내보내도록이 옵션을 선택할 수 있습니다.

- 출력 옵션 (내보낸 콘텐츠는 웹 브라우저를 통해 직접 다운로드 하거나 Azure Storage 계정으로 보낼 수 있습니다. 처음 두 옵션은 직접 다운로드를 허용 합니다.
  
  - 느슨한 파일 및 Pst (가능한 경우 Pst에 전자 메일이 추가 됨)-파일은 기본 응용 프로그램에서 사용자가 본 디렉터리 구조와 비슷한 형식으로 내보내집니다.  자세한 내용은 [파일 및 PST 내보내기 구조 완화](#loose-files-and-pst-export-structure) 섹션을 참조 하십시오.
  
  - 압축 된 디렉터리 구조-파일을 내보내고 다운로드에 포함 합니다.
  
  - Azure Storage 계정으로 내보낸 디렉터리 구조-파일을 조직의 Azure Storage accouunt로 내보냅니다.

## <a name="loose-files-and-pst-export-structure"></a>느슨한 파일 및 PST 내보내기 구조

이 내보내기 옵션을 선택 하면 내보낸 콘텐츠가 다음 구조로 구성 됩니다.

- 루트 폴더-명명 된 ExportName.zip의이 폴더
  
  - Export_load_file.csv 메타 데이터 파일입니다.
  
  - Summary.csv-내보내기 통계도 포함 된 요약 파일입니다.
  
  - Exchange-이 폴더에는 Exchange의 모든 콘텐츠가 기본 파일 형식으로 포함 되어 있습니다. **변환 된 pdf로 redacted Natives 바꾸기** 옵션을 선택한 경우 Natives 파일이 redacted pdf로 대체 됩니다.
  
  - SharePoint =이 폴더에는 SharePoint의 모든 네이티브 콘텐츠가 네이티브 파일 형식으로 포함 되어 있습니다. **변환 된 pdf로 redacted Natives 바꾸기** 옵션을 선택한 경우 Natives 파일이 redacted pdf로 대체 됩니다.

## <a name="condensed-directory-structure"></a>압축 디렉터리 구조

- 루트 폴더-이 폴더의 이름은 ExportName.zip
  
  - Export_load_file.csv 메타 데이터 파일입니다.
  
  - Summary.txt-내보내기 통계도 포함 된 요약 파일입니다.
  
  - Input_or_native_files-이 폴더에는 내보낸 모든 네이티브 파일이 포함 됩니다. Redacted PDF 파일을 내보내면 PST 파일에 저장 되지 않습니다. 대신, 구분 된 폴더에 추가 됩니다.
  
  - Error_files-이 폴더에는 내보내기에 포함 된 경우 다음 오류 파일이 포함 됩니다.
    
    - ExtractionError 부모 파일에서 올바르게 추출 되지 않은 파일의 사용 가능한 메타 데이터가 포함 된 CSV 파일입니다.
    
    - ProcessingError-이 파일에는 처리 오류가 있는 문서 목록이 포함 되어 있습니다. 이 콘텐츠는 항목 수준으로, 첨부 파일에 처리 오류가 발생 한 경우 첨부 파일이 포함 된 전자 메일 메시지가이 폴더에 포함 됩니다.
  
  - Extracted_text_files-이 폴더에는 처리 시 생성 된 추출 된 텍스트 파일이 모두 포함 됩니다.

> [!NOTE]
> 내보내기 작업은 서비스 케이스 수명 동안 보존 되며, 케이스가 삭제 되지 않는 한 다운로드 될 수 있습니다.

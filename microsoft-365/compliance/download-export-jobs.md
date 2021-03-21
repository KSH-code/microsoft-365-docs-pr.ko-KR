---
title: Advanced eDiscovery 사례에 대한 내보내기 작업 다운로드
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Azure 저장소 탐색기를 설치하고 사용하여 Advanced eDiscovery의 검토 집합에서 내보낼 문서를 다운로드합니다.
ms.openlocfilehash: 0a73d157b2661202507883dd6542cdf6c6b482f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926624"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a>Advanced eDiscovery 사례에서 내보내기 작업 다운로드

Advanced eDiscovery 사례의 검토 집합에서 문서를 내보내면 문서가 Microsoft에서 제공하는 Azure Storage 위치 또는 조직에서 관리하는 Azure Storage 위치로 업로드됩니다. 사용된 Azure Storage 위치의 유형은 문서를 내보낼 때 선택한 옵션에 따라 다릅니다.

이 문서에서는 Microsoft Azure Storage Explorer를 사용하여 Azure Storage 위치에 연결하여 내보낼 문서를 찾아 다운로드하는 방법에 대한 지침을 제공합니다. Azure Storage Explorer에 대한 자세한 내용은 [빠른 시작: Azure 저장소 탐색기 사용을 참조하세요.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)

## <a name="step-1-install-the-azure-storage-explorer"></a>1단계: Azure 저장소 탐색기 설치

첫 번째 단계는 Azure Storage Explorer를 다운로드하여 설치하는 것입니다. 자세한 내용은 [Azure 저장소 탐색기 도구를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=544842) 이 도구를 사용하여 3단계에서 내보낼 문서에 연결하고 다운로드할 수 있습니다.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>2단계: 내보내기 작업에서 SAS URL 얻기

다음 단계는 검토 집합에서 문서를 내보내기 위한 내보내기 작업을 만들 때 생성되는 SAS(공유 액세스 서명) [URL을 얻는 것입니다.](export-documents-from-review-set.md) Microsoft에서 제공하는 Azure Storage 위치 또는 조직에서 관리하는 Azure Storage 위치로 업로드되는 문서에 대한 SAS URL을 복사할 수 있습니다. 두 경우 모두 SAS URL을 사용하여 3단계에서 Azure Storage 위치에 연결합니다.

1. Advanced **eDiscovery** 페이지에서 사례로 이동한 다음 내보내기 **탭을** 클릭합니다.

2. 내보내기 **탭에서** 다운로드할 내보내기 작업을 클릭합니다.

3. 플라이아웃 페이지의 **위치** 아래에서 표시되는 SAS URL을 복사합니다. 필요한 경우 3단계에서 액세스할 수 있도록 파일에 저장할 수 있습니다.
 
   ![위치에 표시되는 SAS URL 복사](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>3단계: Azure Storage 위치에 연결

마지막 단계는 Azure 저장소 탐색기 및 SAS URL을 사용하여 Azure Storage 위치에 연결하고 로컬 컴퓨터로 내보낼 문서를 다운로드하는 것입니다.

1. 1단계에서 설치한 Azure Storage Explorer를 열 수 있습니다.

2. 계정 **추가 아이콘을** 클릭합니다. 또는 저장소 계정 을 마우스 오른쪽 **단추로 클릭할 수 있습니다.**

   ![계정 추가 아이콘을 클릭합니다.](../media/AzureStorageConnect.png)

3. Azure **Storage에 연결 페이지에서** **SAS(공유 액세스 서명) URI 사용을** 클릭하고 다음 을 **클릭합니다.**

    ![SAS(공유 액세스 서명) URI 사용을 클릭한 후 다음을 클릭합니다.](../media/AzureStorageConnect2.png)

4. **SAS URI로** 첨부 페이지에서 URI 상자를 클릭한 다음 2단계에서 획득한 SAS URL을 붙여 넣습니다. 

    ![URI 상자에 SAS URL 붙여넣기](../media/AzureStorageConnect3.png)

    SAS URL의 일부가 표시 이름 **상자에** 표시됩니다. 이 이름은 저장소 위치에 연결한 후 **저장소** 계정 아래에 만들어진 컨테이너의 표시 이름으로 사용됩니다. 이 이름은 Advanced eDiscovery 사례의 ID와 고유 식별자로 구성됩니다. 기본 표시 이름을 유지하거나 변경할 수 있습니다. 변경하는 경우 표시 이름은 고유해야 합니다.

5. **다음** 을 클릭합니다.

    연결 **요약 페이지가** 표시됩니다.

    ![연결 요약 페이지에서 연결을 클릭하여 Azure Storage 위치에 연결합니다.](../media/AzureStorageConnect4.png)

6. 연결 **요약 페이지에서** 연결 정보를 검토한 다음 연결을 **클릭합니다.**

    **Blob 컨테이너** 노드(저장소 계정(연결된 컨테이너  >  **아래)가** \> 열립니다.

    ![Blobs 컨테이너 노드에서 작업 내보내기](../media/AzureStorageConnect5.png)

    4단계의 표시 이름으로 이름이 인 컨테이너가 들어 있습니다. 이 컨테이너에는 만든 각 내보내기 작업의 폴더가 포함되어 있습니다. 이러한 폴더의 이름은 내보내기 작업의 ID에 해당하는 ID로 지정됩니다. 이러한 내보내기 ID(및 내보내기 이름)는  작업 탭에 나열된  각 내보내기 작업 준비 작업의 플라이아웃 페이지의 지원 정보에서 찾을 **수** 있습니다.

7. 내보내기 작업 폴더를 두 번 클릭하여 열립니다.

   폴더 및 내보내기 보고서 목록이 표시됩니다.
   
    ![내보내기 폴더에 내보낼 파일 및 내보내기 보고서가 포함되어 있습니다.](../media/AzureStorageConnect6.png)

   내보내기 작업 폴더에는 다음 항목이 포함되어 있습니다. 내보내기 폴더의 실제 항목은 내보내기 작업을 만들 때 구성된 내보내기 옵션에 따라 결정됩니다. 자세한 내용은 검토 [집합에서 문서 내보내기 를 참조하세요.](export-documents-from-review-set.md)

    - Export_load_file.csv: 이 CSV 파일은 내보낼 각 문서에 대한 정보를 포함하는 세부 정보 내보내기 보고서입니다. 파일은 문서의 각 메타데이터 속성에 대한 열로 구성됩니다. 이 보고서에 포함된 메타데이터의 목록과 설명은 [Advanced eDiscovery의](document-metadata-fields-in-advanced-ediscovery.md)문서 메타데이터 필드에서 표의 내보낼 필드 이름 열을 참조하세요. 
    
    - Summary.txt: 내보내기 통계를 포함하여 내보내기 요약이 포함된 텍스트 파일입니다.
    
    - Extracted_text_files: 이 폴더에는 내보낼 각 문서의 텍스트 파일 버전이 포함되어 있습니다.
     
    - NativeFiles: 이 폴더에는 내보낼 각 문서의 기본 파일 버전이 포함되어 있습니다.
    
    - Error_files: 내보내기 작업에서 오류 파일이 포함된 경우 이 폴더에는 다음 항목이 포함됩니다. 
        
      - ExtractionError.csv: 이 CSV 파일에는 상위 항목에서 제대로 추출되지 않은 파일에 대한 사용 가능한 메타데이터가 포함되어 있습니다.
        
      - ProcessingError: 이 폴더에는 처리 오류가 있는 문서가 포함되어 있습니다. 이 콘텐츠는 항목 수준에 있습니다. 즉, 첨부 파일에 처리 오류가 있는 경우 첨부 파일이 포함된 문서도 이 폴더에 포함됩니다.
 
8. 내보내기에서 모든 콘텐츠를 내보내려면 내보내기 폴더를 선택한 다음 다운로드를 **클릭합니다.**

9. 내보낼 파일을 다운로드할 위치를 지정하고 폴더 선택을 클릭합니다.

    Azure 저장소 탐색기가 내보내기 프로세스를 시작합니다. 내보낼 항목 다운로드의 상태가 활동 **창에** 표시됩니다. 다운로드가 완료되면 메시지가 표시됩니다.

    ![다운로드가 완료되면 메시지가 표시됩니다.](../media/AzureStorageConnect8.png)

> [!NOTE]
> 전체 내보내기 작업을 다운로드하는 대신 다운로드할 특정 항목을 선택할 수 있습니다. 항목을 다운로드하는 대신 항목을 두 번 클릭하여 볼 수 있습니다.
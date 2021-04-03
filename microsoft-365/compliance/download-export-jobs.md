---
title: 조직의 Azure Storage 계정으로 문서 내보내기
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
ms.custom: seo-marvel-mar2020
description: 검토 집합의 문서를 Azure Storage 계정으로 내보내고 Azure Storage Explorer를 사용하여 로컬 컴퓨터에 다운로드합니다.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574730"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>검토 집합에서 Azure Storage 계정으로 문서 내보내기

Advanced eDiscovery 사례의 검토 집합에서 문서를 내보낼 때 조직에서 관리하는 Azure Storage 계정으로 내보낼 수 있습니다. 이 옵션을 사용하면 문서가 Azure Storage 위치에 업로드됩니다. 문서를 내보낼 때 Azure Storage Explorer를 사용하여 문서에 액세스하여 로컬 컴퓨터 또는 다른 위치에 다운로드할 수 있습니다. 이 문서에서는 Azure Storage 계정으로 문서를 내보내고 Azure Storage Explorer를 사용하여 Azure Storage 위치에 연결하여 내보낼 문서를 다운로드하는 방법에 대한 지침을 제공합니다. Azure Storage Explorer에 대한 자세한 내용은 [Azure Storage Explorer 사용을 참조하세요.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)

## <a name="before-you-export-documents-from-a-review-set"></a>검토 집합에서 문서를 내보내기 전에

- 검토 집합에서 문서를 내보내기 위해 Azure Storage 계정에 대한 SAS(공유 액세스 서명) 토큰과 저장소 계정의 특정 컨테이너에 대한 URL을 제공해야 합니다. 2단계를 수행할 때 이러한 작업을 준비해야 합니다(예: 텍스트 파일에 복사).

  - **SAS 토큰: SAS** 토큰은 컨테이너가 아니라 Azure Storage 계정에 대한 토큰입니다. Azure Storage에서 계정에 대한 SAS 토큰을 생성할 수 있습니다. 이렇게하려면 Azure Storage 계정으로 이동한  다음 저장소 계정  블레이드의 설정 설정에서 공유 액세스 서명을 선택합니다. 기본 설정을 사용하여 SAS 토큰을 생성할 때 모든 리소스 유형을 허용합니다.

  - **컨테이너 URL:** 검토 집합 문서를 업로드한 다음 컨테이너의 URL 복사본을 다운로드할 컨테이너를 만들어야 합니다. 예를 들면 `https://ediscoverydata.blob.core.windows.net/exportdata` 입니다. URL을 다운로드하려면 Azure Storage의 컨테이너로 이동한 다음  컨테이너 블레이드의 설정 섹션에서 속성을 선택합니다. 

- Azure Storage Explorer를 다운로드하여 설치합니다. 자세한 내용은 [Azure 저장소 탐색기 도구를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=544842) 이 도구를 사용하여 Azure Storage 계정의 컨테이너에 연결하고 1단계에서 내보낼 문서를 다운로드합니다.

## <a name="step-1-export-the-documents-from-a-review-set"></a>1단계: 검토 집합에서 문서 내보내기

첫 번째 단계는 검토 집합에서 문서를 내보내는 내보내기 작업을 만드는 것입니다. 모든 내보내기 옵션에 대한 자세한 지침은 검토 집합에서 문서 [내보내기 를 참조하세요.](export-documents-from-review-set.md) 다음 절차에서는 문서를 조직의 Azure Storage 계정으로 내보내기 위한 설정을 중시합니다.

1. Microsoft 365 규정 준수 센터에서 고급 eDiscovery  사례를 열고 검토 집합 탭을 선택한 다음 내보낼 검토 집합을 선택합니다.

2. 검토 집합에서 작업 **내보내기 를**  >  **클릭합니다.**

3. 내보내기 **옵션** 플라이아웃 페이지에서 내보내기 이름(필수) 및 설명(선택 사항)을 입력합니다.

4. 문서, 메타데이터, 콘텐츠 및 옵션 섹션의 설정을 구성합니다. 이러한 설정에 대한 자세한 내용은 [검토 집합에서 문서 내보내기 를 참조하세요.](export-documents-from-review-set.md)

5. 출력 옵션 **섹션에서** Azure Storage 계정으로 **내보낼 압축된** 디렉터리 구조를 선택합니다.

6. 저장소 계정의 컨테이너 URL과 SAS 토큰을 해당 필드에 붙여 넣습니다.

   ![해당 필드에 연결 URL 및 SAS 토큰 붙여넣기](../media/AzureStorageOutputOptions.png)

7. 내보내기 **를** 클릭하여 내보내기 작업을 만들 수 있습니다.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>2단계: 내보내기 작업에서 SAS URL 얻기

다음 단계는 1단계에서 내보내기 작업을 만든 후 생성되는 SAS URL을 얻는 것입니다. SAS URL을 사용하여 검토 집합 문서를 내보낼 Azure Storage 계정의 컨테이너에 연결합니다.

1. Advanced **eDiscovery** 페이지에서 사례로 이동한 다음 내보내기 **탭을** 클릭합니다.

2. 내보내기 **탭에서** 다운로드할 내보내기 작업을 클릭합니다. 1단계에서 만든 내보내기 작업입니다.

3. 플라이아웃 페이지의 **위치** 아래에서 표시되는 SAS URL을 복사합니다. 필요한 경우 3단계에서 액세스할 수 있도록 텍스트 파일에 저장할 수 있습니다.

   ![위치에 표시되는 SAS URL 복사](../media/eDiscoExportJob.png)

   > [!TIP]
   > 내보내기 작업에서 표시되는 SAS URL은 Azure Storage 계정에 대한 컨테이너 URL과 SAS 토큰을 함께 사용합니다. 내보내기 작업에서 복사하거나 URL과 SAS 토큰을 결합하여 직접 만들 수 있습니다.

## <a name="step-3-connect-to-the-azure-storage-container"></a>3단계: Azure Storage 컨테이너에 연결

마지막 단계는 Azure Storage Explorer 및 SAS URL을 사용하여 Azure Storage 계정의 컨테이너에 연결하고 내보낼 문서를 로컬 컴퓨터에 다운로드하는 것입니다.

1. 다운로드하여 설치한 Azure Storage Explorer를 시작하세요.

2. 연결 **대화 상자 열기 아이콘을** 클릭합니다.

   ![계정 추가 아이콘을 클릭합니다.](../media/AzureStorageConnect.png)

3. Azure **Storage에 연결 페이지에서** **Blob 컨테이너 를 클릭합니다.**

4. 인증 **방법 선택 페이지에서** **SAS(공유 액세스 서명)** 옵션을 선택하고 다음 을 **클릭합니다.**

5. 연결 **정보 입력 페이지의** Blob 컨테이너 SAS URL 상자에 2단계의 내보내기 작업에서 획득한 **SAS URL을 붙여 넣습니다.**

    ![URI 상자에 SAS URL 붙여넣기](../media/AzureStorageConnect3.png)

    표시 이름 상자에 컨테이너 **이름이** 표시됩니다. 이 이름을 편집할 수 있습니다.

6. **다음을** 클릭하여 요약 페이지를 **표시한** 다음 연결을 **클릭합니다.**

    **Blob 컨테이너** 노드(저장소 계정(연결된 컨테이너  >  **아래)가** \> 열립니다.

    ![Blobs 컨테이너 노드에서 작업 내보내기](../media/AzureStorageConnect5.png)

    5단계의 표시 이름으로 이름이 인 컨테이너가 들어 있습니다. 이 컨테이너에는 Azure Storage 계정의 컨테이너에 다운로드한 각 내보내기 작업의 폴더가 포함되어 있습니다. 이러한 폴더의 이름은 내보내기 작업의 ID에 해당하는 ID로 지정됩니다. 이러한 내보내기 IDS(내보내기 이름)는  고급 eDiscovery 사례의 작업 탭에 나열된  각 내보내기 작업 준비 작업의 플라이아웃 페이지의 지원 정보에서 찾을 수 있습니다. 

7. 내보내기 작업 폴더를 두 번 클릭하여 열립니다.

   폴더 및 내보내기 보고서 목록이 표시됩니다.

    ![내보내기 폴더에 내보낼 파일 및 내보내기 보고서가 포함되어 있습니다.](../media/AzureStorageConnect6.png)

8. 내보내기 작업에서 모든 콘텐츠를 내보내려면  위쪽 화살표를 클릭하여 내보내기 작업 폴더로 돌아가 다운로드를 **클릭합니다.**

9. 내보낼 파일을 다운로드할 위치를 지정하고 폴더 선택을 클릭합니다.

    Azure 저장소 탐색기에서 다운로드 프로세스를 시작합니다. 내보낼 항목 다운로드의 상태가 활동 **창에** 표시됩니다. 다운로드가 완료되면 메시지가 표시됩니다.

> [!NOTE]
> Azure 저장소 탐색기에서 전체 내보내기 작업을 다운로드하는 대신 다운로드하고 볼 특정 항목을 선택할 수 있습니다.

## <a name="more-information"></a>추가 정보

- 내보내기 작업 폴더에는 다음 항목이 포함되어 있습니다. 내보내기 폴더의 실제 항목은 내보내기 작업을 만들 때 구성된 내보내기 옵션에 따라 결정됩니다. 이러한 옵션에 대한 자세한 내용은 [검토 집합에서 문서 내보내기 를 참조하세요.](export-documents-from-review-set.md)

  - Export_load_file.csv: 이 CSV 파일은 내보낼 각 문서에 대한 정보를 포함하는 세부 정보 내보내기 보고서입니다. 파일은 문서의 각 메타데이터 속성에 대한 열로 구성됩니다. 이 보고서에 포함된 메타데이터의 목록과 설명은 [Advanced eDiscovery의](document-metadata-fields-in-advanced-ediscovery.md)문서 메타데이터 필드에서 표의 내보낼 필드 이름 열을 참조하세요. 

  - Summary.txt: 내보내기 통계를 포함하여 내보내기 요약이 포함된 텍스트 파일입니다.

  - Extracted_text_files: 이 폴더에는 내보낼 각 문서의 텍스트 파일 버전이 포함되어 있습니다.

  - NativeFiles: 이 폴더에는 내보낼 각 문서의 기본 파일 버전이 포함되어 있습니다.

  - Error_files: 내보내기 작업에서 오류 파일이 포함된 경우 이 폴더에는 다음 항목이 포함됩니다.

    - ExtractionError.csv: 이 CSV 파일에는 상위 항목에서 제대로 추출되지 않은 파일에 대한 사용 가능한 메타데이터가 포함되어 있습니다.

    - ProcessingError: 이 폴더에는 처리 오류가 있는 문서가 포함되어 있습니다. 이 콘텐츠는 항목 수준에 있습니다. 즉, 첨부 파일에 처리 오류가 있는 경우 첨부 파일이 포함된 문서도 이 폴더에 포함됩니다.

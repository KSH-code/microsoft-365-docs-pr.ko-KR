---
title: ID 목록 콘텐츠 검색을 위한 CSV 파일 준비
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: 기존 콘텐츠 검색의 CSV 파일을 사용하여 특정 전자 메일 항목을 반환하는 ID 목록 검색을 만들 수 있습니다.
ms.openlocfilehash: 3fc43f410d6361ac655f7f839b6b4f8752483ef9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216912"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>ID 목록 콘텐츠 검색을 위한 CSV 파일 준비

특정 사서함 전자 메일 메시지 및 기타 사서함 항목은 특정 사서함 EXCHANGE 있습니다. ID 목록 검색을 만들려면 검색할 특정 사서함 항목을 식별하는 CSV(쉼표로 구분된 값) 파일을 제출합니다. 이 CSV 파일의 경우  콘텐츠 검색 결과를 내보내거나 기존 콘텐츠 검색에서 콘텐츠 검색 보고서를 **내보낼 때** 포함된Results.csv파일 또는 인덱서되지 않은 Items.csv파일을 사용할 수 있습니다. 그런 다음 이러한 파일 중 하나를 편집하여 검색할 특정 항목을 나타내고, 새 ID 목록 검색을 만들고, CSV 파일을 제출합니다.

**ID 목록 검색을 만드는 이유** Results.csv또는 인덱서되지 않은 Items.csv파일의 메타데이터를 기반으로 항목이 eDiscovery 요청에 응답하는지 여부를 확인할 수 없는 경우 ID 목록 검색을 사용하여 해당 항목을 찾고 **미리** 보고 내보낼 수 있습니다.  ID 목록 검색은 일반적으로 인덱서되지 않은 특정 항목 집합을 검색하고 반환하는 데 사용됩니다.

ID 목록 검색을 만드는 프로세스를 간략하게 간략하게 소개합니다.

1. 검색에서 새 검색을 만들고 Microsoft 365 규정 준수 센터.

2. 콘텐츠 검색 결과 또는 콘텐츠 검색 보고서를 내보낼 수 있습니다. 자세한 내용은 다음을 참조하세요.

    - [콘텐츠 검색 결과 내보내기](export-search-results.md)

    - [콘텐츠 검색 보고서 내보내기](export-a-content-search-report.md)

3. Results.csv 파일 또는 Items.csv **파일을** 편집하고 ID 목록 검색에 포함할 특정 사서함 항목을 식별합니다. ID 목록 [검색을](#prepare-the-csv-file-for-an-id-list-search) 위해 CSV 파일을 준비하기 위한 지침을 참조하세요.

4. 새 ID 목록 검색을 만들고(지침 [참조)](#create-an-id-list-search)준비한 CSV 파일을 제출합니다. 생성된 검색 쿼리는 CSV 파일에서 선택한 항목만 검색합니다.

> [!NOTE]
> ID 목록 검색은 사서함 항목에만 지원됩니다. ID 목록 검색에서 SharePoint OneDrive 검색할 수 없습니다.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>ID 목록 검색을 위한 CSV 파일 준비

검색에 대한 검색 결과 또는 보고서를 내보본 후 다음 단계를 수행하여 ID 목록 검색을 위해 CSV 파일을 준비합니다. 이 CSV 파일은 ID 목록 검색의 모든 항목을 식별합니다.

사이트 및 SharePoint 계정이 포함된 검색에서 CSV OneDrive 수 있지만 ID 목록 검색을 위해 사서함 항목만 선택할 수 있습니다. SharePoint 또는 OneDrive 경우 ID 목록 검색을 만들 때 CSV 파일의 유효성 검사가 실패합니다.

1. 파일 **Results.csv** 또는 인덱서되지 **않은** Items.csv파일을 Excel.

2. 선택한 **열에서** 검색할 항목에 해당하는 셀에 예를 입력합니다.  검색하려는 모든 항목에 대해 이 단계를 반복합니다.

    > [!IMPORTANT]
    > CSV 파일을 열면 Excel **ID** 열의 데이터 형식이 일반으로 변경될 수 **있습니다.** 그러면 항목에 대한 문서 ID가 과학적 표시로 표시됩니다. 예를 들어 "481037338205"의 문서 ID는 "4.81037E+11"으로 표시됩니다. 이 경우 다음 단계를 수행하여 문서 **ID** 열의 데이터 형식을 **번호로** 변경하여 문서 ID에 대한 올바른 형식을 복원해야 합니다. 이렇게 하지 않는 경우 CSV 파일을 사용하는 ID 목록 검색이 실패합니다.

3. 전체 문서 **ID 열을 마우스 오른쪽 단추로** 클릭하고 **셀 서식을 선택합니다.**

4. 범주 **상자에서** 번호를 **클릭합니다.**

5. 소수 자식 수를 **0으로** 변경한  다음 확인을 클릭하여 변경 내용을 저장합니다. 문서 ID 열의 값은 숫자로 변경됩니다.

    다음은 ID 목록 콘텐츠 검색을 위해 제출할 준비가 된 CSV 파일의 예입니다.

    ![대상 콘텐츠 검색을 위한 CSV 파일의 예입니다.](../media/SearchIDListCSVFile.png)

6. CSV 파일을 저장하거나  다른 이름으로 저장을 사용하여 다른 파일 이름으로 파일을 저장합니다. 두 경우 모두 CSV 형식으로 파일을 저장해야 합니다.

## <a name="create-an-id-list-search"></a>ID 목록 검색 만들기

다음 단계는 새 ID 목록 검색을 만들고 이전 단계에서 준비한 CSV 파일을 제출하는 것입니다.

> [!IMPORTANT]
> 검색 결과 또는 보고서를 내보낼 때 ID 목록 검색을 2일 이상 만들어야 합니다. 2일 전에 내보낼 검색 결과 또는 보고서의 경우 검색 결과 또는 보고서를 다시 내보내서 업데이트된 CSV 파일을 생성해야 합니다. 그런 다음 업데이트된 CSV 파일 중 하나를 준비하고 이를 사용하여 ID 목록 검색을 만들 수 있습니다.

1. <https://compliance.microsoft.com>으로 이동하여 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **모두 표시** 를 클릭한 다음 **콘텐츠 검색** 을 클릭합니다.

3. 콘텐츠 검색 **페이지에서** **ID 목록으로 검색을 클릭합니다.**

4. ID로  검색 목록 플라이아웃에서 검색 이름을 지정하고 원하는 경우  설명을 지정한 다음 찾아보기를 클릭하고 이전 단계에서 준비한 CSV 파일을 선택합니다.

    Microsoft 365 CSV 파일의 유효성을 검사하려고 시도합니다. 유효성 검사에 실패하면 유효성 검사 오류를 해결하는 데 도움이 될 수 있는 오류 메시지가 표시됩니다. ID 목록 검색을 만들 수 있는 CSV 파일의 유효성을 검사해야 합니다.

5. CSV 파일의 유효성을 검사한 후  검색을 클릭하여 ID 목록 검색을 생성합니다.

    다음은 생성된 쿼리와 예상 검색 결과 수를 표시하는 ID 목록 검색의 플라이아웃 페이지의 예입니다.

    ![ID 목록 검색을 위한 검색 쿼리입니다.](../media/SearchIDListFlyout.png)

    ID 검색 통계에 표시되는 예상 항목 수는 CSV 파일에서 선택한 항목 수와 일치해야 합니다.

6. ID 목록 검색에서 반환된 항목을 미리 보거나 내보낼 수 있습니다.

## <a name="more-information"></a>추가 정보

ID 목록 검색을 만들고 나서 사서함을 이동하면 검색 쿼리에서 지정된 항목이 반환되지 않습니다. 사서함을 이동할 때 사서함 항목의 **DocumentId** 속성이 변경되어 있기 때문에입니다. ID 목록 검색을 만든 후 사서함을 이동하는 경우는 드물지만 새 콘텐츠 검색을 만들거나 기존 검색에 대한 검색 결과를 업데이트한 다음 검색 결과 또는 보고서를 내보내 새 ID 목록 검색을 만드는 데 사용할 수 있는 업데이트된 CSV 파일을 생성해야 합니다.

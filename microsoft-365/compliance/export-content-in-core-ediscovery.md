---
title: Core eDiscovery 사례에서 콘텐츠 내보내기 및 다운로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Core eDiscovery 사례에서 콘텐츠를 내보내고 다운로드하는 방법을 설명합니다.
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760302"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Core eDiscovery 사례에서 콘텐츠 내보내기

검색이 성공적으로 실행된 후 검색 결과를 내보낼 수 있습니다. 검색 결과를 내보내면 사서함 항목이 PST 파일 또는 개별 메시지로 다운로드됩니다. SharePoint 및 비즈니스용 OneDrive 사이트에서 콘텐츠를 내보내면 기본 Office 문서 및 기타 문서의 복사본이 내보내됩니다. 내보낼 Results.csv 대한 정보가 포함된 파일과 모든 검색 결과에 대한 정보가 포함된 매니페스트 파일(XML 형식)도 내보내기됩니다.
  
사례와 연결된 단일 [](#export-the-results-of-a-single-search) 검색의 결과를 내보내거나 사례와 연결된 여러 검색의 결과를 내보낼 [수 있습니다.](#export-the-results-of-multiple-searches)
  
## <a name="export-the-results-of-a-single-search"></a>단일 검색 결과 내보내기

1. 적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 사용하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.

3. Core **eDiscovery** 페이지에서 검색 결과를 내보낼 사례를 선택하고 사례 **열기를 클릭합니다.**

4. 사례의 **홈** 페이지에서 검색 **탭을** 클릭합니다.

5. 사례에 대한 검색 목록에서 검색 결과를 내보낼 검색을 클릭한 다음  플라이아웃에서 결과 내보내기를 클릭합니다.

    결과 **내보내기** 페이지가 표시됩니다. 

    ![결과 내보내기 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Core eDiscovery 사례와 연결된 검색 결과를 내보내는 워크플로는 콘텐츠 검색 페이지에서 검색 결과를 내보내는 워크플로와 **동일합니다.** 단계별 지침은 콘텐츠 검색 결과 [내보내기를 참조하세요.](export-search-results.md)

    > [!NOTE]
    > 검색 결과를 내보낼 때 동일한 메시지의 여러 인스턴스가 검색된 사서함에 있을 수 있는 경우에도 전자 메일 메시지 복사본을 하나만 내보낼 수 있도록 중복 제거를 사용하도록 설정할 수 있습니다. 중복 제거 및 중복 항목을 식별하는 방법에 대한 자세한 내용은 [eDiscovery](de-duplication-in-ediscovery-search-results.md)검색 결과에서 중복 제거를 참조하세요.

    내보내기 시작하면 검색 결과가 다운로드 준비됩니다. 즉, Microsoft 클라우드의 Microsoft 제공 Azure Storage 위치에 업로드됩니다.
  
6. 내보내기 **탭을** 클릭하여 사례에 대한 내보내기 작업 목록을 표시합니다.
  
    새로 고침을 **클릭하여** 만든 내보내기 작업을 표시하기 위해 내보내기 작업 목록을 업데이트해야 할 수 있습니다. 내보내기 작업의 이름은 검색 이름에  추가된 _Export 검색과 동일합니다.

7. 만든 내보내기 작업을 클릭하여 플라이아웃 페이지에 상태 정보를 표시합니다. 이 정보에는 Azure Storage 위치로 전송된 항목의 백분율이 포함됩니다.

8. 모든 항목이 전송된 후  결과 다운로드를 클릭하여 검색 결과를 로컬 컴퓨터에 다운로드합니다. 검색 결과를 다운로드하는 자세한 내용은 콘텐츠 검색 결과 내보내기 [2단계를 참조하세요.](export-search-results.md#step-2-download-the-search-results)

## <a name="export-the-results-of-multiple-searches"></a>여러 검색 결과 내보내기

사례와 연결된 단일 검색의 결과를 내보내는 대신 단일 내보내기 작업에서 동일한 사례에서 여러 검색 결과를 내보낼 수 있습니다. 여러 검색의 결과를 한 번씩 내보내는 것보다 결과를 한 번 더 빠르고 쉽게 내보낼 수 있습니다.
  
> [!NOTE]
> 이러한 검색 중 하나를 보류된 위치로 구성한 경우 여러 검색 결과를 내보낼 수 없습니다.

1. 적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 사용하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.

3. Core **eDiscovery** 페이지에서 검색 결과를 내보낼 사례를 선택하고 사례 **열기를 클릭합니다.**

4. 사례의 **홈** 페이지에서 검색 **탭을** 클릭합니다.
    
5. 사례에 대한 검색 목록에서 검색 결과를 내보낼 둘 이상의 검색 옆에 있는 확인란을 선택합니다. 

   대량 **작업 플라이아웃** 페이지가 나타납니다. 

    ![대량 작업 페이지에서 결과 내보내기 클릭](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. 결과 **내보내기 를 클릭합니다.**

   결과 **내보내기** 페이지가 표시됩니다. 

    ![결과 내보내기 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    이때 Core eDiscovery 사례와 연결된 여러 검색의 결과를 내보내는 워크플로는 단일 검색에 대한 검색 결과를 내보내는 워크플로와 동일합니다. 이전 섹션의 5단계를 참조하세요.

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>여러 검색 결과 내보내기에 대한 자세한 정보

- 여러 검색의 결과를 내보내면 **OR** 연산자를 사용하여 모든 검색의 검색 쿼리가 결합된 다음 결합된 검색이 시작됩니다. 결합된 검색의 예상 결과는 선택한 내보내기 작업의 플라이아웃 페이지에 표시됩니다. 그런 다음 검색 결과가 Microsoft 클라우드의 Azure Storage 위치에 복사됩니다. 복사 작업의 상태도 플라이아웃 페이지에 표시됩니다. 앞서 설명한 것 처럼 모든 검색 결과가 복사된 후 로컬 컴퓨터에 다운로드할 수 있습니다.

- 내보낼 모든 검색에 대한 쿼리의 최대 키워드 수는 500개입니다. 단일 검색에 대한 제한과 동일합니다. 이는 내보내기 작업에서 **OR** 연산자를 사용하여 모든 검색 쿼리를 결합하기 때문에입니다. 이 제한을 초과하면 오류가 반환됩니다. 이 경우 더 적은 수의 검색에서 결과를 내보내거나 내보낼 원본 검색의 검색 쿼리를 단순화해야 합니다.

- 내보낼 검색 결과는 항목을 찾은 콘텐츠 위치에 따라 구성됩니다. 즉, 내보내기 결과의 콘텐츠 위치에 다른 검색에서 반환된 항목이 있을 수 있습니다. 예를 들어 각 사서함에 대해 하나의 PST 파일로 전자 메일 메시지를 내보내는 경우 PST 파일에 여러 검색 결과가 있을 수 있습니다.

- 동일한 콘텐츠 위치의 동일한 전자 메일 항목 또는 문서가 내보내는 검색 중 두 개 이상에 의해 반환되는 경우 항목의 복사본이 하나만 내보낼 수 있습니다.

- 여러 검색을 만든 후 내보내기 기능을 편집할 수 없습니다. 예를 들어 내보내기 작업에서 검색을 추가하거나 제거할 수 없습니다. 내보내는 검색 결과를 변경하기 위해 내보내기 작업을 만들어야 합니다. 내보내기 작업을 만든 후 결과를 컴퓨터에 다운로드하거나 내보내기 작업을 다시 시작하거나 내보내기 작업을 삭제할 수만 있습니다.

- 내보내기 작업을 다시 시작하는 경우 내보내기 작업을 만드는 검색의 쿼리에 대한 변경 내용은 검색된 검색 결과에 영향을 주지 않습니다. 내보내기 작업을 다시 시작하면 내보내기 작업을 만들 때 실행된 동일한 결합된 검색 쿼리 작업이 다시 실행됩니다.

- 또한 내보내기 기능을 다시 시작하면 Azure Storage 위치로 복사된 검색 결과가 이전 결과를 덮어 덮어 덮어입습니다. 복사된 이전 결과는 다운로드할 수 없습니다.

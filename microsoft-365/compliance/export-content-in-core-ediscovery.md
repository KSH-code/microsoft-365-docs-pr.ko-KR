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
description: 핵심 eDiscovery 사례에서 콘텐츠를 내보내고 다운로드하는 방법을 Microsoft 365.
ms.openlocfilehash: 68535f8623b26aa4f2b30dc88362f4550c256162
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184075"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Core eDiscovery 케이스에서 콘텐츠 내보내기

Core eDiscovery 사례와 연결된 검색이 성공적으로 실행된 후 검색 결과를 내보낼 수 있습니다. 검색 결과를 내보내면 사서함 항목이 PST 파일 또는 개별 메시지로 다운로드됩니다. 사이트 및 SharePoint 비즈니스용 OneDrive 내보낼 때 기본 Office 문서 및 기타 문서의 복사본을 내보낼 수 있습니다. 내보내는 Results.csv 대한 정보가 포함된 파일과 모든 검색 결과에 대한 정보가 포함된 매니페스트 파일(XML 형식)도 내보내기됩니다.
  
## <a name="export-search-results"></a>검색 결과 내보내기

1. 으로 이동한 후 적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 [https://compliance.microsoft.com](https://compliance.microsoft.com) 사용하여 로그인합니다.

2. 창의 왼쪽 탐색 창에서 Microsoft 365 규정 준수 센터 표시를 클릭한 다음 **eDiscovery**> 클릭합니다. 

3. Core **eDiscovery** 페이지에서 보류를 만들 사례의 이름을 클릭합니다.

4. 사례에 **대한 홈** 페이지에서 검색 **탭을** 클릭합니다.

5. **플라이아웃** 페이지의 아래쪽에 있는 작업 메뉴에서 결과 **내보내기 를 클릭합니다.**

   ![작업 메뉴에서 결과 내보내기 옵션입니다.](../media/ActionMenuExportResults.png)

   Core eDiscovery 사례와 연결된 검색 결과를 내보내는 워크플로는 콘텐츠 검색 페이지에서 검색 결과를 내보내는 워크플로와 **동일합니다.** 단계별 지침은 콘텐츠 검색 결과 [내보내기 를 참조하세요.](export-search-results.md)

   > [!NOTE]
   > 검색 결과를 내보낼 때 동일한 메시지의 여러 인스턴스가 검색된 사서함에 있을 수 있는 경우에도 전자 메일 메시지의 복사본 하나만 내보낼 수 있도록 중복 제거를 사용하도록 설정할 수 있습니다. 중복 제거 및 중복 항목을 식별하는 방법에 대한 자세한 내용은 [eDiscovery](de-duplication-in-ediscovery-search-results.md)검색 결과에서 중복 제거를 참조하세요.

   내보내기 시작하면 검색 결과가 다운로드할 수 있습니다. 즉, 검색 결과가 Microsoft 클라우드의 Microsoft 제공 Azure Storage 위치로 전송됩니다.
  
6. 이 경우 **내보내기** 탭을 클릭하여 내보내기 작업 목록을 표시합니다.
  
   ![Core eDiscovery 사례의 내보내기 탭에서 작업을 내보낼 수 있습니다.](../media/CoreeDiscoveryExport.png)

   새로 고침을 **클릭하여** 만든 내보내기 작업이 표시될 수 있도록 내보내기 작업 목록을 업데이트해야 할 수 있습니다. 내보내기 작업의 이름은 검색 이름에  추가된 _Export 검색과 동일합니다.

7. 만든 내보내기 작업을 클릭하여 플라이아웃 페이지에 상태 정보를 표시합니다. 이 정보에는 이전 위치로 전송된 항목의 Azure Storage 포함됩니다.

8. 모든 항목이 전송된 후  결과 다운로드를 클릭하여 검색 결과를 로컬 컴퓨터에 다운로드합니다. 검색 결과를 다운로드하는 자세한 내용은 콘텐츠 검색 결과 내보내기에서 [2단계를 참조하세요.](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>사례에서 검색 내보내기에 대한 자세한 정보

- 검색 결과를 내보낼 때 포함된 파일 내보내기에 대한 자세한 내용은 콘텐츠 검색 보고서 [내보내기 를 참조하세요.](export-a-content-search-report.md#whats-included-in-the-report)

- 내보내기 작업을 다시 시작하는 경우 내보내기 작업을 만드는 검색의 쿼리에 대한 변경 내용은 검색된 검색 결과에 영향을 주지 않습니다. 내보내기 작업을 다시 시작하면 내보내기 작업을 만들 때 실행된 동일한 결합된 검색 쿼리 작업이 다시 실행됩니다.

- 또한 내보내기 기능을 다시 시작하면 해당 위치로 복사된 검색 Azure Storage 이전 결과를 덮어 덮어 매기게 됩니다. 복사한 이전 결과는 다운로드할 수 없습니다.

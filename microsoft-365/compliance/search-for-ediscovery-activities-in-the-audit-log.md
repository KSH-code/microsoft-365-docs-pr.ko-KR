---
title: 감사 로그에서 eDiscovery 활동 검색
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: EDiscovery 권한이 할당 된 사용자가 보안 & 준수 센터에서 콘텐츠 검색 및 코어 eDiscovery 작업을 수행할 때 기록 되는 이벤트에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 529e1a0ac3dc66ac15bd1b3fbcde466fb36d5f4e
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357548"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>감사 로그에서 eDiscovery 활동 검색

보안 & 준수 센터에서 또는 해당 PowerShell cmdlet을 실행 하 여 수행 되는 핵심 eDiscovery 및 고급 eDiscovery에 대 한 콘텐츠 검색 및 eDiscovery 관련 작업을 감사 로그에 기록 합니다. 이벤트는 관리자나 eDiscovery 관리자 또는 사용자가 할당 한 eDiscovery 권한이 있는 경우 보안 & 준수 센터에서 다음과 같은 콘텐츠 검색 및 핵심 eDiscovery 작업을 수행할 때 기록 됩니다.
  
- 핵심 및 고급 eDiscovery 사례 만들기 및 관리

- 콘텐츠 검색 만들기, 시작 및 편집

- 검색 결과 미리 보기, 내보내기, 삭제 등 콘텐츠 검색 작업 수행

- 고급 eDiscovery에서 custodians 및 검토 집합 관리

- 콘텐츠 검색에 대한 사용 권한 필터링 구성

- eDiscovery 관리자 역할 관리

> [!IMPORTANT]
> 이 문서에서 설명 하는 작업은 보안 & 준수 센터를 사용 하 여 수행 된 eDiscovery 작업의 결과에 불과합니다. Exchange Online의 원본 위치 eDiscovery 도구 또는 SharePoint Online의 eDiscovery Center를 사용 하 여 수행한 eDiscovery 작업은 포함 되지 않습니다. 
  
감사 로그 검색, 필요한 권한, 검색 결과 내보내기에 대 한 자세한 내용은 [Security & 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>EDiscovery 작업을 검색 하 고 확인 하는 방법

현재 감사 로그에서 eDiscovery 활동을 확인 하려면 몇 가지 특정 작업을 수행 해야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.
  
1. [https://protection.office.com](https://protection.office.com)으로 이동합니다.

2. 회사 또는 학교 계정을 사용하여 로그인합니다.

3. 왼쪽 창에서 **검색**을 클릭 하 고 **감사 로그 검색**을 클릭 합니다.

4. **작업** 드롭다운 목록의 **EDiscovery 작업** 또는 **고급 eDiscovery 활동**에서 검색할 활동을 하나 이상 클릭 합니다.

    > [!NOTE]
    > 또한 **작업** 드롭다운 목록에는 cmdlet 감사 로그의 레코드를 반환 하는 **eDiscovery cmdlet 작업** 이라는 작업 그룹이 포함 되어 있습니다.
  
5. 날짜 및 시간 범위를 선택 하 여 해당 기간 내에 발생 한 eDiscovery 이벤트를 표시 합니다. 

6. **사용자** 상자에서 검색 결과를 표시할 사용자를 한 명 이상 선택 합니다. 모든 사용자에 대 한 항목을 반환 하려면이 상자를 비워 둡니다.

7. **검색**을 클릭하여 검색 조건을 사용한 검색을 실행합니다. 

8. 검색 결과가 표시 된 후 **결과 필터링** 을 클릭 하 여 결과 활동 레코드를 필터링 하거나 정렬할 수 있습니다. 아쉽게도 필터링을 사용 하 여 특정 활동을 명시적으로 제외할 수는 없습니다. 

9. 활동에 대 한 세부 정보를 보려면 검색 결과 목록에서 활동 레코드를 클릭 합니다. 

    이벤트 레코드의 자세한 속성을 포함 하는 **세부 정보가** 플라이 아웃 페이지에 표시 됩니다. 자세한 내용을 표시 하려면 **추가 정보**를 클릭 합니다. 이러한 속성에 대 한 [자세한 내용은 eDiscovery 작업에 대 한 자세한 속성](#detailed-properties-for-ediscovery-activities) 섹션을 참조 하십시오.

10. 필요한 경우 감사 로그 검색 결과를 CSV 파일로 내보낸 다음 Excel 파워 쿼리 기능을 사용 하 여 이러한 레코드의 서식 지정 및 필터링을 수행할 수 있습니다. 자세한 내용은 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md)를 참조하세요.

## <a name="ediscovery-activities"></a>eDiscovery 활동

다음 표에서는 관리자 또는 eDiscovery 관리자가 보안 & 준수 센터를 사용 하 여 eDiscovery 관련 작업을 수행 하거나 보안 & 준수 센터 PowerShell에서 해당 cmdlet을 실행 하는 경우 기록 되는 콘텐츠 검색 및 핵심 eDiscovery 작업에 대해 설명 합니다. 또한이 목록에서 활동을 검색할 때 Advanced에서 수행 되는 일부 활동이 반환 됩니다.
  
> [!NOTE]
> 이 섹션에서 설명 하는 eDiscovery 작업은 다음 섹션에서 설명 하는 eDiscovery cmdlet 작업에 대 한 유사한 정보를 제공 합니다. 이 섹션에서 설명 하는 eDiscovery 작업은 감사 로그 검색 결과에서 30 분 이내에 표시 되므로 사용 하는 것이 좋습니다. EDiscovery cmdlet 작업이 감사 로그 검색 결과에 표시 되는 데 최대 24 시간이 걸릴 수 있습니다. 
  
|**친숙한 이름**|**작업**|**해당 cmdlet**|**설명**|
|:-----|:-----|:-----|:-----|
|EDiscovery 사례에 구성원이 추가 됨  <br/> |CaseMemberAdded  <br/> |Get-compliancecasemember 추가  <br/> |사용자가 eDiscovery 사례의 구성원으로 추가 되었습니다. 사례 구성원으로 서, 사용자는 필요한 권한이 할당 되었는지 여부에 따라 다양 한 사례 관련 작업을 수행할 수 있습니다.  <br/> |
|변경 된 콘텐츠 검색  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |기존 콘텐츠 검색이 변경 되었습니다. 변경 사항에는 콘텐츠 위치 추가 또는 제거 또는 검색 쿼리 편집이 포함 될 수 있습니다.  <br/> |
|EDiscovery 관리자 멤버 자격 변경  <br/> |CaseAdminUpdated  <br/> |업데이트-eDiscoveryCaseAdmin  <br/> |조직의 eDiscovery 관리자 목록이 변경 되었습니다. 이 작업은 eDiscovery 관리자 목록이 새 사용자의 그룹으로 바뀔 때 기록 됩니다. 단일 사용자를 추가 하거나 제거 하면 CaseAdminAdded 작업이 기록 됩니다.  <br/> |
|EDiscovery 사례 변경  <br/> |CaseUpdated  <br/> |Remove-compliancecase  <br/> |EDiscovery 사례가 변경 되었습니다. 변경 내용에는 대/소문자 닫기 또는 닫힌 사례 다시 열기가 포함 됩니다.  <br/> |
|EDiscovery 사례 구성원 자격이 변경 됨  <br/> |CaseMemberUpdated  <br/> |업데이트-Get-compliancecasemember  <br/> |EDiscovery 사례의 구성원 목록이 변경 되었습니다. 이 작업은 모든 구성원이 새 사용자의 그룹으로 바뀔 때 기록 됩니다. 단일 구성원을 추가 하거나 제거 하는 경우 CaseMemberAdded 또는 CaseMemberRemoved 작업이 기록 됩니다.  <br/> |
|변경 된 검색 권한 필터  <br/> |Search추가 업데이트  <br/> |New-compliancesecurityfilter  <br/> |검색 권한 필터가 변경 되었습니다.  <br/> |
|EDiscovery 사례 보류에 대 한 검색 쿼리 변경  <br/> |HoldUpdated  <br/> |New-caseholdrule  <br/> |EDiscovery 사례와 관련 된 쿼리 기반 보류가 변경 되었습니다. 가능한 변경 사항에는 쿼리 기반 보존에 대 한 쿼리 또는 날짜 범위 편집이 포함 됩니다.  <br/> |
|콘텐츠 검색 미리 보기 항목 다운로드 됨  <br/> |PreviewItemDownloaded  <br/> |해당 없음  <br/> |사용자가 검색 결과를 미리 볼 때 **원래 항목 다운로드** 링크를 클릭 하 여 항목을 로컬 컴퓨터에 다운로드 한 경우  <br/> |
|나열 된 콘텐츠 검색 미리 보기 항목  <br/> |PreviewItemListed  <br/> |해당 없음  <br/> |사용자가 **검색 결과 미리 보기** 를 클릭 하 여 콘텐츠 검색 결과에서 최대 1000 개의 항목을 나열 하는 검색 결과 미리 보기 페이지를 표시 합니다.  <br/> |
|콘텐츠 검색 미리 보기 항목 표시  <br/> |PreviewItemRendered  <br/> |해당 없음  <br/> |EDiscovery 관리자가 검색 결과를 미리 볼 때 해당 항목을 클릭 하 여 확인 했습니다.  <br/> |
|만든 콘텐츠 검색  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |새 콘텐츠 검색을 만들었습니다.  <br/> |
|EDiscovery 관리자를 만들었습니다.  <br/> |CaseAdminAdded  <br/> |EDiscoveryCaseAdmin 추가  <br/> |사용자가 조직에서 eDiscovery 관리자로 추가 되었습니다.  <br/> |
|EDiscovery 사례를 만들었습니다.  <br/> |CaseAdded  <br/> |Remove-compliancecase  <br/> |EDiscovery 사례를 만들었습니다. 사례를 만들 때 이름을 지정 하기만 하면 됩니다. 멤버 추가, 보류 만들기, 사례와 연결 된 콘텐츠 검색 만들기 등의 기타 사례 관련 작업은 추가 이벤트가 기록 됩니다.  <br/> |
|만든 검색 권한 필터  <br/> |SearchPermissionCreated  <br/> |New-compliancesecurityfilter  <br/> |검색 권한 필터를 만들었습니다.  <br/> |
|EDiscovery 사례 보류에 대 한 검색 쿼리를 만들었습니다.  <br/> |HoldCreated  <br/> |New-caseholdrule  <br/> |EDiscovery 사례와 관련 된 쿼리 기반 보류를 만들었습니다.  <br/> |
|삭제 된 콘텐츠 검색  <br/> |SearchRemoved 됨  <br/> |Remove-ComplianceSearch  <br/> |기존 콘텐츠 검색이 삭제 되었습니다.  <br/> |
|삭제 된 eDiscovery 관리자  <br/> |CaseAdminRemoved  <br/> |EDiscoveryCaseAdmin을 제거 합니다.  <br/> |EDiscovery 관리자가 조직에서 삭제 되었습니다.  <br/> |
|삭제 된 eDiscovery 사례  <br/> |CaseRemoved  <br/> |Remove-compliancecase을 제거 합니다.  <br/> |EDiscovery 사례가 삭제 되었습니다. 사례를 삭제 하려면 먼저 케이스와 연결 된 보류를 모두 제거 해야 합니다.  <br/> |
|삭제 된 검색 권한 필터  <br/> |Search에이 제거 됨  <br/> |New-compliancesecurityfilter을 제거 합니다.  <br/> |검색 권한 필터가 삭제 되었습니다.  <br/> |
|EDiscovery 사례 보류에 대해 삭제 된 검색 쿼리  <br/> |HoldRemoved  <br/> |New-caseholdrule을 제거 합니다.  <br/> |EDiscovery 사례와 관련 된 쿼리 기반 보류가 삭제 되었습니다. 보류 삭제의 결과는 보류에서 쿼리를 제거 하는 경우가 많습니다. 보류 또는 보류 쿼리를 삭제 하면 보류 되었던 콘텐츠 위치가 릴리스됩니다.  <br/> |
|다운로드 된 콘텐츠 검색 내보내기  <br/> |SearchExportDownloaded  <br/> |해당 없음  <br/> |사용자가 콘텐츠 검색 결과를 로컬 컴퓨터에 다운로드 했습니다. 검색 결과를 다운로드 하려면 먼저 **콘텐츠 검색 작업의 내보내기를** 시작 해야 합니다.  <br/> |
|미리 본 콘텐츠 검색 결과  <br/> |SearchPreviewed 보기  <br/> |해당 없음  <br/> |콘텐츠 검색 결과를 미리 본 사용자입니다.  <br/> |
|제거 된 콘텐츠 검색 결과  <br/> |SearchResultsPurged  <br/> |New-compliancesearchaction  <br/> |사용자가 **new-compliancesearchaction** 명령을 실행 하 여 콘텐츠 검색의 결과를 제거 했습니다.  <br/> |
|콘텐츠 검색 분석이 제거 됨  <br/> |RemovedSearchResultsSentToZoom  <br/> |New-compliancesearchaction을 제거 합니다.  <br/> |콘텐츠 검색 준비 작업 (고급 eDiscovery에 대 한 검색 결과 준비)이 삭제 되었습니다. 준비 작업이 2 주 이내 였으 면 고급 eDiscovery 용으로 준비 된 검색 결과가 Microsoft Azure storage 영역에서 삭제 되었습니다. 준비 작업이 2 주 이상 경과 된 경우이 이벤트는 해당 준비 동작만 삭제 되었음을 나타냅니다.  <br/> |
|콘텐츠 검색 내보내기 제거 됨  <br/> |RemovedSearchExported  <br/> |New-compliancesearchaction을 제거 합니다.  <br/> |콘텐츠 검색 내보내기 작업이 삭제 되었습니다. 내보내기 작업이 2 주 이내 였던 경우 Microsoft Azure 저장소 영역에 업로드 된 검색 결과가 삭제 되었습니다. 내보내기 작업이 2 주 보다 오래 된 경우이 이벤트는 해당 내보내기 동작만 삭제 되었음을 나타냅니다.  <br/> |
|EDiscovery 사례에서 구성원 제거 됨  <br/> |CaseMemberRemoved  <br/> |Get-compliancecasemember을 제거 합니다.  <br/> |사용자가 eDiscovery 사례의 구성원으로 제거 되었습니다.  <br/> |
|콘텐츠 검색 결과 미리 보기 제거 됨  <br/> |RemovedSearchPreviewed  <br/> |New-compliancesearchaction을 제거 합니다.  <br/> |콘텐츠 검색 미리 보기 작업이 삭제 되었습니다.  <br/> |
|콘텐츠 검색에 대해 수행 된 삭제 된 제거 작업  <br/> |RemovedSearchResultsPurged  <br/> |New-compliancesearchaction을 제거 합니다.  <br/> |콘텐츠 검색 제거 작업이 삭제 되었습니다.  <br/> |
|제거 된 검색 보고서  <br/> |SearchReportRemoved 됨  <br/> |New-compliancesearchaction을 제거 합니다.  <br/> |콘텐츠 검색 내보내기 보고서 작업이 삭제 되었습니다.  <br/> |
|콘텐츠 검색 분석이 시작 됨  <br/> |SearchResultsSentToZoom  <br/> |New-compliancesearchaction  <br/> |콘텐츠 검색 결과는 고급 eDiscovery에서 분석을 위해 준비 되었습니다.  <br/> |
|시작 콘텐츠 검색  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |콘텐츠 검색을 시작 했습니다. 보안 & 준수 센터 GUI를 사용 하 여 콘텐츠 검색을 만들거나 변경 하면 검색이 자동으로 시작 됩니다. **ComplianceSearch** 또는 **ComplianceSearch** cmdlet을 사용 하 여 검색을 만들거나 변경 하는 경우 **ComplianceSearch** cmdlet을 실행 하 여 검색을 시작 해야 합니다.  <br/> |
|콘텐츠 검색 내보내기 시작  <br/> |내보낸 search  <br/> |New-compliancesearchaction  <br/> |사용자가 콘텐츠 검색 결과를 내보냈습니다.  <br/> |
|보고서 내보내기 시작  <br/> |SearchReport  <br/> |New-compliancesearchaction  <br/> |사용자가 콘텐츠 검색 보고서를 내보냈습니다.  <br/> |
|콘텐츠 검색 중지 됨  <br/> |SearchStopped 됨  <br/> |Stop-ComplianceSearch  <br/> |사용자가 콘텐츠 검색을 중지 했습니다.  <br/> |
|(없음)|CaseViewed|Remove-compliancecase|사용자가 보안 및 준수 센터의 **eDiscovery** 페이지에서 또는 cmdlet을 실행 하 여 사례 목록을 본 경우|
|(없음)|SearchViewed|Get-ComplianceSearch|보안 및 준수 센터에서 또는 cmdlet을 실행 하 여 **검색** 탭에 나열 된 콘텐츠 검색에 대 한 목록을 본 사용자입니다. 이 작업은 사용자가 eDiscovery 사례와 연결 된 콘텐츠 검색 목록을 보거나 사례에서 **검색** 탭을 클릭 하 여 **ComplianceSearch** 명령을 실행 하는 경우에도 기록 됩니다.|
|(없음)|ViewedSearchExported|New-compliancesearchaction-Export|보안 및 준수 센터에서 또는 cmdlet을 실행 하 여 **내보내기** 탭에 나열 된 콘텐츠 검색 내보내기 작업 목록을 본 사용자입니다. 또한이 작업은 사용자가 eDiscovery 사례의 내보내기 작업 목록을 볼 때, **예를 들면 내보내기 탭에** 나열 되어 있거나 **new-compliancesearchaction-export** 명령을 실행 하는 경우에도 기록 됩니다.|
|(없음)|ViewedSearchPreviewed|New-compliancesearchaction-Preview|사용자는 보안 및 준수 센터에서 또는 cmdlet을 실행 하 여 콘텐츠 검색 결과를 미리 볼 수 있습니다.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>고급 eDiscovery 활동

다음 표에서는 감사 로그에 기록 된 고급 eDiscovery 작업에 대해 설명 합니다. 이러한 작업 (관련 eDiscovery 활동 외에도 고급 eDiscovery 사례에서 활동 진행을 추적 하는 데 도움이 될 수 있습니다.

|**친숙한 이름**|**작업**|**설명**|
|:-----|:-----|:-----|
|다른 검토 집합에 데이터 추가됨|AddWorkingSetQueryToWorkingSet|사용자가 한 검토 집합에서 다른 검토 집합으로 문서를 추가했습니다.|
|검토 집합에 데이터 추가됨|AddQueryToWorkingSet|사용자가 고급 eDiscovery 사례와 연결된 콘텐츠 검색에서 검토 집합에 검색 결과를 추가했습니다.|
|검토 집합에 비 Microsoft 365 데이터 추가됨|AddNonOffice365DataToWorkingSet|사용자가 검토 집합에 비 Microsoft 365 데이터를 추가했습니다.|
|수정된 문서가 검토 집합에 추가됨|AddRemediatedData|사용자가 검토 집합으로 수정된 색인 작성 오류가 있는 문서를 업로드합니다.|
|검토 집합의 데이터가 분석됨|RunAlgo|사용자가 검토 집합의 문서에 대한 분석을 실행했습니다.|
|검토 집합의 문서에 주석이 달림|AnnotateDocument|사용자가 검토 집합의 문서에 주석을 달았습니다. 주석에는 문서의 내용을 편집하는 것이 포함되어 있습니다. |
|부하 집합 비교됨|LoadComparisonJob|사용자가 검토 집합에서 서로 다른 두 개의 부하 집합을 비교했습니다. 부하 집합은 사례와 연결된 콘텐츠 검색 데이터가 검토 집합에 추가되는 경우입니다.|
|편집된 문서가 PDF로 변환됨|BurnJob|사용자가 검토의 모든 편집된 문서를 PDF 파일로 변환했습니다.|
|검토 집합 생성됨|CreateWorkingSet|사용자가 검토 집합을 만들었습니다.|
|검토 집합 검색 생성됨|CreateWorkingSetSearch|사용자가 검토 집합에서 문서를 검색하는 검색 쿼리를 만들었습니다.|
|태그 생성됨|태그 생성|사용자가 검토 집합에 태그 그룹을 만들었습니다. 태그 그룹에는 하나 이상의 하위 태그가 포함될 수 있습니다. 그런 다음 이 태그를 사용하여 검토 집합의 문서에 태그를 지정합니다.|
|검토 집합 검색 삭제됨|DeleteWorkingSetSearch|사용자가 검토 집합에서 검색 쿼리를 삭제했습니다.|
|태그 삭제됨|DeleteTag|사용자가 검토 집합의 태그 그룹을 삭제었습니다.|
|문서 다운로드됨|DownloadDocument|사용자가 검토 집합에서 문서를 다운로드했습니다.|
|태그 편집됨|UpdateTag|사용자가 검토 집합에서 태그를 변경했습니다.|
|검토 집합에서 문서 내보냄|ExportJob|사용자가 검토 집합에서 문서를 내보냈습니다.|
|사례 설정 수정됨|UpdateCaseSettings|사용자가 사례에 대한 설정을 수정했습니다. 사례 설정에는 사례 정보, 액세스 권한 및 검색 및 분석 동작을 제어하는 설정이 포함됩니다.|
|검토 집합 검색 수정됨|UpdateWorkingSetSearch|사용자가 검토 집합에서 검색 쿼리를 편집했습니다.|
|검토 집합 검색 미리 보기됨|PreviewWorkingSetSearch|사용자가 검토 집합에 검색 쿼리의 결과를 미리 보았습니다.|
|오류 문서 수정됨|ErrorRemediationJob|사용자가 인덱싱 오류가 있는 파일을 수정합니다.|
|문서에 태그가 지정됨|TagFiles|사용자가 검토 집합의 문서에 태그를 지정합니다.|
|쿼리의 결과가 태그됨|TagJob|사용자는 검토 집합의 검색 쿼리 조건과 일치하는 모든 문서를 태그합니다.|
|검토 집합의 문서 조회됨|ViewDocument|사용자가 검토 집합의 문서를 조회했습니다.|
|||

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery cmdlet 작업

다음 표에서는 관리자 또는 사용자가 보안 & 준수 센터를 사용 하 여 eDiscovery 관련 작업을 수행 하거나 조직의 보안 & 준수 센터에 연결 된 원격 PowerShell에서 해당 cmdlet을 실행 하 여 기록 되는 cmdlet 감사 로그 레코드를 보여 줍니다. 이 표에 나와 있는 cmdlet 작업 및 이전 섹션에 설명 된 eDiscovery 작업에 대 한 감사 로그 레코드의 자세한 정보는 서로 다릅니다.
  
앞에서 설명한 것 처럼 감사 로그 검색 결과에 eDiscovery cmdlet 작업을 표시 하는 데 최대 24 시간이 걸릴 수 있습니다.
  
> [!TIP]
> 다음 표의 **작업** 열에 있는 Cmdlet은 TechNet의 해당 cmdlet 도움말 항목에 연결 됩니다. 각 cmdlet에 대해 사용 가능한 매개 변수에 대 한 설명을 보려면 cmdlet 도움말 항목으로 이동 합니다. Cmdlet에 사용 된 매개 변수 및 매개 변수 값은 로깅된 각 eDiscovery cmdlet 작업에 대 한 감사 로그 항목에 포함 됩니다. 
  
|**친숙한 이름**|**작업 (cmdlet)**|**설명**|
|:-----|:-----|:-----|
|EDiscovery 사례에서 생성 되는 보류  <br/> |[New-caseholdpolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |EDiscovery 사례에 대 한 보류를 만들었습니다. 콘텐츠 원본을 지정 하지 않고 또는을 사용 하 여 보류를 만들 수 있습니다. 콘텐츠 원본이 지정 된 경우 감사 로그 항목에서 식별 됩니다.  <br/> |
|EDiscovery 사례에서 보류 삭제  <br/> |[New-caseholdpolicy을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |EDiscovery 사례와 연결 된 보류가 삭제 되었습니다. 보류를 삭제 하면 보류의 모든 콘텐츠 위치가 해제 됩니다. 보류를 삭제 하면 보류와 연결 된 케이스 보류 규칙도 삭제 됩니다 (아래 **new-caseholdrule** 참조).  <br/> |
|EDiscovery 사례의 변경 된 보류  <br/> |[New-caseholdpolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |EDiscovery와 연결 된 보류가 변경 되었습니다. 가능한 변경 사항으로는 콘텐츠 위치를 추가 또는 제거 하거나 보류를 해제 (사용 하지 않도록 설정)가 포함 됩니다.  <br/> |
|EDiscovery 사례 보류에 대 한 검색 쿼리를 만들었습니다.  <br/> |[New-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |EDiscovery 사례와 관련 된 쿼리 기반 보류를 만들었습니다.  <br/> |
|EDiscovery 사례 보류에 대해 삭제 된 검색 쿼리  <br/> |[New-caseholdrule을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |EDiscovery 사례와 관련 된 쿼리 기반 보류가 삭제 되었습니다. 보류 삭제의 결과는 보류에서 쿼리를 제거 하는 경우가 많습니다. 보류 또는 보류 쿼리를 삭제 하면 보류 되었던 콘텐츠 위치가 릴리스됩니다.  <br/> |
|EDiscovery 사례 보류에 대 한 검색 쿼리 변경  <br/> |[New-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |EDiscovery 사례와 관련 된 쿼리 기반 보류가 변경 되었습니다. 가능한 변경 사항에는 쿼리 기반 보존에 대 한 쿼리 또는 날짜 범위 편집이 포함 됩니다.  <br/> |
|EDiscovery 사례를 만들었습니다.  <br/> |[Remove-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |EDiscovery 사례를 만들었습니다. 사례를 만들 때 이름을 지정 하기만 하면 됩니다. 멤버 추가, 보류 만들기, 사례와 연결 된 콘텐츠 검색 만들기 등의 기타 사례 관련 작업은 추가 이벤트가 기록 됩니다.  <br/> |
|삭제 된 eDiscovery 사례  <br/> |[Remove-compliancecase을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |EDiscovery 사례가 삭제 되었습니다. 사례를 삭제 하려면 먼저 케이스와 연결 된 보류를 모두 제거 해야 합니다.  <br/> |
|EDiscovery 사례 변경  <br/> |[Remove-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |EDiscovery 사례가 변경 되었습니다. 변경 내용에는 대/소문자 닫기 또는 닫힌 사례 다시 열기가 포함 됩니다.  <br/> |
|EDiscovery 사례에 구성원이 추가 됨  <br/> |[Get-compliancecasemember 추가](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |사용자가 eDiscovery 사례의 구성원으로 추가 되었습니다. 사례 구성원으로 서, 사용자는 필요한 권한이 할당 되었는지 여부에 따라 다양 한 사례 관련 작업을 수행할 수 있습니다.  <br/> |
|EDiscovery 사례에서 구성원 제거 됨  <br/> |[Get-compliancecasemember을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |사용자가 eDiscovery 사례의 구성원으로 제거 되었습니다.  <br/> |
|EDiscovery 사례 구성원 자격이 변경 됨  <br/> |[업데이트-Get-compliancecasemember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |EDiscovery 사례의 구성원 목록이 변경 되었습니다. 이 작업은 모든 구성원이 새 사용자의 그룹으로 바뀔 때 기록 됩니다. 단일 구성원을 추가 하거나 제거 하는 경우 **get-compliancecasemember** 또는 **get-compliancecasemember** 작업이 기록 됩니다.  <br/> |
|만든 콘텐츠 검색  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |새 콘텐츠 검색을 만들었습니다.  <br/> |
|삭제 된 콘텐츠 검색  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |기존 콘텐츠 검색이 삭제 되었습니다.  <br/> |
|변경 된 콘텐츠 검색  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |기존 콘텐츠 검색이 변경 되었습니다. 이러한 변경 사항에는 검색 쿼리를 편집 하거나 편집할 콘텐츠 위치를 추가 하거나 제거 하는 것이 포함 될 수 있습니다.  <br/> |
|시작 콘텐츠 검색  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |콘텐츠 검색을 시작 했습니다. 보안 & 준수 센터 GUI를 사용 하 여 콘텐츠 검색을 만들거나 변경 하면 검색이 자동으로 시작 됩니다. **ComplianceSearch** 또는 **ComplianceSearch** cmdlet을 사용 하 여 검색을 만들거나 변경 하는 경우 **ComplianceSearch** cmdlet을 실행 하 여 검색을 시작 해야 합니다.  <br/> |
|콘텐츠 검색 중지 됨  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |실행 중 이었던 콘텐츠 검색을 중지 했습니다.  <br/> |
|만든 콘텐츠 검색 작업  <br/> |[New-compliancesearchaction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |콘텐츠 검색 작업을 만들었습니다. 콘텐츠 검색 작업에는 검색 결과 미리 보기, 검색 결과 내보내기, 고급 eDiscovery에서 분석에 대 한 검색 결과 준비, 콘텐츠 검색의 검색 조건과 일치 하는 항목 영구 삭제 등이 포함 됩니다.  <br/> |
|삭제 된 콘텐츠 검색 작업  <br/> |[New-compliancesearchaction을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |콘텐츠 검색 작업이 삭제 되었습니다.  <br/> |
|만든 검색 권한 필터  <br/> |[New-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |검색 권한 필터를 만들었습니다.  <br/> |
|삭제 된 검색 권한 필터  <br/> |[New-compliancesecurityfilter을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |검색 권한 필터가 삭제 되었습니다.  <br/> |
|변경 된 검색 권한 필터  <br/> |[New-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |검색 권한 필터가 변경 되었습니다.  <br/> |
|EDiscovery 관리자를 만들었습니다.  <br/> |[EDiscoveryCaseAdmin 추가](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |사용자가 조직에서 eDiscovery 관리자로 추가 되었습니다.  <br/> |
|삭제 된 eDiscovery 관리자  <br/> |[EDiscoveryCaseAdmin을 제거 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |EDiscovery 관리자가 조직에서 삭제 되었습니다.  <br/> |
|EDiscovery 관리자 멤버 자격 변경  <br/> |[업데이트-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |조직의 eDiscovery 관리자 목록이 변경 되었습니다. 이 작업은 eDiscovery 관리자 목록이 새 사용자의 그룹으로 바뀔 때 기록 됩니다. 단일 사용자를 추가 하거나 제거 하는 경우 **eDiscoveryCaseAdmin** 또는 **eDiscoveryCaseAdmin 제거** 작업이 기록 됩니다.  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>EDiscovery 작업에 대 한 자세한 속성

다음 표에는 검색 결과에 나열 된 eDiscovery 활동에 대 한 **세부** 정보 페이지에서 **자세한 내용을** 클릭 하면 포함 되는 속성에 대 한 설명이 나와 있습니다. 이러한 속성은 감사 로그 검색 결과를 내보낼 때 CSV 파일에도 포함 됩니다. EDiscovery 활동에 대 한 감사 로그 레코드에는 아래 나열 된 모든 세부 속성이 포함 되지 않습니다. 
  
> [!TIP]
> 검색 결과를 내보낼 때 CSV 파일에는 여러 값 속성의 다음 표에 설명 된 자세한 속성을 포함 하는 **Detail**이라는 열이 포함 되어 있습니다. Excel에서 파워 쿼리 기능을 사용 하 여이 열을 여러 열로 분할 하 여 각 속성에 자체 열을 표시할 수 있습니다. 이렇게 하면 이러한 속성 중 하나 이상을 정렬 및 필터링 할 수 있습니다. 자세한 내용은 [search the audit log](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)에서 "파일로 검색 결과 내보내기" 섹션을 참조 하십시오. 
  
|**속성**|**설명**|
|:-----|:-----|
|사례  <br/> |생성, 변경 또는 삭제 된 eDiscovery 사례의 id (GUID)입니다.  <br/> |
|ClientApplication  <br/> |eDiscovery cmdlet 활동에는이 속성에 대 한 값이 **EMC** 로 포함 됩니다. 이는 보안 & 준수 센터 GUI를 사용 하 여 작업을 수행한 것 이며 PowerShell에서 cmdlet을 실행 하는 것을 나타냅니다.  <br/> |
|ClientIP  <br/> |활동을 로그할 때 사용 된 장치의 IP 주소입니다. IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다.  <br/> |
|ClientRequestId  <br/> | EDiscovery 작업의 경우이 속성은 일반적으로 비어 있습니다.  <br/> |
|CmdletVersion  <br/> |조직에서 실행 되는 보안 & 준수 센터 버전의 빌드 번호입니다.  <br/> |
|CreationTime  <br/> |EDiscovery 활동이 완료 된 UTC (협정 세계시)로 된 날짜와 시간입니다.  <br/> |
|EffectiveOrganization  <br/> |Microsoft 365 조직의 이름입니다.  <br/> |
|ExchangeLocations  <br/> |콘텐츠 검색에 포함 되거나 eDiscovery 사례에서 보류 된 Exchange Online 사서함입니다.  <br/> |
|제외 항목  <br/> |EDiscovery 사례의 콘텐츠 검색 또는 보류에서 제외 되는 사서함 또는 사이트 위치입니다.  <br/> |
|ExtendedProperties  <br/> |콘텐츠 검색의 추가 속성, 콘텐츠 검색 작업 또는 eDiscovery 사례 (예: 개체 GUID, 작업을 수행할 때 사용 된 cmdlet 매개 변수 등)  <br/> |
|Id  <br/> |보고서 항목의 ID입니다. ID는 감사 로그 항목을 고유 하 게 식별 합니다.  <br/> |
|NonPIIParameters  <br/> |Operation 속성에서 식별 한 cmdlet에 사용 된 매개 변수 (값 제외)의 목록입니다. 이 속성에 나열 된 매개 변수는 Parameters 속성에 나와 있는 것과 동일 합니다.  <br/> |
|Id  <br/> |작업 속성에 나열 된 작업에 의해 만들어지거나, 변경 되거나, 삭제 되는 개체의 GUID 또는 이름 (예: 콘텐츠 검색 또는 eDiscovery 사례)입니다. 이 개체는 감사 로그 검색 결과의 항목 열에도 식별 됩니다.  <br/> |
|ObjectType  <br/> |사용자가 만들거나 삭제 하거나 수정한 eDiscovery 개체의 유형입니다. 예를 들어 콘텐츠 검색 작업 (미리 보기, 내보내기 또는 삭제), eDiscovery 사례 또는 콘텐츠 검색 등이 있습니다.  <br/> |
|작업  <br/> |수행한 eDiscovery 활동에 해당 하는 작업의 이름입니다.  <br/> |
|OrganizationId  <br/> |Microsoft 365 조 직의 GUID입니다.  <br/> |
|매개 변수  <br/> |해당 cmdlet에 사용 된 매개 변수의 이름 및 값입니다.  <br/> |
|PublicFolderLocations  <br/> |콘텐츠 검색에 포함 되거나 eDiscovery 사례에 유지 되는 Exchange Online의 공용 폴더 위치입니다.  <br/> |
|Query  <br/> |활동에 연결 된 검색 쿼리 (예: 콘텐츠 검색 또는 쿼리 기반 유지)  <br/> |
|RecordType  <br/> |Record에서 지정한 작업의 유형입니다. **18** 값은 [eDiscovery cmdlet 작업](#ediscovery-cmdlet-activities) 섹션에 나열 된 작업과 관련 된 이벤트를 나타냅니다. 값이 **24** 이면 [eDiscovery 활동 검색 및 보기](#how-to-search-for-and-view-ediscovery-activities) 섹션에 나열 된 작업과 관련 된 이벤트를 나타냅니다.  <br/> |
|ResultStatus  <br/> |작업 속성에 지정 된 작업이 성공 했는지 여부를 나타냅니다.  <br/> |
|SecurityComplianceCenterEventType  <br/> |작업이 보안 & 준수 센터 이벤트 임을 나타냅니다. 이 속성의 경우 모든 eDiscovery 활동 값은 **0** 입니다.  <br/> |
|SharepointLocations  <br/> |콘텐츠 검색에 포함 되거나 eDiscovery 사례에서 보류 되는 SharePoint Online 사이트입니다.  <br/> |
|StartTime  <br/> |EDiscovery 활동이 시작 된 시간을 UTC (협정 세계시)로 된 날짜와 시간입니다.  <br/> |
|UserId  <br/> |작업 속성에 지정 된 활동을 수행한 사용자가 레코드를 기록 합니다. 시스템 계정 (예: NT 권한 \ 컴퓨터)에서 수행 하는 eDiscovery 작업에 대 한 레코드는 감사 로그에도 포함 됩니다.  <br/> |
|UserKey  <br/> |UserId 속성에서 식별 된 사용자의 대체 ID입니다. EDiscovery 작업의 경우이 속성 값은 일반적으로 UserId 속성과 동일 합니다.  <br/> |
|UserServicePlan  <br/> |조직에서 사용 하는 구독입니다. EDiscovery 작업의 경우이 속성은 일반적으로 비어 있습니다.  <br/> |
|UserType  <br/> |작업을 수행한 사용자의 유형입니다. 다음 값은 사용자 형식을 나타냅니다.  <br/> 0 일반 사용자입니다. 2 조직의 관리자 3 A Microsoft 데이터 센터 관리자 또는 데이터 센터 시스템 계정입니다. 4 시스템 계정입니다. 5 응용 프로그램 6 서비스 사용자 |
|Version  <br/> |기록 된 작업의 버전 번호 (Operation 속성으로 식별 됨)를 나타냅니다.  <br/> |
|워크로드  <br/> |활동이 발생 한 Theservice입니다. EDiscovery 활동의 경우이 값은 **SecurityComplianceCenter**입니다.  <br/> |
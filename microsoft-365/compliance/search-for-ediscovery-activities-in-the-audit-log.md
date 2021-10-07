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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: eDiscovery 권한이 할당된 사용자가 콘텐츠 검색, Core eDiscovery 및 Advanced eDiscovery 수행할 때 로깅되는 이벤트를 Microsoft 365 규정 준수 센터.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e033864b15032e66995be439e1de750da06e988b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151017"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>감사 로그에서 eDiscovery 활동 검색

콘텐츠 검색 및 eDiscovery 관련 활동(Core eDiscovery 및 Advanced eDiscovery)은 Microsoft 365 규정 준수 센터 또는 해당 PowerShell cmdlet을 실행하여 감사 로그에 기록됩니다. 이벤트는 관리자 또는 eDiscovery 관리자(또는 eDiscovery 권한이 할당된 사용자)가 다음 콘텐츠 검색 및 핵심 eDiscovery 작업을 수행할 때 Microsoft 365 규정 준수 센터.
  
- 핵심 및 핵심 사례 Advanced eDiscovery 관리

- 콘텐츠 검색 만들기, 시작 및 편집

- 검색 결과 미리 보기, 내보내기 및 삭제와 같은 검색 작업 수행

- 2016년 8월에 있는 관리자 및 검토 Advanced eDiscovery

- 콘텐츠 검색에 대한 사용 권한 필터링 구성

- eDiscovery 관리자 역할 관리
  
감사 로그, 필요한 사용 권한 및 검색 결과를 내보내는 데 대한 자세한 내용은 감사 로그의 검색을 [Microsoft 365 규정 준수 센터.](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>eDiscovery 활동을 검색하고 보는 방법

현재 감사 로그에서 eDiscovery 활동을 확인하려면 몇 가지 특정 작업을 해야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.
  
1. <https://compliance.microsoft.com>으로 이동하여 회사 또는 학교 계정을 사용하여 로그인합니다.

2. 창의 왼쪽 탐색 창에서 Microsoft 365 규정 준수 센터 **클릭합니다.**

3. 활동 **드롭다운** 목록의 **eDiscovery** 활동 또는 Advanced eDiscovery 활동에서 검색할 활동을 하나 이상 클릭합니다.

    > [!NOTE]
    > 또한 **활동 드롭다운** 목록에는 cmdlet 감사 로그의 레코드를 반환하는 **eDiscovery cmdlet** 활동이라는 활동 그룹도 포함됩니다.
  
4. 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 eDiscovery 이벤트를 표시합니다.

5. 사용자 **상자에서** 검색 결과를 표시할 사용자를 한명 이상 선택합니다. 모든 사용자에 대한 항목을 반환하기 위해 이 상자를 비워 두십시오.

6. **검색** 을 클릭하여 검색 조건을 사용한 검색을 실행합니다. 

7. 검색 결과가 표시되면 결과 필터링을 클릭하여 결과 활동 레코드를 필터링하거나 정렬할 수 있습니다.  안타깝게도 필터링을 사용하여 특정 활동을 명시적으로 제외할 수 없습니다. 

8. 활동에 대한 세부 정보를 보려면 검색 결과 목록에서 활동 레코드를 클릭합니다. 

    이벤트 **레코드의** 자세한 속성이 포함된 세부 정보 플라이아웃 페이지가 표시됩니다. 추가 세부 정보를 표시하려면 추가 정보를 **클릭합니다.** 이러한 속성에 대한 설명은 [eDiscovery](#detailed-properties-for-ediscovery-activities) 활동의 자세한 속성 섹션을 참조하세요.

9. 원하는 경우 감사 로그 검색 결과를 CSV 파일로 내보냈다가 Power Query Excel 사용하여 이러한 레코드의 형식을 지정하고 필터링할 수 있습니다. 자세한 내용은 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md)를 참조하세요.

## <a name="ediscovery-activities"></a>eDiscovery 활동

다음 표에서는 관리자 또는 eDiscovery 관리자가 관리자 또는 eDiscovery 관리자를 사용하여 eDiscovery 관련 활동을 수행할 때 기록되는 콘텐츠 검색 및 핵심 eDiscovery 활동에 대해 Microsoft 365 규정 준수 센터. 이 목록에서 Advanced eDiscovery 검색할 때 일부 활동이 반환될 수 있습니다.
  
> [!NOTE]
> 이 섹션에 설명된 eDiscovery 활동은 다음 섹션에 설명된 eDiscovery cmdlet 활동과 유사한 정보를 제공합니다. 이 섹션에 설명된 eDiscovery 활동은 30분 이내에 감사 로그 검색 결과에 표시될 것이기 때문에 사용하는 것이 좋습니다. eDiscovery cmdlet 활동이 감사 로그 검색 결과에 표시될 경우 최대 24시간이 걸릴 수 있습니다.
  
|**친숙한 이름**|**작업**|**해당 cmdlet**|**설명**|
|:-----|:-----|:-----|:-----|
|eDiscovery 사례에 구성원 추가  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |사용자가 eDiscovery 사례의 구성원으로 추가되었습니다. 사례의 구성원인 사용자는 필요한 사용 권한이 할당되어 있는지 여부에 따라 다양한 사례 관련 작업을 수행할 수 있습니다.  <br/> |
|변경된 콘텐츠 검색  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |기존 콘텐츠 검색이 변경된 경우 변경 내용에는 콘텐츠 위치 추가 또는 제거 또는 검색 쿼리 편집이 포함됩니다.  <br/> |
|eDiscovery 관리자 구성원 자격 변경  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |조직의 eDiscovery 관리자 목록이 변경된 경우 이 활동은 eDiscovery 관리자 목록이 새 사용자 그룹으로 대체될 때 기록됩니다. 단일 사용자를 추가하거나 제거하면 CaseAdminAdded 작업이 기록됩니다.  <br/> |
|eDiscovery 사례 변경  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |eDiscovery 사례가 변경된 경우 변경 내용에는 열린 사례를 닫거나 닫힌 사례를 다시 여는 것이 포함됩니다.  <br/> |
|eDiscovery 사례 멤버 자격 변경  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |eDiscovery 사례의 멤버 자격 목록이 변경된 경우 이 활동은 모든 구성원이 새 사용자 그룹으로 대체될 때 기록됩니다. 구성원을 하나 추가하거나 제거하면 CaseMemberAdded 또는 CaseMemberRemoved 작업이 기록됩니다.  <br/> |
|검색 권한 필터 변경  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |검색 권한 필터가 변경된 경우  <br/> |
|eDiscovery 사례 보류에 대한 검색 쿼리가 변경되었습니다.  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |eDiscovery 사례와 연결된 쿼리 기반 보류가 변경되었습니다. 가능한 변경 내용에는 쿼리 기반 보류에 대한 쿼리 또는 날짜 범위 편집이 포함됩니다.  <br/> |
|다운로드한 콘텐츠 검색 미리 보기 항목  <br/> |PreviewItemDownloaded  <br/> |해당 없음  <br/> |사용자가 검색 결과를 미리 볼 때 원래 항목  다운로드 링크를 클릭하여 로컬 컴퓨터에 항목을 다운로드했습니다.  <br/> |
|나열된 콘텐츠 검색 미리 보기 항목  <br/> |PreviewItemListed  <br/> |해당 없음  <br/> |사용자가 검색  결과 미리 보기를 클릭하여 검색 결과에서 최대 1,000개 항목을 나열하는 미리 보기 검색 결과 페이지를 표시합니다.  <br/> |
|콘텐츠 검색 미리 보기 항목 보기  <br/> |PreviewItemRendered  <br/> |해당 없음  <br/> |eDiscovery 관리자는 검색 결과를 미리 볼 때 해당 항목을 클릭하여 항목을 보게 됩니다.  <br/> |
|콘텐츠 검색 생성  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |새 콘텐츠 검색이 만들어졌습니다.  <br/> |
|eDiscovery 관리자 생성  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |사용자가 조직에서 eDiscovery 관리자로 추가되었습니다.  <br/> |
|eDiscovery 사례 생성  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |eDiscovery 사례가 생성되었습니다. 사례를 만들 때 이름만 지정하면 됩니다. 구성원 추가, 보류 만들기, 사례와 연결된 콘텐츠 검색 만들기 등의 기타 사례 관련 작업을 수행하면 추가 이벤트가 기록됩니다.  <br/> |
|검색 권한 필터 생성  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |검색 권한 필터가 만들어졌습니다.  <br/> |
|eDiscovery 사례 보류에 대한 검색 쿼리 생성  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |eDiscovery 사례와 연결된 쿼리 기반 보류가 만들어졌습니다.  <br/> |
|삭제된 콘텐츠 검색  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |기존 콘텐츠 검색이 삭제되었습니다.  <br/> |
|eDiscovery 관리자 삭제  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |eDiscovery 관리자가 조직에서 삭제되었습니다.  <br/> |
|eDiscovery 사례 삭제  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |eDiscovery 사례가 삭제되었습니다. 사례와 연결된 모든 보류를 제거해야 사례를 삭제할 수 있습니다.  <br/> |
|삭제된 검색 권한 필터  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |검색 권한 필터가 삭제되었습니다.  <br/> |
|eDiscovery 사례 보류에 대한 삭제된 검색 쿼리  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |eDiscovery 사례와 연결된 쿼리 기반 보류가 삭제되었습니다. 보류에서 쿼리를 제거하면 보류가 삭제되는 경우가 종종 있습니다. 보류 또는 보류 쿼리가 삭제되면 보류된 콘텐츠 위치가 릴리스됩니다.  <br/> |
|콘텐츠 검색의 다운로드된 내보내기  <br/> |SearchExportDownloaded  <br/> |해당 없음  <br/> |사용자가 로컬 컴퓨터에 콘텐츠 검색 결과를 다운로드했습니다. 검색 **결과를 다운로드하려면** 먼저 콘텐츠 검색 활동의 시작된 내보내기 작업을 시작해야 합니다.  <br/> |
|콘텐츠 검색의 미리 보기 결과  <br/> |SearchPreviewed  <br/> |해당 없음  <br/> |사용자가 콘텐츠 검색 결과를 미리 보게 됩니다.  <br/> |
|콘텐츠 검색의 제거된 결과  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |사용자가 **New-ComplianceSearchAction -Purge** 명령을 실행하여 콘텐츠 검색 결과를 제거했습니다.  <br/> |
|콘텐츠 검색 분석 제거됨  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |콘텐츠 검색 준비 작업(검색 결과를 Advanced eDiscovery)이 삭제되었습니다. 준비 작업이 2주 미만이면 검색을 위해 준비된 Advanced eDiscovery 저장 Microsoft Azure 삭제됩니다. 준비 작업이 2주보다 오래된 경우 이 이벤트는 해당 준비 작업만 삭제된 것을 나타냅니다.  <br/> |
|콘텐츠 검색 내보내기 제거됨  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |콘텐츠 검색 내보내기 작업이 삭제되었습니다. 내보내기 작업이 2주 미만이면 저장소 영역에 업로드된 Microsoft Azure 삭제되었습니다. 내보내기 작업이 2주보다 오래된 경우 이 이벤트는 해당 내보내기 작업만 삭제된 것을 나타냅니다.  <br/> |
|eDiscovery 사례에서 구성원 제거됨  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |사용자가 eDiscovery 사례의 구성원으로 제거되었습니다.  <br/> |
|콘텐츠 검색의 미리 보기 결과 제거됨  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |콘텐츠 검색 미리 보기 작업이 삭제되었습니다.  <br/> |
|콘텐츠 검색에 수행된 삭제 작업 제거  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |콘텐츠 검색 삭제 작업이 삭제되었습니다.  <br/> |
|검색 보고서 제거됨  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |콘텐츠 검색 내보내기 보고서 작업이 삭제되었습니다.  <br/> |
|콘텐츠 검색 분석 시작  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |콘텐츠 검색 결과는 콘텐츠 검색에서 분석할 수 Advanced eDiscovery.  <br/> |
|시작된 콘텐츠 검색  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |콘텐츠 검색이 시작된 경우 검색 창을 사용하여 콘텐츠 검색을 만들거나 변경하면 Microsoft 365 규정 준수 센터 검색이 자동으로 시작됩니다.<br/> |
|콘텐츠 검색 내보내기 시작  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |사용자가 콘텐츠 검색 결과를 내보낼 수 있습니다.  <br/> |
|시작된 내보내기 보고서  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |사용자가 콘텐츠 검색 보고서를 내보낼 때  <br/> |
|중지된 콘텐츠 검색  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |사용자가 콘텐츠 검색을 중지한 경우  <br/> |
|(없음)|CaseViewed|Get-ComplianceCase|사용자가 준수 센터에서 핵심 eDiscovery 사례를 보게 됩니다. 이 이벤트에 대한 감사 레코드에는 본 사례의 이름이 포함됩니다. |
|(없음)|SearchViewed|Get-ComplianceSearch|사용자가 Core eDiscovery 사례의 검색 탭에서  검색에 액세스하거나 콘텐츠 검색 페이지에서 액세스하여 준수 센터에서 콘텐츠 검색을 **보게** 됩니다. 이 이벤트에 대한 감사 레코드에는 본 검색의 ID가 포함됩니다.|
|(없음)|ViewedSearchExported|Get-ComplianceSearchAction -Export|사용자가 콘텐츠 검색 페이지의 내보내기 탭에서 내보내기 탭에  액세스하여 준수 센터에서 콘텐츠 검색 내보내기를 **보게** 됩니다. 이 활동은 사용자가 Core eDiscovery 사례와 연결된 내보내기 보기 시에도 기록됩니다.|
|(없음)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|사용자가 준수 센터에서 콘텐츠 검색 결과를 미리 보게 됩니다. 이 활동은 사용자가 Core eDiscovery 사례와 연결된 검색 결과를 미리 볼 때도 기록됩니다.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>고급 eDiscovery 활동

다음 표에서는 감사 Advanced eDiscovery 기록된 작업의 설명을 제공합니다. 이러한 활동은 특정 사례에서 활동의 진행률을 추적하는 데 Advanced eDiscovery 있습니다.

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

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery cmdlet 활동

다음 표에는 관리자 또는 사용자가 준수 센터를 사용하여 또는 보안 및 준수 센터 PowerShell에서 해당 cmdlet을 실행하여 eDiscovery 관련 활동을 수행할 때 기록되는 cmdlet 감사 로그 레코드가 & 나열되어 있습니다. 감사 로그 레코드의 세부 정보는 이 표에 나열된 cmdlet 활동 및 이전 섹션에서 설명한 eDiscovery 활동에 따라 다릅니다.
  
앞서 언급했듯이 eDiscovery cmdlet 활동이 감사 로그 검색 결과에 표시될 경우 최대 24시간이 걸릴 수 있습니다.
  
> [!TIP]
> 다음 표의 작업  열에 있는 cmdlet은 TechNet의 해당 cmdlet 도움말 항목에 연결됩니다. 각 cmdlet에 대해 사용 가능한 매개 변수에 대한 설명은 cmdlet 도움말 항목으로 이동하십시오. cmdlet에 사용된 매개 변수 및 매개 변수 값은 기록되는 각 eDiscovery cmdlet 활동에 대한 감사 로그 항목에 포함됩니다. 
  
|**친숙한 이름**|**Operation(cmdlet)**|**설명**|
|:-----|:-----|:-----|
|eDiscovery 사례에서 보류 생성  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |eDiscovery 사례에 대해 보류가 만들어졌습니다. 콘텐츠 원본을 지정하거나 지정하지 않고 보류를 만들 수 있습니다. 콘텐츠 원본이 지정된 경우 감사 로그 항목에서 식별됩니다.  <br/> |
|eDiscovery 사례에서 보류 삭제  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |eDiscovery 사례와 연결된 보류가 삭제되었습니다. 보류를 삭제하는 경우 모든 콘텐츠 위치가 보류에서 해제됩니다. 또한 보류를 삭제하면 보류와 연결된 케이스 보류 규칙이 삭제됩니다(아래 **Remove-CaseHoldRule** 참조).  <br/> |
|eDiscovery 사례에서 보류 변경  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |eDiscovery와 연결된 보류가 변경된 경우 콘텐츠 위치를 추가 또는 제거하거나 보류를 해제(해제)하는 등 가능한 변경이 가능합니다.  <br/> |
|eDiscovery 사례 보류에 대한 검색 쿼리 생성  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |eDiscovery 사례와 연결된 쿼리 기반 보류가 만들어졌습니다.  <br/> |
|eDiscovery 사례 보류에 대한 삭제된 검색 쿼리  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |eDiscovery 사례와 연결된 쿼리 기반 보류가 삭제되었습니다. 보류에서 쿼리를 제거하면 보류가 삭제되는 경우가 종종 있습니다. 보류 또는 보류 쿼리가 삭제되면 보류된 콘텐츠 위치가 릴리스됩니다.  <br/> |
|eDiscovery 사례 보류에 대한 검색 쿼리가 변경되었습니다.  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |eDiscovery 사례와 연결된 쿼리 기반 보류가 변경되었습니다. 가능한 변경 내용에는 쿼리 기반 보류에 대한 쿼리 또는 날짜 범위 편집이 포함됩니다.  <br/> |
|eDiscovery 사례 생성  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |eDiscovery 사례가 생성되었습니다. 사례를 만들 때 이름만 지정하면 됩니다. 구성원 추가, 보류 만들기, 사례와 연결된 콘텐츠 검색 만들기 등의 기타 사례 관련 작업을 수행하면 추가 이벤트가 기록됩니다.  <br/> |
|eDiscovery 사례 삭제  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |eDiscovery 사례가 삭제되었습니다. 사례와 연결된 모든 보류를 제거해야 사례를 삭제할 수 있습니다.  <br/> |
|eDiscovery 사례 변경  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |eDiscovery 사례가 변경된 경우 변경 내용에는 열린 사례를 닫거나 닫힌 사례를 다시 여는 것이 포함됩니다.  <br/> |
|eDiscovery 사례에 구성원 추가  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |사용자가 eDiscovery 사례의 구성원으로 추가되었습니다. 사례의 구성원인 사용자는 필요한 사용 권한이 할당되어 있는지 여부에 따라 다양한 사례 관련 작업을 수행할 수 있습니다.  <br/> |
|eDiscovery 사례에서 구성원 제거됨  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |사용자가 eDiscovery 사례의 구성원으로 제거되었습니다.  <br/> |
|eDiscovery 사례 멤버 자격 변경  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |eDiscovery 사례의 멤버 자격 목록이 변경된 경우 이 활동은 모든 구성원이 새 사용자 그룹으로 대체될 때 기록됩니다. 구성원을 하나 추가하거나 제거하면 **Add-ComplianceCaseMember** 또는 **Remove-ComplianceCaseMember** 작업이 기록됩니다.  <br/> |
|콘텐츠 검색 생성  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |새 콘텐츠 검색이 만들어졌습니다.  <br/> |
|삭제된 콘텐츠 검색  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |기존 콘텐츠 검색이 삭제되었습니다.  <br/> |
|변경된 콘텐츠 검색  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |기존 콘텐츠 검색이 변경된 경우 변경 내용에는 검색되는 콘텐츠 위치 추가 또는 제거 및 검색 쿼리 편집이 포함됩니다.  <br/> |
|시작된 콘텐츠 검색  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |콘텐츠 검색이 시작된 경우 준수 센터 GUI를 사용하여 콘텐츠 검색을 만들거나 변경하면 검색이 자동으로 시작됩니다. **New-ComplianceSearch** 또는 **Set-ComplianceSearch** cmdlet을 사용하여 검색을 만들거나 변경하는 경우 **Start-ComplianceSearch** cmdlet을 실행하여 검색을 시작해야 합니다.  <br/> |
|중지된 콘텐츠 검색  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |실행 중인 콘텐츠 검색이 중지되었습니다.  <br/> |
|콘텐츠 검색 작업 생성  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |콘텐츠 검색 작업이 만들어졌습니다. 콘텐츠 검색 작업에는 검색 결과 미리 보기, 검색 결과 내보내기, Advanced eDiscovery 분석에 대한 검색 결과 준비, 콘텐츠 검색의 검색 조건과 일치하는 항목을 영구적으로 삭제하는 작업이 포함됩니다.  <br/> |
|삭제된 콘텐츠 검색 작업  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |콘텐츠 검색 작업이 삭제되었습니다.  <br/> |
|검색 권한 필터 생성  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |검색 권한 필터가 만들어졌습니다.  <br/> |
|삭제된 검색 권한 필터  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |검색 권한 필터가 삭제되었습니다.  <br/> |
|검색 권한 필터 변경  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |검색 권한 필터가 변경된 경우  <br/> |
|eDiscovery 관리자 생성  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |사용자가 조직에서 eDiscovery 관리자로 추가되었습니다.  <br/> |
|eDiscovery 관리자 삭제  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |eDiscovery 관리자가 조직에서 삭제되었습니다.  <br/> |
|eDiscovery 관리자 구성원 자격 변경  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |조직의 eDiscovery 관리자 목록이 변경된 경우 이 활동은 eDiscovery 관리자 목록이 새 사용자 그룹으로 대체될 때 기록됩니다. 단일 사용자를 추가하거나 제거하면 **Add-eDiscoveryCaseAdmin** 또는 **Remove-eDiscoveryCaseAdmin** 작업이 기록됩니다.  <br/> |
|(없음)|[Get-ComplianceCase](/powershell/module/exchange/get-compliancecase) <br/>|이 활동은 사용자가 핵심 eDiscovery 또는 사례의 목록을 볼 Advanced eDiscovery 기록됩니다. 이 활동은 사용자가 Core eDiscovery에서 특정 사례를 볼 때도 기록됩니다. 사용자가 특정 사례를 볼 때 감사 레코드에는 확인된 사례의 ID가 포함됩니다. 사용자가 사례 목록만 본 경우 감사 레코드에는 사례 ID가 포함되지 않습니다.|
|(없음)|[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)|이 활동은 사용자가 Core eDiscovery 사례와 연결된 콘텐츠 검색 또는 검색 목록을 볼 때 기록됩니다. 이 활동은 사용자가 특정 콘텐츠 검색을 보거나 Core eDiscovery 사례와 연결된 특정 검색을 볼 때도 기록됩니다. 사용자가 특정 검색을 볼 때 감사 레코드에는 본 검색의 ID가 포함됩니다. 사용자가 검색 목록만 본 경우 감사 레코드에 검색 ID가 포함되지 않습니다.
|(없음)|[Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)|이 활동은 사용자가 Core eDiscovery 사례와 관련된 준수 검색 작업(예: 내보내기, 미리 보기 또는 제거) 또는 작업 목록을 볼 때 기록됩니다. 이 활동은 사용자가 특정 준수 검색 작업(예: 내보내기)을 보거나 Core eDiscovery 사례와 관련된 특정 작업을 볼 때도 기록됩니다. 사용자가 검색 작업을 볼 때 감사 레코드에는 본 검색 작업의 ID가 포함됩니다. 사용자가 작업 목록만 본 경우 감사 레코드에 작업 ID가 포함되지 않습니다.|
||||

## <a name="detailed-properties-for-ediscovery-activities"></a>eDiscovery 활동에 대한 자세한 속성

다음 표에는 검색 결과에 나열된 eDiscovery 활동의 플라이아웃 페이지에 포함된 속성에 대한 설명이 나와 있습니다. 이러한 속성은 감사 로그 검색 결과를 내보낼 때도 CSV 파일에 포함됩니다. eDiscovery 활동에 대한 감사 로그 레코드는 아래에 나열된 모든 세부 속성을 포함하지 않습니다.
  
> [!TIP]
> 검색 결과를 내보낼 때 CSV 파일에는 다중 값 속성의 다음 표에 설명된 자세한 속성이 포함된 **AudtiData** 열이 포함되어 있습니다. 이 열의 파워 쿼리 기능을 사용하여 Excel 열을 여러 열로 분할하여 각 속성에 자체 열을 사용할 수 있습니다. 이렇게 하면 이러한 속성 중 하나 이상을 정렬하고 필터링할 수 있습니다. 자세한 내용은 감사 로그 검색의 "파일로 검색 결과 내보내기" [섹션을 참조하세요.](search-the-audit-log-in-security-and-compliance.md#step-3-export-the-search-results-to-a-file) 
  
|**속성**|**설명**|
|:-----|:-----|
|사례  <br/> |작성, 변경 또는 삭제된 eDiscovery 사례의 ID(GUID)입니다.  <br/> |
|ClientApplication  <br/> |eDiscovery cmdlet 활동은 이 속성에 **대한 EMC** 값을 가집니다. 이는 준수 센터 GUI를 사용하여 또는 PowerShell에서 cmdlet을 실행하여 수행된 활동을 나타냅니다.  <br/> |
|ClientIP  <br/> |활동이 기록될 때 사용된 장치의 IP 주소입니다. IP 주소는 IPv4 또는 IPv6 주소 형식으로 표시됩니다.  <br/> |
|ClientRequestId  <br/> | eDiscovery 작업의 경우 일반적으로 이 속성은 비어 있습니다.  <br/> |
|CmdletVersion  <br/> |조직에서 실행되는 준수 센터 버전의 빌드 번호입니다.  <br/> |
|CreationTime  <br/> |eDiscovery 활동이 완료된 UTC(협정 세계시)의 날짜 및 시간입니다.  <br/> |
|EffectiveOrganization  <br/> |Microsoft 365 조직의 이름입니다.  <br/> |
|ExchangeLocations  <br/> |콘텐츠 Exchange Online eDiscovery 사례에서 보류된 사서함을 검색합니다.  <br/> |
|제외  <br/> |eDiscovery 사례에서 콘텐츠 검색 또는 보류에서 제외되는 사서함 또는 사이트 위치입니다.  <br/> |
|ExtendedProperties  <br/> |활동이 수행될 때 사용된 개체 GUID 및 해당 cmdlet 및 cmdlet 매개 변수와 같은 콘텐츠 검색, 콘텐츠 검색 작업 또는 eDiscovery 사례에 보유되는 추가 속성  <br/> |
|Id  <br/> |보고서 항목의 ID입니다. ID는 감사 로그 항목을 고유하게 식별합니다.  <br/> |
|NonPIIParameters  <br/> |Operation 속성에 식별된 cmdlet과 함께 사용된 매개 변수 목록(값 없이)입니다. 이 속성에 나열된 매개 변수는 Parameters 속성에 나열된 매개 변수와 같습니다.  <br/> |
|ObjectId  <br/> |Operation 속성에 나열된 활동에 의해 생성, 액세스, 변경 또는 삭제된 개체의 GUID 또는 이름(예: 콘텐츠 검색 또는 Core eDiscovery 사례)입니다. 이 개체는 감사 로그 검색 결과의 항목 열에서도 식별됩니다.  <br/> |
|ObjectType  <br/> |사용자가 만들거나 삭제하거나 수정한 eDiscovery 개체의 형식입니다. 예를 들어 콘텐츠 검색 작업(미리 보기, 내보내기 또는 제거), eDiscovery 사례 또는 콘텐츠 검색을 예로 들 수 있습니다.  <br/> |
|작업  <br/> |수행된 eDiscovery 활동에 해당하는 작업의 이름입니다.  <br/> |
|OrganizationId  <br/> |조직에 대한 Microsoft 365 GUID입니다.  <br/> |
|매개 변수  <br/> |해당 cmdlet과 함께 사용된 매개 변수의 이름 및 값입니다.  <br/> |
|PublicFolderLocations  <br/> |콘텐츠 검색에 Exchange Online eDiscovery 사례에서 보류된 공용 폴더 위치입니다.  <br/> |
|쿼리  <br/> |콘텐츠 검색 또는 쿼리 기반 보류와 같은 활동과 연결된 검색 쿼리입니다.  <br/> |
|RecordType  <br/> |레코드가 나타내는 작업의 유형입니다. 값 **18은** [eDiscovery cmdlet](#ediscovery-cmdlet-activities) 활동 섹션에 나열된 활동과 관련된 이벤트를 나타냅니다. 값 **24는** [eDiscovery](#how-to-search-for-and-view-ediscovery-activities) 활동을 검색하고 보는 방법 섹션에 나열된 활동과 관련된 이벤트를 나타냅니다.  <br/> |
|ResultStatus  <br/> |Operation 속성에 지정된 작업이 성공적이지 여부를 나타냅니다.  <br/> |
|SecurityComplianceCenterEventType  <br/> |활동이 준수 센터 이벤트인 경우를 나타냅니다. 모든 eDiscovery 활동의 값은 이 속성에 **대해 0입니다.**  <br/> |
|SharepointLocations  <br/> |콘텐츠 SharePoint 포함되거나 eDiscovery 사례에서 보류된 온라인 사이트입니다.  <br/> |
|StartTime  <br/> |eDiscovery 활동이 시작된 UTC(협정 세계시)의 날짜 및 시간입니다.  <br/> |
|UserId  <br/> |Operation 속성에 지정된 활동을 수행한 사용자로 인해 레코드가 기록됩니다. 시스템 계정(예: NT AUTHORITY\SYSTEM)에서 수행되는 eDiscovery 활동에 대한 레코드도 감사 로그에 포함됩니다.  <br/> |
|UserKey  <br/> |UserId 속성에 식별된 사용자의 대체 ID입니다. eDiscovery 작업의 경우 이 속성의 값은 일반적으로 UserId 속성과 동일합니다.  <br/> |
|UserServicePlan  <br/> |조직에서 사용하는 구독입니다. eDiscovery 작업의 경우 일반적으로 이 속성은 비어 있습니다.  <br/> |
|UserType  <br/> |작업을 수행한 사용자 유형입니다. 다음 값은 사용자 유형을 나타냅니다.  <br/> 0 일반 사용자입니다. 2 조직의 관리자입니다. 3 Microsoft 데이터 센터 관리자 또는 데이터 센터 시스템 계정입니다. 4 시스템 계정입니다. 5 응용 프로그램. 6 서비스 주체입니다. |
|버전  <br/> |기록된 활동의 버전 번호(Operation 속성으로 식별)를 나타냅니다.  <br/> |
|워크로드  <br/> |활동이 발생한 서비스입니다. eDiscovery 활동의 경우 값은 **SecurityComplianceCenter입니다.**  <br/> |

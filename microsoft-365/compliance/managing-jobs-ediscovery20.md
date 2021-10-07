---
title: 작업 관리 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery 작업을 사용하면 다양한 작업 수행과 관련된 장기 실행 프로세스의 상태를 추적할 Advanced eDiscovery 있습니다.
ms.openlocfilehash: d5b2facdead3be1369cd261392117fc33fa1a4fb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192202"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>작업 관리 Advanced eDiscovery

다음은 여러 사례의 작업 탭에서 추적되는 작업(일반적으로 장기 실행 프로세스)의 Advanced eDiscovery.  이러한 작업은 사례를 사용하고 관리할 때 사용자 작업에 의해 트리거됩니다.

| 작업 유형           | 설명     |
| :----------------- | :----------     |
|검토 집합에 데이터 추가 | 사용자가 검토 집합에 컬렉션을 추가합니다. 이 작업은 다음 두 개의 하위 작업으로 구성됩니다. </br>• **Export** - 컬렉션의 항목 목록이 생성됩니다. </br>•  수집 & 인덱싱 - 검색 쿼리와 일치하는 컬렉션의 항목이 Azure Storage 위치(수집이라는 프로세스)에 복사된 다음 Azure Storage 위치의 항목이 다시 인덱싱됩니다. 이 새 인덱스는 데이터 집합의 항목을 쿼리하고 분석할 때 사용됩니다. </br></br>자세한 내용은 [리뷰 집합에 검색 결과 추가를 참조하세요.](add-data-to-review-set.md) |
|다른 검토 집합에 데이터 추가 | 사용자는 동일한 경우 한 검토 집합의 문서를 다른 검토 집합에 추가합니다. 자세한 내용은 다른 검토 집합의 검토 집합에 [데이터 추가를 참조하세요.](add-data-to-review-set-from-another-review-set.md)|
|검토 집합에 Microsoft 365 비영구 데이터 추가 | 사용자가 검토 집합에 Microsoft 365 데이터를 업로드합니다. 이 프로세스 중에도 데이터가 인덱싱됩니다. 예를 들어, 사내 파일 서버 또는 클라이언트 컴퓨터의 파일이 검토 집합에 업로드됩니다. 자세한 내용은 검토 집합에 비영구 Microsoft 365 [로드를 참조하세요.](load-non-office-365-data-into-a-review-set.md)| 
|검토 집합에 수정된 데이터 추가 | 처리 오류가 있는 데이터는 수정되어 검토 집합으로 다시 로드됩니다. 자세한 내용은 다음을 참조하세요.</br>• [데이터를 처리하는 경우 오류 수정](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [단일 항목 오류 수정](single-item-error-remediation.md)| 
|부하 집합 비교 | 사용자는 검토 집합에서 서로 다른 부하 집합 간의 차이를 검토합니다. 로드 집합은 검토 집합에 데이터를 추가하는 인스턴스입니다. 예를 들어 동일한 검토 집합에 서로 다른 두 검색의 결과를 추가하는 경우 각 검색은 부하 집합을 나타내게 됩니다. |
|대화 재구성|사용자가 검색 결과를 대화 검토 집합에 추가하면 사용자와 같은 서비스에서 인스턴트 메시지 대화(스레드 Microsoft Teams)가 PDF 파일로 재구성됩니다. 사용자가 검토 집합에서 대화 >  만들기 작업을 클릭하면 이 작업이 트리거됩니다. 자세한 내용은 에서 [대화 검토를 Advanced eDiscovery.](conversation-review-sets.md)
|편집된 문서를 PDF로 변환|사용자가 검토 집합의 문서에 주석을 추가하고 문서의 일부를 편집한 후 편집된 문서를 PDF 파일로 변환하도록 선택할 수 있습니다. 이렇게 하면 프레젠테이션을 위해 문서를 내보낼 때 변경된 부분이 표시되지 않습니다. 자세한 내용은 검토 집합에서 [문서 보기를 참조하세요.](annotating-and-redacting-documents.md) |
|검색 결과 예상 | 사용자가 초안 컬렉션을 만들고 실행하거나 다시 실행한 후 검색 도구는 검색 쿼리와 일치하는 항목의 인덱스를 검색하고 검색을 통해 모든 항목의 총 크기와 검색되는 데이터 원본 수를 포함하는 예상 정보를 준비합니다.  자세한 내용은 [사례에 대한 데이터 수집을 참조하세요.](collecting-data-for-ediscovery.md) | 
|내보내기용 데이터 준비 | 사용자가 검토 집합에서 문서를 내보낼 수 있습니다. 내보내기 프로세스가 완료되면 내보낼 데이터를 로컬 컴퓨터로 다운로드할 수 있습니다. 자세한 내용은 사례 데이터 [내보내기 를 참조하세요.](exporting-data-ediscover20.md) | 
|오류 해결 준비 |사용자가 파일을 선택하고 사례의 처리 탭에 있는 오류 보기에서  새 오류 수정을 만드는 경우 프로세스의 첫 번째 단계는 처리 오류가 있는 파일을 Microsoft 클라우드의 Azure Storage 위치로 업로드하는 것입니다. 이 작업은 업로드 프로세스의 진행률을 추적합니다. 오류 수정 워크플로에 대한 자세한 내용은 데이터 처리 시 오류 [수정을 참조하세요.](error-remediation-when-processing-data-in-advanced-ediscovery.md) | 
|검색 미리 보기 준비 | 사용자가 새 초안 컬렉션을 만들고 실행하거나 기존 초안 컬렉션을 다시 실행하면 검색 도구에서 미리 볼 수 있는 항목의 예제 하위 집합(검색 쿼리와 일치하는 항목)을 준비합니다. 검색 결과를 미리 보고 검색의 효율성을 결정하는 데 도움이 됩니다.  자세한 내용은 [사례에 대한 데이터 수집을 참조하세요.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|보호자 데이터 다시 인덱싱 | 사례에 보호자 를 추가하면, 보호자 선택한 데이터 원본의 부분적으로 인덱싱된 모든 항목이 고급 인덱싱 이라는 프로세스에 의해 다시 *인덱싱됩니다.* 이 작업은 사례의 처리  탭에서 인덱스  업데이트를 클릭할 때와 속성 플라이아웃 페이지에서 특정 정보주에 대한 인덱스를 업데이트할 때도 트리거됩니다. 자세한 내용은 보호자 데이터의 고급 인덱싱을 [참조하세요.](indexing-custodian-data.md)
|분석 실행 | 사용자는 중복에 가까운 검색, 전자 메일 스레딩 분석 및 테마 분석과 같은 Advanced eDiscovery 분석 도구를 실행하여 검토 집합의 데이터를 분석합니다. 자세한 내용은 리뷰 [집합의 데이터 분석 을 참조하세요.](analyzing-data-in-review-set.md) | 
|문서 태그 지정 | 사용자가 검토 집합의 문서를 검토할 때 태그  지정 패널에서 태그 지정 작업 시작을 클릭하면 이 작업이 트리거됩니다.  사용자는 검토 집합에서 문서에 태그를 지정한 다음 문서 보기 패널에서 문서를 대량으로 선택한 후에 이 작업을 시작할 수 있습니다. 자세한 내용은 검토 [집합의 문서 태그 지정을 참조하세요.](tagging-documents.md) | 
|||

## <a name="job-status"></a>작업 상태

다음 표에서는 작업의 다양한 상태 설명을 제공합니다.

| 상태           | 설명     |
| :----------------- | :----------     |
| 제출 | 새 작업이 만들어졌습니다.  작업이 제출된 날짜 및 시간은 작업 탭의 **만든** **열에** 표시됩니다. |
| 제출 실패 | 작업 제출이 실패했습니다.  작업을 트리거한 작업을 다시 실행해야 합니다. |
| 진행 중 | 작업이 진행 중이면 작업 탭에서 작업 진행률을 모니터링할 **수** 있습니다. |
| 성공 | 작업이 완료되었습니다. 작업이 완료된 날짜와 시간이 작업 탭의 **완료된** **열에** 표시됩니다. |
| 부분적으로 성공 | 작업이 성공했습니다. 이 상태는 일반적으로 일부 보호자 데이터 원본에서 부분적으로 인덱싱된 데이터(인덱싱되지 않은 데이터라고도 하는 데이터)를 찾지 못하면 반환됩니다.   |
| 실패 | 작업이 실패했습니다.  작업을 트리거한 작업을 다시 실행해야 합니다. 작업이 다시 실패하면 Microsoft 지원에 문의하여 작업의 지원 정보를 제공하는 것이 좋습니다. |
|||

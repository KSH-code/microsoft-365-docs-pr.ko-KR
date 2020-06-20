---
title: Microsoft 365에서 법적 조사 관리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: 조직의 법적 조사를 관리 하려면 Office 365의 보안 & 준수 센터에서 eDiscovery 사례를 사용 합니다.
ms.openlocfilehash: 0e39c2cfb865e6cf649bf1ff7702d97bd29352b9
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815505"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Microsoft 365에서 법적 조사 관리

조직에는 조직의 특정 임원 또는 다른 직원과 관련 된 법적 사례에 대응 해야 하는 여러 가지 이유가 있습니다. 이 작업을 수행 하는 동안에는 다른 조사 관련 정보를 전자 메일, 문서, 인스턴트 메시징 대화 및 기타 콘텐츠 위치에 빠르게 찾고 보존 하는 작업이 진행 될 수 있습니다. 보안 및 준수 센터에서 eDiscovery 사례 도구를 사용 하 여 이와 유사한 여러 가지 비슷한 작업을 수행할 수 있습니다.
  
**Microsoft에서 eDiscovery 조사를 관리 하는 방법을 알고 싶으십니까?** 이 문서에서는 내부 eDiscovery 워크플로를 관리 하기 위해 동일한 검색 및 조사 도구를 사용 하는 방법에 대해 설명 하는 [기술](https://go.microsoft.com/fwlink/?linkid=852161) 백서를 다운로드할 수 있습니다.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>EDiscovery 사례를 사용 하 여 법적 조사 관리

eDiscovery 사례를 사용 하면 조직에서 eDiscovery 사례를 만들고, 액세스 하 고, 관리할 수 있는 사용자를 제어할 수도 있습니다. 사례를 사용 하 여 구성원을 추가 하 고 수행할 수 있는 작업 유형을 제어 하 고, 법적 사례와 관련 된 콘텐츠 위치를 유지 하 고, 콘텐츠 검색 도구를 사용 하 여 해당 사례에 응답할 수 있는 콘텐츠에 대해 보류 중인 위치를 검색 합니다. 그런 다음 외부 검토자의 추가 조사를 위해 해당 결과를 내보내고 다운로드할 수도 있습니다.
  
- 조직이 수행 해야 하는 모든 법률 조사에 대해 eDiscovery 사례를 만들고 사용 하 여 [ediscovery 워크플로를 관리 합니다](ediscovery-cases.md) . 
    
- 조직에서 eDiscovery 사례를 만들고 관리할 수 있는 사용자를 제어 하기 위해 [ediscovery 권한 할당](assign-ediscovery-permissions.md) 
    
- EDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치를 제어 하는 [준수 경계를 설정](tagging-and-assessment-in-advanced-ediscovery.md) 합니다. 
    
- 조직의 [콘텐츠 검색](search-for-content.md) 
    
### <a name="use-scripts-for-advanced-scenarios"></a>고급 시나리오에 스크립트 사용

콘텐츠 검색 시나리오에 대해 스크립트를 나열 하는 이전 섹션에서와 마찬가지로, eDiscovery 사례를 관리 하는 데 도움이 되는 몇 가지 보안 & 준수 센터 PowerShell 스크립트도 만들었습니다.
  
- 조직의 eDiscovery 사례와 관련 된 모든 보류에 대 한 정보가 포함 된 [eDiscovery 보류 보고서를 만듭니다](create-a-report-on-holds-in-ediscovery-cases.md) . 
    
- EDiscovery 보류에 사용자 목록에 대 한 [사서함 및 OneDrive 위치 추가](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Microsoft 365의 고급 eDiscovery 솔루션을 사용 하 여 법적 조사 관리

Microsoft 365의 고급 eDiscovery 솔루션은 Office 365의 기존 eDiscovery 및 분석 기능을 기반으로 작성 되었습니다. *Advanced eDiscovery*라는이 새로운 솔루션은 조직의 내부 및 외부 조사에 응답 하는 콘텐츠를 보존, 수집, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공 합니다. 또한 법률 팀에서 법적 보존 알림 워크플로 전체를 관리 하 여 사례와 관련 된 custodians와 통신할 수 있습니다.

고급 eDiscovery를 사용 하려면 Microsoft 365 또는 Office 365 조 직에 대 한 E5 구독이 필요 합니다. 라이선스에 대 한 자세한 내용은 [Advanced eDiscovery 시작](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)을 참조 하세요.

다음은 Advanced eDiscovery의 기본 제공 워크플로에 대 한 간략 한 개요입니다. 자세한 내용은 [Advanced eDiscovery 워크플로 탐색](get-started-with-advanced-ediscovery.md#explore-the-advanced-ediscovery-workflow)을 참조 하십시오.

- 시작 하려면 [사례 만들기](create-new-ediscovery-case.md)

- [Custodians](managing-custodians.md) 를 사례에 추가 하 고 해당 사서함, OneDrive 계정 및 Microsoft 팀 구성원 인 콘텐츠에 법적 보존을 배치 하 여 관리 합니다.

- 법적 보존 알림 프로세스를 자동화 하 여 custodians와의 [통신 관리](managing-custodian-communications.md)

- 조사를 위해 데이터를 효과적으로 수집할 수 있도록 [custodian 데이터를 인덱싱하고](processing-data-for-case.md) 인덱싱 오류를 해결 합니다.

- 사례에 대 한 [데이터를 수집](collecting-data-for-ediscovery.md) 하 고 추가 조사를 위해 [검토 집합에](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) 추가 합니다.

- 검토 집합의 문서, [쿼리](review-set-search.md) 데이터 및 [태그](tagging-documents.md) 항목 [보기](view-documents-in-review-set.md)

- 고급 분석 도구를 사용 하 여 [사례 데이터 분석](analyzing-data-in-review-set.md)

- 자문 위원 외부에서 검토할 [사례 데이터 내보내기](exporting-data-ediscover20.md)

- 고급 eDiscovery에서 [장기 실행 작업 관리](managing-jobs-ediscovery20.md)

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
description: Office 365의 보안 & 준수 센터에서 eDiscovery 사례를 사용하여 조직의 법적 조사를 관리합니다.
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840707"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Microsoft 365에서 법적 조사 관리

조직은 조직의 특정 임원이나 다른 직원과 관련된 법률 사례에 대응해야 하는 여러 가지 이유가 있습니다. 여기에는 전자 메일, 문서, 인스턴트 메시징 대화 및 매일 작업에서 사람들이 사용하는 기타 콘텐츠 위치에서 추가 조사 관련 정보를 빠르게 찾아서 보존해야 할 수 있습니다. 보안 및 규정 준수 센터에서 eDiscovery 사례 도구를 사용하여 이러한 활동 및 기타 많은 유사한 작업을 수행할 수 있습니다.
  
**Microsoft에서 eDiscovery 조사를 관리하는 방법을 알고 싶나요?** 다음은 동일한 [](https://go.microsoft.com/fwlink/?linkid=852161) 검색 및 조사 도구를 사용하여 내부 eDiscovery 워크플로를 관리하는 방법을 설명하는 다운로드할 수 있는 기술 백서입니다.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>eDiscovery 사례를 사용하여 법적 조사 관리

eDiscovery 사례를 사용하면 조직에서 eDiscovery 사례를 만들고, 액세스하고, 관리할 수 있는 사용자들을 제어할 수 있습니다. 사례를 사용하여 구성원을 추가하고 수행할 수 있는 작업 유형을 제어하고, 법률 사례와 관련된 콘텐츠 위치를 보류하고, 콘텐츠 검색 도구를 사용하여 보류된 위치를 검색하여 사례에 응답할 수 있는 콘텐츠를 검색합니다. 그런 다음 외부 검토자에 의해 추가 조사를 위해 이러한 결과를 내보내고 다운로드할 수도 있습니다.
  
- [조직에서 진행해야 하는](ediscovery-cases.md) 모든 법적 조사에 eDiscovery 사례를 만들고 사용하여 eDiscovery 워크플로를 관리합니다.

- [eDiscovery 권한을](assign-ediscovery-permissions.md) 할당하여 조직에서 eDiscovery 사례를 만들고 관리할 수 있는 사용자 제어

- [준수 경계를 설정하여](set-up-compliance-boundaries.md) eDiscovery 관리자가 검색할 수 있는 사용자 콘텐츠 위치를 제어합니다.

- [조직에서 콘텐츠를](search-for-content.md) 검색합니다.

### <a name="use-scripts-for-advanced-scenarios"></a>고급 시나리오에 스크립트 사용

콘텐츠 검색 시나리오에 대한 스크립트를 나열한 이전 섹션과 마찬가지로 eDiscovery 사례를 관리하는 데 도움이 되는 몇 가지 보안 & 준수 센터 PowerShell 스크립트도 만들어졌습니다.
  
- [조직의 eDiscovery](create-a-report-on-holds-in-ediscovery-cases.md) 사례와 연결된 모든 보류에 대한 정보가 포함된 eDiscovery 보류 보고서를 만들 수 있습니다.

- 사용자 목록에 대한 사서함 및 [OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) 위치를 eDiscovery 보류에 추가합니다.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Microsoft 365의 Advanced eDiscovery 솔루션으로 법적 조사 관리

Microsoft 365의 Advanced eDiscovery 솔루션은 Office 365의 기존 eDiscovery 및 분석 기능을 빌드합니다. *Advanced eDiscovery라는* 이 새로운 솔루션은 조직의 내부 및 외부 조사에 응답하는 콘텐츠를 보존, 수집, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공합니다. 또한 법률 팀에서 전체 법적 보유 알림 워크플로를 관리하여 사례에 관련된 보유자와 통신할 수 있습니다.

Advanced eDiscovery를 사용하려면 Microsoft 365 또는 Office 365 조직에 대한 E5 구독이 필요합니다. 라이선스에 대한 자세한 내용은 [Advanced eDiscovery 설정을 참조하세요.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

다음은 Advanced eDiscovery의 기본 제공 워크플로에 대한 간략한 개요입니다. 자세한 내용은 [Advanced eDiscovery 워크플로 관리를 참조하세요.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [시작할 사례를](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) 만드시다.

- [보유자들을](managing-custodians.md) 사례에 추가하고 사서함, OneDrive 계정 및 구성원으로 있는 Microsoft Teams의 콘텐츠에 법적 보유를 배치하여 보유자 관리

- [법적 보유](managing-custodian-communications.md) 알림 프로세스를 자동화하여 보유자와의 통신을 관리합니다.

- [조사를 위해](processing-data-for-case.md) 데이터를 효과적으로 수집할 수 있도록 보호자 데이터를 인덱싱하고 인덱싱 오류를 수정합니다.

- [사례에](collecting-data-for-ediscovery.md) 대한 데이터를 [](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) 수집하고 추가 조사를 위해 검토 집합에 추가합니다.

- [검토](view-documents-in-review-set.md) 집합에서 문서, [](tagging-documents.md) [쿼리](review-set-search.md) 데이터 및 태그 항목을 볼 수 있습니다.

- [고급 분석 도구를 사용하여](analyzing-data-in-review-set.md) 사례 데이터를 분석합니다.

- [외부 자문이 검토할](exporting-data-ediscover20.md) 사례 데이터를 내보낼 수 있습니다.

- [Advanced](managing-jobs-ediscovery20.md) eDiscovery에서 장기 실행 작업을 관리합니다.

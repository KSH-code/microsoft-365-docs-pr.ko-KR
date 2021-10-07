---
title: Microsoft 개인 정보 관리(미리 보기)에서 주체 권한 요청 관리
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Microsoft 개인 정보 보호 관리의 주체 권한 요청 영역을 사용하면 개인 데이터를 찾고 콘텐츠를 검토하고 보고서를 만드는 데 공동 작업을 할 수 있습니다.
ms.openlocfilehash: deb5bc50aa047cd336684e586ee3bf86286417c1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207214"
---
# <a name="manage-subject-rights-requests-in-privacy-management-preview"></a>개인 정보 관리에서 주체 권한 요청 관리(미리 보기)

개인 정보 보호 관리는 조직 내에서 개인 데이터를 관리하기를 원하는 사용자로부터의 요청을 처리하는 데 도움이 되는 강력한 주체 권한 요청 기능을 제공합니다. 이러한 요청을 DSRs(데이터 주체 요청), DSARS(데이터 주체 액세스 요청) 또는 소비자 권한 요청이라고도 합니다. 개인 정보 보호 관리를 통해 주체 권한 요청을 이행하는 담당자는 데이터 주체가 쉽게 식별될 수 있도록 지원하여 Exchange, SharePoint, OneDrive 및 데이터에서 조직의 데이터 사이에서 개인 정보를 Teams.

개인 정보 관리는 이러한 요청에 대해 수집한 데이터 내에서 검토할 항목의 우선 순위를 지정할 수 있도록 돕습니다. 이 솔루션은 잠재적으로 기밀이 Microsoft Information Protection 수 있는 콘텐츠를 나타내고 이러한 레이블로 항목에 플래그를 지정하는 민감도 레이블을 인식하고 있습니다. 민감도 레이블에 대한 자세한 내용은 민감도 레이블에 대한 자세한 [정보를 참조하세요.](sensitivity-labels.md) 또한 개인 정보 보호 관리는 여러 사용자 데이터가 포함된 항목을 검색하고 플래그를 지정합니다. 여기서 데이터 주체에게 콘텐츠를 제공하기 전에 콘텐츠를 재배치해야 할 수 있습니다.

데이터가 수집 및 평가된 후 보고서 및 내보내기에서 포함할 가장 관련성이 높은 항목을 선택하고 다른 팀 구성원과 안전하게 공동 작업을 통해 요청을 완료하기 위해 이동할 수 있습니다.

## <a name="get-started-with-subject-rights-requests"></a>주체 권한 요청 시작

개인 정보 관리는 개인 정보 관리자가 조직에서 받은 주체 권한 요청을 처리할 수 있는 중앙 허브를 제공합니다.

새 요청 사례 처리를 시작하거나 진행 중 요청에 대한 작업을 진행하기 위해 주체 권한 요청 페이지를 **방문하세요.** 팀이 개인 정보 관리 내에서 만든 사례, 상태(활성, 마감 또는 연한), 요청 유형 및 필터링할 수 있는 모든 요청 목록을 시각적으로 제공합니다. 이 페이지에서도 새 요청을 열 수 있습니다.

열려 있는 사례에 대한 세부 정보를 확인하려면 목록에서 요청을 선택하고 이동을 선택하여 세부 **정보를 요청합니다.** 자세한 내용은 검토 및 [요청에 대한 작업 수행을 참조하세요.](#review-and-take-action-on-requests)

새 요청을 열기 위해 요청 [만들기를 참조합니다.](#create-a-request)

## <a name="create-a-request"></a>요청 만들기

주체 권한 관리 관리자는 개인 정보 관리 마법사를 사용하여 요청을 만들 수 있습니다. 마법사는 데이터 주체에 대한 개인 데이터를 찾아 요청을 이행하는 프로세스를 안내합니다.

네 가지 주요 단계는 다음과 같습니다.

### <a name="identify-the-data-subject"></a>데이터 주체 식별

요청을 한 주체의 이름을 제공하고 회사와의 관계를 지정합니다.

### <a name="select-the-request-type"></a>요청 유형 선택

데이터 주체가 데이터로 원하는 작업을 기반으로 요청 유형을 선택하십시오. 요청이 특정 데이터 개인 정보 보호 규정과 관련된 경우 제공된 목록에서 해당 요청을 선택하여 컨텍스트를 더 추가할 수도 있습니다. 기한(필수)을 설정하면 요청에 접근하거나 기한이 지난 요청을 쉽게 정렬하고 시기에 따라 해결할 수 있습니다. 요청 유형은 다음과 같습니다.

- **액세스:** 조직에서 데이터 주체의 개인 정보를 요약하여 Microsoft 365.
- **내보내기:** 검토하는 동안 수집 및 주석을 달고 수집된 데이터 주체의 개인 정보의 요약 및 내보내기 기능을 제공합니다.
- **추가 작업용 태그가** 지정된 목록: 개인 정보 관리 외부에서 추가 작업이 필요할 수 있는 파일의 요약을 생성합니다. 한 가지 예제 시나리오는 요청에 따라 데이터 주체의 개인 정보를 쉽게 지우는 것이 필요한 경우일 수 있습니다.

### <a name="confirm-the-request-name"></a>요청 이름 확인

이 단계를 통해 이 요청의 이름을 확인하고 참조를 위한 선택적 설명을 추가할 수 있습니다.

### <a name="review-and-finish"></a>검토 및 완료

이전 단계에서 입력한 내용에 대한 요약입니다. 요청 만들기 를 선택하기 전에 모든 필드를 **편집할 수 있습니다.**

이 수준에서는 마감일, 요청 이름 및 설명을 포함하여 요청이 만들어진 후 일부 속성을 편집할 수 있지만 주체의 ID와 같은 주요 속성은 변경할 수 없습니다. 기존 요청을 편집하려면 주체 권한 요청 페이지의 요청 목록에서 기존 요청을 찾고 요청 세부 정보 편집 **작업을** 사용하세요.

## <a name="review-and-take-action-on-requests"></a>검토 및 요청에 대한 작업 수행

요청이 열리면 개인 정보 보호 관리에서 사용자 Microsoft 365 검색을 시작하여 주체에 대한 데이터를 검색합니다. 초기 결과를 확인하려면 목록에서 해당 요청을 선택하고 이동을 선택하여 세부 **정보를 요청합니다.** 여기에서 요청의 속성, 검색 결과 및 요청의 상태에 대해 자세히 확인할 수 있습니다. 또한 이 페이지는 찾은 파일 관리, 보고서 및 내보내기 만들기, 요청을 완료하는 데 사용할 수 있는 허브가 됩니다.

이 페이지의 타일은 다음과 같습니다.

- **세부 정보:** 마감일 및 요청 날짜, 설명 및 관련 개인 정보 규정을 포함하여 요청에 대한 핵심 세부 정보입니다.
- **진행률**: 완료된 단계와 아직 완료되지 않은 작업을 나타내는 시간 표시 막대입니다.
- 현재 진행 단계에 대한 통계입니다. 이 타일은 데이터 예상 요약, 검색에서 찾은 항목 수, 검색된 항목의 위치 또는 Microsoft 365 상태와 같은 정보를 표시될 수 있습니다.
- **검토할** 우선 순위 항목: 적용 가능한 경우 Microsoft 민감도 레이블이 이미 있는 기밀 정보 또는 여러 개인에 대한 데이터가 있는 항목을 포함하여 개인 정보 관리에서 검색한 중요한 항목에 대한 정보가 표시됩니다. 우선 순위 항목은 "우선 순위 유형" 열을 통해 필터링하여 수집한 데이터에서 찾을 수 있습니다.

### <a name="monitor-progress-and-complete-requests"></a>진행률 모니터링 및 요청 완료

주체 권한 요청은 완료하는 방법을 여러 단계로 거치게 됩니다. 개인 정보 관리가 데이터 평가를 수행하면 일부 단계가 자동으로 진행되고, 주체 권한이 관리자와 참가자가 파일 검토, 선택 및 삭제와 같은 필수 단계를 완료하면 진행되는 단계도 있습니다.

시간이 지날 때 또는 여러 참가자가 요청을 처리해야 할 수 있습니다. 개인 정보 보호 관리는 요청의 상태에 대한 지속적인 업데이트와 다음 단계에 대한 지침을 제공합니다. 이러한 업데이트는 주체 권한 요청의 개요 페이지에서 볼 수 있습니다. 진행률 단계는 다음과 같습니다.

#### <a name="data-estimate"></a>데이터 예상

데이터 예상치는 데이터 평가의 초기 단계입니다. 요청이 만들어진 후 개인 정보 관리는 조직의 데이터에서 데이터 주체와의 잠재적인 일치 항목을 포함할 수 있는 항목 수를 식별하고 이러한 항목이 데이터 주체의 위치를 Microsoft 365. 데이터 예상 데이터가 완료되면 결과를 미리 보고 원래 검색 쿼리의 세부 정보를 검토할 수 있습니다. 검색 쿼리를 편집하려면 검색 쿼리 보기 및 [편집의 지침을 참조하세요.](#view-and-edit-search-queries) 초기 결과가 만족스러운 경우 계속 데이터 **검색을 진행할 수 있습니다.**

- 모든 검색에서 최대 10,000개 개별 항목을 검색할 수 있습니다. 일치하는 항목과 연결된 파일(예: 전자 메일의 첨부 파일)은 합계에 계산될 수 있습니다. 검색이 파일 수 임계값을 초과하는 경우 검색을 수정하여 범위를 구체화합니다. 자세한 [내용은 검색 쿼리](#view-and-edit-search-queries) 보기 및 편집 섹션을 참조하세요. 데이터 검색 단계가 시작되면 검색 쿼리를 편집할 수 없습니다.

#### <a name="retrieve-data"></a>데이터 검색

이 단계에서는 개인 정보 관리가 데이터를 검색하고 있는 중입니다. 완료되면 자동으로 데이터 검토로 **진행됩니다.**

#### <a name="review-data"></a>데이터 검토

이 단계에서 참가자는 데이터 수집 탭에서 결과를 검토해야 합니다. 필수 단계는 다음과 같습니다.

- 요약 및/또는 내보내기에서 식별된 항목을 포함할지 여부를 선택 합니다. 내보내기 또는 보고서에 보고된 일치가 필요하지 않은 경우 "제외"의 옵션을 선택합니다. 콘텐츠가 가짓 긍정으로 표시될 경우 "일치하지 않습니다."를 선택하면 최종 보고서에서 파일을 제외하고 요청에 의해 선택되지 않은 항목으로 항목에 플래그를 지정합니다. 항목의 상태를 설정하려면 이름 옆에 있는 작업 메뉴(세로 타원)를 사용하여 원하는 항목을 선택합니다. 메시지가 표시될 경우 내부 참조에 대한 메모를 추가하여 결정에 대해 설명합니다. 파일을 제외할 때 메모가 필요합니다.
- 태그 **적용** 옵션을 사용하여 주의가 필요한 항목을 식별할 수 있습니다. 사용 가능한 태그에는 시스템에서 제공하는 옵션(예: 추가 기능을 위해 항목에 태그 지정)이 포함되고, 시스템에서 정의한 사용자 지정 태그가 설정.
- **Annotate를 사용하여** 선택한 파일에 인라인 표시 또는 변경을 만들 수 있습니다. 예를 들어 다른 사람의 개인 정보도 포함하는 개인용 파일을 포함해야 하는  경우 영역 변경(명령 표시줄의 그리기 단추 아래)을 사용하여 요청한 사용자와 관련이 없는 모든 정보를 블랙아웃할 수 있습니다. 편집이 완료되면 포함을 선택하여 수정된 파일을 요청에 추가합니다. 주석은 파일의 복사본을 만들어 원래 파일의 아무 것도 변경되지 않은 상태로 원래 위치에 남아 있습니다. 복사본이 Azure Blob에 저장됩니다.
- 항목에 대한 메모를 검토하려면 해당 항목을 선택하고 파일 메모 탭으로 이동하십시오. 파일 메모 추가 옵션을 사용하여 새 메모를 만들 수 있습니다. 전체 사례 수준에서 메모를 검토하거나 추가하기 위해 위의 주 메모 탭으로 이동하여 사례 메모 **추가 를 사용합니다.** 이러한 메모는 요청에 대해 작업하는 사용자에게 표시되지만 최종 보고서에 포함되거나 데이터 주체와 공유되지는 않습니다.

모든 항목이 검토되고 상태가 설정되어 있는  경우 검토 완료를 선택하여 데이터 요약을 검토하고 관련 메모를 추가할 수 있는 플라이오버 창을 열 수 있습니다. 이러한 메모는 내부 레코드 유지를 위한 것이고 데이터 주체와 공유되지 않습니다. 검토 완료를 다시 선택하여 다음 단계로 진행합니다. 결정에 대한 요약은 나중에 보고서 탭에서 제공됩니다.

#### <a name="generate-reports"></a>보고서 생성

이 단계는 보고서가 생성되고 있는 것을 나타냅니다. 완료되면 보고서 탭에서 찾을 **수** 있습니다. 여기서 완료된 파일은 요청을 한 데이터 주체에게 배달하기 위해 내보낼 수 있습니다.

#### <a name="close-the-request"></a>요청 닫기

주체 권한 요청을 해결하는 데 필요한 작업을 수행한 경우 요청 **닫기 를 선택하세요.** 그러면 보고서 탭에서 암호화되고 사용할 수 있는 최종 **보고서가** 생성됩니다. 요청의 파일 수에 따라 시간이 걸릴 수 있습니다.

### <a name="view-and-edit-search-queries"></a>검색 쿼리 보기 및 편집

주체 권한 요청 뒤의 데이터 검색에 대한 자세한 정보를 확인하려면 검색 쿼리 세부 정보 **보기를 선택합니다.** 그러면 쿼리를 요약하고 찾은 내용에 대한 추가 세부 정보가 표시되는 창이 열립니다.

여기서 검색 결과 미리  보기 옵션을 사용하여 이 쿼리에 대해 반환되는 콘텐츠 형식을 볼 수 있습니다. 이 검색의 속성을 변경하고 데이터 검색 단계를 시작하지 않은 경우 검색 쿼리 편집 옵션을 사용할 **수** 있습니다. 이 마법사는 데이터 주체 식별, 검색 필터 및 조건 및 데이터를 찾을 위치(예: Exchange, SharePoint, OneDrive 및/또는 데이터)에 대한 속성을 변경하거나 추가하는 기능을 Teams. 이러한 옵션을 사용하여 원하는 특정성 수준에 도달할 수 있습니다. 저장을 실행하기 전에 새 쿼리의 최종 버전을 검토할 **수 있습니다.**

검색 쿼리 편집을 마치면 이전 검색 결과를 바꾸기 위해 새 검색이 실행됩니다. 그러면 진행률 섹션의 상태가 첫 번째 단계인 데이터 예상 으로 **다시 설정됩니다.** 새 검색을 완료하는 데 최대 60분이 걸릴 수 있습니다. 완료되면 요청의 세부 정보 페이지에 업데이트된 결과가 표시됩니다.

## <a name="collaborate-on-requests-with-teams"></a>요청에 대해 공동 작업을 Teams

개인 정보 보호 관리는 그룹이 Microsoft Teams 요청에 대해 공동 작업을 할 수 있도록 하여 공동 작업을 지원하고 있습니다. 새 요청을 만들면 기본적으로 Teams 채널이 자동으로 만들어지며 요청에 연결됩니다. 여기서 요청에 대해 논의하고 완료를 진행할 때 입력 및 기여를 안전하게 공유할 수 있습니다. 대화에 참가하기 위해 요청을 열고 공동 작업자와 **채팅 옵션을** 사용합니다. 그러면 Microsoft Teams 권한 요청의 팀 사이트에 대한 일반 채널 내에 추가됩니다.

팀 사이트를 보고 기여할 수 있는 활성 공동 작업자 목록을 검토하기 위해 주체 권한 요청 내에서 공동 작업자 탭을 **여는** 것이 좋습니다. 이 요청에 대해 공동 작업을 할 사용자를 더 추가하려면 공동 작업자 추가 옵션을 선택합니다.

주체 권한 요청을 만들 때 Teams 사이트의 기본 동작을 변경하려면 주체 권한 요청 페이지의 오른쪽 **위 모서리에** 있는  설정 기어를 선택하고 Teams 공동 작업을 선택하여 설정을 수정합니다.

주체 권한  요청 내의 오른쪽 위에 있는 공유 옵션을 사용하여 Teams 또는 전자 메일을 통해 다른 사용자와 반복하거나 개인 정보 관리에서 해당 링크를 페이지에 복사할 수도 있습니다. Teams 공유를 사용하면 계정에 사용할 수 있는 기존 Teams 사이트를 선택하고 해당 사이트 내에서 사용자가 제공한 메시지와 함께 이 사례에 대한 링크를 게시할 특정 채널을 선택할 수 있습니다.

## <a name="automate-subject-rights-request-tasks"></a>주체 권한 요청 작업 자동화

Microsoft Power Automate 응용 프로그램 및 서비스 전반에 걸쳐 작업을 자동화하는 워크플로 서비스입니다. 개인 정보 관리에 Power Automate 흐름을 사용하도록 설정하면 사례 및 사용자에 대한 중요한 작업을 자동화할 수 있습니다. 자세한 내용은 Power Automate 사이트를 [방문하세요.](/power-automate/getting-started)

개인 정보 관리를 Microsoft 365 구독을 사용하는 고객은 권장되는 개인 정보 관리 Power Automate 템플릿을 사용하기 위해 다른 Power Automate 필요가 없습니다. 이러한 템플릿은 조직을 지원하고 핵심 개인 정보 관리 시나리오를 다루기 위해 사용자 지정될 수 있습니다. 이러한 템플릿에서 프리미엄 Power Automate 기능을 사용하려면 Microsoft 365 준수 커넥터를 사용하여 사용자 지정 템플릿을 만들거나 Microsoft 365 다른 준수 영역에 대해 Power Automate 템플릿을 사용하려면 추가 Power Automate 라이선스가 필요할 수 있습니다.

다음 Power Automate 템플릿이 개인 정보 관리에 포함됩니다.

- **ServiceNow에서** 개인 정보 관리 사례에 대한 레코드 만들기 : 이 템플릿은 ServiceNow 솔루션을 사용하여 주체 권한 요청 사례를 추적하려는 조직을 위한 것입니다. ServiceNow에 연결할 계정을 포함해 ServiceNow 인스턴스 세부 정보를 입력해야 합니다. 이 계정에는 ServiceNow에서 인시던트 만들기 및 인시던트 세부 정보를 입력할 수 있는 능력이 있어야 합니다. 인스턴스에 연결되면 주체 권한 요청 관리자는 ServiceNow에서 사례에 대한 레코드를 만들고 필요한 경우 서식 파일을 선택한 필드에 채울 대상을 사용자 지정할 수 있습니다. 커넥터에 대한 자세한 내용은 [ServiceNow Connector 참조 페이지를 참조하세요.](/connectors/service-now/)
- **일정 미리** 알림 만들기: 이 템플릿은 주체 권한 요청에 대한 Outlook 일정에서 기한 미리 알림을 설정하기 위한 것입니다. 이 도구는 요청의 속성에서 특정 세부 정보(예: 요청 이름 및 기한)를 채우게 됩니다. 자세한 내용을 추가하고, 받는 사람을 지정하고, 기타 고급 설정을 조정할 수 있습니다.

### <a name="create-a-new-power-automate-flow-from-a-template"></a>템플릿에서 새 Power Automate 흐름 만들기

시작하려면 작업할 주체 권한 요청을 열고 자동화를 선택한 다음 흐름 Power Automate **선택합니다.** 그러면 흐름 플라이아웃 창이 열립니다. 새 옵션을 사용하여 사용 가능한 옵션에서 사용할 서식 파일을 선택합니다. 여기에서 프롬프트에 따라 설정을 완료합니다.

템플릿의 인스턴스를 저장한 후 흐름 인스턴스에 올바른 컨텍스트와 ID가 있도록 주체 권한 요청의 세부 정보 페이지에서 인스턴스를 실행해야 합니다. 요청을 열고 자동화 메뉴로 **돌아가고** 템플릿을 선택한 다음 흐름 **실행을 선택합니다.** 흐름 실행 활동 참조를 선택하여 과거 활동을 **볼 수 있습니다.**

### <a name="share-a-power-automate-flow"></a>공유 Power Automate 공유

흐름을 Power Automate 다른 소유자를 추가하고 흐름을 편집, 업데이트 및 삭제할 수 있습니다. 모든 소유자는 실행 기록에 액세스하여 다른 소유자를 추가하거나 제거할 수도 있습니다. 흐름을 공유하려면 작업할 주체 권한 요청을 열고 자동화를 선택한 다음 흐름 Power Automate **선택합니다.**  이 창에서 기존 흐름을 선택한 다음 공유 옵션을 사용하여 사용자 또는 그룹을 추가할 수 있습니다.

또한 이 창에서는 서비스 흐름에 사용되는 서비스에 대한 포함된 연결을 관리하는 Power Automate 있습니다. 이러한 설정을 변경하면 흐름 실행 능력에 영향을 줄 수 있습니다.

### <a name="edit-or-delete-power-automate-flow"></a>흐름 편집 또는 Power Automate 삭제

흐름의 세부 Power Automate 조정하려면 주체 권한 요청을 열고 자동화를 선택하고 흐름 Power Automate **선택합니다.** 이 창에서 기존 흐름을 선택하여 세부 정보를 볼 수 있습니다. 모든 섹션에서 편집을 사용하여 속성을 변경한 다음 저장합니다.

흐름을 완전히 제거하려면 삭제 **옵션을** 사용합니다. 모든 소유자에 대한 흐름을 제거하고 모든 사용자에 대해 제거합니다. 이전 흐름 인스턴스는 데이터 손실을 방지하기 위해 계속 실행됩니다. 선택을 확인한 후, 선택을 끝까지 할 수 있습니다.

## <a name="data-matching"></a>데이터 일치

데이터 일치를 통해 조직은 개인 정보 관리 솔루션을 사용하여 정확한 제공된 데이터 값에 따라 데이터 주체를 식별할 수 있습니다. 이렇게 하여 내부 직원과 상호 작용하는 외부 사용자 모두에 대해 데이터 주체 콘텐츠를 검색하는 정확도를 높일 수 있습니다. 또한 주체 권한 요청을 생성하는 동안 필드를 수동으로 제공해야 하는 필요성을 간소화하고 주체 권한 요청 내의 컨텍스트와 가장 많은 데이터 주체 콘텐츠가 있는 항목을 소개하는 개요 타일에 대한 컨텍스트를 제공합니다. 보기에 대한 자세한 내용은 데이터 찾기 및 [시각화를 참조합니다.](privacy-management-data-profile.md#items-with-the-most-data-subject-content)

데이터 일치 기능을 사용하려면 개인 정보 관리 역할 그룹의 구성원이 되어야 합니다. 주체 권한 요청 페이지의 오른쪽 상단에서 설정 기어 아이콘을 선택하고 데이터 **일치를 선택합니다.** 여기에서는 아래와 같이 개인 데이터chema를 정의하고 개인 데이터 업로드를 제공해야 합니다. 항목을 추가할 수 있으며 UI를 통해 추가한 항목을 삭제할 수 있습니다. 그러나 현재 UI에서 현재 있는 항목을 수정할 수는 없습니다.

### <a name="prepare-for-data-import"></a>데이터 가져오기 준비

데이터를 업로드하거나 해당 데이터를 정의하기 전에 데이터 주체 정보의 원본을 식별해야 합니다. 필수 파일 형식은 .csv 응용 프로그램에서 읽을 수 있는 Microsoft Excel. 열 머리줄이 첫 번째 행에 나타나게 이 내보내기 구조를 구성합니다. 이러한 헤더에는 개인 데이터 스마의 특성 이름이 포함되어야 합니다. 각 필드의 데이터 형식을 검사합니다. 데이터 중 하나에 콤보가 포함되어 있는 경우 이러한 값을 작은 따옴표로 하여 별도의 필드로 구문 분석되지 않도록 합니다.

### <a name="define-the-personal-data-schema"></a>개인 데이터Chema 정의

개인 데이터 schema는 데이터 주체의 특성을 설명합니다. 업로드 설정 영역의 첫 번째 탭에서 이 schema를 선택합니다. 필요한 파일에는 개인 **데이터 schema** XML 파일과 규칙 **패키지** XML 파일이 포함됩니다.

#### <a name="personal-data-schema-xml"></a>개인 데이터 schema XML

개인 데이터chema 파일은 예상되는 열 이름을 정의하는 XML 파일입니다.

- 이 schema *파일의* 이름을 에pdm.xml.
- 아래 예제와 같은 필드 이름 태그를 사용하여 각 열 이름을 정의합니다.
- 검색할 수 있는 필드에 대해 최대 5개의 필드까지 검색 가능 = "true"를 사용할 수 있습니다. 하나 이상의 필드 이름을 검색할 수 있어야 합니다. 샘플 구문: `\<Field name="" searchable=""/>` .
- 개인 데이터 schema에는 DataStore 태그 섹션이 있습니다. primaryKeyField, upnField, firstNameField, lastNameField의 네 가지 필수 필드를 필드 이름에 매핑해야 합니다.

예를 들어 다음 XML 파일은 PatientID, MRN, SSN, 전화 및 DOB 필드가 검색 가능으로 지정된 샘플 전화 정의합니다. primaryKeyField는 PatientID에 매핑하고, upnField는 MRN에 매핑하고, firstNameField는 FirstName에 매핑하고, lastNameField는 LastName에 매핑됩니다.

(여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)

 ```xml
<PdmSchema xmlns="http://schemas.microsoft.com/office/2020/pdm">
      <DataStore name="Patientrecords" description="Schema for patient records" version="1" primaryKeyField="PatientID" upnField="MRN" firstNameField="FirstName" lastNameField="LastName">
            <Field name="PatientID" searchable="true"/>
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</PdmSchema>
 ```

#### <a name="rule-package-xml"></a>규칙 패키지 XML

규칙 패키지를 설정할 때 위에서 만든 개인 데이터 스마마 파일을 올바르게 참조해야 합니다. pdm.xml. 다음 샘플 규칙 패키지 XML에서 데이터 일치 중요한 유형을 만들 수 있도록 다음 필드를 사용자 지정해야 합니다.

- **RulePack id**  &  **PrivacyMatch id:** New-GUID를 사용하여 GUID를 생성합니다.
- **데이터 저장소:** 이 필드는 사용할 개인 데이터 일치 데이터 저장소를 지정합니다. 구성된 개인 데이터 schema의 정의된 DataStore 이름을 제공합니다.
- **idMatch:** 이 필드는 개인 데이터 일치의 기본 요소를 포인트로 합니다.
  - **일치:** 정확한 Lookup에 사용할 필드를 지정합니다. 개인 데이터 schema에서 검색 가능한 필드 이름을 제공합니다.
  - **분류:** 이 필드는 개인 데이터 일치를 트리거하는 중요한 유형 일치를 지정합니다. 기존 기본 제공 이름이나 GUID 또는 사용자 지정 중요 유형 정보를 제공할 수 있습니다. 성능 문제가 발생하지 않도록 개인 데이터 일치에서 분류 요소로 사용자 지정 중요한 정보 유형을 사용하는 경우 콘텐츠의 많은 비율(예: "숫자" 또는 "5문자 단어")과 일치하는 사용자 지정 중요한 정보 유형을 사용하지 않도록 합니다. 지원 키워드를 추가하거나 사용자 지정 분류 중요한 정보 유형 정의에 서식을 포함하는 것이 좋습니다.
- **일치:** 이 필드는 idMatch의 근접성에서 발견된 추가 증거를 포인트로 합니다.
  - **일치:** DataStore의 개인 데이터 schema에 필드 이름을 입력합니다.
- **리소스**: 이 섹션에서는 여러 로 지역의 중요한 유형에 대한 이름과 설명을 지정합니다.
  - **idRef**: ExactMatch ID에 대한 GUID를 제공 합니다.
  - **이름 & 설명:** 필요에 따라 사용자 지정합니다.

아래 규칙 패키지 XML 예제에서는 개인 데이터 pdm.xml XML을 만드는 이전 단계의 예제 파일을 참조합니다.

- **Datastore**: dataStore 이름은 앞에서 만든 스마마 파일을 참조합니다. dataStore = "PatientRecords".
- **idMatch**: idMatch 값은 앞에서 만든 pdm.xml 파일에 나열된 검색 가능한 필드를 참조합니다. idMatch matches = "SSN".
  - **분류**: 분류 값은 기존 또는 사용자 지정 중요한 정보 유형인 분류 = "미국 SSN(사회 보장 번호)"을 참조합니다. (이 경우 미국 주민 등록 번호의 기존의 중요한 정보 유형을 사용합니다.)

다음 예제 코드와 같이 유니코드 인코딩을 사용하여 XML 형식으로 규칙 패키지를 만들 수 있습니다. 이 예제를 복사, 수정 및 사용할 수 있습니다.

 ```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2020/pdm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b21">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care PDM Rulepack</Name>
        <Description>This rule package contains the Personal Data Match sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <PrivacyMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB381" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="6">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </PrivacyMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB381">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">PDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
 ```

### <a name="upload-personal-data"></a>업로드 데이터 저장
개인 데이터chema를 정의한 후 데이터  일치 설정 페이지의 두 번째 탭에서 개인 데이터 업로드를 수행할 수 있습니다. 추가를 **선택하면** 첫 번째 단계에서 정의한 개인 Schema를 선택한 다음 개인 데이터가 포함된 파일을 업로드합니다.

로컬 파일을 선택하거나 개인 데이터 파일이 포함된 기존 Microsoft Azure Storage 위치에 SAS URL을 제공하여 이 개인 데이터를 업로드할 수 있습니다.
이 프로세스에서 만든 Schema를 준수하는 파일을 첫 번째 단계로 준비한 경우 해당 파일을 업로드에 사용할 수 있습니다.

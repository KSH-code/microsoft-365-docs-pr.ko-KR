---
title: SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: SharePoint 및 OneDrive에서 보존이 작동하는 방식을 알아봅니다.
ms.openlocfilehash: 1194ba1aa2367980207d33e2ca4020b8e0ba57d1
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753074"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

SharePoint 및 OneDrive 관련 정보를 포함하므로 이 문서의 정보는 [보존에 대한 자세한 정보](retention.md)를 보완합니다.

다른 워크로드는 다음을 참조하세요.

- [Microsoft Teams의 보존에 대해 자세히 알아보기](retention-policies-teams.md)
- [Yammer의 보존에 대한 자세한 정보](retention-policies-yammer.md)
- [Exchange의 보존에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>보존 및 삭제에 포함된 항목

SharePoint 또는 OneDrive 사이트에 저장된 모든 파일은 보존 정책 또는 보존 레이블을 적용하여 보존할 수 있습니다. 

다음 파일을 삭제할 수 있습니다.

- 보존 정책을 사용하는 경우 다음을 수행합니다. 문서 라이브러리의 모든 파일. 자동으로 생성된 SharePoint 문서 라이브러리를 포함합니다(예: **사이트 자산**).
    
- 보존 레이블을 사용하는 경우: 모든 문서 라이브러리의 모든 파일 및 폴더에 없는 루트 수준의 모든 파일.
    
> [!TIP]
> [보존 레이블에 자동 적용 정책과 함께 쿼리](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)를 사용하는 경우, `NOT(DocumentLink:"<URL to document library>")` 항목을 사용하여 특정 문서 라이브러리를 제외할 수 있습니다.

목록 항목은 보존 정책에서 지원되지 않지만 시스템 목록의 항목을 제외하고 보존 레이블에서 지원됩니다. 이러한 목록은 SharePoint에서 시스템을 관리하는 데 사용하는 숨겨진 목록으로, 마스터 페이지 카탈로그, 솔루션 카탈로그 및 데이터 원본을 포함합니다. 문서 첨부 파일이 있는 지원되는 목록 항목에 보존 레이블을 적용하는 경우:
- 표준 보존 레이블의 경우(항목을 레코드로 선언하지 않는 경우):
    - 문서 첨부 파일은 레이블의 보존 설정을 자동으로 상속하지는 않지만 독립적으로 레이블을 지정할 수 있습니다.
- 항목을 레코드로 선언하는 보존 레이블의 경우: 
    - 문서 첨부 파일은 문서의 레이블이 아직 지정되지 않은 경우 레이블에서 보존 설정을 자동으로 상속합니다.

보존 정책 및 보존 레이블의 보존 설정은 라이브러리, 목록 및 폴더를 포함하는 조직 구조에는 모두 적용되지 않습니다.

보존 정책 및 자동 적용 레이블 정책의 경우, 보존 설정을 적용하려면 SharePoint 사이트를 색인화해야 합니다. 그러나 SharePoint 문서 라이브러리의 항목이 검색 결과에 나타나지 않도록 구성된 경우, 이 구성은 보존 설정의 파일을 제외하지 않습니다.

## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive에서 보존이 작동하는 방식

보존해야 하는 콘텐츠를 저장하기 위해 SharePoint 및 OneDrive는 해당 사이트에 대한 자료 보존 라이브러리가 없는 경우 해당 라이브러리를 생성합니다. 자료 보존 라이브러리는 대화형으로 사용하도록 설계되지 않고, 규정 준수를 위해 필요할 때 파일을 자동으로 저장합니다.

표준 보존 레이블이 있는 SharePoint 항목(이 항목을 레코드로 선언하지 않는 경우)은 원래 위치에 유지되므로 자료 보존 라이브러리가 필요하지 않습니다. SharePoint는 적용된 보존 레이블이 콘텐츠를 유지하도록 구성될 때 사용자가 항목을 삭제하는 것을 방지하고, SharePoint 버전 지정은 항목이 편집될 때 이전 버전을 유지합니다. 그러나 다른 시나리오의 경우 항목을 보존해야 할 때 자료 보존 라이브러리가 사용됩니다.
- 표준 보존 레이블이 있는 단일 드라이브 항목
- 레코드를 선언하는 보존 레이블이 있는 SharePoint 또는 OneDrive의 항목이 있으며 해당 항목이 편집을 위해 잠금 해제됩니다.
- 보존 레이블이 자동으로 적용된 클라우드 첨부 파일로 공유된 파일
- 보존 정책의 적용을 받는 항목

사용자가 콘텐츠를 변경하거나 삭제하려고 할 때 이 내용을 유지하기 위해 보존 설정이 적용된 이후 내용이 변경되었는지 확인합니다. 보존 설정이 적용되고 처음 변경하는 경우라면 해당 콘텐츠는 자료 보존 라이브러리에 복사되어 거기에서 해당 사용자는 원본 콘텐츠를 변경하거나 삭제할 수 있습니다.
  
타이머 작업이 주기적으로 자료 보존 라이브러리를 정리합니다. 자료 보존 라이브러리에 30일 이상 있는 콘텐츠의 경우 이 작업은 콘텐츠를 해당 콘텐츠의 보존 설정에서 사용하는 모든 쿼리와 비교합니다. 구성된 보존 기간보다 오래된 콘텐츠는 자료 보존 라이브러리에서 삭제되고, 아직 남아 있는 경우, 원본 위치에서도 삭제됩니다. 이 타이머 작업은 7일마다 실행되므로 최소 30일과 함께 자료 보존 라이브러리에서 콘텐츠를 삭제하는 데 최대 37일이 걸릴 수 있습니다.

파일을 자료 보존 라이브러리로 복사하기 위한 이 동작은 보존 설정이 적용될 때 존재하는 콘텐츠에 적용됩니다. 또한 보존 정책의 경우 정책에 포함된 후 사이트에 생성되거나 추가된 모든 새 콘텐츠는 자료 보존 라이브러리에 보존됩니다. 그러나 새 콘텐츠는 처음 편집할 때 자료 보존 라이브러리에 복사되지 않고 삭제된 경우에만 복사됩니다. 파일의 모든 버전을 유지하려면 [버전 관리](#how-retention-works-with-document-versions)를 켜야 합니다.
  
보존 대상 라이브러리, 목록, 폴더 또는 사이트를 삭제하려고 하면 오류 메시지가 표시됩니다. 먼저 보존이 적용되는 폴더의 모든 파일을 이동하거나 삭제하는 경우에 폴더를 삭제할 수 있습니다.

보존 설정을 OneDrive 계정 또는 SharePoint 사이트의 콘텐츠에 할당한 후 콘텐츠가 사용하는 경로는 보존 설정이 보존 후 삭제하는지, 아니면 보존 또는 삭제만 가능한지 여부에 따라 달라집니다.

보존 설정이 보존 및 삭제인 경우:

![SharePoint 및 OneDrive의 콘텐츠 수명 주기 다이어그램.](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. 보존 기간 내에 **콘텐츠가 수정되거나 삭제되면** 보존 설정이 적용된 시점과 동일한 원본 콘텐츠의 사본이 자료 보존 라이브러리에 생성됩니다. 여기에서 타이머 작업이 보존 기간이 만료된 항목을 식별합니다. 해당 항목은 2단계 휴지통으로 이동되고, 93일이 지나면 영구적으로 삭제됩니다. 2단계 휴지통은 최종 사용자에게 표시되지 않습니다(1단계 휴지통에만 해당). 하지만 사이트 모음 관리자는 해당 사이트에서 콘텐츠를 보고 복원할 수 있습니다.

    > [!NOTE]
    > 실수로 데이터가 손실되는 것을 방지하기 위해 더 이상 보존 라이브러리의 콘텐츠를 영구적으로 삭제하지 않습니다. 대신 휴지통에서 콘텐츠를 영구적으로 삭제합니다. 이제는 보존 라이브러리의 모든 콘텐츠가 2단계 휴지통을 거칩니다.
    
2. 보존 기간 동안 **콘텐츠가 수정 또는 삭제되지 않은 경우** 타이머 작업은 보존 기간이 끝날 때 이 콘텐츠를 1단계 휴지통으로 이동합니다. 사용자가 휴지통에서 콘텐츠를 삭제하거나 이 휴지통을 비우면(제거라고도 함) 문서는 2단계 휴지통으로 이동됩니다. 93일의 보존 기간은 1단계 및 2단계 휴지통 모두에 걸쳐 있습니다. 93일이 지나면 문서는 1단계 또는 2단계 휴지통에 있는 모든 위치에서 영구적으로 삭제됩니다. 휴지통은 인덱싱되지 않으므로 검색할 수 없습니다. 결과적으로 eDiscovery 검색은 보존할 휴지통 콘텐츠를 찾을 수 없습니다.

> [!NOTE]
> [첫 번째 보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence) 때문에 다른 보존 정책 또는 보존 레이블로 인해 동일한 항목을 유지해야 하거나 법적 또는 조사상의 이유로 eDiscovery 보류 상태에 있는 경우 영구 삭제는 항상 일시 중단됩니다.

보존 설정이 보존 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보존 및 삭제의 변형입니다.

### <a name="content-paths-for-retain-only-retention-settings"></a>보존 전용 보존 설정의 컨텐츠 경로

1. 보존 기간 동안 **컨텐츠가 수정되거나 삭제된 경우**: 보존 라이브러리의 사본이 2단계로 이동될 때 원본 문서의 사본이 보존 라이브러리에 작성되고 보존 기간이 끝날 때까지 보존됩니다. 휴지통이며 93일 후에 영구적으로 삭제됩니다.

2. 보존 기간 동안 **컨텐츠가 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 문서는 원래 위치에 남아 있습니다.

### <a name="content-paths-for-delete-only-retention-settings"></a>삭제만 보존 설정의 컨텐츠 경로

1. 구성된 기간 동안 **컨텐츠가 삭제되는 경우**, 해당 문서는 1단계 휴지통으로 이동됩니다. 여기에서 사용자가 문서를 삭제하거나 휴지통을 비우면 문서가 2단계 휴지통으로 이동됩니다. 1단계 휴지통과 2단계 휴지통을 포함하여 총 93일 간의 보존 기간이 적용됩니다. 93일이 지나면 1단계 휴지통 또는 2단계 휴지통에서 문서가 영구적으로 삭제됩니다. 구성된 기간 동안 컨텐츠가 수정되면 구성된 기간이 지난 후 동일한 삭제 경로를 따릅니다.

2. 설정한 기간 동안 **콘텐츠를 삭제하지 않는 경우**: 보존 정책에 설정된 기간이 종료되면 문서를 1단계 휴지통으로 이동합니다. 사용자가 휴지통에서 문서를 삭제하거나 이 휴지통을 비우면(제거라고도 함) 문서는 2단계 휴지통으로 이동됩니다. 93일의 보존 기간은 1단계 및 2단계 휴지통 모두에 걸쳐 있습니다. 93일이 지나면 문서는 1단계 또는 2단계 휴지통에 있는 모든 위치에서 영구적으로 삭제됩니다. 휴지통은 인덱싱되지 않으므로 검색할 수 없습니다. 결과적으로 eDiscovery 검색은 보존할 휴지통 콘텐츠를 찾을 수 없습니다.

## <a name="how-retention-works-with-cloud-attachments"></a>클라우드 첨부 파일에서 보존이 작동하는 방식

클라우드 첨부 파일은 사용자가 공유하는 파일에 대한 포함된 링크이며 사용자가 Outlook 전자 메일 및 Teams 메시지에서 공유할 때 이 파일을 보존하고 삭제할 수 있습니다. [클라우드 첨부 파일에 보존 레이블을 자동으로 적용](apply-retention-labels-automatically.md#auto-apply-labels-to-cloud-attachments)하면 보존 레이블이 자료 보존 라이브러리에 저장된 공유 파일의 복사본에 적용됩니다.

이 시나리오에서는 항목에 레이블이 지정된 시기를 기준으로 보존 기간을 시작하도록 레이블 설정을 구성하는 것이 좋습니다. 항목이 생성되거나 마지막으로 수정된 날짜를 기준으로 보존 기간을 구성하면 이 날짜는 공유 시점의 원본 파일에서 가져옵니다. 보존 시작을 마지막으로 수정한 날짜로 구성한 경우 이 설정은 자료 보존 라이브러리에 있는 이 복사본에 영향을 주지 않습니다.

그러나 원본 파일을 수정한 다음 다시 공유하면 파일의 새 복사본이 새 버전으로 저장되고 자료 보존 라이브러리에 레이블이 지정됩니다.

원본 파일이 다시 공유되지만 수정되지 않은 경우 자료 보존 라이브러리에 있는 복사본의 레이블이 지정된 날짜가 업데이트됩니다. 이 작업은 보존 기간의 시작을 재설정하므로 항목에 레이블이 지정된 시기를 기준으로 보존 기간의 시작을 구성하는 것이 좋습니다.

보존 레이블은 원본 파일에 적용되지 않으므로 레이블이 지정된 파일은 사용자에 의해 수정되거나 삭제되지 않습니다. 레이블이 지정된 파일은 타이머 작업에서 보존 기간이 만료되었음을 식별할 때까지 자료 보존 라이브러리에 남아 있습니다. 항목을 삭제하도록 보존 설정이 구성된 경우 파일은 2단계 휴지통으로 이동되어 93일이 지나면 영구적으로 삭제됩니다.

![SharePoint 및 OneDrive에 저장된 클라우드 첨부 파일에 대한 보존 작동 방식](../media/retention-diagram-of-retention-flow-cloud-attachments.png)

자료 보존 라이브러리에 저장된 복사본은 일반적으로 공유되는 클라우드 첨부 파일에서 1시간 이내에 생성됩니다.

## <a name="how-retention-works-with-onenote-content"></a>OneNote 콘텐츠에서 보존이 작동하는 방식

OneNote 콘텐츠가 포함된 위치에 보존 정책을 적용하거나 보이지 않는 OneNote 폴더에 보존 레이블을 적용하는 경우 다른 OneNote 섹션은 보존 설정을 상속하는 개별 파일입니다. 즉, 지정한 보존 설정에 따라 각 구역이 개별적으로 유지 및 삭제됩니다.

## <a name="how-retention-works-with-document-versions"></a>보존이 문서 버전에서 작동하는 방식입니다.

버전 관리는 SharePoint 및 OneDrive의 모든 문서 목록 및 라이브러리의 기능입니다. 기본적으로 버전 관리는 최소 500개의 주요 버전을 유지하지만 이 제한을 늘릴 수 있습니다. 자세한 내용은 [목록 또는 라이브러리에 대한 버전 관리 사용](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37) 및 [구성 및 목록 및 라이브러리에서 버전 관리가 작동하는 방식](https://support.microsoft.com/office/how-versioning-works-in-lists-and-libraries-0f6cd105-974f-44a4-aadb-43ac5bdfd247)을 참조하세요.
  
버전이 있는 문서가 해당 내용을 보존하기 위한 보존 설정의 적용을 받는 경우 보존 보류 라이브러리에 복사되는 버전은 별도의 항목으로 존재합니다. 보존 기간이 끝날 때 삭제하도록 보존 설정이 구성된 경우 다음을 수행합니다.

- 보존 기간이 콘텐츠가 만들어진 시점을 기준으로 하는 경우 각 버전은 원본 문서와 동일한 만료 날짜를 갖습니다. 따라서 원본 문서 및 해당 버전은 동시에 만료됩니다.

- 보존 기간이 콘텐츠가 마지막으로 수정된 시점을 기준으로 하는 경우 각 버전은 원본 문서가 해당 버전을 만들기 위해 수정된 시점을 기준으로 하는 자체 만료 날짜를 가집니다. 따라서 원본 문서와 해당 버전은 별도로 만료됩니다.

보존 작업이 문서를 삭제하는 경우 현재 버전에 따라 보존 보류 라이브러리에 없는 모든 버전이 동시에 삭제됩니다.

보존 정책(또는 eDiscovery 보류) 대상 항목의 경우 문서의 보존 기간에 도달하거나 eDiscovery 보류가 해제될 때까지 문서 라이브러리의 버전 관리 제한이 무시됩니다. 이 시나리오에서 오래된 버전은 자동으로 제거되지 않으며, 사용자는 버전을 삭제할 수 없습니다.

콘텐츠가 보존 정책(또는 eDiscovery 보류)의 적용을 받지 않는 경우에는 보존 레이블이 적용되지 않습니다. 대신 새 버전을 수용하기 위해 이전 버전이 자동으로 삭제되도록 버전 지정 제한이 적용되지만 사용자는 여전히 버전을 삭제할 수 없습니다.

## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우

**SharePoint**:

사용자가 조직을 떠나는 경우, 사용자의 사서함 또는 OneDrive 계정과 달리, SharePoint는 공동 작업 환경으로 간주되므로 사용자가 만든 콘텐츠는 영향을 받지 않습니다.

**OneDrive**:

사용자가 조직을 떠나면 보존 정책의 적용을 받거나 보존 레이블이 있는 모든 파일은 정책 또는 레이블에 지정된 보존 기간 동안 보존 설정의 적용을 받습니다. 그 시간 동안 모든 공유 액세스가 계속 작동하고 콘텐츠 검색 및 eDiscovery를 통해 콘텐츠를 계속 검색할 수 있습니다. 

보존 기간이 만료되고 보존 설정에 삭제 작업이 포함된 경우 콘텐츠는 사이트 모음 휴지통으로 이동하고 관리자를 제외한 누구도 액세스할 수 없습니다.

## <a name="configuration-guidance"></a>구성 지침

Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.

Exchange의 보존 정책 또는 보존 레이블을 구성할 준비가 되면 다음 지침을 참조하세요.
- [보존 정책 만들기 및 구성하기](create-retention-policies.md)
- [보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)
- [보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)
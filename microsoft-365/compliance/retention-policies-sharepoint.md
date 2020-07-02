---
title: SharePoint 및 OneDrive의 보존 정책에 대한 자세한 정보
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: SharePoint 및 OneDrive에 적용되는 보존 정책에 대한 자세한 정보
ms.openlocfilehash: e7a265d39b3cca2ffb9c403cf2c87f287a9325b2
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016249"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive의 보존 정책에 대한 자세한 정보

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

이 문서의 정보는 SharePoint 및 OneDrive와 관련된 정보를 포함하므로 [보존 정책에 대한 자세한 정보](retention-policies.md)를 보완합니다.

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>보존 정책이 SharePoint 및 OneDrive와 작동하는 방식

보존 정책이 사이트 모음 수준에서 적용됩니다. 보존 정책에 SharePoint 사이트 모음 또는 OneDrive 계정을 포함할 시 보존 라이브러리가 없는 경우 보존 라이브러리가 새로 생성됩니다. 사이트 모음의 최상위 사이트에 있는 **사이트 콘텐츠** 페이지에서 이 라이브러리를 볼 수 있습니다. 자료 보존 라이브러리는 사이트 모음 관리자만 볼 수 있기 때문에 대부분의 사용자는 볼 수 없습니다.
  
사용자가 보존 정책을 따르는 사이트의 콘텐츠를 변경하거나 삭제하려고 하면 보존 정책은 먼저 정책이 적용된 이후 콘텐츠가 변경되었는지 여부를 확인합니다. 보존 정책이 적용되고 처음 변경한 경우라면 보존 정책은 해당 콘텐츠를 자료 보존 라이브러리로 복사하고 해당 사용자가 원본 콘텐츠를 변경하거나 삭제할 수 있도록 허용합니다. 사이트 모음의 콘텐츠는 보존 정책에 사용된 필터와 일치하지 않더라도 자료 보존 라이브러리로 복사될 수 있습니다.
  
타이머 작업이 주기적으로 자료 보존 라이브러리를 정리합니다. 타이머 작업은 자료 보존 라이브러리의 모든 콘텐츠를 사이트의 보존 정책에서 사용하는 모든 쿼리와 비교합니다. 구성된 보존 기간보다 오래된 콘텐츠는 자료 보존 라이브러리에서 삭제되고, 아직 남아 있는 경우, 원본 위치에서도 삭제됩니다. 이 타이머 작업은 7일마다 실행되며 이는 콘텐츠를 삭제하는 데 최대 7일이 걸릴 수 있음을 의미합니다.
  
이러한 동작은 보존 정책이 적용될 때 존재하는 콘텐츠에 적용됩니다. 또한 정책에 포함된 후 사이트 모음에 만들거나 추가된 새 콘텐츠는 삭제 후에도 유지됩니다. 그렇지만 새 콘텐츠는 처음 편집할 때는 자료 보존 라이브러리에 복사되지 않고 삭제되었을 때만 복사됩니다. 파일의 모든 버전을 보존하려면, [버전 관리](#how-a-retention-policy-works-with-document-versions-in-a-site-collection)를 설정해야 합니다.
  
사용자가 보존 정책이 적용되는 라이브러리, 목록, 폴더 또는 사이트를 삭제하려고 하면 오류가 표시됩니다. 사용자는 먼저 정책이 적용되는 폴더의 모든 파일을 이동하거나 삭제하는 경우에 폴더를 삭제할 수 있습니다. 또한 자료 보존 라이브러리는 보존 정책을 만들 때가 아닌, 이 단계에서 만들어집니다. 즉, 정책을 테스트하려면 먼저 보존 정책이 적용되는 사이트에서 문서를 편집하거나 삭제한 다음, 자료 보존 라이브러리로 이동하여 보존된 복사본을 확인해야 합니다.
  
보존 정책을 OneDrive 계정 또는 SharePoint 사이트에 할당한 후 콘텐츠가 사용하는 경로는 보존 정책이 보존 및 삭제, 유지 또는 삭제 만 가능한지 여부에 따라 다릅니다.

보존 정책이 보존 및 삭제되는 경우:

![SharePoint 및 OneDrive의 콘텐츠 수명 주기 다이어그램](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. 보존 기간 내에 **콘텐츠가 수정되거나 삭제되면** 보존 정책이 적용된 시점과 동일한 원본 콘텐츠의 사본이 자료 보존 라이브러리에 생성됩니다. 여기에서 타이머 작업이 보존 기간이 만료된 항목을 식별합니다. 해당 항목은 2단계 휴지통으로 이동되고, 93일이 지나면 영구적으로 삭제됩니다. 2단계 휴지통은 최종 사용자에게 표시되지 않습니다(1단계 휴지통에만 해당). 하지만 사이트 모음 관리자는 해당 사이트에서 콘텐츠를 보고 복원할 수 있습니다.

    > [!NOTE]
    > 실수로 데이터가 손실되는 것을 방지하기 위해 더 이상 보존 라이브러리의 콘텐츠를 영구적으로 삭제하지 않습니다. 대신 휴지통에서 콘텐츠를 영구적으로 삭제합니다. 이제는 보존 라이브러리의 모든 콘텐츠가 2단계 휴지통을 거칩니다.
    
2. 보존 기간 동안 **콘텐츠가 수정되거나 삭제되지 않으면** 타이머 작업은 해당 콘텐츠를 보존 기간의 종료 시점에 1단계 휴지통으로 이동시킵니다. 여기에서 사용자가 콘텐츠를 삭제하거나 휴지통을 비우면 문서가 2단계 휴지통으로 이동됩니다. 1단계 휴지통과 2단계 휴지통을 포함하여 총 93일간의 보존 기간이 적용됩니다. 93일이 지나면 1단계 휴지통 또는 2단계 휴지통에서 문서가 영구적으로 삭제됩니다. 휴지통이 인덱싱되지 않으므로 검색할 수 없습니다. 따라서 eDiscovery 검색에서 보류할 휴지통 콘텐츠를 찾을 수 없습니다.

보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.

#### <a name="content-paths-for-retain-only-retention-policy"></a>보유 전용 보존 정책의 컨텐츠 경로

1. 보존 기간 동안 **컨텐츠가 수정되거나 삭제된 경우**: 보존 라이브러리의 사본이 2단계로 이동될 때 원본 문서의 사본이 보존 라이브러리에 작성되고 보존 기간이 끝날 때까지 보존됩니다. 휴지통이며 93일 후에 영구적으로 삭제됩니다.

2. 보존 기간 동안 **컨텐츠가 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 문서는 원래 위치에 남아 있습니다.

#### <a name="content-paths-for-delete-only-retention-policy"></a>삭제 전용 보존 정책의 컨텐츠 경로

1. 구성된 기간 동안 **컨텐츠가 삭제되는 경우**, 해당 문서는 1단계 휴지통으로 이동됩니다. 여기에서 사용자가 문서를 삭제하거나 휴지통을 비우면 문서가 2단계 휴지통으로 이동됩니다. 1단계 휴지통과 2단계 휴지통을 포함하여 총 93일 간의 보존 기간이 적용됩니다. 93일이 지나면 1단계 휴지통 또는 2단계 휴지통에서 문서가 영구적으로 삭제됩니다. 구성된 기간 동안 컨텐츠가 수정되면 구성된 기간이 지난 후 동일한 삭제 경로를 따릅니다.

2. 구성된 기간 동안 **컨텐츠가 삭제되지 않는 경우**, 보존 정책에 구성된 기간이 끝나는 시점에 문서가 1단계 휴지통으로 이동됩니다. 여기에서 사용자가 문서를 삭제하거나 휴지통을 비우면 문서가 2단계 휴지통으로 이동됩니다. 1단계 휴지통과 2단계 휴지통을 포함하여 총 93일 간의 보존 기간이 적용됩니다. 93일이 지나면 1단계 휴지통 또는 2단계 휴지통에서 문서가 영구적으로 삭제됩니다. 휴지통이 인덱싱되지 않으므로 검색할 수 없습니다. 따라서 eDiscovery 검색에서 보류할 휴지통 콘텐츠를 찾을 수 없습니다.
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>보존 정책이 사이트 모음의 문서 버전과 작동하는 방식

버전 관리는 SharePoint 및 OneDrive의 모든 문서 라이브러리의 기능입니다. 기본적으로 버전 관리에서는 최소 500개의 주요 버전이 유지되지만이 제한을 늘릴 수 있습니다. 자세한 내용은 [목록 또는 라이브러리의 버전 관리 설정 및 구성](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)을 참조하세요.
  
보존 전용 정책은 SharePoint 사이트 모음 또는 OneDrive 계정에 있는 문서의 모든 버전을 보존합니다. 보류 또는 보존 전용 정책이 적용되는 문서를 처음 편집하면 원본 문서의 버전이 자료 보존 라이브러리에 복사됩니다. 버전 관리가 설정된 경우, 보류 또는 보존 정책이 적용되는 문서가 삭제될 때 버전 관리 기능을 사용하도록 설정한 경우, 모든 버전이 자료 보존 라이브러리에 복사됩니다. 보존 보류 라이브러리의 각 문서 버전은 자체 보존 기간이 있는 별도의 항목으로 존재합니다.
  
- If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.
    
- If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.

> [!NOTE]
> 보존된 버전의 SharePoint 및 OneDrive 문서는 eDiscovery 도구로 검색할 수 없습니다.

## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 

**SharePoint**:

사용자가 조직을 떠나는 경우, 사용자의 사서함 또는 OneDrive 계정과 달리, SharePoint는 공동 작업 환경으로 간주되므로 사용자가 만든 콘텐츠는 영향을 받지 않습니다.

**OneDrive**:

사용자가 조직을 떠나는 경우, 보존 정책이 적용되거나 보존 레이블이 포함된 모든 파일은 정책이나 레이블 기간 동안 유지됩니다. 이 기간 동안 모든 공유 액세스는 계속 작동합니다. 보존 기간이 만료되면 콘텐츠가 사이트 모음 휴지통으로 이동하고 관리자를 제외한 모든 사용자가 액세스할 수 없습니다. 문서가 보존 정책에서 레코드로 표시되는 경우 보존 기간이 종료될 때까지 해당 문서는 삭제되지 않으며 그 후에는 콘텐츠가 영구적으로 삭제됩니다. 

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive에 보존 정책을 구성하는 방법

[보존 정책 만들기](create-retention-policies.md) 및 구성 지침에 따라 마법사의 **위치 선택** 페이지에서 다음 옵션 중 하나를 선택합니다.

- **Exchange 전자 메일, 공용 폴더, Office 365 그룹, OneDrive 및 SharePoint 문서에 있는 콘텐츠에만 정책 적용하기**

- **특정 위치를 직접 선택** > **SharePoint 사이트**, **OneDrive 계정** 또는 **Office 365 그룹**

**SharePoint 사이트** 위치를 선택할 때 보존 정책을 사용하여 SharePoint 커뮤니케이션 사이트, Office 365 그룹에서 연결되지 않는 팀 사이트 및 클래식 사이트에서 콘텐츠를 보존할 수 있습니다. Office 365 그룹에서 연결된 팀 사이트는 이 옵션에서 지원되지 않으며 대신 해당 그룹의 사서함, 사이트 및 파일에 있는 콘텐츠에 적용되는 **Office 365 그룹** 위치를 사용합니다. 

SharePoint 사이트의 위치를 지정하는 경우, 사이트에 액세스할 수 있는 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정하는 시점에 유효성 검사가 수행되지 않습니다. 그러나 사이트를 색인화해야 하며 마법사 종료 시 지정한 사이트가 존재하는지 검사합니다. 

이 검사에 실패하는 경우, 입력한 URL에 대한 유효성 검사에 실패했다는 메시지가 표시되고 유효성 검사가 통과한 후에 마법사에서 보존 정책이 만들어집니다. 이 메시지가 표시되는 경우 마법사에서 돌아가서 URL을 변경하거나 사이트를 제거합니다.

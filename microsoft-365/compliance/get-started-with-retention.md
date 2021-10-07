---
title: 보존 정책 및 보존 레이블 시작하기
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
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 조직의 데이터를 관리하도록 보존 정책 및 보존 레이블 구현을 시작할 준비가 되었지만, 어디서부터 시작해야 할지 모르겠나요? 시작을 위한 몇 가지 실용적인 지침을 읽어보세요.
ms.openlocfilehash: 3154388eaf1c677cec00782642de6f83819d0665
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195596"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블 시작하기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

보관해야 할 콘텐츠를 보존하고 보관할 필요 없는 콘텐츠를 삭제하여 조직의 데이터 관리를 시작할 준비가 되었나요? 시작을 위해 다음 지침을 사용하세요.

1. Microsoft 365의 **보존 방식을 이해** 한 다음 보존 정책이나 보존 레이블을 사용해야 하는지 또는 조합을 사용해야 하는지 식별합니다. [보존에 대해 알아보기](retention.md)

2. 조직 정책 또는 업계 규정에 필요한 **보존 설정 및 작업을 식별** 합니다.
    
    이 평가의 일환으로 [레코드 관리](records-management.md)를 사용할지 여부를 결정합니다.

3. 사용자가 식별한 보존 설정 및 작업을 기반으로 **보존 정책 및 보존 레이블을 만듭니다**.
    
    보존 레이블의 경우 [파일 계획](file-plan-manager.md)을 사용하여 스프레드시트에서 보존 레이블을 정의하고 구체화하는 것이 유용할 수 있습니다. 그런 다음 해당 스프레드시트를 가져와 레이블을 만듭니다.
    
3. **보존 레이블을 게시하고 적용합니다**. 보존 정책은 "설정하고 잊는" 구성을 위해 설계되었지만, 보존 레이블은 여러 정책에서 사용될 수 있고 사용자 워크플로에 통합될 수 있는 재사용 가능한 빌딩 블록입니다. 보존 레이블이 사용되는 방식을 식별하는 데 도움이 되는 [일반적인 시나리오](#common-scenarios-for-retention-policies-and-retention-labels) 목록을 참조세요. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블에 대한 구독 및 라이선스 요구 사항

다양한 구독이 보존 정책 및 보존 레이블을 지원하며 사용자에 대한 라이선스 요구 사항은 사용하는 기능에 따라 다릅니다.

사용자에게 Microsoft 365 규정 준수 기능을 사용하도록 라이선스를 부여하는 옵션을 보려면 [보안 및 규정 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조하세요. 보존에 대한 자세한 내용은 기능 수준 라이선스 요구 사항에 대한 [정보 거버넌스](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 섹션 및 관련 PDF 다운로드를 참조하세요.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한

보존 정책과 보존 레이블을 만들고 관리할 규정 준수 팀의 구성원에게는 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에 대한 권한이 필요합니다. 기본적으로 테넌트 관리자(전역 관리자)는 이 위치에 액세스할 수 있으며, 규정 준수 책임자와 기타 사용자에게 테넌트 관리자의 모든 권한을 부여하지는 않으면서 액세스 권한을 부여할 수 있습니다. 이 제한적 관리를 위한 권한을 부여하기 위해서는 사용자를 **규정 준수 관리자** 관리 역할 그룹에 추가할 것을 권장합니다.

이 기본 역할을 사용하는 대신 새 역할 그룹을 만들고 이 그룹에 **보존 관리** 역할을 추가할 수 있습니다. 읽기 전용 역할의 경우 **보기 전용 보존 관리** 를 사용합니다. 

기본 역할에 사용자를 추가하거나 고유의 역할 그룹을 만드는 방법에 대한 지침은 [Office 365 규정 준수 센터의 사용 권한](microsoft-365-compliance-center-permissions.md)을 참조하세요.

해당 권한은 보존 정책 및 보존 레이블을 만들고 구성하고 적용하는 경우에만 필요합니다. 해당 정책 및 레이블을 구성하는 사용자는 콘텐츠에 대한 액세스 권한이 필요하지 않습니다.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블에 대한 일반적인 시나리오

다음 표를 사용하여 보존 정책 및 보존 레이블이 지원하는 보존 시나리오에 비즈니스 요구 사항을 매핑할 수 있습니다.

|필요|설명서|
|----------------|---------------|
|Microsoft 365 서비스별로 효율적으로 보관 및 삭제 작업 설정 <br />-  Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 그룹 <br />- 비즈니스용 Skype  <br />- Microsoft Teams <br />- Yammer 네트워크 |[보존 정책 만들기 및 구성하기](create-retention-policies.md)|
|관리자와 사용자가 다음 문서 및 전자 메일에 대한 보존 및 삭제 동작을 수동으로 적용하도록 허용합니다. <br />-  SharePoint <br />- OneDrive <br />- Outlook 및 웹용 Outlook|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|사이트 관리자가 SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 및 삭제 동작을 설정하도록 허용|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|사용자가 Outlook 규칙을 사용하여 자동으로 전자 메일에 보존 및 삭제 동작을 적용할 수 있도록 허용|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|관리자가 문서를 이해하기 위해 보존 및 삭제 작업을 적용할 수 있도록 합니다 .이는 SharePoint 라이브러리의 식별된 문서에 자동으로 적용됩니다.|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|문서 및 전자 메일에 대한 보존 및 삭제 동작을 자동으로 적용 |[보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)|
|다음과 같은 이벤트가 발생할 때 보존 기간 시작:  <br />- 직원 퇴사 <br />- 계약 만료 <br />- 제품 수명 주기 종료| [이벤트가 발생할 때 보존 시작하기](event-driven-retention.md)|
|규정 요구 사항을 충족하거나 로그 관리자로부터 안전을 보호하는 데 도움이 되는 정책 변경 제한| [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 유지 잠금 사용](retention-preservation-lock.md)
|보존 기간 종료 시 콘텐츠를 삭제하기 전에 누군가가 검토하고 승인하도록 하세요.|[처리 검토](disposition.md#disposition-reviews) |
| 항목에 대한 보존 및 삭제 설정이 적용되는 방법과 위치 모니터링 | [보존 레이블 모니터링](retention.md#monitoring-retention-labels) |
|문서 및 전자 메일에 대한 단일 레코드 관리 솔루션 사용 |[레코드 관리에 대한 자세한 정보](records-management.md) |

레코드 관리에 보존 레이블을 사용하는 경우 콘텐츠를 레코드로 표시하는 보존 레이블에 고유한 추가 시나리오가 있습니다. [레코드 관리를 위한 일반적인 시나리오](get-started-with-records-management.md#common-scenarios-for-records-management)를 참조하세요.

## <a name="end-user-documentation-for-retention"></a>보존에 대한 최종 사용자 설명서

대부분 보존 정책은 사용자와의 상호 작용 없이 백그라운드에서 조용히 드러나지 않게 작동하므로 사용자를 위한 문서가 거의 필요하지 않습니다. Teams 보존 정책은 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)로 가는 링크가 포함된 메시지가 삭제되는 경우 사용자에게 공지됩니다.

Microsoft 365 앱의 경우 보전 레이블이 UI에 표시되므로 프로덕션 네트워크에 해당 레이블을 배포하기 전에 최종 사용자와 지원 센터용 지침을 제공하세요. 사용자가 SharePoint 및 OneDrive의 보존 레이블을 적용할 수 있도록 하려면 [SharePoint 또는 OneDrive의 파일에 보존 레이블 적용](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)을 참조하세요.

그러나, 가장 효과적인 최종 사용자 문서는 선택한 보존 레이블 이름 및 구성에 대한 사용자 지정 안내사항 및 지침입니다. 사용자 교육을 지원하는 데 사용할 수 있는 다음 페이지 및 다운로드를 참조하세요. [데이터 보존 레이블에 대한 최종 사용자 교육](https://microsoft.github.io/ComplianceCxE/enduser/retention/).
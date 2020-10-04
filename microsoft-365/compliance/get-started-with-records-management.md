---
title: Microsoft 365에서 레코드 관리 시작
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
description: 법률, 비즈니스 또는 규제 의무에 대한 높은 가치의 콘텐츠를 관리하는 Microsoft 365의 레코드 관리 솔루션이 필요하지만 어디서 시작해야 하나요? 시작을 도와주는 실질적인 지침을 참조하세요.
ms.openlocfilehash: fd3e3368b7a23cb31a8df4953268576de2419f89
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333854"
---
# <a name="get-started-with-records-management"></a>레코드 관리 시작

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 365에서 레코드 관리 솔루션을 사용하여 법률, 비즈니스 또는 규제 의무에 대한 조직의 높은 가치의 콘텐츠 관리를 시작할 준비가 되었나요? 시작하려면 다음과 같은 고급 지침을 사용하세요.

1. **레코드 관리 솔루션**과 문서 및 전자 메일을 레코드로 선언할 때 허용되거나 차단되는 작업을 이해합니다. [레코드 관리에 대해 자세히 알아보세요.](records-management.md) 

2. 레코드를 선언하는 데 보존 레이블이 사용되므로 **보존 레이블과 SharePoint 및 Exchange에 대한 보존 작동 방식을 이해합니다.** [보존 정책 및 보존 레이블에 대해 자세히 알아보세요.](retention.md)

3. 기존 계획이 있는 경우 **해당 계획을 가져와** [보존 설정 및 작업에 대한 파일 계획을 만들거나](file-plan-manager.md#import-retention-labels-into-your-file-plan ) [레코드를 선언하는 새 보존 레이블을 만듭니다.](declare-records.md)

4. **보존 레이블을 게시하고 적용합니다.** 보존 레이블은 여러 정책에서 사용될 수 있으며 사용자 워크플로에 통합될 수 있는 재사용 가능한 빌딩 블록입니다. 
    
    - [보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)
    - [보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>레코드 관리에 대한 구독 및 라이선스 요구 사항

다양한 구독 지원 레코드 관리 및 사용자에 대한 라이선스 요구 사항은 사용하는 기능에 따라 다릅니다.

사용자에게 Microsoft 365 규정 준수 기능을 사용하도록 라이선스를 부여하는 옵션을 보려면 [보안 및 규정 준수에 대한 Microsoft 365 라이선스 지침](https://aka.ms/ComplianceSD)을 참조하세요. 레코드 관리에 대한 자세한 내용은 기능 수준 라이선스 요구 사항에 대한 [레코드 관리](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) 섹션 및 관련 PDF 또는 Excel 다운로드를 참조하세요.

## <a name="permissions-required-for-records-management"></a>레코드 관리에 필요한 사용 권한

레코드 관리에 대해 책임이 있는 규정 준수 팀의 구성원에게는 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에 대한 권한이 필요합니다. 기본적으로 테넌트 관리자(전역 관리자)는 이 위치에 액세스할 수 있으며 규정 준수 책임자와 기타 사용자에게 테넌트 관리자의 모든 권한을 부여하지 않고도 액세스 권한을 부여할 수 있습니다. 해당 제한적 관리에 대해 권한을 부여하려면 **RecordManagement** 역할을 부여하는 **레코드 관리**의 관리 역할 그룹에 사용자를 추가하는 것이 좋습니다.

이 역할 그룹에 포함된 권한에는 [처리 검토 및 확인](disposition.md)에 대해 필요한 권한이 포함되어 있지 않으며 전역 관리자에게는 기본적으로 해당 권한이 없습니다. 처리를 관리하려면 사용자 지정 역할 그룹을 만들거나 이 역할(예: **준수 관리자**)을 포함하는 기본 역할 그룹을 사용하여 **처리 관리** 역할을 사용합니다.

해당 역할 그룹 및 역할에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center#roles-in-the-security--compliance-center)을 참조하세요.

사용자에게 역할 그룹을 추가하고 역할을 할당하는 방법에 대한 지침은 [사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)를 참조하세요.

해당 권한은 레코드를 선언하고 처리를 관리하는 보존 레이블을 만들고 구성하고 적용하는 경우에만 필요합니다. 해당 레이블을 구성하는 사용자는 콘텐츠에 대한 액세스 권한이 필요하지 않습니다.

## <a name="common-scenarios-for-records-management"></a>레코드 관리에 대한 일반적인 시나리오

다음 표를 사용하여 레코드 관리가 지원하는 시나리오에 비즈니스 요구 사항을 매핑할 수 있습니다.

> [!NOTE]
> 레코드 관리는 보존 레이블을 사용하여 항목을 레코드로 표시하기 때문에 이 표의 여러 시나리오는 [보존 정책 및 보존 레이블에 대한 일반적인 시나리오](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels)로 나열됩니다.

|필요|설명서|
|----------------|---------------|
|레코드 선언 |[보존 레이블을 사용하여 레코드 선언](declare-records.md)|
|레코드 업데이트 |[레코드 버전 관리를 사용하여 SharePoint 또는 OneDrive에 저장된 레코드 업데이트](record-versioning.md)|
|관리자와 사용자가 다음 문서 및 전자 메일에 대한 보존 및 삭제 동작을 수동으로 적용하도록 허용합니다. <br />-  SharePoint <br />- OneDrive <br />- Outlook 및 웹용 Outlook|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|사이트 관리자가 SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 및 삭제 동작을 설정하도록 허용|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|사용자가 Outlook 규칙을 사용하여 자동으로 전자 메일에 보존 및 삭제 동작을 적용할 수 있도록 허용|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|관리자가 문서를 이해하기 위해 보존 및 삭제 작업을 적용할 수 있도록 합니다 .이는 SharePoint 라이브러리의 식별된 문서에 자동으로 적용됩니다.|[보존 레이블을 만들어 앱에 적용합니다](create-apply-retention-labels.md)|
|문서 및 전자 메일에 대한 보존 및 삭제 동작을 자동으로 적용 |[보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)|
|다음과 같은 이벤트가 발생할 때 보존 기간 시작:  <br />- 직원 퇴사 <br />- 계약 만료 <br />- 제품 수명 주기 종료| [이벤트가 발생할 때 보존 시작하기](event-driven-retention.md)|
|SharePoint에서 다른 문서 유형 수명 주기 관리| [보존 레이블로 SharePoint에 저장된 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)|
|보존 기간 종료 시 콘텐츠를 영구적으로 삭제하기 전에 누군가가 검토하고 승인하도록 하세요.|[처리 검토](disposition.md#disposition-reviews) |
|보존 기간 종료시 영구적으로 삭제되는 콘텐츠에 대한 처리 증명을 보유합니다.|[콘텐츠 처분](disposition.md#disposition-of-records) |
|항목에 대한 보존 및 삭제 설정이 적용되는 방법과 위치 모니터링 | [보존 레이블 모니터링](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>레코드에 대한 최종 사용자 설명서

레코드 관리에 사용되는 보존 레이블에는 Microsoft 365 앱에 UI 상태가 있습니다. 프로덕션 네트워크에 보존 레이블을 배포하기 전에 최종 사용자와 지원 센터에 대한 지침을 제공하세요.

가장 효과적인 최종 사용자 문서는 선택한 보존 레이블 이름 및 구성에 대한 사용자 지정 안내사항 및 지침입니다. 그러나 기본 지침으로 다음 정보를 사용할 수 있습니다.

- [수동으로 보존 레이블 적용하기](create-apply-retention-labels.md#manually-apply-retention-labels)

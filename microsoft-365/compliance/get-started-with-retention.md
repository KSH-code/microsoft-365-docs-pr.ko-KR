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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 조직의 데이터를 관리하도록 보존 정책 및 보존 레이블 구현을 시작할 준비가 되었지만, 어디서부터 시작해야 할지 모르겠나요? 시작을 도와주는 실질적인 지침을 읽어 보세요.
ms.openlocfilehash: b390e4594d97e96eadac9541429a838abe006a3f
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560765"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블 시작하기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

보관해야 할 콘텐츠를 보존하고 보관할 필요 없는 콘텐츠를 삭제하여 조직의 데이터 관리를 시작할 준비가 되었나요? 시작하려면 다음과 같은 개괄적인 지침을 사용하세요.

1. Microsoft 365의 **보존 방식을 이해**한 다음 보존 정책이나 보존 레이블을 사용해야 하는지 또는 조합을 사용해야 하는지 식별합니다. [보존에 대해 알아보기](retention.md)

2. 조직 정책 또는 업계 규정에 필요한 **보존 설정 및 작업을 식별**합니다.
    
    이 평가의 일환으로 [레코드 관리](records-management.md)를 사용할지 여부를 결정합니다.

3. 사용자가 식별한 보존 설정 및 작업을 기반으로 **보존 정책 및 보존 레이블을 만듭니다**.
    
    보존 레이블의 경우, [파일 계획](file-plan-manager.md)을 사용하여 스프레드시트에서 보존 레이블을 정의하고 세분화하는 것이 유용할 수 있습니다. 그런 다음 해당 스프레드시트를 가져와 레이블을 만듭니다.
    
3. **보존 레이블을 게시하고 적용합니다**. 보존 정책은 "설정하고 잊는" 구성을 위해 설계되었지만, 보존 레이블은 여러 정책에서 사용될 수 있고 사용자 워크플로에 통합될 수 있는 재사용 가능한 빌딩 블록입니다. 보존 레이블이 사용되는 방식을 식별하는 데 도움이 되는 [일반적인 시나리오](#common-scenarios-for-retention-policies-and-retention-labels) 목록을 참조세요. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블에 대한 구독 및 라이선스 요구 사항

다양한 구독이 보존 정책 및 보존 레이블을 지원하며 사용자에 대한 라이선스 요구 사항은 사용하는 기능에 따라 다릅니다.

사용자에게 Microsoft 365 규정 준수 기능을 사용하도록 라이선스를 부여하는 옵션을 보려면 [보안 및 규정 준수에 대한 Microsoft 365 라이선스 지침](https://aka.ms/ComplianceSD)을 참조하세요. 보존에 대한 자세한 내용은 기능 수준 라이선스 요구 사항에 대한 [정보 거버넌스](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 섹션 및 관련 PDF 또는 Excel 다운로드를 참조하세요.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한

보존 정책과 보존 레이블을 만들고 관리할 규정 준수 팀의 구성원에게는 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에 대한 권한이 필요합니다. 기본적으로 테넌트 관리자(전역 관리자)는 이 위치에 액세스할 수 있으며, 규정 준수 책임자와 기타 사용자에게 테넌트 관리자의 모든 권한을 부여하지는 않으면서 액세스 권한을 부여할 수 있습니다. 이 제한적 관리를 위한 권한을 부여하기 위해서는 사용자를 **규정 준수 관리자** 관리 역할 그룹에 추가할 것을 권장합니다. 지침은 [사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)를 참조하세요.

이러한 권한은 보존 정책을 생성하고 적용할 때만 필요합니다. 보존 정책을 구성하는 사용자는 콘텐츠에 액세스할 필요가 없습니다.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블에 대한 일반적인 시나리오

다음 표를 사용하여 보존 정책 및 보존 레이블이 지원하는 보존 시나리오에 비즈니스 요구 사항을 매핑할 수 있습니다.

|필요|설명서|
|----------------|---------------|
|조직 또는 Microsoft 365 서비스별로 효율적으로 보관 및 삭제 작업 설정 <br />-  Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 그룹 <br />- 비즈니스용 Skype  <br />- Microsoft Teams  |[보존 정책 만들기 및 구성하기](create-retention-policies.md)|
|관리자와 사용자가 문서 및 전자 메일에 대한 보존 및 삭제 동작 집합을 수동으로 적용하도록 허용: <br />-  SharePoint <br />- OneDrive <br />- Outlook 및 웹용 Outlook|[보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)|
|사이트 관리자가 SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 레이블을 설정하도록 허용|[보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)|
|사용자가 Outlook 규칙을 사용하여 자동으로 전자 메일에 보존 레이블을 적용할 수 있도록 허용|[보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)|
|문서 및 전자 메일에 대한 보존 및 삭제 동작 집합을 자동으로 적용 |[보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)|
|다음과 같은 이벤트가 발생할 때 보존 기간 시작:  <br />- 직원 퇴사 <br />- 계약 만료 <br />- 제품 수명 주기 종료| [이벤트가 발생할 때 보존 시작하기](event-driven-retention.md)|
|SharePoint에서 다른 문서 유형 수명 주기 관리| [보존 레이블로 SharePoint에 저장된 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)|
|문서 및 전자 메일에 단일 레코드 관리 솔루션 사용 |[Microsoft 365의 레코드 관리하기](records-management.md) |
|SEC 규칙 17a-4 준수|[SEC Rule 17a-4를 준수하기 위해 Exchange Online과 보안 및 준수 센터 사용하기](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|보존 기간 종료 시 콘텐츠를 삭제하기 전에 누군가가 검토하고 승인하도록 하세요.|[처리 검토](disposition.md#disposition-reviews) |
|보존 기간 종료시 삭제되는 콘텐츠에 대한 처리 증명을 보유합니다.|[콘텐츠 처분](disposition.md#disposition-of-records) |

## <a name="end-user-documentation-for-retention-labels"></a>보존 레이블에 대한 최종 사용자 설명서

보존 정책과 달리 보존 레이블에는 Microsoft 365 앱에 UI가 있습니다. 프로덕션 네트워크에 보존 레이블을 배포하기 전에 최종 사용자와 지원 센터에 대한 지침을 제공하세요.

가장 효과적인 최종 사용자 문서는 선택한 보존 레이블 이름 및 구성에 대한 사용자 지정 안내사항 및 지침입니다. 그러나 기본 지침으로 다음 정보를 사용할 수 있습니다.

- [수동으로 보존 레이블 적용하기](create-apply-retention-labels.md#manually-apply-retention-labels)

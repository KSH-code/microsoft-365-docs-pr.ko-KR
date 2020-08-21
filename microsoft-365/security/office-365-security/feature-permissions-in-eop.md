---
title: EOP의 기능 사용 권한
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 독립 실행형 Exchange Online Protection의 작업에 필요한 권한에 대해 알아보기
ms.openlocfilehash: f9c0f0549ba5a0a65fa3bbe3af1afbfddc6e735c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826628"
---
# <a name="permissions-in-standalone-eop"></a>독립 실행형 EOP의 사용 권한

Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 사용 권한 모델을 사용하여 관리자에게 사용 권한을 쉽게 부여합니다. 독립 실행형 EOP에서 사용 권한 기능을 사용하여 신속하게 새 조직을 계획하고 실행할 수 있습니다.

사용자에게 사용 권한을 부여하려면 [EOP에서 관리자 역할 그룹 관리를 참조하십시오.](manage-admin-role-group-permissions-in-eop.md)

Microsoft 365의 사용 권한에 대한 자세한 내용은 관리자 [역할을 참고하십시오.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

## <a name="role-based-permissions"></a>역할 기반 권한

사용자에게 부여되는 관리자 권한은 관리 역할을 기반으로 합니다. 관리 역할은 지정된 일집합의 작업에 사용할 수 있는 cmdlet을 정의합니다. EAC(Exchange 관리 센터) 및 독립 실행형 EOP PowerShell은 모두 cmdlet을 사용하므로 cmdlet에 액세스 권한을 부여하면 EAC 또는 독립 실행형 EOP PowerShell에서 관련 작업을 수행할 수 있는 권한이 사용자에게 부여됩니다. 예를 들어 Mail Recipients 역할은 메일 사용자를 수정하는 데 필요한 cmdlet을 정의합니다.

독립 실행형 EOP에서는 사용할 수 있는 관리 역할 유형이 관리 역할이 있습니다(최종 사용자 역할 또는 역할 할당 정책은 없음).

## <a name="role-groups"></a>역할 그룹

사용자에게 더 쉽게 역할을 할당하기 위해 독립 실행형 EOP는 역할 그룹을 사용합니다. 관리 역할은 역할 그룹에 할당되며 역할 그룹 구성원은 해당 역할과 연관된 사용 권한을 얻습니다. 즉, 관리 역할은 사용자에게 직접 할당되지 않습니다. 역할 그룹에 할당됩니다. 이 모델을 사용하면 여러 역할을 여러 역할 그룹 구성원에게 한 번에 할당할 수 있습니다. 역할 그룹 구성원은 메일 사용자, 메일 사용이 가능한 보안 그룹, Microsoft 365 관리 센터의 사용자 및 기타 역할 그룹이 될 수 있습니다.

다음 그림은 사용자, 역할 그룹 및 역할 간의 관계를 보여줍니다.

![역할, 역할 그룹 및 구성원 관계](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

독립 실행형 EOP에서 사용할 수 있는 역할 그룹은 다음 표에 설명되어 있습니다.

****

|역할 그룹|설명|할당된 기본 역할|
|---|---|---|
|ComplianceManagement|구독에 DLP 기능이 있는 경우 DLP(데이터 손실 방지)를 포함하여 조직 내의 준수 설정을 구성하고 관리합니다. <br/><br/> Azure AD에서 [규정 준수 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) 역할의 구성원에게 이 역할 그룹의 권한이 자동으로 적용됩니다.|감사 로그 <br/><br/> 준수 관리 <br/><br/> 정보 권한 관리 <br/><br/> 보존 관리 <br/><br/> 보기 전용 감사 로그 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 받는 사람|
|ContentExplorerContentViewer|사용되지 않습니다.|데이터 분류 콘텐츠 뷰어|
|ContentExplorerListViewer|사용되지 않습니다.|데이터 분류 목록 뷰어|
|HelpDesk|메일 사용자 보기 및 관리|암호 재설정 <br/><br/> 사용자 옵션 <br/><br/> 보기 전용 받는 사람|
|HygieneManagement|보호 기능(스팸 방지, 맬웨어 방지 등)을 관리합니다.|전송 예리 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 받는 사람|
|MailFlowAdministrator|허용 도메인 및 커넥터 보기 및 관리|원격 및 허용 도메인 <br/><br/> 보기 전용 받는 사람|
|OrganizationManagement|전체 조직에 대한 관리자 액세스 권한 및 거의 모든 작업을 수행할 수 있어야 합니다. <br/><br/> Azure AD에서 [전역 관리자 역할의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 구성원에게는 이 역할 그룹의 권한이 자동으로 적용됩니다. <br/><br/> **중요**: OrganizationManagement 역할 그룹이 강력한 역할이므로 조직 수준 관리 작업을 수행하는 사용자만 이 역할 그룹의 구성원이어야 합니다.|맬웨어 방지 <br/><br/> 스팸 방지 <br/><br/> 감사 로그 <br/><br/> 준수 관리자 <br/><br/> 동적 메일 그룹 <br/><br/> 정보 권한 관리 <br/><br/> 메일 받는 사람 만들기 <br/><br/> 메일 받는 사람 <br/><br/> 메시지 추적 <br/><br/> 마이그레이션 <br/><br/> 조직 클라이언트 액세스 <br/><br/> 조직 구성 <br/><br/> 조직 전송 설정 <br/><br/> 격리 <br/><br/> 받는 사람 정책 <br/><br/> 원격 및 허용 도메인 <br/><br/> 암호 재설정 <br/><br/> 보존 관리 <br/><br/> 역할 관리 <br/><br/> 보안 관리자 <br/><br/> 보안 그룹 만들기 및 멤버 자격 <br/><br/> 보안 읽기 권한자 <br/><br/> 민감도 레이블 관리자 <br/><br/> 감독 <br/><br/> 전송 예리 <br/><br/> 전송 규칙 <br/><br/> 사용자 옵션 <br/><br/> 맬웨어 방지 보기 <br/><br/> 보기 전용 스팸 방지 <br/><br/> 보기 전용 감사 로그 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 격리 <br/><br/> 보기 전용 받는 사람 <br/><br/> 보기 전용 위협 인텔리전스|
|QuarantineAdministrator|모든 받는 사람에 대해 격리된 메시지를 관리합니다.|격리|
|RecipientManagement|조직에서 받는 사람 개체를 만들고 관리하고 제거합니다.|동적 메일 그룹 <br/><br/> 메일 받는 사람 만들기 <br/><br/> 메일 받는 사람 <br/><br/> 메시지 추적 <br/><br/> 마이그레이션 <br/><br/> 받는 사람 정책 <br/><br/> 암호 재설정|
|RecordsManagement|보존 정책 태그, 메시지 분류 및 메일 흐름 규칙(전송 규칙이라고도 함)과 같은 준수 기능을 구성합니다.|메시지 추적 <br/><br/> 보존 관리 <br/><br/> 전송 규칙|
|SecurityAdministrator|조직에서 모든 보호 기능(스팸 방지, 맬웨어 방지, 스푸핑 방지, 격리 등)을 구성합니다. <br/><br/> Azure AD에서 [보안 관리자 역할의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 구성원에게는 자동으로 이 역할 그룹의 사용 권한이 부여됩니다.|맬웨어 방지 <br/><br/> 스팸 방지 <br/><br/> 감사 로그 <br/><br/> 격리 <br/><br/> 보안 관리자 <br/><br/> 민감도 레이블 관리자 <br/><br/> 맬웨어 방지 보기 <br/><br/> 보기 전용 스팸 방지 <br/><br/> 보기 전용 감사 로그 <br/><br/> 보기 전용 격리 <br/><br/> 보기 전용 위협 인텔리전스|
|SecurityReader|조직의 모든 보호 기능(스팸 방지, 맬웨어 방지, 스푸핑 방지, 격리 등)에 대한 보기만 액세스할 수 있습니다. <br/><br/> Azure AD에서 [보안 읽기 프로그램 역할의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) 구성원에게는 자동으로 이 역할 그룹의 사용 권한이 부여됩니다.|보안 읽기 권한자 <br/><br/> 맬웨어 방지 보기 <br/><br/> 보기 전용 스팸 방지 <br/><br/> 보기 전용 격리 <br/><br/> 보기 전용 위협 인텔리전스|
|TenantAdmins|이 역할 그룹의 멤버 자격은 서비스 전체에서 관리됩니다. 기본적으로 이 역할 그룹에는 역할이 할당되어 있지 않습니다. 그러나 이 역할은 Organization Management 역할 그룹의 구성원이 되며 해당 사용 권한을 상속합니다.|없음|
|ViewOnlyOrganizationManagement|조직의 받는 사람, 보호 및 구성 개체와 해당 속성을 확인합니다.|준수 관리자 <br/><br/> 보안 관리자 <br/><br/> 보안 읽기 권한자 <br/><br/> 민감도 레이블 관리자 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 받는 사람|
|

소수의 관리자만 있는 소규모의 조직에서 일하는 경우, 이러한 사용자를 조직 관리 역할 그룹에만 추가해야 하며 다른 역할 그룹을 사용할 필요가 없습니다. 규모가 큰 조직에서일 경우 받는 사람 구성과 같은 특정 작업을 수행하는 관리자가 있을 수 있습니다. 이러한 경우 Recipient Management 역할 그룹과 조직 관리 역할 그룹에 각각 한 명의 관리자를 추가할 수 있습니다. 이러한 관리자는 해당 영역을 관리할 수 있지만 책임이 없는 영역을 관리할 수 있는 권한은 없습니다.

Exchange Online의 기본 제공 역할 그룹이 관리자의 작업 기능과 일치하지 않는 경우 역할 그룹을 만들고 역할을 추가할 수 있습니다. 자세한 내용은 독립 [실행형 EOP에서 역할 그룹 관리를 참조하십시오.](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>역할

독립 실행형 EOP에서 사용할 수 있는 기본 제공 역할은 다음 표에 설명되어 있습니다.

****

|역할**|설명|기본 역할 그룹 할당|
|---|---|---|
|맬웨어 방지|맬웨어 방지 기능에 대한 구성 및 보고서를 보고 수정합니다.|OrganizationManagement <br/><br/> SecurityAdministrator|
|스팸 방지|스팸 방지 기능에 대한 구성과 보고서를 보고 수정합니다.|OrganizationManagement <br/><br/> SecurityAdministrator|
|감사 로그|관리자 감사 로그를 검색하고 결과를 확인합니다.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|준수 관리자<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|데이터 분류 콘텐츠 뷰어<sup>\*</sup>||ContentExplorerContentViewer|
|데이터 분류 목록 뷰어<sup>\*</sup>||
|동적 메일 그룹|모든 메일 그룹, 메일 사용이 가능한 보안 그룹 및 구성원을 만들고 관리합니다.|OrganizationManagement <br/><br/> RecipientManagement|
|정보 권한 관리<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|메일 받는 사람 만들기|메일 사용자를 만들고 제거합니다.|OrganizationManagement <br/><br/> RecipientManagement|
|메일 받는 사람|기존 메일 사용자를 수정합니다.|OrganizationManagement <br/><br/> RecipientManagement|
|메시지 추적<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> 레코드 관리|
|마이그레이션<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|사용자가 자신의 격리된 메시지를 볼 수 있습니다. <br/><br/> 이 역할은 사용자에게 자동으로 할당되며 수동으로 할당할 수 없습니다.|없음|
|조직 클라이언트 액세스<sup>\*</sup>||OrganizationManagement|
|조직 구성|보고서를 봅니다.|OrganizationManagement|
|조직 전송 설정<sup>\*</sup>||OrganizationManagement|
|격리|모든 유형의 격리된 메시지를 모든 받는 사람에 대해 관리합니다.|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|받는 사람 정책<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|원격 및 허용 도메인|원격 도메인, 허용 도메인 및 커넥터를 관리합니다.|MailFlowAdministrator <br/><br/> OrganizationManagement|
|암호 재설정<sup>\*</sup>||HelpDesk <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|보존 관리<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> RecordsManagement|
|역할 관리|역할 그룹 만들기 및 관리|OrganizationManagement|
|보안 관리자|모든 보안 및 보호 기능에 대한 구성과 보고서를 관리합니다.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|보안 그룹 만들기 및 멤버 자격|메일 사용 가능 보안 그룹을 만들고 관리합니다.|OrganizationManagement|
|보안 읽기 권한자|보안 및 보호 기능에 대한 구성 및 보고서를 볼 수 있습니다.|조직 관리 <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|민감도 레이블 관리자<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|감독<sup>\*</sup>||OrganizationManagement|
|전송 예리|맬웨어 방지, 스팸 방지 기능 및 스푸핑 방지 기능을 관리합니다.|HygieneManagement <br/><br/> OrganizationManagement|
|전송 규칙|메일 흐름 규칙(전송 규칙이라고도 함)을 만들고 관리합니다.|OrganizationManagement <br/><br/> RecordsManagement|
|사용자 옵션|기존 메일 사용자를 수정합니다.|HelpDesk <br/><br/> OrganizationManagement|
|맬웨어 방지 보기|맬웨어 방지 기능에 대한 구성 및 보고서를 볼 수 있습니다.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|보기 전용 스팸 방지|스팸 방지 기능에 대한 구성 및 보고서를 볼 수 있습니다.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|보기 전용 감사 로그|관리자 감사 로그를 검색하고 결과를 확인합니다.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|보기 전용 구성|조직의 모든 조직 및 메일 흐름(받는 사람이 아닌) 설정을 확인합니다.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|보기 전용 격리|모든 받는 사람에 대해 격리된 모든 메시지를 볼 수 있습니다.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|보기 전용 받는 사람|받는 사람 속성을 보고 메시지 추적을 실행합니다.|ComplianceManagement <br/><br/> HelpDesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|보기 전용 위협 인텔리전스<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> 이 역할은 사용 가능하지만 기본적으로 독립 실행형 EOP에는 유용하지 않습니다.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>독립 실행형 EOP의 Microsoft 365 사용 권한

Microsoft 365 관리 센터에서 사용자를 만들 때는 전역 관리자, 서비스 관리자, 암호 관리자 등 사용자에게 할당할 관리 역할등의 다양한 관리 역할을 할당할지 여부를 선택할 수 있습니다. 일부(전체는 아무는 경우도) Microsoft 365 역할은 EOP의 관리 권한을 사용자에게 부여합니다.

> [!NOTE]
> 독립 실행형 EOP 조직을 만드는 데 사용한 계정은 자동으로 전역 관리자 역할에 할당됩니다.

다음 표에는 Microsoft 365 역할 및 해당 역할에 해당하는 독립 실행형 EOP 역할 그룹이 나와 있습니다. 이러한 역할에 대한 자세한 내용은 관리자 [역할을 참고하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

****

|Microsoft 365 역할|EOP 역할 그룹|
|---|---|
|Exchange 관리자|OrganizationManagement|
|전역 관리자|OrganizationManagement <br/><br/> **참고:** 전역 관리자 역할 및 OrganizationManagement 역할 그룹은 특수 회사 관리자 역할 그룹을 사용하여 연결됩니다. 회사 관리자 역할 그룹은 내부적으로 관리되며 직접 수정할 수 없습니다.|
|암호 관리자|HelpDesk|
|전역 읽기 권한자|ViewOnlyOrganizationManagement|
|보안 관리자|SecurityAdministrator|
|보안 읽기 권한자|SecurityReader|
|

기타 Microsoft 365 역할에는 해당EOP 역할 그룹이 제공되지 않고 EOP에서 관리 권한을 부여하지 않습니다. 사용자에게 Microsoft 365 역할을 할당하는 방법에 대한 자세한 내용은 관리자 역할 [할당을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

사용자를 Microsoft 365 역할에 추가하지 않고도 EOP에서 관리자 권한을 부여받을 수 있습니다. 이 작업은 사용자를 EOP 역할 그룹의 구성원으로 추가하여 수행합니다. 사용자는 EOP에서 권한을 얻지만 다른 Microsoft 365 작업에서 권한을 얻지는 않습니다.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

역할 그룹이 성공적으로 복사되었는지 확인하려면 다음 단계 중 하나를 수행하십시오.

- EAC에서 사용 권한 **Permissions** 관리자 \> **역할로 이동한**후 역할 그룹이 나열되는지 또는 나열되지 않았는지 확인합니다. 역할 그룹을 선택한 다음 세부 정보 창에서 설정을 확인하거나 편집 아이콘을 **클릭하여** ![ ](../../media/ITPro-EAC-EditIcon.png) 설정을 확인합니다.

- Exchange Online PowerShell에서 역할 그룹의 이름으로 바꾸고, 다음 명령을 실행하여 역할 그룹이 존재하는지(또는 존재하지 \<Role Group Name\> 않는지)를 확인하고 설정을 확인합니다.

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```

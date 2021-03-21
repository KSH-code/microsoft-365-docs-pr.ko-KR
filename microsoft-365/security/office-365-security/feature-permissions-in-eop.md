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
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 독립 실행형 Exchange Online Protection의 작업에 필요한 권한에 대해 자세히 알아보기
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926985"
---
# <a name="permissions-in-standalone-eop"></a>독립 실행형 EOP의 사용 권한

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection)에서는 RBAC(역할 기반 액세스 제어) 권한 모델을 사용하여 관리자에게 사용 권한을 쉽게 부여합니다. 독립 실행형 EOP의 권한 기능을 사용하여 새 조직을 빠르게 운영할 수 있습니다.

사용자에게 사용 권한을 부여하려면 [EOP에서 관리자 역할 그룹 관리를 참조하세요.](manage-admin-role-group-permissions-in-eop.md)

Microsoft 365의 사용 권한에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](../../admin/add-users/about-admin-roles.md)

## <a name="role-based-permissions"></a>역할 기반 사용 권한

사용자에게 부여하는 관리자 권한은 관리 역할을 기반으로 합니다. 관리 역할은 특정 작업 집합에 사용할 수 있는 cmdlet을 정의합니다. EAC(Exchange 관리 센터) 및 독립 실행형 EOP PowerShell은 둘 다 cmdlet을 사용하기 때문에 cmdlet에 대한 액세스 권한을 부여하면 사용자에게 EAC 또는 독립 실행형 EOP PowerShell에서 관련 작업을 수행할 수 있는 권한이 부여됩니다. 예를 들어 Mail Recipients 역할은 메일 사용자를 수정하는 데 필요한 cmdlet을 정의합니다.

독립 실행형 EOP에서 관리 역할은 사용 가능한 유일한 관리 역할 유형입니다(최종 사용자 역할 또는 역할 할당 정책은 없음).

## <a name="role-groups"></a>역할 그룹

사용자에게 역할을 더 쉽게 할당하기 위해 독립 실행형 EOP는 역할 그룹을 사용 합니다. 관리 역할은 역할 그룹에 할당되어 있으며 역할 그룹 구성원은 역할과 연결된 사용 권한을 얻습니다. 즉, 관리 역할은 사용자에게 직접 할당되지 않습니다. 역할 그룹에 할당됩니다. 이 모델을 사용하면 여러 역할 그룹 구성원에게 여러 역할을 동시에 할당할 수 있습니다. 역할 그룹 구성원은 메일 사용자, 메일 사용이 가능한 보안 그룹, Microsoft 365 관리 센터의 사용자 및 기타 역할 그룹일 수 있습니다.

다음 그림은 사용자, 역할 그룹 및 역할 간의 관계를 보여줍니다.

![역할, 역할 그룹 및 구성원 관계](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

독립 실행형 EOP에서 사용 가능한 역할 그룹은 다음 표에 설명되어 있습니다.

****

|역할 그룹|설명|할당된 기본 역할|
|---|---|---|
|ComplianceManagement|구독에 DLP 기능이 있는 경우 DLP(데이터 손실 방지)를 포함하여 조직 내의 규정 준수 설정을 구성하고 관리합니다. <p> Azure [AD의 준수 관리자](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) 역할 구성원은 자동으로 이 역할 그룹의 사용 권한을 얻습니다.|감사 로그 <p> 준수 관리 <p> 정보 권한 관리 <p> 보존 관리 <p> View-Only 감사 로그 <p> 보기 전용 구성 <p> 보기 전용 받는 사람|
|ContentExplorerContentViewer|사용되지 않습니다.|데이터 분류 콘텐츠 뷰어|
|ContentExplorerListViewer|사용되지 않습니다.|데이터 분류 목록 뷰어|
|HelpDesk|메일 사용자를 보고 관리합니다.|암호 다시 설정 <p> 사용자 옵션 <p> 보기 전용 받는 사람|
|HygieneManagement|보호 기능(스팸 방지, 맬웨어 방지 등)을 관리합니다.|전송방지 <p> 보기 전용 구성 <p> 보기 전용 받는 사람|
|MailFlowAdministrator|허용 도메인 및 커넥터 보기 및 관리|원격 및 허용 도메인 <p> 보기 전용 받는 사람|
|OrganizationManagement|전체 조직에 대한 관리자 액세스 및 거의 모든 작업을 수행하는 능력. <p> Azure [AD의 전역 관리자](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 역할 구성원은 자동으로 이 역할 그룹의 사용 권한을 얻습니다. <p> **중요:** OrganizationManagement 역할 그룹은 강력한 역할이기 때문에 조직 수준 관리 작업을 수행하는 사용자만 이 역할 그룹의 구성원이 됩니다.|맬웨어 방지 <p> AntiSpam <p> 감사 로그 <p> 준수 관리자 <p> 동적 메일 그룹 <p> 정보 권한 관리 <p> 메일 받는 사람 만들기 <p> 메일 받는 사람 <p> 메시지 추적 <p> 마이그레이션 <p> 조직 클라이언트 액세스 <p> 조직 구성 <p> 조직 전송 설정 <p> 격리 <p> 받는 사람 정책 <p> 원격 및 허용 도메인 <p> 암호 다시 설정 <p> 보존 관리 <p> 역할 관리 <p> 보안 관리자 <p> Security Group Creation and Membership <p> 보안 읽기 권한자 <p> 민감도 레이블 관리자 <p> 감독 <p> 전송방지 <p> 전송 규칙 <p> 사용자 옵션 <p> View-Only 맬웨어 방지 <p> View-Only 방지 <p> View-Only 감사 로그 <p> 보기 전용 구성 <p> View-Only Quarantine <p> 보기 전용 받는 사람 <p> View-Only 위협 인텔리전스|
|QuarantineAdministrator|모든 받는 사람에 대해 quarantined messages를 관리합니다.|격리|
|RecipientManagement|조직에서 받는 사람 개체를 만들고 관리하고 제거합니다.|동적 메일 그룹 <p> 메일 받는 사람 만들기 <p> 메일 받는 사람 <p> 메시지 추적 <p> 마이그레이션 <p> 받는 사람 정책 <p> 암호 다시 설정|
|RecordsManagement|보존 정책 태그, 메시지 분류 및 메일 흐름 규칙(전송 규칙)과 같은 준수 기능을 구성합니다.|메시지 추적 <p> 보존 관리 <p> 전송 규칙|
|SecurityAdministrator|조직의 모든 보호 측면(스팸 방지, 맬웨어 방지, 스푸핑 방지, 검역 등)을 구성합니다. <p> Azure [AD의 보안 관리자](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 역할 구성원은 자동으로 이 역할 그룹의 사용 권한을 얻습니다.|맬웨어 방지 <p> AntiSpam <p> 감사 로그 <p> 격리 <p> 보안 관리자 <p> 민감도 레이블 관리자 <p> View-Only 맬웨어 방지 <p> View-Only 방지 <p> View-Only 감사 로그 <p> View-Only Quarantine <p> View-Only 위협 인텔리전스|
|SecurityReader|조직의 모든 보호 측면(스팸 방지, 맬웨어 방지, 스푸핑 방지, 검역 등)에 대한 보기 전용 액세스입니다. <p> Azure [AD의 보안](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) 읽기 권한자 역할 구성원은 자동으로 이 역할 그룹의 사용 권한을 얻습니다.|보안 읽기 권한자 <p> View-Only 맬웨어 방지 <p> View-Only 방지 <p> View-Only Quarantine <p> View-Only 위협 인텔리전스|
|TenantAdmins|이 역할 그룹의 구성원 자격은 여러 서비스에서 동기화되고 중앙에서 관리됩니다. 기본적으로 이 역할 그룹에는 어떤 역할도 할당되지 않습니다. 그러나 이 역할 그룹은 Organization Management 역할 그룹의 구성원이 되어 해당 사용 권한을 상속합니다.|없음|
|ViewOnlyOrganizationManagement|조직에서 받는 사람, 보호 및 구성 개체와 해당 속성을 볼 수 있습니다.|준수 관리자 <p> 보안 관리자 <p> 보안 읽기 권한자 <p> 민감도 레이블 관리자 <p> 보기 전용 구성 <p> 보기 전용 받는 사람|
|

소수의 관리자만 있는 소규모 조직에서 작업하는 경우 해당 사용자를 조직 관리 역할 그룹에만 추가해야 할 수 있으며 다른 역할 그룹을 사용할 필요가 없습니다. 대규모 조직에서 작업하는 경우 받는 사람 구성과 같은 특정 작업을 수행하는 관리자가 있을 수 있습니다. 이러한 경우 받는 사람 관리 역할 그룹에 관리자 한 명을 추가하고 조직 관리 역할 그룹에 다른 관리자를 추가할 수 있습니다. 그러면 해당 관리자는 특정 영역을 관리할 수 있지만 담당하지 않는 영역을 관리할 수 있는 권한이 없습니다.

Exchange Online의 기본 제공 역할 그룹이 관리자의 작업 기능과 일치하지 않는 경우 역할 그룹을 만들고 역할을 추가할 수 있습니다. 자세한 내용은 독립 실행형 [EOP에서 역할 그룹 관리를 참조하세요.](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>역할

독립 실행형 EOP에서 사용할 수 있는 기본 제공 역할은 다음 표에 설명되어 있습니다.

****

|역할**|설명|기본 역할 그룹 할당|
|---|---|---|
|맬웨어 방지|맬웨어 방지 기능에 대한 구성 및 보고서를 보고 수정합니다.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|스팸 방지 기능에 대한 구성 및 보고서를 보고 수정합니다.|OrganizationManagement <p> SecurityAdministrator|
|감사 로그|관리자 감사 로그를 검색하고 결과를 시청합니다.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|준수 관리자<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|데이터 분류 콘텐츠 뷰어<sup>\*</sup>||ContentExplorerContentViewer|
|데이터 분류 목록 뷰어<sup>\*</sup>||
|동적 메일 그룹|모든 메일 그룹, 메일 사용이 가능한 보안 그룹 및 구성원을 만들고 관리합니다.|OrganizationManagement <p> RecipientManagement|
|정보 권한 관리<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|메일 받는 사람 만들기|메일 사용자를 만들고 제거합니다.|OrganizationManagement <p> RecipientManagement|
|메일 받는 사람|기존 메일 사용자 수정|OrganizationManagement <p> RecipientManagement|
|메시지 추적<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> 레코드 관리|
|마이그레이션<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|사용자가 자신의 고지된 메시지를 볼 수 있도록 허용합니다. <p> 이 역할은 사용자에게 자동으로 할당되며 수동으로 할당할 수 없습니다.|없음|
|조직 클라이언트 액세스<sup>\*</sup>||OrganizationManagement|
|조직 구성|보고서를 봅니다.|OrganizationManagement|
|조직 전송 설정<sup>\*</sup>||OrganizationManagement|
|격리|모든 받는 사람에 대해 모든 유형의 분리된 메시지를 관리합니다.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|받는 사람 정책<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|원격 및 허용 도메인|원격 도메인, 허용 도메인 및 커넥터를 관리합니다.|MailFlowAdministrator <p> OrganizationManagement|
|암호 다시 설정<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|보존 관리<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|역할 관리|역할 그룹을 만들고 관리합니다.|OrganizationManagement|
|보안 관리자|모든 보안 및 보호 기능에 대한 구성 및 보고서를 관리합니다.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Security Group Creation and Membership|메일 사용이 가능한 보안 그룹을 만들고 관리합니다.|OrganizationManagement|
|보안 읽기 권한자|보안 및 보호 기능에 대한 구성 및 보고서를 시청합니다.|조직 관리 <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|민감도 레이블 관리자<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|감독<sup>\*</sup>||OrganizationManagement|
|전송방지|맬웨어 방지, 스팸 방지 기능 및 스푸핑 방지 기능을 관리합니다.|HygieneManagement <p> OrganizationManagement|
|전송 규칙|메일 흐름 규칙(전송 규칙)을 만들고 관리합니다.|OrganizationManagement <p> RecordsManagement|
|사용자 옵션|기존 메일 사용자 수정|HelpDesk <p> OrganizationManagement|
|View-Only 맬웨어 방지|맬웨어 방지 기능에 대한 구성 및 보고서를 볼 수 있습니다.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only 방지|스팸 방지 기능에 대한 구성 및 보고서를 볼 수 있습니다.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only 감사 로그|관리자 감사 로그를 검색하고 결과를 시청합니다.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|보기 전용 구성|조직의 모든 조직 및 메일 흐름(받는 사람이 아닌) 설정을 확인합니다.|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Quarantine|모든 받는 사람에 대해 모든 고지된 메시지를 보기.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|보기 전용 받는 사람|받는 사람 속성을 보고 메시지 추적을 실행합니다.|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only 위협 인텔리전스<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> 이 역할은 사용할 수 있는 것이지만 기본적으로 독립 실행형 EOP에서 유용한 것은 없습니다.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>독립 실행형 EOP의 Microsoft 365 권한

Microsoft 365 관리 센터에서 사용자를 만들 때 전역 관리자, 서비스 관리자, 암호 관리자 등의 다양한 관리 역할을 사용자에게 할당할지 여부를 선택할 수 있습니다. 일부 Microsoft 365 역할은 EOP에서 사용자 관리 권한을 부여합니다.

> [!NOTE]
> 독립 실행형 EOP 조직을 만드는 데 사용한 계정은 전역 관리자 역할에 자동으로 할당됩니다.

다음 표에는 Microsoft 365 역할 및 해당 역할이 해당하는 독립 실행형 EOP 역할 그룹이 나열됩니다. 이러한 역할에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](../../admin/add-users/about-admin-roles.md)

****

|Microsoft 365 역할|EOP 역할 그룹|
|---|---|
|Exchange 관리자|OrganizationManagement|
|전역 관리자|OrganizationManagement <p> **참고:** 전역 관리자 역할 및 OrganizationManagement 역할 그룹은 특수 회사 관리자 역할 그룹을 사용하여 함께 구성됩니다. 회사 관리자 역할 그룹은 내부적으로 관리되고 직접 수정할 수 없습니다.|
|암호 관리자|HelpDesk|
|전역 읽기 권한자|ViewOnlyOrganizationManagement|
|보안 관리자|SecurityAdministrator|
|보안 읽기 권한자|SecurityReader|
|

다른 Microsoft 365 역할에는 해당하는 EOP 역할 그룹이 있으며 EOP에서 관리 권한을 부여하지 않습니다. 사용자에게 Microsoft 365 역할을 할당하는 데 대한 자세한 내용은 관리자 역할 [할당을 참조하세요.](../../admin/add-users/assign-admin-roles.md)

사용자는 Microsoft 365 역할에 추가하지 않고도 EOP에서 관리 권한을 부여할 수 있습니다. 이 작업을 위해 사용자를 EOP 역할 그룹의 구성원으로 추가합니다. 사용자는 EOP에서 사용 권한을 얻지만 다른 Microsoft 365 워크로드에서는 사용 권한을 얻지 못합니다.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

역할 그룹을 성공적으로 복사한지 확인하기 위해 다음 단계 중 하나를 수행합니다.

- EAC에서 사용 권한  관리자 역할로 이동하여 역할 그룹이 나열되어 \> 있는지(나열되지 않은지) 확인해야 합니다. 역할 그룹을 선택하고 세부 정보 창에서 설정을 확인하거나  편집 편집 아이콘을 클릭하여 ![ 설정을 ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.

- Exchange Online PowerShell에서 역할 그룹의 이름으로 바꾸고 다음 명령을 실행하여 역할 그룹이 존재하거나 존재하지 않는지 확인하고 설정을 \<Role Group Name\> 확인합니다.

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```
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
description: 독립 실행형 Exchange Online Protection의 작업에 필요한 사용 권한에 대해 알아봅니다.
ms.openlocfilehash: ae43dc2223b17d3b73f9b76fa6bde8fb9cb95e77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202870"
---
# <a name="permissions-in-standalone-eop"></a>독립 실행형 EOP의 사용 권한

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 없는 독립 실행형 Exchange Online Protection (EOP)은 RBAC (역할 기반 액세스 제어) 권한 모델을 사용 하 여 관리자에 게 쉽게 사용 권한을 부여 합니다. 독립 실행형 EOP의 사용 권한 기능을 사용 하 여 새 조직을 빠르게 가동 및 실행할 수 있습니다.

사용자에 게 사용 권한을 부여 하려면 [EOP에서 관리자 역할 그룹 관리](manage-admin-role-group-permissions-in-eop.md)를 참조 하십시오.

Microsoft 365의 사용 권한에 대 한 자세한 내용은 [관리 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조 하십시오.

## <a name="role-based-permissions"></a>역할 기반 권한

사용자에 게 부여 하는 관리자 권한은 관리 역할을 기반으로 합니다. 관리 역할은 지정 된 작업 집합에 사용할 수 있는 cmdlet을 정의 합니다. EAC (Exchange 관리 센터) 및 독립 실행형 EOP PowerShell은 둘 다 cmdlet을 사용 하므로 cmdlet에 대 한 액세스 권한을 부여 하면 EAC 또는 독립 실행형 EOP PowerShell에서 관련 작업을 수행할 수 있는 권한이 사용자에 게 부여 됩니다. 예를 들어 Mail Recipients 역할은 메일 사용자를 수정 하는 데 필요한 cmdlet을 정의 합니다.

독립 실행형 EOP에서 관리 역할은 사용할 수 있는 유일한 관리 역할 유형 (최종 사용자 역할 또는 역할 할당 정책이 없음)입니다.

## <a name="role-groups"></a>역할 그룹

사용자에 게 더 쉽게 역할을 할당할 수 있도록 하기 위해 독립 실행형 EOP에서는 역할 그룹을 사용 합니다. 관리 역할이 역할 그룹에 할당 되 고 역할 그룹 구성원에 게 해당 역할과 연결 된 사용 권한이 부여 됩니다. 즉, 관리 역할은 사용자에 게 직접 할당 되지 않습니다. 역할 그룹에 할당 됩니다. 이 모델을 사용 하면 여러 역할 그룹 구성원에 여러 역할을 한 번에 할당할 수 있습니다. 역할 그룹 구성원은 메일 사용자, 메일 사용이 가능한 보안 그룹, Microsoft 365 관리 센터의 사용자 및 기타 역할 그룹 일 수 있습니다.

다음 그림은 사용자, 역할 그룹 및 역할 간의 관계를 보여줍니다.

![역할, 역할 그룹 및 구성원 관계](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

독립 실행형 EOP에서 사용할 수 있는 역할 그룹은 다음 표에 설명 되어 있습니다.

****

|역할 그룹|설명|할당 된 기본 역할|
|---|---|---|
|ComplianceManagement|구독에 DLP 기능이 있는 경우 DLP (데이터 손실 방지)를 포함 하 여 조직 내에서 규정 준수 설정을 구성 하 고 관리 합니다. <br/><br/> Azure AD에서 [규정 준수 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) 역할의 구성원은이 역할 그룹의 사용 권한을 자동으로 부여 합니다.|감사 로그 <br/><br/> 준수 관리 <br/><br/> 정보 권한 관리 <br/><br/> 보존 관리 <br/><br/> 보기 전용 감사 로그 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 받는 사람|
|ContentExplorerContentViewer|사용되지 않습니다.|데이터 분류 콘텐츠 뷰어|
|ContentExplorerListViewer|사용되지 않습니다.|데이터 분류 목록 뷰어|
|HelpDesk|메일 사용자를 보고 관리 합니다.|암호 다시 설정 <br/><br/> 사용자 옵션 <br/><br/> 보기 전용 받는 사람|
|HygieneManagement|보호 기능 관리 (스팸 방지, 맬웨어 방지 등)|전송 바이러스 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 받는 사람|
|MailFlowAdministrator|허용 도메인 및 커넥터 보기 및 관리|원격 및 허용 도메인 <br/><br/> 보기 전용 받는 사람|
|OrganizationManagement|전체 조직에 대 한 관리자 액세스 및 거의 모든 작업을 수행 하는 기능 <br/><br/> Azure AD의 [전역 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 역할 구성원은이 역할 그룹의 사용 권한을 자동으로 부여 합니다. <br/><br/> **중요**: OrganizationManagement 역할 그룹은 매우 강력한 역할 이므로, 조직 수준 관리 작업을 수행 하는 사용자만이 역할 그룹의 구성원 이어야 합니다.|프로그램이 <br/><br/> 스팸 방지 <br/><br/> 감사 로그 <br/><br/> 준수 관리자 <br/><br/> 동적 메일 그룹 <br/><br/> 정보 권한 관리 <br/><br/> 메일 받는 사람 만들기 <br/><br/> 메일 받는 사람 <br/><br/> 메시지 추적 <br/><br/> 마이그레이션 <br/><br/> 조직 클라이언트 액세스 <br/><br/> 조직 구성 <br/><br/> 조직 전송 설정 <br/><br/> 격리 <br/><br/> 받는 사람 정책 <br/><br/> 원격 및 허용 도메인 <br/><br/> 암호 다시 설정 <br/><br/> 보존 관리 <br/><br/> 역할 관리 <br/><br/> 보안 관리자 <br/><br/> 보안 그룹 만들기 및 구성원 <br/><br/> 보안 읽기 권한자 <br/><br/> 민감도 레이블 관리자 <br/><br/> 감독 <br/><br/> 전송 바이러스 <br/><br/> 전송 규칙 <br/><br/> 사용자 옵션 <br/><br/> 보기 전용 맬웨어 방지 <br/><br/> 보기 전용 스팸 방지 <br/><br/> 보기 전용 감사 로그 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 격리 <br/><br/> 보기 전용 받는 사람 <br/><br/> 보기 전용 위협 인텔리전스|
|QuarantineAdministrator|모든 받는 사람에 대해 격리 된 메시지를 관리 합니다.|격리|
|RecipientManagement|조직에서 받는 사람 개체를 만들고, 관리 하 고, 제거 합니다.|동적 메일 그룹 <br/><br/> 메일 받는 사람 만들기 <br/><br/> 메일 받는 사람 <br/><br/> 메시지 추적 <br/><br/> 마이그레이션 <br/><br/> 받는 사람 정책 <br/><br/> 암호 다시 설정|
|레코드 관리|보존 정책 태그, 메시지 분류, 메일 흐름 규칙 (전송 규칙이 라고도 함) 등의 규정 준수 기능을 구성 합니다.|메시지 추적 <br/><br/> 보존 관리 <br/><br/> 전송 규칙|
|보안 관리자|조직의 모든 보호 기능 구성 (스팸 방지, 맬웨어 방지, 스푸핑 방지, 격리 등) <br/><br/> Azure AD의 [보안 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 역할 구성원은이 역할 그룹의 사용 권한을 자동으로 부여 합니다.|프로그램이 <br/><br/> 스팸 방지 <br/><br/> 감사 로그 <br/><br/> 격리 <br/><br/> 보안 관리자 <br/><br/> 민감도 레이블 관리자 <br/><br/> 보기 전용 맬웨어 방지 <br/><br/> 보기 전용 스팸 방지 <br/><br/> 보기 전용 감사 로그 <br/><br/> 보기 전용 격리 <br/><br/> 보기 전용 위협 인텔리전스|
|SecurityReader|보기 전용 조직의 모든 보호 기능에 대 한 액세스 권한 (스팸 방지, 맬웨어 방지, 스푸핑 방지, 격리 등) <br/><br/> Azure AD의 [보안 독자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) 역할 구성원은이 역할 그룹의 사용 권한을 자동으로 부여 합니다.|보안 읽기 권한자 <br/><br/> 보기 전용 맬웨어 방지 <br/><br/> 보기 전용 스팸 방지 <br/><br/> 보기 전용 격리 <br/><br/> 보기 전용 위협 인텔리전스|
|TenantAdmins|이 역할 그룹의 구성원은 서비스 간에 동기화 되 고 중앙에서 관리 됩니다. 기본적으로이 역할 그룹에는 역할이 할당 되지 않습니다. 그러나 조직 관리 역할 그룹의 구성원이 되며 해당 사용 권한을 상속 받습니다.|없음|
|ViewOnlyOrganizationManagement|조직의 받는 사람, 보호 및 구성 개체와 해당 속성을 확인 합니다.|준수 관리자 <br/><br/> 보안 관리자 <br/><br/> 보안 읽기 권한자 <br/><br/> 민감도 레이블 관리자 <br/><br/> 보기 전용 구성 <br/><br/> 보기 전용 받는 사람|
|

소수의 관리자만 포함 하는 소규모 조직에서 작업 하는 경우 해당 사용자를 조직 관리 역할 그룹에만 추가 해야 할 수 있으며, 다른 역할 그룹은 사용 하지 않아도 될 수 있습니다. 대규모 조직에서 작업 하는 경우 받는 사람 구성과 같은 특정 작업을 수행 하는 관리자가 있을 수 있습니다. 이러한 경우 Recipient Management 역할 그룹에 하나의 관리자를 추가 하 고 조직 관리 역할 그룹에 다른 관리자를 추가할 수 있습니다. 그러면 해당 관리자는 특정 영역을 관리할 수 있지만 담당 하지 않는 영역을 관리할 권한이 없습니다.

Exchange Online의 기본 제공 역할 그룹이 관리자의 작업 기능과 일치하지 않는 경우 역할 그룹을 만들고 역할을 추가할 수 있습니다. 자세한 내용은 [독립 실행형 EOP에서 역할 그룹 관리](manage-admin-role-group-permissions-in-eop.md)를 참조 하십시오.

## <a name="roles"></a>역할

독립 실행형 EOP에서 사용할 수 있는 기본 제공 역할은 다음 표에 설명 되어 있습니다.

****

|역할 * *|설명|기본 역할 그룹 할당|
|---|---|---|
|프로그램이|맬웨어 방지 기능에 대 한 구성 및 보고서를 보고 수정 합니다.|OrganizationManagement <br/><br/> 보안 관리자|
|스팸 방지|스팸 방지 기능에 대 한 구성 및 보고서를 보고 수정 합니다.|OrganizationManagement <br/><br/> 보안 관리자|
|감사 로그|관리자 감사 로그를 검색 하 여 결과를 확인 합니다.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> 보안 관리자|
|준수 관리자<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|데이터 분류 콘텐츠 뷰어<sup>\*</sup>||ContentExplorerContentViewer|
|데이터 분류 목록 뷰어<sup>\*</sup>||
|동적 메일 그룹|모든 메일 그룹, 메일 사용이 가능한 보안 그룹 및 구성원을 만들고 관리 합니다.|OrganizationManagement <br/><br/> RecipientManagement|
|정보 권한 관리<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|메일 받는 사람 만들기|메일 사용자를 만들고 제거 합니다.|OrganizationManagement <br/><br/> RecipientManagement|
|메일 받는 사람|기존 메일 사용자를 수정 합니다.|OrganizationManagement <br/><br/> RecipientManagement|
|메시지 추적<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> 레코드 관리|
|마이그레이션하기<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|사용자가 격리 된 메시지를 직접 볼 수 있습니다. <br/><br/> 이 역할은 사용자에 게 자동으로 할당 되며 수동으로 할당할 수 없습니다.|없음|
|조직 클라이언트 액세스<sup>\*</sup>||OrganizationManagement|
|조직 구성|보고서를 봅니다.|OrganizationManagement|
|조직 전송 설정<sup>\*</sup>||OrganizationManagement|
|격리|모든 받는 사람에 대해 격리 된 메시지의 모든 유형을 관리 합니다.|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> 보안 관리자|
|받는 사람 정책<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|원격 및 허용 도메인|원격 도메인, 허용 도메인 및 커넥터를 관리 합니다.|MailFlowAdministrator <br/><br/> OrganizationManagement|
|암호 다시 설정<sup>\*</sup>||HelpDesk <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|보존 관리<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> 레코드 관리|
|역할 관리|역할 그룹을 만들고 관리 합니다.|OrganizationManagement|
|보안 관리자|모든 보안 및 보호 기능에 대 한 구성 및 보고서를 관리 합니다.|OrganizationManagement <br/><br/> 보안 관리자 <br/><br/> ViewOnlyOrganizationManagement|
|보안 그룹 만들기 및 구성원|메일 사용이 가능한 보안 그룹을 만들고 관리 합니다.|OrganizationManagement|
|보안 읽기 권한자|보안 및 보호 기능에 대 한 구성 및 보고서를 확인 합니다.|조직 관리 <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|민감도 레이블 관리자<sup>\*</sup>||OrganizationManagement <br/><br/> 보안 관리자 <br/><br/> ViewOnlyOrganizationManagement|
|감독<sup>\*</sup>||OrganizationManagement|
|전송 바이러스|맬웨어 방지, 스팸 방지 기능 및 스푸핑 방지 기능을 관리 합니다.|HygieneManagement <br/><br/> OrganizationManagement|
|전송 규칙|메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들고 관리 합니다.|OrganizationManagement <br/><br/> 레코드 관리|
|사용자 옵션|기존 메일 사용자를 수정 합니다.|HelpDesk <br/><br/> OrganizationManagement|
|보기 전용 맬웨어 방지|맬웨어 방지 기능에 대 한 구성 및 보고서를 확인 합니다.|OrganizationManagement <br/><br/> 보안 관리자 <br/><br/> SecurityReader|
|보기 전용 스팸 방지|스팸 방지 기능에 대 한 구성 및 보고서를 확인 합니다.|OrganizationManagement <br/><br/> 보안 관리자 <br/><br/> SecurityReader|
|보기 전용 감사 로그|관리자 감사 로그를 검색 하 여 결과를 확인 합니다.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> 보안 관리자|
|보기 전용 구성|조직의 모든 조직 및 메일 흐름 (받는 사람 외) 설정을 확인 합니다.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|보기 전용 격리|모든 받는 사람에 대해 격리 된 모든 메시지를 확인 합니다.|OrganizationManagement <br/><br/> 보안 관리자 <br/><br/> SecurityReader|
|보기 전용 받는 사람|받는 사람 속성을 확인 하 고 메시지 추적을 실행 합니다.|ComplianceManagement <br/><br/> HelpDesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|보기 전용 위협 인텔리전스<sup>\*</sup>||OrganizationManagement <br/><br/> 보안 관리자 <br/><br/> SecurityReader|
|

<sup>\*</sup> 이 역할은 사용할 수 있지만 기본적으로 독립 실행형 EOP에서는 아무 유용 하지 않습니다.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>독립 실행형 EOP의 Microsoft 365 사용 권한

Microsoft 365 관리 센터에서 사용자를 만들 때 전역 관리자, 서비스 관리자, 암호 관리 등의 다양 한 관리 역할을 사용자에 게 할당할지 여부를 선택할 수 있습니다. 모두는 아니지만 일부 Microsoft 365 역할은 EOP에서 사용자 관리 권한을 부여 합니다.

> [!NOTE]
> 독립 실행형 EOP 조직을 만드는 데 사용한 계정이 전역 관리자 역할에 자동으로 할당 됩니다.

다음 표에서는 Microsoft 365 역할 및 해당 역할과 해당 역할이 해당 하는 독립 실행형 EOP 역할 그룹을 보여 줍니다. 이러한 역할에 대 한 자세한 내용은 [관리 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조 하십시오.

****

|Microsoft 365 역할|EOP 역할 그룹|
|---|---|
|Exchange 관리자|OrganizationManagement|
|전역 관리자|OrganizationManagement <br/><br/> **참고**: 전역 관리자 역할 및 OrganizationManagement 역할 그룹은 특수 회사 관리자 역할 그룹을 사용 하 여 서로 연결 됩니다. 회사 관리자 역할 그룹은 내부적으로 관리 되며 직접 수정할 수 없습니다.|
|암호 관리자|HelpDesk|
|전역 읽기 권한자|ViewOnlyOrganizationManagement|
|보안 관리자|보안 관리자|
|보안 읽기 권한자|SecurityReader|
|

다른 Microsoft 365 역할에는 해당 하는 EOP 역할 그룹이 없으며 EOP에서 관리 권한을 부여 하지 않습니다. 사용자에 게 Microsoft 365 역할을 할당 하는 방법에 대 한 자세한 내용은 [관리자 역할 할당](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)을 참조 하십시오.

사용자에 게 Microsoft 365 역할에 추가 하지 않고 EOP에서 관리 권한을 부여할 수 있습니다. 사용자를 EOP 역할 그룹의 구성원으로 추가 하 여이 작업을 수행 합니다. 사용자는 EOP에서 사용 권한을 얻게 되지만 다른 Microsoft 365 작업에서는 사용 권한이 부여 되지 않습니다.

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

역할 그룹이 성공적으로 복사 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- EAC에서 **사용 권한** \> **관리자 역할로**이동 하 여 해당 역할 그룹이 나열 되는지 확인 합니다 (또는 나열 되지 않음). 역할 그룹을 선택 하 고 세부 정보 창에서 설정을 확인 하거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-EditIcon.png) 하 여 설정을 확인 합니다.

- Exchange Online PowerShell에서 \<Role Group Name\> 역할 그룹의 이름으로 바꾸고 다음 명령을 실행 하 여 역할 그룹이 존재 하는지 확인 하 고 (또는 존재 하지 않음) 설정을 확인 합니다.

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```

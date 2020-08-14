---
title: Microsoft 365 그룹, 팀 및 SharePoint의 액세스 제어
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 그룹, 팀 및 SharePoint의 액세스 권한 관리에 대해 알아봅니다.
ms.openlocfilehash: 8b58016ffa421328e3c1442d4ed2364f2eedc37b
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662759"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 그룹, 팀 및 SharePoint의 액세스 제어

사용자가 그룹, 팀 및 SharePoint에서 리소스에 액세스 하는 방법을 제어 하는 데 사용할 수 있는 여러 컨트롤이 있습니다. 이러한 옵션을 검토 하 여 비즈니스 요구 사항, 데이터의 민감도, 사용자가 공동 작업을 수행 하는 데 필요한 사용자 범위 등을 고려해 야 합니다.

다음 표에서는 Microsoft 365에서 사용할 수 있는 access 컨트롤에 대 한 빠른 참조를 제공 합니다. 다음 섹션에서는 자세한 정보를 제공 합니다.

|범주|설명|참조|
|:-------|:----------|:--------|
|구성원|||
||비공개 팀 검색|[Microsoft 팀에서 비공개 팀 검색 관리](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||규칙을 기반으로 하는 동적 그룹 구성원|[Azure Active Directory에서 동적 그룹 만들기 또는 업데이트](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||파일, 폴더 및 사이트를 공유할 수 있는 사용자를 제어 합니다.|[액세스 요청 설정 및 관리](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|조건부 액세스|||
||다단계 인증|[Azure Multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||그룹, 팀 또는 사이트 민감도를 기반으로 장치 액세스를 제어 합니다.|[민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||관리 되지 않는 장치에 대 한 사이트 액세스를 제한 합니다.|[관리 되지 않는 장치에서 SharePoint 액세스 제어](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||위치를 기반으로 사이트 액세스 제어|[네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|게스트 액세스|||
||지정 된 도메인에서 SharePoint 공유를 허용 하거나 차단 합니다.|[도메인별 SharePoint 및 OneDrive 콘텐츠 공유 제한](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||지정 된 도메인에서 팀 또는 그룹 구성원을 허용 하거나 차단 합니다.|[특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||익명 공유를 차단 합니다.|[모든 사용자 링크 해제](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||익명 액세스 링크에 대 한 사용 권한 제어|[사용자 링크에 대 한 링크 사용 권한 설정](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||익명 공유 링크의 만료를 제어 합니다.|[모든 사용자 링크의 만료 날짜를 설정합니다.](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||사용자에 게 기본적으로 표시 되는 공유 링크 유형을 제어 합니다.|[사이트의 기본 연결 종류 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||특정 사용자에 대 한 외부 공유를 제한 합니다.|[지정 된 보안 그룹에 대 한 외부 공유 제한](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||정보 민감도에 따라 그룹, 팀 또는 사이트에 대 한 게스트 액세스를 제어 합니다.|[민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||공유 옵션을 해제 합니다.|[Microsoft 365에서의 공유 제한](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|사용자 관리|||
||정기적으로 팀 및 그룹 구성원을 검토 합니다.|[Azure AD access 검토 란?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||그룹 및 팀에 대 한 액세스 관리를 자동화 합니다.|[Azure AD 자격 관리 란?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||사용자가 팀에서 개인 채널을 만들지 못하도록 허용 하거나 차단 합니다.|[Microsoft 팀에서 개인 채널의 수명 주기 관리](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>구성원

팀 및 그룹의 구성원 자격은 소유자가 제어 합니다. 구성원은 다른 사용자를 초대할 수 있지만 초대는 승인을 받기 위해 소유자에 게 전송 됩니다. 조직의 모든 사용자가 공용 팀 및 그룹을 검색할 수 있지만 개인 팀과 그룹의 검색 가능 여부를 제어할 수도 있습니다.

- [Microsoft 팀에서 비공개 팀 검색 관리](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

부서와 같은 일부 조건을 기반으로 그룹 또는 팀의 구성원을 동적으로 관리할 수 있습니다. 이 경우 구성원 및 소유자가 팀에 사용자를 초대할 수 없습니다.

- [Azure Active Directory에서 동적 그룹 만들기 또는 업데이트](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint 사이트는 그룹 또는 팀 구성원 자격을 제외 하 고 소유자, 구성원 및 방문자를 추가할 수 있는 기능을 제공 합니다. 요구 사항에 따라 사용자를 사이트에 초대할 수 있는 사용자를 제한할 수 있습니다. 또한 지정 된 사이트의 정보 민감도에 따라 파일 및 폴더를 공유할 수 있는 사용자를 제한할 수 있습니다. 이러한 제한은 팀, 그룹 또는 사이트 소유자가 구성 합니다.

- [액세스 요청 설정 및 관리](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>조건부 액세스

Microsoft 365를 사용 하 여 조직 내부 및 외부 사용자에 대해 다단계 인증을 요구할 수 있습니다. 두 번째 인증 요인을 사용자에 게 묻는 메시지가 표시 되는 상황에 대 한 다양 한 옵션이 있습니다. 조직에 다단계 인증을 배포 하는 것이 좋습니다.

- [Azure Multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

일부 그룹과 팀에 중요 한 정보가 있는 경우 그룹 또는 팀의 민감도 레이블을 기반으로 장치 관리 정책을 적용할 수 있습니다. 관리 되지 않는 장치에서 완전히 액세스를 차단 하거나 제한 된 웹 전용 액세스를 허용할 수 있습니다.

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

SharePoint에서는 지정 된 네트워크 위치의 사이트에 대 한 액세스를 제한할 수 있습니다.

- [네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


추가 리소스:

- [조건부 액세스 배포 계획](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune 개요](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [관리 되지 않는 장치에서 SharePoint 액세스 제어](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>게스트 액세스

전자 메일 주소의 도메인을 기반으로 게스트를 제한할 수 있습니다. SharePoint에서는 조직 전체 및 사이트별 도메인 제한 설정을 제공 합니다. 그룹 및 팀 Azure AD의 도메인 허용 및 거부 목록을 사용 합니다. 원치 않는 공유를 방지 하 고 일관 된 사용자 환경을 유지 하려면 두 설정을 모두 구성 해야 합니다.

- [도메인별 SharePoint 및 OneDrive 콘텐츠 공유 제한](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365에서는 *모든 사용자* 를 공유 하는 링크를 사용 하 여 파일 및 폴더의 익명 공유를 허용 합니다. *모든 사용자* 링크를 전달 하 고 링크가 있는 모든 사용자가 공유 항목에 액세스할 수 있습니다. 데이터의 민감도에 따라 *사용자* 의 연결을 완전히 해제 하거나, 연결 권한을 읽기 전용으로 제한 하거나 만료 시간을 설정 하는 등의 작업을 수행 하는 것을 포함 하 여 링크를 사용 하는 방법을 제어 하는 것이 좋습니다.

- [모든 사용자 링크 해제](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [사용자 링크에 대 한 링크 사용 권한 설정](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [모든 사용자 링크의 만료 날짜를 설정합니다.](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

파일 또는 폴더를 공유 하는 경우 사용자는 여러 링크 유형을 선택할 수 있습니다. 실수로 부적절 한 공유의 위험을 줄이기 위해 공유 시 사용자에 게 제공 되는 기본 연결 유형을 변경할 수 있습니다. 예를 들어 *조직 링크의 사용자* 에 게 익명 액세스를 허용 하는 *사용자* 링크에서 기본값을 변경 하면 중요 한 정보가 원치 않는 외부 공유 위험을 줄일 수 있습니다.

- [사이트의 기본 연결 종류 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

조직에 게스트와 공유 해야 하는 중요 한 데이터가 있지만 부적절 한 공유가 염려 되는 경우에는 지정 된 보안 그룹의 구성원에 게 파일 및 폴더의 외부 공유를 제한할 수 있습니다. 이러한 방식으로 특정 사용자 그룹에 대 한 외부 공유를 제한 하거나, 사용자가 보안 그룹에 추가 하기 전에 적절 한 외부 공유에 대 한 교육을 받도록 해야 할 수 있습니다.

- [지정 된 보안 그룹에 대 한 외부 공유 제한](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

그룹 및 팀에는 게스트 액세스를 허용 하거나 거부 하는 조직 수준 설정이 있습니다. [Microsoft PowerShell을 사용 하 여 특정 팀 이나 그룹에 대 한 게스트 액세스를 제한할](per-group-guest-access.md)수 있지만 민감도 레이블을 통해이 작업을 수행 하는 것이 좋습니다. 민감도 레이블을 사용 하면 적용 된 레이블을 기반으로 게스트 액세스를 자동으로 허용 하거나 거부할 수 있습니다.

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365에서는 다양 한 정보 공유 방법을 제공 합니다. 중요 한 정보가 있는 경우 공유 방식을 제한 하려면 공유 제한 옵션을 검토 하십시오.

- [Microsoft 365에서의 공유 제한](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

추가 리소스:

- [Microsoft 365와 안전한 협업 설정](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [보안 게스트 공유 환경 만들기](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [B2B 외부 공동 작업을 사용 하도록 설정 하 고 게스트를 초대할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>사용자 관리

조직에서 그룹과 팀이 발전 함에 따라 정기적으로 팀 및 그룹 구성원을 검토 하는 것이 좋습니다. 이는 구성원이 변경 되는 구성원, 중요 한 정보를 포함 하는 팀 및 그룹 또는 게스트가 포함 된 그룹과 특히 유용할 수 있습니다. 이러한 팀 및 그룹에 대 한 액세스 검토를 설정 하는 것이 좋습니다.

- [Azure AD access 검토 란?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

대부분의 조직에서는 공동 작업을 수행 하는 다른 조직이 나 주요 공급 업체와의 비즈니스 협력 관계가 있습니다. 이러한 시나리오에서는 리소스에 대 한 사용자 관리 및 액세스를 관리 하기가 어려울 수 있습니다. 일부 사용자 관리 작업을 자동화 하 여 파트너 조직으로 전환 하는 것도 좋습니다.

- [Azure AD 자격 관리 란?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

팀의 개인 채널을 사용 하면 팀원 간에 범위가 지정 되 고 파일을 공유할 수 있습니다. 특정 비즈니스 요구 사항에 따라이 기능을 허용 하거나 차단 하는 것이 좋습니다.

- [Microsoft 팀의 개인 채널](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Microsoft 팀에서 개인 채널의 수명 주기 관리](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

추가 리소스:

- [Azure Active Directory Id 거 버 넌 스](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>관련 항목

[Microsoft Teams의 보안 및 규정 준수](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[SharePoint의 공유 설정 관리](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Yammer에서 외부 네트워크 생성 및 관리](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[세 가지 보호 계층으로 Teams 구성](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)

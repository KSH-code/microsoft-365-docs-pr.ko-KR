---
title: Microsoft 365, Teams 및 SharePoint
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365, 그룹 및 Teams 액세스 제어에 대해 SharePoint.
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214205"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365, Teams 및 SharePoint

사용자가 그룹, 팀 및 팀의 리소스에 액세스하는 방법을 제어할 수 있는 많은 컨트롤이 SharePoint. 이러한 옵션을 검토하고 비즈니스 요구, 데이터의 민감도 및 사용자가 공동 작업해야 하는 사용자의 범위에 매핑되는 방법을 고려합니다.

다음 표에서는 이 문서에서 사용할 수 있는 액세스 컨트롤에 대한 빠른 참조를 Microsoft 365. 추가 정보는 다음 섹션에서 제공됩니다.

|범주|설명|참조|
|:-------|:----------|:--------|
|구성원|||
||비공개 팀 검색|[2013에서 비공개 팀 검색 Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||규칙을 기반으로 하는 동적 그룹 구성원|[2016에서 동적 그룹을 만들거나 Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||파일, 폴더 및 사이트를 공유할 수 있는 사용자 제어|[액세스 요청 설정 및 관리](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|조건부 액세스|||
||다단계 인증|[Azure AD 다단계 인증](/azure/active-directory/authentication/concept-mfa-howitworks)|
||그룹, 팀 또는 사이트 민감도에 따라 장치 액세스를 제어합니다.|[민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)|
||관리되지 않는 장치에 대한 사이트 액세스를 제한합니다.|[관리되지 SharePoint 액세스 제어](/sharepoint/control-access-from-unmanaged-devices)|
||위치에 따라 사이트 액세스 제어|[네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어](/sharepoint/control-access-based-on-network-location)|
|게스트 액세스|||
||지정된 도메인에서 SharePoint 공유를 허용하거나 차단합니다.|[도메인별 SharePoint 및 OneDrive 콘텐츠의 공유 제한](/sharepoint/restricted-domains-sharing)|
||지정된 도메인에서 팀 또는 그룹 구성원을 허용하거나 차단합니다.|[특정 조직의 B2B 사용자에 대한 초대 허용 또는 차단](/azure/active-directory/b2b/allow-deny-list)|
||익명 공유를 방지합니다.|[모든 사용자 링크 해제](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||익명 액세스 링크에 대한 사용 권한을 제어합니다.|[모든 사용자 링크에 대한 링크 사용 권한 설정](./best-practices-anonymous-sharing.md#set-link-permissions)|
||익명 공유 링크의 만료를 제어합니다.|[모든 사용자 링크의 만료 날짜를 설정합니다.](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||기본적으로 사용자에게 표시되는 공유 링크 유형을 제어합니다.|[Change the default link type for a site](/sharepoint/change-default-sharing-link)(사이트의 기본 링크 유형 변경)|
||외부 공유를 특정 사용자로 제한합니다.|[지정된 보안 그룹으로 외부 공유 제한](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||정보 민감도에 따라 그룹, 팀 또는 사이트에 대한 게스트 액세스를 제어합니다.|[민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)|
||공유 옵션을 해제합니다.|[Microsoft 365에서의 공유 제한](./microsoft-365-limit-sharing.md)|
|사용자 관리|||
||정기적으로 팀 및 그룹 구성원을 검토합니다.|[Azure AD 액세스 검토란?](/azure/active-directory/governance/access-reviews-overview)|
||그룹 및 팀에 대한 액세스 관리를 자동화합니다.|[Azure AD 권리 관리란?](/azure/active-directory/governance/entitlement-management-overview)|
||사용자가 비공개 채널을 만들 수 있도록 허용하거나 Teams.|[개인 채널의 수명 주기를 Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>구성원

팀과 그룹의 구성원 자격은 소유자가 제어합니다. 구성원은 다른 사용자들을 초대할 수 있지만 초대는 승인을 위해 소유자에게 전송됩니다. 공개 팀과 그룹은 조직의 모든 사람이 검색할 수 있는 반면 비공개 팀과 그룹을 검색할 수 있는지 여부를 제어할 수 있습니다.

- [2013에서 비공개 팀 검색 Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

부서와 같은 일부 기준에 따라 그룹 또는 팀의 구성원 자격을 동적으로 관리할 수 있습니다. 이 경우 구성원과 소유자는 팀에 다른 사용자들을 초대할 수 없습니다. 동적 그룹은 사용자 정의 메타데이터를 사용하여 Azure Active Directory 구성원을 제어합니다. 사용 하는 메타데이터가 완전하고 잘못된 메타데이터로 인해 사용자가 그룹에서 삭제되거나 잘못된 사용자가 추가될 수 있는 최신 메타데이터를 최신으로 유지해야 합니다.

- [2016에서 동적 그룹을 만들거나 Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint 사이트는 그룹 또는 팀 구성원과는 별도로 소유자, 구성원 및 방문자를 추가할 수 있는 기능을 제공합니다. 요구 사항에 따라 사이트에 초대할 수 있는 사용자만 제한할 수 있습니다. 또한 특정 사이트의 정보의 민감도에 따라 파일 및 폴더를 공유할 수 있는 사용자도 제한할 수 있습니다. 이러한 제한은 팀, 그룹 또는 사이트 소유자가 구성합니다.

- [액세스 요청 설정 및 관리](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>조건부 액세스

이 Microsoft 365 조직 내부 및 외부의 사용자 모두에 대해 다단계 인증을 요구할 수 있습니다. 두 번째 인증 단계에 대한 메시지가 표시될 때 상황에는 여러 가지 옵션이 있습니다. 조직에 다단계 인증을 배포하는 것이 좋습니다.

- [Azure AD 다단계 인증](/azure/active-directory/authentication/concept-mfa-howitworks)

일부 그룹 및 팀에 중요한 정보가 있는 경우 그룹 또는 팀의 민감도 레이블에 따라 장치 관리 정책을 적용할 수 있습니다. 관리되지 않는 장치에서 액세스를 완전히 차단하거나 제한된 웹 전용 액세스를 허용할 수 있습니다.

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)

이 SharePoint 지정된 네트워크 위치에서 사이트에 대한 액세스를 제한할 수 있습니다.

- [네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어](/sharepoint/control-access-based-on-network-location)


추가 리소스:

- [조건부 액세스 배포 계획](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune 개요](/mem/intune/fundamentals/what-is-intune)

- [관리되지 SharePoint 액세스 제어](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>게스트 액세스

전자 메일 주소의 도메인에 따라 게스트를 제한할 수 있습니다. SharePoint 조직 전체 및 사이트별 도메인 제한 설정을 제공합니다. 그룹 및 Teams Azure AD의 도메인 허용 및 거부 목록을 사용하세요. 원치 않는 공유를 방지하고 일관된 사용자 환경을 보장하도록 두 설정을 모두 구성해야 합니다.

- [도메인별 SharePoint 및 OneDrive 콘텐츠의 공유 제한](/sharepoint/restricted-domains-sharing)

- [특정 조직의 B2B 사용자에 대한 초대 허용 또는 차단](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 공유 링크를 사용하여 파일 및 폴더를 *익명으로* 공유할 수 있습니다. *모든* 사용자 링크를 전달할 수 있으며 링크가 있는 모든 사람은 공유 항목에 액세스할 수 있습니다. 데이터의 민감도에 따라 모든 사용자 링크  사용 방법(전체 해제, 링크 사용 권한을 읽기 전용으로 제한 또는 만료 시간 설정 포함)을 고려합니다.

- [모든 사용자 링크 해제](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [모든 사용자 링크에 대한 링크 사용 권한 설정](./best-practices-anonymous-sharing.md#set-link-permissions)

- [모든 사용자 링크의 만료 날짜를 설정합니다.](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

파일 또는 폴더를 공유할 때 선택할 수 있는 여러 링크 유형이 있습니다. 실수로 부적절한 공유의 위험을 줄이기 위해 사용자가 공유할 때 사용자에게 제공된 기본 링크 유형을 변경할 수 있습니다. 예를 들어 익명 액세스를  허용하는 모든 사용자 링크에서 기본값을 조직의 사용자 링크로 변경하면 중요한 정보가 원치 않는 외부 공유 위험을 줄일 수 있습니다. 

- [Change the default link type for a site](/sharepoint/change-default-sharing-link)(사이트의 기본 링크 유형 변경)

조직에 게스트와 공유해야 하는 중요한 데이터가 있지만 부적절한 공유가 우려되는 경우 파일 및 폴더의 외부 공유를 지정된 보안 그룹의 구성원으로 제한할 수 있습니다. 이렇게 하면 특정 사용자 그룹에 외부적으로 공유를 제한하거나 사용자가 보안 그룹에 추가하기 전에 적절한 외부 공유에 대한 교육을 하도록 요구할 수 있습니다.

- [지정된 보안 그룹으로 외부 공유 제한](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

그룹 및 Teams 게스트 액세스를 허용하거나 거부하는 조직 수준 설정이 있습니다. [Microsoft PowerShell을](per-group-guest-access.md)사용하여 게스트 액세스를 특정 팀 또는 그룹으로 제한할 수 있는 반면 민감도 레이블을 사용하여 이 작업을 하는 것이 좋습니다. 민감도 레이블을 사용하면 적용된 레이블에 따라 게스트 액세스를 자동으로 허용하거나 거부할 수 있습니다.

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)

게스트를 그룹 및 팀에 자주 초대하는 환경에서는 정기적으로 예약된 게스트 액세스 검토를 설정하는 것이 좋습니다. 소유자는 그룹 및 팀의 게스트를 검토하고 액세스를 승인하거나 거부하라는 메시지를 표시할 수 있습니다.

- [게스트 액세스 검토 설정](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 정보를 공유하는 다양한 방법을 제공합니다. 중요한 정보가 있는 경우 공유 방법을 제한하려는 경우 공유 제한 옵션을 검토하세요.

- [Microsoft 365에서의 공유 제한](./microsoft-365-limit-sharing.md)

추가 리소스:

- [Microsoft 365를 사용하여 안전한 공동 작업 설정](./setup-secure-collaboration-with-teams.md)

- [인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례](./best-practices-anonymous-sharing.md)

- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](./share-limit-accidental-exposure.md)

- [보안 게스트 공유 환경 만들기](./create-secure-guest-sharing-environment.md)

- [B2B 외부 공동 작업을 활성화하고 게스트를 초대할 수 있는 사용자 관리](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>사용자 관리

그룹과 팀이 조직에서 발전함에 따라 팀 및 그룹 구성원을 정기적으로 검토하는 것이 좋습니다. 이 기능은 구성원이 변경되거나 중요한 정보를 포함하는 팀 및 그룹 또는 게스트를 포함하는 그룹에 특히 유용할 수 있습니다. 이러한 팀 및 그룹에 대한 액세스 검토를 설정할 수 있습니다.

- [Azure AD 액세스 검토란?](/azure/active-directory/governance/access-reviews-overview)

많은 조직에서는 다른 조직 또는 주요 공급업체와의 비즈니스 파트너 관계에 대해 심도 깊은 공동 작업을 합니다. 사용자 관리 및 리소스 액세스는 이러한 시나리오에서 관리하기 어려울 수 있습니다. 일부 사용자 관리 작업을 자동화하고 일부 사용자 관리 작업을 파트너 조직으로 전환하는 것을 고려합니다.

- [Azure AD 권리 관리란?](/azure/active-directory/governance/entitlement-management-overview)

비공개 채널은 Teams 구성원의 하위 집합 간에 범위가 지정되는 대화 및 파일 공유를 허용합니다. 특정 비즈니스 요구에 따라 이 기능을 허용하거나 차단할 수 있습니다.

- [개인 채널의 Microsoft Teams](/MicrosoftTeams/private-channels)

- [개인 채널의 수명 주기를 Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

추가 리소스:

- [Azure Active Directory ID 거버넌스](/azure/active-directory/governance)

## <a name="related-topics"></a>관련 항목

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[Microsoft Teams의 보안 및 규정 준수](/microsoftteams/security-compliance-overview)

[2016에서 공유 설정 SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Yammer에서 외부 네트워크 생성 및 관리](/yammer/work-with-external-users/create-and-manage-an-external-network)

[3 계층 보안으로 Teams 구성](./configure-teams-three-tiers-protection.md)
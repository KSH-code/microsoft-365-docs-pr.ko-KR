---
title: 권장 Teams 정책 - Microsoft 365 정책에 대한 | Microsoft Docs
description: 통신 및 파일 액세스를 보호하는 방법에 대한 Microsoft 권장 Teams 설명
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: b135c6dd691607dd128bfd83e0d2b484bb3a97ae
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213265"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>채팅, 그룹 및 Teams 보안에 대한 정책 권장 사항

이 문서에서는 권장되는 ID 및 장치 액세스 정책을 구현하여 파일 및 일정과 같은 Microsoft Teams, 그룹 및 콘텐츠를 보호하는 방법을 설명합니다. 이 지침은 일반적인 [](identity-access-policies.md)ID 및 장치 액세스 정책 에 따라 작성된 것으로, 특정 Teams 추가 정보를 제공합니다. 다른 Teams 통합되어 있기 때문에 전자 메일 [](sharepoint-file-access-policies.md) 보안에 대한 SharePoint 사이트 및 파일 보안에 대한 정책 권장 사항도 [참조하세요.](secure-email-recommended-policies.md)

이러한 권장 사항은 요구의 세분성에 따라 적용할 수 있는 Teams 기준, 중요 및 높은 규제의 세 가지 보안 및 보호 계층을 기반으로 합니다. 이러한 보안 계층 및 ID 및 장치 액세스 구성에서 이러한 권장 사항에서 참조하는 권장 정책에 대해 자세히 확인할 [수 있습니다.](microsoft-365-policies-configurations.md)

조직 외부의 사용자를 Teams 특정 인증 상황을 다루기 위해 Teams 배포와 관련한 추가 권장 사항이 이 문서에 포함되어 있습니다. 완전한 보안 환경을 위해 이 지침을 따라야 합니다.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>다른 종속 Teams 시작하기

종속 서비스를 사용하도록 설정할 필요는 Microsoft Teams. 이러한 서비스는 모두 "작동"합니다. 그러나 다음과 같은 서비스 관련 요소를 관리할 수 있도록 준비해야 합니다.

- Microsoft 365 그룹
- SharePoint 팀 사이트
- 비즈니스용 OneDrive
- Exchange 사서함
- 비디오 스트림 및 Planner 계획(이러한 서비스가 활성화된 경우)

## <a name="updating-common-policies-to-include-teams"></a>공용 정책을 포함하기 위해 Teams

채팅, 그룹 및 콘텐츠 Teams 보호하기 위해 다음 다이어그램에서는 공통 ID 및 장치 액세스 정책에서 업데이트할 정책을 보여 제공합니다. 업데이트할 각 정책에 대해 클라우드 Teams 및 종속 서비스가 클라우드 앱 할당에 포함해야 합니다.

[![사용자 및 해당 종속 서비스에 대한 액세스를 보호하기 위한 Teams 업데이트 요약입니다.](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

이러한 서비스는 비즈니스용 클라우드 앱 할당에 포함할 종속 Teams.

- Microsoft Teams
- SharePoint 및 비즈니스용 OneDrive
- Exchange Online
- 비즈니스용 Skype Online
- Microsoft Stream(모임 녹음/녹화)
- Microsoft Planner(Planner 작업 및 데이터 계획)

이 표에는 재시도해야 하는 정책과 모든 응용 프로그램에 대해 더 광범위한 정책이 설정된 공통 [ID](identity-access-policies.md)및 장치 액세스 정책의 각 정책에 Office 나열되어 있습니다.

|보호 수준|정책|구현에 대한 Teams 정보|
|---|---|---|
|**기준**|[로그인 위험이 중간 또는 높음인 경우 MFA *필요*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|앱 Teams 종속 서비스가 포함해야 합니다. Teams 게스트 액세스 및 외부 액세스 규칙도 고려할 수 있습니다. 이 문서 의 부분에서 이러한 규칙에 대해 자세히 알아보게 됩니다.|
||[최신 인증을 지원하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|클라우드 Teams 할당에 서비스 및 종속 서비스를 포함합니다.|
||[위험이 높은 사용자는 암호를 변경해야 함](identity-access-policies.md#high-risk-users-must-change-password)|사용자가 Teams 높은 위험 활동이 감지된 경우 로그인할 때 암호를 강제로 변경합니다. 앱 Teams 종속 서비스가 포함해야 합니다.|
||[APP 데이터 보호 정책 적용](identity-access-policies.md#apply-app-data-protection-policies)|앱 Teams 종속 서비스가 포함해야 합니다. 각 플랫폼(iOS, Android, Windows)에 대한 정책을 업데이트합니다.|
||[장치 준수 정책 정의](identity-access-policies.md#define-device-compliance-policies)|이 Teams 및 종속 서비스를 포함합니다.|
||[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|이 Teams 및 종속 서비스를 포함합니다.|
|**중요**|[로그인 위험이 낮거나 보통 또는 *높을* 때 MFA *필요*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams 게스트 액세스 및 외부 액세스 규칙도 고려할 수 있습니다. 이 문서 의 부분에서 이러한 규칙에 대해 자세히 알아보게 됩니다. 이 Teams 및 종속 서비스를 포함합니다.|
||[호환 PC 및 *모바일* 장치 필요](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|이 Teams 및 종속 서비스를 포함합니다.|
|**매우 엄격한 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|사용자 ID에 관계없이 조직에서 MFA가 사용됩니다. 이 Teams 및 종속 서비스를 포함합니다. |
|

## <a name="teams-dependent-services-architecture"></a>Teams 서비스 아키텍처

참조를 위해 다음 다이어그램에서는 사용하는 서비스를 Teams 있습니다. 자세한 내용은 IT 설계자용 Microsoft Teams 및 관련 생산성 Microsoft 365 [참조하세요.](../../solutions/productivity-illustrations.md)

[![Teams, Teams 및 SharePoint 종속성 비즈니스용 OneDrive 다이어그램을 Exchange.](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[이 이미지의 더 큰 버전 참조](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>사용자에 대한 게스트 및 Teams

Microsoft Teams 다음 액세스 유형을 정의합니다.

- **게스트 액세스는** 팀의 구성원으로 추가할 수 있으며 팀의 통신 및 리소스에 대한 모든 권한을 가지는 게스트 또는 외부 사용자에 대해 Azure AD B2B 계정을 사용합니다.

- **외부 액세스는** Azure AD B2B 계정이 없는 외부 사용자를 위한 것입니다. 외부 액세스에는 초대 및 통화, 채팅 및 모임 참가가 포함할 수 있지만 팀 구성원 자격 및 팀 리소스 액세스는 포함하지 않습니다.

조건부 액세스 정책은 해당 Azure AD Teams 계정이 있기 때문에 정책의 게스트 액세스에만 적용됩니다.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Azure AD B2B 계정이 있는 게스트 및 외부 사용자에 대한 액세스를 허용하는 권장 정책은 게스트 및 외부 B2B 계정 액세스를 허용하는 [정책을 참조하세요.](identity-access-policies-guest-access.md)

### <a name="guest-access-in-teams"></a>Teams의 게스트 액세스

관리자는 비즈니스 또는 조직 내부의 사용자에 대한 정책 외에도, 게스트 액세스를 허용하여 비즈니스 또는 조직 외부의 사용자가 Teams 리소스에 액세스하고 그룹 대화, 채팅 및 모임과 같은 내부 사용자와 상호 작용할 수 있도록 허용할 수 있습니다.

게스트 액세스 및 게스트 액세스 구현 방법에 대한 자세한 내용은 게스트 액세스 Teams [참조하세요.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>외부 액세스 Teams

외부 액세스는 게스트 액세스와 혼동되는 경우도 있으므로 이러한 두 가지 비 내부 액세스 메커니즘이 서로 다른 액세스 유형임이 명확히 하는 것이 중요합니다.

외부 액세스는 Teams 도메인의 사용자가 외부 도메인의 사용자와 모임을 찾고, 통화하고, 채팅하고, 설정하는 Teams. Teams 관리자가 조직 수준에서 외부 액세스를 구성합니다. 자세한 내용은 [Manage external access in Microsoft Teams.](/microsoftteams/manage-external-access)

외부 액세스 사용자는 게스트 액세스를 통해 추가된 개인보다 액세스 및 기능이 적습니다. 예를 들어 외부 액세스 사용자는 내부 사용자와 채팅할 수 있지만 팀 채널Teams 파일 또는 기타 리소스에는 액세스할 수 없습니다.

외부 액세스는 Azure AD B2B 사용자 계정을 사용하지 않습니다. 따라서 조건부 액세스 정책을 사용하지 않습니다.

## <a name="teams-policies"></a>Teams 정책

위에 나열된 일반적인 정책 외부에는 다양한 정책 Teams 관리하도록 구성해야 하는 특정 정책이 Teams 있습니다.

### <a name="teams-and-channels-policies"></a>Teams 및 채널 정책

Teams 및 채널은 Microsoft Teams 일반적으로 사용되는 두 가지 요소로, 팀과 채널을 사용할 때 사용자가 할 수 있는 작업을 제어할 수 있는 정책이 있습니다. 전역 팀을 만들 수 있는 반면 조직에 사용자가 5,000명 이하인 경우 조직 요구에 따라 특정 목적을 위해 소규모 팀과 채널을 구성하는 것이 도움이 될 수 있습니다.

기본 정책을 변경하거나 사용자 지정 정책을 만드는 것이 좋습니다. 정책 관리에 대한 자세한 내용은 에서 팀 정책 [Microsoft Teams.](/microsoftteams/teams-policies)

### <a name="messaging-policies"></a>메시징 정책

메시징 또는 채팅은 기본 글로벌 정책 또는 사용자 지정 정책을 통해 관리할 수도 있으며, 이를 통해 사용자가 조직에 적합한 방식으로 서로 통신하는 데 도움이 될 수 있습니다. 이 정보는 [Managing messaging policies in Teams.](/microsoftteams/messaging-policies-in-teams)

### <a name="meeting-policies"></a>모임 정책

모임에 Teams 정책을 계획하고 구현하지 않으면 정책에 대한 설명이 Teams 없습니다. 모임은 사용자들이 한 Teams 공식적으로 만나고 발표하고 모임과 관련된 콘텐츠를 공유할 수 있도록 하는 중요한 구성 요소입니다. 모임과 관련한 조직에 적합한 정책을 설정하는 것이 중요합니다.

자세한 내용은 에서 [모임 정책 관리를 Teams.](/microsoftteams/meeting-policies-in-teams)

### <a name="app-permission-policies"></a>앱 사용 권한 정책

Teams 통해 채널 또는 개인 채팅과 같은 다양한 장소에서 앱을 사용할 수도 있습니다. 앱을 추가 및 사용할 수 있는 내용 및 안전한 콘텐츠가 풍부한 환경을 유지 관리하는 데 필요한 위치와 관련한 정책을 유지하는 것이 중요합니다.

앱 사용 권한 정책에 대한 자세한 내용은 에서 앱 권한 정책 [관리를 Microsoft Teams.](/microsoftteams/teams-app-permission-policies)

## <a name="next-steps"></a>다음 단계

![4단계: 클라우드 Microsoft 365 정책.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

조건부 액세스 정책 구성:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
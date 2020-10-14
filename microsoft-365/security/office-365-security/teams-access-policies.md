---
title: 권장 팀 정책-Microsoft 365 for enterprise | Microsoft Docs
description: 팀 통신과 파일 액세스를 보호 하는 방법에 대 한 Microsoft 권장 사항에 대 한 정책에 대해 설명 합니다.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
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
ms.openlocfilehash: 56b712c73d63bfcb06d5d35d627facb229668c59
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464147"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>팀 대화방, 그룹 및 파일을 보호 하기 위한 정책 권장 사항

이 문서에서는 Microsoft 팀의 채팅, 그룹, 콘텐츠, 파일 및 일정 등을 보호 하기 위해 권장 되는 id 및 장치 액세스 정책을 구현 하는 방법을 설명 합니다. 이 지침은 [일반적인 id 및 장치 액세스 정책](identity-access-policies.md)에 따라 구성 되며, 이러한 정책은 팀 관련 추가 정보와 함께 작성 됩니다. 팀은 다른 제품과 통합 되므로 [전자 메일을 보호 하기 위한 정책](secure-email-recommended-policies.md)권장 사항 및 [SharePoint 사이트를 보호 하기 위한 정책 권장](sharepoint-file-access-policies.md) 사항도 참조 하세요.

이러한 권장 사항은 초기 계획, 중요 및 높은 규제의 요구 사항에 따라 적용할 수 있는 팀에 대 한 세 가지 보안 및 보호 계층을 기반으로 합니다. 이러한 보안 계층에 대 한 자세한 내용을 확인 하 고 [id 및 장치 액세스 구성](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조 하는 권장 정책을 확인할 수 있습니다.

이 문서에는 조직 외부의 사용자를 비롯 한 특정 인증 환경을 다루는 팀 구축과 관련 된 추가 권장 사항이 포함 되어 있습니다. 이 지침을 따라 전체 보안 환경을 확인 해야 합니다.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>다른 종속 서비스 이전의 팀 시작

Microsoft 팀을 시작 하기 위해 종속 서비스를 사용 하도록 설정할 필요는 없습니다. 이러한 모든 작업은 "작동" 합니다. 그러나 다음을 관리할 준비를 해야 합니다.

- Microsoft 365 그룹
- SharePoint 팀 사이트
- 비즈니스용 OneDrive
- Exchange 사서함
- Stream 비디오 및 Planner 계획 (이러한 서비스를 사용 하는 경우)

## <a name="updating-common-policies-to-include-teams"></a>팀을 포함 하도록 일반 정책 업데이트

다음 다이어그램에서는 팀의 채팅, 그룹 및 콘텐츠를 보호 하기 위해 일반 id 및 장치 액세스 정책에서 업데이트할 정책을 보여 줍니다. 업데이트할 각 정책에 대해 팀 및 종속 서비스가 클라우드 앱 할당에 포함 되어 있는지 확인 합니다.

[![팀 및 해당 종속 서비스에 대 한 액세스를 보호 하기 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[이 이미지의 더 큰 버전 보기](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

다음은 팀에 대 한 클라우드 앱 할당에 포함할 종속 서비스입니다.

- Microsoft Teams
- SharePoint 및 비즈니스용 OneDrive
- Exchange Online
- 비즈니스용 Skype Online
- Microsoft Stream (모임 녹음/녹화)
- Microsoft Planner (Planner 작업 및 계획 데이터)

이 표에는 모든 Office 응용 프로그램에 대해 설정 된 보다 광범위 한 정책을 가진 [일반 id 및 장치 액세스 정책](identity-access-policies.md)에서 다시 검토 하 고 각 정책에 연결 해야 하는 정책이 나열 되어 있습니다.

|보호 수준|정책|팀 구현에 대 한 추가 정보|
|:---------------|:-------|:----------------|
|**기준**|[로그인 위험이 *보통* 또는 *높을* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|팀 및 종속 서비스가 앱 목록에 포함 되어 있어야 합니다. 팀에서 게스트 액세스 및 외부 액세스 규칙을 고려해 야 하는 경우이 문서의 뒷부분에 나오는 이러한 항목에 대해 자세히 알아볼 수 있습니다.|
|        |[최신 인증을 지원하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|클라우드 앱 할당에 팀 및 종속 서비스를 포함 합니다.|
|        |[위험이 높은 사용자는 암호를 변경해야 함](identity-access-policies.md#high-risk-users-must-change-password)|계정에 대해 높은 위험 활동이 검색 되는 경우 팀 사용자가 로그인 할 때 암호를 변경 하도록 강제 적용 합니다. 팀 및 종속 서비스가 앱 목록에 포함 되어 있어야 합니다.|
|        |[앱 데이터 보호 정책 적용](identity-access-policies.md#apply-app-data-protection-policies)|팀 및 종속 서비스가 앱 목록에 포함 되어 있어야 합니다. 각 플랫폼 (iOS, Android, Windows)에 대 한 정책을 업데이트 합니다.|
|        |[장치 준수 정책 정의](identity-access-policies.md#define-device-compliance-policies)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|        |[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|**중요**|[로그인 위험이 *낮은* *경우 MFA* 필요 *high*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|팀에서 게스트 액세스 및 외부 액세스 규칙을 고려해 야 하는 경우이 문서의 뒷부분에 나오는 이러한 항목에 대해 자세히 알아볼 수 있습니다. 이 정책에 팀 및 종속 서비스를 포함 합니다.|
|         |[준수 Pc *및* 모바일 장치 요구](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|**매우 엄격한 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|사용자 id와 상관 없이 MFA는 조직에서 사용 됩니다. 이 정책에 팀 및 종속 서비스를 포함 합니다. |
| | |

## <a name="teams-dependent-services-architecture"></a>팀 종속 서비스 아키텍처

참조용으로 다음 다이어그램에는 서비스 팀이 의존 하는 것이 나와 있습니다. 자세한 내용 및 추가 그림은 [IT 설계자 용 microsoft 365의 Microsoft 팀 및 관련 생산성 서비스](../../solutions/productivity-illustrations.md)를 참조 하세요.

[![SharePoint, 비즈니스용 OneDrive 및 Exchange의 팀 종속성을 보여 주는 다이어그램](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[이 이미지의 더 큰 버전 보기](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>게스트 및 팀에 대 한 외부 액세스

Microsoft 팀에서는 다음을 정의 합니다.

- **게스트 액세스** 에서는 팀 구성원으로 추가할 수 있는 게스트 또는 외부 사용자에 대해 AZURE AD B2B 계정을 사용 하며,이 경우 팀의 통신 및 리소스에 대 한 모든 고유한 액세스 권한을 갖습니다.

- **외부 액세스** 는 AZURE AD B2B 계정이 없는 외부 사용자를 위한 것입니다. 외부 액세스에는 초대 및 참여를 포함할 수 있지만 팀 구성원 자격 및 팀의 리소스에 대 한 액세스는 포함 되지 않습니다.

조건부 액세스 정책은 해당 Azure AD B2B 계정이 있기 때문에 팀의 게스트 액세스에만 적용 됩니다.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

게스트 및 Azure AD B2B 계정을 사용 하는 외부 사용자에 대 한 액세스를 허용 하는 권장 정책에 대해서는 [게스트 및 외부 B2B 계정 액세스를 허용 하기 위한 정책을](identity-access-policies-guest-access.md)참조 하세요.

### <a name="guest-access-in-teams"></a>Teams의 게스트 액세스

비즈니스 또는 조직 내부에 있는 사용자에 대 한 정책 외에도 관리자는 게스트 액세스를 허용 하 고 사용자가 비즈니스 또는 조직 외부에 있는 사용자가 팀 리소스에 액세스 하 고 그룹 대화, 채팅 및 모임 등의 내부 사람들과 상호 작용할 수 있습니다. 

게스트 액세스에 대 한 자세한 내용과 구현 방법에 대 한 자세한 내용은  [팀 게스트 액세스](https://docs.microsoft.com/microsoftteams/guest-access)를 참조 하세요.

### <a name="external-access-in-teams"></a>팀의 외부 액세스

외부 액세스는 게스트 액세스와 혼동 하는 경우가 많지만, 이러한 두 가지 비 내부 액세스 메커니즘이 실제로 서로 다른 지는 것이 중요 합니다. 

외부 액세스는 팀의 사용자와 함께 회의를 찾고, 통화 하 고, 채팅 하 고, 사용자와 모임을 설정 하는 데 사용 됩니다. 팀 관리자는 조직 수준에서 외부 액세스를 구성 합니다. 자세한 내용은 [Microsoft 팀에서 외부 액세스 관리](https://docs.microsoft.com/microsoftteams/manage-external-access)를 참조 하세요.

외부 액세스 사용자는 게스트 액세스를 통해 추가 된 개인 보다 더 적은 액세스 및 기능을 사용할 수 있습니다. 예를 들어 외부 액세스 사용자는 팀과의 내부 사용자와 채팅을 할 수 있지만 팀 채널, 파일 또는 기타 리소스에는 액세스할 수 없습니다.

외부 액세스는 Azure AD B2B 사용자 계정을 사용 하지 않으므로 조건부 액세스 정책을 사용 하지 않습니다. 

## <a name="teams-policies"></a>팀 정책

위에 나열 된 일반적인 정책 외에도 다양 한 팀 기능을 관리 하기 위해 구성 해야 하는 팀 관련 정책이 있습니다.

### <a name="teams-and-channels-policies"></a>팀 및 채널 정책

팀과 채널은 Microsoft 팀에서 일반적으로 사용 되는 두 가지 요소 이며, 팀 및 채널을 사용할 때 사용자가 수행할 수 있는 작업을 제어 하기 위해 배치할 수 있는 정책이 있습니다. 전역 팀을 만들 수 있지만 조직에 사용자가 5000 명 이하인 경우 조직의 요구 사항에 맞게 특정 목적으로 더 작은 팀과 채널을 사용 하는 것이 도움이 될 것입니다.

기본 정책을 변경 하거나 사용자 지정 정책을 만드는 것이 권장 되며,이 링크에서 정책 관리에 대 한 자세한 내용을 보려면 [Microsoft 팀에서 팀 정책 관리](https://docs.microsoft.com/microsoftteams/teams-policies)를 선택 합니다.

### <a name="messaging-policies"></a>메시징 정책

메시징 또는 채팅은 기본 글로벌 정책 또는 사용자 지정 정책을 통해 관리할 수도 있으며,이를 통해 사용자가 조직에 적합 한 방식으로 서로 통신 하는 데 도움이 될 수 있습니다. 이 정보는 [팀의 메시징 정책 관리](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)에서 검토할 수 있습니다.

### <a name="meeting-policies"></a>모임 정책

팀 회의에 대 한 정책을 계획 및 구현 하지 않으면 팀에 대 한 토론이 완료 되지 않습니다. 회의는 팀의 필수 구성 요소 이며, 사용자가 동시에 여러 사용자에 게 공식적으로 회의를 하 고 소개 하 고 모임에 관련 된 콘텐츠를 공유할 수 있도록 합니다. 조직에서 모임에 적합 한 정책을 설정 하는 것은 필수 사항입니다.

자세한 내용은 [팀에서 모임 정책 관리](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 를 검토 하세요.

### <a name="app-permission-policies"></a>앱 권한 정책

또한 팀에서는 채널 또는 개인 채팅 등의 다양 한 위치에서 앱을 사용할 수 있습니다. 어떤 앱을 추가 하 고 사용할 수 있는지에 대 한 정책이 있고, 여기서는 보안이 향상 된 콘텐츠 환경을 유지 관리 하는 데 필수적입니다.

앱 사용 권한 정책에 대 한 자세한 내용은 [Microsoft 팀에서 앱 사용 권한 정책 관리](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)를 참조 하세요.

## <a name="next-steps"></a>다음 단계

![4 단계: Microsoft 365 클라우드 앱에 대 한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

다음에 대 한 조건부 액세스 정책 구성:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)


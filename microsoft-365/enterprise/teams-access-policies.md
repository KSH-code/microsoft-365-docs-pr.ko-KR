---
title: 권장 팀 정책-Microsoft 365 Enterprise | Microsoft Docs
description: 팀 통신과 파일 액세스를 보호 하는 방법에 대 한 Microsoft 권장 사항에 대 한 정책에 대해 설명 합니다.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 052edafa64f2704fb5a6df525b0ad5609ddc72b9
ms.sourcegitcommit: 8e8230ceab480a5f1506e31de828f04f5590a350
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42959197"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>팀 대화방, 그룹 및 파일을 보호 하기 위한 정책 권장 사항

이 문서에서는 팀 대화방, 그룹 및 파일 및 일정과 같은 콘텐츠를 보호 하기 위해 권장 되는 id 및 장치 액세스 정책을 구현 하는 방법을 설명 합니다. 이 지침은 [일반적인 id 및 장치 액세스 정책](identity-access-policies.md)에 따라 구성 되며, 이러한 정책은 팀 관련 추가 정보와 함께 작성 됩니다. 팀은 다른 제품과 통합 되므로 [전자 메일을 보호 하기 위한 정책](secure-email-recommended-policies.md)권장 사항 및 [SharePoint 사이트를 보호 하기 위한 정책 권장](sharepoint-file-access-policies.md) 사항도 참조 하세요.

이러한 권장 사항은 초기 계획, 중요 및 높은 규제의 요구 사항에 따라 적용할 수 있는 팀에 대 한 세 가지 보안 및 보호 계층을 기반으로 합니다. 이러한 보안 계층에 대 한 자세한 내용을 확인 하 고 [id 및 장치 액세스 구성](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조 하는 권장 정책을 확인할 수 있습니다.

이 문서에는 조직 외부의 사용자를 비롯 한 특정 인증 환경을 다루는 팀 구축과 관련 된 추가 권장 사항이 포함 되어 있습니다. 이 지침을 따라 전체 보안 환경을 확인 해야 합니다.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>다른 종속 서비스 이전의 팀 시작

Microsoft 팀을 시작 하기 위해 종속 서비스를 사용 하도록 설정할 필요는 없습니다. 모든 작업을 수행 합니다. 그러나 다음을 관리할 준비를 해야 합니다.

- Office 365 그룹
- SharePoint 팀 사이트
- 비즈니스용 OneDrive
- 사서함
- Stream 비디오 및 Planner 계획 (이러한 서비스를 사용 하는 경우)

## <a name="updating-common-policies-to-include-teams"></a>팀을 포함 하도록 일반 정책 업데이트

다음 다이어그램에서는 팀의 채팅, 그룹 및 콘텐츠를 보호 하기 위한 권장 정책 집합을 보여 줍니다. 연필 아이콘은 팀 및 종속 서비스가 클라우드 앱 할당에 포함 되도록 하기 위해 다시 검토 해야 하는 정책을 나타냅니다.

![다양 한 장치에서 Microsoft 팀을 사용 하는 방법을 보여 주는 다이어그램](../media/identity-access-ruleset-teams.png)

다음은 팀에 대 한 클라우드 앱 할당에 포함할 종속 서비스입니다.

- Microsoft Teams
- SharePoint Online 및 비즈니스용 OneDrive
- Exchange Online
- 비즈니스용 Skype Online
- Microsoft Stream (모임 녹음/녹화)
- Microsoft Planner (Planner 작업 및 계획 데이터)

이 표에서는 모든 Office 응용 프로그램에 대해 더 광범위 한 규칙 집합이 포함 된 [일반 id 및 장치 액세스 정책의](identity-access-policies.md)각 정책에 대 한 링크 및 다시 확인 해야 하는 정책을 보여 줍니다.

|보호 수준|정책도|팀 구현에 대 한 추가 정보|
|:---------------|:-------|:----------------|
|**기준선**|[로그인 위험이 *보통* 또는 *높을* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|팀 및 종속 서비스가 앱 목록에 포함 되어 있어야 합니다. 팀에서 게스트 액세스 및 외부 액세스 규칙을 고려해 야 하는 경우이 문서의 뒷부분에 나오는 이러한 항목에 대해 자세히 알아볼 수 있습니다.|
|        |[최신 인증을 지원하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|클라우드 앱 할당에 팀 및 종속 서비스를 포함 합니다.|
|        |[높은 위험 사용자가 암호를 변경 해야 함](identity-access-policies.md#high-risk-users-must-change-password)|계정에 대해 높은 위험 활동이 검색 되는 경우 팀 사용자가 로그인 할 때 암호를 변경 하도록 강제 적용 합니다. 팀 및 종속 서비스가 앱 목록에 포함 되어 있어야 합니다.|
|        |[앱 보호 정책 정의](identity-access-policies.md#define-app-protection-policies)|팀 및 종속 서비스가 앱 목록에 포함 되어 있어야 합니다. 각 플랫폼 (iOS, Android, Windows)에 대 한 정책을 업데이트 합니다.|
|        |[Intune 앱 보호 정책을 지 원하는 앱 필요](identity-access-policies.md#require-apps-that-support-intune-app-protection-policies)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|        |[장치 준수 정책 정의](identity-access-policies.md#define-device-compliance-policies)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|        |[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|**중요**|[로그인 위험이 *낮은* *경우 MFA* 필요 *high*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|팀에서 게스트 액세스 및 외부 액세스 규칙을 고려해 야 하는 경우이 문서의 뒷부분에 나오는 이러한 항목에 대해 자세히 알아볼 수 있습니다. 이 정책에 팀 및 종속 서비스를 포함 합니다.|
|         |[준수 Pc *및* 모바일 장치 요구](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|이 정책에 팀 및 종속 서비스를 포함 합니다.|
|**매우 엄격한 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|사용자 id와 상관 없이 MFA는 조직에서 사용 됩니다. 이 정책에 팀 및 종속 서비스를 포함 합니다.
| | |

## <a name="teams-dependent-services-architecture"></a>팀 종속 서비스 아키텍처

참조용으로 다음 다이어그램에는 서비스 팀이 의존 하는 것이 나와 있습니다. 자세한 내용 및 추가 그림은 [IT 설계자 용 microsoft 365의 Microsoft 팀 및 관련 생산성 서비스](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects)를 참조 하세요.

![SharePoint Online, 비즈니스용 OneDrive 및 Exchange에 대 한 팀 종속성을 보여 주는 다이어그램입니다.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>팀에 대 한 게스트 및 외부 액세스 설정

Azure AD에서 게스트 및 외부 사용자는 동일 합니다. 이러한 두 가지 유형의 사용자는 모두 게스트입니다. 게스트 사용자는 B2B 사용자입니다. Microsoft 팀은 앱에서 게스트 사용자와 외부 사용자를 구분 합니다. 각 사용자 유형은 팀에서 처리 되는 방식을 이해 하는 것이 중요 하지만, 두 유형의 사용자나 Azure AD의 B2B 사용자 이며, B2B 사용자에 게 권장 되는 정책이 두 가지 모두에 적용 됩니다. 게스트 액세스를 허용 하는 권장 정책에 대해서는 [게스트 및 외부 B2B 액세스](identity-access-policies-guest-access.md)를 허용 하기 위한 정책을 참조 하세요.

### <a name="guest-access-in-teams"></a>팀의 게스트 액세스

비즈니스 또는 조직 내부에 있는 사용자에 대 한 정책 외에도 관리자는 게스트 액세스를 사용 하도록 설정 하 여 회사 또는 조직 외부의 사용자가 팀 리소스에 액세스 하 고 상호 작용할 수 있도록 할 수 있습니다. 그룹 대화, 채팅 및 모임 같은 사물에 대 한 내부 사용자입니다. 게스트 액세스에 대 한 자세한 내용은 [팀 게스트 액세스](https://docs.microsoft.com/microsoftteams/guest-access) 링크를 통해 확인할 수 있습니다.

### <a name="external-access-in-teams"></a>팀의 외부 액세스

외부 액세스는 게스트 액세스와 혼동 하는 경우가 많지만, 이러한 두 가지 비 내부 액세스 메커니즘이 실제로 서로 다른 지는 것이 중요 합니다. 게스트 액세스는 사용자를 한 번에 하나씩 추가 하 여 사용자별로 수행 되지만, 관리자가 외부 액세스를 사용 하도록 설정 하면 외부 도메인의 모든 사용자를 동시에 추가할 수 있습니다. 하지만 이러한 외부 사용자는 게스트 액세스를 통해 추가 된 개인에 비해 액세스 및 기능이 적습니다. 외부 액세스 사용자는 팀을 통해 내부 사용자와 채팅을 할 수 있습니다.

외부 액세스에 대 한 자세한 내용을 읽고 필요한 경우이를 구현 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 외부 액세스 관리](https://docs.microsoft.com/microsoftteams/manage-external-access) 를 참조 하세요.

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

[Exchange Online에 대 한 조건부 액세스를 사용 하도록 설정 하는 방법 알아보기](secure-email-recommended-policies.md)



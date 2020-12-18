---
title: 데이터 손실 방지 및 Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 이제 Microsoft Teams 채팅 및 채널에 DLP 정책을 적용할 수 있습니다. 이 문서를 읽고 작동 방식에 대해 자세히 알아보고자 합니다.
ms.openlocfilehash: 3d55c447b2e808af2ac35f04b67a002304e3e9eb
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709540"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>데이터 손실 방지 및 Microsoft Teams

> [!NOTE]
> 데이터 손실 방지 기능은 최근에 Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 정보 보호 및 거버넌스 또는 Office 365 고급 규정 준수 라이선스가 있는 사용자를 위한 Microsoft Teams 채팅 및 채널 메시지에 추가되었습니다. Office 365 및 Microsoft 365 E3에는 SharePoint Online, OneDrive 및 Exchange Online에 대한 DLP 보호가 포함되어 있습니다. 여기에는 Teams에서 SharePoint Online 및 OneDrive를 사용하여 파일을 공유하기 때문에 Teams를 통해 공유되는 파일도 포함됩니다.
Teams 채팅에서 DLP 보호를 지원하려면 E5가 필요합니다.
라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.

> [!IMPORTANT]
> Teams용 DLP는 사용자에게 Exchange Online에 사서함이 있는 경우만 지원됩니다.

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams용 DLP 개요

최근에는 [](data-loss-prevention-policies.md) 비공개 채널 메시지를 포함하여 Microsoft Teams 채팅 및 채널 메시지를 포함하기 위해 DLP(데이터 손실 방지) **기능이 확장했습니다.**


조직에 DLP가 있는 경우 이제 사용자가 Microsoft Teams 채널 또는 채팅 세션에서 중요한 정보를 공유하지 못하게 하는 정책을 정의할 수 있습니다. 다음은 이 보호가 작동하는 방식의 몇 가지 예입니다.

- **예제 1: 메시지의 중요한 정보 보호.** 누군가 Teams 채팅 또는 채널에서 게스트(외부 사용자)와 중요한 정보를 공유하려고 시도하는 경우를 가정해 보세요. 이를 방지하는 DLP 정책이 정의되어 있는 경우 외부 사용자에게 전송되는 중요한 정보가 있는 메시지가 삭제됩니다. 이 문제는 DLP 정책이 구성된 방식에 따라 초 내에 자동으로 수행됩니다.

    > [!NOTE]
    > Microsoft Teams용 DLP는 사용자가 있는 Microsoft Teams 사용자와 공유할 때 중요한 콘텐츠를 차단합니다.<br/>- [팀 및](https://docs.microsoft.com/MicrosoftTeams/guest-access) 채널의 게스트 액세스 또는<br/>- [모임 및](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) 채팅 세션의 외부 액세스 <p>외부 채팅 세션에 대한 DLP는 보낸 사람과 수신자가 둘 다 Teams 전용 모드에 있으며 Microsoft Teams 기본 페더러ation을 사용하는 [경우만 작동됩니다.](https://docs.microsoft.com/microsoftteams/manage-external-access) Teams용 DLP는 비즈니스용 [](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) Skype 또는 네이티브가 아닌 페더타임 채팅 세션과 상호 연동된 메시지를 차단하지 않습니다.

- **예제 2: 문서의 중요한 정보 보호** 누군가 Microsoft Teams 채널 또는 채팅에서 게스트와 문서를 공유하려고 시도하고 문서에 중요한 정보가 포함되어 있는 경우를 가정해 보세요. 이를 방지하는 DLP 정책이 정의되어 있는 경우 해당 사용자에 대해 문서가 열리지 않습니다. 이 경우 보호를 적용하려면 DLP 정책에 SharePoint 및 OneDrive가 포함되어야 합니다. 이 예제는 Microsoft Teams에 표시하는 SharePoint용 DLP의 예로, 사용자에게 Office 365 DLP(Office 365 E3에 포함)에 대한 라이선스가 필요하지만 사용자에게 Office 365 고급 규정 준수 라이선스가 필요하지 않습니다.

## <a name="policy-tips-help-educate-users"></a>정책 팁은 사용자를 교육하는 데 도움이 됩니다.

[Exchange, Outlook,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)웹용 Outlook, SharePoint Online, 비즈니스용 [OneDrive](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)사이트 및 [Office 데스크톱](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)클라이언트에서 DLP가 작동하는 방식과 마찬가지로 작업이 DLP 정책과 충돌할 때 정책 팁이 표시됩니다. 정책 팁의 예는 다음과 같습니다.

![Teams에서 차단된 메시지 알림](../media/dlp-teams-blockedmessage-notification.png)

이 경우 보낸 사람이 Microsoft Teams 채널에서 사회 보장 번호를 공유하려고 시도합니다. What **can I do?** link opens a dialog box that provides options for the sender to resolve the issue. 이 경우 보낸 사람이 정책을 다시 설정하거나 관리자에게 검토 및 해결을 요청할 수 있습니다.

![차단된 메시지를 해결하기 위한 옵션](../media/dlp-teams-blockedmessage-possibleactions.png)

조직에서 사용자가 DLP 정책을 다시 설정하도록 선택할 수 있습니다. 또한 DLP 정책을 구성할 때 기본 정책 팁을 사용하거나 조직의 정책 팁을 사용자 [지정할](#to-customize-policy-tips) 수 있습니다.

보낸 사람이 Teams 채널에서 사회 보장 번호를 공유한 예제로 돌아가면 받는 사람이 본 예는 다음과 같습니다.

![메시지가 차단됩니다.](../media/dlp-teams-blockedmessage-notification-to-user.png)

**What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.

### <a name="to-customize-policy-tips"></a>정책 팁을 사용자 지정

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 [사용 권한을 참조합니다.](data-loss-prevention-policies.md#permissions)

1. 보안 & 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.

2. 데이터 **손실 방지 정책을**  >  **선택하십시오.**

3. 정책을 선택하고 정책 설정 **옆에** 있는 편집을 **선택합니다.**

4. 새 규칙을 만들거나 정책에 대한 기존 규칙을 편집합니다.<br/>![정책에 대한 규칙 편집](../media/dlp-teams-editrule.png)<br/>

5. 사용자 알림 **탭에서** 전자  메일 텍스트 사용자 지정 및/또는 정책 팁 텍스트 **옵션 사용자 지정을** 선택합니다.<br/>![사용자 알림 및 정책 팁 사용자 지정](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 전자 메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정하고 저장을 **선택하십시오.**

7. 정책 설정 **탭에서** 저장을 **선택합니다.**

변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화할 수 있도록 약 1시간을 허용합니다.
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>기존 DLP 정책에 위치로 Microsoft Teams 추가

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 [사용 권한을 참조합니다.](data-loss-prevention-policies.md#permissions)

1. 보안 & 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.

2. 데이터 **손실 방지 정책을**  >  **선택하십시오.**

3. 정책을 선택하고 위치의 값을 **봐야 합니다.** Teams 채팅 및 **채널** 메시지가 표시되어 있는 경우 모두 설정됩니다. 그렇지 않은 경우 편집을 **클릭합니다.**<br/>![기존 정책의 위치](../media/dlp-teams-editexistingpolicy.png)<br/>

4. 상태 **열에서** Teams 채팅 및 채널 메시지에 대한 **정책을 켜야 합니다.**<br/>![Teams 채팅 및 채널용 DLP](../media/dlp-teams-addteamschatschannels.png)<br/>

5. 모든 계정의 기본 설정을 유지하거나 포함할 계정을 지정하거나 제외할 계정을 지정합니다.

6. **저장** 을 클릭합니다.

변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화할 수 있도록 약 1시간을 허용합니다.
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams에 대한 새 DLP 정책 정의

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 [사용 권한을 참조합니다.](data-loss-prevention-policies.md#permissions)

1. 보안 & 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.

2. 데이터 **손실 방지**  >  **정책**  >  **선택 + 정책 만들기.**

3. 서식 파일을 [선택하고](data-loss-prevention-policies.md#dlp-policy-templates)다음을 **선택하십시오.**<br/>이 예제에서는 미국 개인 식별 정보 데이터 템플릿을 선택해야 합니다.<br/>![DLP 정책에 대한 개인 정보 템플릿](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. 정책 **이름 탭에서** 정책의 이름과 설명을 지정하고 다음을 **선택합니다.**

5. 위치 **선택** 탭에서 모든 위치의 기본 설정을 유지하거나 특정 위치를 선택하고 다음을 **선택합니다.**<br/>특정 위치를 선택한 경우 DLP 정책에 대해 해당 위치를 선택하고 다음을 **선택합니다.**<br/>![DLP 정책 위치](../media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > Teams에서 중요한 정보를 포함하는 문서가 부적절하게 공유되지 않는지 확인하려는 경우 Teams 채팅 및 채널 메시지와 함께  **SharePoint** 사이트 및 **OneDrive** 계정이 켜져 있는지 확인

<br/>

6. 정책 설정 **탭의** 보호할 콘텐츠 형식 사용자 지정 **아래에서** 기본 간단한 설정을 유지하거나 고급 설정 사용을 선택한 다음 **다음을** **선택합니다.** 고급 설정을 선택하는 경우 정책에 대한 규칙을 만들거나 편집할 수 있습니다. 이에 대한 도움말을 얻었다면 간단한 설정과 고급 설정을 [참조하세요.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  정책 설정 **탭의** 중요한 정보를 검색하는 경우 어떤 작업을 하고 **싶나요?** 아래에서 설정을 검토합니다. (다음은 기본 정책 팁 및 전자 메일 알림을 유지하거나 [사용자](use-notifications-and-policy-tips.md)지정할 수 있는 위치입니다.)<br/>![팁 및 알림이 있는 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)<br/>설정 검토 또는 편집을 마치면 다음을 **선택합니다.**

8. 정책  설정 탭의 정책 설정 탭에서 먼저 정책을 켜거나 테스트할지 여부, 정책을 [켜거나,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)먼저 테스트할지, 아니면 지금 해제된 후 다음을 **선택합니다.**<br/>![정책을 끄지 여부를 지정합니다.](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. 설정 **검토 탭에서** 새 정책에 대한 설정을 검토합니다. 편집을 **선택해** 변경합니다. 완료되면 만들기를 **선택 합니다.**

새 정책이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하도록 약 1시간을 허용합니다.

## <a name="prevent-external-access-to-sensitive-documents"></a>중요한 문서에 대한 외부 액세스 방지

중요한 정보가 포함된 SharePoint 문서는 기본적으로 SharePoint 또는 Teams에서 외부 게스트가 액세스할 수 없는지 확인하려면 다음을 선택합니다.

- DLP에서 검사하고 새 파일을 기본적으로 중요한 것으로 표시하여 문서를 공유하기에 안전한 것으로 표시할 때까지 문서가 [보호되도록 할 수 있습니다.](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- 권장 DLP 정책 구조
    - **조건**
        - 콘텐츠에는 다음 중요한 정보 유형이 포함되어 있습니다. [적용되는 모든 정보 선택]
        - 콘텐츠가 Microsoft 365에서 조직 외부의 사용자와 공유됩니다.
        <br/>![중요한 콘텐츠의 외부 공유를 감지하기 위한 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **작업**
        - 외부 사용자에 대한 콘텐츠 액세스 제한
        - 사용자에게 전자 메일 및 정책 팁 알림
        - 관리자에게 문제 보고서 보내기    
        <br/>![중요한 콘텐츠의 외부 공유를 차단하기 위한 DLP 작업](../media/dlp-teams-external-sharing/external-action.png)<br/>

SharePoint에서 중요한 정보가 포함된 문서를 외부 게스트와 공유하려고 할 때 실행된 DLP 정책:
<br/>![외부 공유 차단](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


게스트가 외부 차단을 통해 Teams에서 문서를 열려고 시도할 때 실행된 DLP 정책:
<br/>![외부 액세스 차단](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>관련 문서

[DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)

[DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시](use-notifications-and-policy-tips.md)

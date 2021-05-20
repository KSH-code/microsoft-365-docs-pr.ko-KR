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
description: 이제 채팅 및 채널에 DLP 정책을 Microsoft Teams 적용할 수 있습니다. 이 문서에서 작동 방식에 대해 자세히 알아보세요.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572468"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>데이터 손실 방지 및 Microsoft Teams

> [!NOTE]
> 데이터 손실 방지 기능은 최근 Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 정보 보호 및 거버넌스 또는 Office 365 Advanced Compliance 라이선스를 받은 사용자를 위한 채팅 및 채널 메시지에 Microsoft Teams 추가되었습니다. Office 365 및 Microsoft 365 E3 SharePoint 온라인, OneDrive 및 Exchange Online 대한 DLP 보호 기능이 포함됩니다. 여기에는 Teams SharePoint 온라인 및 OneDrive 사용하여 파일을 공유하기 때문에 Teams 통해 공유되는 파일도 포함됩니다.
Teams 채팅에서 DLP 보호에 대한 지원은 E5가 필요합니다.
라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams용 DLP 개요

최근에는 **개인 채널 메시지를 포함한** Microsoft Teams 채팅 및 채널 메시지를 포함하도록 데이터 손실 [방지](dlp-learn-about-dlp.md) 기능이 확장되었습니다. 

> [!IMPORTANT]
> DLP는 현재 채팅 또는 채널 스레드의 실제 메시지에만 적용됩니다. 짧은 메시지 미리 보기를 포함하고 사용자의 알림 설정에 따라 표시되는 활동 알림은 현재 Teams DLP에 포함되지 **않습니다.** 미리 보기에 나타나는 메시지 부분에 있는 중요한 정보는 DLP 정책이 적용되고 메시지 자체를 제거한 후에도 알림에 표시됩니다.

이제 조직에 DLP가 있는 경우 Microsoft Teams 채널 또는 채팅 세션에서 중요한 정보를 공유하지 못하도록 하는 정책을 정의할 수 있습니다. 다음은 이 보호의 작동 방식에 대한 몇 가지 예입니다.

- **예 1: 메시지에서 중요한 정보를 보호합니다.** 다른 사람이 Teams 채팅 또는 채널에서 게스트(외부 사용자)와 중요한 정보를 공유하려고 한다고 가정해 보라고 가정합니다. 이를 방지하기 위해 DLP 정책이 정의된 경우 외부 사용자에게 전송되는 중요한 정보가 포함된 메시지가 삭제됩니다. DLP 정책이 구성되는 방식에 따라 몇 초 내에 자동으로 수행됩니다.

    > [!NOTE]
    > Microsoft Teams 대한 DLP는 다음과 같은 Microsoft Teams 사용자와 공유할 때 중요한 콘텐츠를 차단합니다.<br/>- 팀 및 채널에서 [게스트 액세스;](/MicrosoftTeams/guest-access) 또는<br/>- 회의 및 채팅 세션에서 [외부 액세스.](/MicrosoftTeams/manage-external-access) <p>외부 채팅 세션의 DLP는 보낸자와 수신자가 Teams 전용 모드에 있고 [Microsoft Teams 네이티브 페더레이션을](/microsoftteams/manage-external-access)사용하는 경우에만 작동합니다. Teams 대한 DLP는 비즈니스용 Skype 또는 네이티브가 아닌 연합 채팅 세션이 있는 [interop에서](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) 메시지를 차단하지 않습니다.

- **예 2: 문서에서 중요한 정보 보호.** 다른 사람이 Microsoft Teams 채널 또는 채팅에서 게스트와 문서를 공유하려고 시도하고 문서에 중요한 정보가 포함되어 있다고 가정해 보실 수 있습니다. 이를 방지하기 위해 정의된 DLP 정책이 있는 경우 해당 사용자에 대해 문서가 열리지 않습니다. 이 경우 DLP 정책에보호가 준비되려면 SharePoint 및 OneDrive 포함되어야 합니다. (이 Microsoft Teams 표시 SharePoint 대 한 DLP의 예, 따라서 사용자가 Office 365 DLP에 대 한 라이센스 (Office 365 E3에 포함), 하지만 사용자가 Office 365 Advanced Compliance 대 한 라이센스를 필요로 하지 않습니다.)

## <a name="policy-tips-help-educate-users"></a>정책 팁은 사용자를 교육하는 데 도움이 됩니다.

DLP가 [Exchange, Outlook, 웹,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint 온라인, 비즈니스용 OneDrive 사이트](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)및 Office 데스크톱 [클라이언트에서](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)Outlook 것과 마찬가지로 DLP 정책과 작업이 충돌할 때 정책 팁이 나타납니다. 정책 팁의 예는 다음과 같습니다.

![Teams 메시지 알림 차단](../media/dlp-teams-blockedmessage-notification.png)

이 경우 보낸 사람은 Microsoft Teams 채널에서 사회 보장 번호를 공유하려고 시도했습니다. **수행할 수 있는 작업을 수행할 수 있습니까?** 링크는 보낸 사람이 문제를 해결할 수 있는 옵션을 제공하는 대화 상자가 열립니다. 이 경우 보낸 사람이 정책을 재정의하거나 관리자에게 정책을 검토하고 해결하도록 알릴 수 있습니다.

![차단된 메시지를 해결하는 옵션](../media/dlp-teams-blockedmessage-possibleactions.png)

조직에서 사용자가 DLP 정책을 재정의할 수 있도록 선택할 수 있습니다. 또한 DLP 정책을 구성할 때 기본 정책 팁을 사용하거나 조직의 [정책 팁을 사용자 지정할](#to-customize-policy-tips) 수 있습니다.

보낸 사람이 Teams 채널에서 사회 보장 번호를 공유한 예제로 돌아가면 받는 사람이 본 내용은 다음과 같습니다.

> [!div class="mx-imgBorder"]
> ![메시지가 차단됨](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>정책 팁 사용자 지정

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조하십시오.

1. 보안 & 규정 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.

2. **데이터 손실 방지** > **정책** 을 선택합니다.

3. 정책을 선택하고 **정책 설정** 옆에 **있는 편집을 선택합니다.**

4. 새 규칙을 만들거나 정책에 대한 기존 규칙을 편집합니다.

    > [!div class="mx-imgBorder"]
    > ![정책에 대한 규칙 편집](../media/dlp-teams-editrule.png)

5. 사용자 **알림** 탭에서 **이메일 텍스트 사용자 지정을** 선택하고 정책 팁 텍스트 옵션을 **사용자 지정합니다.**

    > [!div class="mx-imgBorder"]
    > ![사용자 알림 및 정책 팁 사용자 지정](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 이메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정한 다음 **저장을 선택합니다.**

7. 정책 **설정** 탭에서 **저장을** 선택합니다.

변경 사항이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하는 데 약 1시간을 허용합니다.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>기존 DLP 정책에 Microsoft Teams를 위치로 추가

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조하십시오.

1. 보안 & 규정 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.

2. **데이터 손실 방지** > **정책** 을 선택합니다.

3. 정책을 선택하고 **위치** 아래값을 살펴봅니다. **채팅 및 채널 메시지에 Teams** 표시되면 모두 설정됩니다. 그렇지 않은 경우 **편집을 클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![기존 정책의 위치](../media/dlp-teams-editexistingpolicy.png)

4. **상태** 열에서 **Teams 채팅 및 채널 메시지에** 대한 정책을 켭니다.

    > [!div class="mx-imgBorder"]
    > ![Teams 채팅 및 채널용 DLP](../media/dlp-teams-addteamschatschannels.png)

5. 위치 **선택** 탭에서 모든 계정의 기본 설정을 유지하거나 **특정 위치를 선택하도록 선택합니다.** 지정할 수 있는 사항은 다음과 같습니다.

    1. 포함하거나 제외할 개별 계정 최대 1,000개
    1. 포함하거나 제외할 메일 목록 및 보안 그룹입니다. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. 그런 후 **다음** 을 선택합니다.

7. **저장** 을 클릭합니다.

변경 사항이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하는 데 약 1시간을 허용합니다.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams에 대한 새 DLP 정책 정의

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 [사용 권한을](data-loss-prevention-policies.md#permissions)참조하십시오.

1. 보안 & 규정 준수 [https://protection.office.com](https://protection.office.com) 센터()로 이동하여 로그인합니다.

2. **데이터 손실 방지** > **정책** > **+ 정책 만들기** 를 선택합니다.

3. [템플릿을](data-loss-prevention-policies.md#dlp-policy-templates)선택한 다음을 **선택합니다.**

    예제에서는 미국 개인 식별 정보 데이터 템플릿을 선택했습니다.

    > [!div class="mx-imgBorder"]
    > ![DLP 정책에 대한 개인 정보 보호 템플릿](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. 정책 **이름** 탭에서 정책에 대한 이름과 설명을 지정한 다음 **다음을** 선택합니다.

5. 위치 **선택** 탭에서 모든 계정의 기본 설정을 유지하거나 **특정 위치를 선택하도록 선택합니다.** 지정할 수 있는 사항은 다음과 같습니다.

    1. 포함하거나 제외할 개별 계정 최대 1,000개
    1. 포함하거나 제외할 메일 목록 및 보안 그룹입니다. **공개 미리 보기 기능입니다.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 정책 위치](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > 중요한 정보가 포함된 문서가 Teams 부적절하게 공유되지 않도록 하려면 **SharePoint 사이트와** **OneDrive 계정이** Teams 채팅 및 **채널 메시지와** 함께 켜져 있는지 확인합니다.

6. 정책 **설정** 탭에서 **보호하려는 콘텐츠 유형을 사용자 지정하거나** 기본 간단한 설정을 유지하거나 **고급 설정을 선택한** 다음 **다음을** 선택합니다. 고급 설정을 선택하면 정책에 대한 규칙을 만들거나 편집할 수 있습니다. (이 에 대한 도움을 받으려면 [간단한 설정 과 고급 설정을](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)참조하십시오.)

7.  정책 **설정** 탭에서 **중요한 정보를 감지하면 어떻게 하시겠습니까?** 기본 [정책 팁과 이메일 알림을](use-notifications-and-policy-tips.md)유지하거나 사용자 지정할 수 있는 곳은 다음과 같습니다.

    > [!div class="mx-imgBorder"]
    > ![팁 및 알림이 있는 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)

    설정 검토 또는 편집이 완료되면 **다음을** 선택합니다.

8. 정책 **설정** [](dlp-overview-plan-for-dlp.md#policy-deployment) **탭에서 정책을 켜거나 먼저 테스트하시겠습니까?** 

    > [!div class="mx-imgBorder"]
    > ![정책을 켤지 여부를 지정합니다.](../media/dlp-teams-policysettings-turnonnow.png)

9. 설정 **검토** 탭에서 새 정책의 설정을 검토합니다. **수정을** 선택하여 변경합니다. 완료되면 **만들기를** 선택합니다.

새 정책이 데이터 센터를 통해 작동하고 사용자 계정에 동기화하는 데 약 1시간을 허용합니다.

## <a name="prevent-external-access-to-sensitive-documents"></a>중요한 문서에 대한 외부 액세스 방지

중요한 정보가 포함된 SharePoint 문서는 기본적으로 SharePoint 또는 Teams 외부 게스트가 액세스할 수 없도록 하려면 다음을 선택합니다.

- DLP가 스캔할 때까지 문서를 보호하고 새 파일을 기본적으로 [민감한 파일로 표시하여](/sharepoint/sensitive-by-default)공유할 수 있는 안전한 것으로 표시할 수 있습니다.

- 권장되는 DLP 정책 구조

    - **조건**
        - 콘텐츠에는 이러한 중요한 정보 유형이 포함되어 있습니다.
        
        - 콘텐츠는 Microsoft 365 조직 외부의 사용자와 공유됩니다.
        
          > [!div class="mx-imgBorder"]
          > ![민감한 콘텐츠의 외부 공유를 감지하는 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)

    - **작업**
        - 외부 사용자의 콘텐츠에 대한 액세스 제한
        
        - 전자 메일 및 정책 팁을 통해 사용자에게 알림
        
        - 관리자에게 인시던트 보고서 보내기
        
        > [!div class="mx-imgBorder"]
        > ![민감한 콘텐츠의 외부 공유를 차단하는 DLP 작업](../media/dlp-teams-external-sharing/external-action.png)

중요한 정보가 포함된 SharePoint 문서를 외부 게스트와 공유하려고 할 때 작동하는 DLP 정책:

> [!div class="mx-imgBorder"]
> ![외부 공유 차단](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


게스트가 외부 블록이 있는 Teams 문서를 열려고 할 때 작동하는 DLP 정책:

> [!div class="mx-imgBorder"]
> ![외부 액세스 차단](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>관련 문서

[DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)

[DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시](use-notifications-and-policy-tips.md)

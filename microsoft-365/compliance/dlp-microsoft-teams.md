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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams 채널은 DLP(데이터 손실 방지) 정책을 지원합니다.
ms.openlocfilehash: f4e4c7b0d25d411fe8aa3d69b1768ed7508b9b6b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168713"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>데이터 손실 방지 및 Microsoft Teams

조직에 DLP(데이터 손실 방지)가 있는 경우 사용자가 특정 채널 또는 채팅 세션에서 중요한 정보를 공유하지 Microsoft Teams 정의할 수 있습니다. 다음은 이 보호가 작동하는 방식의 몇 가지 예입니다.

- **예제 1: 메시지의 중요한 정보 보호** 누군가가 게스트(외부 사용자)와 Teams 채팅 또는 채널에서 중요한 정보를 공유하려고 시도하는 경우를 가정해 보세요. 이를 방지하는 DLP 정책이 정의되어 있는 경우 외부 사용자에게 전송되는 중요한 정보가 있는 메시지는 삭제됩니다. 이 문제는 DLP 정책이 구성된 방식에 따라 자동으로 몇 초 내에 발생합니다.

    > [!NOTE]
    > 다음을 Microsoft Teams 사용자와 공유하는 경우 중요한 Microsoft Teams 차단하는 DLP입니다.<br/>- [팀 및](/MicrosoftTeams/guest-access) 채널의 게스트 액세스 또는<br/>- [모임 및](/MicrosoftTeams/manage-external-access) 채팅 세션의 외부 액세스 <p>외부 채팅 세션에 대한 DLP는 보낸 사람 및 수신자가 모두 Teams 전용 모드에 있으며 기본 Microsoft Teams [사용하는 경우만 사용할 수 있습니다.](/microsoftteams/manage-external-access) Teams 대한 DLP는 비즈니스용 Skype 비 네이티브 페더러드 채팅 세션과 상호 연결되는 메시지를 차단하지 않습니다. [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)

- **예제 2: 문서의 중요한 정보 보호** 다른 사용자가 특정 채널 또는 채팅에서 게스트와 문서를 공유하려고 Microsoft Teams 중요한 정보가 포함된 경우를 가정해 보세요. 이를 방지하는 DLP 정책이 정의되어 있는 경우 해당 사용자에 대해 문서가 열리지 않습니다. 이 보호 기능을 사용하려면, DLP 정책에 SharePoint 및 OneDrive가 포함되어야 합니다. 이 예는 SharePoint 에 표시되어 사용자에게 Office 365 Microsoft Teams DLP(Office 365 E3에 포함)에 대한 라이선스가 필요하지만 사용자에게 Office 365 Advanced Compliance.)

## <a name="dlp-licensing-for-microsoft-teams"></a>사용자에 대한 DLP Microsoft Teams

[데이터 손실 방지](dlp-learn-about-dlp.md) 기능은 다음에 대한 비공개 채널 Microsoft Teams 및 채널 메시지를 포함하기 위해 **확장했습니다.**

- Office 365 E5/A5/G5
- Microsoft 365 E5/A5/G5
- Microsoft 365 E5/A5/G5 정보 보호 및 거버넌스
- Microsoft 365 E5/A5/G5/F5 규정 준수 및 F5 보안 & 규정 준수

Office 365 Microsoft 365 E3 온라인, OneDrive 및 SharePoint DLP 보호가 Exchange Online. 이 파일에는 Teams Online을 사용하여 Teams 공유하기 때문에 SharePoint 공유하는 OneDrive 포함됩니다.

채팅에서 DLP 보호를 지원하려면 Teams E5가 필요합니다.

라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참고하십시오.

> [!IMPORTANT]
> DLP는 채팅 또는 채널 스레드의 실제 메시지에만 적용됩니다. 짧은 메시지 미리 보기를 포함하며 사용자의 알림 설정에 따라 나타나는 활동  알림은 DLP에 Teams 없습니다. 미리 보기에 표시되는 메시지 부분에 있는 모든 중요한 정보는 DLP 정책이 적용되고 메시지 자체를 제거한 후에도 알림에 계속 표시됩니다.

## <a name="scope-of-dlp-protection"></a>DLP 보호 범위

DLP 보호는 엔터티에 Teams 다르게 적용됩니다.

|정책의 범위가 |이러한 Teams 엔터티 |DLP 보호를 사용할 수 있습니다.|
|---------|---------|---------|
|개별 사용자 계정     |1:1/n 채팅         |예         |
|     |일반 채팅         |아니요         |
|     |비공개 채널         |예         |
|보안 그룹/메일 그룹  | 1:1/n 채팅         |예         |
|     |일반 채팅         |아니요         |
|     |비공개 채널         |예        |
|Microsoft 365 그룹    |1:1/n 채팅          |아니요         |
|     |일반 채팅          |예        |
|     |비공개 채널|아니요| 


## <a name="policy-tips-help-educate-users"></a>정책 팁은 사용자를 교육하는 데 도움이 됩니다.

Exchange, [Outlook, 웹용 Outlook,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)SharePoint [Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)비즈니스용 OneDrive 사이트 및 Office 데스크톱 클라이언트에서 DLP가 작동하는 방식과 마찬가지로 DLP 정책을 사용하여 작업이 트리거될 때 정책 [팁이](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)나타납니다. 정책 팁의 예는 다음과 같습니다.

![차단된 메시지 알림의 Teams.](../media/dlp-teams-blockedmessage-notification.png)

여기서 보낸 사람이 공유 채널에서 주민 Microsoft Teams 하려고 했습니다. What **can I do?** 링크를 클릭하면 보낸 사람이 문제를 해결할 수 있는 옵션을 제공하는 대화 상자가 열립니다. 보낸 사람이 정책을 다시 설정하거나 관리자에게 검토 및 해결을 알리도록 선택할 수 있습니다.

![차단된 메시지를 해결하기 위한 옵션입니다.](../media/dlp-teams-blockedmessage-possibleactions.png)

조직에서 사용자가 DLP 정책을 다시 설정하도록 선택할 수 있습니다. DLP 정책을 구성할 때 기본 정책 팁을 사용하거나 조직의 정책 팁을 [사용자 지정할](#to-customize-policy-tips) 수 있습니다.

보낸 사람이 Teams 채널에서 사회 보장 번호를 공유한 예제로 돌아가면 받는 사람이 본 예는 다음과 같습니다.

> [!div class="mx-imgBorder"]
> ![메시지가 차단됩니다.](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>정책 팁 사용자 지정

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 사용 권한을 [참조합니다.](data-loss-prevention-policies.md#permissions)

1. 준수 센터()로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 로그인합니다.

2. **데이터 손실 방지** > **정책** 을 선택합니다.

3. 정책을 선택하고 정책 설정 옆에 **있는** 편집 을 **선택합니다.**

4. 새 규칙을 만들거나 정책에 대한 기존 규칙을 편집합니다.

    > [!div class="mx-imgBorder"]
    > ![정책에 대한 규칙 편집](../media/dlp-teams-editrule.png)

5. 사용자 **알림 탭에서** 전자  메일 텍스트 사용자 지정 및/또는 정책 팁 텍스트 **옵션 사용자 지정을** 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![사용자 알림 및 정책 팁을 사용자 지정합니다.](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 전자 메일 알림 및/또는 정책 팁에 사용할 텍스트를 지정하고 저장 을 **선택하십시오.**

7. 정책 **설정 탭에서** 저장을 **선택합니다.**

변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화되는 데 약 1시간을 허용합니다.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>기존 DLP 정책에 Microsoft Teams를 위치로 추가

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 사용 권한을 [참조합니다.](data-loss-prevention-policies.md#permissions)

1. 준수 센터()로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 로그인합니다.

2. **데이터 손실 방지** > **정책** 을 선택합니다.

3. 정책을 선택하고 위치 에서 값을 **봐야 합니다.** 채팅 및 **Teams 메시지가** 표시되어 있는 경우 모두 설정됩니다. 그렇지 않은 경우 편집 을 **클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![기존 정책의 위치입니다.](../media/dlp-teams-editexistingpolicy.png)

4. 상태 **열에서** 채팅 및 채널 메시지 **에 Teams 을 으로 끄습니다.**

    > [!div class="mx-imgBorder"]
    > ![채팅 및 Teams 대한 DLP입니다.](../media/dlp-teams-addteamschatschannels.png)

5. 위치 **선택 탭에서** 모든 계정의 기본 설정을 유지하거나 특정 위치를 선택하도록 **를 선택합니다.** 지정할 수 있는 사항은 다음과 같습니다.

    1. 포함하거나 제외할 최대 1,000개 개별 계정
    1. 포함하거나 제외할 메일 그룹 및 보안 그룹 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. 그런 후 **다음** 을 선택합니다.

7. **저장** 을 클릭합니다.

변경 내용이 데이터 센터를 통해 작동하고 사용자 계정과 동기화되는 데 약 1시간을 허용합니다.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams에 대한 새 DLP 정책 정의

이 작업을 수행하려면 DLP 정책을 편집할 수 있는 권한이 있는 역할이 할당되어야 합니다. 자세한 내용은 사용 권한을 [참조합니다.](data-loss-prevention-policies.md#permissions)

1. 준수 센터()로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 로그인합니다.

2. **데이터 손실 방지** > **정책** > **+ 정책 만들기** 를 선택합니다.

3. 템플릿 [을](data-loss-prevention-policies.md#dlp-policy-templates)선택하고 다음 을 **선택 합니다.**

    이 예제에서는 미국 개인 식별 정보 데이터 템플릿을 선택 합니다.

    > [!div class="mx-imgBorder"]
    > ![DLP 정책의 개인 정보 템플릿입니다.](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. 정책 **이름 지정 탭에서** 정책의 이름과 설명을 지정하고 다음 을 **선택합니다.**

5. 위치 **선택 탭에서** 모든 계정의 기본 설정을 유지하거나 특정 위치를 선택하도록 **를 선택합니다.** 지정할 수 있는 사항은 다음과 같습니다.

    1. 포함하거나 제외할 최대 1,000개 개별 계정
    1. 포함하거나 제외할 메일 그룹 및 보안 그룹 **공개 미리 보기 기능입니다.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 정책 위치.](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > 중요한 정보가 포함된 문서가 Teams 부적절하게 공유되지 않는지 확인하려는 경우 SharePoint  사이트 및 OneDrive  계정과 채팅 및 채널 메시지와 **함께** Teams 설정해야 합니다.

6. 정책 **설정 탭의** 보호할 콘텐츠 형식 사용자 지정에서 **기본** 단순 설정을 유지하거나 고급 설정 사용을 선택한 후 다음 을 **선택합니다.** 고급 설정을 선택하는 경우 정책에 대한 규칙을 만들거나 편집할 수 있습니다. 이에 대한 도움말은 단순 설정 및 고급 설정 [을 참조하세요.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  정책 **설정 탭의** 중요한 정보를 검색하는 경우 어떤 작업을 하고 **싶나요?** 아래에서 설정을 검토합니다. 다음은 기본 정책 팁 및 [](use-notifications-and-policy-tips.md)전자 메일 알림을 유지하거나 사용자 지정할 수 있는 위치입니다.

    > [!div class="mx-imgBorder"]
    > ![팁 및 알림이 있는 DLP 정책 설정](../media/dlp-teams-policysettings-tipsemails.png)

    설정 검토 또는 편집을 마치면 다음 을 **선택합니다.**

8. 정책  설정 탭의 정책을 켜거나 먼저 테스트할지 여부에서 정책을 켜거나 먼저 테스트할지, 아니면 지금 해제된 후 다음 을 **선택합니다.** [](dlp-overview-plan-for-dlp.md#policy-deployment)

    > [!div class="mx-imgBorder"]
    > ![정책을 끄지 여부를 지정합니다.](../media/dlp-teams-policysettings-turnonnow.png)

9. 설정 **검토 탭에서** 새 정책에 대한 설정을 검토합니다. 편집을 **선택해** 변경합니다. 완료되면 만들기 를 **선택 합니다.**

새 정책이 데이터 센터를 통해 작동하고 사용자 계정에 동기화되는 데 약 1시간을 허용합니다.

## <a name="prevent-external-access-to-sensitive-documents"></a>중요한 문서에 대한 외부 액세스 방지

중요한 SharePoint 포함된 문서에 기본적으로 외부 게스트가 액세스하지 못하도록 SharePoint Teams 다음을 선택합니다.

- 기본적으로 새 파일을 중요한 파일로 표시하여 DLP가 문서를 검사하고 공유하기 안전한 것으로 표시할 때까지 문서가 [보호되도록 할 수 있습니다.](/sharepoint/sensitive-by-default)

- 권장되는 DLP 정책 구조

    - **조건**
        - 콘텐츠에 다음 중요한 정보 유형이 포함되어 있습니다. [적용되는 모든 정보 선택]
        
        - 콘텐츠가 조직 Microsoft 365 사용자와 공유됩니다.
        
          > [!div class="mx-imgBorder"]
          > ![중요한 콘텐츠의 외부 공유를 감지하기 위한 DLP 조건](../media/dlp-teams-external-sharing/external-condition.png)

    - **작업**
        - 외부 사용자의 콘텐츠에 대한 액세스 제한
        
        - 전자 메일 및 정책 팁을 통해 사용자에게 알림
        
        - 관리자에게 인시던트 보고서 보내기
        
        > [!div class="mx-imgBorder"]
        > ![중요한 콘텐츠의 외부 공유를 차단하는 DLP 작업입니다.](../media/dlp-teams-external-sharing/external-action.png)

외부 게스트와 중요한 정보를 포함하는 SharePoint 공유하려고 할 때 실행되는 DLP 정책:

> [!div class="mx-imgBorder"]
> ![외부 공유가 차단됩니다.](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


게스트가 외부 차단을 통해 Teams 열려고 할 때 실행되는 DLP 정책

> [!div class="mx-imgBorder"]
> ![외부 액세스가 차단됩니다.](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>관련 문서

- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [DLP 정책에 대한 전자 메일 알림 보내기 및 정책 팁 표시](use-notifications-and-policy-tips.md)

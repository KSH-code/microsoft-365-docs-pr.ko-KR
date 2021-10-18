---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책을 만들고 구성하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 정책을 사용하면 사용자가 전자 메일과 문서, 대화를 사용하여 생성하는 콘텐츠를 효율적으로 유지 관리할 수 있습니다. 원하는 내용을 유지하고 원하지 않는 항목을 제거하세요.
ms.openlocfilehash: 4a1a0c5334772d9259278d884090c75d8441df22
ms.sourcegitcommit: f6fff04431d632db02e7bdbf12f691091a30efad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60432604"
---
# <a name="create-and-configure-retention-policies"></a>보존 정책 만들기 및 구성

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하여 조직 데이터를 관리하기 위해 보존 정책을 사용합니다.

보존 정책은 컨테이너 수준에서 동일한 데이터 보존 설정을 할당하여 해당 컨테이너의 콘텐츠가 자동으로 이를 상속하게 함으로써 이 작업을 매우 효율적으로 수행할 수 있게 해 줍니다. 예를 들어 SharePoint 사이트의 모든 항목과 사용자 Exchange 사서함의 모든 전자 메일, Microsoft Teams에서 사용되는 팀의 모든 채널 메시지가 여기 해당합니다. 컨테이너 수준에서의 보존 정책이나 항목 수준에서의 보존 레이블을 사용해야 할지가 확실하지 않다면 [보존 정책 및 보존 레이블](retention.md#retention-policies-and-retention-labels)을 참조하세요.

Microsoft 365에서의 보존 정책과 보존 레이블 작동 방식에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.

> [!NOTE]
> 이 페이지의 정보는 규정 준수 관리자를 위한 정보입니다. 관리자가 아니지만 본인이 사용하는 앱의 보존 정책 구성 방식을 알고 싶다면 지원 센터나 IT 팀 또는 관리자에게 문의하세요. Teams 차트와 채널 메시지에 보존 정책 관련 메시지가 표시된다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 리뷰하는 게 도움이 될 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

조직의 전역 관리자는 보존 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.

보존 정책을 만들기 전에 **적응형** 또는 **정적** 정책인지 결정합니다. 자세한 내용은 [보존을 위한 적응형 또는 정적 정책 범위](retention.md#adaptive-or-static-policy-scopes-for-retention)를 참조하세요. 적응형 정책을 사용하기로 결정한 경우 보존 정책을 만들기 전에 하나 이상의 적응형 범위를 만든 다음 보존 정책 만들기 프로세스 중에 선택해야 합니다. 자세한 내용은 [적응형 범위에 대한 구성 정보](retention-settings.md#configuration-information-for-adaptive-scopes)를 참조하세요.

## <a name="create-and-configure-a-retention-policy"></a>보존 정책 만들기 및 구성하기

보존 정책은 보존 정책에 ‘위치’로 식별되는 여러 서비스를 지원할 수 있지만 지원되는 모든 위치를 포함하는 단일 보존 정책을 만들 수는 없습니다.

- Exchange 전자 메일
- SharePoint 사이트
- OneDrive 계정
- Microsoft 365 그룹
- 비즈니스용 Skype
- Exchange 공용 폴더
- Teams 채널 메시지
- Teams 채팅
- Teams 비공개 채널 메시지
- Yammer 커뮤니티 메시지
- Yammer 사용자 메시지

보존 정책을 생성할 때 Teams 또는 Yammer 위치를 선택하면 다른 위치는 자동으로 제외됩니다. 즉, Teams 또는 Yammer 위치 포함 여부에 따라, 따라야 할 지침도 달라진다는 뜻이죠.

- [Teams 위치](#retention-policy-for-teams-locations)에 대한 보존 정책에 대한 지침
- [Yammer 위치에 대한 보존 정책에 대한 지침](#retention-policy-for-yammer-locations)
- [Teams 및 Yammer](#retention-policy-for-locations-other-than-teams-and-yammer) 이외의 위치에 대한 보존 정책에 대한 지침

> [!NOTE]
> 정적 정책 대신 적응형 정책을 사용하는 경우 Teams 및 Yammer 위치를 모두 포함하도록 단일 보존 정책을 구성할 수 있습니다. Teams 및 Yammer 위치에 자체 보존 정책이 필요한 정적 정책의 경우는 그렇지 않습니다.

보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.

### <a name="retention-policy-for-teams-locations"></a>Teams 위치 보존 정책

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 **보존 정책 만들기** 구성을 시작하고 새 보존 정책의 이름을 지정합니다.

3. **생성할 보존 정책 유형 선택** 페이지에서 [시작하기 전](#before-you-begin) 지침에서 선택한 항목에 따라 **적응형** 또는 **정적** 을 선택합니다. 적응형 범위를 아직 만들지 않은 경우 **적응형** 을 선택할 수 있지만 선택할 적응형 범위가 없기 때문에 이 옵션으로 구성을 완료할 수 없습니다.

4. 선택한 범위에 따라:
    
    - **적응형** 을 선택한 경우: **적응형 정책 범위 및 위치 선택** 페이지에서 **범위 추가** 를 선택하고 생성된 하나 이상의 적응형 범위를 선택합니다. 그런 다음 하나 이상의 위치를 ​​선택합니다. 선택할 수 있는 위치는 추가된 [범위 유형](retention-settings.md#configuration-information-for-adaptive-scopes)에 따라 다릅니다. 예를 들어 **사용자** 의 범위 유형만 추가한 경우 **Teams 채팅** 은 선택할 수 있지만 **Teams 채널 메시지** 는 선택할 수 없습니다. 
    
    - **정적** 을 선택한 경우: **정책을 적용할 위치 선택** 페이지에서 Teams에 대해 하나 이상의 위치를 ​​선택합니다.
        - **Teams 채널 메시지**: 표준 채널 채팅 및 표준 채널 모임의 메시지이지만 자체 정책 위치가 있는 [비공개 채널](/microsoftteams/private-channels)에서 보낸 메시지는 아닙니다.
        - **Teams 채팅**: 비공개 1:1 채팅, 그룹 채팅 및 모임 채팅의 메시지입니다.
        - **Teams 비공개 채널 메시지**: 비공개 채널 채팅 및 비공개 채널 모임의 메시지입니다.
        
       기본적으로 [모든 팀과 모든 사용자가 선택되어 있지만](retention-settings.md#a-policy-that-applies-to-entire-locations), [**선택** 및 **배제** 옵션](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions)을 선택하여 이를 구체화할 수 있습니다. 그러나 기본값을 변경하기 전에 포함 또는 제외되도록 구성할 때 메시지를 삭제하는 보존 정책의 다음과 같은 결과에 유의해야 합니다.
        
        - 그룹 채팅 메시지 및 비공개 채널 메시지의 경우 메시지 복사본이 채팅에 포함된 각 사용자의 사서함에 저장되므로 정책이 할당되지 않은 사용자의 eDiscovery 결과에 메시지 복사본이 계속 반환됩니다.
        - 정책을 할당하지 않은 사용자의 경우 삭제된 메시지가 Teams 검색 결과에 반환되지만 사용자에게 할당된 정책에서 영구적으로 삭제한 결과 메시지 내용은 표시되지 않습니다.

5. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.

   삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 [콘텐츠 보존 및 삭제 설정](retention-settings.md#settings-for-retaining-and-deleting-content)을 참조하세요.

6. 구성을 완료하고 설정을 저장합니다.

Teams에 대한 보존 정책을 사용하고 최종 사용자 환경을 이해해야할 시기에 대한 지침은 Teams 설명서에서 [Microsoft Teams에 대한 보존 정책 관리](/microsoftteams/retention-policies)를 참조하세요.

예제 연습을 통해 보존 및 타이밍 정보용으로 지원되는 메시지 요소를 포함하여 Teams에 대한 보존 작동 방식에 관한 기술 세부 정보는 [Microsoft Teams의 보존에 대해 자세히 알아보기](retention-policies-teams.md)를 참조하세요.

#### <a name="known-configuration-issues"></a>알려진 구성 문제

- 항목을 마지막으로 수정한 경우 보존 기간을 시작하는 옵션을 선택할 수 있어도 항상 **항목을 만든 시간** 이 사용됩니다. 편집된 메시지의 경우 원본 메시지의 복사본이 원래 타임스탬프와 함께 저장되어 미리 편집된 메시지를 만들 때를 식별하고, 사후 편집된 메시지에 새로운 타임스탬프가 있습니다.

- **Teams 채널 메시지** 위치에 대해 **편집** 을 선택하면 팀이 아닌 Microsoft 365 그룹이 표시될 수 있습니다. 이 그룹을 선택하지 마세요.

- **Teams 채팅 위치에 대한 편집** 을 선택하면 게스트 및 비 사서함이 사용자가 표시될 수 있습니다. 보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.


#### <a name="additional-retention-policy-needed-to-support-teams"></a>Teams 지원에 필요한 추가 보존 정책

Teams는 채팅 및 채널 메시지 그 이상 Microsoft 365 그룹에서 만든 팀(이전에는 Office 365 그룹)이 있는 경우 **Microsoft 365 그룹** 위치를 사용하여 Microsoft 365 그룹을 포함하는 보존 정책을 추가적으로 구성해야 합니다. 이 보존 정책은 그룹의 사서함, 사이트 및 파일의 콘텐츠에 적용됩니다.

Microsoft 365 그룹에 연결되어 있지 않은 팀 사이트가 있는 경우, Teams에서 파일을 보존하고 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.

- 채팅에서 공유되는 파일은 해당 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다.

- 채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다.

> [!TIP]
> 특정 팀의 SharePoint 사이트 및 특정 팀 사용자의 OneDrive 계정을 선택하여 Microsoft 365 그룹에 연결되어 있지 않으면 해당 팀의 파일에 보존 정책을 적용할 수 있습니다.

Microsoft 365 그룹, SharePoint 사이트 또는 OneDrive 계정에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다. 이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다. 이 동작은 보존 정책에만 국한된 것이 아니며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.

### <a name="retention-policy-for-yammer-locations"></a>Yammer 위치에 대한 보존 정책

> [!NOTE]
> Yammer에 대한 보존 정책은 미리 보기 상태이며 현재 보존 정책의 결과로 메시지가 삭제될 때 사용자에게 알리지 않습니다.
>
> 이 기능을 사용하려면 Yammer 네트워크가 하이브리드 모드가 아니라 [기본 모드](/yammer/configure-your-yammer-network/overview-native-mode)여야 합니다.

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 새 보존 정책을 만듭니다.

3. **생성할 보존 정책 유형 선택** 페이지에서 [시작하기 전](#before-you-begin) 지침에서 선택한 항목에 따라 **적응형** 또는 **정적** 을 선택합니다. 적응형 범위를 아직 만들지 않은 경우 **적응형** 을 선택할 수 있지만 선택할 적응형 범위가 없기 때문에 이 옵션으로 구성을 완료할 수 없습니다.

4. 선택한 범위에 따라:
    
    - **적응형** 을 선택한 경우: **적응형 정책 범위 및 위치 선택** 페이지에서 **범위 추가** 를 선택하고 생성된 하나 이상의 적응형 범위를 선택합니다. 그런 다음 하나 이상의 위치를 ​​선택합니다. 선택할 수 있는 위치는 추가된 [범위 유형](retention-settings.md#configuration-information-for-adaptive-scopes)에 따라 다릅니다. 예를 들어 **사용자** 의 범위 유형만 추가한 경우 **Yammer 사용자 메시지** 는 선택할 수 있지만 **Yammer 커뮤니티 메시지** 는 선택할 수 없습니다. 
    
    - **정적** 을 선택한 경우: **정책을 적용할 위치 선택** 페이지에서 Yammer: **Yammer 커뮤니티 메시지** 및 **Yammer 사용자 메시지** 중 하나 또는 두 가지 모두를 전환합니다.
        
        > [!IMPORTANT]
        > Yammer 사용자 메시지에 대한 보존 정책을 만들 수 있지만 이 위치에 대한 보존 정책은 모든 커뮤니티 구성원에 대한 Yammer 앱에서 커뮤니티 메시지를 삭제할 수 있습니다.
        > 
        > 이 옵션을 선택하고 사용자 메시지를 삭제하도록 보존 정책이 구성되는 경우 이 의미를 이해해야 합니다. 자세한 내용은 [Yammer에서 보존 작업이 작동하는 방식](retention-policies-yammer.md#how-retention-works-with-yammer)을 참조하세요.
        
        기본적으로 모든 커뮤니티와 사용자가 선택되지만 포함하거나 제외할 커뮤니티와 사용자를 지정하여 세분화할 수 있습니다.
        
        Yammer 사용자 메시지의 경우: 
        - 기본값을 **모든 사용자** 로 유지하면 Azure B2B 게스트 사용자가 포함되지 않습니다. 
        - **모든 사용자** 에 대해 **편집** 을 선택하면 외부 사용자의 계정을 알고 있는 경우 해당 사용자에게 보존 정책을 적용할 수 있습니다.

5. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요. 
    
    삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 [콘텐츠 보존 및 삭제 설정](retention-settings.md#settings-for-retaining-and-deleting-content)을 참조하세요.

6. 구성을 완료하고 설정을 저장합니다.

Yammer용 보존 정책이 작동하는 방식에 대한 자세한 내용은 [Yammer용 보존 정보](retention-policies-yammer.md)를 참조하세요.

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Yammer를 지원하려면 추가 보존 정책이 필요합니다.

Yammer는 단지 커뮤니티 메시지와 비공개 메시지 그 이상의 기능을 수행합니다. Yammer 네트워크의 전자 메일 메시지를 보존 및 삭제하려면 **Microsoft 365 그룹** 위치를 사용하여 Yammer에 사용되는 Microsoft 365 그룹을 포함하는 추가 보존 정책을 구성합니다. 

Yammer에 저장된 파일을 유지 및 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.

- 개인 메시지에서 공유되는 파일은 파일을 공유한 사용자의 OneDrive 계정에 저장됩니다. 

- 커뮤니티에 업로드된 파일은 Yammer 커뮤니티의 SharePoint 사이트에 저장됩니다.

SharePoint 사이트 또는 OneDrive 계정에 적용된 보존 정책은 해당 메시지가 삭제되기 전에 Yammer 메시지에 참조된 파일을 삭제할 수 있습니다. 이 시나리오에서는 파일이 Yammer 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다. 이러한 동작은 보존 정책에만 국한되지 않으며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Teams 및 Yammer 이외의 위치에 대한 보존 정책

이러한 서비스에 적용되는 보존 정책에 대해 다음 지침을 사용합니다.

- Exchange: 전자 메일 및 공용 폴더
- SharePoint: 사이트
- OneDrive: 계정
- Microsoft 365 그룹
- 비즈니스용 Skype

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 **보존 정책 만들기** 구성을 시작하고 새 보존 정책의 이름을 지정합니다.

3. **생성할 보존 정책 유형 선택** 페이지에서 [시작하기 전](#before-you-begin) 지침에서 선택한 항목에 따라 **적응형** 또는 **정적** 을 선택합니다. 적응형 범위를 아직 만들지 않은 경우 **적응형** 을 선택할 수 있지만 선택할 적응형 범위가 없기 때문에 이 옵션으로 구성을 완료할 수 없습니다. 적응형 정책은 Exchange 공용 폴더 또는 비즈니스용 Skype의 위치를 ​​지원하지 않습니다.

4. 선택한 범위에 따라:
    
    - **적응형** 을 선택한 경우: **적응형 정책 범위 및 위치 선택** 페이지에서 **범위 추가** 를 선택하고 생성된 하나 이상의 적응형 범위를 선택합니다. 그런 다음 하나 이상의 위치를 ​​선택합니다. 선택할 수 있는 위치는 추가된 [범위 유형](retention-settings.md#configuration-information-for-adaptive-scopes)에 따라 다릅니다. 예를 들어 **사용자** 의 범위 유형만 추가한 경우 **Exchange 이메일** 은 선택할 수 있지만 **SharePoint 사이트** 는 선택할 수 없습니다. 
    
    - **정적** 을 선택한 경우: **위치 선택** 페이지에서 Teams 및 Yammer의 위치를 ​​제외한 모든 위치를 켜거나 끕니다. 각 위치에 대해 설정을 기본값으로 유지하여 [전체 위치에 정책을 적용](retention-settings.md#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다.
    
    위치 관련 정보:
    - [Exchange 전자 메일 및 Exchange 공용 폴더](retention-settings.md#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 사이트 및 OneDrive 계정](retention-settings.md#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Microsoft 365 그룹](retention-settings.md#configuration-information-for-microsoft-365-groups)
    - [비즈니스용 Skype](retention-settings.md#configuration-information-for-skype-for-business)

5. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.
    
    삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](retention-settings.md#settings-for-retaining-and-deleting-content)을 참조하세요.

6. 구성을 완료하고 설정을 저장합니다.

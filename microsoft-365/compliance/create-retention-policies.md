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
ms.custom: admindeeplinkMAC
description: 보존 정책을 사용하면 사용자가 전자 메일과 문서, 대화를 사용하여 생성하는 콘텐츠를 효율적으로 유지 관리할 수 있습니다. 원하는 내용을 유지하고 원하지 않는 항목을 제거하세요.
ms.openlocfilehash: ec138414078d18915c26755867d2f1a792573cfe
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189456"
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

보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.

### <a name="retention-policy-for-teams-locations"></a>Teams 위치 보존 정책

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 보존 정책 만들기 구성을 시작하고 새 보존 정책의 이름을 지정합니다.

3. **정책을 적용할 위치 선택** 페이지의 경우 Teams의 위치 중 일부 또는 전부를 선택합니다.
    - **Teams 채널 메시지**: 표준 채널 채팅 및 표준 채널 모임의 메시지이지만 자체 정책 위치가 있는 [비공개 채널](/microsoftteams/private-channels)에서 보낸 메시지는 아닙니다.
    - **Teams 채팅**: 비공개 1:1 채팅, 그룹 채팅 및 모임 채팅의 메시지입니다.
    - **Teams 비공개 채널 메시지**: 비공개 채널 채팅 및 비공개 채널 모임의 메시지입니다.
    
   기본적으로 [모든 팀과 모든 사용자가 선택](#a-policy-that-applies-to-entire-locations)되어 있지만 **편집** 옵션을 선택하여 [특정 포함 또는 제외](#a-policy-with-specific-inclusions-or-exclusions)에 대한 보존 정책을 구성하여 이를 구체화할 수 있습니다. 그러나 기본값을 변경하기 전에 포함 또는 제외되도록 구성할 때 메시지를 삭제하는 보존 정책의 다음과 같은 결과에 유의해야 합니다.
    
    - 그룹 채팅 메시지 및 비공개 채널 메시지의 경우 메시지 복사본이 채팅에 포함된 각 사용자의 사서함에 저장되므로 정책이 할당되지 않은 사용자의 eDiscovery 결과에 메시지 복사본이 계속 반환됩니다.
    - 정책을 할당하지 않은 사용자의 경우 삭제된 메시지가 Teams 검색 결과에 반환되지만 사용자에게 할당된 정책에서 영구적으로 삭제한 결과 메시지 내용은 표시되지 않습니다.

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.

   삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.

5. 구성을 완료하여 설정을 저장합니다.

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

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 새 보존 정책을 만듭니다.

3. **정책을 적용할 위치 선택** 페이지에 대해, Yammer에 대한 위치인 **Yammer 커뮤니티 메시지** 및 **Yammer 사용자 메시지** 중 하나 또는 두 가지 모두를 전환합니다.
    
    > [!IMPORTANT]
    > Yammer 사용자 메시지에 대한 보존 정책을 만들 수 있지만 이 위치에 대한 보존 정책은 모든 커뮤니티 구성원에 대한 Yammer 앱에서 커뮤니티 메시지를 삭제할 수 있습니다.
    > 
    > 이 옵션을 선택하고 사용자 메시지를 삭제하도록 보존 정책이 구성되는 경우 이 의미를 이해해야 합니다. 자세한 내용은 [Yammer에서 보존 작업이 작동하는 방식](retention-policies-yammer.md#how-retention-works-with-yammer)을 참조하세요.
    
    기본적으로 모든 커뮤니티와 사용자가 선택되지만 포함하거나 제외할 커뮤니티와 사용자를 지정하여 세분화할 수 있습니다.
    
    Yammer 사용자 메시지의 경우: 
    - 기본값 **모두** 를 그대로 두면 Azure B2B 게스트 사용자가 포함되지 않습니다. 
    - **포함된** 열에 대해 **편집** 을 선택하는 경우 해당 계정을 알고 있는 경우 외부 사용자에게 보존 정책을 적용할 수 있습니다.

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요. 
    
    삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.

5. 구성을 완료하여 설정을 저장합니다.

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

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 보존 정책 만들기 구성을 시작하고 새 보존 정책의 이름을 지정합니다.

3. **정책을 적용할 위치 선택** 페이지의 경우 Teams의 위치를 제외한 모든 위치를 켜거나 끕니다. 각 위치에 대해 설정을 기본값으로 유지하여 [전체 위치에 정책을 적용](#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다.

    위치 관련 정보:
    - [Exchange 전자 메일 및 Exchange 공용 폴더](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 사이트 및 OneDrive 계정](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Microsoft 365 그룹](#configuration-information-for-microsoft-365-groups)
    - [비즈니스용 Skype](#configuration-information-for-skype-for-business)

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.

    삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.

5. 구성을 완료하여 설정을 저장합니다.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Exchange 전자 메일 및 Exchange 공용 폴더에 대한 구성 정보

**Exchange 이메일** 위치는 사서함 수준에서 보존 설정을 적용하여 사용자의 이메일, 캘린더 및 기타 사서함 항목에 대한 보존을 지원합니다. 공유 사서함도 지원됩니다.

보존 설정을 **모든 받는 사람** 에 적용하면 [비활성 사서함](create-and-manage-inactive-mailboxes.md)이 포함됩니다. 그러나 이 기본값을 변경하고 [특정 포함 또는 제외](#a-policy-with-specific-inclusions-or-exclusions)를 구성하는 경우 비활성 사서함은 지원되지 않으며 해당 사서함에 대해 보존 설정이 적용되거나 제외되지 않습니다.

또한 리소스 사서함 및 Microsoft 365 그룹 사서함은 **모든 받는 사람** 기본값 또는 특정 포함 또는 제외에 대해 지원되지 않습니다. Microsoft 365 그룹 사서함의 경우 대신 **Microsoft 365 그룹** 위치를 선택합니다.

포함하거나 제외할 받는 사람을 선택하는 경우 메일 그룹 및 전자 메일 사용이 가능한 보안 그룹을 선택할 수 있습니다. 내부적으로 이러한 그룹은 구성 시 자동으로 확장되어 그룹에 있는 사용자의 사서함을 선택합니다. 해당 그룹의 멤버십이 나중에 변경되면 기존 보존 정책이 자동으로 업데이트되지 않습니다.

Exchange에 대한 보존 설정을 구성할 때 포함 및 제외되는 사서함 항목에 대한 자세한 내용은 [보존 및 삭제에 포함된 항목](retention-policies-exchange.md#whats-included-for-retention-and-deletion)을 참조하세요.

**Exchange 공용 폴더** 위치는 보존 설정을 모든 공용 폴더에 적용하며 폴더 또는 사서함 수준에서 적용될 수 없습니다.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>SharePoint 사이트 및 OneDrive 계정에 대한 구성 정보

**SharePoint 사이트** 위치를 선택할 때 보존 정책을 사용하여 SharePoint 커뮤니케이션 사이트, Microsoft 365 그룹으로 연결되지 않는 팀 사이트 및 클래식 사이트에서 문서를 보존하고 삭제할 수 있습니다. Microsoft 365 그룹에서 연결된 팀 사이트는 이 옵션으로 지원되지 않으며 대신 해당 그룹의 사서함, 사이트 및 파일에 있는 콘텐츠에 적용되는 **Microsoft 365 그룹** 위치를 사용합니다.

보존 정책이 사이트 수준에서 적용되더라도 보존 설정은 문서에만 적용됩니다. SharePoint 및 OneDrive에 대한 보존 설정을 구성할 때 포함되고 제외되는 항목에 대한 자세한 내용은 [보존 및 삭제에 포함되는 항목](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)을 참조하세요.

SharePoint 사이트 또는 OneDrive 계정의 위치를 지정하는 경우, 사이트에 액세스할 수 있는 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정하는 시점에 유효성 검사가 수행되지 않습니다. 그러나 지정하는 SharePoint 사이트는 구성 종료 시 존재하는지 확인됩니다. 이 검사에 실패하는 경우, 입력한 URL에 대한 유효성 검사에 실패했다는 메시지가 표시되고 유효성 검사가 통과한 후에 구성 프로세스에서 보존 정책이 만들어집니다. 이 메시지가 표시되는 경우, 구성에서 돌아가서 URL을 변경하거나 보존 정책에서 사이트를 제거합니다.

포함하거나 제외할 개별 OneDrive 계정을 지정하려면 [조직의 모든 사용자 OneDrive URL 목록 가져오기](/onedrive/list-onedrive-urls)를 참조하세요.

> [!NOTE]
> 포함하거나 제외할 개별 OneDrive 계정을 지정할 때 OneDrive 계정이 [사전 프로비전](/onedrive/pre-provision-accounts)되어 있지 않으면 사용자가 OneDrive에 처음 액세스할 때까지 URL이 생성되지 않는다는 점에 유의하세요.
> 
> 또한 사용자의 UPN이 변경되면 OneDrive URL이 [자동적으로 변경](/onedrive/upn-changes)됩니다. 예를 들어, 이름 변경 이벤트(예: 결혼)입니다. 또는 조직의 이름 바꾸기 또는 비즈니스 재구성을 지원하기 위해 도메인 이름을 변경합니다. UPN이 변경되면 여기에서 지정한 OneDrive URL을 업데이트해야 합니다.

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 그룹에 대한 구성 정보

Microsoft 365 그룹(이전의 Office 365 그룹)의 콘텐츠를 보존하거나 삭제하려면 **Microsoft 365 그룹** 위치를 사용합니다. Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다. **Exchange 전자 메일** 위치에서 처음에 포함하거나 제외할 그룹 사서함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 발생합니다.

Microsoft 365 그룹에 적용되는 보존 정책에는 그룹 사서함 및 SharePoint Teams 사이트가 기본값으로 포함됩니다. SharePoint Teams 사이트에 저장된 파일은 이 위치에 포함되지만 Teams 대화 또는 Teams 채널 메시지가 고유한 보존 정책 위치를 가지지 않습니다.

보존 정책을 Microsoft 365 사서함에만 적용되거나 연결된 SharePoint 팀 사이트에만 적용하기 위해 기본값을 변경하려면 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet을 *Applications* 매개 변수와 함께 사용합니다.

- 그룹과 연결된 Microsoft 365 사서함의 경우`Group:Exchange`
- 그룹과 연결된 SharePoint 사이트의 경우 `Group:SharePoint`

선택한 Microsoft 365 그룹이 사서함과 SharePoint 사이트의 기본값으로 돌아가기 위해 `Group:Exchange,SharePoint`를 지정하세요.

### <a name="configuration-information-for-skype-for-business"></a>비즈니스용 Skype에 대한 구성 정보

다른 위치와 달리 Skype 위치의 상태를 전환하여 모든 사용자를 자동으로 포함할 수 없습니다. 대신 해당 위치를 켤 때 **편집** 옵션을 선택하여 대화를 유지하려는 사용자를 수동으로 선택해야 합니다.

![보존 정책을 위한 Skype 위치 편집.](../media/skype-location-retention-policies.png)

이 **편집** 옵션을 선택한 후 **비즈니스용 Skype** 창에서 **이름** 열 앞에 숨겨진 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다. 그러나 각 사용자가 정책의 특정 포함사항으로 간주된다는 점을 이해해야 합니다. 따라서 이 상자를 선택하여 1,000명의 사용자를 포함하는 경우, 포함할 1,000명의 사용자를 수동으로 선택한 것과 같으며 이는 비즈니스용 Skype에 대해 지원되는 최대를 선택하는 것과 같습니다.

Outlook 폴더인 **대화 내용** 은 Skype 아카이빙은 관계가 없는 기능 **대화 내용** 은 최종 사용자가 끌 수 있지만, Skype 아카이빙은 사용자는 액세스할 수 없고 eDiscovery에서만 액세스 가능한 숨김 폴더에 Skype 대화 사본을 저장하는 기능

## <a name="settings-for-retaining-and-deleting-content"></a>콘텐츠를 보존 및 삭제하기 위한 설정

보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.

- 보존 전용

    이 구성에서는 **특정 기간에 대한 항목을 보존** 을 선택하고 **보존 기간의 종료 시, 아무 작업도 수행하지 않습니다**. 또는 **항목을 영구적으로 보존** 을 선택합니다.

- 보존 후 삭제

    이 구성에서는 **특정 기간에 대한 항목을 보존** 을 선택하고 **보존 기간의 종료 시, 항목을 자동으로 삭제합니다**.

- 삭제 전용

    이 구성에서는 **특정 기간에 도달했을 때만 항목 삭제** 를 선택합니다.

### <a name="retaining-content-for-a-specific-period-of-time"></a>특정 기간 동안 콘텐츠 보존

보존 정책을 구성하면 항목을 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다. 또는 항목이 영구적으로 보존됩니다.

보존 정책을 구성하면 콘텐츠를 영구적으로 또는 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다. 콘텐츠 보존 기간은 보존 정책이 적용된 시점이 아닌 콘텐츠 생성 시점을 기준으로 계산됩니다.

보존 기간이 시작되는 경우, 또한 콘텐츠가 언제 만들어졌는지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Microsoft 365 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.

예제:

- SharePoint: 내용을 마지막으로 수정한 후 7년 동안 사이트 모음에 항목을 보관하고 해당 사이트 모음에 있는 문서가 6년 동안 수정되지 않은 경우, 문서가 수정되지 않은 경우, 문서는 1년 더만 보존됩니다. 문서를 다시 편집할 경우, 문서의 연령이 새로운 마지막 수정 날짜로부터 계산되며, 7년 더 유지됩니다.

- Exchange: 7년 동안 우편함에 항목을 보관하고 6년 전에 메시지가 발송된 경우 메시지는 1년 동안만 유지됩니다. Exchange 항목의 경우 기간은 수신 전자 메일에 대해 수신된 날짜 또는 송신 전자 메일에 대해 전송된 날짜를 기준으로 합니다. 마지막으로 수정한 시점을 기준으로 항목을 유지하면 OneDrive 및 SharePoint의 사이트 컨텐츠에만 적용됩니다.

보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.

![보존 설정 페이지.](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>특정 사용 기간보다 오래된 콘텐츠 삭제

보존 정책은 항목을 보존했다가 삭제하거나, 혹은 보존하지 않고 오래된 콘텐츠를 삭제할 수 있습니다.

두 경우 모두, 보존 정책이 항목을 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.

따라서 보존 정책을 처음으로 할당하기 전에 특히 해당 정책이 항목을 삭제할 때 먼저 기존 콘텐츠의 사용 기간과 해당 콘텐츠에 미치는 영향을 고려해야 합니다. 또한 새 정책을 할당하기 전에 사용자에게 가능한 영향을 평가할 시간을 제공하기 위해 새 정책을 전달해야 할 수도 있습니다.

### <a name="a-policy-that-applies-to-entire-locations"></a>전체 위치에 적용되는 정책

위치를 선택하는 경우 비즈니스용 Skype를 제외하고, 위치의 상태가 **On** 인 경우, 기본 설정은 **모두** 가 됩니다.

보존 정책이 전체 위치의 조합에 적용되는 경우, 정책에 포함할 수 있는 수혜자, 사이트, 계정, 그룹 등의 수에 제한이 없습니다.

예를 들어 정책에 모든 Exchange 전자 메일과 모든 SharePoint 사이트가 포함된 경우 개수에 상관없이 모든 사이트와 수신자가 포함됩니다. 또한 Exchange의 경우 정책이 적용된 후 생성된 새 편지함이 정책을 자동으로 상속합니다.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>특정 포함 또는 제외가 적용된 정책

선택적 구성을 사용하여 보존 설정의 범위를 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트로 지정하는 경우 정책별로 알아야 할 몇 가지 제한이 있습니다. 자세한 내용은 [보존 정책 및 보존 레이블 정책 제한](retention-limits.md)을 참조하세요. 

선택적 구성을 사용하여 보존 설정의 범위를 지정하려면 해당 위치의 **상태** 가 **켜짐** 인지 확인한 후 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다.

> [!WARNING]
> 마지막 구성을 포함했다가 제거하면 해당 위치에 대해 **모두** 로 되돌아갑니다.  정책을 저장하기 전에 원하는 구성인지 확인합니다.
>
> 예를 들어 데이터를 삭제하도록 구성된 보존 정책에 포함할 SharePoint 사이트 하나를 지정한 다음 단일 사이트를 제거하면 기본적으로 모든 SharePoint 사이트는 데이터를 영구적으로 삭제하는 보존 정책의 적용을 받습니다. Exchange 수신인, OneDrive 계정, 팀 채팅 사용자 등의 경우에도 마찬가지
>
> 이 시나리오에서 위치에 대한 **모두** 설정을 보존 정책의 적용을 받지 않으려면 위치를 해제합니다. 또는 정책에서 제외할 제외 항목을 지정합니다.

## <a name="updating-retention-policies"></a>보존 정책 업데이트

다음 내용을 포함하는 보존 정책을 만들고 저장한 후에는 일부 설정을 변경할 수 없습니다.
- 보존 기간 및 보존 기간의 시작 시기를 제외한 보존 정책 이름 및 보존 설정입니다.

보존 정책을 편집하고 항목이 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 항목 외에 이 항목에도 자동으로 적용됩니다.

일반적으로 이 업데이트는 아주 간단하지만 며칠이 걸릴 수 있습니다. Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 준수 센터의 보존 정책 상태가 **켜기(보류)** 에서 **켜기(성공)** 으로 변경됩니다.

## <a name="locking-the-policy-to-prevent-changes"></a>변경 방지를 위한 정책 잠금

아무도 정책을 끄거나, 삭제하거나, 제한 수준을 낮출 수 없도록 하려면, [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 보존 잠금 사용](retention-preservation-lock.md)을 참조하세요.

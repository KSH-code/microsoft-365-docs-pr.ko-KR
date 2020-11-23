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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 정책을 사용하면 사용자가 전자 메일, 문서 및 대화로 생성하는 콘텐츠를 매우 효율적으로 제어할 수 있습니다. 원하는 것을 유지하고 원하지 않는 것은 없애세요.
ms.openlocfilehash: bcf0ef5aa76113102013bc20fca02e6d516c3203
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376581"
---
# <a name="create-and-configure-retention-policies"></a>보존 정책 만들기 및 구성

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하기 위해 보존 정책을 사용합니다.

보존 정책을 사용하면 사이트 또는 편지함 수준에서 위치별로 컨텐츠에 대해 동일한 보존 설정을 할당하여 이 작업을 매우 효율적으로 수행할 수 있습니다. 보존 정책 또는 보존 레이블을 사용할지 확실하지 않으면 [보존 정책 및 보존 레이블](retention.md#retention-policies-and-retention-labels)을(를) 참조합니다.

보존 정책과 보존이 작동하는 방식에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

조직의 글로벌 관리자는 보존 정책을 만들고 편집할 수 있는 모든 권한을 가집니다. 글로벌 관리자로 로그인하지 않는 경우 [유지 정책 및 보존 레이블](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을(를) 생성하고 관리하는 데 필요한 권한입니다.

## <a name="create-and-configure-a-retention-policy"></a>보존 정책 만들기 및 구성하기

보존 정책은 여러 위치를 지원할 수 있지만 지원되는 모든 위치를 포함하는 단일 보존 정책을 만들 수는 없습니다.

- Exchange 전자 메일
- SharePoint 사이트
- OneDrive 계정
- Microsoft 365 그룹
- 비즈니스용 Skype
- Exchange 공용 폴더
- Teams 채널 메시지
- Teams 채팅
- Yammer 커뮤니티 메시지
- Yammer 개인 메시지

보존 정책을 생성할 때 Teams 또는 Yammer 위치를 선택하면 다른 위치는 자동으로 제외됩니다. 따라서 Teams 또는 Yammer 위치를 포함해야 하는지에 따라 다음 지침을 따라야 합니다.

- [Teams 위치](#retention-policy-for-teams-locations)에 대한 보존 정책에 대한 지침
- [Yammer 위치에 대한 보존 정책에 대한 지침](#retention-policy-for-yammer-locations)
- [Teams 및 Yammer](#retention-policy-for-locations-other-than-teams-and-yammer) 이외의 위치에 대한 보존 정책에 대한 지침

보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.

### <a name="retention-policy-for-teams-locations"></a>Teams 위치 보존 정책

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.

3. **정책을 적용하기 위한 위치 선택** 페이지에서, Teams에 대한 하나 혹은 양쪽 위치를 선택합니다. **Teams 채널 메시지** 및 **Teams 채팅**.

   **Teams 채널 메시지** 의 경우 [개인 채널이 아닌 표준 채널의 메시지](https://docs.microsoft.com/microsoftteams/private-channels)가 포함됩니다. 현재 개인 채널은 보존 정책에서 지원되지 않습니다.

   기본적으로 [모든 팀과 모든 사용자가 선택되어 있지만](#a-policy-that-applies-to-entire-locations), [**선택** 및 **배제** 옵션](#a-policy-with-specific-inclusions-or-exclusions)을 선택하여 이를 구체화할 수 있습니다.

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.

   지정된 기간 동안 내용을 삭제하지 않고 그대로 유지한 다음 삭제하거나 지정된 기간 후에 내용만 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지의 [내용 유지 및 삭제 설정](#settings-for-retaining-and-deleting-content)을(를) 참조하시기 바랍니다.

5. 마법사를 완료하여 설정을 저장합니다.

Teams 보존 정책에 대한 자세한 내용은 Teams 설명서에서 [Microsoft Teams의 보존 정책](https://docs.microsoft.com/microsoftteams/retention-policies)을 참조하세요.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Teams 지원에 필요한 추가 보존 정책

Teams는 대화와 채널 메시지 그 이상입니다. Microsoft 365 그룹(이전의 Office 365 그룹)에서 생성된 팀이 있는 경우 **Microsoft 365 그룹** 위치를 사용하여 해당 Microsoft 365 그룹을 포함하는 보존 정책을 추가로 구성해야 합니다. 이 보존 정책은 그룹의 편지함, 사이트 및 파일에 있는 콘텐츠에 적용됩니다.

Microsoft 365 그룹에 연결되어 있지 않은 팀 사이트가 있는 경우, Teams에서 파일을 보존하고 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.

- 채팅에서 공유되는 파일은 해당 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다.

- 채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다.

> [!TIP]
> 특정 팀의 SharePoint 사이트 및 특정 팀 사용자의 OneDrive 계정을 선택하여 Microsoft 365 그룹에 연결되어 있지 않으면 해당 팀의 파일에 보존 정책을 적용할 수 있습니다.

Microsoft 365 그룹, SharePoint 사이트 또는 OneDrive 계정에 적용된 보존 정책은 해당 메시지를 삭제하기 전에 Teams 대화 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다. 이 시나리오에서는 파일이 Teams 메시지에 계속 표시되지만 사용자가 파일을 선택하면 "파일 없음" 오류가 발생합니다. 이러한 동작은 보존 정책에만 국한되지 않으며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.

### <a name="retention-policy-for-yammer-locations"></a>Yammer 위치에 대한 보존 정책

> [!NOTE]
> Yammer에 대 한 보존 정책이 미리 보기에서 배포됩니다. Yammer에 대한 새 위치가 아직 표시되지 않는 경우 몇주 후에 다시 시도하세요.
>
> 이 기능을 사용하려면 Yammer 네트워크가 하이브리드 모드가 아니라 [기본 모드](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)여야 합니다.

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 새 보존 정책을 만듭니다.

3. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요. 
    
    지정된 기간 동안 내용을 삭제하지 않고 그대로 유지한 다음 삭제하거나 지정된 기간 후에 내용만 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지의 [내용 유지 및 삭제 설정](#settings-for-retaining-and-deleting-content)을(를) 참조하시기 바랍니다.
    
    이 옵션은 Yammer 위치에 지원되지 않으므로 **고급 보존 설정 사용** 을 선택하지 않습니다. 

4. **위치 선택** 페이지에 대해 **특정 위치 선택** 를 선택합니다. 그런 다음 Yammer에 대한 위치 중 하나 또는 둘 모두를 전환합니다. **Yammer 커뮤니티 메시지** 및 **Yammer 개인 메시지**.
    
    기본적으로 모든 커뮤니티와 사용자가 선택되지만 포함하거나 제외할 커뮤니티와 사용자를 지정하여 세분화할 수 있습니다.
    
    Yammer 개인 메시지의 경우 다음을 수행합니다. 
    - 기본값 **모두** 를 그대로 두면 Azure B2B 게스트 사용자가 포함되지 않습니다. 
    - **사용자 선택** 을 선택한 경우, 계정을 알고 있는 외부 사용자에게 보존 정책을 적용할 수 있습니다.

5. 마법사를 완료하여 설정을 저장합니다.

Yammer용 보존 정책이 작동하는 방식에 대한 자세한 내용은 [Yammer용 보존 정보](retention-policies-yammer.md)를 참조하세요.

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Yammer를 지원하려면 추가 보존 정책이 필요합니다.

Yammer는 단지 커뮤니티 메시지와 사적인 메시지 그 이상입니다. Yammer 네트워크의 전자 메일 메시지를 유지 및 삭제하려면 **Microsoft 365 그룹** 위치를 사용하여 Yammer에 사용되는 Microsoft 365 그룹을 포함하는 추가 보존 정책을 구성합니다. 

Yammer에 저장된 파일을 유지 및 삭제하려면 **Microsoft Office SharePoint Online 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.

- 개인 메시지에서 공유되는 파일은 파일을 공유한 사용자의 OneDrive 계정에 저장됩니다. 

- 커뮤니티에 업로드된 파일은 Yammer 커뮤니티의 Microsoft Office SharePoint Online 사이트에 저장됩니다.

SharePoint 사이트 또는 OneDrive 계정에 적용된 보존 정책은 해당 메시지가 삭제되기 전에 Yammer 메시지에 참조된 파일을 삭제할 수 있습니다. 이 시나리오에서는 Yammer 메시지에 파일이 계속 표시되지만 사용자가 파일을 선택하면 "File not found" 오류가 발생합니다. 이러한 동작은 보존 정책에만 국한되지 않으며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Teams 및 Yammer 이외의 위치에 대한 보존 정책

이러한 서비스에 적용되는 보존 정책에 대해 다음 지침을 사용합니다.

- Exchange: 전자 메일 및 공용 폴더
- SharePoint: 사이트
- OneDrive: 계정
- Microsoft 365 그룹
- 비즈니스용 Skype

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존** 을 선택합니다.

2. **새 보존 정책** 을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.

3. **위치 선택** 페이지의 경우 팀 위치를 제외한 모든 위치를 설정하거나 해제합니다. 각 위치에 대해 정책을 [(전체 위치](#a-policy-that-applies-to-entire-locations))에 적용하거나 [특정 항목에 포함 및 제외](#a-policy-with-specific-inclusions-or-exclusions)를 기본값으로 둘 수 있습니다.

    위치 관련 정보:
    - [Exchange 전자 메일 및 Exchange 공용 폴더](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 사이트 및 OneDrive 계정](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Microsoft 365 그룹](#configuration-information-for-microsoft-365-groups)
    - [비즈니스용 Skype](#configuration-information-for-skype-for-business)

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.

    지정된 기간 동안 내용을 삭제하지 않고 그대로 유지한 다음 삭제하거나 지정된 기간 후에 내용만 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지의 [내용 유지 및 삭제 설정](#settings-for-retaining-and-deleting-content)을(를) 참조하시기 바랍니다.

5. 마법사를 완료하여 설정을 저장합니다.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Exchange 전자 메일 및 Exchange 공용 폴더에 대한 구성 정보

**Exchange 전자 메일** 위치는 사서함 수준에서 보존 설정을 적용하여 사용자의 전자 메일, 일정 및 기타 사서함 항목에 대한 보존을 지원합니다.

Exchange에 대한 보존 설정을 구성할 때 포함되고 제외되는 항목에 대한 자세한 내용은 [보존 및 삭제에 포함되는 항목](retention-policies-exchange.md#whats-included-for-retention-and-deletion)을 참조하세요.

Microsoft 365 그룹에 Exchange 편지함이 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책은 Microsoft 365 그룹 편지함에 콘텐츠를 포함하지 않습니다. 이러한 편지함의 콘텐츠를 유지하려면 **Microsoft 365 그룹** 위치를 선택합니다.

**Exchange 공용 폴더** 위치는 보존 설정을 모든 공용 폴더에 적용하며 폴더 또는 사서함 수준에서 적용될 수 없습니다.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Microsoft Office SharePoint Online 사이트 및 OneDrive 계정에 대한 구성 정보

**SharePoint 사이트** 위치를 선택하면 보존 정책이 SharePoint 통신 사이트, Microsoft 365 그룹에 의해 연결되지 않은 팀 사이트 및 클래식 사이트의 문서를 유지 및 삭제할 수 있습니다. Microsoft 365 그룹에 의해 연결된 팀 사이트는 이 옵션에서 지원되지 않으며 대신 그룹의 편지함, 사이트 및 파일의 컨텐츠에 적용되는 **Microsoft 365 그룹** 위치를 사용합니다.

보존 정책은 사이트 수준에서 적용되지만 문서에만 보존 설정이 적용됩니다. SharePoint 및 OneDrive에 대한 보존 설정을 구성할 때 포함되거나 제외되는 항목에 대한 자세한 내용은 [보존 및 삭제에 포함된 항목](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)을(를) 참조하시기 바랍니다. 

SharePoint 사이트 또는 OneDrive 계정에 대한 위치를 지정하는 경우 사이트에 액세스할 수 있는 사용 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정할 때 유효성 검사가 수행되지 않습니다. 그러나 지정한 SharePoint 사이트는 마법사의 끝에 존재하는지 확인합니다. 이 검사가 실패하면 입력한 URL에 대한 유효성 검사가 실패했다는 메시지가 표시되고 유효성 검사 통과 전까지 마법사가 보존 정책을 생성하지 않습니다. 이 메시지가 표시되면 마법사로 돌아가서 URL을 변경하거나 보존 정책에서 사이트를 제거합니다.

포함하거나 제외할 개별 OneDrive 계정을 지정하려면 URL은 `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com` 형식이어야 합니다.

예를 들어, "rsimone"라는 사용자 이름을 보유한 Contoso 테넌트에 있는 사용자의 경우: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

테넌트의 구문을 확인하고 사용자 URL을 확인하려면, [조직에 있는 모든 사용자 OneDrive URL 목록 가져오기](https://docs.microsoft.com/onedrive/list-onedrive-urls)를 참조하세요.

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 그룹에 대한 구성 정보

Microsoft 365 그룹(이전의 Office 365 그룹)의 콘텐츠를 유지하거나 삭제하려면 **Microsoft 365 그룹** 위치를 사용합니다. Microsoft 365 그룹에 Exchange 편지함이 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책은 Microsoft 365 그룹 편지함에 콘텐츠를 포함하지 않습니다. 또한 처음에 **Exchange e-메일** 위치를 사용하여 포함하거나 제외할 그룹 편지함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 표시됩니다.

Microsoft 365 그룹에 적용된 보존 정책에는 그룹 편지함 및 Teams 사이트가 포함됩니다. 그룹 생성 시 팀 사이트를 선택했거나 나중에 그룹에 추가한 경우 이 사이트는 그룹 편지함 및 Teams 사이트를 포함합니다. Teams 사이트에 저장된 파일은 이 위치에 포함되지만 Teams 대화 또는 Teams 채널 메시지가 자체 보존 정책 위치에 있는 것은 아닙니다.

### <a name="configuration-information-for-skype-for-business"></a>비즈니스용 Skype에 대한 구성 정보

Exchange 전자 메일과 달리, Skype 위치의 상태는 간단히 설정으로 전환하여 모든 사용자를 자동으로 포함할 수 없습니다. 그렇지만 해당 위치를 켜면 해당 대화를 보존하려는 사용자를 수동으로 선택할 수 있습니다.

![보존 정책을 위한 Skype 위치 선택](../media/skype-location-retention-policies.png)

**사용자 선택** 을(를) 선택할 때 **모두 선택** 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다. 그러나 각 사용자가 정책에 특정 포함으로 간주된다는 점을 이해하는 것이 중요합니다. 따라서 **모두 선택** 상자를 선택하여 1,000명의 사용자를 포함하면 수동으로 포함할 1,000명의 사용자를 선택한 경우와 동일하며 이는 비즈니스용 Skype에서 지원되는 최대값입니다.

Outlook의 **대화 내용** 폴더는 Skype 보관과 아무 관계가 없는 기능입니다. **대화 내용** 은 최종 사용자가 해제할 수 있지만 Skype 보관은 사용자는 액세스할 수 없고 eDiscovery에서 사용할 수 있는 숨겨진 폴더에 Skype 대화 사본을 저장하여 수행됩니다.

## <a name="settings-for-retaining-and-deleting-content"></a>콘텐츠를 보존 및 삭제하기 위한 설정

보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.

- 보존 전용

    이 구성의 경우 **특정 기간 동안 항목 보존** 및 **유지 기간이 끝나면 다음을 선택합니다. 아무 작업도 수행하지 않습니다**. 또는 **항목을 영구 보존** 을 선택합니다.

- 보존 후 삭제

    이 구성에서는 **특정 기간에 대한 항목을 보존** 을 선택하고 **보존 기간의 종료 시, 항목을 자동으로 삭제합니다**.

- 삭제 전용

    이 구성에서는 **특정 기간에 도달했을 때만 항목 삭제** 를 선택합니다.

### <a name="retaining-content-for-a-specific-period-of-time"></a>특정 기간 동안 콘텐츠 보존

보존 정책을 구성할 때 특정 일, 월 또는 년 수 동안 항목을 보존하도록 선택할 수 있습니다. 또는 항목을 영구적으로 보관할 수도 있습니다.

보존 정책을 구성할 때 콘텐츠를 무기한 또는 특정 일, 월 또는 년 동안 보존하도록 선택할 수 있습니다. 보존 기간은 보존 정책이 적용되는 시기가 아니라 내용 보존 기간부터 계산됩니다.

보존 기간이 시작되는 경우 또한 콘텐츠를 언제 만들어졌을지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Office 365 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.

예제:

- SharePoint: 내용을 마지막으로 수정한 후 7년 동안 사이트 모음에 항목을 보관하고 해당 사이트 모음에 있는 문서가 6년 동안 수정되지 않은 경우, 문서가 수정되지 않은 경우, 문서는 1년 더만 보존됩니다. 문서를 다시 편집할 경우, 문서의 연령이 새로운 마지막 수정 날짜로부터 계산되며, 7년 더 유지됩니다.

- Exchange: 7년 동안 우편함에 항목을 보관하고 6년 전에 메시지가 발송된 경우 메시지는 1년 동안만 유지됩니다. Exchange 항목의 경우 기간은 수신 전자 메일에 대해 수신된 날짜 또는 송신 전자 메일에 대해 전송된 날짜를 기준으로 합니다. 마지막으로 수정한 시점을 기준으로 항목을 유지하면 OneDrive 및 SharePoint의 사이트 컨텐츠에만 적용됩니다.

보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.

![보존 설정 페이지](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>특정 사용 기간보다 오래된 콘텐츠 삭제

보존 정책은 항목을 보존했다가 삭제하거나, 혹은 보존하지 않고 오래된 콘텐츠를 삭제할 수 있습니다.

두 경우 모두, 보존 정책이 항목을 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.

따라서 보존 정책을 처음으로 할당하기 전에 특히 해당 정책이 항목을 삭제할 때 먼저 기존 콘텐츠의 사용 기간과 해당 콘텐츠에 미치는 영향을 고려해야 합니다. 또한 새 정책을 할당하기 전에 사용자에게 가능한 영향을 평가할 시간을 제공하기 위해 새 정책을 전달해야 할 수도 있습니다.

### <a name="a-policy-that-applies-to-entire-locations"></a>전체 위치에 적용되는 정책

위치를 선택하는 경우 비즈니스용 Skype를 제외하고, 위치의 상태가 **On** 인 경우, 기본 설정은 **모두** 가 됩니다.

보존 정책이 전체 위치의 조합에 적용되는 경우, 정책에 포함할 수 있는 수혜자, 사이트, 계정, 그룹 등의 수에 제한이 없습니다.

예를 들어 정책에 모든 Exchange 전자 메일과 모든 SharePoint 사이트가 포함된 경우 개수에 상관없이 모든 사이트와 수신자가 포함됩니다. 또한 Exchange의 경우 정책이 적용된 후 생성된 새 편지함이 정책을 자동으로 상속합니다.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>특정 포함 또는 제외가 적용된 정책

선택적 구성을 사용하여 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 대한 보존 설정의 범위를 지정 하는 경우에만 다음의 몇 가지 제한 사항을 고려해야 합니다. 

- 보존 정책의 최대 수:
  - 1,000개의 사서함
  - 1,000개의 Microsoft 365 그룹
  - Teams 비공개 채팅에 참여하는 1,000명의 사용자
  - 100개의 사이트(OneDrive 또는 SharePoint)

테넌트에 대해 지원되는 최대 정책 수도 10,000개입니다. 이러한 항목에는 보존 정책, 보존 레이블 정책 및 자동 적용 보존 정책이 포함됩니다.

보존 정책에 이러한 제한이 적용될 가능성이 높은 경우에는 해당 정책에 제한이 없는 전체 위치에 적용되는 기본 구성을 사용합니다.

선택적 구성을 사용하여 보존 설정의 범위를 지정하려면 해당 위치의 **상태** 가 **켜짐** 인지 확인한 후 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다.

> [!WARNING]
> 마지막 구성을 포함했다가 제거하면 해당 위치에 대해 **모두** 로 되돌아갑니다.  정책을 저장하기 전에 원하는 구성인지 확인합니다.
>
> 예를 들어 데이터를 삭제하도록 구성된 보존 정책에 포함할 SharePoint 사이트 하나를 지정한 다음 단일 사이트를 제거하면 기본적으로 모든 SharePoint 사이트는 데이터를 영구적으로 삭제하는 보존 정책의 적용을 받습니다. Exchange 수신인, OneDrive 계정, Teams 채팅 사용자 등의 경우에도 마찬가지입니다.
>
> 이 시나리오에서 위치에 대한 **All** 설정을 보존 정책의 적용을 받지 않으려면 위치를 해제합니다. 또는 정책에서 제외할 제외 항목을 지정합니다.

## <a name="updating-retention-policies"></a>보존 정책 업데이트

보존 정책을 편집하고 항목이 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 항목 외에 이 항목에도 자동으로 적용됩니다.

일반적으로 이 업데이트는 매우 빠르지만 며칠이 걸릴 수 있습니다. Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 규정 준수 센터의 보존 정책 상태가 **On(대기 중)** 에서 **On(성공)**(으)로 변경됩니다.

## <a name="locking-the-policy-to-prevent-changes"></a>변경 방지를 위한 정책 잠금

아무도 정책을 끄거나, 삭제하거나, 제한 수준을 낮출 수 없도록 하려면, [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 보존 잠금 사용](retention-preservation-lock.md)을 참조하세요.

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
description: 보존 정책을 사용하면 사용자가 전자 메일, 문서 및 대화를 사용하여 생성하는 콘텐츠를 매우 효율적으로 유지 관리할 수 있습니다. 원하는 내용을 유지하고 원하지 않는 항목을 제거하세요.
ms.openlocfilehash: b992452cffbe7fa2df5e7ad02726ca337fbe0f45
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816857"
---
# <a name="create-and-configure-retention-policies"></a>보존 정책 만들기 및 구성

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하기 위해 보존 정책을 사용합니다. 

보존 정책을 사용하면 사이트 또는 사서함 수준에서 위치별로 콘텐츠의 보존 설정을 동일하게 할당하여 효율적으로 이 작업을 수행할 수 있습니다. 보존 정책 또는 보존 레이블을 사용해야 할지 확실하지 않다면 [보존 정책 및 보존 레이블](retention.md#retention-policies-and-retention-labels)을 참조하세요.

보존 정책과 보존이 작동하는 방식에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

조직의 전역 관리자는 보존 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.

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

보존 정책을 만들 때 Teams 위치 중 하나를 선택하면 다른 위치는 자동으로 제외됩니다. 따라서, 따라야 하는 지침은 Teams 위치를 포함해야 하는지에 따라 다릅니다.

- [Teams 위치 보존 정책에 대한 지침](#retention-policy-for-teams-locations)
- [Teams 이외의 위치 보존 정책에 대한 지침](#retention-policy-for-locations-other-than-teams)

보존 정책이 두 개 이상이고 보존 레이블도 사용하는 경우에는 여러 보존 설정이 동일한 콘텐츠에 적용되는 경우의 결과를 이해하기 위해 [보존 원칙 또는 우선하는 항목](retention.md#the-principles-of-retention-or-what-takes-precedence)을 참조하세요.

### <a name="retention-policy-for-teams-locations"></a>Teams 위치 보존 정책

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.

2. **새 보존 정책**을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.

3. **정책을 적용하기 위한 위치 선택** 페이지에서, Teams에 대한 하나 혹은 양쪽 위치를 선택합니다. **Teams 채널 메시지** 및 **Teams 채팅**.
     
    **Teams 채널 메시지**의 경우, 표준 채널이지만 [비공개 채널](https://docs.microsoft.com/microsoftteams/private-channels)의 메시지는 포함되지 않습니다. 현재 개인 채널은 보존 정책에서 지원되지 않습니다.
    
    기본적으로 [모든 팀과 모든 사용자가 선택되어 있지만](#a-policy-that-applies-to-entire-locations), [**선택** 및 **배제** 옵션](#a-policy-with-specific-inclusions-or-exclusions)을 선택하여 이를 구체화할 수 있습니다.

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.
    
    삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.
    
5. 마법사를 완료하여 설정을 저장합니다.

Teams 보존 정책에 대한 자세한 내용은 Teams 설명서에서 [Microsoft Teams의 보존 정책](https://docs.microsoft.com/microsoftteams/retention-policies)을 참조하세요.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Teams 지원에 필요한 추가 보존 정책

Teams는 채팅 및 채널 메시지 그 이상입니다. Microsoft 365 그룹에서 만든 팀(이전에는 Office 365 그룹)을 가진 경우 **Office 365 그룹** 위치를 사용하여 Microsoft 365 그룹을 포함하는 보존 정책을 추가적으로 구성해야 합니다. 이 보존 정책은 그룹의 사서함, 사이트 및 파일의 콘텐츠에 적용됩니다.

Microsoft 365 그룹에 연결되어 있지 않은 팀 사이트가 있는 경우, Teams에서 파일을 보존하고 삭제하려면 **SharePoint 사이트** 또는 **OneDrive 계정** 위치를 포함하는 보존 정책이 필요합니다.

- 채팅에서 공유되는 파일은 해당 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다. 

- 채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다.

> [!TIP]
> 특정 팀의 SharePoint 사이트 및 특정 팀 사용자의 OneDrive 계정을 선택하여 Microsoft 365 그룹에 연결되어 있지 않으면 해당 팀의 파일에 보존 정책을 적용할 수 있습니다.

Microsoft 365 그룹, SharePoint 사이트 또는 OneDrive 계정에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다. 이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만 사용자가 파일을 선택하면 "파일을 찾을 수 없음" 오류가 발생합니다. 이 동작은 보존 정책에만 국한된 것이 아니며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.


### <a name="retention-policy-for-locations-other-than-teams"></a>Teams 이외의 위치 보존 정책

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.

2. **새 보존 정책**을 선택하여 보존 정책 만들기 마법사를 시작하고 새 보존 정책의 이름을 지정합니다.

3. **위치 선택** 페이지를 선택하려면 Teams 위치를 제외한 모든 위치를 토글로 설정하거나 해제합니다. 각 위치에 대해 설정을 기본값으로 유지하여 [전체 위치에 정책을 적용](#a-policy-that-applies-to-entire-locations)하거나 [포함 및 제외를 지정](#a-policy-with-specific-inclusions-or-exclusions)할 수 있습니다. 
    
    위치 관련 정보:
    - [Exchange 전자 메일 및 Exchange 공용 폴더](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 사이트 및 OneDrive 계정](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Office 365 그룹](#configuration-information-for-microsoft-365-groups)
    - [비즈니스용 Skype](#configuration-information-for-skype-for-business)

4. **콘텐츠를 유지, 삭제 또는 둘 다 수행할지 결정** 마법사 페이지에서 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요.
    
    삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하기 위한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.

5. 마법사를 완료하여 설정을 저장합니다.


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Exchange 전자 메일 및 Exchange 공용 폴더에 대한 구성 정보

**Exchange 전자 메일** 위치는 사서함 수준에서 보존 설정을 적용하여 사용자의 전자 메일, 일정 및 기타 사서함 항목에 대한 보존을 지원합니다.

다음 메일 항목 포함: 첨부 파일, 작업 및 일정 항목이 끝나는 날짜, 메모가 포함된 메일 메시지(임시 보관함 포함) 종료 날짜가 없는 모든 작업 및 일정 항목은 포함되지 않습니다. Skype 및 Teams에 저장된 메시지와 같이 사서함에 저장된 다른 항목은 이 위치에 포함되지 않습니다. 이러한 항목은 자체 보존 위치가 있습니다.

Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다. 이러한 사서함의 콘텐츠를 보존하려면 **Office 365 그룹** 위치를 선택하세요.

**Exchange 공용 폴더** 위치는 보존 설정을 모든 공용 폴더에 적용하며 폴더 또는 사서함 수준에서 적용될 수 없습니다.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>SharePoint 사이트 및 OneDrive 계정에 대한 구성 정보

**SharePoint 사이트** 위치를 선택할 때 보존 정책을 사용하여 SharePoint 커뮤니케이션 사이트, Office 365 그룹으로 연결되지 않는 팀 사이트 및 클래식 사이트에서 문서를 보존하고 삭제할 수 있습니다. Office 365 그룹에서 연결된 팀 사이트는 이 옵션에서 지원되지 않으며 대신 해당 그룹의 사서함, 사이트 및 파일에 있는 콘텐츠에 적용되는 **Office 365 그룹** 위치를 사용합니다.

보존 정책이 사이트 수준에서 적용되더라도 보존 설정은 문서에만 적용됩니다. 보존 설정은 사이트 내의 라이브러리, 목록 및 폴더를 포함하는 구성 구조에 적용되지 않습니다. 

SharePoint 사이트 또는 OneDrive 계정의 위치를 지정하는 경우, 사이트에 액세스할 수 있는 권한이 필요하지 않으며 **위치 편집** 페이지에서 URL을 지정하는 시점에 유효성 검사가 수행되지 않습니다. 그러나 SharePoint 사이트를 색인화해야 하며 마법사 종료 시 지정한 사이트가 존재하는지 검사합니다.

이 검사에 실패하는 경우, 입력한 URL에 대한 유효성 검사에 실패했다는 메시지가 표시되고 유효성 검사가 통과한 후에 마법사에서 보존 정책이 만들어집니다. 이 메시지가 표시되는 경우, 마법사에서 돌아가서 URL을 변경하거나 보존 정책에서 사이트를 제거합니다.

포함하거나 제외할 개별 OneDrive 계정을 지정하려면 URL은 `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com` 형식이어야 합니다.

예를 들어, "rsimone"라는 사용자 이름을 보유한 Contoso 테넌트에 있는 사용자의 경우: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

테넌트의 구문을 확인하고 사용자 URL을 확인하려면, [조직에 있는 모든 사용자 OneDrive URL 목록 가져오기](https://docs.microsoft.com/onedrive/list-onedrive-urls)를 참조하세요.

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 그룹에 대한 구성 정보

Microsoft 365 그룹(이전 이름: Office 365 그룹)의 콘텐츠를 보존하거나 삭제하려면 **Office 365 그룹** 위치를 사용합니다. Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다. 또한 **Exchange 전자 메일** 위치에서 처음에 포함하거나 제외할 그룹 사서함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 발생합니다.

만약 팀 사이트가 그룹이 만들어 졌을 때 선택되었거나 혹은 나중에 그룹에 추가 된 경우, 그룹 사서함 및 팀 사이트를 포함한 Microsoft 365 그룹에 적용되는 보존 정책입니다. 팀 사이트에 저장된 파일은 이 위치에 포함되지만 자신의 보존 정책 위치가 있는 Teams 채팅 혹은 Teams 채널 메시지는 포함되지 않습니다.

### <a name="configuration-information-for-skype-for-business"></a>비즈니스용 Skype에 대한 구성 정보

Exchange 전자 메일과 달리, Skype 위치의 상태는 간단히 설정으로 전환하여 모든 사용자를 자동으로 포함할 수 없습니다. 그렇지만 해당 위치를 켜면 해당 대화를 보존하려는 사용자를 수동으로 선택할 수 있습니다.

![보존 정책을 위한 Skype 위치 선택](../media/skype-location-retention-policies.png)
  
**사용자 선택**을 선택하면 **모두 선택** 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다. 그러나 각 사용자가 정책의 특정 포함사항으로 간주된다는 점을 이해해야 합니다. 따라서 **모두 선택** 상자를 선택하여 1,000명의 사용자를 포함하는 경우, 포함할 1,000명의 사용자를 수동으로 선택한 것과 같으며 이는 비즈니스용 Skype에 대해 지원되는 최대를 선택하는 것과 같습니다.

Outlook 폴더인 **대화 내용**은 Skype 아카이빙은 관계가 없는 기능입니다. **대화 내용**은 최종 사용자가 끌 수 있지만, Skype 아카이빙은 사용자는 액세스할 수 없고 eDiscovery에서만 액세스 가능한 숨김 폴더에 Skype 대화 사본을 저장하는 기능입니다.

## <a name="settings-for-retaining-and-deleting-content"></a>콘텐츠를 보존 및 삭제하기 위한 설정

보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.

- 보존 전용
    
    이 구성에서는 **특정 기간에 대한 항목을 보존**을 선택하고 **보존 기간의 종료 시, 아무 작업도 수행하지 않습니다**. 또는 **항목을 영구적으로 보존**을 선택합니다.

- 보존 후 삭제
    
    이 구성에서는 **특정 기간에 대한 항목을 보존**을 선택하고 **보존 기간의 종료 시, 항목을 자동으로 삭제합니다**.

- 삭제 전용
    
    이 구성에서는 **특정 기간에 도달했을 때만 항목 삭제**를 선택합니다.

### <a name="retaining-content-for-a-specific-period-of-time"></a>특정 기간 동안 콘텐츠 보존

보존 정책을 구성하면 항목을 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다. 또는 항목이 영구적으로 보존됩니다.

보존 정책을 구성하면 콘텐츠를 영구적으로 또는 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다. 콘텐츠 보존 기간은 보존 정책이 적용된 시점이 아닌 콘텐츠 생성 시점을 기준으로 계산됩니다. 

보존 기간이 시작되는 경우 또한 콘텐츠를 언제 만들어졌을지 또는 콘텐츠가 마지막으로 수정된 경우에는 파일 및 SharePoint, OneDrive 및 Office 365 위치에 대해서만 지원되었는지의 경우를 선택할 수도 있습니다.

예제:
  
- SharePoint: 콘텐츠가 마지막으로 수정된 후 7년 동안 사이트 모음에 항목을 유지하고 해당 사이트 모음에 있는 문서가 6년 내에 수정되지 않은 경우, 문서가 수정되지 않으면 다른 한 해에만 보존됩니다. 문서를 다시 편집하면 문서 사용 기간은 마지막으로 수정한 날부터 계산되고 앞으로 7년 동안 더 보존됩니다.
  
- Exchange: 사서함의 항목을 7년 동안 보존하려고 하고 메시지가 6년 전에 발송되었다면, 메시지는 1년 동안만 더 보존됩니다. Exchange 항목의 경우 해당 기간은 받는 전자 메일의 받은 날짜 또는 보내는 전자 메일에 대해 보낸 날짜를 기준으로 합니다. 항목을 최종 수정된 시점을 기준으로 보존하는 것은 OneDrive 및 SharePoint의 사이트 콘텐츠에만 해당됩니다.
  
보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.
  
![보존 설정 페이지](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>특정 사용 기간보다 오래된 콘텐츠 삭제

보존 정책은 항목을 보존했다가 삭제하거나, 혹은 보존하지 않고 오래된 콘텐츠를 삭제할 수 있습니다.
  
두 경우 모두, 보존 정책이 항목을 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.

따라서 처음으로 사이트에 보존 정책을 할당하기 전에 그리고 특히 정책이 항목을 삭제할 시, 먼저 기존 콘텐츠의 사용 기간과 정책이 기존 콘텐츠에 어떤 영향을 줄 수 있는지 고려해야 합니다. 또한 새 정책을 할당하기 전에 사이트 소유자에게 미리 알려, 가능한 영향을 평가할 시간을 줄 수도 있습니다.

### <a name="a-policy-that-applies-to-entire-locations"></a>전체 위치에 적용되는 정책

위치를 선택하는 경우 비즈니스용 Skype를 제외하고, 위치의 상태가 **On**인 경우, 기본 설정은 **모두**가 됩니다.
  
보존 정책이 전체의 위치 조합에 적용되는 경우 정책에 포함할 수 있는 수혜자, 사이트, 계정, 그룹 등에 제한이 없습니다. 

예를 들어, 정책에 모든 Exchange 전자 메일과 모든 SharePoint 사이트가 모두 포함된다면, 개수와 상관없이 모든 사이트와 수혜자가 포함될 것입니다. 또한 Exchange의 경우 정책이 적용된 후 만들어진 모든 새 사서함은 자동으로 정책을 상속합니다.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>특정 포함 또는 제외가 적용된 정책

특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 보존 정책을 적용할 수도 있습니다. 이는 해당 위치의 **상태**를 **켠**후 다음 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다. 
  
그러나 이 구성을 사용하는 경우 보존 정책에는 다음과 같은 1000개의 특정 개체를 포함하거나 제외하는 몇 가지 제한이 있습니다.
  
- 보존 정책의 최대 수:
    - 1,000개의 사서함
    - 1,000개의 Microsoft 365 그룹
    - Teams 비공개 채팅에 참여하는 1,000명의 사용자
    - 100개의 사이트(OneDrive 또는 SharePoint)

테넌트에 대해 지원되는 최대 정책 수는 10,000입니다. 이러한 항목에는 보존 정책, 보존 레이블 정책, 자동 적용 보존 정책이 포함됩니다.

보존 정책에 이러한 제한이 적용되는 경우 전체 위치에 적용되는 구성 옵션을 선택하세요.

> [!WARNING]
> 마지막 구성을 포함했다가 제거하면 해당 위치에 대해 **모두**로 되돌아갑니다.  정책을 저장하기 전에 원하는 구성인지 확인합니다.
> 
> 예를 들어 데이터를 삭제하도록 구성된 보존 정책에 포함할 SharePoint 사이트 하나를 지정한 다음 단일 사이트를 제거하면 기본적으로 모든 SharePoint 사이트는 데이터를 영구적으로 삭제하는 보존 정책의 적용을 받습니다. Exchange 수신인, OneDrive 계정, 팀 채팅 사용자 등의 경우에도 마찬가지입니다.
> 
> 이 시나리오에서 위치에 대한 **모두** 설정을 보존 정책의 적용을 받지 않으려면 위치를 해제합니다. 또는 정책에서 제외할 제외 항목을 지정합니다.

## <a name="updating-retention-policies"></a>보존 정책 업데이트

보존 정책을 편집하고 항목이 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 항목 외에 이 항목에도 자동으로 적용됩니다.

일반적으로 이 업데이트는 아주 간단하지만 며칠이 걸릴 수 있습니다. Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 준수 센터의 보존 정책 상태가 **켜기(보류)** 에서 **켜기(성공)** 으로 변경됩니다.

## <a name="lock-a-retention-policy-by-using-powershell"></a>PowerShell을 사용하여 보존 정책 잠금

규정 요구 사항을 준수하기 위해 [보존 잠금](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)을 사용해야 하는 경우 PowerShell을 사용해야 합니다. 유지 잠금이 적용된 후에는 관리자가 보존 정책을 사용하지 않도록 설정하거나 삭제할 수 없기 때문에, 이 기능을 사용하도록 설정하는 것은 잘못된 구성으로부터 보호하는 UI에서 사용할 수 없습니다.

모든 구성 지원 보존 잠금이 있는 모든 보존 정책. 그러나 뒤에 나오는 PowerShell 명령을 사용하는 경우 **작업부하** 매개변수에는 정책에 구성된 실제 작업 부하를 반영하는 것이 아니라 **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup**을 표시하는 것을 볼 수 있습니다. 이는 표시 문제일 뿐입니다.

1. [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다.

2. [RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy)를 실행하여 잠글 정책의 이름을 나열하고 보존 정책을 확인합니다. 예를 들어,
    
   ![PowerShell의 보존 정책 목록](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. 보존 정책에 보존 잠금을 설정하려면 [Set-RetentionCompliancePolicy]( ) cmdlet을 보존 정책 이름으로 실행하고 *RestrictiveRetention* 매개변수를 true로 설정합니다.
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    예를 들어,
    
    ![PowerShell의 RestrictiveRetention 매개 변수](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     메시지가 표시되면 이 구성과 함께 제공되는 제한 사항을 읽고 **Y**를 입력하여 승인합니다.
    
   ![PowerShell에서 보존 정책 잠금을 원하는지 확인하는 메시지](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

이제 보존 정책에 보존 잠금이 적용됩니다. 확인하려면 `Get-RetentionCompliancePolicy` 다시 실행 하지만, 보존 정책 이름을 지정하고 정책 매개변수를 표시합니다.

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

**RestrictiveRetention**이 **True**로 설정되어 있는지 확인해야 합니다. 예를 들어,

![PowerShell에 모든 매개 변수와 함께 표시된 잠긴 정책](../media/retention-policy-preservation-lock-locked-policy.PNG)
  


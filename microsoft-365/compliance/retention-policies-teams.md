---
title: Teams의 보존 정책에 대해 알아보기
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
description: Microsoft Teams에 적용되는 보존 정책에 대해 자세히 알아보기
ms.openlocfilehash: 869f457ddb64e5d828dcb5f1244ba779f889e8c9
ms.sourcegitcommit: e3900c818877c2cdcd227917ec975c03e828c7ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861165"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a>Microsoft Teams의 보존 정책에 대해 자세히 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

이 문서의 정보는 Microsoft Teams와 관련된 정보를 포함하므로 [보존 정책에 대해 자세히 알아보기](retention-policies.md)를 보완합니다.

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a>보존 정책이 Microsoft Teams에 작동하는 방식

보존 정책을 사용하여 Teams에서 채팅 및 채널 메시지를 보존할 수 있습니다. Teams 채팅은 채팅에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, Teams 채널 메시지는 Teams의 그룹 사서함에 있는 유사한 숨겨진 폴더에 저장됩니다. 

Teams에서 역시 이 데이터를 저장하는 Azure 기반 채팅 서비스를 사용하고, 기본적으로 이 서비스에서는 데이터를 무제한적으로 저장한다는 사실을 이해하는 것이 중요합니다. 이러한 이유로 Teams 위치를 사용하여 Teams 데이터를 보존 및 삭제하는 것이 좋습니다. Teams 위치를 사용하면 Exchange 사서함 및 기본 Azure 기반 채팅 서비스 모두에서 데이터가 영구적으로 삭제됩니다. 자세한 내용은 [Microsoft Teams의 보안 및 규정 준수](https://go.microsoft.com/fwlink/?linkid=871258) 및 특히 [정보 보호 아키텍처](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) 섹션을 참조하세요.

Teams 채팅 및 채널 메시지는 사용자 또는 그룹 사서함에 대해 구성된 보존 정책의 영향을받지 않습니다. Teams 채팅 및 채널 메시지가 Exchange에 저장되어 있어도이 Teams 데이터는 **Teams 채널 메시지** 및 **Teams 채팅** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.

> [!NOTE]
> Teams 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Teams 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)로 변환됩니다. 사용자에 대한 이 Teams 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.

채팅 및 채널 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존 또는 삭제만 가능한지 여부에 따라 달라집니다.

보존 정책이 보존 및 삭제되는 경우:

![Teams 채팅 및 채널 메시지의 보존 흐름 다이어그램](../media/TeamsRetentionLifecycle.png)

1. 보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 수정하거나 삭제하는 경우**, 메시지는 SubstrateHolds 폴더(모든 폴더에서 숨겨진 폴더)로 이동(또는 편집시 복사)됩니다. 보존 기간이 만료 될 때까지 이 폴더에 저장됩니다. 메시지는 보존 기간이 만료되는 날에 영구적으로 삭제됩니다.

2. 보존 기간 동안 **채팅 또는 채널 메시지가 삭제되지 않는 경우** 보존 기간이 만료되면 메시지는 1일 이내에 SubstrateHolds 폴더로 이동 합니다(0에서 24시간까지 소요). 메시지는 SubstrateHolds 폴더로 이동한 후 1일 후에 영구적으로 삭제 됩니다. 

> [!NOTE]
> SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다. 영구적으로 삭제된 메시지는 eDiscovery 검색에서 반환되지 않습니다.

보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.

### <a name="content-paths-for-retain-only-retention-policy"></a>보유 전용 보존 정책의 컨텐츠 경로

1. 보존 기간 동안 **채팅 또는 채널 메시지가 수정되거나 삭제된 경우**: SubstrateHolds 폴더의 복사본이 항목이 만료된 후 하루 후에 영구적으로 삭제되면 원본 메시지의 복사본이 SubstrateHolds 폴더에 생성되고 보존 기간이 끝날 때까지 보존됩니다. 

2. 보존 기간 동안 **항목이 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 메시지는 원래 위치에 남아 있습니다.

#### <a name="content-paths-for-delete-only-retention-policy"></a>삭제 전용 보존 정책의 컨텐츠 경로

1. 보존 기간 동안 **메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다. 

2. 해당 기간 동안 **항목이 사용자에 의해 삭제되면** 항목은 즉시 SubstrateHolds 폴더로 이동합니다. 사용자가 메시지를 삭제하거나 SubstrateHolds 폴더를 비우면 항목이 영구적으로 삭제됩니다. 그렇지 않으면 SubstrateHolds 폴더에 들어간 후 하루가 지나면 메시지가 영구적으로 삭제됩니다.


## <a name="skype-for-business-and-teams-interop-chats"></a>비즈니스용 Skype 및 팀 상호 운용 채팅

비즈니스용 Skype 및 Teams interop 채팅에도 동일한 흐름이 적용됩니다. 비즈니스용 Skype 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다. Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 삭제합니다. 

그러나 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트 쪽에서 대화 기록을 사용하도록 설정한 경우 기록이 사서함에 저장되는 경우 해당 Teams의 보존 정책이 해당 채팅 데이터를 처리하지 않습니다.

## <a name="files-in-teams"></a>Teams의 파일

Teams의 채팅에서 공유되는 파일은 파일을 공유하는 사용자의 OneDrive 계정에 저장됩니다. 채널에 업로드된 파일은 해당 팀의 SharePoint 사이트에 저장됩니다. 즉, Teams에서 파일을 유지하거나 삭제하려면 Teams에 대해 구성한 보존 정책 외에도 OneDrive 계정 및 SharePoint에 적용되는 하나 이상의 보존 정책을 구성해야 합니다. 이러한 위치에서 보존 정책이 작동하는 방법에 대한 자세한 내용은 [SharePoint 및 OneDrive의 보존 정책에 대해 알아보기](retention-policies-sharepoint.md)를 참조하세요.

> [!NOTE]
> Teams 채널 메시지 또는 Teams 채팅을 포함하는 보존 정책에는 Teams 위치만 포함될 수 있습니다. 따라서 Teams에서 이러한 파일을 유지하거나 삭제하려면 별도의 보존 정책을 만들어야합니다.
> 
> 특정 팀의 파일에 보존 정책을 적용하려면 해당 팀의 SharePoint 사이트 및 해당 팀 사용자의 OneDrive 계정을 선택할 수 있습니다.

SharePoint 또는 OneDrive에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다. 이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만, 사용자가 파일을 클릭하면 "파일을 찾을 수 없음" 오류가 발생합니다. 이 동작은 보존 정책에만 국한된 것이 아니며 사용자가 SharePoint 또는 OneDrive에서 파일을 수동으로 삭제하는 경우에도 발생할 수 있습니다.

## <a name="meetings-and-external-users"></a>모임 및 외부 사용자

채널 모임 메시지는 채널 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채널 메시지** 위치를 선택하세요.

즉석 모임 메시지는 그룹 채팅 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채팅** 위치를 선택하세요.

조직에서 호스팅하는 모임에 외부 사용자가 포함된 경우:

- 외부 사용자가 테넌트에서 게스트 계정을 사용하여 참여하는 경우 이 사용자에게는 조직의 Teams 보존 정책을 적용할 수 있는 섀도 사서함이 있습니다. 모임의 모든 메시지는 사용자의 사서함과 섀도 사서함에 모두 저장됩니다. 

- 외부 사용자가 다른 Microsoft 365 조직의 계정을 사용하여 참여하는 경우 보존 정책은 이 사용자의 메시지가 다른 테넌트의 해당 사용자의 사서함에 저장되어 있기 때문에 해당 사용자의 메시지를 삭제할 수 없습니다. 그러나 동일한 모임의 경우 보존 정책이 사용자의 메시지를 삭제할 수 있습니다.


## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 

사용자가 조직을 떠나 Office 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 채팅 메시지는 비활성 사서함에 저장됩니다. 채팅 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다. 자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요. 

사용자가 Teams에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.

## <a name="limitations"></a>제한 사항

Microsoft는 Teams에서 보존 기능을 최적화하기 위해 지속적으로 노력하고 있습니다. 그동안에는 다음과 같은 몇 가지 제한 사항을 알고 있어야 합니다.
  
- **Teams에는 별도의 보존 정책이 필요합니다**. 보존 정책을 만들고 Teams 위치를 켜면 다른 모든 위치는 꺼집니다. Teams를 포함하는 보존 정책은 Teams만 포함할 수 있고 다른 위치는 포함할 수 없습니다. 
    
- **Teams는 조직 전체 정책에 포함되지 않습니다**. Teams에는 별도 보존 정책 필요하므로 조직 전체 정책을 만들어도 여기에 포함되지 않습니다. 
    
- **Teams는 고급 보존을 지원하지 않습니다**. 보존 정책을 만들 때 [특정 조건을 만족하는 콘텐츠를 식별하기 위해 고급 설정](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)을 선택하면 Teams 위치를 사용할 수 없습니다. 현재 Teams에서 보존은 해당 위치를 선택할 때 모든 채팅 및 채널 메시지 내용에 적용됩니다. 

- **개인 채널의 Teams 메시지는 Teams 채널 메시지에 대한 보존 정책을 구성할 때 포함되지 않습니다**. 대신 개인 채널의 메시지는 **Teams 채팅** 옵션을 사용하여 그룹 채팅으로 사용자에게 포함됩니다. 
    
- **Teams에서 만료된 메시지를 정리하는 데 최대 3 일이 걸릴 수 있습니다**. Teams에 적용되는 보존 정책은 보존 기간이 만료되면 채팅 및 채널 메시지를 삭제합니다. 그러나 이 메시지를 정리하고 영구적으로 삭제하는 데 최대 3일이 걸릴 수 있습니다. 또한 보존 기간이 만료된 후 및 메시지가 영구적으로 삭제된 경우 eDiscovery 도구를 사용하여 채팅 및 채널 메시지를 검색할 수 있습니다.
    
   > [!NOTE]
   > 전에는 보존 정책으로 30일이 지나지 않은 Teams 콘텐츠를 삭제할 수 없었지만 이 제한을 제거했습니다. 이제 Teams 콘텐츠의 보존 기간은 원하는 일수이며 단 하루에 그칠 수도 있습니다. 보존 기간이 하루인 경우 보존 기간이 만료 된 후 메시지가 영구적으로 삭제되기까지 최대 3일이 소요됩니다.

- **Outlook에서 잘못된 표시 문제가 발생했습니다**. Skype 또는 Teams 위치에 대한 보존 정책을 만드는 경우 사용자가 Outlook 데스크톱 클라이언트에서 사서함 폴더의 속성을 볼 때 해당 정책 중 하나가 기본 폴더 정책으로 표시됩니다. 이것은 Outlook의 잘못된 표시 문제이며 [알려진 문제](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)입니다. 기본 폴더 정책으로 표시되어야 하는 것은 폴더에 적용되는 사서함 보존 정책입니다. Skype 또는 Teams 보존 정책은 사용자의 사서함에 적용되지 않습니다.

- **구성 문제** 
    - **Teams 채널 메시지 위치**에 **팀 선택**을 선택하면 Teams가 아닌 Office 365 그룹이 표시될 수 있습니다. 이 그룹을 선택하지 마세요.
    
    - **Teams 채팅** 위치에 대해 **사용자 선택**을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다. 보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.

## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a>Microsoft Teams에 보존 정책을 구성하는 방법

[보존 정책 만들기](create-retention-policies.md) 및 구성 지침에 따라 마법사의 **위치 선택** 페이지에서 다음 옵션을 선택합니다.

- **** > **Teams 채널 메시지** 및 **Teams 채팅**에서 특정 위치를 선택할 수 있습니다.

Teams에 적용되는 보존 정책은 보존 이유로 필요할 수 있는 [보존 잠금](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)을 사용할 수 있습니다.

## <a name="related-information"></a>관련 정보

[Microsoft Teams의 보존 정책](https://docs.microsoft.com/microsoftteams/retention-policies)

---
title: Teams의 보존에 대해 알아보기
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
ms.openlocfilehash: ec5085b2d0a828300cb90fb260cb293eda4b9433
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988184"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Microsoft Teams의 보존에 대해 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

이 문서의 정보는 Microsoft Teams 메시지와 관련된 정보를 포함하므로 [보존에 대해 알아보기](retention.md)를 보완합니다.

다른 워크로드는 다음을 참조하세요.

- [SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기](retention-policies-sharepoint.md)
- [Yammer의 보존에 대한 자세한 정보](retention-policies-yammer.md)
- [Exchange의 보존에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>보존 및 삭제에 포함된 항목

Teams 보존 정책을 통해 다음의 Teams 항목(포함된 이미지, 표, 하이퍼텍스트 링크, 다른 Teams 메시지, 파일, [카드 콘텐츠](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)에 연결된 링크를 포함한 채팅 및 채널 메시지)을 보존하고 삭제할 수 있습니다. 채팅 메시지에는 채팅에 속한 모든 사람의 이름이 포함되어 있고, 채널 메시지에는 팀 이름과 메시지 제목이 포함되어 있습니다(제공되는 경우). 

> [!NOTE]
> 카드 콘텐츠 포함은 최근에 추가된 사항이며 현재 테넌트에 배포되고 있습니다. 자세한 내용은 [이제 Teams의 응용 프로그램을 통한 적응형 카드 콘텐츠에 대한 Microsoft 365 규정 준수 기능 제공](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)을 참조하세요.

비공개 채널의 Teams 메시지는 포함되지 않으며 이모티콘 형태의 상대방의 반응도 포함되지 않습니다.

Teams에서 사용하는 전자 메일 및 파일은 Teams의 보존 정책에 포함되지 않습니다. 이러한 항목은 자체 보존 정책이 있습니다.

## <a name="how-retention-works-with-microsoft-teams"></a>보존이 Microsoft Teams에 작동하는 방식

보존 정책을 사용하여 Teams의 채팅 및 채널 메시지를 유지할 수 있습니다. Teams 채팅의 테이터는 채팅에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, Teams 채널 메시지의 데이터는 팀의 그룹 사서함에 있는 유사한 숨겨진 폴더에 저장됩니다.

Teams에서 역시 이 데이터를 저장하는 Azure 기반 채팅 서비스를 사용하고, 기본적으로 이 서비스에서는 데이터를 무제한적으로 저장한다는 사실을 이해하는 것이 중요합니다. 이러한 이유로 Teams 위치를 사용하여 Teams 데이터를 보존 및 삭제하는 보존 정책을 만드는 것이 좋습니다. 이 보존 정책은 Exchange 사서함 및 기본 Azure 기반 채팅 서비스 모두에서 이 데이터를 영구적으로 삭제할 수 있습니다. 자세한 내용은 [Microsoft Teams의 보안 및 규정 준수](https://go.microsoft.com/fwlink/?linkid=871258) 및 특히 [정보 보호 아키텍처](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) 섹션을 참조하세요.

Teams 채팅 및 채널 메시지는 사용자 또는 그룹 사서함에 대해 구성된 보존 정책의 영향을받지 않습니다. Teams 채팅 및 채널 메시지가 Exchange에 저장되어 있어도이 Teams 데이터는 **Teams 채널 메시지** 및 **Teams 채팅** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.

> [!NOTE]
> Teams 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Teams 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)로 변환됩니다. 사용자에 대한 이 Teams 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.

채팅 및 채널 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Teams 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다. 타이머 작업의 실행은 7일까지 걸립니다. 이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 또 다른 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.

채팅 및 채널 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.

보존 정책이 보존 및 삭제하는 경우:

![Teams 채팅 및 채널 메시지의 보존 흐름 다이어그램](../media/teamsretentionlifecycle.png)

다이어그램의 두 경로:

1. 보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 21일 내에 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다. 이 메시지는 보존 기간이 만료 될 때까지 저장된 다음 24 시간 내에 영구적으로 삭제됩니다.

2. **채팅 또는 채널 메시지가 삭제되지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동합니다. 이 작업은 만료 날짜로부터 최대 7일이 걸립니다. 메시지가 SubstrateHolds 폴더에 있으면 24시간 내에 영구적으로 삭제됩니다. 

> [!NOTE]
> SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다. SubstrateHolds 폴더에서 메시지가 영구적으로 삭제될 때까지 메시지는 eDiscovery 도구로 검색 가능한 상태로 유지됩니다.

보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.

### <a name="content-paths-for-retain-only-retention-policy"></a>보유 전용 보존 정책의 컨텐츠 경로

1. **채팅 또는 채널 메시지를 편집하거나 삭제하는 경우**, 원본 메시지의 복사본은 21일 내에 SubstrateHolds 폴더에 만들어지고 보존 기간이 만료될 때까지 보존됩니다. 그런 다음 24시간 이내에 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.

2. **항목이 수정되거나 삭제되지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.

### <a name="content-paths-for-delete-only-retention-policy"></a>삭제 전용 보존 정책의 컨텐츠 경로

1. 보존 기간 동안 **메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다. 이 작업은 만료 날짜로부터 최대 7일이 걸립니다. 그런 다음 24시간 이내에 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.

2. 해당 기간 동안 **사용자가 해당 항목을 삭제하는 경우** 항목은 21일 이내에 24시간 안에 영구적으로 삭제되는 SubstrateHolds 폴더로 이동됩니다.


## <a name="skype-for-business-and-teams-interop-chats"></a>비즈니스용 Skype 및 팀 상호 운용 채팅

비즈니스용 Skype 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다. Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 적용합니다. 

그러나 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트 쪽에서 대화 기록을 사용하도록 설정한 경우 기록이 사서함에 저장되는 경우 해당 Teams의 보존 정책이 해당 채팅 데이터를 처리하지 않습니다. 이 콘텐츠의 경우 비즈니스용 Skype에 대해 구성된 보존 정책을 사용합니다.

## <a name="meetings-and-external-users"></a>모임 및 외부 사용자

채널 모임 메시지는 채널 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채널 메시지** 위치를 선택하세요.

즉석 모임 메시지는 그룹 채팅 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채팅** 위치를 선택하세요.

조직에서 호스팅하는 모임에 외부 사용자가 포함된 경우:

- 외부 사용자가 테넌트에서 게스트 계정을 사용하여 참여하는 경우 이 사용자에게는 조직의 Teams 보존 정책을 적용할 수 있는 섀도 사서함이 있습니다. 모임의 모든 메시지는 사용자의 사서함과 섀도 사서함에 모두 저장됩니다. 

- 외부 사용자가 다른 Microsoft 365 조직의 계정을 사용하여 참여하는 경우 보존 정책은 이 사용자의 메시지가 다른 테넌트의 해당 사용자의 사서함에 저장되어 있기 때문에 해당 사용자의 메시지를 삭제할 수 없습니다. 그러나 동일한 모임의 경우 보존 정책이 사용자의 메시지를 삭제할 수 있습니다.

## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 

Exchange Online에 사서함이 있는 사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 채팅 메시지는 비활성 사서함에 저장됩니다. 채팅 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다. 자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요. 

사용자가 Teams에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.

## <a name="limitations"></a>제한 사항

Microsoft는 Teams에서 보존 기능을 최적화하기 위해 지속적으로 노력하고 있습니다. 그 동안 Teams 채널 메시지와 채팅에 대한 보존을 사용할 때는 다음 몇 가지 제한 사항에 유의해야 합니다.

- **Outlook에서 잘못된 표시 문제가 발생했습니다**. Skype 또는 Teams 위치에 대한 보존 정책을 만드는 경우 사용자가 Outlook 데스크톱 클라이언트에서 사서함 폴더의 속성을 볼 때 해당 정책 중 하나가 기본 폴더 정책으로 표시됩니다. 이것은 Outlook의 잘못된 표시 문제이며 [알려진 문제](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)입니다. 기본 폴더 정책으로 표시되어야 하는 것은 폴더에 적용되는 사서함 보존 정책입니다. Skype 또는 Teams 보존 정책은 사용자의 사서함에 적용되지 않습니다.

- **구성 문제** 
    - **Teams 채널 메시지** 위치에 **팀 선택** 을 선택하면 팀이 아닌 Microsoft 365 그룹이 표시될 수 있습니다. 이 그룹을 선택하지 마세요.
    
    - **Teams 채팅** 위치에 대해 **사용자 선택** 을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다. 보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.

## <a name="configuration-guidance"></a>구성 지침

Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.

Teams에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.

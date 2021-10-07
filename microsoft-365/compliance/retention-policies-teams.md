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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft Teams에 적용되는 보존 정책에 대해 자세히 알아보기
ms.openlocfilehash: f14e729858f3285f9cefc4d3db7da99d6c6f9e7d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189324"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Microsoft Teams의 보존에 대해 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

> [!NOTE]
> Teams에서 보존 규정에 따라 채팅이나 메시지가 삭제되었다는 메시지를 본 적이 있다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 확인하세요.
> 
> 이 페이지는 해당 보존 정책을 관리하는 IT 관리자를 위한 정보를 담고 있습니다.

이 문서의 정보는 Microsoft Teams 메시지와 관련된 정보를 포함하므로 [보존에 대해 알아보기](retention.md)를 보완합니다.

다른 워크로드는 다음을 참조하세요.

- [SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기](retention-policies-sharepoint.md)
- [Yammer의 보존에 대한 자세한 정보](retention-policies-yammer.md)
- [Exchange의 보존에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>보존 및 삭제에 포함된 항목

Teams 채팅 메시지, 채널 메시지 및 비공개 채널 메시지는 Teams 보존 정책을 사용하여 삭제될 수 있으며, 메시지의 텍스트 외에도 다음의 Teams 항목(포함된 이미지, 표, 하이퍼텍스트 링크, 다른 Teams 메시지 및 파일, [카드 콘텐츠](/microsoftteams/platform/task-modules-and-cards/what-are-cards)에 연결된 링크)을 규정 준수를 위해 보존할 수 있습니다. 채팅 메시지와 비공개 채널 메시지에는 대화에 속한 모든 사람의 이름이 포함되어 있고, 채널 메시지에는 팀 이름과 메시지 제목이 포함되어 있습니다(제공되는 경우). 

Teams에 대한 보존 정책을 사용할 때 코드 조각, Teams 모바일 클라이언트에서 녹음된 목소리 메모, 미리 보기, 알림 이미지, 이모티콘 형태로 표현된 다른 사용자의 응답은 보존되지 않습니다.

Teams에서 사용하는 전자 메일 및 파일은 Teams의 보존 정책에 포함되지 않습니다. 이 항목에는 자체 보존 정책이 있습니다.

## <a name="how-retention-works-with-microsoft-teams"></a>보존이 Microsoft Teams에서 작동하는 방식

이 섹션에서는 백엔드 스토리지 및 프로세스를 통해 규정 준수 요구 사항이 충족되는 방법과 현재 Teams 앱에 표시되는 메시지가 아니라 eDiscovery 도구를 통해 확인해야 하는 방법에 대해 설명합니다.

보존 정책을 사용하여 Teams의 채팅 및 채널 메시지를 보존하고, 해당 채팅 및 메시지를 삭제할 수 있습니다. Exchange 사서함은 이러한 메시지에서 복사된 데이터를 저장하는 데 사용됩니다. Teams 채팅의 테이터는 채팅에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, 팀의 그룹 사서함에 있는 유사한 숨겨진 폴더는 Teams 채널 메시지에 사용됩니다. 이러한 숨겨진 폴더는 사용자 또는 관리자가 직접 액세스할 수 있도록 설계되지 않지만 규정 준수 관리자가 eDiscovery 도구를 사용하여 검색할 수 있는 데이터를 저장합니다.

이러한 사서함은 RecipientTypeDetails 특성에 따라 나열됩니다.

- **UserMailbox**: 이러한 사서함은 클라우드 기반 Teams 사용자를 위한 메시지 데이터를 저장합니다.
- **MailUser**: 이러한 사서함은 [온-프레미스 Teams 사용자](search-cloud-based-mailboxes-for-on-premises-users.md)를 위한 메시지 데이터를 저장합니다.
- **GroupMailbox**: 이러한 사서함은 Teams 표준 채널의 메시지 데이터를 저장합니다.

Teams 회의실에 사용되는 RoomMailbox와 같은 다른 사서함 유형은 Teams 보존 정책에 대해 지원되지 않습니다.

Teams는 모든 메시지(채팅 및 채널 메시지)에 대해 Azure 제공 채팅 서비스를 기본 저장소로 사용합니다. Teams 메시지를 삭제해야 하는 경우, 메시지가 만들어진 시기에 따라 특정 기간 후에 메시지를 삭제할 수 있는 Teams용 보존 정책을 사용합니다. 그런 다음 메시지는 규정 준수 작업을 위해 저장된 Exchange 사서함 및 기본 Azure 기반 채팅 서비스에서 사용하는 기본 저장소에서 모두 영구적으로 삭제됩니다. 기본 아키텍처에 대한 자세한 내용은 [Microsoft Teams의 보안 및 규정 준수](/MicrosoftTeams/security-compliance-overview), 특히 [정보 보호 아키텍처](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) 섹션을 참조하세요.

Teams 채팅 및 채널 메시지의 이 데이터가 사서함에 저장되어 있는 경우, **Teams 채널 메시지** 및 **Teams 채팅** 에 대한 보존 정책을 구성해야 합니다. Teams 채팅 및 채널 메시지는 Exchange 사용자 또는 그룹 사서함에 대해 구성된 보존 정책에 포함되지 않습니다.

> [!NOTE]
> Teams 메시지를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 이 정책에 포함된 사용자의 사서함을 삭제하면, 사서함이 Teams 데이터를 보존하기 위해 [비활성 사서함](inactive-mailboxes-in-office-365.md)으로 변환됩니다. 사용자에 대한 이 Teams 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.

채팅 및 채널 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Teams 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다. 일반적으로 타이머 작업을 실행하는 데 1~7일이 소요됩니다. 이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 또 다른 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다. 

메시지는 SubstrateHolds 폴더에 최소 1일 동안 남아 있으며 삭제할 수있는 경우, 타이머 작업은 다음에 실행할 때 해당 메시지를 영구적으로 삭제합니다.

> [!NOTE]
> [첫 번째 보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence) 때문에 다른 보존 정책으로 인해 동일한 항목을 유지해야 하거나 법적 또는 조사상의 이유로 eDiscovery 보류 상태에 있는 경우, 영구 삭제는 항상 일시 중단됩니다.

채팅 및 채널 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.

보존 정책이 보존 및 삭제하는 경우:

![Teams 채팅 및 채널 메시지의 보존 흐름 다이어그램](../media/teamsretentionlifecycle.png)

다이어그램의 두 경로:

1. 보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다. 메시지는 최소 1일 동안 저장됩니다. 보존 기간이 만료되면 메시지가 다음에 실행될 때(일반적으로 1~7일) 영구적으로 삭제됩니다.

2. **사용자가 채팅 또는 채널 메시지를 삭제하지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동됩니다. 이 작업은 일반적으로 만료 날짜로부터 1~7일 사이에 수행됩니다. 메시지가 SubstrateHolds 폴더에 있으면 최소 1일 동안 여기에 저장되고 다음에 타이머 작업이 실행될 때 메시지가 영구적으로 삭제됩니다(일반적으로 1-7일 사이). 

> [!NOTE]
> 숨겨진 폴더를 포함하여 사서함에 저장된 메시지는 eDiscovery 도구로 검색할 수 있습니다. SubstrateHolds 폴더에서 메시지가 영구적으로 삭제될 때까지 메시지는 eDiscovery 도구로 검색 가능한 상태로 유지됩니다.

메시지가 SubstrateHolds 폴더에서 영구적으로 삭제되면 삭제 작업이 백엔드 Azure 채팅 서비스에 전달된 다음 동일한 작업을 Teams 클라이언트 앱에 릴레이합니다. 이 통신 또는 캐싱의 지연은 짧은 시간 동안 사용자가 Teams 앱에서 이러한 메시지를 계속 볼 수 있지만 이러한 메시지의 데이터가 eDiscovery 검색에서 반환되지 않는 이유를 설명할 수 있습니다. Teams 앱에 표시되는 메시지는 규정 준수 요구 사항을 위해 보존되었는지 또는 영구적으로 삭제되었는지를 정확하게 반영하지 않습니다.

보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.

### <a name="content-paths-for-retain-only-retention-policy"></a>보유 전용 보존 정책의 컨텐츠 경로

1. 보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동되며 최소 1일 이상 해당 폴더에 보존됩니다. 보존 정책이 영구 보존되도록 구성된 경우 항목은 그대로 유지됩니다. 보존 정책에 보존 기간의 종료 날짜가 있고 보존 기간이 만료되면 메시지가 다음에 실행될 때(일반적으로 1~7일) 영구적으로 삭제됩니다.

2. **사용자가 채팅 또는 채널 메시지를 수정 또는 삭제하지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.

### <a name="content-paths-for-delete-only-retention-policy"></a>삭제 전용 보존 정책에 대한 콘텐츠 경로

1. 보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 편집하거나 삭제** 하는 경우에는, 원본 메시지가 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다. 메시지는 최소 1일 동안 해당 폴더에 보존되고 다음에 타이머 작업이 실행될 때 영구적으로 삭제됩니다(일반적으로 1-7일 사이).

2. 보존 기간 동안 사용자가 **채팅 또는 채널 메시지를 삭제하지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다. 이 작업은 일반적으로 만료 날짜로부터 1~7일 사이에 수행됩니다. 메시지는 최소 1일 동안 해당 폴더에 보존되고 다음에 타이머 작업이 실행될 때 영구적으로 삭제됩니다(일반적으로 1-7일 사이).

#### <a name="example-flows-and-timings-for-retention-policies"></a>보존 정책의 흐름 및 타이밍 예

다음 예제를 사용하여 이전 섹션에서 설명한 프로세스 및 타이밍이 다음 구성을 가진 보존 정책에 어떻게 적용되는지 확인합니다.

- [예제 1: 7년 동안 보존만](#example-1-retain-only-for-7-years)
- [예제 2: 30일 동안 보존한 다음 삭제](#example-2-retain-for-30-days-and-then-delete)
- [예제 3: 1일 후에 ​​삭제만](#example-3-delete-only-after-1-day)

영구 삭제를 참조하는 모든 예제의 경우 [보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence)으로 인해 메시지가 항목을 보존하기 위한 다른 보존 정책의 적용을 받거나 eDiscovery 보존이 적용되는 경우 이 작업이 일시 중지됩니다.

##### <a name="example-1-retain-only-for-7-years"></a>예제 1: 7년 동안 보존만

1일 차에 사용자가 채팅 또는 채널 메시지를 작성합니다.

5일 차에 사용자가 해당 메시지를 편집합니다.

30일 차에 사용자가 현재 메시지를 삭제합니다.

보존 결과:

- 원본 메시지의 경우:
    - 5일 차에는 메시지가 SubstrateHolds 폴더에 복사되어 eDiscovery 도구를 사용하여 1일부터 최소 7년(보존 기간) 동안 계속 검색할 수 있습니다.

- 현재 (편집된) 메시지의 경우:
    - 30일 차에는 메시지가 SubstrateHolds 폴더에 이동되어 eDiscovery 도구를 사용하여 1일부터 최소 7년(보존 기간) 동안 계속 검색할 수 있습니다.

사용자가 보존 기간이 아닌 지정된 보존 기간 이후에 현재 메시지를 삭제 한 경우 메시지는 여전히 SubstrateHolds 폴더로 이동됩니다. 그러나 이제 보존 기간이 만료되었으므로 메시지는 최소 1일 후에 영구적으로 삭제되고 일반적으로 1~7일 이내에 삭제됩니다.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>예제 2: 30일 동안 보존한 다음 삭제

1일 차에 사용자가 채팅 또는 채널 메시지를 작성합니다.

10일 차에 사용자가 해당 메시지를 편집합니다.

사용자는 더 이상 편집하지 않고 메시지를 삭제하지 않습니다.

보존 결과:

- 원본 메시지의 경우:
    - 10 일에 메시지는 SubstrateHolds 폴더에 복사되며 eDiscovery 도구를 사용하여 검색 할 수 있습니다.
    - 보존 기간(1일부터 30일)이 끝나면 메시지는 일반적으로 최소 1일 후 1~ 7일 이내에 영구적으로 삭제된 다음 eDiscovery 검색과 함께 반환되지 않습니다.

- 현재 (편집된) 메시지의 경우:
    - 보존 기간(1일부터 30일)이 끝나면 메시지는 일반적으로 1~7일 이내에 SubstrateHolds 폴더로 이동하며 eDiscovery 도구를 사용하여 검색할 수 있습니다.
    - 그리고 나서 메시지는 일반적으로 최소 1일 후 1~ 7일 이내에 영구적으로 삭제된 다음 eDiscovery 검색과 함께 반환되지 않습니다.

##### <a name="example-3-delete-only-after-1-day"></a>예제 3: 1일 후에 ​​삭제만

> [!NOTE]
> 1-7 일의 기간 내에 작동하는 이 구성 및 보존 프로세스의 짧은 1일 기간으로 인해 이 섹션에서는 일반적인 시간 범위 내에 있는 예제 타이밍을 보여줍니다.

1일 차에 사용자가 채팅 또는 채널 메시지를 작성합니다.

사용자가 메시지를 편집하거나 삭제하지 않은 경우 보존 결과의 예:

- 5일(일반적으로 2일 보존 기간이 시작된 후 1~7일):
    - 메시지는 이 폴더로 이동하며 eDiscovery 도구로 검색할 수 있는 최소 1일 동안 이 폴더에 남아 있습니다.

- 9일(일반적으로 SubstrateHolds 폴더에서 최소 1일 이후부터 1~7일):
    - 메시지가 영구적으로 삭제된 후 eDiscovery 검색에서 반환되지 않습니다.

이 예제에서 볼 수 있는처럼, 하루만에 메시지를 삭제하도록 보존 정책을 구성할 수 있습니다. 그러나 이 서비스는 규정 준수 삭제를 보장하기 위해 여러 프로세스를 진행합니다. 결과적으로 1일 후 삭제 작업은 메시지가 영구적으로 삭제되기 까지 16일이 걸릴 수 있으므로 eDiscovery 검색에서 더 이상 반환되지 않습니다.

## <a name="skype-for-business-and-teams-interop-chats"></a>비즈니스용 Skype 및 팀 상호 운용 채팅

비즈니스용 Skype 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다. Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 적용합니다. 

그러나 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트 쪽에서 대화 기록을 사용하도록 설정한 경우 기록이 사서함에 저장되는 경우 해당 Teams의 보존 정책이 해당 채팅 데이터를 처리하지 않습니다. 이 콘텐츠의 경우 비즈니스용 Skype에 대해 구성된 보존 정책을 사용합니다.

## <a name="meetings-and-external-users"></a>모임 및 외부 사용자

채널 모임 메시지는 채널 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채널 메시지** 위치를 선택하세요.

즉석 모임 및 예약된 모임 메시지는 그룹 채팅 메시지와 같은 방식으로 저장되므로 이 데이터의 경우 보존 정책을 구성할 때 **Teams 채팅** 위치를 선택하세요.

조직에서 호스팅하는 모임에 외부 사용자가 포함된 경우:

- 외부 사용자가 테넌트에서 게스트 계정을 사용하여 참여하는 경우 이 사용자에게는 조직의 Teams 보존 정책을 적용할 수 있는 섀도 사서함이 있습니다. 모임의 모든 메시지는 사용자의 사서함과 섀도 사서함에 모두 저장됩니다. 

- 외부 사용자가 다른 Microsoft 365 조직의 계정을 사용하여 참여하는 경우 보존 정책은 이 사용자의 메시지가 다른 테넌트의 해당 사용자의 사서함에 저장되어 있기 때문에 해당 사용자의 메시지를 삭제할 수 없습니다. 그러나 동일한 모임의 경우 보존 정책이 사용자의 메시지를 삭제할 수 있습니다.

## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 

Exchange Online에 사서함이 있는 사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 채팅 메시지는 비활성 사서함에 저장됩니다. 채팅 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다. 자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요. 

사용자가 Teams에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.

## <a name="configuration-guidance"></a>구성 지침

Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.

Teams에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.
---
title: Yammer의 보존에 대한 자세한 정보
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
description: Yammer에 적용되는 보존 정책에 대해 자세히 알아보기
ms.openlocfilehash: 88e4081ba23ce38153af7eb5fe8af69a00df73b8
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667709"
---
# <a name="learn-about-retention-for-yammer"></a>Yammer의 보존에 대한 자세한 정보

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> 미리 보기에 이 기능이 있으며, 변경될 수 있습니다.

Yammer에 관한 정보를 담고 있으므로 이 문서의 정보는 [보존 정책에 대해 자세히 알아보기](retention.md)를 보완합니다.

다른 워크로드는 다음을 참조하세요.

- [SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기](retention-policies-sharepoint.md)
- [Microsoft Teams의 보존에 대해 자세히 알아보기](retention-policies-teams.md)
- [Exchange의 보존에 대해 자세히 알아보기](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>보존 및 삭제에 포함된 항목

Yammer에 대한 보존 정책을 사용하여 Yammer 사용자 메시지 및 커뮤니티 메시지를 삭제할 수 있으며 메시지의 텍스트 외에도 규정 준수를 위해 하이퍼텍스트 링크 및 다른 Yammer 메시지에 대한 링크와 같은 항목을 보존할 수 있습니다.

사용자 메시지에는 대화에 있는 모든 사람의 이름이 포함되며 커뮤니티 메시지에는 커뮤니티 이름과 메시지 제목(제공된 경우)이 포함됩니다.

Yammer에 대한 보존 정책을 사용할 때 이모티콘 형태의 다른 사람의 반응은 보존되지 않습니다.

Yammer와 함께 사용하는 파일은 Yammer의 보존 정책에 포함되지 않습니다. 이러한 항목에는 고유한 보존 정책이 있습니다.

## <a name="how-retention-works-with-yammer"></a>Yammer를 사용하는 경우의 보존 방식

이 섹션에서는 백엔드 스토리지 및 프로세스를 통해 규정 준수 요구 사항이 충족되는 방법과 현재 Yammer 앱에 표시되는 메시지가 아니라 eDiscovery 도구를 통해 확인해야 하는 방법에 대해 설명합니다.

보존 정책을 사용하여 Yammer에서 커뮤니티 메시지 및 사용자 메시지의 데이터를 보존하고 이러한 메시지를 삭제할 수 있습니다. Exchange 사서함은 이러한 메시지에서 복사된 데이터를 저장하는 데 사용됩니다. Yammer 사용자 메시지의 데이터는 사용자 메시지에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되며, 그룹 사서함의 숨겨진 유사한 폴더가 커뮤니티 메시지에 사용됩니다.

커뮤니티 메시지의 복사본은 사용자를 @멘션하거나 사용자에게 회신을 알릴 때 사용자 사서함의 숨겨진 폴더에 저장할 수도 있습니다. 이러한 메시지는 커뮤니티 메시지로 시작되지만 Yammer 사용자 메시지에 대한 보존 정책에는 종종 커뮤니티 메시지의 복사본이 포함됩니다.

이러한 숨겨진 폴더는 사용자 또는 관리자가 직접 액세스할 수 있도록 설계되지 않지만 규정 준수 관리자가 eDiscovery 도구를 사용하여 검색할 수 있는 데이터를 저장합니다.

> [!IMPORTANT]
> 커뮤니티 메시지의 복사본을 사용자 사서함에 저장할 수도 있으므로 Yammer 사용자 메시지에 대한 삭제 작업이 포함된 보존 정책으로 인해 Yammer 앱의 사용자에게 원래 커뮤니티 메시지가 더 이상 표시되지 않을 수 있습니다.
> 
> 그러나 원본 메시지의 복사본은 커뮤니티 그룹 사서함의 숨겨진 폴더에서 계속 사용할 수 있으며 eDiscovery를 통해 호환성 검색을 통해 액세스할 수 있습니다.

Yammer 메시지는 Exchange 사서함에 대해 구성된 보존 정책의 영향을 받지 않습니다. Yammer 메시지가 Exchange에 저장되어 있어도 이 Yammer 데이터는 **Yammer 커뮤니티 메시지** 및 **Yammer 사용자 메시지** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.

> [!NOTE]
> Yammer 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Yammer 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)으로 변환됩니다. 사용자에 대한 이 Yammer 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.

Yammer 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Yammer 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다. 타이머 작업의 실행은 7일까지 걸립니다. 이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 하나의 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.

> [!NOTE]
> [첫 번째 보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence) 때문에 다른 보존 정책으로 인해 동일한 항목을 유지해야 하거나 법적 또는 조사상의 이유로 eDiscovery 보류 상태에 있는 경우 영구 삭제는 항상 일시 중단됩니다.

Yammer 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.

보존 정책을 유지한 후 삭제하려면 다음을 수행합니다.

![Yammer 메시지의 보존 흐름 다이어그램.](../media/yammerretentionlifecycle.png)

다이어그램의 두 경로:

1. 보존 기간 동안 사용자가 **Yammer 메시지를 편집하거나 삭제** 하는 경우에는 원본 메시지가 즉시 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다. 이 메시지는 보존 기간이 만료될 때까지 저장된 다음 즉시 영구적으로 삭제됩니다.

2. **Yammer 메시지가 삭제되지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동합니다. 이 작업은 만료 날짜로부터 최대 7일이 걸립니다. 메시지가 SubstrateHolds 폴더에 있으면 즉시 영구적으로 삭제됩니다. 

> [!NOTE]
> SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다. 메시지가 영구적으로 삭제 될 때까지 (SubstrateHolds 폴더에서)는 eDiscovery 도구에 의해 검색가능한 상태로 유지됩니다.

보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.

### <a name="content-paths-for-retain-only-retention-policy"></a>보유 전용 보존 정책의 컨텐츠 경로

1. **Yammer 메시지를 편집하거나 삭제하는 경우**: 원본 메시지의 복사본은 SubstrateHolds 폴더에 즉시 만들어지고 보존 기간이 만료될 때까지 보존됩니다. 그러면 메시지가 SubstrateHolds 폴더에서 즉시 영구적으로 삭제됩니다.

2. **Yammer 메시지가 수정되거나 삭제되지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.

### <a name="content-paths-for-delete-only-retention-policy"></a>삭제 전용 보존 정책의 컨텐츠 경로

1. 보존 기간 동안 **Yammer 메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다. 이 작업은 만료 날짜로부터 최대 7일이 걸립니다. 그런 다음 즉시 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.

2. 해당 기간 동안 **사용자가 Yammer 메시지를 삭제하는 경우** 그 항목은 즉시 영구적으로 삭제되는 SubstrateHolds 폴더로 즉시 이동됩니다.

#### <a name="example-flows-and-timings-for-retention-policies"></a>보존 정책의 흐름 및 타이밍 예

다음 예제를 사용하여 이전 섹션에서 설명한 프로세스 및 타이밍이 다음 구성을 가진 보존 정책에 어떻게 적용되는지 확인합니다.

- [예제 1: 7년 동안 보존만](#example-1-retain-only-for-7-years)
- [예제 2: 30일 동안 보존한 다음 삭제](#example-2-retain-for-30-days-and-then-delete)
- [예제 3: 1일 후에 ​​삭제만](#example-3-delete-only-after-1-day)

영구 삭제를 참조하는 모든 예제의 경우 [보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence)으로 인해 메시지가 항목을 보존하기 위한 다른 보존 정책의 적용을 받거나 eDiscovery 보존이 적용되는 경우 이 작업이 일시 중지됩니다.

##### <a name="example-1-retain-only-for-7-years"></a>예제 1: 7년 동안 보존만

1일 차에 사용자가 새 Yammer 메시지를 게시합니다.

5일 차에 사용자가 해당 메시지를 편집합니다.

30일 차에 사용자가 현재 메시지를 삭제합니다.

보존 결과:

- 원본 메시지의 경우:
    - 5일 차에는 메시지가 SubstrateHolds 폴더에 복사되어 eDiscovery 도구를 사용하여 1일부터 최소 7년(보존 기간) 동안 계속 검색할 수 있습니다.

- 현재 (편집된) 메시지의 경우:
    - 30일 차에는 메시지가 SubstrateHolds 폴더에 이동되어 eDiscovery 도구를 사용하여 1일부터 최소 7년(보존 기간) 동안 계속 검색할 수 있습니다.

사용자가 보존 기간이 아닌 지정된 보존 기간 이후에 현재 메시지를 삭제 한 경우 메시지는 여전히 SubstrateHolds 폴더로 이동됩니다. 그러나 이제 보존 기간이 만료되었으므로 메시지는 최소 1일 후에 영구적으로 삭제되고 일반적으로 1~7일 이내에 삭제됩니다.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>예제 2: 30일 동안 보존한 다음 삭제

1일 차에 사용자가 새 Yammer 메시지를 게시합니다.

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

1일 차에 사용자가 새 Yammer 메시지를 게시합니다.

사용자가 메시지를 편집하거나 삭제하지 않은 경우 보존 결과의 예:

- 5일(일반적으로 2일 보존 기간이 시작된 후 1~7일):
    - 메시지는 이 폴더로 이동하며 eDiscovery 도구로 검색할 수 있는 최소 1일 동안 이 폴더에 남아 있습니다.

- 9일(일반적으로 SubstrateHolds 폴더에서 최소 1일 이후부터 1~7일):
    - 메시지가 영구적으로 삭제된 후 eDiscovery 검색에서 반환되지 않습니다.

이 예제에서 볼 수 있는처럼, 하루만에 메시지를 삭제하도록 보존 정책을 구성할 수 있습니다. 그러나 이 서비스는 규정 준수 삭제를 보장하기 위해 여러 프로세스를 진행합니다. 결과적으로 1일 후 삭제 작업은 메시지가 영구적으로 삭제되기 까지 16일이 걸릴 수 있으므로 eDiscovery 검색에서 더 이상 반환되지 않습니다.

## <a name="messages-and-external-users"></a>메시지 및 외부 사용자

기본적으로 Yammer 사용자 메시지에 대한 보존 정책은 조직의 모든 사용자에게 적용되지만 외부 사용자에게는 적용되지 않습니다. **포함된 사용자에 대한 옵션 편집** 을 사용하고 해당 계정을 지정하는 경우 외부 사용자에게 보존 정책을 적용할 수 있습니다.

지금은 Azure B2B 게스트 사용자가 지원되지 않습니다.

## <a name="when-a-user-leaves-the-organization"></a>사용자가 조직을 떠나는 경우 

사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 Yammer 사용자 메시지는 비활성 사서함에 저장됩니다. 이들 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다. 자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요. 

사용자가 Yammer에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.

## <a name="limitations"></a>제한 사항

Yammer 보존 정책은 현재 미리 보기 상태이며 당사는 보존 기능 최적화를 계속 진행하고 있습니다. 그동안 Yammer 커뮤니티 메시지 및 사용자 메시지에 대해 보존을 사용할 때 다음 제한 사항에 유의해야 합니다.

- **Yammer 사용자 메시지** 위치에 대해 **편집** 을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다. 보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.

## <a name="configuration-guidance"></a>구성 지침

Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.

Yammer에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.
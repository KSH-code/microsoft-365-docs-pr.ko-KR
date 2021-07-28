---
title: Microsoft 365 서비스 상태를 확인하는 방법
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: 지원에 전화하기 전에 Microsoft 365 서비스의 상태를 확인하여 활성 서비스 중단이 있는지 확인하세요.
ms.openlocfilehash: fd54e888ffa1522e43c5e798ada855f9ca9f7785
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2021
ms.locfileid: "53596257"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Microsoft 365 서비스 상태를 확인하는 방법

[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

[Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)의 **서비스 상태** 페이지에서 웹상의 Office, Yammer, Microsoft Dynamics CRM 및 모바일 장치 관리 클라우드 서비스를 비롯한 Microsoft 서비스의 상태를 볼 수 있습니다. 클라우드 서비스와 관련된 문제가 발생한 경우 지원 서비스에 문의하거나 문제 해결에 시간을 소비하기 전에 먼저 서비스 상태를 확인하여 이 문제가 현재 해결이 진행 중인 상태인 알려진 문제인지 확인할 수 있습니다.

관리 센터에 로그인할 수 없는 경우 [서비스 상태 페이지](https://status.office365.com)를 사용하여 테넌트 로그인을 방해하는 알려진 문제를 확인할 수 있습니다.  또한 Twitter에서 [@MSFT365status](https://twitter.com/MSFT365Status)를 팔로우하여 특정 이벤트에 대한 정보를 확인하세요.

## <a name="how-to-check-service-health"></a>서비스 상태를 확인하는 방법

1. [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339)의 Microsoft 365 관리 센터로 이동하여 관리자 계정으로 로그인합니다.

    > [!NOTE]
    > 전역 관리자 또는 서비스 지원 관리자 역할이 할당된 사용자는 서비스 상태를 볼 수 있습니다. Exchange, SharePoint 및 비즈니스용 Skype 관리자가 서비스 상태를 볼 수 있도록 허용하려면 서비스 관리자 역할도 할당되어야 합니다. 서비스 상태를 볼 수 있는 역할에 대한 자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)를 참조하세요.

2. 서비스 상태를 보려면 관리 센터에서 **상태** > **서비스 상태** 로 이동하거나 **홈 대시보드에서 **서비스 상태** 카드를 선택합니다.**. 대시보드 카드는 활성 서비스 문제가 있는지 여부와 자세한 **서비스 상태** 페이지에 대한 링크를 나타냅니다.

3. **서비스 상태** 페이지에서 각 클라우드 서비스의 상태가 표 형식으로 표시됩니다.

   ![서비스 상태의 현재 문제 보기](../media/service-health-all-services.png)

**모든 서비스** 탭(기본 보기)에는 모든 서비스, 현재 상태, 활성 인시던트 또는 권고가 표시됩니다. **상태** 열의 아이콘과 상태는 각 서비스의 상태를 나타냅니다.

서비스에 대한 활성 인시던트 또는 권고가 있는 경우 중첩 테이블의 서비스 이름 바로 아래에 나열됩니다. 서비스 이름 왼쪽에 있는 갈매기 모양 아이콘을 클릭하면 중첩된 테이블을 축소하여 이 보기에서 인시던트 또는 권고를 숨길 수 있습니다.   

모든 활성 인시던트만 표시하도록 보기를 필터링하려면 페이지 상단의 **인시던트** 탭을 선택합니다. **권고** 탭을 선택하면 게시된 모든 활성 권고만 표시됩니다.

**기록** 탭에는 지난 7일 또는 30일 이내에 해결된 모든 인시던트 및 권고가 표시됩니다.

Microsoft 365 서비스에 문제가 있고 **서비스 상태** 페이지에 표시되지 않는 경우 **문제 신고** 를 선택하고 짧은 형식을 작성하여 알려주세요. Microsoft는 다른 조직의 관련 데이터와 보고서를 살펴보고 문제가 얼마나 널리 퍼져 있는지, 그리고 그것이 당사의 서비스에서 비롯되었는지 확인할 것입니다. 문제가 발생한 경우 해결 방법을 추적할 수 있는 **서비스 상태** 페이지에 새로운 문제 또는 권고로 추가됩니다. **보고된 문제** 페이지에는 테넌트가 이 양식에서 보고한 모든 문제와 상태가 표시됩니다.

대시보드에 표시되는 서비스 보기를 맞춤설정하려면 **환경설정** > **맞춤 보기** 를 선택하고 서비스 상태 대시보드 보기에서 필터링할 서비스의 확인란을 선택 취소합니다. 모니터링하려는 각 서비스에 대해 확인란이 선택되어 있는지 확인합니다.

테넌트에 영향을 미치는 새 인시던트 및 활성 인시던트에 대한 상태 변경에 대한 이메일 알림을 신청하려면 **기본 설정** > **이메일** 을 선택하고 **다음 위치에서 서비스 상태 알림 보내기를 클릭합니다. 이메일** 을 입력하고 다음을 지정합니다.

- 최대 2개의 이메일 주소.
- 인시던트 또는 권고에 대한 알림을 원하는지 여부
- 알림을 받고 싶은 서비스

서비스에 대한 모든 이벤트 대신 개별 이벤트에 대한 이메일 알림을 구독할 수도 있습니다. 이렇게 하려면 이메일 알림 업데이트를 수신할 활성 문제를 선택하고 **이 문제에 대한 알림 관리** 를 선택한 후 다음을 지정합니다. 
- 최대 2개의 이메일 주소.

> [!NOTE]
> 각 관리자는 기본 설정을 지정할 수 있으며 위의 두 개의 이메일 주소 제한은 관리자 계정당입니다.

> [!TIP]
> 또한 모바일 장치에서 [Microsoft 365 관리 앱](https://go.microsoft.com/fwlink/p/?linkid=627216)을 사용하여 푸시 알림을 최신 상태로 유지하는 좋은 방법인 서비스 상태를 볼 수 있습니다.

### <a name="view-details-of-posted-service-health"></a>게시된 서비스 상태 세부 정보 보기

**모든 서비스** 보기에서 문제 제목을 선택하면 문제 세부 정보 페이지가 표시됩니다. 여기에는 솔루션을 개발하는 동안 게시된 모든 메시지의 피드를 포함하여 문제에 대한 자세한 정보가 표시됩니다. 

[ ![서비스 권고를 보여주는 스크린샷](../media/service-health-advisory.png) ](../media/service-health-advisory.png#lightbox)

권고 또는 인시던트 요약은 다음 정보를 제공합니다.

- **제목** - 문제 요약
- **ID** - 문제의 숫자 식별자입니다.
- **서비스** - 영향을 받는 서비스의 이름입니다.
- **마지막 업데이트** - 서비스 상태 메시지가 마지막으로 업데이트된 시간입니다.
- **예상 시작 시간** - 문제가 시작된 예상 시간입니다.
- **상태** - 이 문제가 서비스에 미치는 영향.
- **사용자 영향** - 이 문제가 최종 사용자에게 미치는 영향에 대한 간략한 설명입니다.
- **모든 업데이트** - 솔루션 적용 과정에서 진행 상황을 알리기 위해 메시지를 자주 게시합니다.

![문제 세부 정보를 보여주는 스크린샷](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>서비스 상태 세부 정보 번역

기계 번역을 사용하여 귀하가 선호하는 언어로 메시지를 자동으로 표시합니다. 언어 설정 방법에 대한 자세한 내용은 [서비스 상태 대시보드에 대한 언어 번역](lang-service-health.md)을 참조하세요.

### <a name="definitions"></a>정의

대부분의 시간에 서비스는 추가 정보 없이 정상으로 표시됩니다. 서비스에 문제가 있으면 문제가 권고 또는 인시던트로 식별되고 현재 상태를 표시합니다.

> [!TIP]
> 계획된 유지 관리 이벤트는 서비스 상태에 표시되지 않습니다. **메시지 센터** 를 통해 최신 상태를 유지함으로써 계획된 유지 관리 이벤트를 추적할 수 있습니다. 변경 계획으로 분류된 메시지로 필터링하여 변경이 발생하는 시기, 해당 효과 및 이러한 변경에 대해 준비하는 방법을 확인하세요. 자세한 내용은 [Microsoft 365의 메시지 센터](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)를 참조하세요.

### <a name="incidents-and-advisories"></a>인시던트 및 권고

| 아이콘 | 설명 |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|서비스에 권고가 표시되면 Microsoft에서 일부 사용자에게 영향을 미치는 문제를 알고 있지만, 서비스를 계속 사용할 수는 있습니다. 권고에는 일반적으로 문제에 대한 해결 방법이 있으며, 문제가 일시적으로 발생하는 것일 수 있거나 범위 및 사용자 영향에서 제한적입니다.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|서비스에 활성 인시던트가 표시되면 이 인시던트가 중요 문제이며 서비스 또는 서비스의 주요 기능을 사용할 수 없습니다. 예를 들어 사용자가 전자 메일을 보내고 받을 수 없거나 로그인할 수 없습니다. 인시던트는 사용자에게 눈에 띄는 영향을 줍니다. 진행 중인 인시던트가 있는 경우 서비스 상태 대시보드에서 조사, 완화 노력 및 해결 확인과 관련된 업데이트를 제공합니다.  <br/> |

### <a name="status-definitions"></a>상태 정의

| 상태 | 정의 |
|:-----|:-----|
|**조사하는 중** | Microsoft에서 잠재적인 문제를 알고 있으며 문제의 상황과 영향의 범위에 대한 추가 정보를 수집하고 있습니다. |
|**서비스 저하** | Microsoft에서 서비스 또는 기능 사용에 영향을 줄 수 있는 문제가 있음을 확인했습니다. 서비스가 평소보다 느리게 작동하거나, 일시적인 중단이 발생하거나, 기능이 작동하지 않는 등의 경우에 이 상태가 표시될 수 있습니다. |
|**서비스 중단** | 문제가 사용자의 서비스 액세스 기능에 영향을 준다고 판단한 이 상태가 표시됩니다. 이 경우 문제가 중대하며 일관되게 재현될 수 있습니다. |
|**서비스를 복원하는 중** | 문제의 원인이 식별되었으며, Microsoft에서 수행할 정정 작업을 알고 있고 서비스를 다시 정상 상태로 복원하는 프로세스를 진행하고 있습니다. |
|**확장된 복구** | 이 상태는 대부분의 사용자에 대해 서비스를 복원하기 위한 정정 작업이 진행 중이지만, 영향을 받는 모든 시스템에 이를 적용하는 데 시간이 다소 소요될 것임을 나타냅니다. 영구적인 수정 사항을 적용하기 위해 대기하는 동안 영향을 줄이기 위해 임시 수정 사항을 적용한 경우에도 이 상태가 표시될 수 있습니다. |
|**조사 일시 중단됨** | 잠재적 문제에 대한 자세한 조사 결과, 추가 조사를 하기 위한 고객의 추가 정보가 필요한 경우 이 상태가 표시됩니다. 고객의 행동이 요구되는 경우 필요한 데이터나 로그를 알려드립니다. |
|**서비스 복원됨** | Microsoft에서 정정 작업이 기본 문제를 해결했으며 서비스가 정상 상태로 복원되었음을 확인했습니다. 문제를 확인하려면 문제 세부 정보를 확인하세요. |
|**가양성** | 자세한 조사 결과 서비스가 정상적이며 설계된 대로 작동하고 있음을 확인했습니다. 서비스에 대한 영향이 관찰되지 않았거나 인시던트의 원인이 서비스 외부에서 발생했습니다. |
|**인시던트 후 보고서 게시됨** | 근본 원인 정보와 유사한 문제가 다시 발생하지 않도록 하기 위한 다음 단계가 포함된 특정 문제에 대한 사후 인시던트 보고서를 게시했습니다. |

### <a name="message-post-types"></a>메시지 게시물 유형

| 유형 | 정의 |
|:-----|:-----|
|**빠른 업데이트** | 모든 고객이 사용할 수 있는 광범위하게 영향을 미치는 인시던트에 대한 짧고 빈번한 증분 업데이트입니다. |
|**추가 세부 정보** | 이러한 추가 게시물은 인시던트 처리에 대한 더 깊은 가시성을 제공하기 위해 보다 풍부한 기술 및 해결 세부 정보를 제공합니다. 이는 [Exchange Online 모니터링](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements)에 대해 설명된 것과 동일한 요구사항을 충족하는 테넌트에서 사용할 수 있습니다. |

### <a name="history"></a>기록

서비스 상태를 사용하면 현재 상태를 확인하고 지난 30일 동안 테넌트에 영향을 미친 서비스 권고 및 인시던트의 기록을 볼 수 있습니다. 모든 서비스의 과거 상태를 보려면 **기록** 보기를 선택합니다.

가동 시간에 대한 약속에 대한 자세한 내용은 [Microsoft 365의 투명한 운영](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)을 참조하세요.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 활동 보고서](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[메시지 센터 기본 설정](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[관리 센터에서 Windows 릴리스 상태를 확인하는 방법](/windows/deployment/update/check-release-health)

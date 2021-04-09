---
title: Microsoft 365 서비스 상태 확인 방법
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 지원 서비스에 문의하기 전에 Microsoft 365 서비스의 상태를 확인하여 활성 서비스 중단이 있는지 확인할 수 있습니다.
ms.openlocfilehash: e0ab4eaa1f7a96168839a4abef2f0f254a21d0ad
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644635"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Microsoft 365 서비스 상태 확인 방법

[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

웹용 Office, Yammer, Microsoft Dynamics CRM 및 모바일 장치 관리 클라우드 서비스를 비롯한 Microsoft 서비스의 상태는 Microsoft  [365](https://go.microsoft.com/fwlink/p/?linkid=2024339)관리 센터의 서비스 상태 페이지에서 볼 수 있습니다. 클라우드 서비스와 관련된 문제가 발생한 경우 지원 서비스에 문의하거나 문제 해결에 시간을 소비하기 전에 먼저 서비스 상태를 확인하여 이 문제가 현재 해결이 진행 중인 상태인 알려진 문제인지 확인할 수 있습니다.

관리 센터에 로그인할 수 없는 경우 서비스 상태 [](https://status.office365.com) 페이지를 사용하여 테넌트에 로그인하지 못하게 하는 알려진 문제를 확인할 수 있습니다.  또한 Twitter의 @MSFT365status [](https://twitter.com/MSFT365Status) 팔로우하여 특정 이벤트에 대한 정보를 볼 수 있습니다.

  
### <a name="how-to-check-service-health"></a>서비스 상태 확인 방법

1. 의 Microsoft 365 관리 센터로 이동하고 관리자 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) 계정으로 로그인합니다.

    > [!NOTE]
    > 전역 관리자 또는 서비스 지원 관리자 역할이 할당된 사용자는 서비스 상태 볼 수 있습니다. Exchange, SharePoint 및 비즈니스용 Skype 관리자가 서비스 상태를 볼 수 있도록 하려면 이러한 관리자에게도 서비스 관리자 역할을 할당해야 합니다. 서비스 상태 볼 수 있는 역할에 대한 자세한 내용은 관리자 역할 [정보를 참조하세요.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)
  
2. 새 관리 센터를 사용하지 않는 경우  홈 페이지에서  오른쪽 위에 있는 새 관리 센터 시도 토글을 선택합니다.

3. 서비스 상태 보기를 위해 관리 센터에서 상태 서비스 상태로 이동하거나 홈 대시보드에서 서비스 상태   >   **카드를 선택합니다.**  대시보드 카드는 활성 서비스 문제가 있는지 여부와 자세한 서비스 상태 페이지에 대한 **링크를** 나타냅니다.
  
4. 서비스 **상태 페이지에서** 각 클라우드 서비스의 상태는 표 형식으로 표시됩니다.

   ![View of current issues in service health](../media/service-health-all-services.png)

모든 **서비스 탭(기본** 보기)에는 모든 서비스와 해당 현재 상태가 표시됩니다. 아이콘과 **상태** 열은 각 서비스의 상태를 나타냅니다. 

현재 인시던트가 발생하는 서비스로 보기를  필터링하려면 페이지 위쪽의 인시던트 탭을 선택합니다. 권고 **탭을 선택하면** 현재 권고가 게시된 서비스만 표시됩니다. 

기록 **탭에는** 해결된 인시던트 및 권고 기록이 표시됩니다.

Microsoft 365 서비스에서 문제가 발생하고 서비스 상태 페이지에 나열되어 있는  문제가 없는 경우 문제 보고 및 짧은 양식을 완료하여 해당 문제를 알려 주세요. 다른 조직의 관련 데이터 및 보고서를 살펴보고 문제가 얼마나 광범위하고, 서비스가 시작된 경우를 살펴 봐야 합니다. 이 경우 해결을 추적할 수 있는 서비스 상태 페이지에서  새 인시던트 또는 권고로 추가합니다. 약 30분 내에 목록에 나타나지 않으면 지원에 문의하여 문제를 해결하는 것이 가장 까다로우면 됩니다.

대시보드에 표시하는 서비스의 보기를 사용자 지정하려면 기본 설정 사용자 지정 보기를 선택하고 서비스 상태 대시보드 보기에서 필터링할 서비스의 확인란 선택을   >  취소합니다. 모니터링할 각 서비스에 대해 확인란이 선택되어 있는지 확인란을 선택해야 합니다.    

테넌트에 영향을 주는 새 인시던트 및 활성 인시던트에 대한 상태 변경에 대한 전자 메일 알림을 등록하려면 기본 설정 전자 메일을 선택하고 전자 메일로 서비스 열 알림 보내기 를 클릭한 후 다음을  >  지정합니다. 

- 최대 2개의 전자 메일 주소.
- 인시던트 또는 권고에 대한 알림을 원하는지 여부
- 알림을 원하는 서비스

> [!NOTE]
> 각 관리자는 기본 설정을 사용할 수 있으며 위의 두 전자 메일 주소 제한은 관리자 계정당입니다.

> [!TIP]
> 모바일 장치에서 [Microsoft 365 관리](https://go.microsoft.com/fwlink/p/?linkid=627216) 앱을 사용하여 서비스 상태도 볼 수 있습니다. 이는 푸시 알림을 사용하여 최신 정보를 유지 하는 좋은 방법입니다. 
  
### <a name="view-details-of-posted-service-health"></a>게시된 서비스 상태의 세부 정보 보기

모든 **서비스 보기에서** 서비스 상태를 선택하면 권고 또는 인시던트의 요약 보기가 열립니다.
  
[![서비스 권고를 보여주는 스크린샷 ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

권고 또는 인시던트 요약은 다음 정보를 제공합니다.

- **title** - 문제의 요약입니다.
- **Service** - 영향을 받는 서비스의 이름입니다.
- **ID** - 문제의 숫자 식별자입니다.
- **Status** - 이 문제가 서비스에 미치는 영향.
- **시작 시간** - 문제가 시작된 시간입니다.
- **Last updated** - 서비스 상태 메시지가 마지막으로 업데이트된 시간입니다. 솔루션 적용 진행률을 알려주기 위해 자주 메시지를 게시합니다.

문제 제목을 선택하여 해결 방법에서 작업하는 동안 게시된 모든 [](#history) 메시지 기록을 포함하여 문제에 대한 자세한 정보를 표시하는 문제 세부 정보 페이지를 볼 수 있습니다.

![문제 세부 정보를 보여주는 스크린샷](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>서비스 상태 세부 정보 번역

서비스 상태 설명은 실시간으로 게시되므로 해당 언어로 자동 번역되지 않으며 서비스 이벤트의 세부 정보는 영어로만 제공됩니다. 설명을 번역하려면 다음 단계를 수행합니다.
  
1. 1.[번역기](https://www.bing.com/translator/)로 이동합니다.

2. **서비스 상태** 페이지에서 인시던트 또는 권고를 선택합니다. **세부 정보 표시** 아래에서 문제에 대한 텍스트를 복사합니다.

3. 번역기에서 텍스트를 붙여넣고 **번역하기** 을 선택합니다.

### <a name="definitions"></a>정의

대부분의 경우 서비스는 추가 정보도 없는 정상으로 표시됩니다. 서비스에 문제가 있으면 문제가 권고 또는 인시던트로 식별되고 현재 상태를 표시합니다.
  
> [!TIP]
> 계획된 유지 관리 이벤트는 서비스 상태에 표시되지 않습니다. **메시지 센터** 를 통해 최신 상태를 유지함으로써 계획된 유지 관리 이벤트를 추적할 수 있습니다. 변경 계획으로 분류된 메시지로 필터링하여 변경이 발생하는 시기, 해당 효과 및 이러한 변경에 대해 준비하는 방법을 확인하세요. 자세한 [내용은 Microsoft 365의 메시지](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) 센터를 참조합니다.
  
### <a name="incidents-and-advisories"></a>인시던트 및 권고

| 아이콘 | 설명 |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|서비스에 권고가 표시되면 Microsoft에서 일부 사용자에게 영향을 미치는 문제를 알고 있지만, 서비스를 계속 사용할 수는 있습니다. 권고에는 일반적으로 문제에 대한 해결 방법이 있으며, 문제가 일시적으로 발생하는 것일 수 있거나 범위 및 사용자 영향에서 제한적입니다.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|서비스에 활성 인시던트가 표시되면 이 인시던트가 중요 문제이며 서비스 또는 서비스의 주요 기능을 사용할 수 없습니다. 예를 들어 사용자가 전자 메일을 보내고 받을 수 없거나 로그인할 수 없습니다. 인시던트는 사용자에게 눈에 띄는 영향을 줍니다. 진행 중인 인시던트가 있는 경우 서비스 상태 대시보드에서 조사, 완화 노력 및 해결 확인과 관련된 업데이트를 제공합니다.  <br/> |

### <a name="status-definitions"></a>상태 정의

| 상태 | 정의 |
|:-----|:-----|
|**조사 중** | Microsoft에서 잠재적인 문제를 알고 있으며 문제의 상황과 영향의 범위에 대한 추가 정보를 수집하고 있습니다. |
|**서비스 저하** | Microsoft에서 서비스 또는 기능 사용에 영향을 줄 수 있는 문제가 있음을 확인했습니다. 서비스가 평소보다 느리게 작동하거나, 일시적인 중단이 발생하거나, 기능이 작동하지 않는 등의 경우에 이 상태가 표시될 수 있습니다. |
|**서비스 중단** | 문제가 사용자의 서비스 액세스 기능에 영향을 준다고 판단한 이 상태가 표시됩니다. 이 경우 문제가 중대하며 일관되게 재현될 수 있습니다. |
|**서비스를 복원하는 중** | 문제의 원인이 식별되었으며, Microsoft에서 수행할 정정 작업을 알고 있고 서비스를 다시 정상 상태로 복원하는 프로세스를 진행하고 있습니다. |
|**확장된 복구** | 이 상태는 대부분의 사용자에 대해 서비스를 복원하기 위한 정정 작업이 진행 중이지만, 영향을 받는 모든 시스템에 이를 적용하는 데 시간이 다소 소요될 것임을 나타냅니다. 영구적인 수정 사항을 적용하기 위해 대기하는 동안 영향을 줄이기 위해 임시 수정 사항을 적용한 경우에도 이 상태가 표시될 수 있습니다. |
|**조사 일시 중단됨** | 잠재적 문제에 대한 자세한 조사 결과, 추가 조사를 하기 위한 고객의 추가 정보가 필요한 경우 이 상태가 표시됩니다. 고객의 행동이 요구되는 경우 필요한 데이터나 로그를 알려드립니다. |
|**서비스 복원됨** | Microsoft에서 정정 작업이 기본 문제를 해결했으며 서비스가 정상 상태로 복원되었음을 확인했습니다. 문제를 확인하려면 문제 세부 정보를 확인하세요. |
|**가긍성** | 자세한 조사가 끝날 때 서비스가 정상 상태인지와 설계에 따라 작동하고 있는 것으로 확인했습니다. 서비스에 대한 영향이 관찰되지 않았습니다. 또는 인시던트의 원인이 서비스 외부에서 발생했습니다. |
|**게시된 인시던트 사후 보고서** | 근본 원인 정보가 포함된 특정 문제와 유사한 문제가 다시 발생하지 않도록 하는 다음 단계가 포함된 인시던트 사후 보고서를 게시했습니다. |

### <a name="history"></a>기록

서비스 상태를 통해 현재 상태를 보고 지난 30일 동안 테넌트에 영향을 미쳤던 모든 서비스 권고 및 인시던트의 기록을 볼 수 있습니다. 모든 서비스의 지난 상태 확인하려면 문제 **세부** 정보 페이지에서 기록 보기를 선택합니다.
  
![Show link to health history](../media/service-health-view-history.png)
  
선택한 시간 범위에서 게시된 모든 서비스 상태 메시지 목록이 다음과 같이 표시됩니다.
  
![View service health history](../media/service-health-history.png)
  
모든 행을 확장하여 문제의 세부 정보를 볼 수 있습니다.
  
작동 시간 약속에 대한 자세한 내용은 [Microsoft 365의 투명한 운영을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 활동 보고서](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 [메시지 센터 기본 설정](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)<br/>
[관리 센터에서 Windows 릴리스 상태 확인 방법](https://docs.microsoft.com/windows/deployment/update/check-release-health)

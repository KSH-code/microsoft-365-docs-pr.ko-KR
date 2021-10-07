---
title: Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
description: Multi-Geo에서 Teams 작동하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: e561332052f226fe98d0304bd6a76d6b76cfd1c4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177282"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Microsoft Teams

Teams Multi-Geo 기능을 Teams 채팅 데이터를 지정된 지리적 위치에 저장할 수 있습니다. 채팅 데이터는 비공개 메시지, 채널 메시지 및 채팅에 사용되는 이미지를 포함하여 채팅 메시지로 구성됩니다.

Teams 사용자 및 그룹에 대해 PDL(기본 설정 데이터 위치)을 사용하여 데이터를 저장할 위치를 결정할 수 있습니다. PDL이 설정되지 않은 경우 또는 유효하지 않은 경우 데이터는 테넌트의 중앙 위치에 저장됩니다.

> [!NOTE]
> 2021년 7월에 출시된 Teams Multi-Geo 기능 채팅 및 채널 메시지는 다음 몇 분기 동안 올바른 지리적 위치로 자동으로 마이그레이션됩니다. 새 PDL 변경 내용은 테넌트가 초기 동기화를 완료한 후 처리하고 그 이후의 새 PDL 변경 내용은 수신된 순서대로 큐에 대기하고 처리됩니다.

## <a name="user-chat"></a>사용자 채팅

사용자 채팅에는 일대일, 일대다 및 비공개 모임 메시지가 포함됩니다.

새 사용자를 만들면 Teams PDL을 읽고 해당 지리적 위치에 모든 채팅 데이터를 저장합니다.

기존 사용자의 경우 관리자가 사용자의 PDL을 추가하거나 수정하면 해당 사용자의 채팅 데이터가 마이그레이션 큐에 추가되어 지정된 지리적 위치로 이동됩니다.

일대일 또는 일대다 채팅의 저장소 위치는 채팅을 만든 사람의 PDL을 기반으로 합니다. 해당 사용자의 PDL이 변경된 경우 채팅이 새 지리적 위치로 마이그레이션됩니다. 모임 채팅의 저장소 위치는 모임 이끌이의 PDL을 기반으로 합니다.

사용자 계정 데이터의 현재 위치를 Teams [PowerShell에](/powershell/module/teams/connect-microsoftteams) Teams 다음 명령을 실행합니다.

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>채널 메시지

각 Microsoft 365 그룹에는 관련 데이터를 저장할 지리적 위치를 지정하는 PDL(기본 설정 데이터 위치)이 있습니다. Teams 팀과 연결된 그룹에 대해 PDL을 사용하여 해당 팀의 채널 메시징 데이터를 저장할 위치를 결정할 수 있습니다. 여기에는 채널 모임 내에서 발생하는 채팅뿐만 아니라 비공개 채널도 포함됩니다.

사용자가 새 팀을 만드는 경우 해당 사용자의 PDL은 새 팀 그룹에 할당된 PDL을 Microsoft 365 합니다. 그룹 PDL은 해당 팀의 데이터가 저장되는 위치를 파악합니다. 해당 사용자의 PDL이 나중에 변경될 경우 그룹의 PDL이 변경되지 않습니다.

기존 팀의 경우 관리자가 팀을 백업하는 Microsoft 365 그룹의 PDL을 추가하거나 수정하면 해당 팀의 채널 메시징 데이터가 지정된 지리적 위치로 이동될 마이그레이션 큐에 추가됩니다.

Microsoft 365 그룹의 PDL을 변경하면 선택한 위치로 마이그레이션할 Teams 데이터가 대기열에 추가됩니다. 그러나 그룹과 연결된 SharePoint 사이트나 파일이 자동으로 마이그레이션되지는 않습니다. Move a SharePoint 사이트를 다른 지리적 위치로 이동의 절차에 따라 사이트를 별도로 [이동해야 합니다.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) 두 단계를 모두 수행하여 서로 다른 위치에 있는 Teams 및 SharePoint 데이터를 저장하지 않도록 해야 합니다.

팀 데이터의 현재 위치를 찾으면 [PowerShell에](/powershell/module/teams/connect-microsoftteams) Teams 다음 명령을 실행합니다.

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>사용자 환경

Teams Multi-Geo는 최종 사용자에게 매끄럽게 연결됩니다. 사용자 또는 그룹의 PDL을 변경하면 해당 데이터가 마이그레이션을 위해 큐에 대기하고 마이그레이션이 수행되는 동안에도 사용자 또는 Teams 클라이언트에 영향을 미치지 Teams 자동으로 수행됩니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Multi-Geo 테넌트 구성](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[다중 지역 환경 관리](administering-a-multi-geo-environment.md)

[Multi-Geo 환경에서 Exchange Online 사서함 관리](administering-exchange-online-multi-geo.md)

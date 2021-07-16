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
localization_priority: Normal
description: Multi-Geo에서 Teams 작동하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453528"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="71ec6-103">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71ec6-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="71ec6-104">Teams Multi-Geo 기능을 Teams 채팅 데이터를 지정된 지리적 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="71ec6-105">채팅 데이터는 비공개 메시지, 채널 메시지 및 채팅에 사용되는 이미지를 포함하여 채팅 메시지로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="71ec6-106">Teams 사용자 및 그룹에 대해 PDL(기본 설정 데이터 위치)을 사용하여 데이터를 저장할 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="71ec6-107">PDL이 설정되지 않은 경우 또는 유효하지 않은 경우 데이터는 테넌트의 중앙 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="71ec6-108">사용자 채팅</span><span class="sxs-lookup"><span data-stu-id="71ec6-108">User chat</span></span>

<span data-ttu-id="71ec6-109">사용자 채팅에는 일대일, 일대다 및 비공개 모임 메시지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="71ec6-110">새 사용자를 만들면 Teams PDL을 읽고 해당 지리적 위치에 모든 채팅 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="71ec6-111">기존 사용자의 경우 관리자가 사용자의 PDL을 추가하거나 수정하면 해당 사용자의 채팅 데이터가 마이그레이션 큐에 추가되어 지정된 지리적 위치로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="71ec6-112">일대일 또는 일대다 채팅의 저장소 위치는 채팅을 만든 사람의 PDL을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="71ec6-113">해당 사용자의 PDL이 변경된 경우 채팅이 새 지리적 위치로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="71ec6-114">모임 채팅의 저장소 위치는 모임 이끌이의 PDL을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="71ec6-115">사용자 계정 데이터의 현재 위치를 Teams [PowerShell에](/powershell/module/teams/connect-microsoftteams) Teams 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="71ec6-116">채널 메시지</span><span class="sxs-lookup"><span data-stu-id="71ec6-116">Channel messages</span></span>

<span data-ttu-id="71ec6-117">각 Microsoft 365 그룹에는 관련 데이터를 저장할 지리적 위치를 지정하는 PDL(기본 설정 데이터 위치)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="71ec6-118">Teams 팀과 연결된 그룹에 대해 PDL을 사용하여 해당 팀의 채널 메시징 데이터를 저장할 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="71ec6-119">여기에는 채널 모임 내에서 발생하는 채팅뿐만 아니라 비공개 채널도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-119">This includes private channels as well as chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="71ec6-120">사용자가 새 팀을 만드는 경우 해당 사용자의 PDL은 새 팀 그룹에 할당된 PDL을 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="71ec6-121">그룹 PDL은 해당 팀의 데이터가 저장되는 위치를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="71ec6-122">해당 사용자의 PDL이 나중에 변경될 경우 그룹의 PDL이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="71ec6-123">기존 팀의 경우 관리자가 팀을 백업하는 Microsoft 365 그룹의 PDL을 추가하거나 수정하면 해당 팀의 채널 메시징 데이터가 지정된 지리적 위치로 이동될 마이그레이션 큐에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="71ec6-124">Microsoft 365 그룹의 PDL을 변경하면 선택한 위치로 마이그레이션할 Teams 데이터가 대기열에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="71ec6-125">그러나 그룹과 연결된 SharePoint 사이트나 파일이 자동으로 마이그레이션되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="71ec6-126">Move a SharePoint 사이트를 다른 지리적 위치로 이동의 절차에 따라 사이트를 별도로 [이동해야 합니다.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)</span><span class="sxs-lookup"><span data-stu-id="71ec6-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="71ec6-127">두 단계를 모두 수행하여 서로 다른 위치에 있는 Teams 및 SharePoint 데이터를 저장하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="71ec6-128">팀 데이터의 현재 위치를 찾으면 [PowerShell에](/powershell/module/teams/connect-microsoftteams) Teams 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="71ec6-129">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="71ec6-129">User Experience</span></span>

<span data-ttu-id="71ec6-130">Teams Multi-Geo는 최종 사용자에게 매끄럽게 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="71ec6-131">사용자 또는 그룹의 PDL을 변경하면 해당 데이터가 마이그레이션을 위해 큐에 대기하고 마이그레이션이 수행되는 동안에도 사용자 또는 Teams 클라이언트에 영향을 미치지 Teams 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ec6-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="71ec6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71ec6-132">See also</span></span>

[<span data-ttu-id="71ec6-133">Microsoft 365 Multi-Geo 테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="71ec6-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="71ec6-134">다중 지역 환경 관리</span><span class="sxs-lookup"><span data-stu-id="71ec6-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="71ec6-135">Multi-Geo 환경에서 Exchange Online 사서함 관리</span><span class="sxs-lookup"><span data-stu-id="71ec6-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)

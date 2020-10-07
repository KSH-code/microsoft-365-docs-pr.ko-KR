---
title: 그룹 서비스 상호 작용
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 그룹 서비스 상호 작용
ms.openlocfilehash: 235a897314a784ba3bb1ac50fe8bdfe9986a70d3
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377632"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="e12e7-103">그룹 서비스 상호 작용</span><span class="sxs-lookup"><span data-stu-id="e12e7-103">Groups services interactions</span></span>

<span data-ttu-id="e12e7-104">Microsoft 365 그룹은 Microsoft 365 플랫폼 내의 다양 한 서비스 및 작업에 대 한 공통 패브릭을 제공 하 여 최종 사용자에 게 연결 된 환경을 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="e12e7-105">핵심은 Microsoft 365 그룹이 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="e12e7-106">구성원 자격 (Azure AD)을 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="e12e7-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="e12e7-107">메시징과 대화를 수행할 장소 (Exchange 사서함, Microsoft 팀, Yammer)</span><span class="sxs-lookup"><span data-stu-id="e12e7-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="e12e7-108">파일을 저장할 위치 (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="e12e7-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="e12e7-109">일정 예약 (Exchange)</span><span class="sxs-lookup"><span data-stu-id="e12e7-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="e12e7-110">메모를 캡처하기 위한 전자 필기장 (OneNote)</span><span class="sxs-lookup"><span data-stu-id="e12e7-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="e12e7-111">그룹을 만들 때 여러 다른 리소스가 프로 비전 되 고 서비스에서 처음으로 액세스 하기 전까지 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="e12e7-112">그룹 작업을 관리 하는 보드 (Planner)</span><span class="sxs-lookup"><span data-stu-id="e12e7-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="e12e7-113">보고를 위한 작업 영역 (Power BI)</span><span class="sxs-lookup"><span data-stu-id="e12e7-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="e12e7-114">공유 비디오 영역 (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="e12e7-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="e12e7-115">공유 폼 영역 (폼)</span><span class="sxs-lookup"><span data-stu-id="e12e7-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="e12e7-116">Microsoft 365에서 다른 서비스는 Microsoft 365 그룹과 상호 작용 하 여 그룹 구성원에 게 추가 기능과 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="e12e7-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-117">Examples of this include:</span></span>

- <span data-ttu-id="e12e7-118">앱 용 파워 앱</span><span class="sxs-lookup"><span data-stu-id="e12e7-118">Power Apps for apps</span></span>
- <span data-ttu-id="e12e7-119">워크플로의 전원 자동화</span><span class="sxs-lookup"><span data-stu-id="e12e7-119">Power Automate for workflows</span></span>
- <span data-ttu-id="e12e7-120">웹에 있는 프로젝트 및 폭포 기반 프로젝트 관리 로드맵</span><span class="sxs-lookup"><span data-stu-id="e12e7-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="e12e7-121">채널 기반 대화 팀</span><span class="sxs-lookup"><span data-stu-id="e12e7-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="e12e7-122">관심 커뮤니티를 위한 Yammer</span><span class="sxs-lookup"><span data-stu-id="e12e7-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="e12e7-123">그룹과의 사용자 상호 작용</span><span class="sxs-lookup"><span data-stu-id="e12e7-123">User interactions with groups</span></span>

<span data-ttu-id="e12e7-124">Microsoft 365 그룹은 관리자와 최종 사용자가 모두 다양 한 인터페이스에서 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="e12e7-125">관리 환경</span><span class="sxs-lookup"><span data-stu-id="e12e7-125">Administrative experiences</span></span>

<span data-ttu-id="e12e7-126">관리자는 Graph API와 상호 작용 하는 사용자 지정 구성 된 앱 뿐 아니라 스크립팅을 지 원하는 여러 작업 관리 센터, 명령줄 인터페이스에서 Microsoft 365 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="e12e7-127">단, yammer 웹 인터페이스 내에서 만들어야 하는 Yammer 그룹은 여기에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="e12e7-128">**관련 설정**</span><span class="sxs-lookup"><span data-stu-id="e12e7-128">**Related settings**</span></span>

<span data-ttu-id="e12e7-129">그룹 설정을 관리할 수 있는 다양 한 관리 인터페이스에 걸쳐 몇 가지 중복 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="e12e7-130">**Microsoft 365 관리 센터**</span><span class="sxs-lookup"><span data-stu-id="e12e7-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="e12e7-131">Microsoft 365 관리 센터에서 그룹에 대 한 게스트 액세스는 기본적으로 사용 하도록 설정 되며 소유자가 게스트를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="e12e7-132">이 관리 센터에서 그룹에 대해 사용할 수 있는 조직 수준 컨트롤이 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="e12e7-133">**Azure AD 관리 센터**</span><span class="sxs-lookup"><span data-stu-id="e12e7-133">**Azure AD admin center**</span></span>

<span data-ttu-id="e12e7-134">Azure AD 관리 센터는 사용자가 Azure 포털에서 그룹을 만들거나 소유자를 할당 하 고 만료 및 이름 지정 정책 설정을 지정할 수 있는지 여부에 대 한 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="e12e7-135">관리 센터는 또한 비 소유자가 게스트를 초대할 수 있는지 여부를 제한 하는 기능과 같이 Microsoft 365 관리 센터의 범위를 벗어나는 여러 가지 게스트 초대 제어 조치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="e12e7-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="e12e7-136">**SharePoint**</span></span>

<span data-ttu-id="e12e7-137">SharePoint 사이트는 소유자, 구성원 및 방문자 보안 그룹을 사용 하 여 작성 되며 처음 두 개는 해당 Microsoft 365 그룹을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="e12e7-138">일반적으로 SharePoint Online 사이트의 구성원 자격은 연결 된 Microsoft 365 그룹에 의해 관리 되지만 양방향 관계는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="e12e7-139">Microsoft 365 그룹 수준의 멤버 자격에 대 한 변경 내용은 SharePoint에 반영 되지만 SharePoint 그룹에서 구성원 자격이 변경 되는 경우에는 Microsoft 365 그룹에 반영 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="e12e7-140">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="e12e7-140">User experiences</span></span>

<span data-ttu-id="e12e7-141">최종 사용자는 Microsoft 365 내의 몇 가지 서비스에서 그룹을 만들 수 있으며,이 경우에는 그룹과만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="e12e7-142">최종 사용자가 그룹을 만들 수 있도록 하는 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="e12e7-143">웹용 Outlook Planner Project for SharePoint Stream Microsoft 팀별로 Yammer</span><span class="sxs-lookup"><span data-stu-id="e12e7-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="e12e7-144">**그룹 만들기 제한**</span><span class="sxs-lookup"><span data-stu-id="e12e7-144">**Restriction of group creation**</span></span>

<span data-ttu-id="e12e7-145">팀의 sprawl을 제어 하는 일반적인 방법은 사용자를 만들 수 있는 사람을 제한 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="e12e7-146">이 작업은 그룹 만들기를 제한 해야만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="e12e7-147">이렇게 하면 최종 사용자에 게 필요할 수 있는 다른 서비스에서 그룹을 만드는 기능이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="e12e7-148">Microsoft 365 그룹에서는 일부 앱 이나 서비스에서 그룹을 만드는 것을 허용 하는 동시에 해당 사용자를 제한 하는 기능을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="e12e7-149">앱과 서비스에 따라 그룹 만들기 제한의 환경은 다양 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="e12e7-150">앱 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="e12e7-150">App or service</span></span>|<span data-ttu-id="e12e7-151">환경</span><span class="sxs-lookup"><span data-stu-id="e12e7-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="e12e7-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="e12e7-152">Outlook</span></span>|<span data-ttu-id="e12e7-153">**새 그룹** 옵션이 사용자 페이지의 새로 만들기 메뉴에서 제거 됨</span><span class="sxs-lookup"><span data-stu-id="e12e7-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="e12e7-154">Planner</span><span class="sxs-lookup"><span data-stu-id="e12e7-154">Planner</span></span>|<span data-ttu-id="e12e7-155">**새 계획** 그룹 만들기가 해제 되었으며 계획을 기존 그룹에 추가 하는 것을 제공 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="e12e7-156">웹 및 로드맵 용 프로젝트</span><span class="sxs-lookup"><span data-stu-id="e12e7-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="e12e7-157">**Create group** menu 그룹 만들기가 제한 되 고 기존 그룹을 사용 하는 것을 제안 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="e12e7-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e12e7-158">SharePoint</span></span>|<span data-ttu-id="e12e7-159">아직 그룹에 연결 되어 있지 않은 팀 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="e12e7-160">Stream</span><span class="sxs-lookup"><span data-stu-id="e12e7-160">Stream</span></span>|<span data-ttu-id="e12e7-161">**그룹** 옵션이 **만들기 메뉴**아래에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="e12e7-162">Teams</span><span class="sxs-lookup"><span data-stu-id="e12e7-162">Teams</span></span>|<span data-ttu-id="e12e7-163">사용자가 새 그룹을 사용 하 여 팀을 만들 수는 없지만 기존 그룹을 활용 하는 팀을 만들 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="e12e7-164">**팀** 구성 단추가 **그룹에서 팀 만들기**단추로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="e12e7-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="e12e7-165">Yammer</span></span>|<span data-ttu-id="e12e7-166">**그룹 만들기** 옵션은 주 그룹/커뮤니티 탐색에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="e12e7-167">그룹과의 서비스 상호 작용</span><span class="sxs-lookup"><span data-stu-id="e12e7-167">Services interactions with groups</span></span>

<span data-ttu-id="e12e7-168">다양 한 유형의 그룹에 대 한 자세한 내용은 Microsoft 365 포스터의 그룹, 이러한 구성 및 관리 방법, 그리고 몇 가지 거 버 넌 스 권장 사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e12e7-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="e12e7-169">[![그룹 인포그래픽용 축소판 이미지](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="e12e7-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="e12e7-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="e12e7-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="e12e7-171">다음 표에는 다양 한 서비스와의 Microsoft 365 그룹 상호 작용에 대 한 개요가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="e12e7-172">제품</span><span class="sxs-lookup"><span data-stu-id="e12e7-172">Product</span></span>|<span data-ttu-id="e12e7-173">기능</span><span class="sxs-lookup"><span data-stu-id="e12e7-173">Features</span></span>|<span data-ttu-id="e12e7-174">서비스</span><span class="sxs-lookup"><span data-stu-id="e12e7-174">Does the service</span></span><br><span data-ttu-id="e12e7-175">그룹 없이 존재 하나요?</span><span class="sxs-lookup"><span data-stu-id="e12e7-175">exist without a group?</span></span>|<span data-ttu-id="e12e7-176">서비스</span><span class="sxs-lookup"><span data-stu-id="e12e7-176">Can the service</span></span><br><span data-ttu-id="e12e7-177">그룹을 만드시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="e12e7-177">create a group?</span></span>|<span data-ttu-id="e12e7-178">삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-178">Does deleting the</span></span><br><span data-ttu-id="e12e7-179">인스턴스 그룹을 삭제 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="e12e7-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="e12e7-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="e12e7-180">Azure AD</span></span>|<span data-ttu-id="e12e7-181">멤버 자격, 그룹 컨트롤, 게스트</span><span class="sxs-lookup"><span data-stu-id="e12e7-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="e12e7-182">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-182">Yes</span></span>|<span data-ttu-id="e12e7-183">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-183">Yes</span></span>|<span data-ttu-id="e12e7-184">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-184">Yes</span></span>|
|<span data-ttu-id="e12e7-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="e12e7-185">Exchange</span></span>|<span data-ttu-id="e12e7-186">일정, 사서함</span><span class="sxs-lookup"><span data-stu-id="e12e7-186">Calendar, mailbox</span></span>|<span data-ttu-id="e12e7-187">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-187">Yes</span></span>|<span data-ttu-id="e12e7-188">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-188">Yes</span></span>|<span data-ttu-id="e12e7-189">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-189">Yes</span></span>|
|<span data-ttu-id="e12e7-190">Forms</span><span class="sxs-lookup"><span data-stu-id="e12e7-190">Forms</span></span>|<span data-ttu-id="e12e7-191">형식</span><span class="sxs-lookup"><span data-stu-id="e12e7-191">Form</span></span>|<span data-ttu-id="e12e7-192">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-192">Yes</span></span>|<span data-ttu-id="e12e7-193">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-193">No</span></span>|<span data-ttu-id="e12e7-194">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-194">No</span></span>|
|<span data-ttu-id="e12e7-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="e12e7-195">OneNote</span></span>|<span data-ttu-id="e12e7-196">노트북과</span><span class="sxs-lookup"><span data-stu-id="e12e7-196">Notebook</span></span>|<span data-ttu-id="e12e7-197">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-197">Yes</span></span>|<span data-ttu-id="e12e7-198">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-198">No</span></span>|<span data-ttu-id="e12e7-199">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-199">No</span></span>|
|<span data-ttu-id="e12e7-200">Planner</span><span class="sxs-lookup"><span data-stu-id="e12e7-200">Planner</span></span>|<span data-ttu-id="e12e7-201">작업 보드</span><span class="sxs-lookup"><span data-stu-id="e12e7-201">Task board</span></span>|<span data-ttu-id="e12e7-202">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-202">No</span></span>|<span data-ttu-id="e12e7-203">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-203">Yes</span></span>|<span data-ttu-id="e12e7-204">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-204">Yes</span></span>|
|<span data-ttu-id="e12e7-205">Power Apps 앱</span><span class="sxs-lookup"><span data-stu-id="e12e7-205">Power Apps app</span></span>|<span data-ttu-id="e12e7-206">앱</span><span class="sxs-lookup"><span data-stu-id="e12e7-206">App</span></span>|<span data-ttu-id="e12e7-207">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-207">Yes</span></span>|<span data-ttu-id="e12e7-208">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-208">No</span></span>|<span data-ttu-id="e12e7-209">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-209">No</span></span>|
|<span data-ttu-id="e12e7-210">전원 자동화</span><span class="sxs-lookup"><span data-stu-id="e12e7-210">Power Automate</span></span>|<span data-ttu-id="e12e7-211">워크플로</span><span class="sxs-lookup"><span data-stu-id="e12e7-211">Workflow</span></span>|<span data-ttu-id="e12e7-212">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-212">Yes</span></span>|<span data-ttu-id="e12e7-213">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-213">No</span></span>|<span data-ttu-id="e12e7-214">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-214">No</span></span>|
|<span data-ttu-id="e12e7-215">Power BI (클래식)</span><span class="sxs-lookup"><span data-stu-id="e12e7-215">Power BI (classic)</span></span>|<span data-ttu-id="e12e7-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="e12e7-216">Workspace</span></span>|<span data-ttu-id="e12e7-217">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-217">No</span></span>|<span data-ttu-id="e12e7-218">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-218">Yes</span></span>|<span data-ttu-id="e12e7-219">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-219">Yes</span></span>|
|<span data-ttu-id="e12e7-220">Power BI (신규)</span><span class="sxs-lookup"><span data-stu-id="e12e7-220">Power BI (new)</span></span>|<span data-ttu-id="e12e7-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="e12e7-221">Workspace</span></span>|<span data-ttu-id="e12e7-222">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-222">Yes</span></span>|<span data-ttu-id="e12e7-223">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-223">No</span></span>|<span data-ttu-id="e12e7-224">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-224">Yes</span></span>|
|<span data-ttu-id="e12e7-225">웹용 Project</span><span class="sxs-lookup"><span data-stu-id="e12e7-225">Project for the web</span></span>|<span data-ttu-id="e12e7-226">프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="e12e7-226">Project plan</span></span>|<span data-ttu-id="e12e7-227">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-227">Yes</span></span>|<span data-ttu-id="e12e7-228">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-228">Yes</span></span>|<span data-ttu-id="e12e7-229">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-229">No</span></span>|
|<span data-ttu-id="e12e7-230">로드맵</span><span class="sxs-lookup"><span data-stu-id="e12e7-230">Roadmap</span></span>|<span data-ttu-id="e12e7-231">로드맵</span><span class="sxs-lookup"><span data-stu-id="e12e7-231">Roadmap</span></span>|<span data-ttu-id="e12e7-232">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-232">Yes</span></span>|<span data-ttu-id="e12e7-233">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-233">Yes</span></span>|<span data-ttu-id="e12e7-234">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-234">No</span></span>|
|<span data-ttu-id="e12e7-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e12e7-235">SharePoint</span></span>|<span data-ttu-id="e12e7-236">사이트</span><span class="sxs-lookup"><span data-stu-id="e12e7-236">Site</span></span>|<span data-ttu-id="e12e7-237">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-237">Yes</span></span>|<span data-ttu-id="e12e7-238">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-238">Yes</span></span>|<span data-ttu-id="e12e7-239">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-239">Yes</span></span>|
|<span data-ttu-id="e12e7-240">Stream</span><span class="sxs-lookup"><span data-stu-id="e12e7-240">Stream</span></span>|<span data-ttu-id="e12e7-241">채널, 비디오</span><span class="sxs-lookup"><span data-stu-id="e12e7-241">Channel, video</span></span>|<span data-ttu-id="e12e7-242">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-242">Yes</span></span>|<span data-ttu-id="e12e7-243">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-243">Yes</span></span>|<span data-ttu-id="e12e7-244">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-244">Yes</span></span>|
|<span data-ttu-id="e12e7-245">Teams</span><span class="sxs-lookup"><span data-stu-id="e12e7-245">Teams</span></span>|<span data-ttu-id="e12e7-246">팀</span><span class="sxs-lookup"><span data-stu-id="e12e7-246">Team</span></span>|<span data-ttu-id="e12e7-247">아니요</span><span class="sxs-lookup"><span data-stu-id="e12e7-247">No</span></span>|<span data-ttu-id="e12e7-248">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-248">Yes</span></span>|<span data-ttu-id="e12e7-249">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-249">Yes</span></span>|
|<span data-ttu-id="e12e7-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="e12e7-250">Yammer</span></span>|<span data-ttu-id="e12e7-251">그룹</span><span class="sxs-lookup"><span data-stu-id="e12e7-251">Group</span></span>|<span data-ttu-id="e12e7-252">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-252">Yes</span></span>|<span data-ttu-id="e12e7-253">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-253">Yes</span></span>|<span data-ttu-id="e12e7-254">예</span><span class="sxs-lookup"><span data-stu-id="e12e7-254">Yes</span></span>|

<span data-ttu-id="e12e7-255">위의 표에는 Microsoft 365 서비스와의 그룹 상호 작용에 대 한 간략 한 개요가 나와 있지만 이해 해야 하는 nuances 및 복잡 한 몇 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="e12e7-256">다음 섹션에서는 특정 작업 및 그룹과의 상호 작용에 대 한 자세한 내용을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="e12e7-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="e12e7-257">Azure AD</span></span>

<span data-ttu-id="e12e7-258">Azure AD는 Microsoft 365에서 기본 id 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="e12e7-259">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-260">그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="e12e7-260">Group membership</span></span>
- <span data-ttu-id="e12e7-261">명명 정책</span><span class="sxs-lookup"><span data-stu-id="e12e7-261">Naming policy</span></span>
- <span data-ttu-id="e12e7-262">만료 정책</span><span class="sxs-lookup"><span data-stu-id="e12e7-262">Expiration policy</span></span>
- <span data-ttu-id="e12e7-263">게스트</span><span class="sxs-lookup"><span data-stu-id="e12e7-263">Guests</span></span>
- <span data-ttu-id="e12e7-264">그룹 만들기 제한</span><span class="sxs-lookup"><span data-stu-id="e12e7-264">Restriction of Group creation</span></span>

<span data-ttu-id="e12e7-265">**Azure AD에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="e12e7-266">예, Microsoft 365 그룹은 관리 웹 포털, PowerShell 또는 Graph API를 통해 Azure AD에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="e12e7-267">**Azure AD가 그룹 없이 존재 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="e12e7-268">예, Azure AD는 Microsoft 365 그룹과 관계가 없는 많은 서비스를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="e12e7-269">각 Microsoft 365 그룹은 Azure AD에서 개체로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="e12e7-270">**그룹 당 Azure AD의 인스턴스가 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="e12e7-271">아니요, Azure AD 인스턴스가 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="e12e7-272">**Azure AD는 여러 그룹과 연결 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="e12e7-273">예, Azure AD는 그룹 멤버 자격 서비스를 제공 하는 기본 플랫폼 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="e12e7-274">**Azure AD와 그룹 변경의 연결 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-275">아니요, Azure AD는 그룹이 있는 기본 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="e12e7-276">**인스턴스를 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="e12e7-277">Azure AD에서 그룹을 삭제 하면 관련 그룹 관련 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="e12e7-278">Teams</span><span class="sxs-lookup"><span data-stu-id="e12e7-278">Teams</span></span>

<span data-ttu-id="e12e7-279">팀은 다양 한 Microsoft 및 타사 서비스와 상호 작용 하기 위한 단일 인터페이스를 제공 하 여 공동 작업의 향상을 목표로 하는 채팅 중심 작업 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="e12e7-280">기본적으로 팀을 만들 때 Microsoft 365 그룹과 연결 된 사서함 및 일정은 Exchange의 전체 주소 목록 및 Outlook에서 모두 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="e12e7-281">사용자가 같은 Microsoft 365 그룹에서 Outlook과 팀을 모두 사용 하려는 경우 관리자가 수동으로이를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="e12e7-282">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-283">Conversations</span><span class="sxs-lookup"><span data-stu-id="e12e7-283">Conversations</span></span>
- <span data-ttu-id="e12e7-284">채널 & 탭</span><span class="sxs-lookup"><span data-stu-id="e12e7-284">Channels & tabs</span></span>
- <span data-ttu-id="e12e7-285">Meetings</span><span class="sxs-lookup"><span data-stu-id="e12e7-285">Meetings</span></span>

<span data-ttu-id="e12e7-286">**팀에서 그룹을 만들 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="e12e7-287">예, 새 팀을 만들면 새 Microsoft 365 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="e12e7-288">현재 없는 기존 그룹에 대 한 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="e12e7-289">**그룹을 사용 하지 않고 팀이 존재 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="e12e7-290">아니요, 그룹 없이 팀이 존재 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="e12e7-291">**그룹당 여러 팀이 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="e12e7-292">아니요, 팀과 그룹의 관계는 1:1입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="e12e7-293">**팀이 여러 그룹과 연결 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-294">아니요, 팀 자체는 단일 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="e12e7-295">**팀이 그룹 변경에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-296">아니요, 팀은 원래 연결 되었던 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="e12e7-297">**팀을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="e12e7-298">예, Microsoft 팀에서 팀을 삭제 하면 그룹, 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="e12e7-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="e12e7-299">Exchange</span></span>

<span data-ttu-id="e12e7-300">Exchange Online은 메시징, 일정, 연락처 및 관련 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="e12e7-301">그룹 컨텍스트에서는 전체 서비스 인스턴스와는 달리 단일 리소스가 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="e12e7-302">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-303">사서함 및 일정</span><span class="sxs-lookup"><span data-stu-id="e12e7-303">Mailbox and calendar</span></span>
- <span data-ttu-id="e12e7-304">모든 그룹 구성원에 게 전자 메일 보내기 기능</span><span class="sxs-lookup"><span data-stu-id="e12e7-304">Ability to email all Group members</span></span>
- <span data-ttu-id="e12e7-305">EDiscovery 목적에 대 한 팀 채널 대화 저장소, Planner 설명</span><span class="sxs-lookup"><span data-stu-id="e12e7-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="e12e7-306">**Exchange에서 그룹을 만들 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="e12e7-307">예, Exchange Online 관리 센터에서 뿐만 아니라 Outlook 에서도 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="e12e7-308">Exchange 메일 그룹을 Microsoft 365 그룹으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="e12e7-309">**그룹 없이 Exchange가 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="e12e7-310">예, Exchange Online은 그룹 연결 없이 공유 사서함 및 일정을 비롯 한 다양 한 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="e12e7-311">**그룹 당 Exchange 사서함 또는 일정의 인스턴스가 여러 개 있을 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="e12e7-312">아니요, 그룹에 대해 하나의 Exchange Online 사서함과 일정만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="e12e7-313">**Exchange 사서함과 일정을 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-314">아니요, 사서함과 일정의 범위는 그룹에 1:1 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="e12e7-315">다른 사용자 또는 그룹과 사서함을 공유할 수는 있지만 어떤 형태의 서비스 연결도 설정 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="e12e7-316">**Exchange 사서함 또는 일정 그룹과 그룹의 연결을 변경할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-317">아니요, 사서함과 일정을 다른 그룹으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="e12e7-318">그러나 Outlook 내에서 또는 타사 도구를 사용 하 여 사서함 간에 콘텐츠를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="e12e7-319">**사서함을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="e12e7-320">예, Exchange에서 사서함을 삭제 하면 그룹 및 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="e12e7-321">Forms</span><span class="sxs-lookup"><span data-stu-id="e12e7-321">Forms</span></span>

<span data-ttu-id="e12e7-322">양식은 웹 기반 설문 조사 및 퀴즈를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="e12e7-323">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="e12e7-324">양식의 소유권</span><span class="sxs-lookup"><span data-stu-id="e12e7-324">Ownership of forms</span></span>

<span data-ttu-id="e12e7-325">**폼에서 그룹을 만들 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="e12e7-326">아니요, 폼에서 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="e12e7-327">**그룹을 사용 하지 않고 양식이 존재 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="e12e7-328">예, 설문 조사 및 퀴즈는 최종 사용자의 계정에 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="e12e7-329">**그룹당 여러 양식을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="e12e7-330">예, 그룹에 연결 된 양식이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="e12e7-331">**양식은 여러 그룹과 연결 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-332">아니요, 양식을 단일 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="e12e7-333">**양식의 그룹과 연결을 변경할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-334">아니요, 양식이 그룹 (바로 아래에서 만들어짐 또는 개인이 보낸 소유권)에 연결 된 경우 다른 그룹으로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="e12e7-335">**양식을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="e12e7-336">아니요, 양식 인터페이스에서 그룹을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="e12e7-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="e12e7-337">OneNote</span></span>

<span data-ttu-id="e12e7-338">OneNote는 디지털 전자 필기장 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="e12e7-339">그룹을 사용 하 여 만든 OneNote 전자 필기장은 그룹 연결 서비스가 아닌 연결 된 SharePoint 사이트의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="e12e7-340">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="e12e7-341">공유 전자 필기장 (그룹 연결 SharePoint 라이브러리에 저장)</span><span class="sxs-lookup"><span data-stu-id="e12e7-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="e12e7-342">**OneNote에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="e12e7-343">아니요, OneNote 응용 프로그램에서 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="e12e7-344">**그룹을 사용 하지 않고 OneNote 전자 필기장이 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="e12e7-345">예, OneDrive 또는 다른 공유 위치에서 직접 전자 필기장을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="e12e7-346">**그룹 마다 OneNote 전자 필기장이 여러 개 있을 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="e12e7-347">예, 기본적으로 전자 필기장이 만들어지며 다른 사용자는 추가할 수 있지만 그룹 연결 서비스에서 OneNote로 연결 하는 링크는 항상 기본 전자 필기장으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="e12e7-348">**OneNote 전자 필기장을 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-349">아니요, 전자 필기장이 그룹 연결 SharePoint 사이트 라이브러리에 저장 되 고 다양 한 인터페이스에서 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="e12e7-350">그러나 다른 그룹과 공유 하는 것과 같은 방법으로 사용자와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="e12e7-351">**전자 필기장에서 그룹과의 연결이 변경 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-352">아니요, 전자 필기장 자체가 그룹과 연결 되 고 다른 그룹 연결 서비스에서 직접 액세스할 수 있지만 콘텐츠를 OneNote 응용 프로그램 내에서 다른 전자 필기장으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="e12e7-353">**전자 필기장을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="e12e7-354">아니오, OneNote 전자 필기장을 삭제 한 경우 일부 그룹 관련 서비스에 끊어진 링크가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="e12e7-355">Planner</span><span class="sxs-lookup"><span data-stu-id="e12e7-355">Planner</span></span>

<span data-ttu-id="e12e7-356">Planner는 경량 그룹 작업 관리 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="e12e7-357">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="e12e7-358">그룹 작업 관리용 보드</span><span class="sxs-lookup"><span data-stu-id="e12e7-358">Board for managing group tasks</span></span>

<span data-ttu-id="e12e7-359">**Planner에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="e12e7-360">예, 계획을 작성 하면 새 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="e12e7-361">**그룹 없이 Planner 보드가 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="e12e7-362">아니요, 계획을 그룹에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="e12e7-363">**그룹당 여러 요금제를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="e12e7-364">예, 그룹당 여러 요금제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="e12e7-365">**계획을 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-366">아니요, 계획은 액세스를 결정 하기 위해 그룹 구성원에만 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="e12e7-367">**그룹 변경에 대 한 계획의 연결 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-368">아니요, 계획을 복사 하면 새 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="e12e7-369">다른 응용 프로그램에서 만든 그룹은 사용자를 위해 자동으로 Planner에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="e12e7-370">초기에 보드에 액세스 하려면 Outlook과 같은 다른 그룹 기반 인터페이스에서 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="e12e7-371">**요금제를 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="e12e7-372">예, 계획을 삭제 하면 그룹 및 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="e12e7-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="e12e7-373">Power Apps</span></span>

<span data-ttu-id="e12e7-374">Power Apps는 코드 없이 앱 개발을 위한 캔버스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="e12e7-375">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-376">앱을 실행 및 수정할 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="e12e7-377">**Power Apps에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="e12e7-378">아니요, Power Apps에서 Microsoft 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="e12e7-379">**그룹 없이 Power Apps가 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="e12e7-380">예, 앱을 Power Apps 내에서 만들고 공유 또는 게시할 때까지 작성자 계정 내에 상주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="e12e7-381">**그룹당 여러 개의 앱을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="e12e7-382">예, 그룹과 공유 되는 앱이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="e12e7-383">**앱이 여러 그룹과 연결 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-384">예, 앱을 여러 그룹으로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="e12e7-385">**그룹 변경에 대 한 앱의 연결 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-386">예, 전원 앱과 Microsoft 365 그룹 간의 연결이 공유 전용 이므로이 앱은 여전히 작성자와 함께 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e12e7-387">[앱을 공유 하려면 먼저 그룹의 보안을 설정 해야 합니다](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="e12e7-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="e12e7-388">**앱을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="e12e7-389">아니요, 앱이 공유 하는 것이 아닌 다른 그룹에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="e12e7-390">전원 자동화</span><span class="sxs-lookup"><span data-stu-id="e12e7-390">Power Automate</span></span>

<span data-ttu-id="e12e7-391">전원 자동화 (이전의 Microsoft Flow)는 워크플로 및 자동화 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="e12e7-392">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="e12e7-393">워크플로를 실행 하 고 수정할 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="e12e7-394">**전원을 자동화할 때 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="e12e7-395">아니요, 전원 자동화는 연결 된 컨텍스트에서 Microsoft 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="e12e7-396">그러나 Azure AD 보안 그룹을 만들거나 Microsoft 365 그룹의 구성원을 업데이트 하는 등의 다양 한 작업을 수행 하는 흐름을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="e12e7-397">**그룹 없이 어떤 흐름이 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="e12e7-398">예, 전원 자동화 내에서 흐름을 만들 수 있으며 공유 또는 게시할 때까지 작성자 계정 내에 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="e12e7-399">**그룹당 여러 흐름을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="e12e7-400">예, 그룹과 여러 개의 흐름을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="e12e7-401">**흐름을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-402">예, 흐름을 여러 그룹으로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="e12e7-403">**그룹 변경에 대 한 흐름의 연결 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-404">예, 전원 자동화와 Microsoft 365 그룹 간의 연결이 공유 전용 이므로 해당 흐름이 여전히 작성자와 함께 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="e12e7-405">**흐름을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="e12e7-406">No (예를 들어, 전원 앱과 마찬가지로, 흐름은 공유 되는 것이 아닌 다른 그룹에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="e12e7-407">Power BI (클래식)</span><span class="sxs-lookup"><span data-stu-id="e12e7-407">Power BI (classic)</span></span>

<span data-ttu-id="e12e7-408">Power BI는 대화형 데이터 기반 대시보드 및 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="e12e7-409">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="e12e7-410">데이터 보고</span><span class="sxs-lookup"><span data-stu-id="e12e7-410">Data reporting</span></span>

<span data-ttu-id="e12e7-411">**Power BI에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="e12e7-412">예, 클래식 작업 영역을 만들면 Microsoft 365 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="e12e7-413">**Power BI 클래식 작업 영역이 그룹 없이 존재 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="e12e7-414">아니요, [POWER BI의 클래식 작업 영역을 그룹에 연결 해야 합니다](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="e12e7-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="e12e7-415">**그룹당 여러 Power BI 작업 영역을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="e12e7-416">아니요, 클래식 작업 영역과 그룹 간의 관계는 1:1입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="e12e7-417">**작업 영역을 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-418">기술적으로 아니요, 클래식 작업 영역이 그룹을 사용 하 여 만들어지므로 사용자 및 보안 그룹을 사용 하 여 그룹 외부에서 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="e12e7-419">**그룹을 변경할 때 작업 영역의 연결이 가능 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="e12e7-420">아니요, 클래식 작업 영역 자체는 그룹에 연결 되지만, 콘텐츠는 한 작업 영역에서 Power BI 인터페이스 내에 있거나 로컬로 콘텐츠를 내보내는 방식으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="e12e7-421">**작업 영역을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="e12e7-422">예, Power BI에서 작업 영역을 삭제 하면 그룹 및 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="e12e7-423">Power BI (신규)</span><span class="sxs-lookup"><span data-stu-id="e12e7-423">Power BI (new)</span></span>

<span data-ttu-id="e12e7-424">Power BI는 대화형 데이터 기반 대시보드 및 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="e12e7-425">Power BI에서 새 작업 영역을 만들 때 Microsoft 365 그룹을 만들지 않으면 다른 방법으로 그룹을 만들면 Power BI에서 클래식이 아닌 새 작업 영역이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="e12e7-426">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="e12e7-427">데이터 보고</span><span class="sxs-lookup"><span data-stu-id="e12e7-427">Data reporting</span></span>

<span data-ttu-id="e12e7-428">**Power BI에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="e12e7-429">아니요, 새 Power BI 인터페이스에서 Microsoft 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="e12e7-430">**새 Power BI 작업 영역이 그룹 없이 존재 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="e12e7-431">예, Power BI에서 만든 보고서 및 작업 환경이 Microsoft 365 그룹과 연결 되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="e12e7-432">**그룹당 여러 개의 작업 영역을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="e12e7-433">예, [POWER BI에서 만든 여러 작업 환경이 단일 그룹과 공유 될 수 있습니다](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="e12e7-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="e12e7-434">**작업 영역을 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-435">아니요, Power BI에서 만든 작업 영역은 단일 그룹과 연결 될 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="e12e7-436">**그룹을 변경할 때 작업 영역의 연결이 가능 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="e12e7-437">그렇기도 하고 그렇지 않기도 하고.</span><span class="sxs-lookup"><span data-stu-id="e12e7-437">Yes and no.</span></span> <span data-ttu-id="e12e7-438">Power BI에서 만든 작업 영역은 한 번에 하나의 그룹에만 연결할 수 있지만 언제 든 지 연결을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="e12e7-439">그룹에 의해 Power BI에서 만들어진 작업 영역은 해당 그룹에 영구적으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="e12e7-440">**작업 영역을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="e12e7-441">예, Power BI에서 작업 영역을 삭제 하면 그룹 및 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="e12e7-442">웹용 Project</span><span class="sxs-lookup"><span data-stu-id="e12e7-442">Project for the web</span></span>

<span data-ttu-id="e12e7-443">웹용 project에서는 프로젝트 계획, Gantt 차트 및 로드맵을 만드는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="e12e7-444">주요 기능은 그룹에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-444">Key features provided to groups.</span></span>

- <span data-ttu-id="e12e7-445">프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="e12e7-445">Project plans</span></span>

<span data-ttu-id="e12e7-446">**웹 프로젝트에서 그룹 만들기 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="e12e7-447">예, 웹의 Project에서 직접 새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="e12e7-448">**그룹 없는 프로젝트 유무**</span><span class="sxs-lookup"><span data-stu-id="e12e7-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="e12e7-449">예, Microsoft 365 그룹과 연결 하지 않고도 프로젝트가 존재할 수 있지만 작업 할당에는 그룹 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="e12e7-450">**그룹당 여러 프로젝트를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="e12e7-451">예, 여러 프로젝트를 단일 그룹으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="e12e7-452">**프로젝트를 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-453">아니요, 프로젝트를 단일 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="e12e7-454">**프로젝트와 그룹의 연결을 변경할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-455">아니요, 그룹에 대 한 연결이 설정 된 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="e12e7-456">**프로젝트를 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="e12e7-457">아니요, 웹에서 프로젝트를 삭제 해도 해당 그룹은 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="e12e7-458">로드맵</span><span class="sxs-lookup"><span data-stu-id="e12e7-458">Roadmap</span></span>

<span data-ttu-id="e12e7-459">로드맵을 사용 하 여 웹 및 Project Online 프로젝트와 project 로드맵을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="e12e7-460">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-461">Project 로드맵</span><span class="sxs-lookup"><span data-stu-id="e12e7-461">Project roadmaps</span></span>

<span data-ttu-id="e12e7-462">**로드맵에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="e12e7-463">예, 로드맵에 직접 새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="e12e7-464">**로드맵은 그룹 없이 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="e12e7-465">예, 로드맵는 Microsoft 365 그룹과 연결 되지 않고 존재할 수 있지만 로드맵을 공유 하려면 그룹 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="e12e7-466">**그룹당 여러 로드맵 수 있는지 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="e12e7-467">예, 여러 로드맵를 단일 그룹에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="e12e7-468">**로드맵을 여러 그룹에 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-469">아니요, 로드맵을 단일 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="e12e7-470">**그룹 변경에 대 한 로드맵 연결 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="e12e7-471">아니요, 그룹에 대 한 연결이 설정 된 후에는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="e12e7-472">**로드맵을 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="e12e7-473">아니요, 로드맵을 삭제 해도 그룹은 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="e12e7-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e12e7-474">SharePoint</span></span>

<span data-ttu-id="e12e7-475">SharePoint는 다양 한 Microsoft 365 서비스에 대 한 저장소 서비스를 제공 하는 웹 기반 콘텐츠 관리 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="e12e7-476">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-477">문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e12e7-477">Document library</span></span>
- <span data-ttu-id="e12e7-478">OneNote 전자 필기장 저장용 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e12e7-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="e12e7-479">팀의 위 키 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="e12e7-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="e12e7-480">**SharePoint에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="e12e7-481">예, SharePoint에서 팀 사이트를 만들면 기본적으로 Microsoft 365 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="e12e7-482">또한 그룹을 만들고 원하는 경우 기존 사이트의 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="e12e7-483">**SharePoint 사이트가 그룹 없이 존재 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="e12e7-484">예, SharePoint는 통신 및 허브 사이트와 같은 여러 그룹에 연결 되지 않은 서비스와 사이트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="e12e7-485">**그룹당 여러 개의 사이트를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="e12e7-486">아니요, 한 그룹만 하나의 사이트만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="e12e7-487">팀의 비공개 채널은 해당 그룹과 연결 되지 않은 사이트를 추가로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="e12e7-488">**사이트가 여러 그룹과 연결 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-489">기술적으로는 없지만 그룹을 사용 하 여 사이트를 만드는 경우에는 콘텐츠를 다른 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="e12e7-490">**사이트와 그룹의 연결을 변경할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="e12e7-491">아니요, 사이트 자체는 그룹에 연결 되지만 콘텐츠를 로컬로 내보내거나 타사 도구를 사용 하 여 SharePoint 인터페이스 내에서 사이트 간에 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="e12e7-492">**사이트를 삭제 하 여 그룹을 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="e12e7-493">예, SharePoint에서 사이트를 삭제 하면 그룹 및 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="e12e7-494">Stream</span><span class="sxs-lookup"><span data-stu-id="e12e7-494">Stream</span></span>

<span data-ttu-id="e12e7-495">Microsoft Stream은 비디오 호스팅 및 공유 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="e12e7-496">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-497">비디오 저장</span><span class="sxs-lookup"><span data-stu-id="e12e7-497">Video storage</span></span>
- <span data-ttu-id="e12e7-498">팀 모임 녹음</span><span class="sxs-lookup"><span data-stu-id="e12e7-498">Teams meeting recording</span></span>
- <span data-ttu-id="e12e7-499">비디오 채널</span><span class="sxs-lookup"><span data-stu-id="e12e7-499">Video channels</span></span>

<span data-ttu-id="e12e7-500">**Stream에서 그룹을 만들 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="e12e7-501">예, Stream에서 직접 새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="e12e7-502">**그룹이 없는 Stream이 존재 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="e12e7-503">예, 비디오 채널과 비디오가 그룹에 연결 되어 있지 않으면 Stream에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="e12e7-504">**그룹 마다 비디오 및 채널이 여러 개 있을 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="e12e7-505">예, 각 그룹에 여러 비디오 및 채널이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="e12e7-506">**비디오 또는 채널이 여러 그룹과 연결 될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="e12e7-507">예, 비디오 또는 채널이 그룹으로 작성 되는 동안 다른 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="e12e7-508">**그룹 변경에 대 한 연결 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="e12e7-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="e12e7-509">예 및 아니요, Stream의 비디오는 원래 업 로더 또는 모임 레코더에서 소유 하며, 어떤 그룹과도 연결 될 수 있지만, 비디오 채널은 원래 만든 그룹과 연결 될 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="e12e7-510">**비디오나 채널 삭제가 그룹을 삭제 합니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="e12e7-511">아니요, 비디오나 채널을 삭제 해도 그룹은 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="e12e7-512">그러나 Stream에서 그룹 자체를 삭제 하면 실제 비디오를 제외 하 고 그룹 관련 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="e12e7-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="e12e7-513">Yammer</span></span>

<span data-ttu-id="e12e7-514">Yammer는 조직 내에서 및 조직과 간의 커뮤니티 계약을 촉진 하도록 설계 된 엔터프라이즈 소셜 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="e12e7-515">Yammer에서 이전에 "그룹" 이라고 알려진 커뮤니티를 만들면 사서함이 만들어지지만 현재는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="e12e7-516">Yammer와 연결 된 Microsoft 365 그룹은 Microsoft 팀의 팀과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="e12e7-517">**그룹에 제공 되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="e12e7-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="e12e7-518">대화 영역</span><span class="sxs-lookup"><span data-stu-id="e12e7-518">Conversation area</span></span>

<span data-ttu-id="e12e7-519">**Yammer에서 Microsoft 365 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="e12e7-520">예, Yammer에서 새 그룹을 만들면 플랫폼이 연결 되 고 사용자에 게 그룹을 만들 수 있는 경우 새 Microsoft 365 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="e12e7-521">Microsoft 365 그룹이 연결 된 Yammer 그룹은 Yammer 자체 이외의 인터페이스 또는 서비스에서 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="e12e7-522">**Microsoft 365 그룹이 없는 Yammer 그룹이 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="e12e7-523">예, Microsoft 365 그룹을 사용 하지 않고 Yammer 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="e12e7-524">Yammer 플랫폼이 Microsoft 365 그룹에 연결 되어 있지 않거나 사용자에 게 microsoft 365 그룹을 만들 수 없는 경우 Microsoft 365 그룹 연결 없이 Yammer 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="e12e7-525">**Microsoft 365 그룹당 여러 Yammer 그룹을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="e12e7-526">아니요, Yammer 그룹과 Microsoft 365 그룹 간의 관계는 1:1입니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="e12e7-527">**Yammer 그룹을 여러 Microsoft 365 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="e12e7-528">아니요, Yammer 그룹은 단일 Microsoft 365 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="e12e7-529">게시물을 다른 Yammer 그룹에서 공유 하거나 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="e12e7-530">**Yammer 그룹에서 Microsoft 365 그룹을 변경할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="e12e7-531">아니요, Yammer 그룹은 원래 연결 되었던 Microsoft 365 그룹에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="e12e7-532">**Yammer 그룹 365 삭제를 삭제 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="e12e7-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="e12e7-533">예, Yammer에서 그룹을 삭제 하면 관련 Microsoft 그룹과 그룹에 연결 된 서비스 및 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e12e7-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>


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
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921027"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="7c2bf-103">그룹 서비스 상호 작용</span><span class="sxs-lookup"><span data-stu-id="7c2bf-103">Groups services interactions</span></span>

<span data-ttu-id="7c2bf-104">Microsoft 365 그룹은 최종 사용자에게 연결된 환경을 제공하기 위해 Microsoft 365 플랫폼 내의 다양한 서비스 및 워크로드에 공통 패브릭을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="7c2bf-105">핵심적인 Microsoft 365 그룹은 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="7c2bf-106">멤버 자격을 관리하는 방법(Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="7c2bf-107">메시징 및 대화가 이행되는 장소(Exchange 사서함, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="7c2bf-108">파일을 저장할 위치(SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="7c2bf-109">일정을 위한 일정(Exchange)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="7c2bf-110">메모 캡처용 전자 필기장(OneNote)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="7c2bf-111">그룹 만들기 시점에는 여러 다른 리소스도 프로비전됩니다. 그러나 서비스에서 처음으로 액세스할 때까지는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="7c2bf-112">그룹 작업 관리용 보드(Planner)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="7c2bf-113">보고를 위한 작업 영역(Power BI)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="7c2bf-114">공유 비디오 영역(Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="7c2bf-115">공유 양식의 영역(Forms)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="7c2bf-116">Microsoft 365에서 다른 서비스는 Microsoft 365 그룹과 상호 작용하여 그룹 구성원에게 추가 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="7c2bf-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-117">Examples of this include:</span></span>

- <span data-ttu-id="7c2bf-118">앱용 Power Apps</span><span class="sxs-lookup"><span data-stu-id="7c2bf-118">Power Apps for apps</span></span>
- <span data-ttu-id="7c2bf-119">워크플로용 Power Automate</span><span class="sxs-lookup"><span data-stu-id="7c2bf-119">Power Automate for workflows</span></span>
- <span data-ttu-id="7c2bf-120">웹용 프로젝트 및 워터파일 기반 프로젝트 관리를 위한 로드맵</span><span class="sxs-lookup"><span data-stu-id="7c2bf-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="7c2bf-121">채널 기반 대화를 위한 Teams</span><span class="sxs-lookup"><span data-stu-id="7c2bf-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="7c2bf-122">Yammer 커뮤니티를 위한 지원</span><span class="sxs-lookup"><span data-stu-id="7c2bf-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="7c2bf-123">사용자와 그룹 상호 작용</span><span class="sxs-lookup"><span data-stu-id="7c2bf-123">User interactions with groups</span></span>

<span data-ttu-id="7c2bf-124">Microsoft 365 그룹은 관리자와 최종 사용자가 모두 다양한 인터페이스에서 만들어 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="7c2bf-125">관리 환경</span><span class="sxs-lookup"><span data-stu-id="7c2bf-125">Administrative experiences</span></span>

<span data-ttu-id="7c2bf-126">관리자는 여러 작업 관리 센터, 스크립팅을 지원하는 명령줄 인터페이스, Graph API와 상호 작용하는 사용자 지정 앱에서 Microsoft 365 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="7c2bf-127">이 예외는 Yammer 웹 인터페이스 내에서 만들어야 하는 Yammer 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="7c2bf-128">**관련 설정**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-128">**Related settings**</span></span>

<span data-ttu-id="7c2bf-129">그룹 설정을 관리할 수 있는 다양한 관리 인터페이스에는 여러 가지 겹쳐서 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="7c2bf-130">**Microsoft 365 관리 센터**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="7c2bf-131">Microsoft 365 관리 센터에서는 소유자가 게스트를 추가할 수 있도록 허용하는 기능처럼 기본적으로 그룹에 대한 게스트 액세스가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="7c2bf-132">이 관리 센터의 그룹에는 추가 조직 수준 컨트롤을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="7c2bf-133">**Azure AD 관리 센터**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-133">**Azure AD admin center**</span></span>

<span data-ttu-id="7c2bf-134">Azure AD 관리 센터는 사용자가 Azure Portal에서 그룹을 만들거나 소유자를 할당할 수 있는지 여부와 만료 및 이름 지정 정책 설정에 대한 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="7c2bf-135">또한 관리 센터는 비소유자도 게스트를 초대할 수 있는지 여부를 제한하는 등 Microsoft 365 관리 센터를 넘어서는 다양한 게스트 초대 제어 방안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="7c2bf-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-136">**SharePoint**</span></span>

<span data-ttu-id="7c2bf-137">SharePoint 사이트는 소유자, 구성원 및 방문자 보안 그룹으로 만들어지며 처음 두 사이트는 해당 Microsoft 365 그룹과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="7c2bf-138">SharePoint Online 사이트의 멤버 자격은 일반적으로 연결된 Microsoft 365 그룹에 의해 관리되는 반면 양방향 관계는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="7c2bf-139">Microsoft 365 그룹 수준의 구성원에 대한 변경 내용은 SharePoint에 반영됩니다. 그러나 SharePoint 그룹에서 구성원이 변경된 경우 이는 Microsoft 365 그룹에 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="7c2bf-140">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="7c2bf-140">User experiences</span></span>

<span data-ttu-id="7c2bf-141">최종 사용자는 Microsoft 365 내의 여러 서비스에서 그룹을 만들 수 있으며, 다른 서비스에서는 그룹과만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="7c2bf-142">다음 서비스를 사용하면 최종 사용자가 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="7c2bf-143">웹용 Outlook Planner Project SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="7c2bf-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="7c2bf-144">**그룹 만들기 제한**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-144">**Restriction of group creation**</span></span>

<span data-ttu-id="7c2bf-145">팀의 돌출을 제어하는 일반적인 방법은 팀을 만들 수 있는 사용자를 제한하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="7c2bf-146">그룹 만들기를 제한해야만 이행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="7c2bf-147">이렇게 하면 최종 사용자에게 필요한 다른 서비스에서 그룹을 만드는 능력에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="7c2bf-148">Microsoft 365 그룹은 일부 앱 또는 서비스에서 그룹을 만들지 못하도록 제한하는 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="7c2bf-149">그룹 만들기 제한의 환경은 앱과 서비스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="7c2bf-150">앱 또는 서비스</span><span class="sxs-lookup"><span data-stu-id="7c2bf-150">App or service</span></span>|<span data-ttu-id="7c2bf-151">환경</span><span class="sxs-lookup"><span data-stu-id="7c2bf-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="7c2bf-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="7c2bf-152">Outlook</span></span>|<span data-ttu-id="7c2bf-153">**새 그룹** 옵션이 사람 페이지의 새 메뉴에서 제거됨</span><span class="sxs-lookup"><span data-stu-id="7c2bf-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="7c2bf-154">Planner</span><span class="sxs-lookup"><span data-stu-id="7c2bf-154">Planner</span></span>|<span data-ttu-id="7c2bf-155">**새 계획은** 그룹 만들기가 꺼져 있으며 기존 그룹에 계획을 추가하기 위한 제안에 대해 설명</span><span class="sxs-lookup"><span data-stu-id="7c2bf-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="7c2bf-156">웹용 프로젝트 및 로드맵</span><span class="sxs-lookup"><span data-stu-id="7c2bf-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="7c2bf-157">**그룹 만들기** 메뉴에서는 그룹 만들기가 제한되어 있으며 기존 그룹을 사용하는 것이 제안됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="7c2bf-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7c2bf-158">SharePoint</span></span>|<span data-ttu-id="7c2bf-159">그룹에 연결되지 않은 팀 사이트를 계속 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="7c2bf-160">Stream</span><span class="sxs-lookup"><span data-stu-id="7c2bf-160">Stream</span></span>|<span data-ttu-id="7c2bf-161">**그룹** 옵션이 만들기 메뉴 에 **나타나지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="7c2bf-162">Teams</span><span class="sxs-lookup"><span data-stu-id="7c2bf-162">Teams</span></span>|<span data-ttu-id="7c2bf-163">사용자는 새 그룹으로 팀을 만들 수 없지만 기존 그룹을 활용하는 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="7c2bf-164">**팀 만들기 단추가** 그룹에서 팀 **만들기로 대체됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="7c2bf-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="7c2bf-165">Yammer</span></span>|<span data-ttu-id="7c2bf-166">**기본 그룹/커뮤니티** 탐색에서 그룹 만들기 옵션이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="7c2bf-167">그룹과의 서비스 상호 작용</span><span class="sxs-lookup"><span data-stu-id="7c2bf-167">Services interactions with groups</span></span>

<span data-ttu-id="7c2bf-168">다양한 유형의 그룹, 그룹이 생성 및 관리되는 방식 및 몇 가지 거버넌스 권장 사항에 대한 자세한 내용은 Microsoft 365의 그룹 포스터를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="7c2bf-169">[![그룹 인포그래픽용 축소판 이미지](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="7c2bf-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="7c2bf-171">다음 표에서는 다양한 서비스와의 Microsoft 365 그룹 상호 작용에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="7c2bf-172">제품</span><span class="sxs-lookup"><span data-stu-id="7c2bf-172">Product</span></span>|<span data-ttu-id="7c2bf-173">기능</span><span class="sxs-lookup"><span data-stu-id="7c2bf-173">Features</span></span>|<span data-ttu-id="7c2bf-174">서비스</span><span class="sxs-lookup"><span data-stu-id="7c2bf-174">Does the service</span></span><br><span data-ttu-id="7c2bf-175">그룹이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7c2bf-175">exist without a group?</span></span>|<span data-ttu-id="7c2bf-176">서비스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-176">Can the service</span></span><br><span data-ttu-id="7c2bf-177">그룹을 만들나요?</span><span class="sxs-lookup"><span data-stu-id="7c2bf-177">create a group?</span></span>|<span data-ttu-id="7c2bf-178">를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-178">Does deleting the</span></span><br><span data-ttu-id="7c2bf-179">인스턴스가 그룹을 삭제하나요?</span><span class="sxs-lookup"><span data-stu-id="7c2bf-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="7c2bf-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c2bf-180">Azure AD</span></span>|<span data-ttu-id="7c2bf-181">멤버 자격, 그룹 컨트롤, 게스트</span><span class="sxs-lookup"><span data-stu-id="7c2bf-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="7c2bf-182">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-182">Yes</span></span>|<span data-ttu-id="7c2bf-183">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-183">Yes</span></span>|<span data-ttu-id="7c2bf-184">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-184">Yes</span></span>|
|<span data-ttu-id="7c2bf-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="7c2bf-185">Exchange</span></span>|<span data-ttu-id="7c2bf-186">일정, 사서함</span><span class="sxs-lookup"><span data-stu-id="7c2bf-186">Calendar, mailbox</span></span>|<span data-ttu-id="7c2bf-187">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-187">Yes</span></span>|<span data-ttu-id="7c2bf-188">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-188">Yes</span></span>|<span data-ttu-id="7c2bf-189">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-189">Yes</span></span>|
|<span data-ttu-id="7c2bf-190">Forms</span><span class="sxs-lookup"><span data-stu-id="7c2bf-190">Forms</span></span>|<span data-ttu-id="7c2bf-191">폼</span><span class="sxs-lookup"><span data-stu-id="7c2bf-191">Form</span></span>|<span data-ttu-id="7c2bf-192">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-192">Yes</span></span>|<span data-ttu-id="7c2bf-193">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-193">No</span></span>|<span data-ttu-id="7c2bf-194">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-194">No</span></span>|
|<span data-ttu-id="7c2bf-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="7c2bf-195">OneNote</span></span>|<span data-ttu-id="7c2bf-196">전자 필기장</span><span class="sxs-lookup"><span data-stu-id="7c2bf-196">Notebook</span></span>|<span data-ttu-id="7c2bf-197">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-197">Yes</span></span>|<span data-ttu-id="7c2bf-198">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-198">No</span></span>|<span data-ttu-id="7c2bf-199">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-199">No</span></span>|
|<span data-ttu-id="7c2bf-200">Planner</span><span class="sxs-lookup"><span data-stu-id="7c2bf-200">Planner</span></span>|<span data-ttu-id="7c2bf-201">작업 보드</span><span class="sxs-lookup"><span data-stu-id="7c2bf-201">Task board</span></span>|<span data-ttu-id="7c2bf-202">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-202">No</span></span>|<span data-ttu-id="7c2bf-203">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-203">Yes</span></span>|<span data-ttu-id="7c2bf-204">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-204">Yes</span></span>|
|<span data-ttu-id="7c2bf-205">Power Apps 앱</span><span class="sxs-lookup"><span data-stu-id="7c2bf-205">Power Apps app</span></span>|<span data-ttu-id="7c2bf-206">앱</span><span class="sxs-lookup"><span data-stu-id="7c2bf-206">App</span></span>|<span data-ttu-id="7c2bf-207">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-207">Yes</span></span>|<span data-ttu-id="7c2bf-208">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-208">No</span></span>|<span data-ttu-id="7c2bf-209">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-209">No</span></span>|
|<span data-ttu-id="7c2bf-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="7c2bf-210">Power Automate</span></span>|<span data-ttu-id="7c2bf-211">워크플로</span><span class="sxs-lookup"><span data-stu-id="7c2bf-211">Workflow</span></span>|<span data-ttu-id="7c2bf-212">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-212">Yes</span></span>|<span data-ttu-id="7c2bf-213">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-213">No</span></span>|<span data-ttu-id="7c2bf-214">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-214">No</span></span>|
|<span data-ttu-id="7c2bf-215">Power BI(클래식)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-215">Power BI (classic)</span></span>|<span data-ttu-id="7c2bf-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="7c2bf-216">Workspace</span></span>|<span data-ttu-id="7c2bf-217">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-217">No</span></span>|<span data-ttu-id="7c2bf-218">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-218">Yes</span></span>|<span data-ttu-id="7c2bf-219">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-219">Yes</span></span>|
|<span data-ttu-id="7c2bf-220">Power BI(신규)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-220">Power BI (new)</span></span>|<span data-ttu-id="7c2bf-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="7c2bf-221">Workspace</span></span>|<span data-ttu-id="7c2bf-222">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-222">Yes</span></span>|<span data-ttu-id="7c2bf-223">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-223">No</span></span>|<span data-ttu-id="7c2bf-224">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-224">Yes</span></span>|
|<span data-ttu-id="7c2bf-225">웹용 Project</span><span class="sxs-lookup"><span data-stu-id="7c2bf-225">Project for the web</span></span>|<span data-ttu-id="7c2bf-226">프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="7c2bf-226">Project plan</span></span>|<span data-ttu-id="7c2bf-227">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-227">Yes</span></span>|<span data-ttu-id="7c2bf-228">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-228">Yes</span></span>|<span data-ttu-id="7c2bf-229">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-229">No</span></span>|
|<span data-ttu-id="7c2bf-230">로드맵</span><span class="sxs-lookup"><span data-stu-id="7c2bf-230">Roadmap</span></span>|<span data-ttu-id="7c2bf-231">로드맵</span><span class="sxs-lookup"><span data-stu-id="7c2bf-231">Roadmap</span></span>|<span data-ttu-id="7c2bf-232">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-232">Yes</span></span>|<span data-ttu-id="7c2bf-233">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-233">Yes</span></span>|<span data-ttu-id="7c2bf-234">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-234">No</span></span>|
|<span data-ttu-id="7c2bf-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7c2bf-235">SharePoint</span></span>|<span data-ttu-id="7c2bf-236">사이트</span><span class="sxs-lookup"><span data-stu-id="7c2bf-236">Site</span></span>|<span data-ttu-id="7c2bf-237">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-237">Yes</span></span>|<span data-ttu-id="7c2bf-238">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-238">Yes</span></span>|<span data-ttu-id="7c2bf-239">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-239">Yes</span></span>|
|<span data-ttu-id="7c2bf-240">Stream</span><span class="sxs-lookup"><span data-stu-id="7c2bf-240">Stream</span></span>|<span data-ttu-id="7c2bf-241">채널, 비디오</span><span class="sxs-lookup"><span data-stu-id="7c2bf-241">Channel, video</span></span>|<span data-ttu-id="7c2bf-242">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-242">Yes</span></span>|<span data-ttu-id="7c2bf-243">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-243">Yes</span></span>|<span data-ttu-id="7c2bf-244">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-244">Yes</span></span>|
|<span data-ttu-id="7c2bf-245">Teams</span><span class="sxs-lookup"><span data-stu-id="7c2bf-245">Teams</span></span>|<span data-ttu-id="7c2bf-246">팀</span><span class="sxs-lookup"><span data-stu-id="7c2bf-246">Team</span></span>|<span data-ttu-id="7c2bf-247">아니요</span><span class="sxs-lookup"><span data-stu-id="7c2bf-247">No</span></span>|<span data-ttu-id="7c2bf-248">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-248">Yes</span></span>|<span data-ttu-id="7c2bf-249">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-249">Yes</span></span>|
|<span data-ttu-id="7c2bf-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="7c2bf-250">Yammer</span></span>|<span data-ttu-id="7c2bf-251">Group</span><span class="sxs-lookup"><span data-stu-id="7c2bf-251">Group</span></span>|<span data-ttu-id="7c2bf-252">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-252">Yes</span></span>|<span data-ttu-id="7c2bf-253">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-253">Yes</span></span>|<span data-ttu-id="7c2bf-254">예</span><span class="sxs-lookup"><span data-stu-id="7c2bf-254">Yes</span></span>|

<span data-ttu-id="7c2bf-255">위의 표에서는 Microsoft 365 서비스와의 그룹 상호 작용에 대한 간략한 개요를 제공하나, 이해해야 할 미소와 복잡도도 다수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="7c2bf-256">다음 섹션에서는 특정 워크로드 및 그룹과의 상호 작용에 대해 좀 더 깊이 있게 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="7c2bf-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c2bf-257">Azure AD</span></span>

<span data-ttu-id="7c2bf-258">Azure AD는 Microsoft 365 전반에 걸쳐 주된 ID 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="7c2bf-259">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-260">그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="7c2bf-260">Group membership</span></span>
- <span data-ttu-id="7c2bf-261">이름 정책</span><span class="sxs-lookup"><span data-stu-id="7c2bf-261">Naming policy</span></span>
- <span data-ttu-id="7c2bf-262">만료 정책</span><span class="sxs-lookup"><span data-stu-id="7c2bf-262">Expiration policy</span></span>
- <span data-ttu-id="7c2bf-263">게스트</span><span class="sxs-lookup"><span data-stu-id="7c2bf-263">Guests</span></span>
- <span data-ttu-id="7c2bf-264">그룹 만들기 제한</span><span class="sxs-lookup"><span data-stu-id="7c2bf-264">Restriction of Group creation</span></span>

<span data-ttu-id="7c2bf-265">**Azure AD에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="7c2bf-266">예, 관리 웹 포털, PowerShell 또는 Graph API를 통해 Azure AD에서 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="7c2bf-267">**그룹이 없는 Azure AD가 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="7c2bf-268">예, Azure AD는 Microsoft 365 그룹과 관련이 없는 많은 서비스를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="7c2bf-269">각 Microsoft 365 그룹은 Azure AD에서 개체로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="7c2bf-270">**그룹당 Azure AD 인스턴스가 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="7c2bf-271">아니요. Azure AD 인스턴스는 하나뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="7c2bf-272">**Azure AD를 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="7c2bf-273">예, Azure AD는 그룹 멤버 자격 서비스를 제공하는 기반 플랫폼이기 때문에</span><span class="sxs-lookup"><span data-stu-id="7c2bf-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="7c2bf-274">**그룹과 Azure AD의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-275">아니요. Azure AD는 그룹이 존재하는 기반 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="7c2bf-276">**인스턴스를 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="7c2bf-277">Azure AD에서 그룹을 삭제하면 관련 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="7c2bf-278">Teams</span><span class="sxs-lookup"><span data-stu-id="7c2bf-278">Teams</span></span>

<span data-ttu-id="7c2bf-279">Teams는 다양한 Microsoft 및 타사 서비스와 상호 작용할 수 있는 단수 인터페이스를 제공하여 공동 작업을 향상하기 위한 채팅 중심 작업 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="7c2bf-280">기본적으로 팀을 만들면 Microsoft 365 그룹과 연결된 사서함 및 일정이 Exchange의 전체 주소 목록과 Outlook 모두에서 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="7c2bf-281">사용자가 동일한 Microsoft 365 그룹에서 Outlook과 Teams를 모두 사용하려면 관리자가 이를 수동으로 다시 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="7c2bf-282">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-283">Conversations</span><span class="sxs-lookup"><span data-stu-id="7c2bf-283">Conversations</span></span>
- <span data-ttu-id="7c2bf-284">채널 & 탭</span><span class="sxs-lookup"><span data-stu-id="7c2bf-284">Channels & tabs</span></span>
- <span data-ttu-id="7c2bf-285">모임</span><span class="sxs-lookup"><span data-stu-id="7c2bf-285">Meetings</span></span>

<span data-ttu-id="7c2bf-286">**Teams에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="7c2bf-287">예. 새 팀을 만들면 새 Microsoft 365 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="7c2bf-288">현재 팀이 없는 기존 그룹에 대한 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="7c2bf-289">**팀이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="7c2bf-290">아니요. 그룹이 없는 팀은 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="7c2bf-291">**그룹당 여러 팀이 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="7c2bf-292">아니요. 팀과 그룹 간의 관계는 1:1입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="7c2bf-293">**팀을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-294">아니요. 팀 자체는 단일 그룹과만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="7c2bf-295">**그룹과 팀의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-296">아니요. 팀은 원래 연결된 그룹과만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="7c2bf-297">**팀을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="7c2bf-298">예, Microsoft Teams에서 팀을 삭제하면 그룹, 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="7c2bf-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="7c2bf-299">Exchange</span></span>

<span data-ttu-id="7c2bf-300">Exchange Online에서는 메시징, 일정, 연락처 및 관련 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="7c2bf-301">Group의 컨텍스트에서는 전체 서비스 인스턴스가 아니라 단일 리소스만 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="7c2bf-302">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-303">사서함 및 일정</span><span class="sxs-lookup"><span data-stu-id="7c2bf-303">Mailbox and calendar</span></span>
- <span data-ttu-id="7c2bf-304">모든 그룹 구성원에게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="7c2bf-304">Ability to email all Group members</span></span>
- <span data-ttu-id="7c2bf-305">eDiscovery 목적에 대한 Teams 채널 대화 저장소, Planner 설명</span><span class="sxs-lookup"><span data-stu-id="7c2bf-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="7c2bf-306">**Exchange에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="7c2bf-307">예. Exchange Online 관리 센터뿐만 아니라 Outlook에서도 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="7c2bf-308">Exchange 메일 그룹을 Microsoft 365 그룹으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="7c2bf-309">**Exchange가 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="7c2bf-310">예. Exchange Online에서는 그룹 연결 없이 공유 사서함 및 일정을 비롯한 다양한 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="7c2bf-311">**그룹당 Exchange 사서함 또는 일정 인스턴스가 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="7c2bf-312">아니요. 그룹에 대한 단일 Exchange Online 사서함 및 일정만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="7c2bf-313">**Exchange 사서함 및 일정을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-314">아니요. 사서함과 일정은 그룹과 1:1 관계를 맺습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="7c2bf-315">사서함을 다른 사용자 또는 그룹과 공유할 수 있습니다. 그러나 이 경우 어떤 형식의 서비스 연결도 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="7c2bf-316">**Exchange 사서함 또는 일정과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-317">아니요. 사서함과 일정을 다른 그룹으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="7c2bf-318">그러나 콘텐츠를 Outlook 내에서 또는 타사 도구를 사용하여 한 사서함에서 다른 사서함으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="7c2bf-319">**사서함을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="7c2bf-320">예, Exchange에서 사서함을 삭제하면 그룹 및 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="7c2bf-321">Forms</span><span class="sxs-lookup"><span data-stu-id="7c2bf-321">Forms</span></span>

<span data-ttu-id="7c2bf-322">양식은 웹 기반 설문 조사 및 퀴즈를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="7c2bf-323">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="7c2bf-324">양식의 소유권</span><span class="sxs-lookup"><span data-stu-id="7c2bf-324">Ownership of forms</span></span>

<span data-ttu-id="7c2bf-325">**양식에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="7c2bf-326">아니요. Forms는 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="7c2bf-327">**양식이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="7c2bf-328">예. 설문 조사 및 퀴즈는 최종 사용자의 계정에 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="7c2bf-329">**그룹당 여러 양식이 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="7c2bf-330">예. 그룹과 연결된 양식이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="7c2bf-331">**양식을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-332">아니요. 양식은 단일 그룹에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="7c2bf-333">**양식과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-334">아니요. 양식이 그룹과 연결되면(직접 만들어지거나 개인으로부터 전송된 소유권) 다른 그룹으로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="7c2bf-335">**양식을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="7c2bf-336">아니요. 양식 인터페이스에서 그룹을 삭제할 수 없습니다. 개별 양식만 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="7c2bf-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="7c2bf-337">OneNote</span></span>

<span data-ttu-id="7c2bf-338">OneNote는 디지털 전자 필기장 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="7c2bf-339">그룹으로 만든 OneNote 전자 필기장은 그룹 연결 서비스가 아니라 연결된 SharePoint 사이트의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="7c2bf-340">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="7c2bf-341">공유 전자 필기장(그룹 연결 SharePoint 라이브러리에 저장)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="7c2bf-342">**OneNote에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="7c2bf-343">아니요. OneNote 응용 프로그램에서 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="7c2bf-344">**OneNote 전자 필기장은 그룹이 없는가요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="7c2bf-345">예. OneDrive 또는 다른 공유 위치에서 직접 전자 필기장을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="7c2bf-346">**그룹당 OneNote 전자 필기장을 여러 개 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="7c2bf-347">예. 전자 필기장은 기본적으로 만들어지며 다른 전자 필기장은 추가할 수 있습니다. 그러나 그룹 관련 서비스의 OneNote 링크는 항상 기본 전자 필기장으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="7c2bf-348">**OneNote 전자 필기장을 여러 그룹에 연결해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-349">아니요. 전자 필기장은 그룹 연결 SharePoint 사이트 라이브러리에 저장되고 다양한 인터페이스에서 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="7c2bf-350">그러나 개인과 공유할 수 있는 방식으로 다른 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="7c2bf-351">**전자 필기장과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-352">아니요. 전자 필기장 자체는 그룹에 연결되어 있으며 다른 그룹 연결 서비스에서 직접 액세스할 수 있습니다. 그러나 콘텐츠는 OneNote 응용 프로그램 내에서 전자 필기장에서 다른 전자 필기장으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="7c2bf-353">**전자 필기장을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="7c2bf-354">아니요. 그러나 OneNote 전자 필기장을 삭제하면 그룹 관련 서비스의 링크가 끊어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="7c2bf-355">Planner</span><span class="sxs-lookup"><span data-stu-id="7c2bf-355">Planner</span></span>

<span data-ttu-id="7c2bf-356">Planner는 간단한 그룹 작업 관리 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="7c2bf-357">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="7c2bf-358">그룹 작업 관리 보드</span><span class="sxs-lookup"><span data-stu-id="7c2bf-358">Board for managing group tasks</span></span>

<span data-ttu-id="7c2bf-359">**Planner가 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="7c2bf-360">예. 계획을 만들면 새 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="7c2bf-361">**Planner 보드가 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="7c2bf-362">아니요. 계획을 그룹과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="7c2bf-363">**그룹당 계획이 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="7c2bf-364">예. 그룹당 계획이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="7c2bf-365">**계획을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-366">아니요. 계획은 액세스 권한을 결정하기 위해 그룹 구성원에만 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="7c2bf-367">**계획과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-368">아니요. 그러나 계획을 복사하면 새 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="7c2bf-369">다른 응용 프로그램에서 만든 그룹은 사용자의 Planner에 자동으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="7c2bf-370">보드에 처음 액세스하려면 Outlook과 같은 다른 그룹 기반 인터페이스에서 보드를 열 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="7c2bf-371">**계획을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="7c2bf-372">예. 계획을 삭제하면 그룹 및 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="7c2bf-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="7c2bf-373">Power Apps</span></span>

<span data-ttu-id="7c2bf-374">Power Apps는 코드 없이 앱 개발을 위한 캔버스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="7c2bf-375">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-376">실행 및 수정할 그룹과 앱을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="7c2bf-377">**Power Apps에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="7c2bf-378">아니요. Power Apps는 Microsoft 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="7c2bf-379">**Power Apps가 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="7c2bf-380">예, 앱을 Power Apps 내에서 만들 수 있으며 공유 또는 게시될 때까지 크리에이터스 계정 내에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="7c2bf-381">**그룹당 앱이 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="7c2bf-382">예, 그룹과 공유되는 앱이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="7c2bf-383">**앱을 여러 그룹과 연결될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-384">예, 앱을 여러 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="7c2bf-385">**그룹과 앱의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-386">예, Power Apps와 Microsoft 365 그룹 간의 연결은 공유 전용이기에 따라 앱은 여전히 작성자와 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c2bf-387">[앱을 공유하려면 먼저 그룹을 보안을 사용하도록 설정해야 합니다.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="7c2bf-388">**앱을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="7c2bf-389">아니요. 앱이 공유되는 것 외의 그룹에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="7c2bf-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="7c2bf-390">Power Automate</span></span>

<span data-ttu-id="7c2bf-391">Power Automate(이전의 Microsoft Flow)는 워크플로 및 자동화 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="7c2bf-392">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="7c2bf-393">워크플로를 실행 및 수정할 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="7c2bf-394">**Power Automate에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="7c2bf-395">아니요. Power Automate는 연결된 컨텍스트에서 Microsoft 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="7c2bf-396">그러나 Azure AD 보안 그룹을 만들거나 Microsoft 365 그룹의 구성원을 업데이트하는 등의 다양한 작업을 수행하는 흐름을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="7c2bf-397">**흐름이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="7c2bf-398">예. 흐름은 Power Automate 내에서 만들 수 있으며 공유 또는 게시될 때까지 작성자 계정 내에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="7c2bf-399">**그룹당 흐름이 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="7c2bf-400">예, 그룹과 공유되는 흐름이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="7c2bf-401">**흐름을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-402">예, 흐름을 여러 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="7c2bf-403">**그룹과 흐름의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-404">예. Power Automate와 Microsoft 365 그룹 간의 연결은 공유 전용으로, 흐름은 여전히 작성자와 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="7c2bf-405">**흐름을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="7c2bf-406">아니요. Power Apps와 마찬가지로 흐름은 공유되는 것 외의 그룹에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="7c2bf-407">Power BI(클래식)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-407">Power BI (classic)</span></span>

<span data-ttu-id="7c2bf-408">Power BI는 대화형 데이터 기반 대시보드 및 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="7c2bf-409">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="7c2bf-410">데이터 보고</span><span class="sxs-lookup"><span data-stu-id="7c2bf-410">Data reporting</span></span>

<span data-ttu-id="7c2bf-411">**Power BI에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="7c2bf-412">예, 클래식 작업 환경을 만들면 Microsoft 365 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="7c2bf-413">**Power BI 클래식 작업 영역이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="7c2bf-414">아니요. Power BI의 클래식 작업 영역은 [그룹과 연결되어야 합니다.](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="7c2bf-415">**그룹당 여러 Power BI 작업 영역이 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="7c2bf-416">아니요. 클래식 작업 영역과 그룹 간의 관계는 1:1입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="7c2bf-417">**작업 영역이 여러 그룹과 연결될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-418">기술적으로는 그룹으로 클래식 작업 영역이 만들어지지만 그룹 외부에서 사용자 및 보안 그룹과 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="7c2bf-419">**작업 영역과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="7c2bf-420">아니요. 클래식 작업 영역 자체는 Group과 연결되어 있습니다. 그러나 콘텐츠는 Power BI 인터페이스 내의 작업 영역 하나에서 다른 작업 영역으로 이동하거나 로컬로 콘텐츠를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="7c2bf-421">**작업 영역이 삭제되면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="7c2bf-422">예. Power BI에서 작업 영역이 삭제되면 그룹 및 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="7c2bf-423">Power BI(신규)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-423">Power BI (new)</span></span>

<span data-ttu-id="7c2bf-424">Power BI는 대화형 데이터 기반 대시보드 및 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="7c2bf-425">Power BI에서 새 작업 환경을 만들면 Microsoft 365 그룹이 만들어지지는 않습니다. 다른 수단으로 그룹을 만들면 Power BI에 새로운(클래식이 아닌) 작업 영역이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="7c2bf-426">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="7c2bf-427">데이터 보고</span><span class="sxs-lookup"><span data-stu-id="7c2bf-427">Data reporting</span></span>

<span data-ttu-id="7c2bf-428">**Power BI에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="7c2bf-429">아니요. 새 Power BI 인터페이스에서 Microsoft 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="7c2bf-430">**새 Power BI 작업 영역이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="7c2bf-431">예. Power BI에서 Microsoft 365 그룹과 연결되지 않은 보고서 및 작업 영역이 만들어지게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="7c2bf-432">**그룹당 여러 작업 영역이 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="7c2bf-433">예, Power BI에서 만든 여러 작업 영역은 단일 그룹과 [공유할 수 있습니다.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)</span><span class="sxs-lookup"><span data-stu-id="7c2bf-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="7c2bf-434">**작업 영역이 여러 그룹과 연결될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-435">아니요. Power BI에서 만든 작업 영역은 단일 그룹에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="7c2bf-436">**작업 영역과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="7c2bf-437">그렇기도 하고 그렇지 않기도 하고.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-437">Yes and no.</span></span> <span data-ttu-id="7c2bf-438">Power BI에서 만든 작업 영역은 한 번만 단일 그룹에만 연결될 수 있지만, 이 경우 해당 연결은 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="7c2bf-439">그룹이 Power BI에서 만든 작업 영역은 해당 그룹에 영구적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="7c2bf-440">**작업 영역이 삭제되면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="7c2bf-441">예. Power BI에서 작업 영역이 삭제되면 그룹 및 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="7c2bf-442">웹용 Project</span><span class="sxs-lookup"><span data-stu-id="7c2bf-442">Project for the web</span></span>

<span data-ttu-id="7c2bf-443">웹용 Project는 프로젝트 계획, Gantt 차트 및 로드맵을 만드는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="7c2bf-444">그룹에 제공되는 주요 기능</span><span class="sxs-lookup"><span data-stu-id="7c2bf-444">Key features provided to groups.</span></span>

- <span data-ttu-id="7c2bf-445">프로젝트 계획</span><span class="sxs-lookup"><span data-stu-id="7c2bf-445">Project plans</span></span>

<span data-ttu-id="7c2bf-446">**웹용 Project에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="7c2bf-447">예. 웹용 Project에서 직접 새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="7c2bf-448">**프로젝트가 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="7c2bf-449">예. 프로젝트는 Microsoft 365 그룹과 연결되지 않고 존재할 수 있습니다. 그러나 작업을 배정하려면 그룹 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="7c2bf-450">**그룹당 여러 프로젝트가 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="7c2bf-451">예. 단일 그룹에서 여러 프로젝트를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="7c2bf-452">**프로젝트를 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-453">아니요. 프로젝트는 단일 그룹에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="7c2bf-454">**프로젝트의 그룹 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-455">아니요. 그룹과의 연결은 설정되면 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="7c2bf-456">**프로젝트를 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="7c2bf-457">아니요. 웹용 Project에서 프로젝트를 삭제하면 그룹이 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="7c2bf-458">로드맵</span><span class="sxs-lookup"><span data-stu-id="7c2bf-458">Roadmap</span></span>

<span data-ttu-id="7c2bf-459">로드맵은 웹용 Project 및 Project Online을 사용하여 프로젝트 로드맵을 만드는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="7c2bf-460">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-461">프로젝트 로드맵</span><span class="sxs-lookup"><span data-stu-id="7c2bf-461">Project roadmaps</span></span>

<span data-ttu-id="7c2bf-462">**로드맵에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="7c2bf-463">예. 로드맵에서 직접 새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="7c2bf-464">**로드맵이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="7c2bf-465">예. 로드맵은 Microsoft 365 그룹에 연결되지 않고 존재할 수 있습니다. 그러나 로드맵을 공유하려면 그룹 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="7c2bf-466">**그룹당 여러 로드맵이 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="7c2bf-467">예. 여러 로드맵을 단일 그룹에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="7c2bf-468">**로드맵을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-469">아니요. 로드맵은 단일 그룹에만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="7c2bf-470">**로드맵과 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="7c2bf-471">아니요. 그룹과의 연결은 설정되면 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="7c2bf-472">**로드맵을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="7c2bf-473">아니요. 로드맵을 삭제하면 그룹이 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="7c2bf-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7c2bf-474">SharePoint</span></span>

<span data-ttu-id="7c2bf-475">SharePoint는 다양한 Microsoft 365 서비스에 대한 저장소 서비스를 제공하는 웹 기반 콘텐츠 관리 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="7c2bf-476">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-477">문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="7c2bf-477">Document library</span></span>
- <span data-ttu-id="7c2bf-478">OneNote 전자 필기장 저장소 라이브러리</span><span class="sxs-lookup"><span data-stu-id="7c2bf-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="7c2bf-479">Teams 위키 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="7c2bf-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="7c2bf-480">**SharePoint에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="7c2bf-481">예. SharePoint에서 팀 사이트를 만들면 기본적으로 Microsoft 365 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="7c2bf-482">그룹 및 기존 사이트에 대한 팀(선택 사항)을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="7c2bf-483">**SharePoint 사이트가 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="7c2bf-484">예, SharePoint는 통신 및 허브 사이트와 같은 그룹과 관련되지 않은 여러 서비스 및 사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="7c2bf-485">**그룹당 여러 사이트가 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="7c2bf-486">아니요. 그룹당 사이트가 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="7c2bf-487">Teams의 비공개 채널은 그룹에 연결되지 않은 추가 사이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="7c2bf-488">**사이트가 여러 그룹과 연결될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-489">기술적으로는 아니요. 그러나 사이트가 그룹으로 만들어지면서 콘텐츠를 다른 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="7c2bf-490">**사이트와 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="7c2bf-491">아니요. 사이트 자체는 그룹과 연결됩니다. 그러나 콘텐츠를 SharePoint 인터페이스 내에서 한 사이트에서 다른 사이트로 이동하거나 로컬로 내보내거나 타사 도구를 사용하여 콘텐츠를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="7c2bf-492">**사이트를 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="7c2bf-493">예. SharePoint에서 사이트를 삭제하면 그룹 및 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="7c2bf-494">Stream</span><span class="sxs-lookup"><span data-stu-id="7c2bf-494">Stream</span></span>

<span data-ttu-id="7c2bf-495">Microsoft Stream은 비디오 호스팅 및 공유 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="7c2bf-496">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-497">비디오 저장소</span><span class="sxs-lookup"><span data-stu-id="7c2bf-497">Video storage</span></span>
- <span data-ttu-id="7c2bf-498">Teams 모임 녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="7c2bf-498">Teams meeting recording</span></span>
- <span data-ttu-id="7c2bf-499">비디오 채널</span><span class="sxs-lookup"><span data-stu-id="7c2bf-499">Video channels</span></span>

<span data-ttu-id="7c2bf-500">**Stream에서 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="7c2bf-501">예. Stream에서 직접 새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="7c2bf-502">**Stream이 그룹 없이 존재하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="7c2bf-503">예, 비디오 채널 및 비디오는 그룹과 연결되지 않고 Stream에 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="7c2bf-504">**그룹당 여러 비디오 및 채널이 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="7c2bf-505">예, 각 그룹에 여러 비디오 및 채널이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="7c2bf-506">**비디오 또는 채널을 여러 그룹과 연결할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="7c2bf-507">예. 그룹으로 비디오 또는 채널을 만들 때 다른 그룹과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="7c2bf-508">**그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="7c2bf-509">예 및 아니요; Stream의 비디오는 원래 업로더 또는 모임 레코더가 소유하기 때문에 모든 그룹과 연결될 수 있습니다. 그러나 비디오 채널은 원래 만든 그룹과만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="7c2bf-510">**비디오 또는 채널을 삭제하면 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="7c2bf-511">아니요. 비디오 또는 채널을 삭제해도 그룹은 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="7c2bf-512">그러나 Stream에서 그룹 자체를 삭제하면 실제 비디오를 제외하고 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="7c2bf-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="7c2bf-513">Yammer</span></span>

<span data-ttu-id="7c2bf-514">Yammer 조직 내에서 그리고 조직 간에 커뮤니티 참여를 유도하도록 설계된 엔터프라이즈 소셜 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="7c2bf-515">사서함에서 커뮤니티(이전의 "그룹"Yammer 만들기)를 만들면 사서함이 만들어지지만 현재는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="7c2bf-516">사용자와 연결된 Microsoft 365 Yammer Microsoft Teams의 팀과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="7c2bf-517">**그룹에 제공되는 주요 기능**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="7c2bf-518">대화 영역</span><span class="sxs-lookup"><span data-stu-id="7c2bf-518">Conversation area</span></span>

<span data-ttu-id="7c2bf-519">**Microsoft Yammer 그룹을 만들 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="7c2bf-520">예, Yammer 플랫폼이 연결되어 있으며 사용자가 그룹을 만들 수 있는 경우 새 Microsoft 365 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="7c2bf-521">연결된 Yammer 그룹이 있는 그룹은 해당 그룹 자체가 아니라 다른 인터페이스나 서비스에서 만들 Yammer 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="7c2bf-522">**Microsoft Yammer 없는 그룹이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="7c2bf-523">예, Microsoft 365 그룹 없이 Yammer 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="7c2bf-524">Yammer 플랫폼이 Microsoft 365 그룹에 연결되지 않은 경우 또는 사용자가 Microsoft 365 그룹을 만들 수 없는 경우 Yammer 그룹이 Microsoft 365 그룹 연결 없이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="7c2bf-525">**Microsoft 365 그룹당 Yammer 그룹이 여러 개 있을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="7c2bf-526">아니요. Yammer 그룹과 Microsoft 365 그룹 간의 관계는 1:1입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="7c2bf-527">**특정 Yammer Microsoft 365 그룹과 연결될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="7c2bf-528">아니요. Yammer 그룹은 단일 Microsoft 365 그룹과만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="7c2bf-529">게시물을 다른 사용자 그룹과 공유하거나 다른 그룹으로 Yammer 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="7c2bf-530">**Microsoft Yammer 그룹과의 연결은 변경될 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="7c2bf-531">아니요. Yammer 그룹은 원래 연결된 Microsoft 365 그룹과만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="7c2bf-532">**Yammer 삭제하면 Microsoft 365 그룹이 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="7c2bf-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="7c2bf-533">예, 그룹에서 그룹을 삭제하면 Yammer Microsoft 그룹 및 그룹 관련 서비스 및 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c2bf-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c2bf-534">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7c2bf-534">Related topics</span></span>

[<span data-ttu-id="7c2bf-535">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="7c2bf-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="7c2bf-536">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="7c2bf-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)
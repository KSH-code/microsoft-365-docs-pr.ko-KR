---
title: Microsoft 365에서의 공유 제한
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: Microsoft 365에서 공유를 제한하거나 해제할 수 있는 옵션에 대해 알아봅니다.
ms.openlocfilehash: 46cef1aac6d3387366a5e8ce9f9c1129f6c83e61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920207"
---
# <a name="limit-sharing-in-microsoft-365"></a><span data-ttu-id="de9fc-103">Microsoft 365에서의 공유 제한</span><span class="sxs-lookup"><span data-stu-id="de9fc-103">Limit sharing in Microsoft 365</span></span>

<span data-ttu-id="de9fc-104">내부 공유를 완전히 비활성화하거나 사이트에서 공유 버튼을 제거할 수는 없지만 조직의 요구를 충족시키기 위해 Microsoft 365에서 공유를 제한할 수 있는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-104">While you can't disable internal sharing entirely or remove the Share button from sites, there are a variety of ways that you can limit sharing in Microsoft 365 to meet the needs of your organization.</span></span>

<span data-ttu-id="de9fc-105">파일 공유 방법은 아래 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-105">The methods of sharing files are listed in the table below.</span></span> <span data-ttu-id="de9fc-106">자세한 정보를 확인하려면 **공유 방법** 열에서 해당 링크를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-106">Click the link in the **Sharing method** column for detailed information.</span></span>

|<span data-ttu-id="de9fc-107">공유 방법</span><span class="sxs-lookup"><span data-stu-id="de9fc-107">Sharing method</span></span>|<span data-ttu-id="de9fc-108">설명</span><span class="sxs-lookup"><span data-stu-id="de9fc-108">Description</span></span>|<span data-ttu-id="de9fc-109">제한 옵션</span><span class="sxs-lookup"><span data-stu-id="de9fc-109">Limiting options</span></span>|
|:-------------|:----------|:-------------|
|[<span data-ttu-id="de9fc-110">Microsoft 365 그룹 또는 팀</span><span class="sxs-lookup"><span data-stu-id="de9fc-110">Microsoft 365 group or team</span></span>](#microsoft-365-group-or-team)|<span data-ttu-id="de9fc-111">Microsoft Teams 팀 또는 Microsoft 365 그룹에 대한 액세스 권한을 받은 사람들은 연결된 SharePoint 사이트의 파일에 대한 편집 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-111">People granted access to a Microsoft Teams team or Microsoft 365 group have edit access to files in the associated SharePoint site.</span></span>|<span data-ttu-id="de9fc-112">그룹 또는 팀이 비공개인 경우 팀에 대한 초대 공유는 승인을 위해 소유자에게 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-112">If the group or team is private, sharing invitations to join the team go to the owner for approval.</span></span> <span data-ttu-id="de9fc-113">관리자는 게스트 액세스를 비활성화하거나 민감도 레이블을 사용하여 조직 외부의 사람들이 액세스하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-113">Admins can disable guest access or use sensitivity labels to prevent access by people from outside the organization.</span></span>|
|[<span data-ttu-id="de9fc-114">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="de9fc-114">SharePoint site</span></span>](#sharepoint-site)|<span data-ttu-id="de9fc-115">사람들은 소유자, 회원 또는 방문자에게 SharePoint 사이트에 대한 액세스 권한을 부여할 수 있으며 사이트의 파일에 대해 해당 수준의 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-115">People can be granted Owner, Member, or Visitor access to a SharePoint site and will have that level of access to files in the site.</span></span>|<span data-ttu-id="de9fc-116">사이트 소유자만 사이트를 공유할 수 있도록 사이트 권한을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-116">Site permissions can be restricted so that only site owners can share the site.</span></span> <span data-ttu-id="de9fc-117">관리자는 사이트를 읽기 전용으로 설정하거나 액세스를 모두 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-117">Admins can set a site to read-only or block access entirely.</span></span>|
|[<span data-ttu-id="de9fc-118">특정 사용자와 공유</span><span class="sxs-lookup"><span data-stu-id="de9fc-118">Sharing with specific people</span></span>](#sharing-with-specific-people)|<span data-ttu-id="de9fc-119">편집 권한이 있는 사이트 구성원과 사용자는 *특정 사용자* 링크를 사용하여 파일 및 폴더에 직접 권한을 부여하거나 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-119">Site members and people with edit permissions can give direct permissions to files and folders or share them by using *Specific people* links.</span></span>|<span data-ttu-id="de9fc-120">사이트 소유자만 파일 및 폴더를 공유할 수 있도록 사이트 권한을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-120">Site permissions can be restricted so that only site owners can share files and folders.</span></span> <span data-ttu-id="de9fc-121">이 경우 사이트 구성원의 직접 액세스 및 *특정 사용자* 링크 공유는 소유자에게 전달되어 승인을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-121">In this case, direct access and *Specific people* link sharing by site members goes to site owner for approval.</span></span>|
|[<span data-ttu-id="de9fc-122">SharePoint 및 OneDrive 게스트 공유</span><span class="sxs-lookup"><span data-stu-id="de9fc-122">SharePoint and OneDrive guest sharing</span></span>](#sharepoint-guest-sharing)|<span data-ttu-id="de9fc-123">SharePoint 사이트 소유자와 구성원 및 Onedrive 소유자는 조직 외부의 사용자와 파일 및 폴더를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-123">SharePoint site owners and members and OneDrive owners can share files and folders with people outside the organization.</span></span>|<span data-ttu-id="de9fc-124">전체 조직 또는 개별 사이트에 대해 게스트 공유 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-124">Guest sharing can be disabled for the entire organization or for individual sites.</span></span>|
|[<span data-ttu-id="de9fc-125">*조직 내부 사용자* 공유 링크</span><span class="sxs-lookup"><span data-stu-id="de9fc-125">*People in your organization* sharing links</span></span>](#people-in-your-organization-sharing-links)|<span data-ttu-id="de9fc-126">SharePoint 사이트 소유자 및 구성원은 *조직 내 사용자* 링크를 사용하여 파일을 공유할 수 있으며, 이는 조직 내부의 모든 사람이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-126">SharePoint site owners and members can share files using *People in your organization* links, which will work for anyone inside the organization.</span></span>|<span data-ttu-id="de9fc-127">사이트 수준에서 *조직의 사용자* 링크를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-127">*People in your organization* links can be disabled at the site level.</span></span>|
|[<span data-ttu-id="de9fc-128">사이트, 그룹 및 팀 공유</span><span class="sxs-lookup"><span data-stu-id="de9fc-128">Create sites, groups, and teams</span></span>](#create-sites-groups-and-teams)|<span data-ttu-id="de9fc-129">기본적으로 사용자는 콘텐츠를 공유할 수 있는 새 사이트, 그룹 및 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-129">By default, users can create new sites, groups, and teams from which they can share content.</span></span>|<span data-ttu-id="de9fc-130">관리자는 사이트, 그룹 및 팀을 만들 수 있는 사람을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-130">Admins can restrict who can create sites, groups, and teams.</span></span>|
|[<span data-ttu-id="de9fc-131">전자 메일</span><span class="sxs-lookup"><span data-stu-id="de9fc-131">Email</span></span>](#email)|<span data-ttu-id="de9fc-132">파일에 대한 액세스 권한이 있는 사용자는 전자 메일을 통해 파일을 다른 사용자에게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-132">People with access to a file can send it to others via email.</span></span>|<span data-ttu-id="de9fc-133">관리자는 민감도 레이블을 사용하여 파일이 권한 없는 사용자와 공유되지 않도록 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-133">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|
|[<span data-ttu-id="de9fc-134">다운로드 또는 파일 복사</span><span class="sxs-lookup"><span data-stu-id="de9fc-134">Download or file copy</span></span>](#download-or-file-copy)|<span data-ttu-id="de9fc-135">파일에 대한 액세스 권한이 있는 사용자는 파일을 다운로드하거나 복사하여 이를 Microsoft 365 범위 밖에 있는 다른 사용자와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-135">People with access to a file can download or copy it and share it with others outside the scope of Microsoft 365.</span></span>|<span data-ttu-id="de9fc-136">관리자는 민감도 레이블을 사용하여 파일이 권한 없는 사용자와 공유되지 않도록 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-136">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|

<span data-ttu-id="de9fc-137">사용자가 공유 콘텐츠에 액세스하는 조건을 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-137">You can also restrict the conditions under which people access shared content.</span></span> <span data-ttu-id="de9fc-138">자세한 내용은 이 문서의 뒷부분에 나오는 [조건부 액세스](#conditional-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-138">See [conditional access](#conditional-access) later in this article for more information.</span></span>

<span data-ttu-id="de9fc-139">이 문서에 설명된 관리 컨트롤을 사용하여 조직의 공유를 제한할 수 있지만 Microsoft 365에서 제공되는 보안 및 규정 준수 기능을 사용하여 안전한 공유 환경을 만드는 것을 고려해 볼 것을 강력히 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-139">While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment.</span></span> <span data-ttu-id="de9fc-140">자세한 내용은 [ Microsoft 365를 사용하여 SharePoint에서 파일 공동 작업](/sharepoint/deploy-file-collaboration) 및 [보안 격리를 사용하여 팀 구성](secure-teams-security-isolation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-140">See [File collaboration in SharePoint with Microsoft 365](/sharepoint/deploy-file-collaboration) and [Configure a team with security isolation](secure-teams-security-isolation.md) for information.</span></span>

<span data-ttu-id="de9fc-141">조직에서 공유를 사용하는 방법을 이해하려면 [파일 및 폴더 공유에 대한 보고서를 실행하세요](/sharepoint/sharing-reports).</span><span class="sxs-lookup"><span data-stu-id="de9fc-141">To understand how sharing is being used in your organization, [run a report on file and folder sharing](/sharepoint/sharing-reports).</span></span>

## <a name="microsoft-365-group-or-team"></a><span data-ttu-id="de9fc-142">Microsoft 365 그룹 또는 팀</span><span class="sxs-lookup"><span data-stu-id="de9fc-142">Microsoft 365 group or team</span></span>

<span data-ttu-id="de9fc-143">Microsoft 365 그룹 또는 Microsoft Teams 팀에서 공유를 제한하려는 경우 그룹 또는 팀을 비공개로 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-143">If you want to limit sharing in a Microsoft 365 group or Microsoft Teams team, it's important to make the group or team private.</span></span> <span data-ttu-id="de9fc-144">조직 내부 사용자는 언제든 지 공용 그룹이나 팀에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-144">People inside your organization can join a public group or team anytime.</span></span> <span data-ttu-id="de9fc-145">그룹이나 팀이 비공개가 아닌 이상, 조직 내에서 팀 또는 해당 파일의 공유를 제한할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-145">Unless the group or team is private, there's no way to limit sharing of the team or its files within the organization.</span></span>

### <a name="guest-sharing"></a><span data-ttu-id="de9fc-146">게스트 공유</span><span class="sxs-lookup"><span data-stu-id="de9fc-146">Guest sharing</span></span>

<span data-ttu-id="de9fc-147">Teams에서 게스트 액세스를 방지하려는 경우 Teams 관리 센터에서 게스트 공유를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-147">If you want to prevent guest access in Teams, you can turn off guest sharing in the Teams admin center.</span></span>

<span data-ttu-id="de9fc-148">Teams에 대해 게스트 공유를 해제하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-148">To turn off guest sharing for Teams</span></span>
1. <span data-ttu-id="de9fc-149">Teams 관리 센터에서 **조직 전체 설정** 을 확장한 다음 **게스트 액세스** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-149">In the Teams admin center, expand **Org-wide settings**, and then click **Guest access**.</span></span>
2. <span data-ttu-id="de9fc-150">**Teams에서 게스트 액세스 허용** 을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-150">Turn off **Allow guest access in Teams**.</span></span>
3. <span data-ttu-id="de9fc-151">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-151">Click **Save**.</span></span>

<span data-ttu-id="de9fc-152">Microsoft 365 그룹에서 게스트 액세스를 방지하려는 경우 Microsoft 365 관리 센터에서 그룹 게스트 액세스 설정을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-152">If you want to prevent guest access in Microsoft 365 Groups, you can turn off the groups guest access settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="de9fc-153">Microsoft 365 그룹에서 게스트 공유를 해제하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-153">To turn off guest sharing in Microsoft 365 Groups</span></span>
1. <span data-ttu-id="de9fc-154">Microsoft 365 관리 센터에서 **설정** 을 클릭한 다음 **조직 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-154">In the Microsoft 365 admin center, click **Settings**, and then click **Org Settings**.</span></span>
2. <span data-ttu-id="de9fc-155">**서비스** 탭에서 **Microsoft 365 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-155">On the **Services** tab, click **Microsoft 365 Groups**.</span></span>
3. <span data-ttu-id="de9fc-156">**조직 외부의 그룹 구성원이 그룹 콘텐츠에 액세스할 수 있도록 허용** 및 **그룹 소유자가 조직 외부의 사람을 그룹에 추가하도록 허용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-156">Clear the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes.</span></span>
4. <span data-ttu-id="de9fc-157">**변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-157">Click **Save changes**.</span></span>

    ![Microsoft 365 관리 센터의 Microsoft 365 그룹 공유 설정 스크린샷](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> <span data-ttu-id="de9fc-159">특정 그룹이나 팀에 대한 게스트 공유를 방지하려는 경우 [Microsoft PowerShell](per-group-guest-access.md) 또는 [민감도 레이블](../compliance/sensitivity-labels-teams-groups-sites.md)을 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-159">If you want to prevent guest sharing for a particular group or team, you can do so by using [Microsoft PowerShell](per-group-guest-access.md) or [sensitivity labels](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="de9fc-160">Azure Active Directory에서 도메인을 허용하거나 차단하여 게스트를 특정 도메인의 사용자로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-160">You can limit guest sharing to users from specific domains by allowing or blocking domains in Azure Active Directory.</span></span> <span data-ttu-id="de9fc-161">[Azure AD B2B를 SharePoint 및 OneDrive와 통합](/sharepoint/sharepoint-azureb2b-integration-preview)을 활성화한 경우 이러한 설정은 SharePoint의 게스트 공유에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-161">This will also affect guest sharing in SharePoint if you have enabled [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="de9fc-162">지정된 도메인에서만 초대를 공유할 수 있도록 허용하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-162">To allow sharing invitations only from specified domains</span></span>
1. <span data-ttu-id="de9fc-163">Azure Active Directory의 개요 페이지에서 **조직 관계** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-163">In Azure Active Directory, on the Overview page, click **Organizational relationships**.</span></span>
2. <span data-ttu-id="de9fc-164">**설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-164">Click **Settings**.</span></span>
3. <span data-ttu-id="de9fc-165">**공동 작업 제한 사항** 에서 **지정된 도메인에 대한 초대 거부** 또는 **지정된 도메인에 대한 초대만 허용** 을 선택한 다음 사용하려는 도메인을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-165">Under **Collaboration restrictions**, select **Deny invitations to the specified domains** or **Allow invitations only to the specified domains**, and then type the domains that you want to use.</span></span>
4. <span data-ttu-id="de9fc-166">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-166">Click **Save**.</span></span>

    ![Azure Active Directory의 공동 작업 제한 설정 스크린샷](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a><span data-ttu-id="de9fc-168">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="de9fc-168">SharePoint site</span></span>

<span data-ttu-id="de9fc-169">SharePoint 사이트 공유를 사이트 소유자에게만 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-169">You can limit SharePoint site sharing to site owners only.</span></span> <span data-ttu-id="de9fc-170">이렇게 하면 사이트 구성원이 사이트를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-170">This prevents site members from sharing the site.</span></span> <span data-ttu-id="de9fc-171">사이트가 Microsoft 365 그룹에 연결된 경우 그룹 구성원은 다른 사람을 그룹에 초대할 수 있으며 해당 사용자는 사이트에 액세스할 수 있음을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-171">Keep in mind that if the site is connected to a Microsoft 365 group, group members can invite others to the group and those users will have site access.</span></span>

<span data-ttu-id="de9fc-172">소유자에게로만 사이트 공유를 제한하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-172">To limit site sharing to owners</span></span>
1. <span data-ttu-id="de9fc-173">사이트에서 톱니바퀴 아이콘을 클릭한 다음 **사이트 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-173">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="de9fc-174">**공유 설정** 에서 **공유 설정 변경** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-174">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="de9fc-175">**사이트 소유자 및 구성원, 편집 권한이 있는 사용자는 파일 및 폴더를 공유할 수 있지만 사이트는 오직 사이트 소유자만 공유** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-175">Select **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>
4. <span data-ttu-id="de9fc-176">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-176">Click **Save**.</span></span>

    ![SharePoint 사이트의 공유 권한 설정의 스크린샷](../media/sharepoint-site-sharing-permissions-level-two.png)

<span data-ttu-id="de9fc-178">액세스 요청을 해제하여 사이트의 구성원이 아닌 사용자가 액세스를 요청하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-178">You can prevent users who are not members of the site from requesting access by turning off access requests.</span></span>

<span data-ttu-id="de9fc-179">액세스 요청을 해제하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-179">To turn off access requests</span></span>
1. <span data-ttu-id="de9fc-180">사이트에서 톱니바퀴 아이콘을 클릭한 다음 **사이트 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-180">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="de9fc-181">**공유 설정** 에서 **공유 설정 변경** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-181">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="de9fc-182">**액세스 요청 허용** 을 해제한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-182">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="de9fc-183">사이트에 대한 도메인을 허용하거나 차단하여 사이트 공유를 특정 도메인으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-183">You can limit site sharing to specific domains by allowing or blocking domains for the site.</span></span>

<span data-ttu-id="de9fc-184">사이트 공유를 도메인별로 제한하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-184">To limit site sharing by domain</span></span>
1. <span data-ttu-id="de9fc-185">SharePoint 관리 센터의 **사이트** 에서 **활성 사이트** 를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-185">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="de9fc-186">동기화할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-186">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="de9fc-187">**정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-187">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="de9fc-188">**외부 공유에 대한 고급 설정** 에서 **도메인별 공유 제한** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-188">Under **Advanced settings for external sharing**, select the **Limit sharing by domain**.</span></span>
5. <span data-ttu-id="de9fc-189">허용하거나 차단할 도메인을 추가하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-189">Add the domains that you want to allow or block, and then click **Save**.</span></span>
6. <span data-ttu-id="de9fc-190">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-190">Click **Save**.</span></span>

    ![허용된 도메인 사이트 수준 설정 스크린샷](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a><span data-ttu-id="de9fc-192">사이트에 대한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="de9fc-192">Block access to a site</span></span>

<span data-ttu-id="de9fc-193">사이트에 대한 액세스를 차단하거나 사이트의 잠금 상태를 변경하여 사이트를 읽기 전용으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-193">You can block access to a site or make a site read-only by changing the lock state of the site.</span></span> <span data-ttu-id="de9fc-194">자세한 내용은 [사이트 잠금 및 잠금 해제](/sharepoint/manage-lock-status)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-194">For details, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

### <a name="permissions-inheritance"></a><span data-ttu-id="de9fc-195">사용 권한 상속</span><span class="sxs-lookup"><span data-stu-id="de9fc-195">Permissions inheritance</span></span>

<span data-ttu-id="de9fc-196">권장되지 않지만, [SharePoint 사용 권한 상속](/sharepoint/what-is-permissions-inheritance)을 사용하여 사이트와 하위 사이트에 대한 액세스 수준을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-196">While not recommended, you can use [SharePoint permissions inheritance](/sharepoint/what-is-permissions-inheritance) to customize access levels to sites and subsites.</span></span>

## <a name="sharing-with-specific-people"></a><span data-ttu-id="de9fc-197">특정 사용자와 공유</span><span class="sxs-lookup"><span data-stu-id="de9fc-197">Sharing with specific people</span></span>

<span data-ttu-id="de9fc-198">사이트 또는 해당 콘텐츠의 공유를 제한하려는 경우 사이트 소유자만 파일, 폴더 및 사이트를 공유하도록 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-198">if you want to limit the sharing of a site or its contents, you can configure the site to only allow site owners to share files, folders, and the site.</span></span> <span data-ttu-id="de9fc-199">이러한 내용이 구성되면 사이트 구성원이 *특정 사용자* 링크를 사용하여 파일 또는 폴더를 공유하려는 시도가 승인을 위해 사이트 소유자에게 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-199">When this is configured, site members' attempts to share files or folders by using *Specific people* links will go to the site owner for approval.</span></span>

<span data-ttu-id="de9fc-200">사이트, 파일 및 폴더 공유를 소유자에게로만 제한하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-200">To limit site, file, and folder sharing to owners</span></span>
1. <span data-ttu-id="de9fc-201">사이트에서 톱니바퀴 아이콘을 클릭한 다음 **사이트 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-201">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="de9fc-202">**공유 설정** 에서 **공유 설정 변경** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-202">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="de9fc-203">**오직 사이트 소유자만 파일, 폴더 및 사이트를 공유** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-203">Select **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="de9fc-204">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-204">Click **Save**.</span></span>

    ![SharePoint 사이트에서 공유 사용 권한 설정이 소유자 전용으로 설정된 스크린샷](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a><span data-ttu-id="de9fc-206">SharePoint 게스트 공유</span><span class="sxs-lookup"><span data-stu-id="de9fc-206">SharePoint guest sharing</span></span>

<span data-ttu-id="de9fc-207">조직 외부 사람과 SharePoint 또는 OneDrive 파일 및 폴더를 공유하지 못하게 하려면 전체 조직 또는 개별 사이트에 대한 게스트 공유를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-207">If you want to prevent sharing SharePoint or OneDrive files and folders with people outside your organization, you can turn off guest sharing for the entire organization or for an individual site.</span></span>

<span data-ttu-id="de9fc-208">조직에 대한 SharePoint 게스트 공유를 끄려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-208">To turn off SharePoint guest sharing for your organization</span></span>
1. <span data-ttu-id="de9fc-209">SharePoint 관리 센터의 **정책** 에서 **공유** 를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-209">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="de9fc-210">**외부 공유** 에서 SharePoint 슬라이더를 아래쪽에 있는 **조직의 사용자에게만** 으로 드래그합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-210">Under **External sharing**, drag the SharePoint slider down to **Only people in your organization**.</span></span>
3. <span data-ttu-id="de9fc-211">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-211">Click **Save**.</span></span>

    ![SharePoint 조직 수준 공유 설정이 누구나로 설정된 스크린샷](../media/sharepoint-tenant-sharing-off.png)


<span data-ttu-id="de9fc-213">사이트에 대해 게스트 공유를 해제하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-213">To turn off guest sharing for a site</span></span>
1. <span data-ttu-id="de9fc-214">SharePoint 관리 센터의 **사이트** 에서 **활성 사이트** 를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-214">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="de9fc-215">동기화할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-215">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="de9fc-216">**정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-216">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="de9fc-217">**외부 공유** 에서 **조직의 사용자에게만** 을 선택한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-217">Under **External sharing**, choose **Only people in your organization**, and then click **Save**.</span></span>

    ![SharePoint 사이트 수준 공유 설정이 조직 내의 사용자만으로 설정된 스크린샷](../media/sharepoint-site-external-sharing-settings-off.png)

<span data-ttu-id="de9fc-219">Microsoft 365 관리 센터에서 사용자를 클릭하고 **OneDrive** 탭에서 **외부 공유 관리** 를 선택하여 개별 OneDrive에 대한 게스트 공유를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-219">You can turn off guest sharing for an individual OneDrive by clicking the user in the Microsoft 365 admin center and selecting **Manage external sharing** on the **OneDrive** tab.</span></span>

<span data-ttu-id="de9fc-220">조직 외부의 사람들과의 공유를 허용하지만 모든 사람이 인증을 받도록 하려면 전체 조직 또는 개별 사이트에 대해 *모든 사용자*(익명 공유) 링크를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-220">If you would like to allow sharing with people outside your organization but you want to make sure that everyone authenticates, you can disable *Anyone* (anonymous sharing) links for the entire organization or for an individual site.</span></span>

<span data-ttu-id="de9fc-221">조직 수준에서 *모든 사용자* 링크를 해제하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-221">To turn off *Anyone* links at the organization level</span></span>
1. <span data-ttu-id="de9fc-222">SharePoint 관리 센터의 **정책** 에서 **공유** 를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-222">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="de9fc-223">**외부 공유** 에서 SharePoint 슬라이더를 아래쪽에 있는 **신규 및 기존 게스트** 로 드래그합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-223">Under **External sharing**, drag the SharePoint slider down to **New and existing guests**.</span></span>
3. <span data-ttu-id="de9fc-224">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-224">Click **Save**.</span></span>

    ![SharePoint 조직 수준 공유 설정이 신규 및 기존 게스트로 설정된 스크린샷](../media/sharepoint-guest-sharing-new-existing-guests.png)

<span data-ttu-id="de9fc-226">사이트에 대해 *Anyone* 링크를 해제하려면</span><span class="sxs-lookup"><span data-stu-id="de9fc-226">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="de9fc-227">SharePoint 관리 센터의 **사이트** 에서 **활성 사이트** 를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="de9fc-227">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="de9fc-228">동기화할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-228">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="de9fc-229">**정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-229">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="de9fc-230">**외부 공유** 에서 OneDrive에 대한 **신규 및 기존 게스트** 를 선택한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-230">Under **External sharing**, choose **New and existing guests**, and then click **Save**.</span></span>

    ![SharePoint 사이트 수준 공유 설정이 신규 및 기존 설정으로 설정된 스크린샷](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a><span data-ttu-id="de9fc-232">*조직 내부 사용자* 공유 링크</span><span class="sxs-lookup"><span data-stu-id="de9fc-232">*People in your organization* sharing links</span></span>

<span data-ttu-id="de9fc-233">기본적으로 사이트 회원은 *조직 내 사용자* 링크를 사용하여 조직의 다른 사람과 파일 및 폴더를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-233">By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link.</span></span> <span data-ttu-id="de9fc-234">PowerShell을 사용하여 *조직 내 사용자* 링크를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-234">You can disable *People in your organization* links by using PowerShell:</span></span>

```powershell
Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks
```

<span data-ttu-id="de9fc-235">예제:</span><span class="sxs-lookup"><span data-stu-id="de9fc-235">For example:</span></span>

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks
```

## <a name="create-sites-groups-and-teams"></a><span data-ttu-id="de9fc-236">사이트, 그룹 및 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="de9fc-236">Create sites, groups, and teams</span></span>

<span data-ttu-id="de9fc-237">기본적으로, 공유 설정에 따라 콘텐츠를 공유할 수 있는 새 사이트, 그룹 및 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-237">By default, users can create new sites, groups, and teams from which they may be able to share content (depending on your sharing settings).</span></span> <span data-ttu-id="de9fc-238">사이트, 그룹 및 팀을 만들 수 있는 사람을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-238">You can restrict who can create sites, groups, and teams.</span></span> <span data-ttu-id="de9fc-239">다음 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-239">See the following references:</span></span>

- [<span data-ttu-id="de9fc-240">SharePoint에서 사이트 만들기 관리</span><span class="sxs-lookup"><span data-stu-id="de9fc-240">Manage site creation in SharePoint</span></span>](/sharepoint/manage-site-creation)
- [<span data-ttu-id="de9fc-241">Microsoft 365 그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="de9fc-241">Manage who can create Microsoft 365 Groups</span></span>](./manage-creation-of-groups.md)

> [!NOTE]
> <span data-ttu-id="de9fc-242">그룹 만들기를 제한하면 팀 만들기가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-242">Restricting group creation restricts team creation.</span></span>

## <a name="email"></a><span data-ttu-id="de9fc-243">전자 메일</span><span class="sxs-lookup"><span data-stu-id="de9fc-243">Email</span></span>

<span data-ttu-id="de9fc-244">암호화를 사용하여 전자 메일이 의도하지 않게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-244">You can prevent unwanted sharing of emails by using encryption.</span></span> <span data-ttu-id="de9fc-245">따라서 전자 메일이 전달되거나 허가되지 않은 사용자에게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-245">This prevents emails being forwarded or otherwise shared with unauthorized users.</span></span> <span data-ttu-id="de9fc-246">민감도 레이블을 사용하여 전자 메일 암호화를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-246">Email encryption can be enabled by using sensitivity labels.</span></span> <span data-ttu-id="de9fc-247">자세한 내용은 [민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한](../compliance/encryption-sensitivity-labels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-247">See [Restrict access to content by using encryption in sensitivity labels](../compliance/encryption-sensitivity-labels.md) for details.</span></span>

## <a name="download-or-file-copy"></a><span data-ttu-id="de9fc-248">다운로드 또는 파일 복사</span><span class="sxs-lookup"><span data-stu-id="de9fc-248">Download or file copy</span></span>

<span data-ttu-id="de9fc-249">Microsoft 365의 파일 및 폴더에 대한 액세스 권한이 있는 사용자는 파일을 다운로드하고 외부 미디어에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-249">Users who have access to files and folders in Microsoft 365 can download files and copy them to external media.</span></span> <span data-ttu-id="de9fc-250">원치 않는 파일이 공유되는 위험을 줄이기 위해 민감도 레이블을 사용하여 콘텐츠를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-250">To reduce the risk of unwanted file sharing, you can encrypt the content by using sensitivity labels.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="de9fc-251">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="de9fc-251">Conditional access</span></span>

<span data-ttu-id="de9fc-252">Azure Active Directory 조건부 액세스에서는 네트워크 위치, 장치 상태, 로그인 위험 및 기타 요소를 기준으로 사용자와의 공유를 제한하거나 방지할 수 있는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-252">Azure Active Directory conditional access provides options to limit or prevent sharing with people based on network location, device health, sign-in risk, and other factors.</span></span> <span data-ttu-id="de9fc-253">[조건부 액세스란?](/azure/active-directory/conditional-access/overview)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-253">See [What is Conditional Access?](/azure/active-directory/conditional-access/overview).</span></span>

<span data-ttu-id="de9fc-254">SharePoint에서는 관리되지 않는 장치와 네트워크 위치를 위해 Azure AD 조건부 액세스와 직접 통합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de9fc-254">SharePoint provides direct integration with Azure AD conditional access for both unmanaged devices and network location.</span></span> <span data-ttu-id="de9fc-255">자세한 내용은 다음 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de9fc-255">See the following references for details:</span></span>

- [<span data-ttu-id="de9fc-256">관리되지 않는 장치에서 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="de9fc-256">Control access from unmanaged devices</span></span>](/sharepoint/control-access-from-unmanaged-devices)
- [<span data-ttu-id="de9fc-257">네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="de9fc-257">Control access to SharePoint and OneDrive data based on network location</span></span>](/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a><span data-ttu-id="de9fc-258">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de9fc-258">See also</span></span>

[<span data-ttu-id="de9fc-259">Microsoft 365 게스트 공유 설정 참조</span><span class="sxs-lookup"><span data-stu-id="de9fc-259">Microsoft 365 guest sharing settings reference</span></span>](microsoft-365-guest-settings.md)
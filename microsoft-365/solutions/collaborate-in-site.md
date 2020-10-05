---
title: 게스트와 현장에서 공동 작업하기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 게스트가 포함 된 공동 작업을 위해 SharePoint 사이트를 설정 하는 데 필요한 Microsoft 365 구성 단계에 대해 설명 합니다.
ms.openlocfilehash: 4f4b87a02c3ff3a1a7997aee69e3e1e95e4b2ed5
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357997"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="dcb85-103">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="dcb85-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="dcb85-104">여러 문서, 데이터 및 목록에서 게스트와 공동 작업을 수행 해야 하는 경우에는 SharePoint 사이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="dcb85-105">최신 SharePoint 사이트는 Microsoft 365 그룹에 연결 되며, 사이트 구성원 자격을 관리 하 고 공유 사서함 및 일정과 같은 추가 공동 작업 도구를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="dcb85-106">이 문서에서는 게스트가 포함 된 공동 작업을 위해 SharePoint 사이트를 설정 하는 데 필요한 Microsoft 365 구성 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="dcb85-107">비디오 데모</span><span class="sxs-lookup"><span data-stu-id="dcb85-107">Video demonstration</span></span>

<span data-ttu-id="dcb85-108">이 비디오에서는이 문서에서 설명 하는 구성 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="dcb85-109">Azure 외부 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="dcb85-109">Azure external collaboration settings</span></span>

<span data-ttu-id="dcb85-110">Microsoft 365의 공유는 [Azure Active Directory의 조직 관계 설정](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)에 따라 최상위 수준에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="dcb85-111">Azure AD에서 게스트 공유가 사용 하지 않도록 설정 되거나 제한 되 면 Microsoft 365에서 구성한 모든 공유 설정이 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="dcb85-112">외부 공동 작업 설정을 확인 하 여 게스트가 공유 하는 것이 차단 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 외부 공동 작업 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="dcb85-114">외부 공동 작업 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-114">To set external collaboration settings:</span></span>


1. <span data-ttu-id="dcb85-115">Microsoft Azure에 로그인 [https://portal.azure.com](https://portal.azure.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="dcb85-116">왼쪽 탐색 창에서 **Azure Active Directory**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="dcb85-117">**외부 id** 를 선택 하 고 **외부 공동 작업 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-117">Select **External Identities** and click on **External collaboration settings**.</span></span>
4. <span data-ttu-id="dcb85-118">**게스트 초대 설정** 창에서 **guest Inviter 역할의 관리자 및 사용자가 초대** 하 고 **구성원을 초대할** 수 있는지 확인 하 고 둘 다 **예**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-118">In the **Guest invite settings** pane, ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
5. <span data-ttu-id="dcb85-119">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="dcb85-120">**공동 작업 제한** 섹션의 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="dcb85-121">공동 작업 하려는 게스트의 도메인이 차단 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="dcb85-122">여러 조직의 게스트 작업을 수행 하는 경우 디렉터리 데이터에 대 한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="dcb85-123">이렇게 하면 디렉터리에서 게스트에 해당 하는 사람을 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="dcb85-124">이 작업을 수행 하려면 **게스트 사용자 액세스 제한**에서 게스트 사용자는 **속성에 대 한 제한 된 액세스 및 디렉터리 개체 설정의 멤버 자격** 을 선택 하거나 **게스트 사용자 액세스를 자체 디렉터리 개체의 속성 및 구성원으로 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="dcb85-125">Microsoft 365 Groups 게스트 설정</span><span class="sxs-lookup"><span data-stu-id="dcb85-125">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="dcb85-126">최신 SharePoint 사이트에서는 Microsoft 365 그룹을 사용 하 여 사이트 액세스를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-126">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="dcb85-127">SharePoint 사이트에서 게스트 액세스를 사용 하려면 Microsoft 365 Groups 게스트 설정이 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-127">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="dcb85-129">Microsoft 365 그룹 게스트 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-129">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="dcb85-130">Microsoft 365 관리 센터의 왼쪽 탐색 영역에서 **설정을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-130">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="dcb85-131">**서비스 & 추가 기능**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-131">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="dcb85-132">목록에서 **Microsoft 365 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-132">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="dcb85-133">**조직 외부 구성원이 그룹 콘텐츠에 액세스** 하 고 그룹 **소유자가 조직 외부의 사람을 그룹에 추가** 하도록 허용 확인란을 모두 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-133">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="dcb85-134">변경한 경우 **변경 내용 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-134">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="dcb85-135">SharePoint 조직 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="dcb85-135">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="dcb85-136">게스트가 SharePoint 사이트에 액세스할 수 있도록 하려면 SharePoint 조직 수준 공유 설정에서 guests 공유를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-136">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="dcb85-137">조직 수준 설정에 따라 개별 사이트에 사용할 수 있는 설정이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-137">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="dcb85-138">사이트 설정은 조직 수준 설정 보다는 더 이상 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-138">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="dcb85-139">인증 되지 않은 파일 및 폴더 공유를 허용 하려면 **모든 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-139">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="dcb85-140">조직 외부의 모든 사용자가 인증을 받아야 하는 것을 확인 하려면 **신규 및 기존 게스트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-140">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="dcb85-141">조직의 모든 사이트에 필요한 가장 관대 한 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-141">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="dcb85-143">SharePoint 조직 수준 공유 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-143">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="dcb85-144">Microsoft 365 관리 센터의 왼쪽 탐색에 있는 **관리 센터**에서 **SharePoint**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-144">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="dcb85-145">왼쪽 탐색 창의 SharePoint 관리 센터에서 **공유**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-145">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="dcb85-146">SharePoint 용 외부 공유가 **사용자** 또는 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-146">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="dcb85-147">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-147">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="dcb85-148">사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="dcb85-148">Create a site</span></span>

<span data-ttu-id="dcb85-149">다음 단계는 게스트와 공동 작업 하는 데 사용할 사이트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-149">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="dcb85-150">사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-150">To create a site</span></span>
1. <span data-ttu-id="dcb85-151">SharePoint 관리 센터의 **사이트**에서 **활성 사이트**를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="dcb85-151">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="dcb85-152">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-152">Click **Create**.</span></span>
3. <span data-ttu-id="dcb85-153">**팀 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-153">Click **Team site**.</span></span>
4. <span data-ttu-id="dcb85-154">사이트 이름을 입력 하 고 그룹 소유자 (사이트 소유자)의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-154">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="dcb85-155">**고급 설정**에서이 사이트를 공용 또는 개인 사이트로 설정할 것인지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-155">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="dcb85-156">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-156">Click **Next**.</span></span>
7. <span data-ttu-id="dcb85-157">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-157">Click **Finish**.</span></span>

<span data-ttu-id="dcb85-158">나중에 사용자를 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-158">We'll invite users later.</span></span> <span data-ttu-id="dcb85-159">다음으로이 사이트에 대 한 사이트 수준 공유 설정을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-159">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="dcb85-160">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="dcb85-160">SharePoint site level sharing settings</span></span>

<span data-ttu-id="dcb85-161">사이트 수준 공유 설정을 확인 하 여 해당 사이트에 대해 원하는 액세스 유형을 허용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-161">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="dcb85-162">예를 들어 조직 수준 설정을 모든 **사용자**로 설정 했지만 모든 게스트가이 사이트에 대해 인증을 받으려는 경우에는 사이트 수준 공유 설정이 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-162">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="dcb85-163">사이트를 인증 되지 않은 사용자 (**사용자** 설정)와 공유할 수는 없지만 개별 파일 및 폴더를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-163">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="dcb85-165">사이트 수준 공유 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-165">To set site-level sharing settings</span></span>
1. <span data-ttu-id="dcb85-166">SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트**를 확장시키고 **Active 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-166">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="dcb85-167">방금 만든 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-167">Select the site that you just created.</span></span>
3. <span data-ttu-id="dcb85-168">리본 메뉴에서 **공유**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-168">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="dcb85-169">공유가 **사용자** 또는 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-169">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="dcb85-170">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-170">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="dcb85-171">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="dcb85-171">Invite users</span></span>

<span data-ttu-id="dcb85-172">게스트 공유 설정이 이제 구성 되므로 사이트에 내부 사용자 및 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-172">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="dcb85-173">사이트 액세스는 연결 된 Microsoft 365 그룹을 통해 제어 되므로 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-173">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="dcb85-174">그룹에 내부 사용자를 초대 하려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-174">To invite internal users to a group</span></span>
1. <span data-ttu-id="dcb85-175">사용자를 추가 하려는 사이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-175">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="dcb85-176">오른쪽 위에 있는 **구성원** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-176">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="dcb85-177">**구성원 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-177">Click **Add members**.</span></span>
4. <span data-ttu-id="dcb85-178">사이트에 초대할 사용자의 이름 또는 전자 메일 주소를 입력 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-178">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="dcb85-179">게스트 사용자는 사이트에서 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-179">Guest users can't be added from the site.</span></span> <span data-ttu-id="dcb85-180">웹에서 Outlook을 사용 하 여 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-180">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="dcb85-181">그룹에 게스트를 초대 하려면</span><span class="sxs-lookup"><span data-stu-id="dcb85-181">To invite guests to a group</span></span>
1. <span data-ttu-id="dcb85-182">웹용 Outlook의 **그룹**에서 구성원을 추가 하려는 그룹을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-182">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="dcb85-183">그룹 대화 상대 카드를 열고 **기타 옵션** (...)에서 **구성원 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-183">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="dcb85-184">초대 하려는 게스트의 전자 메일 주소를 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-184">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="dcb85-185">**닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcb85-185">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcb85-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcb85-186">See Also</span></span>

[<span data-ttu-id="dcb85-187">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="dcb85-187">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="dcb85-188">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="dcb85-188">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="dcb85-189">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="dcb85-189">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="dcb85-190">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="dcb85-190">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="dcb85-191">Azure AD B2B와의 SharePoint 및 OneDrive 통합</span><span class="sxs-lookup"><span data-stu-id="dcb85-191">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 게스트와 공동 작업하기 위해 Microsoft 365 사이트 설정에 필요한 SharePoint 구성 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539254"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="307bc-103">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="307bc-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="307bc-104">문서, 데이터 및 목록에서 게스트와 공동 작업을 해야 하는 경우 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="307bc-105">최신 SharePoint 사이트는 Microsoft 365 그룹에 연결되고 사이트 구성원을 관리하고 공유 사서함 및 일정과 같은 추가 공동 작업 도구를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="307bc-106">이 문서에서는 게스트와 공동 작업을 위해 Microsoft 365 사이트 설정에 필요한 SharePoint 구성 단계를 단계적으로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="307bc-107">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="307bc-107">Video demonstration</span></span>

<span data-ttu-id="307bc-108">이 비디오에서는 이 문서에서 설명한 구성 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="307bc-109">Azure 외부 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="307bc-109">Azure external collaboration settings</span></span>

<span data-ttu-id="307bc-110">Microsoft 365의 공유는 [Azure Active Directory의 B2B 외부 공동 작업 설정](/azure/active-directory/external-identities/delegate-invitations)에 따라 가자 높은 수준에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="307bc-111">Azure AD에서 게스트 공유가 비활성화되거나 제한된 경우 이 설정은 Microsoft 365에서 구성하는 모든 공유 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="307bc-112">B2B 외부 공동 작업 설정을 확인하여 게스트와의 공유가 차단되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot of Azure Active Directory External collaboration 설정 page](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="307bc-114">외부 공동 작업 설정을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="307bc-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="307bc-115">[https://aad.portal.azure.com](https://aad.portal.azure.com)에서 Azure Active Directory에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="307bc-116">왼쪽 탐색 창에서 **Azure Active Directory** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="307bc-117">**외부 ID** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-117">Click **External identities**.</span></span>
4. <span data-ttu-id="307bc-118">**시작** 화면의 왼쪽 탐색 창에서 **외부 동 작업 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="307bc-119">**게스트 초대자 역할의 관리자 및 사용자가 초대할 수 있음** 및 **구성원이 초대할 수 있음** 이 모두 **예** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="307bc-120">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="307bc-121">**공동 작업 제한** 섹션의 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="307bc-122">공동 작업하려는 게스트의 도메인이 차단되지 않았는지 합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="307bc-123">여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="307bc-124">이 작업을 수행하면 게스트가 디렉터리에 다른 게스트가 누구인지 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="307bc-125">이 작업을 수행하려면, **게스트 사용자 액세스 제한** 아래에서 **디렉터리 개체 설정의 속성 및 멤버십에 대한 게스트 사용자의 액세스가 제한됨** 또는 **게스트 사용자 액세스가 해당 디렉터리 개체의 속성 및 멤버십으로 제한됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="307bc-126">Microsoft 365 그룹 게스트 설정</span><span class="sxs-lookup"><span data-stu-id="307bc-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="307bc-127">최신 SharePoint 사이트는 Microsoft 365 그룹을 사용하여 사이트 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="307bc-128">Microsoft 365 사이트의 게스트 액세스가 작동하려면 SharePoint 그룹 게스트 설정을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="307bc-130">Microsoft 365 Groups 게스트 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="307bc-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="307bc-131">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정** 을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="307bc-132">**조직 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="307bc-133">목록에서 **Microsoft 365 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="307bc-134">**그룹 소유자가 조직 외부의 사용자를 Microsoft 365 그룹에 게스트로 추가하도록 허용** 및 **게스트 그룹 구성원이 그룹 콘텐츠에 액세스하도록 허용** 확인란이 모두 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="307bc-135">변경한 내용이 있으면 **변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="307bc-136">SharePoint 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="307bc-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="307bc-137">게스트가 SharePoint 액세스할 수 있도록 SharePoint 조직 수준 공유 설정에서 게스트와 공유할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="307bc-138">조직 수준 설정에 따라 개별 사이트에 사용할 수 있는 설정이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="307bc-139">사이트 설정은 조직 수준 설정보다 더 제한될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="307bc-140">허용되지 않은 파일 및 폴더 공유를 허용하려는 경우 모든 사람을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="307bc-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="307bc-141">조직 외부의 모든 사용자가 인증을 하도록 하려는 경우 신규 및 기존 게스트 **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="307bc-142">조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="307bc-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="307bc-144">SharePoint 조직 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="307bc-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="307bc-145">Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="307bc-146">SharePoint 관리 센터의 왼쪽 탐색 창에 있는 **정책에서** 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="307bc-147">SharePoint에 대한 외부 공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="307bc-148">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="307bc-149">사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="307bc-149">Create a site</span></span>

<span data-ttu-id="307bc-150">다음 단계는 게스트와 공동 작업하는 데 사용할 사이트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="307bc-151">사이트를 만들 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="307bc-151">To create a site</span></span>
1. <span data-ttu-id="307bc-152">SharePoint 관리 센터의 **사이트** 에서 **활성 사이트** 를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="307bc-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="307bc-153">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-153">Click **Create**.</span></span>
3. <span data-ttu-id="307bc-154">팀 **사이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-154">Click **Team site**.</span></span>
4. <span data-ttu-id="307bc-155">사이트 이름을 입력하고 그룹 소유자(사이트 소유자)의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="307bc-156">고급 **설정에서** 이 사이트를 공용 또는 개인 사이트로 사용할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="307bc-157">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-157">Click **Next**.</span></span>
7. <span data-ttu-id="307bc-158">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-158">Click **Finish**.</span></span>

<span data-ttu-id="307bc-159">나중에 사용자를 초대할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-159">We'll invite users later.</span></span> <span data-ttu-id="307bc-160">다음으로, 이 사이트의 사이트 수준 공유 설정을 점검해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="307bc-161">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="307bc-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="307bc-162">사이트 수준 공유 설정을 확인하여 이 사이트에 대해 원하는 액세스 유형을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="307bc-163">예를 들어 조직 수준 설정을 **모든** 사용자로 설정했지만 모든 게스트가 이 사이트에 대해 인증을 하려는 경우 사이트 수준 공유 설정이 신규 및 기존 게스트로 설정되어 있는지 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="307bc-164">사이트는 모든 사용자(모든 사용자 설정)와 공유할 수 없지만 개별 파일 및 폴더는 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="307bc-165">민감도 레이블을 사용하여 사이트의 외부 공유 [설정을 SharePoint 있습니다.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="307bc-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="307bc-167">사이트 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="307bc-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="307bc-168">SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트** 를 확장시키고 **Active 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="307bc-169">공유할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="307bc-170">...를 클릭하고 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="307bc-171">공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="307bc-172">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="307bc-173">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="307bc-173">Invite users</span></span>

<span data-ttu-id="307bc-174">이제 게스트 공유 설정이 구성되어 내부 사용자 및 게스트를 사이트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="307bc-175">사이트 액세스는 연결된 Microsoft 365 통해 제어되어 있으므로 여기에 사용자를 추가할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="307bc-176">내부 사용자를 그룹에 초대</span><span class="sxs-lookup"><span data-stu-id="307bc-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="307bc-177">사용자를 추가할 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="307bc-178">오른쪽 **상단에서** 구성원 수를 나타 내는 구성원 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="307bc-179">**구성원 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-179">Click **Add members**.</span></span>
4. <span data-ttu-id="307bc-180">사이트에 초대할 사용자의 이름 또는 전자 메일 주소를 입력한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="307bc-181">사이트에서 게스트를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-181">Guests can't be added from the site.</span></span> <span data-ttu-id="307bc-182">웹용 웹 응용 Outlook 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="307bc-183">따라서 게스트를 그룹에 추가하고 그룹에 초대하려면 URL 열에서 사이트의 **URL을**  클릭하여 사이트별 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="307bc-184">이 페이지에서 앱 시작 **프로그램** 아이콘을 클릭하고 를 **Outlook.**</span><span class="sxs-lookup"><span data-stu-id="307bc-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="307bc-185">아래 절차에 설명된 그룹으로 게스트를 초대할 수 있는 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="307bc-186">게스트를 그룹에 초대</span><span class="sxs-lookup"><span data-stu-id="307bc-186">To invite guests to a group</span></span>
1. <span data-ttu-id="307bc-187">**그룹에서** 게스트를 초대할 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="307bc-188">그룹 연락처 카드를 열고 오른쪽 위에 있는 구성원 링크(구성원 수를 나타 내는 링크)를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="307bc-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="307bc-189">구성원 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-189">click **Add members**.</span></span>
4. <span data-ttu-id="307bc-190">초대할 게스트의 전자 메일 주소를 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="307bc-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="307bc-191">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-191">Click **Close**.</span></span>
<span data-ttu-id="307bc-192">그룹의 소유자가 아니며 그 결과 게스트를 그룹에 추가할 수 없는 경우 닫기만 클릭해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="307bc-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="307bc-193">이 경우 그룹에 게스트를 추가하는 요청은 승인을 위해 그룹 소유자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="307bc-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="307bc-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="307bc-194">See also</span></span>

[<span data-ttu-id="307bc-195">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="307bc-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="307bc-196">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="307bc-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="307bc-197">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="307bc-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="307bc-198">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="307bc-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="307bc-199">Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="307bc-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)
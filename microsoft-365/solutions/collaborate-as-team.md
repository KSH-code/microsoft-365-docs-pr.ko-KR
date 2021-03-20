---
title: 게스트와 팀으로 공동 작업하기
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: Teams에서 게스트와 작업, 대화 및 문서 공동 작업을 위한 팀을 설정하는 데 필요한 Microsoft 365 구성 단계에 대해 자세히 알아보세요.
ms.openlocfilehash: 4e734af198563d0bc4599b4476b3823384989212
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904663"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="661ba-103">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="661ba-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="661ba-104">문서, 작업 및 대화에서 게스트와 공동 작업해야 하는 경우 Microsoft Teams를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="661ba-105">Teams는 Office 및 SharePoint에서 사용할 수 있는 모든 공동 작업 기능과 지속적인 채팅을 통해 통합된 사용자 환경에서 사용자 지정 가능하고 배율 가능한 공동 작업 도구 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="661ba-106">이 문서에서는 게스트와 공동 작업할 팀을 설정하는 데 필요한 Microsoft 365 구성 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="661ba-107">게스트 액세스를 구성한 후 [Teams에서 팀에 게스트를 추가](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)하는 단계에 따라 팀에 게스트를 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="661ba-108">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="661ba-108">Video demonstration</span></span>

<span data-ttu-id="661ba-109">이 비디오에서는 이 문서에서 설명한 구성 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="661ba-110">Azure 외부 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="661ba-110">Azure External collaboration settings</span></span>

<span data-ttu-id="661ba-111">Microsoft 365의 공유는 [Azure Active Directory의 B2B 외부 공동 작업 설정](/azure/active-directory/external-identities/delegate-invitations)에 따라 가자 높은 수준에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="661ba-112">Azure AD에서 게스트 공유가 비활성화되거나 제한된 경우 이 설정은 Microsoft 365에서 구성하는 모든 공유 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="661ba-113">게스트와의 공유가 차단되지 않도록 B2B 외부 공동 작업 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 조직 관계 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="661ba-115">외부 공동 작업 설정을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="661ba-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="661ba-116">[https://aad.portal.azure.com](https://aad.portal.azure.com)에서 Azure Active Directory에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="661ba-117">왼쪽 탐색 창에서 **Azure Active Directory** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="661ba-118">**외부 ID** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-118">Click **External identities**.</span></span>
4. <span data-ttu-id="661ba-119">**시작** 화면의 왼쪽 탐색 창에서 **외부 동 작업 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="661ba-120">**게스트 초대자 역할의 관리자 및 사용자가 초대할 수 있음** 및 **구성원이 초대할 수 있음** 이 모두 **예** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="661ba-121">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="661ba-122">**공동 작업 제한** 섹션의 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="661ba-123">공동 작업하려는 게스트의 도메인이 차단되지 않았는지 합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="661ba-124">여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="661ba-125">이 작업을 수행하면 게스트가 디렉터리에 다른 게스트가 누구인지 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="661ba-126">이 작업을 수행하려면, **게스트 사용자 액세스 제한** 아래에서 **디렉터리 개체 설정의 속성 및 멤버십에 대한 게스트 사용자의 액세스가 제한됨** 또는 **게스트 사용자 액세스가 해당 디렉터리 개체의 속성 및 멤버십으로 제한됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="661ba-127">Teams 게스트 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="661ba-127">Teams guest access settings</span></span>

<span data-ttu-id="661ba-128">Teams에는 게스트 액세스에 대한 마스터 켜기/끄기 스위치와 게스트가 팀에서 할 수 있는 작업을 제어할 수 있는 다양한 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="661ba-129">마스터 스위치인 **Teams에서 게스트 액세스 허용** 은 게스트 액세스가 Teams에서 작동하기 위해 반드시 **켜짐** 상태가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="661ba-130">Teams에서 게스트 액세스를 사용하도록 설정하고 비즈니스 요구에 따라 게스트 설정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="661ba-131">이러한 설정은 모든 팀에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-131">Keep in mind that these settings affect all teams.</span></span>

![Teams의 게스트 액세스 토글의 스크린샷](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="661ba-133">Teams 게스트 액세스를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="661ba-134">[https://admin.microsoft.com](https://admin.microsoft.com)에서 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="661ba-135">왼쪽 탐색 창에서 **모두 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="661ba-136">**관리 센터** 에서 **Teams** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="661ba-137">Teams 관리 센터의 왼쪽 탐색 창에서 **조직 전체 설정** 을 확장한 다음 **게스트 액세스** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="661ba-138">Teams의 **게스트 액세스 허용** 이 **사용** 으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="661ba-139">추가 게스트 설정을 원하는대로 변경 한 다음 **저장** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="661ba-140">Teams 게스트 액세스가 설정되어 있는 경우, 민감도 레이블을 사용하여 선택적으로 개별 팀 및 관련 SharePoint 사이트에 대한 게스트 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="661ba-141">자세한 내용은 [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호](../compliance/sensitivity-labels-teams-groups-sites.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="661ba-142">Teams 게스트 설정을 켠 후 활성화되려면 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="661ba-143">Microsoft 365 그룹 게스트 설정</span><span class="sxs-lookup"><span data-stu-id="661ba-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="661ba-144">Teams는 팀 멤버십을 위해 Microsoft 365 그룹을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="661ba-145">Teams에서 게스트 액세스가 작동하려면 Microsoft 365 그룹 게스트 설정이 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="661ba-147">Microsoft 365 Groups 게스트 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="661ba-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="661ba-148">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정** 을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="661ba-149">**조직 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="661ba-150">목록에서 **Microsoft 365 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="661ba-151">**그룹 소유자가 조직 외부의 사용자를 Microsoft 365 그룹에 게스트로 추가하도록 허용** 및 **게스트 그룹 구성원이 그룹 콘텐츠에 액세스하도록 허용** 확인란이 모두 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="661ba-152">변경한 내용이 있으면 **변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="661ba-153">SharePoint 조직 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="661ba-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="661ba-154">파일, 폴더, 목록 등의 Teams 콘텐츠는 모두 SharePoint에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="661ba-155">게스트가 Teams에서 이러한 항목에 액세스할 수 있도록 허용하려면 SharePoint 조직 수준 공유 설정에서 게스트와 공유를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="661ba-156">조직 수준 설정에 따라 팀과 연결된 사이트를 포함하여 개별 사이트에 사용할 수 있는 설정이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="661ba-157">사이트 설정은 조직 수준 설정보다 더 제한될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="661ba-158">사용자와 파일 및 폴더 공유를 허용하려는 경우,**모든 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="661ba-159">모든 게스트가 인증해야 하는지 확인하려는 경우 **새 게스트 및 기존 게스트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="661ba-160">조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="661ba-162">SharePoint 조직 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="661ba-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="661ba-163">Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="661ba-164">SharePoint 관리 센터의 왼쪽 탐색 창에서 **정책** 을 확장한 다음, **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="661ba-165">SharePoint에 대한 외부 공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="661ba-166">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="661ba-167">SharePoint 조직 수준 기본 링크 설정</span><span class="sxs-lookup"><span data-stu-id="661ba-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="661ba-168">기본 파일 및 폴더 링크 설정에 따라 사용자가 파일 또는 폴더를 공유할 때 기본적으로 사용자에게 표시되는 링크 옵션이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="661ba-169">원하는 경우 공유하기 전에 링크 유형을 다른 옵션 중 하나로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="661ba-170">이 설정은 조직의 모든 팀과 SharePoint 사이트에 영향을 미친다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="661ba-171">사용자가 파일 및 폴더를 공유할 때 기본적으로 선택되는 다음 링크 유형 중 하나를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="661ba-172">**링크가 있는 모든 사용자** - 파일 및 폴더의 무단 공유가 많은 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="661ba-173">링크를 *모든 사용자* 에게 공유하고 싶지만 예기치 못한 무단 공유가 우려되는 경우, 다른 옵션 중 하나를 기본값으로 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="661ba-174">이 링크 유형은 **모든 사용자** 와 공유할 수 있도록 사용 설정한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="661ba-175">**조직 내 사용자만** - 대부분의 파일 및 폴더 공유가 조직 내부 사용자와 공유될 것으로 예상되는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="661ba-176">**특정 사용자** - 게스트와 많은 파일 및 폴더 공유를 할 것으로 예상되는 경우 이 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="661ba-177">이러한 유형의 링크는 게스트와 함께 작동하며 인증을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="661ba-179">SharePoint 조직 수준 기본 링크 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="661ba-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="661ba-180">SharePoint 관리 센터의 공유 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="661ba-181">**파일 및 폴더 링크** 에서 사용하려는 기본 공유 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="661ba-182">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="661ba-183">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="661ba-183">Create a team</span></span>

<span data-ttu-id="661ba-184">다음 단계는 게스트와 공동 작업할 팀을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="661ba-185">팀을 만들기 위해</span><span class="sxs-lookup"><span data-stu-id="661ba-185">To create a team</span></span>
1. <span data-ttu-id="661ba-186">Teams의 **Teams** 탭에서 왼쪽 창 맨 아래에 있는 **팀 참가 또는 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="661ba-187">**팀 만들기** 를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="661ba-188">**처음부터 팀 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="661ba-189">**비공개** 또는 **공개** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="661ba-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="661ba-190">팀의 이름과 설명을 입력한 다음 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="661ba-191">**건너뛰기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-191">Click **Skip**.</span></span>

<span data-ttu-id="661ba-192">나중에 사용자를 초대할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-192">We'll invite users later.</span></span> <span data-ttu-id="661ba-193">다음으로, 팀과 연결된 SharePoint 사이트에 대한 사이트 수준 공유 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="661ba-194">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="661ba-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="661ba-195">사이트 수준 공유 설정을 확인하여 이 팀에 대해 원하는 액세스 유형을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="661ba-196">예를 들어. 조직 수준 설정을 **모든 사용자** 로 설정했지만 모든 게스트가 이 팀에 대해 인증하도록 하려면 사이트 수준 공유 설정이 **새 게스트 및 기존 게스트** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="661ba-198">사이트 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="661ba-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="661ba-199">SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트** 를 확장하고 **활성 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="661ba-200">방금 생성한 팀의 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="661ba-201">**공유** 를 클릭하고...선택합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="661ba-202">공유가 **모든 사용자** 또는 **새 게스트 및 기존 게스트** 로 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="661ba-203">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="661ba-204">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="661ba-204">Invite users</span></span>

<span data-ttu-id="661ba-205">이제 게스트 공유 설정이 구성되어 내부 사용자와 게스트를 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="661ba-206">내부 사용자를 팀에 초대</span><span class="sxs-lookup"><span data-stu-id="661ba-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="661ba-207">팀에서 **추가 옵션** (**\*\*\***)을 클릭한 다음, **구성원 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="661ba-208">초대하려는 사람의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="661ba-209">**추가** 를 클릭한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="661ba-210">팀에 게스트를 초대</span><span class="sxs-lookup"><span data-stu-id="661ba-210">To invite guests to a team</span></span>
1. <span data-ttu-id="661ba-211">팀에서 **추가 옵션** (**\*\*\***)을 클릭한 다음, **구성원 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="661ba-212">초대하려는 게스트의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="661ba-213">**게스트 정보 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="661ba-214">게스트의 전체 이름을 입력하고 확인 표시를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="661ba-215">**추가** 를 클릭한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="661ba-216">참고 항목</span><span class="sxs-lookup"><span data-stu-id="661ba-216">See also</span></span>

[<span data-ttu-id="661ba-217">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="661ba-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="661ba-218">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="661ba-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="661ba-219">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="661ba-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="661ba-220">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="661ba-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="661ba-221">Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="661ba-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="661ba-222">SharePoint 또는 OneDrive에서 공유하면 공유 옵션이 회색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="661ba-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
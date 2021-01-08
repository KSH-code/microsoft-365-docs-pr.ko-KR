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
localization_priority: Normal
f1.keywords: NOCSH
description: Teams에서 게스트와 작업, 대화 및 설명서 공동 작업을 위한 팀을 설정하는 데 필요한 Microsoft 365 구성 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780547"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="c7347-103">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="c7347-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="c7347-104">문서, 작업 및 대화에서 게스트와 공동 작업을 해야 하는 경우 Microsoft Teams를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="c7347-105">Teams는 통합된 사용자 환경의 사용자 지정 및 Extensible 공동 작업 도구 집합과 영구 채팅을 통해 Office 및 SharePoint에서 사용할 수 있는 모든 공동 작업 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="c7347-106">이 문서에서는 게스트와 공동 작업을 위한 팀을 설정하는 데 필요한 Microsoft 365 구성 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="c7347-107">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="c7347-107">Video demonstration</span></span>

<span data-ttu-id="c7347-108">이 비디오에서는 이 문서에 설명된 구성 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="c7347-109">Azure 외부 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="c7347-109">Azure External collaboration settings</span></span>

<span data-ttu-id="c7347-110">Microsoft 365에서 공유는 [Azure Active Directory의 B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)외부 공동 작업 설정에 의해 가장 높은 수준에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="c7347-111">Azure AD에서 게스트 공유를 사용하지 않도록 설정하거나 제한하는 경우 이 설정은 Microsoft 365에서 구성한 모든 공유 설정을 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="c7347-112">B2B 외부 공동 작업 설정 설정을 확인하여 게스트와의 공유가 차단되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 조직 관계 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="c7347-114">외부 공동 작업 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c7347-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="c7347-115">Azure Active Directory에 [https://aad.portal.azure.com](https://aad.portal.azure.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="c7347-116">왼쪽 탐색 창에서 **Azure Active Directory를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="c7347-117">외부 **ID를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-117">Click **External identities**.</span></span>
4. <span data-ttu-id="c7347-118">시작 **화면의 왼쪽** 탐색 창에서 외부 공동 작업 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="c7347-119">게스트 초대자 역할의 관리자와 **사용자가** 초대할 수 있으며 구성원이 초대할 수 **있는** 사용자가 모두 예로 설정되어 있도록 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="c7347-120">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="c7347-121">공동 작업 제한 섹션의 **설정을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="c7347-122">공동 작업할 게스트의 도메인이 차단되지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="c7347-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="c7347-123">여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="c7347-124">이렇게 하면 다른 사용자가 디렉터리에서 게스트인 것을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="c7347-125">이를 위해 게스트 사용자 액세스 제한에  따라 선택 게스트 사용자는 디렉터리 개체 설정의 속성 및 멤버 자격에 대한 액세스가 제한되거나 게스트 사용자 액세스는 자신의 디렉터리 개체의 속성 및 멤버 자격으로 제한됩니다. </span><span class="sxs-lookup"><span data-stu-id="c7347-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="c7347-126">Teams 게스트 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="c7347-126">Teams guest access settings</span></span>

<span data-ttu-id="c7347-127">Teams에는 게스트 액세스에 대한 마스터 켜기/끄기 스위치와 게스트가 팀에서 할 수 있는 작업을 제어하는 데 사용할 수 있는 다양한 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="c7347-128">마스터 스위치,  **Teams에서 게스트 액세스가 작동하려면 Teams에서** 게스트 액세스 허용이 켜 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="c7347-129">Teams에서 게스트 액세스를 사용하도록 설정되어 있는지 확인하고 비즈니스 요구에 따라 게스트 설정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="c7347-130">이러한 설정은 모든 팀에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-130">Keep in mind that these settings affect all teams.</span></span>

![Teams의 게스트 액세스 토글의 스크린샷](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="c7347-132">Teams 게스트 액세스를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="c7347-133">[https://admin.microsoft.com](https://admin.microsoft.com)에서 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="c7347-134">왼쪽 탐색 창에서 모두 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="c7347-135">**관리 센터** 에서 **Teams** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="c7347-136">Teams 관리 센터의 왼쪽 탐색 창에서 **Org 전체** 설정을 확장하고 게스트 액세스를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="c7347-137">Teams의 **게스트 액세스 허용** 이 **사용** 으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="c7347-138">추가 게스트 설정을 원하는대로 변경 한 다음 **저장** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="c7347-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="c7347-139">Teams 게스트 액세스가 설정되어 있는 경우 선택적으로 민감도 레이블을 사용하여 개별 팀 및 관련 SharePoint 사이트에 대한 게스트 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="c7347-140">자세한 내용은 [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7347-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="c7347-141">켜고 나면 Teams 게스트 설정이 활성화되기까지 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="c7347-142">Microsoft 365 그룹 게스트 설정</span><span class="sxs-lookup"><span data-stu-id="c7347-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="c7347-143">Teams는 팀 멤버십을 위해 Microsoft 365 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="c7347-144">Teams에서 게스트 액세스가 작동하려면 Microsoft 365 그룹 게스트 설정을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="c7347-146">Microsoft 365 그룹 게스트 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c7347-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="c7347-147">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 설정을 **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="c7347-148">Org **설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="c7347-149">목록에서 Microsoft **365** 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="c7347-150">그룹 소유자가 조직 외부의 구성원을 **게스트로 추가하고** 게스트  그룹 구성원이 그룹 콘텐츠 확인란에 액세스하도록 허용 확인란을 모두 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="c7347-151">변경한 경우 변경 내용 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="c7347-152">SharePoint 조직 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="c7347-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="c7347-153">파일, 폴더 및 목록과 같은 Teams 콘텐츠는 모두 SharePoint에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="c7347-154">게스트가 Teams에서 이러한 항목에 액세스할 수 있도록 SharePoint 조직 수준 공유 설정에서 게스트와의 공유를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="c7347-155">조직 수준 설정에 따라 팀과 연결된 사이트를 포함하여 개별 사이트에 사용할 수 있는 설정이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="c7347-156">사이트 설정은 조직 수준 설정보다 더 많이 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="c7347-157">허용되지 않은 사용자와 파일 및 폴더 공유를 허용하려는 경우 모든 사람을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="c7347-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="c7347-158">모든 게스트가 인증을 하도록 하려는 경우 신규 및 기존 **게스트를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="c7347-159">조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7347-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="c7347-161">SharePoint 조직 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c7347-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="c7347-162">Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 관리 **센터에서** **SharePoint를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="c7347-163">SharePoint 관리 센터의 왼쪽 탐색 창에서  정책을 확장한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="c7347-164">SharePoint의 외부 공유가 **모든** 사용자 또는 신규 및 기존 **게스트로 설정되어 있도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="c7347-165">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="c7347-166">SharePoint 조직 수준 기본 링크 설정</span><span class="sxs-lookup"><span data-stu-id="c7347-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="c7347-167">기본 파일 및 폴더 링크 설정에 따라 파일 또는 폴더를 공유할 때 기본적으로 사용자에게 표시되는 링크 옵션이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="c7347-168">사용자는 원하는 경우 공유하기 전에 링크 유형을 다른 옵션 중 하나로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="c7347-169">이 설정은 조직의 모든 팀 및 SharePoint 사이트에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="c7347-170">사용자가 파일 및 폴더를 공유할 때 기본적으로 선택되는 다음 링크 유형 중 하나를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7347-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="c7347-171">**링크가 있는** 모든 사용자 - 파일 및 폴더의 무인 공유를 많이 할 것으로 예상되는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="c7347-172">모든 사용자 링크를 *허용하지만* 실수로 허용되지 않은 공유가 우려되는 경우 다른 옵션 중 하나를 기본값으로 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="c7347-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="c7347-173">이 링크 유형은 모든 사용자 공유를 사용하도록 설정한 **경우만 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="c7347-174">**조직의 사용자만** - 대부분의 파일 및 폴더 공유가 조직 내부의 사용자와 공유될 것으로 예상하는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="c7347-175">**특정 사용자** - 게스트와 많은 파일 및 폴더 공유를 할 것으로 예상하는 경우 이 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="c7347-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="c7347-176">이 유형의 링크는 게스트와 함께 작동하며 이를 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="c7347-178">SharePoint 조직 수준 기본 링크 설정을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="c7347-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="c7347-179">SharePoint 관리 센터의 공유 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="c7347-180">파일 **및 폴더 링크 아래에서** 사용할 기본 공유 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="c7347-181">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="c7347-182">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="c7347-182">Create a team</span></span>

<span data-ttu-id="c7347-183">다음 단계는 게스트와 공동 작업하는 데 사용할 팀을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="c7347-184">팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-184">To create a team</span></span>
1. <span data-ttu-id="c7347-185">Teams의 **Teams** 탭에서 왼쪽  창의 아래쪽에 참가를 클릭하거나 팀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="c7347-186">팀 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="c7347-187">처음부터 **팀 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="c7347-188">개인 **또는 공용을** **선택**</span><span class="sxs-lookup"><span data-stu-id="c7347-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="c7347-189">팀의 이름과 설명을 입력한 다음 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="c7347-190">건너뛰기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-190">Click **Skip**.</span></span>

<span data-ttu-id="c7347-191">나중에 사용자를 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-191">We'll invite users later.</span></span> <span data-ttu-id="c7347-192">다음으로 팀과 연결된 SharePoint 사이트의 사이트 수준 공유 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="c7347-193">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="c7347-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="c7347-194">사이트 수준 공유 설정을 확인하여 이 팀에 대해 원하는 액세스 유형을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="c7347-195">예를 들어 조직 수준 설정을 **모든** 사용자로 설정했지만 모든 게스트가 이 팀에 대해 인증을 하게 하려는 경우 사이트 수준 공유 설정이 신규 및 기존 게스트로 설정되어 있는지 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="c7347-197">사이트 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c7347-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="c7347-198">SharePoint 관리 센터의 왼쪽 탐색 창에서 사이트를 **확장하고** 활성 **사이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="c7347-199">방금 생성한 팀의 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="c7347-200">Click ... 및 **공유를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="c7347-201">공유가 모든 사용자  또는 신규 및 기존 **게스트로 설정되어 있도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="c7347-202">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="c7347-203">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="c7347-203">Invite users</span></span>

<span data-ttu-id="c7347-204">이제 게스트 공유 설정이 구성되어 팀에 내부 사용자와 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="c7347-205">내부 사용자를 팀에 초대</span><span class="sxs-lookup"><span data-stu-id="c7347-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="c7347-206">팀에서 추가 **옵션()을** 클릭한 다음 구성원 **\*\*\*** **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="c7347-207">초대할 사람의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="c7347-208">**추가** 를 클릭한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="c7347-209">게스트를 팀에 초대</span><span class="sxs-lookup"><span data-stu-id="c7347-209">To invite guests to a team</span></span>
1. <span data-ttu-id="c7347-210">팀에서 추가 **옵션()을** 클릭한 다음 구성원 **\*\*\*** **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="c7347-211">초대할 게스트의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="c7347-212">게스트 **정보 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c7347-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="c7347-213">게스트의 전체 이름을 입력하고 확인 표시를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="c7347-214">**추가** 를 클릭한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7347-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7347-215">See also</span></span>

[<span data-ttu-id="c7347-216">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="c7347-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="c7347-217">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="c7347-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="c7347-218">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="c7347-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="c7347-219">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="c7347-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="c7347-220">Azure AD B2B와 SharePoint 및 OneDrive 통합</span><span class="sxs-lookup"><span data-stu-id="c7347-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="c7347-221">SharePoint 또는 OneDrive에서 공유하는 경우 공유 옵션이 회색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7347-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)

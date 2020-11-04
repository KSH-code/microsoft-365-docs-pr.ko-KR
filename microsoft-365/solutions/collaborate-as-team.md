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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 팀에서 게스트를 사용 하 여 작업, 대화 및 설명서 공동 작업을 수행 하는 데 필요한 Microsoft 365 구성 단계에 대해 설명 합니다.
ms.openlocfilehash: b4eea473f03441144a0236ec53dcecde9080fc7a
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906862"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="46380-103">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="46380-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="46380-104">여러 문서, 작업 및 대화에서 게스트와 공동 작업을 수행 해야 하는 경우 Microsoft 팀을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="46380-105">팀은 영구 채팅 및 통합 사용자 환경에서 사용자 지정 및 확장 가능한 공동 작업 도구 집합을 사용 하 여 Office 및 SharePoint에서 사용할 수 있는 모든 공동 작업 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="46380-106">이 문서에서는 게스트와의 공동 작업을 위해 팀을 설정 하는 데 필요한 Microsoft 365 구성 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="46380-107">비디오 데모</span><span class="sxs-lookup"><span data-stu-id="46380-107">Video demonstration</span></span>

<span data-ttu-id="46380-108">이 비디오에서는이 문서에서 설명 하는 구성 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46380-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="46380-109">Azure 조직 관계 설정</span><span class="sxs-lookup"><span data-stu-id="46380-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="46380-110">Microsoft 365의 공유는 [Azure Active Directory의 조직 관계 설정](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)에 따라 최상위 수준에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46380-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="46380-111">Azure AD에서 게스트 공유를 사용 하지 않도록 설정 하거나 제한 하는 경우이 설정은 Microsoft 365에서 구성한 모든 공유 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="46380-112">조직 관계 설정을 확인 하 여 게스트가 공유 하는 것이 차단 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 조직 관계 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="46380-114">조직 관계 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="46380-115">Azure Active Directory에에 로그인 [https://aad.portal.azure.com](https://aad.portal.azure.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="46380-116">왼쪽 탐색 창에서 **Azure Active Directory** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="46380-117">**외부 id** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-117">Click **External identities**.</span></span>
4. <span data-ttu-id="46380-118">**시작** 화면의 왼쪽 탐색 창에서 **외부 공동 작업 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="46380-119">**Guest inviter 역할의 관리자 및 사용자가 초대** 를 하 고 **구성원은 초대** 를 할 수 있는지 확인 하 고 둘 다 **예** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="46380-120">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="46380-121">**공동 작업 제한** 섹션의 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="46380-122">공동 작업 하려는 게스트의 도메인이 차단 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="46380-123">여러 조직의 게스트 작업을 수행 하는 경우 디렉터리 데이터에 대 한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="46380-124">이렇게 하면 디렉터리에서 게스트에 해당 하는 사람을 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46380-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="46380-125">이 작업을 수행 하려면 **게스트 사용자 액세스 제한** 에서 게스트 사용자는 **속성에 대 한 제한 된 액세스 및 디렉터리 개체 설정의 멤버 자격** 을 선택 하거나 **게스트 사용자 액세스를 자체 디렉터리 개체의 속성 및 구성원으로 제한** 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="46380-126">팀 게스트 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="46380-126">Teams guest access settings</span></span>

<span data-ttu-id="46380-127">팀에는 게스트 액세스에 대 한 마스터 온/오프 스위치가 있으며, 팀원 들이 어떤 게스트 작업을 수행할 수 있는지를 제어 하는 다양 한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="46380-128">게스트 액세스를 팀에서 작동 시키려면 마스터 스위치를 사용 하 여 **팀에서 게스트 액세스 허용** 이 **설정** 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="46380-129">팀에서 게스트 액세스를 사용 하도록 설정 되어 있는지 확인 하 고 비즈니스 요구에 따라 게스트 설정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="46380-130">이러한 설정은 모든 팀에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46380-130">Keep in mind that these settings affect all teams.</span></span>

![Teams의 게스트 액세스 토글의 스크린샷](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="46380-132">Teams 게스트 액세스를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="46380-133">[https://admin.microsoft.com](https://admin.microsoft.com)에서 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="46380-134">왼쪽 탐색 창에서 **모두 표시** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="46380-135">**관리 센터** 에서 **Teams** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-135">Under **Admin centers** , click **Teams**.</span></span>
4. <span data-ttu-id="46380-136">팀 관리 센터의 왼쪽 탐색 창에서 **조직 전체 설정을** 확장 하 고 **게스트 액세스** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="46380-137">Teams의 **게스트 액세스 허용** 이 **사용** 으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="46380-138">추가 게스트 설정을 원하는대로 변경 한 다음 **저장** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="46380-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="46380-139">팀 게스트 설정이 설정 된 후 활성 상태가 되도록 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-139">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="46380-140">Microsoft 365 Groups 게스트 설정</span><span class="sxs-lookup"><span data-stu-id="46380-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="46380-141">팀에서는 team 구성원에 게 Microsoft 365 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="46380-142">팀에서 게스트 액세스를 사용 하려면 Microsoft 365 Groups guest 설정이 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 관리 센터의 Microsoft 365 그룹 게스트 설정 스크린샷](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="46380-144">Microsoft 365 그룹 게스트 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="46380-145">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정을** 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-145">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="46380-146">**조직 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="46380-147">목록에서 **Microsoft 365 그룹** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="46380-148">**그룹 소유자가 조직 외부의 사용자를 게스트로 Microsoft 365 그룹에 추가** 하 고 **게스트 그룹 구성원에 게 그룹 콘텐츠 액세스** 확인란을 모두 선택 해 서 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-148">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="46380-149">변경한 경우 **변경 내용 저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="46380-150">SharePoint 조직 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="46380-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="46380-151">파일, 폴더 및 목록과 같은 팀 콘텐츠는 모두 SharePoint에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46380-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="46380-152">게스트가 팀의 이러한 항목에 액세스할 수 있도록 하려면 SharePoint 조직 수준 공유 설정에서 게스트가 공유 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="46380-153">조직 수준 설정에 따라 팀에 연결 된 사이트를 포함 하 여 개별 사이트에서 사용할 수 있는 설정이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46380-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="46380-154">사이트 설정은 조직 수준 설정 보다는 더 이상 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="46380-155">인증 되지 않은 사용자와 파일 및 폴더 공유를 허용 하려면 **모든 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="46380-156">모든 게스트가 인증을 받도록 하려면 **신규 및 기존 게스트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="46380-157">조직의 모든 사이트에 필요한 가장 관대 한 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="46380-159">SharePoint 조직 수준 공유 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-159">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="46380-160">Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 **관리 센터** 에서 **SharePoint** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-160">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="46380-161">SharePoint 관리 센터의 왼쪽 탐색 창에서 **정책을** 확장 하 고 **공유** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-161">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="46380-162">SharePoint 용 외부 공유가 **사용자** 또는 **신규 및 기존 게스트로** 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="46380-163">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="46380-164">SharePoint 조직 수준 기본 링크 설정</span><span class="sxs-lookup"><span data-stu-id="46380-164">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="46380-165">기본 파일 및 폴더 링크 설정에 따라 파일 또는 폴더를 공유할 때 기본적으로 사용자에 게 표시 되는 링크 옵션이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46380-165">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="46380-166">필요한 경우 공유 하기 전에 다른 옵션 중 하나로 연결 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-166">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="46380-167">이 설정은 조직의 모든 팀 및 SharePoint 사이트에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46380-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="46380-168">사용자가 파일 및 폴더를 공유할 때 기본적으로 선택 되는 다음 링크 유형 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-168">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="46380-169">**링크가 있는 모든 사용자** -파일 및 폴더의 인증 되지 않은 공유를 많이 사용 하는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="46380-170">*모든* 링크를 허용 하지만 실수로 인증 되지 않은 공유가 발생 하는 것이 염려 되는 경우에는 다른 옵션 중 하나를 기본값으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="46380-171">이 링크 형식은 **모든 사용자** 가 공유 하도록 설정한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="46380-172">**조직의 사용자만** 조직 내부 사용자와 파일 및 폴더 공유를 사용할 것으로 예상 되는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="46380-173">**특정 사용자** -게스트와 파일 및 폴더 공유를 많이 수행 해야 하는 경우이 옵션을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="46380-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="46380-174">이 유형의 링크는 게스트에서 작동 하며 인증을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="46380-176">SharePoint 조직 수준 기본 링크 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-176">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="46380-177">SharePoint 관리 센터에서 공유 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="46380-178">**파일 및 폴더 링크** 에서 사용 하려는 기본 공유 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-178">Under **File and folder links** , select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="46380-179">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="46380-180">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="46380-180">Create a team</span></span>

<span data-ttu-id="46380-181">다음 단계는 게스트와 공동 작업 하는 데 사용할 팀을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46380-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="46380-182">팀을 만들려면</span><span class="sxs-lookup"><span data-stu-id="46380-182">To create a team</span></span>
1. <span data-ttu-id="46380-183">팀의 **팀** 탭에서 왼쪽 창의 아래쪽에 있는 **참가 또는 팀 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="46380-184">**팀 만들기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="46380-185">**팀 구성 처음부터 새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="46380-186">**개인** 또는 **공개** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="46380-187">팀의 이름과 설명을 입력 하 고 **만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="46380-188">**건너뛰기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-188">Click **Skip**.</span></span>

<span data-ttu-id="46380-189">나중에 사용자를 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-189">We'll invite users later.</span></span> <span data-ttu-id="46380-190">다음으로 팀과 연결 된 SharePoint 사이트에 대 한 사이트 수준 공유 설정을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="46380-191">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="46380-191">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="46380-192">사이트 수준 공유 설정을 확인 하 여이 팀에 대해 원하는 액세스 유형을 허용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="46380-193">예를 들어 조직 수준 설정을 모든 **사용자** 로 설정 했지만 모든 게스트가이 팀에 대해 인증을 받으려는 경우에는 사이트 수준 공유 설정이 **신규 및 기존 게스트로** 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-193">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="46380-195">사이트 수준 공유 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="46380-196">SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트** 를 확장 하 고 **활성 사이트** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-196">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="46380-197">방금 생성한 팀의 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="46380-198">...을 클릭 합니다. **공유** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-198">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="46380-199">공유가 **사용자** 또는 **신규 및 기존 게스트로** 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="46380-200">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="46380-201">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="46380-201">Invite users</span></span>

<span data-ttu-id="46380-202">이제 게스트 공유 설정이 구성 되므로 팀에 내부 사용자 및 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46380-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="46380-203">팀에 내부 사용자를 초대 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="46380-204">팀에서 **기타 옵션** ( **\*\*\*** )을 클릭 하 고 **구성원 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-204">In the team, click **More options** ( **\*\*\*** ), and then click **Add member**.</span></span>
2. <span data-ttu-id="46380-205">초대 하려는 사용자의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="46380-206">**추가** 를 클릭한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-206">Click **Add** , and then click **Close**.</span></span>

<span data-ttu-id="46380-207">팀에 게스트를 초대 하려면</span><span class="sxs-lookup"><span data-stu-id="46380-207">To invite guests to a team</span></span>
1. <span data-ttu-id="46380-208">팀에서 **기타 옵션** ( **\*\*\*** )을 클릭 하 고 **구성원 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-208">In the team, click **More options** ( **\*\*\*** ), and then click **Add member**.</span></span>
2. <span data-ttu-id="46380-209">초대 하려는 게스트의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-209">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="46380-210">**게스트 정보 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="46380-211">게스트의 전체 이름을 입력 하 고 확인 표시를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="46380-212">**추가** 를 클릭한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46380-212">Click **Add** , and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="46380-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46380-213">See also</span></span>

[<span data-ttu-id="46380-214">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="46380-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="46380-215">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="46380-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="46380-216">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="46380-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="46380-217">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="46380-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="46380-218">Azure AD B2B와의 SharePoint 및 OneDrive 통합</span><span class="sxs-lookup"><span data-stu-id="46380-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

---
title: 게스트와 문서 상 공동 작업하기
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
description: 이 문서에서는 SharePoint 및 OneDrive의 문서에서 게스트와 공동 작업하는 방법을 배우게 됩니다.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663514"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="05485-103">게스트와 문서 상 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="05485-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="05485-104">SharePoint 또는 OneDrive의 문서에 대해 조직 외부의 사용자와 공동 작업을 해야 하는 경우 문서에 대한 공유 링크를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="05485-105">이 문서에서는 조직의 요구에 따라 SharePoint 및 OneDrive에 대한 공유 링크를 설정하는 데 필요한 Microsoft 365 구성 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="05485-106">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="05485-106">Video demonstration</span></span>

<span data-ttu-id="05485-107">이 비디오에서는 이 문서에 설명된 구성 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="05485-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="05485-108">Azure 외부 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="05485-108">Azure external collaboration settings</span></span>

<span data-ttu-id="05485-109">Microsoft 365에서 공유는 [Azure Active Directory의 B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)외부 공동 작업 설정에 의해 가장 높은 수준에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="05485-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="05485-110">Azure AD에서 게스트 공유를 사용하지 않도록 설정하거나 제한하는 경우 이 설정은 Microsoft 365에서 구성한 모든 공유 설정을 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="05485-111">B2B 외부 공동 작업 설정을 확인하여 게스트와의 공유가 차단되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 조직 관계 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="05485-113">외부 공동 작업 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="05485-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="05485-114">Azure Active Directory에 [https://aad.portal.azure.com](https://aad.portal.azure.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="05485-115">왼쪽 탐색 창에서 **Azure Active Directory를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="05485-116">외부 **ID를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-116">Click **External identities**.</span></span>
4. <span data-ttu-id="05485-117">시작 **화면의 왼쪽** 탐색 창에서 외부 공동 작업 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="05485-118">게스트 초대자 역할의 관리자와 **사용자가** 초대할 수 있으며 구성원이 초대할 수 **있는** 사용자가 모두 예로 설정되어 있도록 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="05485-119">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="05485-120">공동 작업 제한 섹션의 **설정을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="05485-121">공동 작업할 게스트의 도메인이 차단되지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="05485-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="05485-122">여러 조직의 게스트와 함께 작업하는 경우 디렉터리 데이터에 액세스하는 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="05485-123">이렇게 하면 다른 사용자가 디렉터리에서 게스트인 것을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="05485-124">이를 위해 게스트 사용자 **액세스** 제한에  따라 선택된 게스트 사용자는 디렉터리 개체 설정의 속성 및 멤버 자격에 대한 액세스가 제한되거나 게스트 사용자 액세스는 자체 디렉터리 개체의 속성 및 멤버 자격으로 제한됩니다. </span><span class="sxs-lookup"><span data-stu-id="05485-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="05485-125">SharePoint 조직 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="05485-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="05485-126">조직 외부의 사용자가 SharePoint 또는 OneDrive의 문서에 액세스할 수 있도록 SharePoint 및 OneDrive 조직 수준 공유 설정을 통해 조직 외부의 사용자와 공유할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="05485-127">SharePoint의 조직 수준 설정에 따라 개별 SharePoint 사이트에 사용할 수 있는 설정이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="05485-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="05485-128">사이트 설정은 조직 수준 설정보다 더 많이 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="05485-129">OneDrive에 대한 조직 수준 설정에 따라 사용자의 OneDrive 라이브러리에서 사용할 수 있는 공유 수준이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="05485-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="05485-130">SharePoint 및 OneDrive의 경우, 허용되지 않은 파일 및 폴더 공유를 허용하려는 경우 모든 사람을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="05485-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="05485-131">조직 외부의 사용자가 인증을 하도록 하려는 경우 신규 및 기존 **게스트를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="05485-132">*모든* 사용자 링크는 가장 쉽게 공유할 수 있는 방법입니다. 조직 외부의 사람은 인증 없이 링크를 열 수 있으며 다른 사용자에게 무료로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="05485-133">SharePoint의 경우 조직의 모든 사이트에서 필요한 가장 적합한 설정을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="05485-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="05485-135">SharePoint 조직 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="05485-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="05485-136">Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 관리 센터에서 **SharePoint를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="05485-137">SharePoint 관리 센터의 왼쪽 탐색 창에 있는 **정책 아래에서** 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="05485-138">SharePoint 또는 OneDrive에 대한 외부 공유가 **모든** 사용자 또는 신규 및 기존 **게스트로 설정되어 있도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="05485-139">OneDrive 설정은 SharePoint 설정보다 더 많이 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="05485-140">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="05485-141">SharePoint 조직 수준 기본 링크 설정</span><span class="sxs-lookup"><span data-stu-id="05485-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="05485-142">기본 파일 및 폴더 링크 설정에 따라 파일 또는 폴더를 공유할 때 기본적으로 사용자에게 표시되는 링크 옵션이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="05485-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="05485-143">사용자는 원하는 경우 공유하기 전에 링크 유형을 다른 옵션 중 하나로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="05485-144">이 설정은 OneDrive뿐만 아니라 조직의 SharePoint 사이트에도 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05485-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="05485-145">사용자가 파일 및 폴더를 공유할 때 기본적으로 선택되는 다음 유형의 링크를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="05485-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="05485-146">**링크가 있는** 모든 사용자 - 많은 확인되지 않은 파일 및 폴더 공유를 할 것으로 예상하는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="05485-147">모든 사용자 링크를 *허용하지만* 실수로 허용되지 않은 공유가 우려되는 경우 다른 옵션 중 하나를 기본값으로 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="05485-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="05485-148">이 링크 유형은 모든 사용자 공유를 사용하도록 설정한 **경우만 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="05485-149">**조직의 사용자만** - 대부분의 파일 및 폴더 공유가 조직 내부의 사용자와 공유될 것으로 예상하는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="05485-150">**특정 사용자** - 게스트와 많은 파일 및 폴더 공유를 할 것으로 예상하는 경우 이 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="05485-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="05485-151">이 유형의 링크는 게스트와 함께 작동하며 이를 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="05485-153">SharePoint 및 OneDrive 조직 수준 기본 링크 설정을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="05485-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="05485-154">SharePoint 관리 센터의 공유 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="05485-155">파일 **및 폴더 링크 아래에서** 사용할 기본 공유 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="05485-156">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="05485-157">공유 링크에 대한 사용 권한을 설정하려면 기본적으로 링크 공유에 대해 선택된 사용 권한을 **선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="05485-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="05485-158">**확인되지** 않은 사용자가 파일 및 폴더를 변경하지 못하게 하려는 경우 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="05485-159">**확인되지** 않은 사용자가 파일 및 폴더를 변경할 수 있도록 허용하려면 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="05485-160">위의 두 가지 사전 설정 옵션은 게스트/외부 사용자뿐만 아니라 내부 사용자에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="05485-161">선택하는 권한 옵션은 자체 재량에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="05485-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="05485-162">모든 사용자와 공유를 허용하는 링크에 대한 사용 권한을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="05485-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="05485-163">이러한 링크 **아래에서 하위** 창,</span><span class="sxs-lookup"><span data-stu-id="05485-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="05485-164">파일 **드롭다운** 목록에서</span><span class="sxs-lookup"><span data-stu-id="05485-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="05485-165">확인되지 **않은** 사용자가 파일을 변경할 수 있도록 허용하려면 보기 및 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="05485-166">**확인되지** 않은 사용자가 파일을 변경하지 못하게 하려는 경우 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="05485-167">폴더 **드롭다운** 목록에서</span><span class="sxs-lookup"><span data-stu-id="05485-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="05485-168">확인되지 **않은 사용자가** 폴더를 변경할 수 있도록 허용하려면 보기, 편집 및 업로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="05485-169">**확인되지** 않은 사용자가 폴더를 변경하지 못하게 하려는 경우 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="05485-170">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="05485-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="05485-171">SharePoint 사이트에 있는 파일 및 폴더를 공유하는 경우 해당 사이트의 사이트 수준 공유 설정도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="05485-173">사이트 수준 공유 설정을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="05485-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="05485-174">SharePoint 관리 센터의 왼쪽 탐색 창에서 사이트를 **확장하고** 활성 **사이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="05485-175">게스트와 파일 및 폴더를 공유할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="05485-176">선택한 사이트가 있는 행에서 오른쪽으로 스크롤하고 외부 공유 열의 아무 곳이나 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="05485-177">팝업 페이지에서 정책 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="05485-178">외부 공유 **창에서** 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="05485-179">공유가 모든 사용자  또는 신규 및 기존 **게스트로 설정되어 있도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05485-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="05485-180">변경한 내용이 있으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05485-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="05485-181">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="05485-181">Invite users</span></span>

<span data-ttu-id="05485-182">게스트 공유 설정이 이제 구성됩니다. 따라서 사용자는 이제 조직 외부의 사용자와 파일 및 폴더를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05485-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="05485-183">자세한 [내용은 OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 파일 및 폴더 및 SharePoint 파일 또는 [폴더 공유를](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05485-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="05485-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05485-184">See also</span></span>

[<span data-ttu-id="05485-185">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="05485-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="05485-186">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="05485-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="05485-187">Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="05485-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

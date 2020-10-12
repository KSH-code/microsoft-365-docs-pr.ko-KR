---
title: 게스트와 문서에서 공동 작업하기
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
description: 이 문서에서는 SharePoint 및 OneDrive의 문서에서 게스트로 공동 작업 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422608"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="57c08-103">게스트와 문서에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="57c08-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="57c08-104">SharePoint 또는 OneDrive의 문서를 조직 외부의 사용자와 공동으로 작업 해야 하는 경우 문서에 대 한 공유 링크를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="57c08-105">이 문서에서는 조직의 필요에 따라 SharePoint 및 OneDrive에 대 한 공유 링크를 설정 하는 데 필요한 Microsoft 365 구성 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="57c08-106">비디오 데모</span><span class="sxs-lookup"><span data-stu-id="57c08-106">Video demonstration</span></span>

<span data-ttu-id="57c08-107">이 비디오에서는이 문서에서 설명 하는 구성 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="57c08-108">Azure 조직 관계 설정</span><span class="sxs-lookup"><span data-stu-id="57c08-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="57c08-109">Microsoft 365의 공유는 [Azure Active Directory의 조직 관계 설정](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)에 따라 최상위 수준에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="57c08-110">Azure AD에서 게스트 공유를 사용 하지 않도록 설정 하거나 제한 하는 경우이 설정은 Microsoft 365에서 구성한 모든 공유 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="57c08-111">조직 관계 설정을 확인 하 여 게스트가 공유 하는 것이 차단 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 조직 관계 설정 페이지 스크린샷](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="57c08-113">조직 관계 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="57c08-113">To set organizational relationship settings</span></span>

<span data-ttu-id="57c08-114">외부 공동 작업 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="57c08-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="57c08-115">Azure Active Directory에에 로그인 [https://aad.portal.azure.com](https://aad.portal.azure.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="57c08-116">왼쪽 탐색 창에서 **Azure Active Directory**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="57c08-117">**외부 id**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-117">Click **External identities**.</span></span>
4. <span data-ttu-id="57c08-118">**시작** 화면의 왼쪽 탐색 창에서 **외부 공동 작업 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="57c08-119">**Guest inviter 역할의 관리자 및 사용자가 초대** 를 하 고 **구성원은 초대** 를 할 수 있는지 확인 하 고 둘 다 **예**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="57c08-120">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="57c08-121">**공동 작업 제한** 섹션의 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="57c08-122">공동 작업 하려는 게스트의 도메인이 차단 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="57c08-123">여러 조직의 게스트 작업을 수행 하는 경우 디렉터리 데이터에 대 한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="57c08-124">이렇게 하면 디렉터리에서 게스트에 해당 하는 사람을 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="57c08-125">이 작업을 수행 하려면 **게스트 사용자 액세스 제한**에서 게스트 사용자는 **속성에 대 한 제한 된 액세스 및 디렉터리 개체 설정의 멤버 자격** 을 선택 하거나 **게스트 사용자 액세스를 자체 디렉터리 개체의 속성 및 구성원으로 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="57c08-126">SharePoint 조직 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="57c08-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="57c08-127">조직 외부의 사용자가 SharePoint 또는 OneDrive의 문서에 액세스할 수 있도록 하려면 SharePoint 및 OneDrive 조직 수준 공유 설정에서 조직 외부의 사용자와 공유 하는 것을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="57c08-128">SharePoint의 조직 수준 설정에 따라 개별 SharePoint 사이트에서 사용할 수 있는 설정이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="57c08-129">사이트 설정은 조직 수준 설정 보다는 더 이상 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="57c08-130">OneDrive에 대 한 조직 수준 설정에 따라 사용자의 OneDrive 라이브러리에서 사용할 수 있는 공유 수준이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="57c08-131">SharePoint 및 OneDrive의 경우 인증 되지 않은 파일 및 폴더 공유를 허용 하려면 **모든 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="57c08-132">조직 외부의 사용자가 인증을 받아야 하는 경우 **신규 및 기존 게스트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="57c08-133">공유 하는 가장 쉬운 방법은 *사용자* 의 조직 외부 사용자가 인증 없이 링크를 열 수 있으며이를 다른 사람에 게 전달 하는 데 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="57c08-134">SharePoint의 경우 조직의 모든 사이트에서 필요한 가장 관대 한 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 조직 수준 공유 설정의 스크린샷](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="57c08-136">SharePoint 조직 수준 공유 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="57c08-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="57c08-137">Microsoft 365 관리 센터의 왼쪽 탐색 창에 있는 **관리 센터**에서 **SharePoint**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="57c08-138">SharePoint 관리 센터의 왼쪽 탐색 창에 있는 **정책**에서 **공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="57c08-139">SharePoint 또는 OneDrive에 대 한 외부 공유가 **모든 사용자** 또는 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="57c08-140">OneDrive 설정은 SharePoint 설정 보다 더 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="57c08-141">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="57c08-142">SharePoint 조직 수준 기본 링크 설정</span><span class="sxs-lookup"><span data-stu-id="57c08-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="57c08-143">기본 파일 및 폴더 링크 설정에 따라 파일 또는 폴더를 공유할 때 기본적으로 사용자에 게 표시 되는 링크 옵션이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="57c08-144">필요한 경우 공유 하기 전에 다른 옵션 중 하나로 연결 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="57c08-145">이 설정은 OneDrive 뿐 아니라 조직의 SharePoint 사이트에도 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="57c08-146">사용자가 파일 및 폴더를 공유할 때 다음 유형 중 하나에서 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="57c08-147">**링크를 포함 하는 모든 사용자** 인증 되지 않은 파일 및 폴더 공유를 많이 수행 하려는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="57c08-148">*모든* 링크를 허용 하지만 실수로 인증 되지 않은 공유가 발생 하는 것이 염려 되는 경우에는 다른 옵션 중 하나를 기본값으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="57c08-149">이 링크 형식은 **모든 사용자** 가 공유 하도록 설정한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="57c08-150">**조직의 사용자만** 조직 내부 사용자와 파일 및 폴더 공유를 사용할 것으로 예상 되는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="57c08-151">**특정 사용자** -게스트와 파일 및 폴더 공유를 많이 수행 해야 하는 경우이 옵션을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="57c08-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="57c08-152">이 유형의 링크는 게스트에서 작동 하며 인증을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 조직 수준 파일 및 폴더 공유 설정 스크린샷](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="57c08-154">SharePoint 및 OneDrive 조직 수준 기본 링크 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="57c08-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="57c08-155">SharePoint 관리 센터에서 공유 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="57c08-156">**파일 및 폴더 링크**에서 사용 하려는 기본 공유 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="57c08-157">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="57c08-158">공유 링크에 대 한 사용 권한을 설정 하려면 **공유 링크에 대해 기본적으로 선택 되는 사용 권한을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="57c08-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="57c08-159">인증 되지 않은 사용자가 파일 및 폴더를 변경할 수 없도록 하려면 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="57c08-160">인증 되지 않은 사용자가 파일 및 폴더를 변경할 수 있도록 하려면 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="57c08-161">위의 두 가지 사전 임무 옵션은 게스트/외부 사용자 뿐만 아니라 내부 사용자 에게도 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="57c08-162">선택 하는 사용 권한 옵션은 자체 판단에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="57c08-163">모든 사용자와의 공유를 허용 하는 링크에 대 한 사용 권한을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="57c08-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="57c08-164">이러한 링크에서 다음 **권한을 부여할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="57c08-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="57c08-165">**파일** 드롭다운 목록에서</span><span class="sxs-lookup"><span data-stu-id="57c08-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="57c08-166">인증 되지 않은 사용자가 파일을 변경할 수 있도록 하려면 **보기 및 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="57c08-167">인증 되지 않은 사용자가 파일을 변경할 수 없도록 하려면 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="57c08-168">**폴더** 드롭다운 목록에서</span><span class="sxs-lookup"><span data-stu-id="57c08-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="57c08-169">인증 되지 않은 사용자가 폴더를 변경할 수 있도록 하려면 **보기, 편집 및 업로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="57c08-170">인증 되지 않은 사용자가 폴더를 변경 하지 못하게 하려면 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="57c08-171">SharePoint 사이트 수준 공유 설정</span><span class="sxs-lookup"><span data-stu-id="57c08-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="57c08-172">SharePoint 사이트에 있는 파일 및 폴더를 공유 하는 경우에는 해당 사이트에 대 한 사이트 수준 공유 설정도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 사이트 외부 공유 설정 스크린샷](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="57c08-174">사이트 수준 공유 설정을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="57c08-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="57c08-175">SharePoint 관리 센터의 왼쪽 탐색 창에서 **사이트** 를 확장 하 고 **활성 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="57c08-176">게스트를 사용 하 여 파일 및 폴더를 공유할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="57c08-177">선택한 사이트가 있는 행에서 오른쪽으로 스크롤한 다음 **외부 공유** 열의 아무 곳 이나 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="57c08-178">팝업 되는 페이지에서 **정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="57c08-179">**외부 공유** 창 아래에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="57c08-180">공유가 **사용자** 또는 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="57c08-181">변경한 내용이 있으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="57c08-182">사용자 초대하기</span><span class="sxs-lookup"><span data-stu-id="57c08-182">Invite users</span></span>

<span data-ttu-id="57c08-183">게스트 공유 설정이 이제 구성 됩니다. 이제 사용자가 조직 외부의 사용자와 파일 및 폴더를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c08-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="57c08-184">자세한 내용은 [OneDrive 파일 및 폴더](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 공유 및 [SharePoint 파일 또는 폴더 공유](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57c08-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="57c08-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57c08-185">See also</span></span>

[<span data-ttu-id="57c08-186">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="57c08-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="57c08-187">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="57c08-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="57c08-188">Azure AD B2B와의 SharePoint 및 OneDrive 통합</span><span class="sxs-lookup"><span data-stu-id="57c08-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

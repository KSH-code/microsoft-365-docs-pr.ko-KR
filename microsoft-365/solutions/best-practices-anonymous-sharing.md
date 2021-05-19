---
title: 인증되지 않은 공유에 대한 모범 사례
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
recommendations: false
description: 이 문서에서는 인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례를 알아봅니다.
ms.openlocfilehash: 7198e2d343f73299bb62ea73863cecd359d90ba2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538234"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="f7717-103">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="f7717-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="f7717-104">인증되지 않은 공유(*모든 사용자* 링크)는 다양한 상황에서 편리하며 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-104">Unauthenticated sharing (*Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="f7717-105">*모든 사용자* 링크는 가장 간편하게 공유하는 방법입니다. 사용자가 인증 없이 링크를 열 수 있으며 다른 사용자에게 무료로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="f7717-p102">일반적으로 조직의 일부 콘텐츠가 인증되지 않은 공유에 적합한 것은 아닙니다. 이 문서에서는 사용자가 파일 및 폴더의 인증되지 않은 공유를 할 수 있지만, 조직의 콘텐츠를 보호하는 데 도움이 되는 보호 기능도 포함된 환경을 만들 수 있는 옵션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-p102">Usually, not all content in an organization is appropriate for unauthenticated sharing. This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="f7717-108">인증되지 않은 공유가 작동하려면 조직 및 사용자가 사용할 개별 사이트 또는 팀에 대해 이 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="f7717-109">활성화하려는 시나리오를 보려면 [조직 외부 사용자와 공동 작업](collaborate-with-people-outside-your-organization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7717-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="f7717-110">모든 사용자 링크의 만료 날짜를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="f7717-111">파일은 오랜 기간 동안 사이트, 그룹 및 팀에 저장되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="f7717-112">경우에 따라, 파일을 수년 동안 보존해야 하는 데이터 보존 정책이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="f7717-113">해당 파일을 인증되지 않은 사용자와 공유하는 경우, 나중에 파일에 대한 예기치 않은 액세스 및 변경 내용이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="f7717-114">이와 같은 가능성을 줄이기 위해 *모든 사용자* 링크의 만료 시간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="f7717-115">*모든 사용자* 링크가 만료되면 계정을 더 이상 콘텐츠에 액세스하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="f7717-116">조직 전반에서 모든 사용자 링크의 만료 날짜를 설정하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-116">To set an expiration date for Anyone links across the organization</span></span>

1. <span data-ttu-id="f7717-117">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-117">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="f7717-118">왼쪽 탐색 창에서 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-118">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="f7717-119">**"모든 사용자" 링크 만료 및 사용 권한 옵션 선택** 에서 **이러한 링크는 다음 기간 내에 만료되어야 합니다** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-119">Under **Choose expiration and permissions options for Anyone links**, select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="f7717-120">![SharePoint 조직 수준 모든 사용자 링크 만료 설정 스크린샷](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="f7717-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="f7717-121">상자에 일 수를 입력한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="f7717-122">특정 사이트에서 모든 사용자 링크의 만료 날짜를 설정하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-122">To set an expiration date for Anyone links on a specific site</span></span>

1. <span data-ttu-id="f7717-123">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-123">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="f7717-124">왼쪽 탐색에서 **사이트** 를 확장한 후 **활성 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-124">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="f7717-125">변경할 사이트를 선택한 다음 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-125">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="f7717-126">**모든 사용자 링크에 대한 고급 설정** 에서 **모든 사용자 링크 만료** 에서 **조직 수준 설정과 동일** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-126">Under **Advanced settings for Anyone links**, under **Expiration of Anyone links**, clear the **Same as organization-level setting** check box.</span></span></br>
   <span data-ttu-id="f7717-127">![SharePoint 사이트 수준 모든 사용자 링크 만료 설정 스크린샷](../media/sharepoint-organization-anyone-link-expiration-site.png)</span><span class="sxs-lookup"><span data-stu-id="f7717-127">![Screenshot of SharePoint site-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration-site.png)</span></span>
5. <span data-ttu-id="f7717-128">**이러한 링크는 이 기간 내에 만료되어야 함** 옵션을 선택하고 상자에 일 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-128">Select the **These links must expire within this many days** option, and type a number of days in the box.</span></span>
6. <span data-ttu-id="f7717-129">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-129">Click **Save**.</span></span>

<span data-ttu-id="f7717-130">*모든 사용자* 링크가 만료되면 파일이나 폴더를 새 *모든 사용자* 링크와 다시 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-130">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="f7717-131">[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite)를 사용하여 특정 OneDrive에 대한 *모든 사용자* 링크 만료를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-131">You can set *Anyone* link expiration for a specific OneDrive by using [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="f7717-132">링크 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="f7717-132">Set link permissions</span></span>

<span data-ttu-id="f7717-133">파일의 *모든 사용자* 링크를 사용하여 파일을 편집할 수 있으며, 폴더의 *모든 사용자* 링크를 통해 파일을 확인하고 편집하며 새 파일을 해당 폴더에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-133">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="f7717-134">파일 및 폴더에 대한 사용 권한을 보기 전용으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-134">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="f7717-135">인증되지 않은 공유를 허용하지만, 인증되지 않은 사용자가 조직의 콘텐츠를 수정하는 것이 우려되는 경우, 파일 및 폴더 사용 권한을 **보기** 로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-135">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="f7717-136">조직 전반에서 모든 사용자 링크의 사용 권한을 설정하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-136">To set permissions for Anyone links across the organization</span></span>

1. <span data-ttu-id="f7717-137">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-137">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="f7717-138">왼쪽 탐색 창에서 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-138">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="f7717-139">**"모든 사용자" 링크의 고급 설정** 에서 사용할 파일 및 폴더 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-139">Under **Advanced settings for "Anyone" links**, select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="f7717-140">![SharePoint 조직 수준 모든 사용자 링크 사용 권한 설정 스크린샷](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="f7717-140">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="f7717-141">*모든 사용자* 링크가 **보기** 로 설정된 경우, 게스트와 파일 및 폴더를 계속 공유하고 *특정 사용자* 링크를 사용하여 편집 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-141">With *Anyone* links set to **View**, users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="f7717-142">이러한 링크를 사용하려면 조직 외부의 사용자가 게스트로 인증해야 하며, 이 링크와 공유되는 파일 및 폴더에서 게스트 활동을 추적하고 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-142">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="f7717-143">기본 링크 유형이 조직에 있는 사용자에 대해서만 작동하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-143">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="f7717-144">*모든 사용자* 공유가 사용자 조직에 사용할 수 있도록 설정된 경우, 기본 공유 링크는 일반적으로 **모든 사용자** 로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-144">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="f7717-145">이 기능이 사용자에게는 편리하지만, 원하지 않는 인증되지 않는 공유의 위험이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-145">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="f7717-146">사용자가 중요한 문서를 공유하는 동안 링크 유형을 변경하는 것을 잊어버린 경우, 사용자가 인증이 필요 없는 공유 링크를 실수로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-146">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="f7717-147">기본 링크 설정을 조직 내부 사용자만 사용할 수 있는 링크로 변경하여 이 위험을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-147">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="f7717-148">인증되지 않은 사용자와 공유하려는 사용자는 해당 옵션을 구체적으로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-148">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="f7717-149">조직에 대한 기본 파일 및 폴더 공유 링크를 설정하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-149">To set the default file and folder sharing link for the organization</span></span>
1. <span data-ttu-id="f7717-150">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-150">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="f7717-151">왼쪽 탐색 창에서 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-151">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="f7717-152">**파일 및 폴더 링크** 에서 **조직 내 사용자만** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-152">Under **File and folder links**, select **Only people in your organization**.</span></span>

   ![SharePoint 기본 링크 유형 설정 스크린샷](../media/sharepoint-default-sharing-link-company-link.png)

4. <span data-ttu-id="f7717-154">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-154">Click **Save**</span></span>

<span data-ttu-id="f7717-155">특정 사이트에 대한 기본 파일 및 폴더 공유 링크를 설정하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-155">To set the default file and folder sharing link for a specific site</span></span>
1. <span data-ttu-id="f7717-156">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-156">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="f7717-157">왼쪽 탐색에서 **사이트** 를 확장한 후 **활성 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-157">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="f7717-158">변경할 사이트를 선택한 다음 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-158">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="f7717-159">**기본 공유** 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-159">Under **Default sharing link type**,  clear the **Same as organization-level setting** check box.</span></span>

   ![SharePoint 사이트 수준의 기본 링크 유형 설정 스크린샷](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. <span data-ttu-id="f7717-161">**조직의 사용자만** 옵션을 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-161">Select the **Only people in your organization** option and click **Save**.</span></span>

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a><span data-ttu-id="f7717-162">중요한 콘텐츠의 인증되지 않은 공유 방지</span><span class="sxs-lookup"><span data-stu-id="f7717-162">Prevent unauthenticated sharing of sensitive content</span></span>

<span data-ttu-id="f7717-163">[DLP(데이터 손실 방지)](../compliance/dlp-learn-about-dlp.md)를 사용하여 중요한 콘텐츠의 인증되지 않은 게스트와의 공유를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-163">You can use [data loss prevention (DLP)](../compliance/dlp-learn-about-dlp.md) to prevent unauthenticated sharing of sensitive content.</span></span> <span data-ttu-id="f7717-164">데이터 손실 방지는 파일 자체의 파일 민감도 레이블, 보존 레이블 또는 중요한 정보를 기반으로 하는 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-164">Data loss prevention can take action based on a file's sensitivity label, retention label, or sensitive information in the file itself.</span></span>

<span data-ttu-id="f7717-165">DLP 규칙을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-165">To create a DLP rule</span></span>
1. <span data-ttu-id="f7717-166">Microsoft 365 준수 관리 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-166">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="f7717-167">**정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-167">Click **Create policy**.</span></span>
3. <span data-ttu-id="f7717-168">**사용자 지정** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-168">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="f7717-169">정책 이름을 입력한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-169">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="f7717-170">**정책을 적용할 위치** 페이지에서 **SharePoint 사이트** 및 **OneDrive 계정** 을 제외한 모든 설정을 해제한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-170">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="f7717-171">**정책 설정 정의** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-171">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="f7717-172">**고급 DLP 규칙 사용자 지정** 페이지에서 **규칙 만들기** 를 클릭하고 규칙의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-172">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="f7717-173">**조건** 에서 **조건 추가** 를 클릭하고 **콘텐츠 포함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-173">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="f7717-174">**추가** 를 클릭하고 인증 되지 않은 공유를 방지하려는 정보 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-174">Click **Add** and choose the type of information for which you want to prevent unauthenticated sharing.</span></span>

   ![조건 옵션, 중요한 정보 유형, 민감도 레이블, 보존 레이블 스크린샷.](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="f7717-176">**작업** 에서 **작업 추가** 를 클릭하고 **액세스를 제한하거나 Microsoft 365 위치에서 콘텐츠를 암호화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-176">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="f7717-177">**Microsoft 365 위치의 콘텐츠에 대한 액세스 제한 또는 암호화** 확인란을 선택한 다음 **“링크에 대한 모든 사용자" 옵션을 통해 콘텐츠에 대한 액세스 권한을 부여받은 유일한 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-177">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people who were given access to the content through the "Anyone withe the link" options** option.</span></span>

      ![DLP 규칙 작업 옵션의 스크린샷](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. <span data-ttu-id="f7717-179">**저장** 을 클릭한 다음 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-179">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="f7717-180">테스트 옵션을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-180">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="f7717-181">**제출** 을 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-181">Click **Submit**, and then click **Done**.</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="f7717-182">악성 파일로부터 보호</span><span class="sxs-lookup"><span data-stu-id="f7717-182">Protect against malicious files</span></span>

<span data-ttu-id="f7717-183">익명 사용자가 파일을 업로드할 수 있도록 허용하는 경우 악성 파일이 업로드되는 위험이 증가하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-183">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="f7717-184">Microsoft 365에서는 Office 365용 Defender에서 *안전한 첨부 파일* 기능을 사용하여 업로드된 파일을 자동으로 검사하고 안전하지 않은 파일을 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-184">In Microsoft 365, you can use the *Safe Attachments* feature in Defender for Office 365 to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="f7717-185">안전한 첨부 파일을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f7717-185">To turn on safe attachments</span></span>
1. <span data-ttu-id="f7717-186">보안 및 준수 관리 센터에서 [ATP 안전한 첨부 파일 페이지](https://protection.office.com/safeattachmentv2)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-186">Open the [ATP Safe Attachments page](https://protection.office.com/safeattachmentv2) in the Security and Compliance admin center.</span></span>
2. <span data-ttu-id="f7717-187">**전역 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-187">Click **Global settings**.</span></span>
3. <span data-ttu-id="f7717-188">SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기</span><span class="sxs-lookup"><span data-stu-id="f7717-188">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   ![보안 및 규정 준수 센터의 안전한 첨부 파일 설정 스크린샷](../media/safe-attachments-setting.png)

4. <span data-ttu-id="f7717-190">필요에 따라 안전한 문서를 켠 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-190">Optionally turn on Safe Documents as well, and then click **Save**</span></span>

<span data-ttu-id="f7717-191">추가 지침은 [SharePoint, OneDrive 및 Microsoft Teams용 ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md)의 경우 [SharePoint, OneDrive 및 Microsoft Teams용 ATP 설정](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md)을 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-191">See [ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) for additional guidance.</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="f7717-192">파일에 저작권 정보 추가</span><span class="sxs-lookup"><span data-stu-id="f7717-192">Add copyright information to your files</span></span>

<span data-ttu-id="f7717-193">Microsoft 365 규정 준수 관리 센터에서 민감도 레이블을 사용하는 경우, 조직의 Office 문서에 워터마크나 머리글 또는 바닥글을 자동으로 추가하도록 레이블을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-193">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="f7717-194">따라서 공유된 파일에 저작권 또는 기타 소유권 정보가 포함되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-194">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="f7717-195">레이블이 지정된 파일에 바닥글을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="f7717-195">To add a footer to a labeled file</span></span>

1. <span data-ttu-id="f7717-196">[Microsoft 365 규정 준수 관리 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-196">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="f7717-197">왼쪽 탐색 창에서 **솔루션** 의 **정보 보호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-197">In the left navigation, under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="f7717-198">바닥글을 추가하려는 레이블을 클릭한 다음 **레이블 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-198">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="f7717-199">**다음** 을 클릭하여 **콘텐츠 표시** 탭으로 이동한 다음, 콘텐츠 표시를 **설정** 합니다. </span><span class="sxs-lookup"><span data-stu-id="f7717-199">Click **Next** to reach the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="f7717-200">추가하려는 텍스트 유형의 확인란을 선택한 다음, **텍스트 사용자 지정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-200">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="f7717-201">문서에 추가하려는 텍스트를 입력하고 원하는 텍스트 옵션을 선택한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-201">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="f7717-202">![민감도 레이블의 콘텐츠 표시 설정 스크린샷](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="f7717-202">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="f7717-203">**다음** 을 클릭하여 마법사의 끝에 도달하고 **레이블 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-203">Click **Next** to reach the end of the wizard, and then click **Save label**.</span></span>

<span data-ttu-id="f7717-204">레이블에 콘텐츠 표시를 사용하는 경우, 사용자가 해당 레이블을 적용하면 사용자가 지정한 텍스트가 Office 문서에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-204">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7717-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7717-205">See Also</span></span>

[<span data-ttu-id="f7717-206">민감도 레이블 개요</span><span class="sxs-lookup"><span data-stu-id="f7717-206">Overview of sensitivity labels</span></span>](/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="f7717-207">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="f7717-207">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="f7717-208">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="f7717-208">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
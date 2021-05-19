---
title: 관리 대상 게스트와 B2B 엑스트라넷 작성
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 파트너 조직의 관리되는 게스트를 사용하여 B2B 엑스트라넷 사이트 또는 팀을 만드는 방법을 학습합니다.
ms.openlocfilehash: d76951da5d8affa1dac08cbdc68a91329ca069ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538246"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="556be-103">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="556be-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="556be-104">권한 [부여](/azure/active-directory/governance/entitlement-management-overview) 관리에서 Azure Active Directory 사용하여 B2B 엑스트라넷을 만들어 사용자 자격 관리를 사용하는 파트너 조직과 공동 작업을 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="556be-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="556be-105">이를 통해 사용자는 엑스트라넷 사이트 또는 팀에 자체 등록하고 승인 워크플로를 통해 액세스 권한을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="556be-106">파트너 조직은 공동 작업을 위해 리소스를 공유하는 이 방법을 통해 게스트를 끝에 유지 관리하고 승인하여 IT 부서의 부담을 줄이고 공동 작업 계약에 가장 익숙한 사용자가 사용자 액세스를 관리할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="556be-107">이 문서에서는 셀프 서비스 액세스 등록 모델을 통해 파트너 조직과 공유할 수 있는 리소스 패키지(이 경우 사이트 또는 팀)를 만드는 단계를 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="556be-108">시작하기 전에 파트너 조직과 공유할 사이트 또는 팀을 만들고 게스트 공유를 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="556be-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="556be-109">자세한 [내용은 사이트에서 게스트와](collaborate-in-site.md) [](collaborate-as-team.md) 공동 작업 또는 팀의 게스트와 공동 작업을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="556be-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="556be-110">게스트와 공동 작업할 때 거버넌스 정책을 유지 관리하는 데 사용할 수 있는 보안 및 규정 준수 기능에 대한 정보는 보안 게스트 공유 환경 만들기를 검토하는 것이 좋습니다. [](create-secure-guest-sharing-environment.md)</span><span class="sxs-lookup"><span data-stu-id="556be-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="556be-111">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="556be-111">License requirements</span></span>

<span data-ttu-id="556be-112">이 기능을 사용하려면 Azure AD Premium P2 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="556be-113">Azure Germany 및 Azure China 21Vianet과 같은 특수 클라우드는 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="556be-114">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="556be-114">Video demonstration</span></span>

<span data-ttu-id="556be-115">이 비디오에서는 이 문서에서 다루는 절차를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="556be-116">커넥트 조직 구성</span><span class="sxs-lookup"><span data-stu-id="556be-116">Connect the partner organization</span></span>

<span data-ttu-id="556be-117">파트너 조직에서 게스트를 초대하려면 파트너의 도메인을 파트너의 도메인에 연결된 조직으로 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="556be-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="556be-118">연결된 조직을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="556be-118">To add a connected organization</span></span>
1. <span data-ttu-id="556be-119">에서 [Azure Active Directory](https://aad.portal.azure.com)ID **거버넌스 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="556be-120">연결된 **조직 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="556be-121">연결된 **조직 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="556be-122">조직의 이름과 설명을 입력하고 **다음: 디렉터리 + 도메인 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="556be-123">디렉터리 **+ 도메인 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="556be-124">연결할 조직의 도메인을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="556be-125">를 **커넥트** **다음: 스폰서 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="556be-126">게스트에 대한 액세스를 승인할 사용자에 연결하려는 조직 또는 조직의 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="556be-127">**다음: 검토 + 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="556be-128">선택한 설정을 검토하고 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![조직의 연결된 조직 페이지 Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="556be-130">공유할 리소스 선택</span><span class="sxs-lookup"><span data-stu-id="556be-130">Choose the resources to share</span></span>

<span data-ttu-id="556be-131">파트너 조직과 공유할 리소스를 선택하는 첫 번째 단계는 포함할 카탈로그를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="556be-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="556be-132">카탈로그를 만들면</span><span class="sxs-lookup"><span data-stu-id="556be-132">To create a catalog</span></span>
1. <span data-ttu-id="556be-133">에서 [Azure Active Directory](https://aad.portal.azure.com)ID **거버넌스 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="556be-134">카탈로그를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="556be-135">새 **카탈로그 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="556be-136">카탈로그의 이름과 설명을 입력하고 외부  사용자에 대해 **사용** 및 사용이 모두 예로 설정되어 있도록 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="556be-137">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-137">Click **Create**.</span></span>

   ![ID 거버넌스에서 카탈로그 Azure Active Directory 스크린샷](../media/identity-governance-catalogs.png)

<span data-ttu-id="556be-139">카탈로그를 만든 후 파트너 SharePoint 공유할 사이트 또는 팀을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="556be-140">카탈로그에 리소스를 추가하는 경우</span><span class="sxs-lookup"><span data-stu-id="556be-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="556be-141">Azure AD ID 거버넌스에서 카탈로그를 **클릭한** 다음 리소스를 추가할 카탈로그를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="556be-142">리소스를 **클릭한** 다음 리소스 **추가 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="556be-143">엑스트라넷에 포함할 팀 또는 SharePoint 사이트를 선택한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![ID 관리의 카탈로그 리소스 Azure Active Directory 스크린샷](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="556be-145">공유할 리소스를 정의한 다음에는 파트너 사용자에게 부여되는 액세스 유형과 액세스를 요청하는 새 파트너 사용자의 승인 프로세스를 정의하는 액세스 패키지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="556be-146">액세스 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-146">To create an access package</span></span>
1. <span data-ttu-id="556be-147">Azure AD ID 거버넌스에서 카탈로그를 클릭한 다음 액세스 패키지를 만들 카탈로그를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="556be-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="556be-148">Access **패키지 를** 클릭한 다음 새 액세스 패키지 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="556be-149">액세스 패키지의 이름과 설명을 입력하고 다음: 리소스 **역할을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="556be-150">카탈로그에서 엑스트라넷에 사용할 리소스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="556be-151">각 리소스의 **역할** 열에서 엑스트라넷을 사용하는 게스트에게 부여할 사용자 역할을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="556be-152">다음: **요청 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="556be-153">액세스를 **요청할 수 있는 사용자 아래에서** 디렉터리에 없는 사용자 **를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="556be-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="556be-154">특정 연결된 조직 **옵션이** 선택되어 있는지 확인한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="556be-155">앞에서 추가한 연결된 조직을 선택한 다음 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="556be-156">승인 **아래에서** **승인 필요 에** 대해 예를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="556be-157">첫 **번째 승인자에서** 앞서 추가한 스폰서 중 하나를 선택하거나 특정 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="556be-158">Add **fallback(변경 추가)을** 클릭하고 fallback approver(변경 승인자)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="556be-159">사용 **에서** 예를 **선택 .**</span><span class="sxs-lookup"><span data-stu-id="556be-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="556be-160">다음: **수명 주기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="556be-161">사용할 만료 및 액세스 검토 설정을 선택하고 **다음: 검토 + 만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="556be-162">설정을 검토하고 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-162">Review your settings, and then click **Create**.</span></span>

    ![ID 거버넌스에서 액세스 패키지 Azure Active Directory 스크린샷](../media/identity-governance-access-packages.png)

<span data-ttu-id="556be-164">대규모 조직과 파트너가 될 경우 액세스 패키지를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="556be-165">패키지가 숨겨져 있는 경우 파트너 조직의 사용자는 내 액세스 포털에 패키지를 볼 *수* 없습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="556be-166">대신 패키지에 등록하려면 직접 링크를 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="556be-167">액세스 패키지를 숨기면 부적절한 액세스 요청 수가 줄어들고 파트너 조직의 포털에서 사용 가능한 액세스 패키지를 구성하여 유지하는 데도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="556be-168">액세스 패키지를 숨김으로 설정</span><span class="sxs-lookup"><span data-stu-id="556be-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="556be-169">Azure AD ID 거버넌스에서 **Access 패키지를** 클릭한 다음 액세스 패키지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="556be-170">개요 **페이지에서** 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="556be-171">**속성에서** **숨김에 예를** **선택하고** 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![액세스 패키지 속성 편집 화면 스크린샷](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="556be-173">파트너 사용자 초대</span><span class="sxs-lookup"><span data-stu-id="556be-173">Invite partner users</span></span>

<span data-ttu-id="556be-174">액세스 패키지를 숨김으로 설정하는 경우 사이트 또는 팀에 대한 액세스를 요청할 수 있도록 파트너 조직에 직접 링크를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="556be-175">액세스 포털 링크를 찾으면</span><span class="sxs-lookup"><span data-stu-id="556be-175">To find the access portal link</span></span>
1. <span data-ttu-id="556be-176">Azure AD ID 거버넌스에서 **Access 패키지를** 클릭한 다음 액세스 패키지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="556be-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="556be-177">개요 **페이지에서** 내 **액세스** 포털 링크의 클립보드에 복사 **링크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="556be-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![액세스 포털 링크가 있는 액세스 패키지 속성 스크린샷](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="556be-179">링크를 복사한 후 해당 링크를 파트너 조직의 연락처와 공유할 수 있으며 공동 작업 팀의 사용자에게 링크를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556be-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="556be-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="556be-180">See Also</span></span>

[<span data-ttu-id="556be-181">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="556be-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
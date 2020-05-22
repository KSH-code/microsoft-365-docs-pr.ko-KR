---
title: 관리 대상 게스트와 B2B 엑스트라넷 작성
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: 파트너 조직에서 관리 되는 게스트 사용자가 포함 된 B2B 엑스트라넷 사이트 또는 팀을 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: f01a558d55f497952494676f0148a1e3e4f06b35
ms.sourcegitcommit: b18949de721c6eef3521d5f8286d9b926ad4aabe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342526"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="a26cd-103">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="a26cd-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="a26cd-104">[Azure Active Directory 자격 관리](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 를 사용 하 여 B2B 엑스트라넷을 만들어 Azure active directory를 사용 하는 파트너 조직과 공동 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="a26cd-105">이를 통해 사용자는 엑스트라넷 사이트 또는 팀에서 자체 등록을 허용 하 고 승인 워크플로를 통해 액세스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="a26cd-106">공동 작업을 위해 리소스를 공유 하는 방법을 사용 하는 경우 파트너 조직은 최종 게스트 사용자를 유지 관리 및 승인 하 고 IT 부서의 부담을 줄이고 공동 작업 계약에 가장 익숙한 사용자 액세스를 허용 하는 데 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="a26cd-107">이 문서에서는 셀프 서비스 액세스 등록 모델을 통해 파트너 조직과 공유할 수 있는 리소스 패키지 (이 경우에는 사이트 또는 팀)를 만드는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="a26cd-108">시작 하기 전에 파트너 조직과 공유 하려는 사이트 또는 팀을 만들고 게스트 공유에 대해 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="a26cd-109">자세한 내용은 [사이트에서 게스트와의 공동 작업](collaborate-in-site.md) 또는 [팀의 게스트 공동 작업](collaborate-as-team.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a26cd-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="a26cd-110">또한 게스트와 공동으로 작업할 때 거 버 넌 스 정책을 유지 관리 하는 데 사용할 수 있는 보안 및 규정 준수 기능에 대 한 정보를 확인 하는 보안 [게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md) 를 검토 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a26cd-111">비디오 데모</span><span class="sxs-lookup"><span data-stu-id="a26cd-111">Video demonstration</span></span>

<span data-ttu-id="a26cd-112">이 비디오에서는이 문서에서 설명 하는 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-112">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="a26cd-113">파트너 조직 연결</span><span class="sxs-lookup"><span data-stu-id="a26cd-113">Connect the partner organization</span></span>

<span data-ttu-id="a26cd-114">파트너 조직에서 게스트를 초대 하려면 파트너의 도메인을 Azure Active Directory에 연결 된 조직으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-114">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="a26cd-115">연결 된 조직을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="a26cd-115">To add a connected organization</span></span>
1. <span data-ttu-id="a26cd-116">[Azure Active Directory](https://aad.portal.azure.com)에서 **Id 거 버 넌 스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-116">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="a26cd-117">**연결 된 조직을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-117">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="a26cd-118">**연결 된 조직 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-118">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="a26cd-119">조직의 이름과 설명을 입력 하 고 **다음: 디렉터리 + 도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-119">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="a26cd-120">**디렉터리 추가 + 도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-120">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="a26cd-121">연결 하려는 조직의 도메인을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-121">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="a26cd-122">**연결**을 클릭 하 고 **다음: 스폰서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-122">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="a26cd-123">게스트 사용자에 대 한 액세스를 승인할 사용자가 조직 또는 조직의 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-123">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="a26cd-124">**다음: 검토 + 만들기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-124">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="a26cd-125">선택한 설정을 검토 하 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-125">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Azure Active Directory의 연결 된 조직 페이지 스크린샷](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="a26cd-127">공유할 리소스 선택</span><span class="sxs-lookup"><span data-stu-id="a26cd-127">Choose the resources to share</span></span>

<span data-ttu-id="a26cd-128">파트너 조직과 공유할 리소스를 선택 하는 첫 번째 단계는이를 포함 하는 카탈로그를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-128">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="a26cd-129">카탈로그를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a26cd-129">To create a catalog</span></span>
1. <span data-ttu-id="a26cd-130">[Azure Active Directory](https://aad.portal.azure.com)에서 **Id 거 버 넌 스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-130">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="a26cd-131">**카탈로그**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-131">Click **Catalogs**.</span></span>
3. <span data-ttu-id="a26cd-132">**새 카탈로그**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-132">Click **New catalog**.</span></span>
4. <span data-ttu-id="a26cd-133">카탈로그에 대 한 이름 및 설명을 입력 하 고 **외부 사용자에 대해** **사용** 및 사용 하도록 설정 하는 것이 둘 다 **예**인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-133">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="a26cd-134">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-134">Click **Create**.</span></span>

   ![Azure Active Directory Id 거 버 넌 스의 카탈로그 페이지 스크린샷](../media/identity-governance-catalogs.png)

<span data-ttu-id="a26cd-136">카탈로그를 만든 후 파트너 조직과 공유 하려는 SharePoint 사이트 또는 팀을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-136">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="a26cd-137">카탈로그에 리소스를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="a26cd-137">To add resources to a catalog</span></span>
1. <span data-ttu-id="a26cd-138">Azure AD Id 거 버 넌 스에서 **카탈로그**를 클릭 한 다음 리소스를 추가 하려는 카탈로그를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-138">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="a26cd-139">**자원을** 클릭 한 다음 **자원 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-139">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="a26cd-140">엑스트라넷에 포함할 팀 또는 SharePoint 사이트를 선택 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-140">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Azure Active Directory Id 거 버 넌 스의 카탈로그 리소스 페이지 스크린샷](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="a26cd-142">공유할 리소스를 정의한 후에는 파트너 사용자에 게 부여 되는 액세스 유형 및 액세스를 요청 하는 새 파트너 사용자에 대 한 승인 프로세스를 정의 하는 액세스 패키지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-142">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="a26cd-143">Access 패키지를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a26cd-143">To create an access package</span></span>
1. <span data-ttu-id="a26cd-144">Azure AD Id 거 버 넌 스에서 **카탈로그**를 클릭 한 다음 액세스 패키지를 만들 카탈로그를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-144">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="a26cd-145">**액세스 패키지**를 클릭 한 다음 **새 Access 패키지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-145">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="a26cd-146">액세스 패키지의 이름과 설명을 입력 하 고 **다음: 리소스 역할**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-146">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="a26cd-147">엑스트라넷에 사용 하려는 카탈로그의 리소스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-147">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="a26cd-148">각 리소스에 대해 **역할** 열에서 엑스트라넷을 사용 하는 게스트 사용자에 게 부여할 사용자 역할을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-148">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="a26cd-149">**다음: 요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-149">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="a26cd-150">**액세스를 요청할 수 있는 사용자**에서 **디렉터리에 없는 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-150">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="a26cd-151">**연결 된 특정 조직** 옵션이 선택 되어 있는지 확인 하 고 **디렉터리 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-151">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="a26cd-152">이전에 추가한 연결 된 조직을 선택 하 고 **선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-152">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="a26cd-153">**승인**에서 **승인 필요**에 대해 **예** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-153">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="a26cd-154">**첫 번째 승인자**아래에서 이전에 추가한 스폰서 중 하나를 선택 하거나 특정 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-154">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="a26cd-155">**대체 추가** 를 클릭 하 고 대체 승인자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-155">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="a26cd-156">**사용**에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-156">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="a26cd-157">**다음: 수명 주기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-157">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="a26cd-158">사용 하려는 만료 및 액세스 검토 설정을 선택 하 고 **다음: 검토 + 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-158">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="a26cd-159">설정을 검토 하 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-159">Review your settings, and then click **Create**.</span></span>

    ![Azure Active Directory Id 거 버 넌 스의 access 패키지 화면 스크린샷](../media/identity-governance-access-packages.png)

<span data-ttu-id="a26cd-161">대규모 조직과 파트너를 연결 하는 경우 액세스 패키지를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-161">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="a26cd-162">패키지가 숨겨진 경우에는 파트너 조직의 사용자가 *내 액세스* 포털에서 패키지를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-162">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="a26cd-163">대신 패키지에 등록 하기 위해 직접 링크를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-163">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="a26cd-164">액세스 패키지를 숨기면 적절 하지 않은 액세스 요청의 수가 줄어들고 파트너 조직의 포털에 사용 가능한 액세스 패키지를 구성 하는 데도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-164">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="a26cd-165">액세스 패키지를 숨김으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a26cd-165">To set an access package to hidden</span></span>
1. <span data-ttu-id="a26cd-166">Azure AD Id 거 버 넌 스에서 **액세스 패키지**를 클릭 한 다음 액세스 패키지를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-166">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="a26cd-167">**개요** 페이지에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-167">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="a26cd-168">**속성**에서 **숨기기**에 대해 **예** 를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-168">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![액세스 패키지 속성 편집 화면의 스크린샷](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="a26cd-170">파트너 사용자 초대</span><span class="sxs-lookup"><span data-stu-id="a26cd-170">Invite partner users</span></span>

<span data-ttu-id="a26cd-171">액세스 패키지를 숨김으로 설정한 경우에는 사이트 또는 팀에 대 한 액세스를 요청할 수 있도록 파트너 조직에 대 한 직접 링크를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-171">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="a26cd-172">액세스 포털 링크를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="a26cd-172">To find the access portal link</span></span>
1. <span data-ttu-id="a26cd-173">Azure AD Id 거 버 넌 스에서 **액세스 패키지**를 클릭 한 다음 액세스 패키지를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-173">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="a26cd-174">**개요** 페이지에서 **내 액세스 포털 링크**에 대 한 **클립보드에 복사 링크를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-174">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![액세스 포털 링크를 사용한 access 패키지 속성 스크린샷](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="a26cd-176">링크를 복사한 후 파트너 조직에서이를 사용자의 대화 상대와 공유 하 고 공동 작업 팀원에 게 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26cd-176">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="a26cd-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a26cd-177">See Also</span></span>

[<span data-ttu-id="a26cd-178">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="a26cd-178">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)


---
title: 보안 게스트 공유 환경 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: Microsoft 365에서 안전한 게스트 공유 환경을 만드는 데 사용할 수 있는 옵션에 대해 알아보고, 공동 작업을 위한 게스트 액세스를 제공합니다.
ms.openlocfilehash: 0eb999d48bc0976d7c2bb32ff1bdba8d63409d81
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918469"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="03192-103">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="03192-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="03192-104">이 문서에서는 Microsoft 365에서 보안 게스트 공유 환경을 만들기 위한 다양 한 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="03192-105">다음은 사용할 수 있는 옵션에 대한 아이디어를 제공하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="03192-105">These are examples to give you an idea of the options available.</span></span> <span data-ttu-id="03192-106">조직의 보안 및 규정 준수 요구 사항을 충족하기 위해 다음과 같이 다양한 조합의 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span>

<span data-ttu-id="03192-107">이 문서에는 다음 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03192-107">This article includes:</span></span>

- <span data-ttu-id="03192-108">게스트에 대한 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="03192-108">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="03192-109">게스트에 대한 사용 약관 설정</span><span class="sxs-lookup"><span data-stu-id="03192-109">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="03192-110">게스트가 계속해서 팀 및 사이트에 대해 권한이 필요한지 주기적으로 확인하기 위한 분기별 게스트 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="03192-110">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="03192-111">관리되지 않은 장치에 대해서는 게스트가 웹에만 액세스하도록 제한</span><span class="sxs-lookup"><span data-stu-id="03192-111">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="03192-112">게스트가 매일 인증할 수 있도록 세션 시간 제한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="03192-112">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="03192-113">매우 중요한 프로젝트에 대한 중요한 정보 유형 만들기입니다.</span><span class="sxs-lookup"><span data-stu-id="03192-113">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="03192-114">중요한 정보 유형을 포함하는 문서에 대한 민감도 레이블을 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-114">Automatically assigning a sensitivity label to documents that contain a sensitive information type.</span></span>
- <span data-ttu-id="03192-115">민감도 레이블이 있는 파일에서 게스트 액세스를 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-115">Automatically removing guest access from files with a sensitivity label.</span></span>

<span data-ttu-id="03192-116">이 문서에서 다루는 일부 옵션은 게스트가 Azure Active Directory의 계정이 있어야 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-116">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="03192-117">파일과 폴더를 공유할 때 게스트가 디렉터리에 포함되도록 하려면 [Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)](/sharepoint/sharepoint-azureb2b-integration-preview)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03192-117">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="03192-118">이 문서에서는 게스트 공유 설정을 활성화하는 방법에 대해서는 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-118">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="03192-119">다른 시나리오의 게스트 공유 활성화에 대해 자세히 알아보려면 [조직 외부 사용자와 공동 작업](collaborate-with-people-outside-your-organization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03192-119">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="03192-120">게스트에 대한 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="03192-120">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="03192-121">다단계 인증은 계정이 손상될 가능성을 대폭 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03192-121">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="03192-122">게스트는 관리 정책이나 모범 사례를 준수하지 않는 개인 이메일 계정을 사용할 가능성이 높기 때문에 게스트에 대해 다단계 인증을 요구하는 것은 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-122">Since guests may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="03192-123">게스트의 사용자 이름 및 비밀번호가 도난될 경우 2단계 인증을 요구하면 알 수 없는 당사자가 내 사이트 및 파일에 액세스할 가능성이 대폭 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="03192-123">If a guest's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="03192-124">이 예제에서는 Azure Active Directory에서 조건부 액세서 정책을 사용하여 게스트에 대한 다단계 인증을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-124">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="03192-125">게스트에 대한 다단계 인증을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="03192-125">To set up multi-factor authentication for guests</span></span>

1. <span data-ttu-id="03192-126">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-126">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="03192-127">**조건부 액세스 | 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-127">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="03192-128">**이름** 필드에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-128">In the **Name** field, type a name.</span></span>
4. <span data-ttu-id="03192-129">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-129">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="03192-130">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-130">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="03192-131">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-131">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="03192-132">**클라우드 앱 또는 작업** 블레이드에 있는 **포함** 탭에서 **모든 클라우드 앱** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-132">On the **Cloud apps or actions** blade, select **All cloud apps** on the **Include** tab.</span></span>
8. <span data-ttu-id="03192-133">**액세스 제어** 아래에서 **허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-133">Under **Access controls**, click **Grant**.</span></span>
9. <span data-ttu-id="03192-134">**허용** 블레이드에서 **다단계 인증 필요** 확인란을 선택한 후, **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select**.</span></span>
10. <span data-ttu-id="03192-135">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-135">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="03192-136">이제 게스트는 공유 콘텐츠, 사이트 또는 팀에 액세스하기 전에 다단계 인증에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="03192-137">추가 정보</span><span class="sxs-lookup"><span data-stu-id="03192-137">More information</span></span>

[<span data-ttu-id="03192-138">Azure AD 다단계 인증 배포 계획</span><span class="sxs-lookup"><span data-stu-id="03192-138">Planning an Azure AD Multi-Factor Authentication deployment</span></span>](/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="03192-139">게스트에 대한 사용 약관 설정</span><span class="sxs-lookup"><span data-stu-id="03192-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="03192-140">일부의 경우에는 게스트는 조직의 비공개 계약 또는 다른 법적 계약에 서명을 하지 않은 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-140">In some situations guests may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="03192-141">게스트에게 공유된 파일에 액세스하기 전에 사용 약관이 동의하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="03192-142">처음 공유 파일 또는 사이트에 액세스하려고 시도할 때 사용 약관이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="03192-143">사용 약관을 만들려면 먼저 Word 또는 다른 작성 프로그램에서 문서를 만든 후에 .pdf 파일로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="03192-144">그런 다음 이 파일을 Azure AD에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="03192-145">Azure AD 사용 약관을 만들려면</span><span class="sxs-lookup"><span data-stu-id="03192-145">To create an Azure AD terms of use</span></span>

1. <span data-ttu-id="03192-146">Azure에 전역 관리자, 보안 관리자 또는 조건부 액세스 관리자로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="03192-147">[사용 약관](https://aka.ms/catou)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="03192-148">**새 사용 약관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-148">Click **New terms**.</span></span>

   ![Azure AD 새 사용 약관 설정의 스크린샷](../media/azure-ad-guest-terms-of-use.png)

4. <span data-ttu-id="03192-150">**이름** 을 입력하고 **이름을 표시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-150">Type a **Name** and **Display name**.</span></span>
6. <span data-ttu-id="03192-151">**사용 약관 문서** 의 경우 작성한 pdf 파일을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-151">For **Terms of use document**, browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="03192-152">사용 약관 문서의 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="03192-153">**사용자가 사용 약관을 확장해야 함** 을 **켜기** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-153">Set **Require users to expand the terms of use** to **On**.</span></span>
9. <span data-ttu-id="03192-154">**조건부 액세스** 의 **조건부 액세스 정책 템플릿으로 적용** 목록에서 **나중에 조건부 액세스 정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-154">Under **Conditional Access**, in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later**.</span></span>
10. <span data-ttu-id="03192-155">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-155">Click **Create**.</span></span>

<span data-ttu-id="03192-156">사용 약관을 만들었으면 다음 단계는 게스트에게 사용 약관을 표시하는 조건부 액세스 정책을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03192-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guests.</span></span>

<span data-ttu-id="03192-157">조건부 액세스 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="03192-157">To create a conditional access policy</span></span>

1. <span data-ttu-id="03192-158">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-158">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="03192-159">**조건부 액세스 | 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-159">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="03192-160">**이름** 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-160">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="03192-161">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-161">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="03192-162">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-162">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="03192-163">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-163">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="03192-164">**포함** 탭에서 **앱 선택** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-164">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="03192-165">**선택** 블레이드에서 **Microsoft Teams**, **Office 365 SharePoint Online**, 및 **Outlook Groups** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-165">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="03192-166">**액세스 제어** 아래에서 **허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-166">Under **Access controls**, click **Grant**.</span></span>
10. <span data-ttu-id="03192-167">**허용** 블레이드에서 **게스트 사용 약관** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-167">On the **Grant** blade, select **Guest terms of use**, and then click **Select**.</span></span>
11. <span data-ttu-id="03192-168">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-168">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="03192-169">이제 게스트가 처음으로 콘텐츠나 조직의 팀 또는 사이트에 액세스하려고 하면 사용 약관을 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-169">Now, the first time a guest attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

> [!NOTE]
> <span data-ttu-id="03192-170">조건부 액세스를 사용 하려면 Azure AD Premium P1 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-170">Using Conditional Access requires an Azure AD Premium P1 license.</span></span> <span data-ttu-id="03192-171">자세한 내용은 [조건부 액세스는 무엇인가요](/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03192-171">For more information, see [What is Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="more-information"></a><span data-ttu-id="03192-172">추가 정보</span><span class="sxs-lookup"><span data-stu-id="03192-172">More information</span></span>

[<span data-ttu-id="03192-173">Azure Active Directory 사용 약관</span><span class="sxs-lookup"><span data-stu-id="03192-173">Azure Active Directory terms of use</span></span>](/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="03192-174">게스트 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="03192-174">Set up guest access reviews</span></span>

<span data-ttu-id="03192-175">Azure AD의 액세스 검토로 다양한 팀과 그룹에 대한 주기적 사용자 액세스 검토를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-175">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="03192-176">특히 게스트에 대해 액세스 검토를 요청하여 게스트가 필요 이상으로 오랫동안 조직의 중요한 정보에 대한 액세스 권한을 유지하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-176">By requiring an access review for guests specifically, you can help ensure guests do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="03192-177">게스트 액세스 검토를 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="03192-177">To set up a guest access review</span></span>

1. <span data-ttu-id="03192-178">[ID 거버넌스 페이지](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)의 왼쪽 메뉴에서 **액세스 검토** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-178">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews**.</span></span>
2. <span data-ttu-id="03192-179">**새 액세스 검토** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-179">Click **New access review**.</span></span>
3. <span data-ttu-id="03192-180">**Teams + 그룹** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-180">Choose the **Teams + Groups** option.</span></span>
4. <span data-ttu-id="03192-181">**게스트 사용자가 있는 모든 Microsoft 365 그룹** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-181">Choose the **All Microsoft 365 groups with guest users** option.</span></span> <span data-ttu-id="03192-182">제외하려는 그룹은 **제외할 그룹 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-182">Click **Select group(s) to exclude** if you want to exclude any groups.</span></span>
5. <span data-ttu-id="03192-183">**게스트 사용자만** 옵션을 선택하고 **다음: 검토** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-183">Choose the **Guest users only** option, and then click **Next: Reviews**.</span></span>
6. <span data-ttu-id="03192-184">**검토자 선택** 에서 **그룹 소유자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-184">Under **Select reviewers**, choose **Group Owner(s)**.</span></span>
7. <span data-ttu-id="03192-185">**Fallback 검토자 선택** 을 클릭하고 Fallback 컴토자를 선택한 다음, **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-185">Click **Select fallback reviewers**, choose who should be the fallback reviewers, and then click **Select**.</span></span>
8. <span data-ttu-id="03192-186">**검토 되풀이 구체화** 에서 **분기별** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-186">Under **Specify recurrence of review**, choose **Quarterly**.</span></span>
9. <span data-ttu-id="03192-187">시작 날짜 및 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-187">Select a start date and duration.</span></span>
10. <span data-ttu-id="03192-188">**종료 기간** 은 **없음** 을 선택하고 **다음: 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-188">For **End**, choose **Never**, and then click **Next: Settings**.</span></span>

    ![Azure AD 액세스 검토 탭 스크린샷](../media/azure-ad-create-access-review.png)

11. <span data-ttu-id="03192-190">**설정** 탭에서 비즈니스 규칙과 규정 준수 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-190">On the **Settings** tab, review the settings for compliance with your business rules.</span></span>

    ![Azure AD 액세스 검토 설정 탭 스크린샷](../media/azure-ad-create-access-review-settings.png)

12. <span data-ttu-id="03192-192">**다음: 검토 + 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-192">Click **Next: Review + Create**.</span></span>
13. <span data-ttu-id="03192-193">**검토자 이름** 을 입력하고 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-193">Type a **Review name** and review the settings.</span></span>
14. <span data-ttu-id="03192-194">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-194">Click **Create**.</span></span>

<span data-ttu-id="03192-195">게스트가 팀이나 그룹에, 또는 개별 파일 및 폴더에 대한 액세스 권한을 받을 수 있음에 주의하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-195">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="03192-196">파일 및 폴더에 대한 액세스 권한을 주면 게스트가 특정 그룹에 추가되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-196">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="03192-197">팀이나 그룹에 속하지 않은 게스트에 대한 액세스 검토를 수행하려는 경우 모든 게스트가 포함되도록 Azure AD에서 동적 그룹을 만든 후에 해당 그룹에 대한 액세스 검토를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03192-197">If you want to do access reviews on guests who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span> <span data-ttu-id="03192-198">사이트 소유자 또한 [사이트에 대한 게스트 만료](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-198">Site owners can also manage [guest expiration for the site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span></span>

### <a name="more-information"></a><span data-ttu-id="03192-199">추가 정보</span><span class="sxs-lookup"><span data-stu-id="03192-199">More information</span></span>

[<span data-ttu-id="03192-200">Azure AD 액세스 검토를 사용하여 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="03192-200">Manage guest access with Azure AD access reviews</span></span>](/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="03192-201">Azure AD 액세스 검토에서 그룹 또는 애플리케이션에 대한 액세스 검토 만들기</span><span class="sxs-lookup"><span data-stu-id="03192-201">Create an access review of groups or applications in Azure AD access reviews</span></span>](/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guests"></a><span data-ttu-id="03192-202">게스트가 웹에만 액세스할 수 있게 설정</span><span class="sxs-lookup"><span data-stu-id="03192-202">Set up web-only access for guests</span></span>

<span data-ttu-id="03192-203">게스트가 웹 브라우저만 사용하여 팀, 사이트 및 파일에 액세스하게 하면 공격 영역을 줄이고 관리가 용이해지게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-203">You can reduce your attack surface and ease administration by requiring guests to access your teams, sites, and files by using a web browser only.</span></span>

<span data-ttu-id="03192-204">Microsoft 365 그룹 및 Teams의 경우, Azure AD 조건부 액세스 정책을 사용하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-204">For Microsoft 365 Groups and Teams, this is done with an Azure AD conditional access policy.</span></span> <span data-ttu-id="03192-205">SharePoint의 경우, 이는 SharePoint 관리 센터에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="03192-205">For SharePoint, this is configured in the SharePoint admin center.</span></span> <span data-ttu-id="03192-206">(사용자는 또한 [민감도 레이블을 사용하여 게스트를 웹 전용 액세스로 제한](../compliance/sensitivity-labels-teams-groups-sites.md)할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="03192-206">(You can also [use sensitivity labels to restrict guests to web-only access](../compliance/sensitivity-labels-teams-groups-sites.md).)</span></span>

<span data-ttu-id="03192-207">그룹 및 Teams에 대해 게스트를 웹 전용 액세스로 제한하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-207">To restrict guests to web-only access for Groups and Teams:</span></span>

1. <span data-ttu-id="03192-208">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-208">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="03192-209">**조건부 액세스 - 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-209">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="03192-210">**이름** 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-210">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="03192-211">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-211">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="03192-212">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-212">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="03192-213">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-213">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="03192-214">**포함** 탭에서 **앱 선택** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-214">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="03192-215">**선택** 블레이드에서 **Microsoft Teams** 및 **Outlook Groups** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-215">On the **Select** blade, select **Microsoft Teams** and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="03192-216">**할당** 아래에서 **조건** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-216">Under **Assignments**, click **Conditions**.</span></span>
10. <span data-ttu-id="03192-217">**조건** 블레이드에서 **클라이언트 앱** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-217">On the **Conditions** blade, click **Client apps**.</span></span>
11. <span data-ttu-id="03192-218">**클라이언트 앱** 블레이드에서 **구성** 의 경우 **예** 를 클릭하고 **모바일 앱 및 데스크톱 클라이언트**, **Exchange ActiveSync 클라이언트** 그리고 **기타 클라이언트** 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-218">On the **Client apps** blade, click **Yes** for **Configure**, and then select the **Mobile apps and desktop clients**, **Exchange ActiveSync clients**, and **Other clients** settings.</span></span> <span data-ttu-id="03192-219">**브라우저** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-219">Clear the **Browser** check box.</span></span>

    ![Azure AD 조건부 액세스 클라이언트 앱 설정 스크린샷](../media/azure-ad-conditional-access-client-mobile.png)

12. <span data-ttu-id="03192-221">**완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-221">Click **Done**.</span></span>
13. <span data-ttu-id="03192-222">**액세스 제어** 아래에서 **허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-222">Under **Access controls**, click **Grant**.</span></span>
14. <span data-ttu-id="03192-223">**허용** 블레이드에서 **디바이스를 준수 상태로 표시해야 함** 및 **하이브리드 Azure AD 조인 디바이스 필요** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-223">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device**.</span></span>
15. <span data-ttu-id="03192-224">**다중 컨트롤의 경우** 아래에서 **선택한 컨트롤 중 하나 필요** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-224">Under **For multiple controls**, select **Require one of the selected controls**, and then click **Select**.</span></span>
16. <span data-ttu-id="03192-225">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-225">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="03192-226">SharePoint에 대해 게스트를 웹 전용 액세스로 제한하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-226">To restrict guests to web-ony access for SharePoint</span></span>

1. <span data-ttu-id="03192-227">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)에서 **정책** 을 확장하고 **액세스 제어** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-227">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), expand **Policies** and click **Access control**.</span></span>
2. <span data-ttu-id="03192-228">**비관리형 장치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-228">Click **Unmanaged devices**.</span></span>
3. <span data-ttu-id="03192-229">**제한된 웹 전용 액세스를 허용** 옵션을 선택한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-229">Select the **Allow limited, web-only access** option, and then click **Save**.</span></span>

<span data-ttu-id="03192-230">SharePoint 관리 센터의 이 설정은 Azure AD에 지원 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03192-230">Note that this setting in the SharePoint admin center creates a supporting conditional access policy in Azure AD.</span></span>

## <a name="configure-a-session-timeout-for-guests"></a><span data-ttu-id="03192-231">게스트에 대한 세션 시간 제한 구성</span><span class="sxs-lookup"><span data-stu-id="03192-231">Configure a session timeout for guests</span></span>

<span data-ttu-id="03192-232">게스트가 정기적으로 인증하도록 요구하면 게스트의 장치가 보안이 유지되지 않을 경우 조직의 콘텐츠에 알 수 없는 사용자가 액세스할 가능성이 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-232">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest's device isn't kept secure.</span></span> <span data-ttu-id="03192-233">Azure AD에서 게스트에 대해 세션 시간 제한 조건부 액세스 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-233">You can configure a session timeout conditional access policy for guests in Azure AD.</span></span>

<span data-ttu-id="03192-234">게스트 세션 시간 제한 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="03192-234">To configure a guest session timeout policy</span></span>

1. <span data-ttu-id="03192-235">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-235">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="03192-236">**조건부 액세스 - 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-236">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="03192-237">**이름** 상자에 *게스트 세션 시간 제한* 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-237">In the **Name** box, type *Guest session timeout*.</span></span>
4. <span data-ttu-id="03192-238">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-238">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="03192-239">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-239">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="03192-240">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-240">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="03192-241">**포함** 탭에서 **앱 선택** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-241">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="03192-242">**선택** 블레이드에서 **Microsoft Teams**, **Office 365 SharePoint Online**, 및 **Outlook Groups** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-242">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="03192-243">**액세스 제어** 아래에서 **세션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-243">Under **Access controls**, click **Session**.</span></span>
10. <span data-ttu-id="03192-244">**세션** 블레이드에서 **로그인 빈도** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-244">On the **Session** blade, select **Sign-in frequency**.</span></span>
11. <span data-ttu-id="03192-245">시간에서 **1** 과 **일** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-245">Select **1** and **Days** for the time period, and then click **Select**.</span></span>
12. <span data-ttu-id="03192-246">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-246">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="03192-247">매우 중요한 프로젝트에 대한 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="03192-247">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="03192-248">중요한 정보 유형은 규정 준수 요구 사항을 적용하기 위해 정책 워크플로에 사용할 수 있는 미리 정의된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="03192-248">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="03192-249">Microsoft 365 규정 준수 센터는 운전면허증 번호, 신용카드 번호, 은행 계좌 번호 등을 포함한 100개 넘는 중요한 정보 유형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-249">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="03192-250">조직에 특정화된 콘텐츠를 관리하기 위해 사용자 지정 중요한 정보 유형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-250">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="03192-251">이 예제에서는 매우 중요한 프로젝트에 대한 사용자 지정 중요한 정보 유형을 만들어봅니다.</span><span class="sxs-lookup"><span data-stu-id="03192-251">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="03192-252">그런 다음 이 중요한 정보 유형을 사용하여 민감도 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-252">We can then use this sensitive information type to automatically apply a sensitivity label.</span></span>

<span data-ttu-id="03192-253">사용자 지정 중요한 정보 유형을 만들려면</span><span class="sxs-lookup"><span data-stu-id="03192-253">To create a sensitive information type</span></span>

1. <span data-ttu-id="03192-254">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)의 왼쪽 탐색에서 **분류** 를 확장한 후 **중요한 정보 유형** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-254">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification**, and then click **Sensitive info types**.</span></span>
2. <span data-ttu-id="03192-255">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-255">Click **Create**.</span></span>
3. <span data-ttu-id="03192-256">**이름** 과 **설명** 에 **프로젝트 Saturn** 을 입력한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-256">For **Name** and **Description**, type **Project Saturn**, and then click **Next**.</span></span>
4. <span data-ttu-id="03192-257">**요소 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-257">Click **Add an element**.</span></span>
5. <span data-ttu-id="03192-258">**다음이 포함된 콘텐츠 검색** 목록에서 **키워드** 를 선택한 후 키워드 상자에 *프로젝트 Saturn* 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-258">On the **Detect content containing** list, select **Keywords**, and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="03192-259">**다음** 을 클릭한 후 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-259">Click **Next**, and then click **Finish**.</span></span>
7. <span data-ttu-id="03192-260">중요한 정보 유형을 테스할지 묻는 메시지가 표시되면 **아니요** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-260">If asked if you would like to test the sensitive information type, click **No**.</span></span>

### <a name="more-information"></a><span data-ttu-id="03192-261">추가 정보</span><span class="sxs-lookup"><span data-stu-id="03192-261">More information</span></span>

[<span data-ttu-id="03192-262">사용자 지정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="03192-262">Custom sensitive information types</span></span>](/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="03192-263">중요한 정보 유형을 기반으로 민감도 레이블을 할당할 자동 레이블 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="03192-263">Create an auto-labeling policy to assign a sensitivity label based on a sensitive information type</span></span>

<span data-ttu-id="03192-264">조직에서 민감도 레이블을 사용하는 경우, 정의된 중요한 정보 유형을 포함하는 파일에 자동으로 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-264">If you are using sensitivity labels in your organization, you can automatically apply a label to files that contain defined sensitive information types.</span></span> 

<span data-ttu-id="03192-265">자동 레이블 지정 정책을 만들려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="03192-265">To create an auto-labeling policy</span></span>

1. <span data-ttu-id="03192-266">[Microsoft 365 규정 준수 관리 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03192-266">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="03192-267">왼쪽 탐색 창에서 **정보 보호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-267">In the left navigation, click **Information protection**.</span></span>
3. <span data-ttu-id="03192-268">**자동 레이블 지정** 탭에서 **자동 레이블 지정 정책 만들기** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-268">On the **Auto-labeling** tab, click **Create auto-labeling policy**.</span></span>
4. <span data-ttu-id="03192-269">**이 레이블을 적용하려는 정보 선택** 페이지에서 **사용자 지정** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-269">On the **Choose info you want this label applied to** page, choose **Custom** and click **Next**.</span></span>
5. <span data-ttu-id="03192-270">정책의 이름과 설명을 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-270">Type a name and description for the policy and click **Next**.</span></span>
6. <span data-ttu-id="03192-271">**레이블을 적용할 위치 선택** 페이지에서 **SharePoint 사이트** 를 켜고 **사이트 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-271">On the **Choose locations where you want to apply the label** page, turn on **SharePoint sites** and click **Choose sites**.</span></span>
7. <span data-ttu-id="03192-272">자동 레이블 지정을 설정하려는 사이트의 URL을 추가하고 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-272">Add the URLs for the sites where you want to turn on auto-labeling and click **Done**.</span></span>
8. <span data-ttu-id="03192-273">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-273">Click **Next**.</span></span>
9. <span data-ttu-id="03192-274">**일반 또는 고급 규칙 설정** 페이지에서 **일반 규칙** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-274">On the **Set up common or advanced rules** page, choose **Common rules** and click **Next**.</span></span>
10. <span data-ttu-id="03192-275">**모든 위치에서 콘텐츠에 대한 규칙 정의** 페이지에서 **새 규칙** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-275">On the **Define rules for content in all locations** page, click **New rule**.</span></span>
11. <span data-ttu-id="03192-276">**새 규칙** 페이지에서 규칙 이름을 지정하고 **조건 추가** 를 클릭한 다음, **콘텐츠에 중요한 정보 유형 포함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-276">On the **New rule** page, give the rule a name, click **Add condition**, and then click **Content contains sensitive info types**.</span></span>
12. <span data-ttu-id="03192-277">**추가** 를 클릭하고 **중요한 정보 유형** 을 클릭하고, 사용하려는 중요한 정보 유형을 선택하고 **추가** 를 클릭한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-277">Click **Add**, click **Sensitive info types**, choose the sensitive info types that you want to use, click **Add**, and then click **Save**.</span></span>
13. <span data-ttu-id="03192-278">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-278">Click **Next**.</span></span>
14. <span data-ttu-id="03192-279">**레이블 선택** 을 클릭하고 사용하려는 레이블을 선택한 다음 **추가** 를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="03192-279">Click **Choose a label**, select the label you want to use, and then click **Add**.</span></span>
15. <span data-ttu-id="03192-280">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-280">Click **Next**.</span></span>
16. <span data-ttu-id="03192-281">정책을 시뮬레이션 모드로 두고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-281">Leave the policy in simulation mode and click **Next**.</span></span>
17. <span data-ttu-id="03192-282">**정책 만들기** 를 클릭한 후 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-282">Click **Create policy**, and then click **Done**.</span></span>

<span data-ttu-id="03192-283">정책이 준비되었으면 사용자가 "프로젝트 Saturn"을 문서에 입력하는 경우, 자동 레이블 지정 정책이 파일을 스캔할 때 지정된 레이블을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-283">With the policy in place, when a user types "Project Saturn" into a document, the auto-labeling policy will automatically apply the specified label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="03192-284">추가 정보</span><span class="sxs-lookup"><span data-stu-id="03192-284">More information</span></span>

[<span data-ttu-id="03192-285">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="03192-285">Apply a sensitivity label to content automatically</span></span>](../compliance/apply-sensitivity-label-automatically.md)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="03192-286">매우 중요한 파일에 대한 게스트 액세스 권한을 제거할 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="03192-286">Create a DLP policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="03192-287">[DLP(데이터 손실 방지)](../compliance/data-loss-prevention-policies.md)를 사용하여 중요한 콘텐츠의 원치 않는 게스트와의 공유를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-287">You can use [data loss prevention (DLP)](../compliance/data-loss-prevention-policies.md) to prevent unwanted guest sharing of sensitive content.</span></span> <span data-ttu-id="03192-288">데이터 손실 방지는 파일의 민감도 레이블에 따라 조치를 취하고 게스트 액세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-288">Data loss prevention can take action based on a file's sensitivity label and remove guest access.</span></span>

<span data-ttu-id="03192-289">DLP 규칙을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-289">To create a DLP rule</span></span>

1. <span data-ttu-id="03192-290">Microsoft 365 준수 관리 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-290">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="03192-291">**정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-291">Click **Create policy**.</span></span>
3. <span data-ttu-id="03192-292">**사용자 지정** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-292">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="03192-293">정책 이름을 입력한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-293">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="03192-294">**정책을 적용할 위치** 페이지에서 **SharePoint 사이트** 및 **OneDrive 계정** 을 제외한 모든 설정을 해제한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-294">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="03192-295">**정책 설정 정의** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-295">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="03192-296">**고급 DLP 규칙 사용자 지정** 페이지에서 **규칙 만들기** 를 클릭하고 규칙의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-296">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="03192-297">**조건** 에서 **조건 추가** 를 클릭하고 **콘텐츠 포함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-297">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="03192-298">**추가** 를 클릭하고 **민감도 레이블** 을 선택하고, 사용하려는 레이블을 선택하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-298">Click **Add**, choose **Sensitivity labels**, choose the labels you want to use, and click **Add**.</span></span>

   ![조건 옵션, 중요한 정보 유형, 민감도 레이블, 보존 레이블 스크린샷.](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="03192-300">**작업** 에서 **작업 추가** 를 클릭하고 **액세스를 제한하거나 Microsoft 365 위치에서 콘텐츠를 암호화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-300">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="03192-301">**액세스를 제한하거나 Microsoft 365 위치에서 콘텐츠를 암호화** 확인란을 선택한 다음 **조직 외부 사용자만** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-301">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people outside your organization** option.</span></span>

      ![DLP 규칙 작업 옵션의 스크린샷](../media/dlp-remove-guest-access-sensitive-files.png)

12. <span data-ttu-id="03192-303">**저장** 을 클릭한 다음 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-303">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="03192-304">테스트 옵션을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-304">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="03192-305">**제출** 을 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-305">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="03192-306">게스트가 전체적으로 사이트나 팀의 구성원인 경우에는 정책이 액세스를 제거하지 않음에 유의하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03192-306">It's important to note that this policy doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="03192-307">게스트 구성원이 포함된 사이트 또는 팀의 매우 중요한 문서를 마련할 계획이면 [팀 내 비공개 채널](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)을 사용하고 비공개 채널의 조직 구성원에게만 허용하는 방법을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="03192-307">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) and only allowing members of your organization in the private channels.</span></span>

## <a name="additional-options"></a><span data-ttu-id="03192-308">추가 옵션</span><span class="sxs-lookup"><span data-stu-id="03192-308">Additional options</span></span>

<span data-ttu-id="03192-309">Microsoft 365 및 Azure Active Directory에는 게스트 공유 환경을 보호하는 데 도움이 되는 몇 가지 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-309">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="03192-310">사용자가 공유할 수 있는 사람을 제한하기 위해 허용 또는 거부된 공유 도메인 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-310">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="03192-311">자세한 내용은 [도메인별 SharePoint 및 OneDrive 콘텐츠 공유 제한](/sharepoint/restricted-domains-sharing) 및 [특정 조직의 B2B 사용자에게 초대 허용 또는 차단](/azure/active-directory/b2b/allow-deny-list)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03192-311">See [Restrict sharing of SharePoint and OneDrive content by domain](/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="03192-312">사용자가 연결할 수 있는 다른 Azure Active Directory 테넌트를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-312">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="03192-313">자세한 내용은 [테넌트 제한을 사용하여 SaaS 클라우드 응용 프로그램에 대한 액세스 관리](/azure/active-directory/manage-apps/tenant-restrictions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03192-313">See [Use tenant restrictions to manage access to SaaS cloud applications](/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="03192-314">파트너가 게스트 계정을 관리할 수 있는 관리형 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03192-314">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="03192-315">자세한 내용은 [관리 대상 게스트와 B2B 엑스트라넷 작성](/Office365/Enterprise/b2b-extranet)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03192-315">See [Create a B2B extranet with managed guests](/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="03192-316">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03192-316">See Also</span></span>

[<span data-ttu-id="03192-317">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="03192-317">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="03192-318">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="03192-318">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="03192-319">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="03192-319">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
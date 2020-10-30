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
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 이 문서에서는 Microsoft 365에서 안전한 게스트 공유 환경을 만드는 데 사용할 수 있는 옵션에 대해 알아봅니다.
ms.openlocfilehash: 3ca7dba7c22f1eaa24f1285e42aa3f4caaf70b65
ms.sourcegitcommit: 21c3e44862854c74e4008cfb661840f069c6b709
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787568"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="d1160-103">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="d1160-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="d1160-104">이 문서에서는 Microsoft 365에서 보안 게스트 공유 환경을 만들기 위한 다양 한 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="d1160-105">다음은 사용할 수 있는 옵션에 대한 아이디어를 제공하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-105">These are examples to give you an idea of the options available.</span></span> <span data-ttu-id="d1160-106">조직의 보안 및 규정 준수 요구 사항을 충족하기 위해 다음과 같이 다양한 조합의 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span>

<span data-ttu-id="d1160-107">이 문서에는 다음 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-107">This article includes:</span></span>

- <span data-ttu-id="d1160-108">게스트에 대한 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-108">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="d1160-109">게스트에 대한 사용 약관 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-109">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="d1160-110">게스트가 계속해서 팀 및 사이트에 대해 권한이 필요한지 주기적으로 확인하기 위한 분기별 게스트 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-110">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="d1160-111">관리되지 않은 장치에 대해서는 게스트가 웹에만 액세스하도록 제한</span><span class="sxs-lookup"><span data-stu-id="d1160-111">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="d1160-112">게스트가 매일 인증할 수 있도록 세션 시간 제한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d1160-112">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="d1160-113">매우 중요한 프로젝트에 대한 중요한 정보 유형 만들기입니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-113">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="d1160-114">중요한 정보 유형을 포함하는 문서에 대한 민감도 레이블을 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-114">Automatically assigning a sensitivity label to documents that contain a sensitive information type.</span></span>
- <span data-ttu-id="d1160-115">민감도 레이블이 있는 파일에서 게스트 액세스를 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-115">Automatically removing guest access from files with a sensitivity label.</span></span>

<span data-ttu-id="d1160-116">이 문서에서 다루는 일부 옵션은 게스트가 Azure Active Directory의 계정이 있어야 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-116">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="d1160-117">파일과 폴더를 공유할 때 게스트가 디렉터리에 포함되도록 하려면 [Azure AD B2B와 SharePoint 및 OneDrive의 통합(미리 보기)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d1160-117">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="d1160-118">이 문서에서는 게스트 공유 설정을 활성화하는 방법에 대해서는 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-118">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="d1160-119">다른 시나리오의 게스트 공유 활성화에 대해 자세히 알아보려면 [조직 외부 사용자와 공동 작업](collaborate-with-people-outside-your-organization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1160-119">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="d1160-120">게스트에 대한 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-120">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="d1160-121">다단계 인증은 계정이 손상될 가능성을 대폭 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-121">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="d1160-122">게스트 사용자는 관리 정책이나 모범 사례를 준수하지 않는 개인 이메일 계정을 사용할 가능성이 높기 때문에 게스트에 대해 다단계 인증을 요구하는 것은 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-122">Since guest users may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="d1160-123">게스트 사용자의 사용자 이름 및 비밀번호가 도난될 경우 2단계 인증을 요구하면 알 수 없는 당사자가 내 사이트 및 파일에 액세스할 가능성이 대폭 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-123">If a guest user's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="d1160-124">이 예제에서는 Azure Active Directory에서 조건부 액세서 정책을 사용하여 게스트에 대한 다단계 인증을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-124">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="d1160-125">게스트에 대한 다단계 인증을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d1160-125">To set up multi-factor authentication for guests</span></span>

1. <span data-ttu-id="d1160-126">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-126">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d1160-127">**조건부 액세스 | 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-127">On the **Conditional Access | Policies** blade, click **New policy** .</span></span>
3. <span data-ttu-id="d1160-128">**이름** 필드에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-128">In the **Name** field, type a name.</span></span>
4. <span data-ttu-id="d1160-129">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-129">Under **Assignments** , click **Users and groups** .</span></span>
5. <span data-ttu-id="d1160-130">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-130">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d1160-131">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-131">Under **Assignments** , click **Cloud apps or actions** .</span></span>
7. <span data-ttu-id="d1160-132">**클라우드 앱 또는 작업** 블레이드에 있는 **포함** 탭에서 **모든 클라우드 앱** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-132">On the **Cloud apps or actions** blade, select **All cloud apps** on the **Include** tab.</span></span>
8. <span data-ttu-id="d1160-133">**액세스 제어** 아래에서 **허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-133">Under **Access controls** , click **Grant** .</span></span>
9. <span data-ttu-id="d1160-134">**허용** 블레이드에서 **다단계 인증 필요** 확인란을 선택한 후, **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select** .</span></span>
10. <span data-ttu-id="d1160-135">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-135">On the **New** blade, under **Enable policy** , click **On** , and then click **Create** .</span></span>

<span data-ttu-id="d1160-136">이제 게스트는 공유 콘텐츠, 사이트 또는 팀에 액세스하기 전에 다단계 인증에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="d1160-137">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d1160-137">More information</span></span>

[<span data-ttu-id="d1160-138">Azure 다단계 인증 배포 계획</span><span class="sxs-lookup"><span data-stu-id="d1160-138">Planning an Azure Multi-Factor Authentication deployment</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="d1160-139">게스트에 대한 사용 약관 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="d1160-140">일부의 경우에는 게스트 사용자는 조직의 비공개 계약 또는 다른 법적 계약에 서명을 하지 않은 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-140">In some situations guest users may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="d1160-141">게스트에게 공유된 파일에 액세스하기 전에 사용 약관이 동의하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="d1160-142">처음 공유 파일 또는 사이트에 액세스하려고 시도할 때 사용 약관이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="d1160-143">사용 약관을 만들려면 먼저 Word 또는 다른 작성 프로그램에서 문서를 만든 후에 .pdf 파일로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="d1160-144">그런 다음 이 파일을 Azure AD에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="d1160-145">Azure AD 사용 약관을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d1160-145">To create an Azure AD terms of use</span></span>

1. <span data-ttu-id="d1160-146">Azure에 전역 관리자, 보안 관리자 또는 조건부 액세스 관리자로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="d1160-147">[사용 약관](https://aka.ms/catou)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="d1160-148">**새 사용 약관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-148">Click **New terms** .</span></span>

   ![Azure AD 새 사용 약관 설정의 스크린샷](../media/azure-ad-guest-terms-of-use.png)

4. <span data-ttu-id="d1160-150">**이름** 을 입력하고 **이름을 표시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-150">Type a **Name** and **Display name** .</span></span>
6. <span data-ttu-id="d1160-151">**사용 약관 문서** 의 경우 작성한 pdf 파일을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-151">For **Terms of use document** , browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="d1160-152">사용 약관 문서의 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="d1160-153">**사용자가 사용 약관을 확장해야 함** 을 **켜기** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-153">Set **Require users to expand the terms of use** to **On** .</span></span>
9. <span data-ttu-id="d1160-154">**조건부 액세스** 의 **조건부 액세스 정책 템플릿으로 적용** 목록에서 **나중에 조건부 액세스 정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-154">Under **Conditional Access** , in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later** .</span></span>
10. <span data-ttu-id="d1160-155">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-155">Click **Create** .</span></span>

<span data-ttu-id="d1160-156">사용 약관을 만들었으면 다음 단계는 게스트 사용자에게 사용 약관을 표시하는 조건부 액세스 정책을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guest users.</span></span>

<span data-ttu-id="d1160-157">조건부 액세스 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d1160-157">To create a conditional access policy</span></span>

1. <span data-ttu-id="d1160-158">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-158">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d1160-159">**조건부 액세스 | 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-159">On the **Conditional Access | Policies** blade, click **New policy** .</span></span>
3. <span data-ttu-id="d1160-160">**이름** 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-160">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d1160-161">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-161">Under **Assignments** , click **Users and groups** .</span></span>
5. <span data-ttu-id="d1160-162">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-162">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d1160-163">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-163">Under **Assignments** , click **Cloud apps or actions** .</span></span>
7. <span data-ttu-id="d1160-164">**포함** 탭에서 **앱 선택** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-164">On the **Include** tab, select **Select apps** , and then click **Select** .</span></span>
8. <span data-ttu-id="d1160-165">**선택** 블레이드에서 **Microsoft Teams** , **Office 365 SharePoint Online** , 및 **Outlook Groups** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-165">On the **Select** blade, select **Microsoft Teams** , **Office 365 SharePoint Online** , and **Outlook Groups** , and then click **Select** .</span></span>
9. <span data-ttu-id="d1160-166">**액세스 제어** 아래에서 **허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-166">Under **Access controls** , click **Grant** .</span></span>
10. <span data-ttu-id="d1160-167">**허용** 블레이드에서 **게스트 사용 약관** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-167">On the **Grant** blade, select **Guest terms of use** , and then click **Select** .</span></span>
11. <span data-ttu-id="d1160-168">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-168">On the **New** blade, under **Enable policy** , click **On** , and then click **Create** .</span></span>

<span data-ttu-id="d1160-169">이제 게스트 사용자가 처음으로 콘텐츠나 조직의 팀 또는 사이트에 액세스하려고 하면 사용 약관을 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-169">Now, the first time a guest user attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

> [!NOTE]
> <span data-ttu-id="d1160-170">조건부 액세스를 사용 하려면 Azure AD Premium P1 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-170">Using Conditional Access requires an Azure AD Premium P1 license.</span></span> <span data-ttu-id="d1160-171">자세한 내용은 [조건부 액세스는 무엇인가요](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1160-171">For more information, see [What is Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="more-information"></a><span data-ttu-id="d1160-172">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d1160-172">More information</span></span>

[<span data-ttu-id="d1160-173">Azure Active Directory 사용 약관</span><span class="sxs-lookup"><span data-stu-id="d1160-173">Azure Active Directory terms of use</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="d1160-174">게스트 액세스 검토 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-174">Set up guest access reviews</span></span>

<span data-ttu-id="d1160-175">Azure AD의 액세스 검토로 다양한 팀과 그룹에 대한 주기적 사용자 액세스 검토를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-175">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="d1160-176">특히 게스트에 대해 액세스 검토를 요청하여 게스트 사용자가 필요 이상으로 오랫동안 조직의 중요한 정보에 대한 액세스 권한을 유지하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-176">By requiring an access review for guests specifically, you can help ensure guest users do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="d1160-177">액세스 검토는 프로그램으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-177">Access reviews can be organized into programs.</span></span> <span data-ttu-id="d1160-178">프로그램은 보고 및 감사 목적으로 액세스 검토를 구성하는 데 사용할 수 있는 유사한 액세스 검토 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-178">A program is a grouping of similar access reviews that can be used to organize access reviews for reporting and auditing purposes.</span></span>

<span data-ttu-id="d1160-179">프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d1160-179">To create a program</span></span>

1. <span data-ttu-id="d1160-180">Azure Portal에 로그인하고 [ID 거버넌스 페이지](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-180">Sign in to the Azure portal and open the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).</span></span>
2. <span data-ttu-id="d1160-181">왼쪽 메뉴에서 **프로그램** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-181">In the left menu, click **Programs**</span></span>
3. <span data-ttu-id="d1160-182">**새 프로그램** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-182">Click **New program** .</span></span>
4. <span data-ttu-id="d1160-183">**이름** 및 **설명** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-183">Type a **Name**  and **Description** .</span></span>
5. <span data-ttu-id="d1160-184">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-184">Click **Create** .</span></span>

<span data-ttu-id="d1160-185">프로그램이 만들어지면 게스트 액세스 검토를 만들고 프로그램에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-185">Once the program has been created, we can create a guest access review and associate it with the program.</span></span>

<span data-ttu-id="d1160-186">게스트 사용자 액세스 검토를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d1160-186">To set up a guest user access review</span></span>

1. <span data-ttu-id="d1160-187">[ID 거버넌스 페이지](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade)의 왼쪽 메뉴에서 **액세스 검토** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-187">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews** .</span></span>
2. <span data-ttu-id="d1160-188">**새 액세스 검토** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-188">Click **New access review** .</span></span>

   ![Azure AD 액세스 검토 설정 스크린샷](../media/azure-ad-create-access-review.png)

3. <span data-ttu-id="d1160-190">**이름** 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-190">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d1160-191">**빈도** 는 **분기별** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-191">For **Frequency** , choose **Quarterly** .</span></span>
5. <span data-ttu-id="d1160-192">**종료** 는 **안 함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-192">For **End** , choose **Never** .</span></span>
6. <span data-ttu-id="d1160-193">**범위** 는 **게스트 사용자만** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-193">For **Scope** , choose **Guest users only** .</span></span>
7. <span data-ttu-id="d1160-194">**그룹** 을 클릭하고 액세스 검토에 포함하려는 그룹을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-194">Click **Group** , select the groups that you want to include in the access review, and then click **Select** .</span></span>
8. <span data-ttu-id="d1160-195">**프로그램** 아래에서 **프로그램에 연결** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-195">Under **Programs** , click **Link to program** .</span></span>
9. <span data-ttu-id="d1160-196">**프로그램 선택** 블레이드에서 **게스트 액세스 검토 프로그램** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-196">On the **Select a program** blade, choose **Guest access review program**</span></span>
10. <span data-ttu-id="d1160-197">**시작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-197">Click **Start** .</span></span>

<span data-ttu-id="d1160-198">각 지정 그룹에 대해 별도의 액세스 검토를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-198">A separate access review is created for each group that you specify.</span></span> <span data-ttu-id="d1160-199">각 그룹의 그룹 소유자는 그룹에 대한 게스트 액세스를 승인 또는 거부하는 전자 메일을 분기별로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-199">Group owners of each group will be emailed quarterly to approve or deny guest access to their groups.</span></span>

<span data-ttu-id="d1160-200">게스트가 팀이나 그룹에, 또는 개별 파일 및 폴더에 대한 액세스 권한을 받을 수 있음에 주의하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-200">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="d1160-201">파일 및 폴더에 대한 액세스 권한을 주면 게스트가 특정 그룹에 추가되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-201">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="d1160-202">팀이나 그룹에 속하지 않은 게스트 사용자에 대한 액세스 검토를 수행하려는 경우 모든 게스트가 포함되도록 Azure AD에서 동적 그룹을 만든 후에 해당 그룹에 대한 액세스 검토를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-202">If you want to do access reviews on guest users who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span> <span data-ttu-id="d1160-203">사이트 소유자 또한 [사이트에 대한 게스트 만료](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-203">Site owners can also manage [guest expiration for the site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span></span>

### <a name="more-information"></a><span data-ttu-id="d1160-204">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d1160-204">More information</span></span>

[<span data-ttu-id="d1160-205">Azure AD 액세스 검토를 사용하여 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="d1160-205">Manage guest access with Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="d1160-206">Azure AD 액세스 검토에서 그룹 또는 애플리케이션에 대한 액세스 검토 만들기</span><span class="sxs-lookup"><span data-stu-id="d1160-206">Create an access review of groups or applications in Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a><span data-ttu-id="d1160-207">게스트 사용자가 웹에만 액세스할 수 있게 설정</span><span class="sxs-lookup"><span data-stu-id="d1160-207">Set up web-only access for guest users</span></span>

<span data-ttu-id="d1160-208">게스트 사용자가 웹 브라우저만 사용하여 팀, 사이트 및 파일에 액세스하게 하면 공격 영역을 줄이고 관리가 용이해지게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-208">You can reduce your attack surface and ease administration by requiring guest users to access your teams, sites, and files by using a web browser only.</span></span>

<span data-ttu-id="d1160-209">Microsoft 365 그룹 및 Teams의 경우, Azure AD 조건부 액세스 정책을 사용하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-209">For Microsoft 365 Groups and Teams, this is done with an Azure AD conditional access policy.</span></span> <span data-ttu-id="d1160-210">SharePoint의 경우, 이는 SharePoint 관리 센터에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-210">For SharePoint, this is configured in the SharePoint admin center.</span></span> <span data-ttu-id="d1160-211">(사용자는 또한 [민감도 레이블을 사용하여 게스트를 웹 전용 액세스로 제한](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d1160-211">(You can also [use sensitivity labels to restrict guests to web-only access](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="d1160-212">그룹 및 팀에 대해 게스트를 웹 전용 액세스로 제한하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-212">To restrict guests to web-ony access for groups and teams</span></span>

1. <span data-ttu-id="d1160-213">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-213">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d1160-214">**조건부 액세스 - 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-214">On the **Conditional Access - Policies** blade, click **New policy** .</span></span>
3. <span data-ttu-id="d1160-215">**이름** 상자에 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-215">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d1160-216">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-216">Under **Assignments** , click **Users and groups** .</span></span>
5. <span data-ttu-id="d1160-217">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-217">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d1160-218">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-218">Under **Assignments** , click **Cloud apps or actions** .</span></span>
7. <span data-ttu-id="d1160-219">**포함** 탭에서 **앱 선택** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-219">On the **Include** tab, select **Select apps** , and then click **Select** .</span></span>
8. <span data-ttu-id="d1160-220">**선택** 블레이드에서 **Microsoft Teams** 및 **Outlook Groups** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-220">On the **Select** blade, select **Microsoft Teams** and **Outlook Groups** , and then click **Select** .</span></span>
9. <span data-ttu-id="d1160-221">**할당** 아래에서 **조건** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-221">Under **Assignments** , click **Conditions** .</span></span>
10. <span data-ttu-id="d1160-222">**조건** 블레이드에서 **클라이언트 앱** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-222">On the **Conditions** blade, click **Client apps** .</span></span>
11. <span data-ttu-id="d1160-223">**클라이언트 앱** 블레이드에서 **구성** 의 경우 **예** 를 클릭하고 **모바일 앱 및 데스크톱 클라이언트** , **Exchange ActiveSync 클라이언트** 그리고 **기타 클라이언트** 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-223">On the **Client apps** blade, click **Yes** for **Configure** , and then select the **Mobile apps and desktop clients** , **Exchange ActiveSync clients** , and **Other clients** settings.</span></span> <span data-ttu-id="d1160-224">**브라우저** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-224">Clear the **Browser** check box.</span></span>

    ![Azure AD 조건부 액세스 클라이언트 앱 설정 스크린샷](../media/azure-ad-conditional-access-client-mobile.png)

12. <span data-ttu-id="d1160-226">**완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-226">Click **Done** .</span></span>
13. <span data-ttu-id="d1160-227">**액세스 제어** 아래에서 **허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-227">Under **Access controls** , click **Grant** .</span></span>
14. <span data-ttu-id="d1160-228">**허용** 블레이드에서 **디바이스를 준수 상태로 표시해야 함** 및 **하이브리드 Azure AD 조인 디바이스 필요** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-228">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device** .</span></span>
15. <span data-ttu-id="d1160-229">**다중 컨트롤의 경우** 아래에서 **선택한 컨트롤 중 하나 필요** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-229">Under **For multiple controls** , select **Require one of the selected controls** , and then click **Select** .</span></span>
16. <span data-ttu-id="d1160-230">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-230">On the **New** blade, under **Enable policy** , click **On** , and then click **Create** .</span></span>

<span data-ttu-id="d1160-231">SharePoint에 대해 게스트를 웹 전용 액세스로 제한하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-231">To restrict guests to web-ony access for SharePoint</span></span>

1. <span data-ttu-id="d1160-232">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)에서 **정책** 을 확장하고 **액세스 제어** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-232">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), expand **Policies** and click **Access control** .</span></span>
2. <span data-ttu-id="d1160-233">**비관리형 장치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-233">Click **Unmanaged devices** .</span></span>
3. <span data-ttu-id="d1160-234">**제한된 웹 전용 액세스를 허용** 옵션을 선택한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-234">Select the **Allow limited, web-only access** option, and then click **Save** .</span></span>

<span data-ttu-id="d1160-235">SharePoint 관리 센터의 이 설정은 Azure AD에 지원 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-235">Note that this setting in the SharePoint admin center creates a supporting conditional access policy in Azure AD.</span></span>

## <a name="configure-a-session-timeout-for-guest-users"></a><span data-ttu-id="d1160-236">게스트 사용자에 대한 세션 시간 제한 구성</span><span class="sxs-lookup"><span data-stu-id="d1160-236">Configure a session timeout for guest users</span></span>

<span data-ttu-id="d1160-237">게스트가 정기적으로 인증하도록 요구하면 게스트 사용자의 장치가 보안이 유지되지 않을 경우 조직의 콘텐츠에 알 수 없는 사용자가 액세스할 가능성이 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-237">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest user's device isn't kept secure.</span></span> <span data-ttu-id="d1160-238">Azure AD에서 게스트 사용자에 대해 세션 시간 제한 조건부 액세스 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-238">You can configure a session timeout conditional access policy for guest users in Azure AD.</span></span>

<span data-ttu-id="d1160-239">게스트 세션 시간 제한 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d1160-239">To configure a guest session timeout policy</span></span>

1. <span data-ttu-id="d1160-240">[Azure 조건부 액세스 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-240">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d1160-241">**조건부 액세스 - 정책** 블레이드에서 **새 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-241">On the **Conditional Access - Policies** blade, click **New policy** .</span></span>
3. <span data-ttu-id="d1160-242">**이름** 상자에 *게스트 세션 시간 제한* 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-242">In the **Name** box, type *Guest session timeout* .</span></span>
4. <span data-ttu-id="d1160-243">**할당** 아래에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-243">Under **Assignments** , click **Users and groups** .</span></span>
5. <span data-ttu-id="d1160-244">**사용자 및 그룹** 블레이드에서 **사용자 및 그룹 선택** 을 선택하고 **모든 게스트 및 외부 사용자** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-244">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d1160-245">**할당** 에서 **클라우드 앱 또는 작업** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-245">Under **Assignments** , click **Cloud apps or actions** .</span></span>
7. <span data-ttu-id="d1160-246">**포함** 탭에서 **앱 선택** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-246">On the **Include** tab, select **Select apps** , and then click **Select** .</span></span>
8. <span data-ttu-id="d1160-247">**선택** 블레이드에서 **Microsoft Teams** , **Office 365 SharePoint Online** , 및 **Outlook Groups** 를 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-247">On the **Select** blade, select **Microsoft Teams** , **Office 365 SharePoint Online** , and **Outlook Groups** , and then click **Select** .</span></span>
9. <span data-ttu-id="d1160-248">**액세스 제어** 아래에서 **세션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-248">Under **Access controls** , click **Session** .</span></span>
10. <span data-ttu-id="d1160-249">**세션** 블레이드에서 **로그인 빈도** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-249">On the **Session** blade, select **Sign-in frequency** .</span></span>
11. <span data-ttu-id="d1160-250">시간에서 **1** 과 **일** 을 선택한 후 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-250">Select **1** and **Days** for the time period, and then click **Select** .</span></span>
12. <span data-ttu-id="d1160-251">**새로 만들기** 블레이드의 **정책 사용** 에서 **설정** 을 클릭한 후 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-251">On the **New** blade, under **Enable policy** , click **On** , and then click **Create** .</span></span>

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="d1160-252">매우 중요한 프로젝트에 대한 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="d1160-252">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="d1160-253">중요한 정보 유형은 규정 준수 요구 사항을 적용하기 위해 정책 워크플로에 사용할 수 있는 미리 정의된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-253">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="d1160-254">Microsoft 365 규정 준수 센터는 운전면허증 번호, 신용카드 번호, 은행 계좌 번호 등을 포함한 100개 넘는 중요한 정보 유형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-254">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="d1160-255">조직에 특정화된 콘텐츠를 관리하기 위해 사용자 지정 중요한 정보 유형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-255">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="d1160-256">이 예제에서는 매우 중요한 프로젝트에 대한 사용자 지정 중요한 정보 유형을 만들어봅니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-256">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="d1160-257">그런 다음 이 중요한 정보 유형을 사용하여 민감도 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-257">We can then use this sensitive information type to automatically apply a sensitivity label.</span></span>

<span data-ttu-id="d1160-258">사용자 지정 중요한 정보 유형을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d1160-258">To create a sensitive information type</span></span>

1. <span data-ttu-id="d1160-259">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)의 왼쪽 탐색에서 **분류** 를 확장한 후 **중요한 정보 유형** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-259">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification** , and then click **Sensitive info types** .</span></span>
2. <span data-ttu-id="d1160-260">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-260">Click **Create** .</span></span>
3. <span data-ttu-id="d1160-261">**이름** 과 **설명** 에 **프로젝트 Saturn** 을 입력한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-261">For **Name** and **Description** , type **Project Saturn** , and then click **Next** .</span></span>
4. <span data-ttu-id="d1160-262">**요소 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-262">Click **Add an element** .</span></span>
5. <span data-ttu-id="d1160-263">**다음이 포함된 콘텐츠 검색** 목록에서 **키워드** 를 선택한 후 키워드 상자에 *프로젝트 Saturn* 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-263">On the **Detect content containing** list, select **Keywords** , and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="d1160-264">**다음** 을 클릭한 후 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-264">Click **Next** , and then click **Finish** .</span></span>
7. <span data-ttu-id="d1160-265">중요한 정보 유형을 테스할지 묻는 메시지가 표시되면 **아니요** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-265">If asked if you would like to test the sensitive information type, click **No** .</span></span>

### <a name="more-information"></a><span data-ttu-id="d1160-266">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d1160-266">More information</span></span>

[<span data-ttu-id="d1160-267">사용자 지정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="d1160-267">Custom sensitive information types</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="d1160-268">중요한 정보 유형을 기반으로 민감도 레이블을 할당할 자동 레이블 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d1160-268">Create an auto-labeling policy to assign a sensitivity label based on a sensitive information type</span></span>

<span data-ttu-id="d1160-269">조직에서 민감도 레이블을 사용하는 경우, 정의된 중요한 정보 유형을 포함하는 파일에 자동으로 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-269">If you are using sensitivity labels in your organization, you can automatically apply a label to files that contain defined sensitive information types.</span></span> 

<span data-ttu-id="d1160-270">자동 레이블 지정 정책을 만들려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="d1160-270">To create an auto-labeling policy</span></span>

1. <span data-ttu-id="d1160-271">[Microsoft 365 규정 준수 관리 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-271">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="d1160-272">왼쪽 탐색 창에서 **정보 보호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-272">In the left navigation, click **Information protection** .</span></span>
3. <span data-ttu-id="d1160-273">**자동 레이블 지정** 탭에서 **자동 레이블 지정 정책 만들기** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-273">On the **Auto-labeling** tab, click **Create auto-labeling policy** .</span></span>
4. <span data-ttu-id="d1160-274">**이 레이블을 적용하려는 정보 선택** 페이지에서 **사용자 지정** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-274">On the **Choose info you want this label applied to** page, choose **Custom** and click **Next** .</span></span>
5. <span data-ttu-id="d1160-275">정책의 이름과 설명을 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-275">Type a name and description for the policy and click **Next** .</span></span>
6. <span data-ttu-id="d1160-276">**레이블을 적용할 위치 선택** 페이지에서 **SharePoint 사이트** 를 켜고 **사이트 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-276">On the **Choose locations where you want to apply the label** page, turn on **SharePoint sites** and click **Choose sites** .</span></span>
7. <span data-ttu-id="d1160-277">자동 레이블 지정을 설정하려는 사이트의 URL을 추가하고 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-277">Add the URLs for the sites where you want to turn on auto-labeling and click **Done** .</span></span>
8. <span data-ttu-id="d1160-278">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-278">Click **Next** .</span></span>
9. <span data-ttu-id="d1160-279">**일반 또는 고급 규칙 설정** 페이지에서 **일반 규칙** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-279">On the **Set up common or advanced rules** page, choose **Common rules** and click **Next** .</span></span>
10. <span data-ttu-id="d1160-280">**모든 위치에서 콘텐츠에 대한 규칙 정의** 페이지에서 **새 규칙** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-280">On the **Define rules for content in all locations** page, click **New rule** .</span></span>
11. <span data-ttu-id="d1160-281">**새 규칙** 페이지에서 규칙 이름을 지정하고 **조건 추가** 를 클릭한 다음, **콘텐츠에 중요한 정보 유형 포함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-281">On the **New rule** page, give the rule a name, click **Add condition** , and then click **Content contains sensitive info types** .</span></span>
12. <span data-ttu-id="d1160-282">**추가** 를 클릭하고 **중요한 정보 유형** 을 클릭하고, 사용하려는 중요한 정보 유형을 선택하고 **추가** 를 클릭한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-282">Click **Add** , click **Sensitive info types** , choose the sensitive info types that you want to use, click **Add** , and then click **Save** .</span></span>
13. <span data-ttu-id="d1160-283">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-283">Click **Next** .</span></span>
14. <span data-ttu-id="d1160-284">**레이블 선택** 을 클릭하고 사용하려는 레이블을 선택한 다음 **추가** 를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="d1160-284">Click **Choose a label** , select the label you want to use, and then click **Add** .</span></span>
15. <span data-ttu-id="d1160-285">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-285">Click **Next** .</span></span>
16. <span data-ttu-id="d1160-286">정책을 시뮬레이션 모드로 두고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-286">Leave the policy in simulation mode and click **Next** .</span></span>
17. <span data-ttu-id="d1160-287">**정책 만들기** 를 클릭한 후 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-287">Click **Create policy** , and then click **Done** .</span></span>

<span data-ttu-id="d1160-288">정책이 준비되었으면 사용자가 "프로젝트 Saturn"을 문서에 입력하는 경우, 자동 레이블 지정 정책이 파일을 스캔할 때 지정된 레이블을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-288">With the policy in place, when a user types "Project Saturn" into a document, the auto-labeling policy will automatically apply the specified label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="d1160-289">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d1160-289">More information</span></span>

[<span data-ttu-id="d1160-290">민감도 레이블을 콘텐츠에 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="d1160-290">Apply a sensitivity label to content automatically</span></span>](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="d1160-291">매우 중요한 파일에 대한 게스트 액세스 권한을 제거할 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d1160-291">Create a DLP policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="d1160-292">[DLP(데이터 손실 방지)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)를 사용하여 중요한 콘텐츠의 원치 않는 게스트와의 공유를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-292">You can use [data loss prevention (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to prevent unwanted guest sharing of sensitive content.</span></span> <span data-ttu-id="d1160-293">데이터 손실 방지는 파일의 민감도 레이블에 따라 조치를 취하고 게스트 액세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-293">Data loss prevention can take action based on a file's sensitivity label and remove guest access.</span></span>

<span data-ttu-id="d1160-294">DLP 규칙을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-294">To create a DLP rule</span></span>

1. <span data-ttu-id="d1160-295">Microsoft 365 준수 관리 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-295">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="d1160-296">**정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-296">Click **Create policy** .</span></span>
3. <span data-ttu-id="d1160-297">**사용자 지정** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-297">Choose **Custom** and click **Next** .</span></span>
4. <span data-ttu-id="d1160-298">정책 이름을 입력한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-298">Type a name for the policy and click **Next** .</span></span>
5. <span data-ttu-id="d1160-299">**정책을 적용할 위치** 페이지에서 **SharePoint 사이트** 및 **OneDrive 계정** 을 제외한 모든 설정을 해제한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-299">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts** , and then click **Next** .</span></span>
6. <span data-ttu-id="d1160-300">**정책 설정 정의** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-300">On the **Define policy settings** page, click **Next** .</span></span>
7. <span data-ttu-id="d1160-301">**고급 DLP 규칙 사용자 지정** 페이지에서 **규칙 만들기** 를 클릭하고 규칙의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-301">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="d1160-302">**조건** 에서 **조건 추가** 를 클릭하고 **콘텐츠 포함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-302">Under **Conditions** , click **Add condition** , and choose **Content contains** .</span></span>
9. <span data-ttu-id="d1160-303">**추가** 를 클릭하고 **민감도 레이블** 을 선택하고, 사용하려는 레이블을 선택하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-303">Click **Add** , choose **Sensitivity labels** , choose the labels you want to use, and click **Add** .</span></span>

   ![조건 옵션, 중요한 정보 유형, 민감도 레이블, 보존 레이블 스크린샷.](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="d1160-305">**작업** 에서 **작업 추가** 를 클릭하고 **액세스를 제한하거나 Microsoft 365 위치에서 콘텐츠를 암호화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-305">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations** .</span></span>
11. <span data-ttu-id="d1160-306">**액세스를 제한하거나 Microsoft 365 위치에서 콘텐츠를 암호화** 확인란을 선택한 다음 **조직 외부 사용자만** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-306">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people outside your organization** option.</span></span>

      ![DLP 규칙 작업 옵션의 스크린샷](../media/dlp-remove-guest-access-sensitive-files.png)

12. <span data-ttu-id="d1160-308">**저장** 을 클릭한 다음 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-308">Click **Save** and then click **Next** .</span></span>
13. <span data-ttu-id="d1160-309">테스트 옵션을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-309">Choose your test options and click **Next** .</span></span>
14. <span data-ttu-id="d1160-310">**제출** 을 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-310">Click **Submit** , and then click **Done** .</span></span>

<span data-ttu-id="d1160-311">게스트가 전체적으로 사이트나 팀의 구성원인 경우에는 정책이 액세스를 제거하지 않음에 유의하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-311">It's important to note that this policy doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="d1160-312">게스트 구성원이 포함된 사이트 또는 팀의 매우 중요한 문서를 마련할 계획이면 [팀 내 비공개 채널](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)을 사용하고 비공개 채널의 조직 구성원에게만 허용하는 방법을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="d1160-312">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) and only allowing members of your organization in the private channels.</span></span>

## <a name="additional-options"></a><span data-ttu-id="d1160-313">추가 옵션</span><span class="sxs-lookup"><span data-stu-id="d1160-313">Additional options</span></span>

<span data-ttu-id="d1160-314">Microsoft 365 및 Azure Active Directory에는 게스트 공유 환경을 보호하는 데 도움이 되는 몇 가지 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-314">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="d1160-315">사용자가 공유할 수 있는 사람을 제한하기 위해 허용 또는 거부된 공유 도메인 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-315">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="d1160-316">자세한 내용은 [도메인별 SharePoint 및 OneDrive 콘텐츠 공유 제한](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) 및 [특정 조직의 B2B 사용자에게 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1160-316">See [Restrict sharing of SharePoint and OneDrive content by domain](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="d1160-317">사용자가 연결할 수 있는 다른 Azure Active Directory 테넌트를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-317">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="d1160-318">자세한 내용은 [테넌트 제한을 사용하여 SaaS 클라우드 응용 프로그램에 대한 액세스 관리](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1160-318">See [Use tenant restrictions to manage access to SaaS cloud applications](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="d1160-319">파트너가 게스트 계정을 관리할 수 있는 관리형 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-319">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="d1160-320">자세한 내용은 [관리 대상 게스트와 B2B 엑스트라넷 작성](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1160-320">See [Create a B2B extranet with managed guests](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1160-321">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1160-321">See Also</span></span>

[<span data-ttu-id="d1160-322">게스트와 공유할 때 파일에 실수로 발생하는 노출을 제한</span><span class="sxs-lookup"><span data-stu-id="d1160-322">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="d1160-323">인증되지 않은 사용자와 파일 및 폴더를 공유하는 모범 사례</span><span class="sxs-lookup"><span data-stu-id="d1160-323">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="d1160-324">관리 대상 게스트와 B2B 엑스트라넷 작성</span><span class="sxs-lookup"><span data-stu-id="d1160-324">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

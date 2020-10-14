---
title: 게스트 및 외부 B2B 액세스를 허용 하기 위한 id 및 장치 액세스 정책 | Microsoft 365 Microsoft Docs
description: 게스트 및 외부 사용자의 액세스를 보호 하기 위한 권장 조건부 액세스 및 관련 정책에 대해 설명 합니다.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 4a0eb530df2709294bf1c9aa0cf285e59c9fd1f8
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464207"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="79451-103">게스트 및 외부 B2B 액세스를 허용 하기 위한 정책</span><span class="sxs-lookup"><span data-stu-id="79451-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="79451-104">이 문서에서는 azure AD (B2B 기업 간) 계정을 가진 게스트 및 외부 사용자에 대 한 액세스를 허용 하도록 권장 되는 일반 id 및 장치 액세스 정책을 조정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="79451-105">이 지침은 [일반 id 및 장치 액세스 정책을](identity-access-policies.md)기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="79451-106">이러한 권장 사항은 보호의 **기본** 계층에 적용 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="79451-107">그러나 **중요** 및 **높은 규제** 보호에 대 한 요구 사항의 세분성을 기반으로 권장 사항을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="79451-108">Azure AD 테 넌 트에서 인증 하기 위해 B2B 계정에 대 한 경로를 제공 하면 이러한 계정에 전체 환경에 대 한 액세스 권한이 부여 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="79451-109">B2B 사용자 및 해당 계정은 조건부 액세스 정책에 부여 된 서비스 내에서 파일과 같이 공유 되는 리소스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="79451-110">게스트 및 외부 액세스를 허용 하 고 보호 하기 위해 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="79451-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="79451-111">Azure AD B2B 계정을 사용 하 여 게스트 및 외부 액세스를 보호 하기 위해 일반 id 및 장치 액세스 정책에서 추가 하거나 업데이트할 정책을 다음 다이어그램에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span> 

<span data-ttu-id="79451-112">[![게스트 액세스 보호를 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="79451-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="79451-113">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="79451-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="79451-114">다음 표에는 만들고 업데이트 해야 하는 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="79451-115">공통 정책- [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="79451-116">보호 수준</span><span class="sxs-lookup"><span data-stu-id="79451-116">Protection level</span></span>|<span data-ttu-id="79451-117">정책</span><span class="sxs-lookup"><span data-stu-id="79451-117">Policies</span></span>|<span data-ttu-id="79451-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="79451-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="79451-119">**기준**</span><span class="sxs-lookup"><span data-stu-id="79451-119">**Baseline**</span></span>|[<span data-ttu-id="79451-120">게스트 및 외부 사용자에 대 한 MFA 항상 필요</span><span class="sxs-lookup"><span data-stu-id="79451-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="79451-121">이 새 정책을 만들고 다음을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="79451-122">**포함 > 사용자 및 그룹 > 할당**에 대해 **사용자 및 그룹 선택을**선택 하 고 **모든 게스트 및 외부 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="79451-123">**로그인 > > 조건**에 대해 항상 MFA (multi-factor authentication)를 적용 하도록 모든 옵션을 선택 하지 않은 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
|        |[<span data-ttu-id="79451-124">로그인 위험이 *보통* 또는 *높을* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="79451-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="79451-125">이 정책을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-125">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="79451-126">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="79451-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="79451-127">이 정책을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="79451-128">조건부 액세스 정책에서 게스트 및 외부 사용자를 포함 하거나 제외 하려면 **사용자 및 그룹에 포함 또는 제외 > > 할당** 에 대해 **모든 게스트 및 외부 사용자**를 확인 합니다. **Exclude**</span><span class="sxs-lookup"><span data-stu-id="79451-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![게스트 및 외부 사용자를 제외 하기 위한 컨트롤의 화면 캡처](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="79451-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="79451-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="79451-131">Microsoft 팀과의 게스트 및 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="79451-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="79451-132">Microsoft 팀에서는 다음을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="79451-133">**게스트 액세스** 에서는 팀 구성원으로 추가할 수 있는 AZURE AD B2B 계정을 사용 하며, 모든 고유한에 팀의 통신 및 리소스에 대 한 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="79451-134">**외부 액세스** 는 B2B 계정이 없는 외부 사용자에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79451-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="79451-135">외부 액세스에는 초대 및 참여를 포함할 수 있지만 팀 구성원 자격 및 팀의 리소스에 대 한 액세스는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="79451-136">자세한 내용은 [팀에 대 한 게스트 및 외부 액세스 간 비교](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79451-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="79451-137">조건부 액세스 정책은 해당 Azure AD B2B 계정이 있기 때문에 팀의 게스트 액세스에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79451-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="79451-138">팀에 대 한 id 및 장치 액세스 정책 보호에 대 한 자세한 내용은 [팀 대화방, 그룹 및 파일 보호에 대 한 정책 권장 사항을](teams-access-policies.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79451-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="79451-139">게스트 및 외부 사용자에 대 한 MFA 항상 필요</span><span class="sxs-lookup"><span data-stu-id="79451-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="79451-140">이 정책은 해당 홈 테 넌 트에서 MFA에 대 한 등록 여부에 관계 없이 테 넌 트에 MFA를 등록 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="79451-141">테 넌 트의 리소스에 액세스할 때 게스트 및 외부 사용자는 모든 요청에 대해 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="79451-142">위험 기반 MFA 로부터 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="79451-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="79451-143">조직은 Azure AD Id 보호를 사용 하 여 B2B 사용자에 게 위험 기반 정책을 적용할 수 있지만, 해당 홈 디렉터리에 있는 id로 인해 리소스 디렉터리의 B2B 공동 작업 사용자에 대 한 Azure AD Id 보호 구현에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="79451-144">이러한 제한으로 인해 Microsoft는 위험 기반 MFA 정책에서 게스트 사용자를 제외 하 고이 사용자가 항상 MFA를 사용 하도록 요구 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="79451-145">자세한 내용은 [B2B 공동 작업 사용자에 대 한 Id 보호의 제한 사항을](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79451-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="79451-146">장치 관리에서 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="79451-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="79451-147">한 조직 에서만 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79451-147">Only one organization can manage a device.</span></span> <span data-ttu-id="79451-148">장치 준수를 요구 하는 정책에서 게스트 및 외부 사용자를 제외 하지 않으면 이러한 정책은 이러한 사용자를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="79451-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="79451-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="79451-149">Next step</span></span>

![4 단계: Microsoft 365 클라우드 앱에 대 한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="79451-151">다음에 대 한 조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="79451-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="79451-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79451-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="79451-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="79451-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="79451-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="79451-154">SharePoint</span></span>](sharepoint-file-access-policies.md)


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
ms.openlocfilehash: c61526139111885ec345bc4a4dd3cd6b147370e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950811"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="7b1e1-103">게스트 및 외부 B2B 액세스를 허용 하기 위한 정책</span><span class="sxs-lookup"><span data-stu-id="7b1e1-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="7b1e1-104">이 문서에서는 B2B (business to Business) 계정 액세스 (게스트 및 외부 사용자)를 허용 하도록 권장 되는 일반 id 및 장치 액세스 정책을 조정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="7b1e1-105">이 지침은 [일반 id 및 장치 액세스 정책을](identity-access-policies.md)기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="7b1e1-106">이러한 권장 사항은 보호의 **기본** 계층에 적용 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="7b1e1-107">그러나 **중요** 및 **높은 규제** 보호에 대 한 요구 사항의 세분성을 기반으로 권장 사항을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="7b1e1-108">B2B 사용자가 Azure AD (Active Directory) 테 넌 트를 사용 하 여 인증할 수 있도록 경로를 제공 하면 이러한 사용자에 게 전체 환경에 대 한 액세스 권한이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="7b1e1-109">B2B 사용자는 조건부 액세스 정책에 부여 된 서비스 내에서 파일과 같이 공유 되는 리소스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="7b1e1-110">게스트 및 외부 액세스를 허용 하 고 보호 하기 위해 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="7b1e1-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="7b1e1-111">다음 다이어그램에서는 게스트 및 외부 액세스를 보호 하기 위해 일반 id 및 장치 액세스 정책에서 추가 하거나 업데이트할 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="7b1e1-112">[![게스트 액세스 보호를 위한 정책 업데이트 요약](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="7b1e1-113">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="7b1e1-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="7b1e1-114">다음 표에는 업데이트 하거나 새로 만드는 데 필요한 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="7b1e1-115">공통 정책- [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="7b1e1-116">보호 수준</span><span class="sxs-lookup"><span data-stu-id="7b1e1-116">Protection level</span></span>|<span data-ttu-id="7b1e1-117">정책</span><span class="sxs-lookup"><span data-stu-id="7b1e1-117">Policies</span></span>|<span data-ttu-id="7b1e1-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7b1e1-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="7b1e1-119">**기준**</span><span class="sxs-lookup"><span data-stu-id="7b1e1-119">**Baseline**</span></span>|[<span data-ttu-id="7b1e1-120">게스트 및 외부 사용자에 대 한 MFA 항상 필요</span><span class="sxs-lookup"><span data-stu-id="7b1e1-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7b1e1-121">이 새 정책을 만들고 게스트 및 외부 사용자 에게만 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="7b1e1-122">**로그인 위험**에서 모든 옵션을 선택 하지 않은 상태로 두면 MFA (multi-factor authentication)가 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="7b1e1-123">로그인 위험이 *보통* 또는 *높을* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="7b1e1-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7b1e1-124">이 정책을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="7b1e1-125">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="7b1e1-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="7b1e1-126">이 정책을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="7b1e1-127">조건부 액세스 정책에서 게스트 및 외부 사용자를 포함 하거나 제외 하려면 **포함** 또는 **제외** 탭을 클릭 하 고 **모든 게스트 및 외부 사용자**를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![게스트를 제외 하기 위한 컨트롤의 화면 캡처](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="7b1e1-129">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7b1e1-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="7b1e1-130">게스트 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="7b1e1-130">Guests vs. external users</span></span>
<span data-ttu-id="7b1e1-131">Azure AD에서 게스트 및 외부 사용자는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="7b1e1-132">이러한 두 가지 유형의 사용자는 모두 게스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="7b1e1-133">게스트 사용자는 B2B 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-133">Guest users are B2B users.</span></span>

<span data-ttu-id="7b1e1-134">Microsoft 팀은 게스트 사용자와 앱 내의 외부 사용자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-134">Microsoft Teams differentiates between guest users and external users within the app.</span></span> <span data-ttu-id="7b1e1-135">게스트 사용자는 Azure AD B2B 계정을 가지 며 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-135">Guest users have Azure AD B2B accounts and can be added to teams.</span></span> <span data-ttu-id="7b1e1-136">외부 사용자는 통화, 채팅 및 모임에만 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-136">External users can only participate in calls, chats, and meetings.</span></span> <span data-ttu-id="7b1e1-137">자세한 내용은 [팀에 대 한 게스트 및 외부 사용자 간의 비교](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-137">For more information, see [this comparison between guest and external users for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="7b1e1-138">팀에 대 한 id 및 장치 액세스 보안에 대 한 자세한 내용은 [팀 대화방, 그룹 및 파일 보호에 대 한 정책 권장 사항](teams-access-policies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access for Teams</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="7b1e1-139">게스트 및 외부 사용자에 대 한 MFA 항상 필요</span><span class="sxs-lookup"><span data-stu-id="7b1e1-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="7b1e1-140">이 정책은 해당 홈 테 넌 트에서 MFA에 대 한 등록 여부에 관계 없이 테 넌 트에 MFA를 등록 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="7b1e1-141">테 넌 트의 리소스에 액세스할 때 게스트 및 외부 사용자는 모든 요청에 대해 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-141">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="7b1e1-142">위험 기반 MFA 로부터 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="7b1e1-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="7b1e1-143">조직은 Azure AD Id 보호를 사용 하 여 B2B 사용자에 게 위험 기반 정책을 적용할 수 있지만, 해당 홈 디렉터리에 있는 id로 인해 리소스 디렉터리의 B2B 공동 작업 사용자에 대 한 Azure AD Id 보호 구현에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="7b1e1-144">이러한 제한으로 인해 Microsoft는 위험 기반 MFA 정책에서 게스트 사용자를 제외 하 고이 사용자가 항상 MFA를 사용 하도록 요구 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="7b1e1-145">자세한 내용은 [B2B 공동 작업 사용자에 대 한 Id 보호의 제한 사항을](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="7b1e1-146">장치 관리에서 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="7b1e1-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="7b1e1-147">한 조직 에서만 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-147">Only one organization can manage a device.</span></span> <span data-ttu-id="7b1e1-148">장치 준수를 요구 하는 정책에서 게스트 및 외부 사용자를 제외 하지 않으면 이러한 정책은 이러한 사용자를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="7b1e1-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7b1e1-149">Next step</span></span>

![4 단계: Microsoft 365 클라우드 앱에 대 한 정책](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="7b1e1-151">다음에 대 한 조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="7b1e1-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="7b1e1-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b1e1-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="7b1e1-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b1e1-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="7b1e1-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b1e1-154">SharePoint</span></span>](secure-email-recommended-policies.md)


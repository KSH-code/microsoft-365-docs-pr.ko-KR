---
title: 게스트 및 외부 사용자 B2B 액세스를 허용하기 위한 ID 및 장치 액세스 정책 - 엔터프라이즈용 Microsoft 365 | Microsoft Docs
description: 게스트 및 외부 사용자의 액세스를 보호하기 위한 권장 조건부 액세스 및 관련 정책에 대해 설명
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845098"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="d888e-103">게스트 액세스 및 B2B 외부 사용자 액세스를 허용하는 정책</span><span class="sxs-lookup"><span data-stu-id="d888e-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="d888e-104">이 문서에서는 Azure AD(Azure Active Directory) B2B(비즈니스 대 비즈니스) 계정이 있는 게스트 및 외부 사용자에 대한 액세스를 허용하도록 권장되는 장치 및 ID 액세스 정책을 조정하는 데 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="d888e-105">이 지침은 공통 ID 및 장치 액세스 [정책을 빌드합니다.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d888e-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="d888e-106">이러한 권장 사항은 보호의 기준 **계층에** 적용하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="d888e-107">그러나 중요하고 높은 규제 대상 보호에 대한 특정 요구 사항에 따라 권장 **사항을** **조정할 수도** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="d888e-108">B2B 계정이 Azure AD 테넌트에 인증하는 경로를 제공해도 이러한 계정에 전체 환경에 대한 액세스 권한이 부여되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="d888e-109">B2B 사용자 및 해당 계정은 조건부 액세스 정책에 의해 공유되는 파일과 같은 서비스 및 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="d888e-110">게스트 및 외부 사용자 액세스를 허용하고 보호하기 위한 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="d888e-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="d888e-111">이 다이어그램은 B2B 게스트 및 외부 사용자 액세스에 대해 공통 ID 및 장치 액세스 정책 사이에서 추가하거나 업데이트할 정책을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="d888e-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="d888e-112">[![게스트 액세스 보호를 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="d888e-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="d888e-113">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="d888e-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="d888e-114">다음 표에는 만들고 업데이트해야 하는 정책이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="d888e-115">일반 정책은 일반 ID 및 장치 액세스 정책 문서의 관련 구성 [지침에 연결됩니다.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d888e-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="d888e-116">보호 수준</span><span class="sxs-lookup"><span data-stu-id="d888e-116">Protection level</span></span>|<span data-ttu-id="d888e-117">정책</span><span class="sxs-lookup"><span data-stu-id="d888e-117">Policies</span></span>|<span data-ttu-id="d888e-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d888e-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="d888e-119">**기준**</span><span class="sxs-lookup"><span data-stu-id="d888e-119">**Baseline**</span></span>|[<span data-ttu-id="d888e-120">게스트 및 외부 사용자에 대해 MFA가 항상 필요</span><span class="sxs-lookup"><span data-stu-id="d888e-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="d888e-121">이 새 정책을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="d888e-122">Assignments **> Users and groups > Include,** choose users and **groups,** and then select **All guest and external users.**</span><span class="sxs-lookup"><span data-stu-id="d888e-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="d888e-123">배정 **> 조건>** 로그인의 경우 항상 MFA(다단계 인증)를 적용하도록 모든 옵션을 선택되지 않은 상태로 떠야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="d888e-124">로그인 위험이 중간 또는 높음인 경우 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="d888e-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="d888e-125">게스트 및 외부 사용자를 제외하도록 이 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="d888e-126">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="d888e-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="d888e-127">게스트 및 외부 사용자를 제외하도록 이 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="d888e-128">조건부 액세스 정책에서 게스트 및 외부 사용자를 포함하거나 제외하기 위해 **Assignments** > 사용자 및 그룹에 대해 포함 또는 제외> 모든 게스트 및 외부 사용자를 **검사합니다.**</span><span class="sxs-lookup"><span data-stu-id="d888e-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![게스트 및 외부 사용자를 제외하는 컨트롤의 화면 캡처](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="d888e-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d888e-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="d888e-131">Microsoft Teams를 통해 게스트 및 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="d888e-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="d888e-132">Microsoft Teams는 다음 사용자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="d888e-133">**게스트 액세스는** 팀의 구성원으로 추가할 수 있으며 팀의 커뮤니케이션 및 리소스에 액세스할 수 있는 Azure AD B2B 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="d888e-134">**외부 액세스는** B2B 계정이 없는 외부 사용자에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="d888e-135">외부 사용자 액세스에는 초대, 통화, 채팅 및 모임이 포함되어 있지만 팀 구성원 자격 및 팀 리소스에 대한 액세스는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="d888e-136">자세한 내용은 게스트와 팀의 외부 사용자 [액세스 간 비교를 참조하세요.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="d888e-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="d888e-137">Teams의 ID 및 장치 액세스 정책 보안에 대한 자세한 내용은 Teams 채팅, 그룹 및 파일을 보호하기 위한 정책 권장 사항을 [참조하세요.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d888e-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="d888e-138">게스트 및 외부 사용자에 대해 MFA가 항상 필요</span><span class="sxs-lookup"><span data-stu-id="d888e-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="d888e-139">이 정책은 게스트가 홈 테넌트에 MFA에 등록되어 있는지 여부에 관계없이 테넌트에 MFA를 등록하라는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="d888e-140">테넌트의 리소스에 액세스할 때 게스트 및 외부 사용자는 모든 요청에 대해 MFA를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="d888e-141">위험 기반 MFA에서 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="d888e-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="d888e-142">조직은 Azure AD ID 보호를 사용하여 B2B 사용자에 대해 위험 기반 정책을 적용할 수 있는 반면, 홈 디렉터리에 기존 ID로 인해 리소스 디렉터리의 B2B 공동 작업 사용자에 대한 Azure AD ID 보호를 구현하는 데 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="d888e-143">이러한 제한으로 인해 위험 기반 MFA 정책에서 게스트를 제외하고 이러한 사용자에게 항상 MFA를 사용하게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="d888e-144">자세한 내용은 B2B 공동 작업 사용자에 대한 [ID 보호의 제한 사항을 참조하세요.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="d888e-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="d888e-145">장치 관리에서 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="d888e-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="d888e-146">한 조직만 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-146">Only one organization can manage a device.</span></span> <span data-ttu-id="d888e-147">게스트 및 외부 사용자를 장치 준수가 필요한 정책에서 제외하지 않는 경우 이러한 정책은 이러한 사용자를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="d888e-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="d888e-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d888e-148">Next step</span></span>

![4단계: Microsoft 365 클라우드 앱에 대한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="d888e-150">조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="d888e-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="d888e-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d888e-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="d888e-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d888e-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="d888e-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d888e-153">SharePoint</span></span>](sharepoint-file-access-policies.md)

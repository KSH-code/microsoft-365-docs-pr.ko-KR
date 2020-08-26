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
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898107"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="7c083-103">게스트 및 외부 B2B 액세스를 허용 하기 위한 정책</span><span class="sxs-lookup"><span data-stu-id="7c083-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="7c083-104">이 문서에서는 B2B 계정 액세스 (게스트 및 외부 사용자)를 허용 하도록 권장 되는 일반 id 및 장치 액세스 정책을 조정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="7c083-105">이 지침은 [일반 id 및 장치 액세스 정책을](identity-access-policies.md)기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="7c083-106">이러한 권장 사항은 보호의 **기본** 계층에 적용 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="7c083-107">그러나 **중요** 및 **높은 규제** 된 보호에 대 한 요구 사항의 세분성을 기반으로 권장 사항을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="7c083-108">B2B 사용자가 Azure AD 테 넌 트를 사용 하 여 인증할 수 있도록 경로를 제공 하면 이러한 사용자에 게 전체 환경에 대 한 액세스 권한이 부여 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="7c083-109">B2B 사용자는 조건부 액세스 정책에 부여 된 서비스 내에서 파일과 같이 공유 되는 리소스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="7c083-110">게스트 및 외부 액세스를 허용 하 고 보호 하기 위해 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="7c083-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="7c083-111">다음 다이어그램에서는 일반 id 및 장치 액세스 정책을 보여주고, 게스트 및 외부 액세스를 보호 하기 위해 추가 하거나 업데이트할 정책을 설명 합니다 (연필 아이콘 포함).</span><span class="sxs-lookup"><span data-stu-id="7c083-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![게스트 액세스 보호를 위한 정책 업데이트 요약](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="7c083-113">다음 표에는 업데이트 하거나 새로 만드는 데 필요한 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="7c083-114">공통 정책- [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="7c083-115">보호 수준</span><span class="sxs-lookup"><span data-stu-id="7c083-115">Protection level</span></span>|<span data-ttu-id="7c083-116">정책</span><span class="sxs-lookup"><span data-stu-id="7c083-116">Policies</span></span>|<span data-ttu-id="7c083-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7c083-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="7c083-118">**기준**</span><span class="sxs-lookup"><span data-stu-id="7c083-118">**Baseline**</span></span>|[<span data-ttu-id="7c083-119">게스트 및 외부 사용자에 대 한 MFA 항상 필요</span><span class="sxs-lookup"><span data-stu-id="7c083-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c083-120">이 새 규칙을 만들어 게스트 및 외부 사용자 에게만 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="7c083-121">로그인 위험에서 항상 MFA를 적용 하도록 모든 옵션을 선택 하지 않은 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="7c083-122">로그인 위험이 *보통* 또는 *높을* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="7c083-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c083-123">이 규칙을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="7c083-124">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="7c083-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="7c083-125">이 규칙을 수정 하 여 게스트 및 외부 사용자를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="7c083-126">조건부 액세스 규칙에 게스트 및 외부 사용자를 포함 하거나 제외 하려면 포함 또는 제외 탭을 클릭 하 고 **모든 게스트 및 외부 사용자**를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![게스트를 제외 하기 위한 컨트롤의 화면 캡처](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="7c083-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7c083-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="7c083-129">게스트 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="7c083-129">Guests vs. external users</span></span>
<span data-ttu-id="7c083-130">Azure AD에서 게스트 및 외부 사용자는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="7c083-131">이러한 두 가지 유형의 사용자는 모두 게스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="7c083-132">게스트 사용자는 B2B 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-132">Guest users are B2B users.</span></span>

<span data-ttu-id="7c083-133">Microsoft 팀은 게스트 사용자와 앱 내의 외부 사용자를 구분 하지만 인증 시 이러한 사용자는 둘 다 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="7c083-134">팀 게스트 및 외부 사용자에 대 한 자세한 내용은 [팀에 대 한 게스트 및 외부 액세스 활성화](teams-access-policies.md#enabling-guest-and-external-access-for-teams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="7c083-135">게스트 및 외부 사용자에 대 한 MFA 항상 필요</span><span class="sxs-lookup"><span data-stu-id="7c083-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="7c083-136">이 규칙은 홈 테 넌 트에서 MFA에 대 한 등록 여부에 관계 없이 테 넌 트에 MFA를 등록 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="7c083-137">테 넌 트의 리소스에 액세스할 때 게스트 및 외부 사용자는 모든 요청에 대해 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="7c083-138">위험 기반 MFA 로부터 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="7c083-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="7c083-139">조직은 Id 보호를 사용 하 여 B2B 사용자에 게 위험 기반 정책을 적용할 수 있지만, 해당 홈 디렉터리에 있는 id로 인해 리소스 디렉터리의 B2B 공동 작업 사용자에 대 한 Id 보호 구현에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="7c083-140">이러한 제한으로 인해 Microsoft는 위험 기반 MFA 정책에서 게스트 사용자를 제외 하 고이 사용자가 항상 MFA를 사용 하도록 요구 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="7c083-141">자세한 내용은 [B2B 공동 작업 사용자에 대 한 Id 보호의 제한 사항을](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c083-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="7c083-142">장치 관리에서 게스트 및 외부 사용자 제외</span><span class="sxs-lookup"><span data-stu-id="7c083-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="7c083-143">한 조직 에서만 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-143">Only one organization can manage a device.</span></span> <span data-ttu-id="7c083-144">장치 준수를 요구 하는 정책에서 게스트 및 외부 사용자를 제외 하지 않으면 이러한 정책은 이러한 사용자를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c083-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7c083-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7c083-145">Next steps</span></span>

[<span data-ttu-id="7c083-146">팀 조건부 액세스를 사용 하도록 설정 하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="7c083-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)


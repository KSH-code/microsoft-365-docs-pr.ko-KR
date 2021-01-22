---
title: Microsoft 365에 대한 다단계 인증 사용
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365의 다단계 인증에 대한 자세한 정보
ms.openlocfilehash: 7d62d88acb5137bd0674de7a42b44103bc9fc5f0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926549"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="67d28-103">Microsoft 365에 대한 다단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="67d28-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="67d28-104">암호는 컴퓨터 또는 온라인 서비스에 로그인을 인증하는 가장 일반적인 방법입지만 가장 취약하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="67d28-105">사용자는 단순한 암호를 선택 하기도 하고 다른 컴퓨터 및 서비스에서 동일한 암호를 사용하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="67d28-106">로그인에 추가 보안 수준을 제공 하려면 다단계 인증(MFA)을 사용해서 암호와 다음을 기반으로 하는 보다 안전한 추가 인증 방법을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="67d28-107">사용자가 보유한 것 중 스마트폰과 같이 쉽게 복제할 수 없는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="67d28-108">사용자의 지문, 얼굴 또는 기타 생체 인식 특성과 같이 고유하고 생물학적으로 가지고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="67d28-109">추가 확인 방법은 사용자의 암호가 확인될 때까지 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="67d28-110">사용자의 강력한 암호가 노출 되었다 하더라도 MFA를 사용하면 공격자는 사용자의 스마트폰이나 지문을 가지고 있지 않기 때문에 로그인을 완성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="67d28-111">Microsoft 365에서 MFA 지원</span><span class="sxs-lookup"><span data-stu-id="67d28-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="67d28-112">기본적으로 다음을 사용하여 Microsoft 365 및 Office 365가 사용자 계정의 MFA를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="67d28-113">사용자가 확인 코드를 입력 하도록 휴대폰으로 전송 된 문자 메시지</span><span class="sxs-lookup"><span data-stu-id="67d28-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="67d28-114">전화 통화</span><span class="sxs-lookup"><span data-stu-id="67d28-114">A phone call.</span></span>
- <span data-ttu-id="67d28-115">Microsoft Authenticator 스마트폰 앱</span><span class="sxs-lookup"><span data-stu-id="67d28-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="67d28-116">두 경우 모두 MFA 로그인은 추가 확인을 위해 "쉽게 중복되지 않는 항목" 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="67d28-117">Microsoft 365 및 Office 365에서 MFA를 사용 설정 하기 위한 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="67d28-118">보안 기본값으로</span><span class="sxs-lookup"><span data-stu-id="67d28-118">With security defaults</span></span>
- <span data-ttu-id="67d28-119">조건부 액세스 정책으로</span><span class="sxs-lookup"><span data-stu-id="67d28-119">With Conditional Access policies</span></span>
- <span data-ttu-id="67d28-120">각 개별 사용자 계정에 대해 (권장 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="67d28-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="67d28-121">이러한 방법은 Microsoft 365 요금제에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="67d28-122">계획</span><span class="sxs-lookup"><span data-stu-id="67d28-122">Plan</span></span>|<span data-ttu-id="67d28-123">권장 사항</span><span class="sxs-lookup"><span data-stu-id="67d28-123">Recommendation</span></span>|<span data-ttu-id="67d28-124">고객 유형</span><span class="sxs-lookup"><span data-stu-id="67d28-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="67d28-125">모든 Microsoft 365 요금제</span><span class="sxs-lookup"><span data-stu-id="67d28-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="67d28-126">모든 사용자 계정에 대해 MFA를 필수로 요청하는 보안 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="67d28-127">개별 사용자 계정에 대해 사용자별 MFA를 구성할 수도 있지만 권장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="67d28-128">소규모 기업</span><span class="sxs-lookup"><span data-stu-id="67d28-128">Small business</span></span>|
|<span data-ttu-id="67d28-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="67d28-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="67d28-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="67d28-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="67d28-131">Azure AD(Azure Active Directory) Premium P1 라이선스</span><span class="sxs-lookup"><span data-stu-id="67d28-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="67d28-132">조건부 액세스 정책을 사용하여 그룹 멤버 자격, 앱 또는 기타 기준에 따라 사용자 계정에 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="67d28-133">소규모 기업에서 기업까지</span><span class="sxs-lookup"><span data-stu-id="67d28-133">Small business to enterprise</span></span>|
|<span data-ttu-id="67d28-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="67d28-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="67d28-135">Azure AD Premium P2 라이선스</span><span class="sxs-lookup"><span data-stu-id="67d28-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="67d28-136">Azure AD ID 보호를 사용하여 로그인 위험 기준에 따라 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="67d28-137">엔터프라이즈</span><span class="sxs-lookup"><span data-stu-id="67d28-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="67d28-138">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="67d28-138">Security defaults</span></span>

<span data-ttu-id="67d28-139">보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="67d28-140">이러한 구독에는 보안 기본값이 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="67d28-141">Microsoft Authenticator 앱의 모든 사용자가 MFA를 사용 하도록 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="67d28-142">레거시 인증을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="67d28-143">사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="67d28-144">14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="67d28-145">보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="67d28-146">조건부 액세스 정책으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="67d28-147">Azure 포털의 Azure AD에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![디렉터리 속성 페이지의 그림입니다.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="67d28-149">모든 Microsoft 365 요금제에 보안 기본값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="67d28-150">자세한 정보는 이 [보안 기본값 개요](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67d28-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="67d28-151">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="67d28-151">Conditional Access policies</span></span>

<span data-ttu-id="67d28-152">조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="67d28-153">예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="67d28-154">사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="67d28-155">이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="67d28-156">특정 앱에 MFA를 요구하거나 Windows 10을 실행하는 노트북과 같은 준수 장치에서 로그인을 수행하는 등의 고급 기능을 위해 조건부 액세스 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="67d28-157">Azure 포털의 Azure AD의 **보안** 창에서 조건부 액세스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![조건부 액세스의 메뉴 옵션 그림](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="67d28-159">조건부 액세스 정책을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="67d28-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="67d28-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="67d28-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="67d28-161">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="67d28-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="67d28-162">Azure AD Premium P1 및 Azure AD Premium P2 라이선스</span><span class="sxs-lookup"><span data-stu-id="67d28-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="67d28-163">Microsoft 365 Business Premium이 있는 소규모 기업의 경우 다음 단계를 통해 조건부 액세스 정책을 손쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="67d28-164">MFA를 필요로 하는 사용자 계정을 포함할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="67d28-165">**전역 관리자에 MFA 요구** 정책을 사용 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="67d28-166">다음 설정을 사용하여 그룹 기반 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="67d28-167">할당 > 사용자 및 그룹: 위의 단계 1에서 지정한 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="67d28-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="67d28-168">할당 > 클라우드 앱 혹은 활동: 모든 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="67d28-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="67d28-169">액세스 제어 > 부여 > 액세스 부여 > 단계 인증 요구</span><span class="sxs-lookup"><span data-stu-id="67d28-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="67d28-170">정책 사용 설정</span><span class="sxs-lookup"><span data-stu-id="67d28-170">Enable the policy.</span></span>
5. <span data-ttu-id="67d28-171">위의 1 단계에서 만든 그룹에 사용자 계정을 추가하고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="67d28-172">추가 사용자 계정에 MFA를 요구 하려면 1 단계에서 만든 그룹에 해당 사용자 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="67d28-173">이 조건부 액세스 정책을 사용하면 사용자가 원하는 진도에 맞춰 MFA 요구 사항을 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="67d28-174">Enterprises는 [공통 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="67d28-175">관리자에게 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="67d28-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="67d28-176">모든 사용자에게 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="67d28-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="67d28-177">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="67d28-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="67d28-178">자세한 내용은 이 [조건부 액세스 개요](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67d28-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="67d28-179">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="67d28-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="67d28-180">Azure AD ID 보호 기능을 사용하여 [로그인 위험이 중간에서 높음일 때 MFA를 요구](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)하는 추가 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="67d28-181">다음에서는 Azure AD ID 보호 및 위험 기반 조건부 액세스 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="67d28-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="67d28-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="67d28-183">Azure AD Premium P2 라이선스</span><span class="sxs-lookup"><span data-stu-id="67d28-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="67d28-184">자세한 내용은 이 [Azure AD ID 보호 개요](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67d28-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="67d28-185">레거시 사용자당 MFA(권장하지 않음)</span><span class="sxs-lookup"><span data-stu-id="67d28-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="67d28-186">사용자 계정 로그인에 MFA를 요구하기 위해 보안 기본값이나 조건부 액세스 정책을 사용해야 합니다. 하지만 둘 다 사용할 수 없는 경우라면 Microsoft는 관리자 권한이 있는 사용자(특히, 모든 구독에 대한 권역 관리자 역할을 가진 사용자)에 MFA를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="67d28-187">Microsoft 365 관리 센터의 **활성 사용자** 창에서 개별 사용자 계정에 대해 MFA를 사용 하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![활성 사용자 페이지의 다단계 인증 옵션 그림](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="67d28-189">사용 설정 되면, 사용자가 다음에 로그인 할 때에 MFA를 등록하고 추가 확인 방법을 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="67d28-190">이 방법들을 함께 사용</span><span class="sxs-lookup"><span data-stu-id="67d28-190">Using these methods together</span></span>

<span data-ttu-id="67d28-191">이 표는 보안 기본값, 조건부 액세스 정책 및 사용자별 계정 설정으로 MFA를 활성화한 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="67d28-192">사용</span><span class="sxs-lookup"><span data-stu-id="67d28-192">Enabled</span></span>|<span data-ttu-id="67d28-193">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="67d28-193">Disabled</span></span>|<span data-ttu-id="67d28-194">보조 인증 방법</span><span class="sxs-lookup"><span data-stu-id="67d28-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="67d28-195">**보안 기본값**</span><span class="sxs-lookup"><span data-stu-id="67d28-195">**Security defaults**</span></span>|<span data-ttu-id="67d28-196">조건부 액세스 정책을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="67d28-197">조건부 액세스 정책을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="67d28-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="67d28-198">Microsoft Authenticator 앱</span><span class="sxs-lookup"><span data-stu-id="67d28-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="67d28-199">**조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="67d28-199">**Conditional Access policies**</span></span>|<span data-ttu-id="67d28-200">사용하도록 설정된 경우 보안 기본값을 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="67d28-201">상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한 </span><span class="sxs-lookup"><span data-stu-id="67d28-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="67d28-202">MFA 등록 중 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="67d28-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="67d28-203">**레거시 사용자당 MFA(권장하지 않음)**</span><span class="sxs-lookup"><span data-stu-id="67d28-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="67d28-204">각 로그인에서 MFA를 요구 하는 보안 기본값과 조건부 액세스 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="67d28-205">보안 기본값과 조건부 액세스 정책에 의해 재정의</span><span class="sxs-lookup"><span data-stu-id="67d28-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="67d28-206">MFA 등록 중 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="67d28-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="67d28-207">보안 기본값을 사용하면 다음 로그인 시 모든 새 사용자에게 MFA 등록 및 Microsoft Authenticator 앱 사용을 요구하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="67d28-208">MFA 설정 관리 방법</span><span class="sxs-lookup"><span data-stu-id="67d28-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="67d28-209">MAF 설정을 관리하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="67d28-210">Azure 포털에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="67d28-211">보안 기본값을 사용 설정 혹은 사용 해제</span><span class="sxs-lookup"><span data-stu-id="67d28-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="67d28-212">조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="67d28-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="67d28-213">Microsoft 365 관리 센터에서 사용자별 및 서비스 MFA 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d28-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="67d28-214">다음 단계</span><span class="sxs-lookup"><span data-stu-id="67d28-214">Your next step</span></span>

[<span data-ttu-id="67d28-215">Microsoft 365 MFA 설정</span><span class="sxs-lookup"><span data-stu-id="67d28-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

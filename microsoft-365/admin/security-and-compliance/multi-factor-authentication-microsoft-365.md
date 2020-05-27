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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365의 다단계 인증에 대해 알아봅니다.
ms.openlocfilehash: eba9ae38dbc17a22abb5d5ef92b8cd30a827ae11
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371455"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="4e01d-103">Microsoft 365에 대한 다단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="4e01d-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="4e01d-104">암호는 컴퓨터 또는 온라인 서비스에 대 한 로그인을 인증 하는 가장 일반적인 방법 이지만 가장 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="4e01d-105">사용자는 여러 컴퓨터와 서비스에 대 한 로그인을 간편 하 게 선택 하 고 동일한 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="4e01d-106">로그인에 대 한 추가 보안 수준을 제공 하려면 암호를 사용 하는 MFA (다단계 인증)와 다음을 기반으로 하는 추가 확인 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="4e01d-107">스마트 전화와 같이 쉽게 복제할 수 없는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="4e01d-108">지문, 얼굴 또는 기타 생체 인식 특성과 같이 고유 하 고 biologically 있는 항목</span><span class="sxs-lookup"><span data-stu-id="4e01d-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="4e01d-109">사용자의 암호를 확인 한 후에는 추가 확인 방법이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="4e01d-110">MFA를 사용 하 여 강력한 사용자 암호가 손상 된 경우에도 공격자는 로그인을 완료 하기 위해 스마트 전화나 지문을 갖고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="4e01d-111">Microsoft 365의 MFA 지원</span><span class="sxs-lookup"><span data-stu-id="4e01d-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="4e01d-112">기본적으로 Microsoft 365 및 Office 365에서는 다음을 사용 하 여 사용자 계정에 대 한 MFA를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="4e01d-113">사용자가 확인 코드를 입력 해야 하는 휴대폰으로 전송 되는 텍스트 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="4e01d-114">전화 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-114">A phone call.</span></span>
- <span data-ttu-id="4e01d-115">Microsoft Authenticator 스마트 폰 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="4e01d-116">두 경우 모두 MFA 로그인에서는 추가 확인을 위해 "쉽게 복제할 수 없는 항목" 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="4e01d-117">Microsoft 365 및 Office 365에서 MFA를 사용 하도록 설정 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="4e01d-118">보안 기본값 사용</span><span class="sxs-lookup"><span data-stu-id="4e01d-118">With security defaults</span></span>
- <span data-ttu-id="4e01d-119">조건부 액세스 정책을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4e01d-119">With Conditional Access policies</span></span>
- <span data-ttu-id="4e01d-120">개별 사용자 계정에 대해 (권장 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="4e01d-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="4e01d-121">이러한 방법은 Microsoft 365 계획을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="4e01d-122">계획</span><span class="sxs-lookup"><span data-stu-id="4e01d-122">Plan</span></span>  |<span data-ttu-id="4e01d-123">권장 사항</span><span class="sxs-lookup"><span data-stu-id="4e01d-123">Recommendation</span></span>  | <span data-ttu-id="4e01d-124">고객 유형</span><span class="sxs-lookup"><span data-stu-id="4e01d-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="4e01d-125">모든 Microsoft 365 계획</span><span class="sxs-lookup"><span data-stu-id="4e01d-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="4e01d-126">모든 사용자 계정에 대해 MFA가 필요한 보안 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="4e01d-127">사용자별 계정 단위로 MFA를 요구할 수도 있지만이는 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="4e01d-128">소규모 기업</span><span class="sxs-lookup"><span data-stu-id="4e01d-128">Small business</span></span> |
| <span data-ttu-id="4e01d-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4e01d-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="4e01d-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="4e01d-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="4e01d-131">Azure Active Directory (Azure AD) Premium P1 라이선스</span><span class="sxs-lookup"><span data-stu-id="4e01d-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="4e01d-132">조건부 액세스 정책을 사용 하 여 그룹 구성원, 앱 또는 기타 기준에 따라 사용자 계정에 대 한 MFA를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="4e01d-133">중소 기업-기업</span><span class="sxs-lookup"><span data-stu-id="4e01d-133">Small business to enterprise</span></span> |
| <span data-ttu-id="4e01d-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4e01d-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="4e01d-135">Azure AD Premium P2 라이선스</span><span class="sxs-lookup"><span data-stu-id="4e01d-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="4e01d-136">Azure AD Id 보호를 사용 하 여 로그인 위험 조건에 따라 MFA를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="4e01d-137">엔터프라이즈</span><span class="sxs-lookup"><span data-stu-id="4e01d-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="4e01d-138">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="4e01d-138">Security defaults</span></span>

<span data-ttu-id="4e01d-139">보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="4e01d-140">이러한 구독은 다음과 같은 보안 기본값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="4e01d-141">모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="4e01d-142">레거시 인증을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="4e01d-143">사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="4e01d-144">14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="4e01d-145">보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="4e01d-146">보안 기본값을 사용 하지 않도록 설정 하려면 MFA가 조건부 액세스 정책에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="4e01d-147">Azure portal의 Azure AD에 대 한 **속성** 창에서 보안 기본값을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="4e01d-148">보안 기본값을 Microsoft 365 계획에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="4e01d-149">자세한 정보는 이 [보안 기본값 개요](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e01d-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="4e01d-150">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="4e01d-150">Conditional Access policies</span></span>

<span data-ttu-id="4e01d-151">조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="4e01d-152">예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="4e01d-153">사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="4e01d-154">이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="4e01d-155">또한 특정 앱에 대해 MFA를 요구 하거나 Windows 10을 실행 하는 랩톱과 같은 준수 장치에서 로그인을 수행 하는 등 고급 기능에 조건부 액세스 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="4e01d-156">Azure portal에서 Azure AD에 대 한 **보안** 창에서 조건부 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="4e01d-157">다음과 같은 조건부 액세스 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="4e01d-158">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4e01d-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="4e01d-159">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="4e01d-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="4e01d-160">Azure AD Premium P1 및 Azure AD Premium P2 라이선스</span><span class="sxs-lookup"><span data-stu-id="4e01d-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="4e01d-161">Microsoft 365 Business Premium을 사용 하는 소규모 기업에서는 다음과 같은 단계를 통해 조건부 액세스 정책을 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="4e01d-162">MFA를 필요로 하는 사용자 계정을 포함할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="4e01d-163">**전역 관리자 정책에 대해 MFA 필요** 를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="4e01d-164">다음 설정을 사용 하 여 그룹 기반 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="4e01d-165">사용자 및 그룹 > 할당: 위의 1 단계에서 그룹 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="4e01d-166">클라우드 앱 또는 작업을 > 할당: 모든 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="4e01d-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="4e01d-167">액세스 제어 > 권한을 부여 > 액세스를 허용 하는 경우에는 multi-factor authentication이 필요 >.</span><span class="sxs-lookup"><span data-stu-id="4e01d-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="4e01d-168">정책을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-168">Enable the policy.</span></span>
5. <span data-ttu-id="4e01d-169">위의 1 단계에서 만든 그룹에 사용자 계정을 추가 하 고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="4e01d-170">추가 사용자 계정에 대해 MFA를 요구 하려면 1 단계에서 만든 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="4e01d-171">이 조건부 액세스 정책을 사용 하면 사용자에 게 원하는 속도로 MFA 요구 사항을 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="4e01d-172">기업에서는 [일반적인 조건부 액세스 정책을](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) 사용 하 여 다음 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="4e01d-173">관리자에게 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="4e01d-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="4e01d-174">모든 사용자에 대해 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="4e01d-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="4e01d-175">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="4e01d-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="4e01d-176">자세한 내용은 이 [조건부 액세스 개요](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e01d-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="4e01d-177">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="4e01d-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="4e01d-178">Azure AD Id 보호를 사용 하면 [로그인 위험이 중간 또는 높은 경우 MFA를 요구](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)하는 추가 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="4e01d-179">다음의 경우 Azure AD Id 보호 및 위험 기반 조건부 액세스 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="4e01d-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4e01d-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="4e01d-181">Azure AD Premium P2 라이선스</span><span class="sxs-lookup"><span data-stu-id="4e01d-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="4e01d-182">자세한 내용은 이 [Azure AD ID 보호 개요](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e01d-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="4e01d-183">개별 사용자 계정에 대 한 MFA (권장 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="4e01d-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="4e01d-184">보안 기본값 또는 조건부 액세스 정책을 사용 하 여 사용자 계정 로그인에 대해 MFA를 요구 해야 합니다. 그러나 이러한 방법 중 하나를 사용할 수 없는 경우에는 모든 크기 구독에 대해 관리자 역할, 특히 전역 관리자 역할을 가진 사용자 계정에 대해 MFA를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="4e01d-185">Microsoft 365 관리 센터의 **활성 사용자** 창에서 개별 사용자 계정에 대해 MFA를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="4e01d-186">다음 번에 사용자가 로그인 하면 다음에는 MFA를 등록 하 고 추가 확인 방법을 선택 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="4e01d-187">이 방법들을 함께 사용</span><span class="sxs-lookup"><span data-stu-id="4e01d-187">Using these methods together</span></span>

<span data-ttu-id="4e01d-188">이 표는 보안 기본값, 조건부 액세스 정책 및 사용자별 계정 설정으로 MFA를 활성화한 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="4e01d-189">사용</span><span class="sxs-lookup"><span data-stu-id="4e01d-189">Enabled</span></span> | <span data-ttu-id="4e01d-190">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4e01d-190">Disabled</span></span> | <span data-ttu-id="4e01d-191">보조 인증 방법</span><span class="sxs-lookup"><span data-stu-id="4e01d-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="4e01d-192">**보안 기본값**</span><span class="sxs-lookup"><span data-stu-id="4e01d-192">**Security defaults**</span></span> | <span data-ttu-id="4e01d-193">조건부 액세스 정책을 사용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="4e01d-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="4e01d-194">조건부 액세스 정책을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="4e01d-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="4e01d-195">Microsoft Authenticator 앱</span><span class="sxs-lookup"><span data-stu-id="4e01d-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="4e01d-196">**조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="4e01d-196">**Conditional Access policies**</span></span> |<span data-ttu-id="4e01d-197">이 중 하나가 사용되는 경우 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="4e01d-198">상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한 </span><span class="sxs-lookup"><span data-stu-id="4e01d-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="4e01d-199">MFA 등록 중 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4e01d-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="4e01d-200">**사용자별 계정 설정 (권장 하지 않음)**</span><span class="sxs-lookup"><span data-stu-id="4e01d-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="4e01d-201">각 로그인에서 MFA를 요구 하는 보안 기본값과 조건부 액세스 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-201">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="4e01d-202">보안 기본값 및 조건부 액세스 정책에 의해 재정의 됨</span><span class="sxs-lookup"><span data-stu-id="4e01d-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="4e01d-203">MFA 등록 중 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4e01d-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="4e01d-204">보안 기본값을 사용 하도록 설정 하면 모든 새 사용자에 게 MFA 등록 및 다음 로그인 시 Microsoft Authenticator 앱 사용에 대 한 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="4e01d-205">MFA 설정을 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4e01d-205">Ways to manage MFA settings</span></span>

<span data-ttu-id="4e01d-206">다음 두 가지 방법으로 MFA 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-206">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="4e01d-207">Azure portal에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-207">In the Azure portal, you can:</span></span>

- <span data-ttu-id="4e01d-208">보안 기본값 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4e01d-208">Enable and disable security defaults</span></span>
- <span data-ttu-id="4e01d-209">조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="4e01d-209">Configure Conditional Access policies</span></span>

<span data-ttu-id="4e01d-210">Microsoft 365 관리 센터에서는 사용자별 및 서비스 MFA 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e01d-210">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="4e01d-211">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4e01d-211">Your next step</span></span>

[<span data-ttu-id="4e01d-212">Microsoft 365에 대 한 MFA 설정</span><span class="sxs-lookup"><span data-stu-id="4e01d-212">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)


---
title: 1단계. MFA를 사용하여 원격 작업자에 대 한 로그인 보안 강화
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 원격 작업자는 MFA(다단계 인증)를 사용하여 로그인해야 합니다.
ms.openlocfilehash: c1436e394174bd3f480186f547f176cea1833cb1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050985"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="f4ecf-104">1단계.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-104">Step 1.</span></span> <span data-ttu-id="f4ecf-105">MFA를 사용하여 원격 작업자에 대 한 로그인 보안 강화</span><span class="sxs-lookup"><span data-stu-id="f4ecf-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="f4ecf-106">원격 작업자의 로그인에 대한 보안을 강화하려면 MFA(다단계 인증)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="f4ecf-107">MFA에서는 사용자 로그인이 사용자 계정 비밀번호 외에 추가 확인을 받아야합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="f4ecf-108">악의적인 사용자가 사용자 계정 암호를 확인하더라도 액세스 권한이 부여되기 전에 스마트폰으로 전송되는 문자 메시지와 같은 추가 확인에 응답 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![올바른 암호와 추가적인 확인을 수행하면 로그인에 성공합니다.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="f4ecf-110">원격 작업자, 특히 관리자를 포함한 모든 사용자에게 MFA를 강력히 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-110">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="f4ecf-111">사용자가 Microsoft 365 계획에 따라 MFA를 사용하도록하는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-111">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="f4ecf-112">계획</span><span class="sxs-lookup"><span data-stu-id="f4ecf-112">Plan</span></span>  |<span data-ttu-id="f4ecf-113">권장 사항</span><span class="sxs-lookup"><span data-stu-id="f4ecf-113">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="f4ecf-114">모든 Microsoft 365 요금제(Azure AD Premium P1 또는 P2 라이선스 제외)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-114">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="f4ecf-115">[Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-115">[Enable Security defaults in Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="f4ecf-116">Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-116">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="f4ecf-117">Microsoft 365 E3(Azure AD Premium P1 라이선스 포함)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-117">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="f4ecf-118">[공통 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-118">Use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="f4ecf-119">- [관리자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-119">- [Require MFA for administrators](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="f4ecf-120">- [모든 사용자에 대해 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-120">- [Require MFA for all users](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="f4ecf-121">- [레거시 인증 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-121">- [Block legacy authentication](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="f4ecf-122">Microsoft 365 E5(Azure AD Premium P2 라이선스 포함)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-122">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="f4ecf-123">Azure AD ID 보호를 활용하여 다음 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](../security/defender-365-security/identity-access-policies.md)을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-123">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of Conditional Access and related policies](../security/defender-365-security/identity-access-policies.md) by creating these policies:</span></span><br> <span data-ttu-id="f4ecf-124">- [로그인 위험이 중간 이상인 경우 MFA 필요](../security/defender-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-124">- [Require MFA when sign-in risk is medium or high](../security/defender-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="f4ecf-125">- [최신 인증을 지원하지 않는 클라이언트 차단](../security/defender-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-125">- [Block clients that don't support modern authentication](../security/defender-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)</span></span><br><span data-ttu-id="f4ecf-126">- [위험이 높은 사용자는 암호를 변경해야 함](../security/defender-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-126">- [High risk users must change password](../security/defender-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="f4ecf-127">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="f4ecf-127">Security defaults</span></span>

<span data-ttu-id="f4ecf-128">보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-128">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="f4ecf-129">이 구독에는 보안 기본값이 설정되어 있으며 ***모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용해야 합니다***.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-129">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="f4ecf-130">사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-130">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="f4ecf-131">14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-131">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="f4ecf-132">보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-132">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="f4ecf-133">조건부 액세스 정책 또는 개별 계정으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-133">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="f4ecf-134">자세한 정보는 이 [보안 기본값 개요](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-134">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="f4ecf-135">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="f4ecf-135">Conditional Access policies</span></span>

<span data-ttu-id="f4ecf-136">조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-136">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="f4ecf-137">예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-137">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="f4ecf-138">사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-138">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="f4ecf-139">이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-139">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="f4ecf-140">Windows 10을 실행하는 노트북과 같은 호환 장치에서 로그인을 요구하는 등 고급 기능을 위해 조건부 액세스 정책을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-140">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="f4ecf-141">조건부 액세스에는 Microsoft 365 E3 및 E5에 포함된 Azure AD Premium P1 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-141">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="f4ecf-142">자세한 내용은 이 [조건부 액세스 개요](/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-142">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-support"></a><span data-ttu-id="f4ecf-143">Azure AD ID 보호 지원</span><span class="sxs-lookup"><span data-stu-id="f4ecf-143">Azure AD Identity Protection support</span></span>

<span data-ttu-id="f4ecf-144">Azure AD ID 보호 기능을 사용하여 다음과 같이 조건을 부여하는 추가 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-144">With Azure AD Identity Protection, you can create an additional Conditional Access policy that states:</span></span>

- <span data-ttu-id="f4ecf-145">로그인의 위험이 중간 또는 높은으로 판단되면, MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-145">If the risk of the sign-in is determined to be medium or high, require MFA.</span></span>

<span data-ttu-id="f4ecf-146">Azure AD ID 보호 기능은 Microsoft 365 E5에 포함된 Azure AD Premium P2 라이선스를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-146">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>

<span data-ttu-id="f4ecf-147">자세한 내용은 [위험에 기반한 조건부 액세스](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-147">For more information, see [Risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).</span></span>

<span data-ttu-id="f4ecf-148">Azure AD ID 보호를 사용하여 사용자가 MFA에 등록하도록 요구하는 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-148">With Azure AD Identity Protection, you can also create a policy to require your users to register for MFA.</span></span> <span data-ttu-id="f4ecf-149">더 자세한 내용은 [Azure AD 다단계 인증 등록 정책 구성](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-149">For more information, see [Configure the Azure AD Multi-Factor Authentication registration policy](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)</span></span>


## <a name="using-these-methods-together"></a><span data-ttu-id="f4ecf-150">이 방법들을 함께 사용</span><span class="sxs-lookup"><span data-stu-id="f4ecf-150">Using these methods together</span></span>

<span data-ttu-id="f4ecf-151">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-151">Keep the following in mind:</span></span>

- <span data-ttu-id="f4ecf-152">조건부 액세스 정책을 사용하도록 설정한 경우에는 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-152">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="f4ecf-153">보안 기본값이 활성화되어 있으면 조건부 액세스 정책을 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-153">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="f4ecf-154">보안 기본값을 사용하면 모든 새 사용자에게 MFA 등록 및 Microsoft Authenticator 앱 사용을 요구하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-154">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="f4ecf-155">이 표는 보안 기본값 및 조건부 액세스 정책으로 MFA를 활성화한 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-155">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="f4ecf-156">메서드</span><span class="sxs-lookup"><span data-stu-id="f4ecf-156">Method</span></span> | <span data-ttu-id="f4ecf-157">사용</span><span class="sxs-lookup"><span data-stu-id="f4ecf-157">Enabled</span></span> | <span data-ttu-id="f4ecf-158">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f4ecf-158">Disabled</span></span> | <span data-ttu-id="f4ecf-159">추가 인증 방법</span><span class="sxs-lookup"><span data-stu-id="f4ecf-159">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="f4ecf-160">**보안 기본값**</span><span class="sxs-lookup"><span data-stu-id="f4ecf-160">**Security defaults**</span></span>  | <span data-ttu-id="f4ecf-161">조건부 액세스 정책을 사용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="f4ecf-161">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="f4ecf-162">조건부 액세스 정책을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="f4ecf-162">Can use Conditional Access policies</span></span> | <span data-ttu-id="f4ecf-163">Microsoft Authenticator 앱</span><span class="sxs-lookup"><span data-stu-id="f4ecf-163">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="f4ecf-164">**조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="f4ecf-164">**Conditional Access policies**</span></span> | <span data-ttu-id="f4ecf-165">이 중 하나가 사용되는 경우 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-165">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="f4ecf-166">상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한 </span><span class="sxs-lookup"><span data-stu-id="f4ecf-166">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="f4ecf-167">보안 기본값을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="f4ecf-167">User specifies during MFA registration</span></span>  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a><span data-ttu-id="f4ecf-168">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="f4ecf-168">Let your users reset their own passwords</span></span>

<span data-ttu-id="f4ecf-169">사용자는 셀프 서비스 암호 재설정(SSPR)을 사용하여 IT 직원이 없어도 암호를 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-169">Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff.</span></span> <span data-ttu-id="f4ecf-170">사용자는 언제 어디에서나 암호를 신속하게 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-170">Users can quickly reset their passwords at any time and from any place.</span></span> <span data-ttu-id="f4ecf-171">더 자세한 내용은 [Azure AD 셀프 서비스 암호 재설정 배포 계획](/azure/active-directory/authentication/howto-sspr-deployment)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-171">For more information, see [Plan an Azure AD self-service password reset deployment](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

## <a name="sign-in-to-saas-apps-with-azure-ad"></a><span data-ttu-id="f4ecf-172">Azure AD를 사용하여 SaaS 앱에 로그인</span><span class="sxs-lookup"><span data-stu-id="f4ecf-172">Sign in to SaaS apps with Azure AD</span></span>

<span data-ttu-id="f4ecf-173">Azure AD는 사용자에게 클라우드 인증을 제공할 뿐만 아니라 사내, 마이크로소프트 클라우드 또는 다른 클라우드에 있는 모든 애플리케이션을 보호하는 중요한 방법이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-173">In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud.</span></span> <span data-ttu-id="f4ecf-174">[Azure AD](/azure/active-directory/manage-apps/plan-an-application-integration)에 앱을 통합하면 원격 작업자들이 필요로 하는 응용 프로그램을 쉽게 검색하고 안전하게 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-174">By [integrating your apps into Azure AD](/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for remote workers to discover the applications they need and sign into them securely.</span></span>

## <a name="admin-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="f4ecf-175">MFA 및 ID에 대한 관리자 기술 리소스</span><span class="sxs-lookup"><span data-stu-id="f4ecf-175">Admin technical resources for MFA and identity</span></span>

- [<span data-ttu-id="f4ecf-176">Azure AD를 사용하여 원격 작업을 수행하는 데 도움이 되는 상위 5가지 방법</span><span class="sxs-lookup"><span data-stu-id="f4ecf-176">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="f4ecf-177">Microsoft 365의 ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="f4ecf-177">Identity roadmap for Microsoft 365</span></span>](../enterprise/identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="f4ecf-178">Azure Academy Azure AD 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="f4ecf-178">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a><span data-ttu-id="f4ecf-179">1단계 결과</span><span class="sxs-lookup"><span data-stu-id="f4ecf-179">Results of Step 1</span></span>

<span data-ttu-id="f4ecf-180">MFA를 배포한 후 사용자는 다음 사항에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-180">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="f4ecf-181">로그인에 MFA를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-181">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="f4ecf-182">MFA 등록 절차를 완료했으며 모든 로그인에 MFA를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-182">Have completed the MFA registration process and are using MFA for all sign-ins.</span></span>
- <span data-ttu-id="f4ecf-183">SSPR을 사용하여 암호를 직접 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-183">Can use SSPR to reset their own passwords.</span></span>

## <a name="next-step"></a><span data-ttu-id="f4ecf-184">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f4ecf-184">Next step</span></span>

<span data-ttu-id="f4ecf-185">[![2단계: 온-프레미스 앱 및 서비스로의 원격 액세스 제공](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span><span class="sxs-lookup"><span data-stu-id="f4ecf-185">[![Step 2: Provide remote access to on-premises apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span></span>

<span data-ttu-id="f4ecf-186">온 프레미스 앱 및 서비스에 대한 원격 액세스를 제공하려면 [2단계](empower-people-to-work-remotely-remote-access.md)를 계속 진행하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ecf-186">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>
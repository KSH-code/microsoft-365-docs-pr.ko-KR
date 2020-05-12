---
title: 1단계. MFA를 사용하여 원격 작업자에 대 한 로그인 보안 강화
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 원격 작업자는 MFA(다단계 인증)를 사용하여 로그인해야 합니다.
ms.openlocfilehash: 2cb16c78f7fb0b1f9f48559c61a6200d6adcf470
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166140"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="8c835-104">1단계.</span><span class="sxs-lookup"><span data-stu-id="8c835-104">Step 1.</span></span> <span data-ttu-id="8c835-105">MFA를 사용하여 원격 작업자에 대 한 로그인 보안 강화</span><span class="sxs-lookup"><span data-stu-id="8c835-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="8c835-106">원격 작업자의 로그인에 대한 보안을 강화하려면 MFA(다단계 인증)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="8c835-107">MFA에서는 사용자 로그인이 사용자 계정 비밀번호 외에 추가 확인을 받아야합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="8c835-108">악의적인 사용자가 사용자 계정 암호를 확인하더라도 액세스 권한이 부여되기 전에 스마트폰으로 전송되는 문자 메시지와 같은 추가 확인에 응답 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![올바른 암호와 추가적인 확인을 수행하면 로그인에 성공합니다.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="8c835-110">원격 작업자, 특히 관리자를 포함한 모든 사용자에게 MFA를 강력히 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-110">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="8c835-111">사용자가 Microsoft 365 계획에 따라 MFA를 사용하도록하는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-111">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="8c835-112">계획</span><span class="sxs-lookup"><span data-stu-id="8c835-112">Plan</span></span>  |<span data-ttu-id="8c835-113">권장 사항</span><span class="sxs-lookup"><span data-stu-id="8c835-113">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="8c835-114">Microsoft 365 요금제(Azure AD Premium P1 또는 P2 제외)</span><span class="sxs-lookup"><span data-stu-id="8c835-114">Microsoft 365 plans (without Azure AD Premium P1 or P2)</span></span>     |<span data-ttu-id="8c835-115">[Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-115">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="8c835-116">Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-116">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="8c835-117">Microsoft 365 E3(Azure AD Premium P1 포함)</span><span class="sxs-lookup"><span data-stu-id="8c835-117">Microsoft 365 E3 (with Azure AD Premium P1)</span></span>     | <span data-ttu-id="8c835-118">[공통 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-118">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="8c835-119">- [관리자에게 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="8c835-119">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="8c835-120">- [모든 사용자에 대해 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="8c835-120">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="8c835-121">- [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="8c835-121">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="8c835-122">Microsoft 365 E5(Azure AD Premium P2 포함)</span><span class="sxs-lookup"><span data-stu-id="8c835-122">Microsoft 365 E5 (with Azure AD Premium P2)</span></span>     | <span data-ttu-id="8c835-123">Azure AD ID 보호를 활용하여 다음 두 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](../enterprise/identity-access-policies.md)을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="8c835-123">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="8c835-124">- [로그인 위험이 중간 이상인 경우 MFA 필요](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="8c835-124">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="8c835-125">- [최신 인증을 지원하지 않는 클라이언트 차단](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="8c835-125">- [Block clients that don't support modern authentication](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span></span><br><span data-ttu-id="8c835-126">- [위험이 높은 사용자는 암호를 변경해야 함](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="8c835-126">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="8c835-127">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="8c835-127">Security defaults</span></span>

<span data-ttu-id="8c835-128">보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-128">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="8c835-129">이 구독에는 보안 기본값이 설정되어 있으며 ***모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용해야 합니다***.</span><span class="sxs-lookup"><span data-stu-id="8c835-129">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="8c835-130">사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-130">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="8c835-131">14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-131">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="8c835-132">보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-132">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="8c835-133">조건부 액세스 정책 또는 개별 계정으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-133">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="8c835-134">자세한 정보는 이 [보안 기본값 개요](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c835-134">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="8c835-135">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="8c835-135">Conditional Access policies</span></span>

<span data-ttu-id="8c835-136">조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-136">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="8c835-137">예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-137">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="8c835-138">사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자인 사용자의 이름인 경우 액세스를 허용하기 전에 MFA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-138">If the user account name is for a user that is an Exchange, user, password, security, SharePoint, or global administrator, require MFA before allowing access.</span></span>

<span data-ttu-id="8c835-139">이 정책은 이러한 관리자 역할에 추가되거나 제거될 때 MFA에 대한 개별 사용자 계정을 구성하는 것을 기억하는 것보다 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-139">This policy is easier than trying to remember to configure individual user accounts for MFA when they are added to or removed from these administrator roles.</span></span>

<span data-ttu-id="8c835-140">Windows 10을 실행하는 노트북과 같은 호환 장치에서 로그인을 요구하는 등 고급 기능을 위해 조건부 액세스 정책을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-140">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="8c835-141">조건부 액세스에는 Microsoft 365 E3 및 E5에 포함된 Azure AD Premium P1이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-141">Conditional Access requires Azure AD Premium P1, which is included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="8c835-142">자세한 내용은 이 [조건부 액세스 개요](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c835-142">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-policies"></a><span data-ttu-id="8c835-143">Azure AD ID 보호 정책</span><span class="sxs-lookup"><span data-stu-id="8c835-143">Azure AD Identity Protection policies</span></span>

<span data-ttu-id="8c835-144">Azure AD ID 보호 정책은 로그인 평가 및 허용 조건을 지정하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-144">Azure AD Identity Protection policies are rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="8c835-145">예를 들어 다음을 나타내는 Azure AD ID 보호 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-145">For example, you can create an Azure AD Identity Protection policy that states:</span></span>

- <span data-ttu-id="8c835-146">로그인 위험이 중간 또는 높은 위험으로 판단되면 사용자는 MFA를 사용하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-146">If the risk of the sign-in is determined to be medium or high risk, the user must use MFA to sign in.</span></span>

<span data-ttu-id="8c835-147">Azure AD ID 보호에는 Microsoft 365 E5에 포함된 Azure AD Premium P2가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-147">Azure AD Identity Protection requires Azure AD Premium P2, which is included with Microsoft 365 E5.</span></span>

<span data-ttu-id="8c835-148">자세한 내용은 이 [Azure AD ID 보호 개요](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c835-148">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="using-these-methods-together"></a><span data-ttu-id="8c835-149">이 방법들을 함께 사용</span><span class="sxs-lookup"><span data-stu-id="8c835-149">Using these methods together</span></span>

<span data-ttu-id="8c835-150">이 경우 다음 사항을 유념해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-150">Keep in mind the following:</span></span>

- <span data-ttu-id="8c835-151">조건부 액세스 정책을 사용하도록 설정한 경우에는 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-151">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="8c835-152">보안 기본값이 활성화되어 있으면 조건부 액세스 정책을 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-152">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="8c835-153">보안 기본값을 사용하면 모든 새 사용자에게 MFA 등록 및 Microsoft Authenticator 앱 사용을 요구하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-153">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="8c835-154">이 표는 보안 기본값, 조건부 액세스 정책 및 사용자별 계정 설정으로 MFA를 활성화한 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-154">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="8c835-155">사용</span><span class="sxs-lookup"><span data-stu-id="8c835-155">Enabled</span></span> | <span data-ttu-id="8c835-156">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8c835-156">Disabled</span></span> | <span data-ttu-id="8c835-157">보조 인증 방법</span><span class="sxs-lookup"><span data-stu-id="8c835-157">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="8c835-158">**보안 기본값**</span><span class="sxs-lookup"><span data-stu-id="8c835-158">**Security defaults**</span></span>  | <span data-ttu-id="8c835-159">조건부 액세스 정책을 사용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="8c835-159">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="8c835-160">조건부 액세스 정책을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="8c835-160">Can use Conditional Access policies</span></span> | <span data-ttu-id="8c835-161">Microsoft Authenticator 앱</span><span class="sxs-lookup"><span data-stu-id="8c835-161">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="8c835-162">**조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="8c835-162">**Conditional Access policies**</span></span> | <span data-ttu-id="8c835-163">이 중 하나가 사용되는 경우 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-163">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="8c835-164">상기 수단을 모두 사용하고 있지 않은 경우 보안 기본값을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="8c835-164">If all are not enabled, you can enable security defaults</span></span>  | <span data-ttu-id="8c835-165">MFA 등록 중 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8c835-165">User-specified during MFA registration</span></span>  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="8c835-166">MFA 및 ID에 대한 관리 교육 및 기술 리소스</span><span class="sxs-lookup"><span data-stu-id="8c835-166">Admin training and technical resources for MFA and identity</span></span>

- [<span data-ttu-id="8c835-167">Microsoft 365에 대한 MFA 계획</span><span class="sxs-lookup"><span data-stu-id="8c835-167">MFA planning for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [<span data-ttu-id="8c835-168">Azure AD를 사용하여 원격 작업을 수행하는 데 도움이 되는 상위 5가지 방법</span><span class="sxs-lookup"><span data-stu-id="8c835-168">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="8c835-169">Microsoft 365 ID 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="8c835-169">Plan and deploy your Microsoft 365 identity infrastructure</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [<span data-ttu-id="8c835-170">Azure Academy Azure AD 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="8c835-170">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="8c835-171">Azure Multi-Factor Authentication 등록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="8c835-171">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a><span data-ttu-id="8c835-172">1단계 결과</span><span class="sxs-lookup"><span data-stu-id="8c835-172">Results of Step 1</span></span>

<span data-ttu-id="8c835-173">MFA를 배포한 후 사용자는 다음 사항에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-173">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="8c835-174">로그인에 MFA를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-174">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="8c835-175">MFA 등록 절차를 완료했으며 모든 로그인에 MFA를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c835-175">Have completed the MFA registration process and is using MFA for all sign-ins.</span></span>

## <a name="next-step"></a><span data-ttu-id="8c835-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8c835-176">Next step</span></span>

<span data-ttu-id="8c835-177">온 프레미스 앱 및 서비스에 대한 원격 액세스를 제공하려면 [2단계](empower-people-to-work-remotely-remote-access.md)를 계속 진행하세요.</span><span class="sxs-lookup"><span data-stu-id="8c835-177">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>

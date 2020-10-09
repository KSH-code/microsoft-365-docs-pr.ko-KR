---
title: Microsoft 365 테넌트에 사용자 로그인 보안 기능
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365initiative-coredeploy
ms.custom: ''
description: 사용자가 MFA(다단계 인증) 및 기타 기능을 사용하여 안전하게 로그인하도록 합니다.
ms.openlocfilehash: 64b873a243d0ce86ee3700d5150076f88031a483
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399138"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="bf211-103">Microsoft 365 테넌트에 사용자 로그인 보안 기능</span><span class="sxs-lookup"><span data-stu-id="bf211-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="bf211-104">사용자 로그인의 보안을 강화하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="bf211-105">비즈니스용 Windows Hello 사용</span><span class="sxs-lookup"><span data-stu-id="bf211-105">Use Windows Hello for Business</span></span>
- <span data-ttu-id="bf211-106">Azure AD(Azure Active Directory) 암호 보호 사용</span><span class="sxs-lookup"><span data-stu-id="bf211-106">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="bf211-107">MFA(다단계 인증) 사용</span><span class="sxs-lookup"><span data-stu-id="bf211-107">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="bf211-108">ID 및 장치 액세스 구성 배포</span><span class="sxs-lookup"><span data-stu-id="bf211-108">Deploy identity and device access configurations</span></span>
- <span data-ttu-id="bf211-109">Azure AD ID 보호를 사용하여 자격 증명 손상으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="bf211-109">Protect against credential compromise with Azure AD Identity Protection</span></span>

## <a name="windows-hello-for-business"></a><span data-ttu-id="bf211-110">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="bf211-110">Windows Hello for Business</span></span>

<span data-ttu-id="bf211-111">Windows 10 Enterprise의 비즈니스용 windows Hello는 Windows 장치에 로그인할 때 암호를 강력한 2 단계 인증으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-111">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="bf211-112">2단계 인증 요소는 장치에 연결된 새로운 유형의 사용자 자격 증명과 생체 인식 또는 PIN입니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-112">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="bf211-113">자세한 내용은 [비즈니스용 Windows Hello 개요](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-113">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


## <a name="azure-ad-password-protection"></a><span data-ttu-id="bf211-114">Azure AD 암호 보호</span><span class="sxs-lookup"><span data-stu-id="bf211-114">Azure AD Password Protection</span></span>

<span data-ttu-id="bf211-115">Azure AD 암호 보호에서는 알려진 취약한 암호와 해당 변형을 감지하고 차단하며 조직에 관련된 추가 취약한 용어를 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-115">Azure AD Password Protection detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="bf211-116">기본 전역 금지 암호 목록은 Azure AD 테넌트의 모든 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-116">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="bf211-117">사용자 지정 금지 암호 목록에서 추가 항목을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-117">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="bf211-118">사용자가 암호를 변경하거나 재설정하면 해당 금지된 암호 목록은 강력한 암호를 사용하도록 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-118">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="bf211-119">자세한 내용은 [Azure AD 암호 보호구성](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-119">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="bf211-120">MFA</span><span class="sxs-lookup"><span data-stu-id="bf211-120">MFA</span></span>

<span data-ttu-id="bf211-121">MFA에서는 사용자 로그인이 사용자 계정 비밀번호 외에 추가 확인을 받아야합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-121">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="bf211-122">악의적인 사용자가 사용자 계정 암호를 확인하더라도 액세스 권한이 부여되기 전에 스마트폰으로 전송되는 문자 메시지와 같은 추가 확인에 응답 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-122">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![올바른 암호와 추가적인 확인을 수행하면 로그인에 성공합니다.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="bf211-124">MFA를 사용하는 첫 번째 단계는 ***모든 관리자 계정(예를 들어, 권한 있는 계정이라고도 함)에 해당 항목을 요청***하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-124">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="bf211-125">첫 번째 단계를 넘어서, Microsoft는 모든 사용자에 대해 MFA를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-125">Beyond this first step, Microsoft recommends MFA For all users.</span></span>

<span data-ttu-id="bf211-126">Microsoft 365 플랜에 따라 관리자나 사용자가 MFA를 사용하도록 요청하는 데 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-126">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="bf211-127">계획</span><span class="sxs-lookup"><span data-stu-id="bf211-127">Plan</span></span> | <span data-ttu-id="bf211-128">권장 사항</span><span class="sxs-lookup"><span data-stu-id="bf211-128">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="bf211-129">모든 Microsoft 365 요금제(Azure AD Premium P1 또는 P2 라이선스 제외)</span><span class="sxs-lookup"><span data-stu-id="bf211-129">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="bf211-130">[Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-130">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="bf211-131">Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-131">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="bf211-132">Microsoft 365 E3(Azure AD Premium P1 라이선스 포함)</span><span class="sxs-lookup"><span data-stu-id="bf211-132">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="bf211-133">[공통 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-133">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="bf211-134">- [관리자에게 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="bf211-134">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="bf211-135">- [모든 사용자에 대해 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="bf211-135">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="bf211-136">- [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="bf211-136">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="bf211-137">Microsoft 365 E5(Azure AD Premium P2 라이선스 포함)</span><span class="sxs-lookup"><span data-stu-id="bf211-137">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="bf211-138">Azure AD ID 보호를 활용하여 다음 두 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](../security/office-365-security/identity-access-policies.md)을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-138">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../security/office-365-security/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="bf211-139">- [로그인 위험이 중간 이상인 경우 MFA 필요](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="bf211-139">- [Require MFA when sign-in risk is medium or high](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="bf211-140">- [위험이 높은 사용자는 암호를 변경해야 함](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="bf211-140">- [High risk users must change password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="bf211-141">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="bf211-141">Security defaults</span></span>

<span data-ttu-id="bf211-142">보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-142">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="bf211-143">이 구독에는 보안 기본값이 설정되어 있으며 ***모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용해야 합니다***.</span><span class="sxs-lookup"><span data-stu-id="bf211-143">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="bf211-144">사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-144">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="bf211-145">14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-145">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="bf211-146">보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-146">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="bf211-147">조건부 액세스 정책 또는 개별 계정으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-147">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="bf211-148">자세한 정보는 [보안 기본값 개요](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-148">For more information, see the [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="bf211-149">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="bf211-149">Conditional Access policies</span></span>

<span data-ttu-id="bf211-150">조건부 액세스 정책은 로그인이 평가되고 액세스 권한이 부여되는 조건을 지정하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-150">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="bf211-151">예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-151">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="bf211-152">사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-152">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="bf211-153">이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-153">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="bf211-154">Windows 10을 실행하는 노트북과 같은 호환 장치에서 로그인을 요구하는 등 고급 기능을 위해 조건부 액세스 정책을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-154">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="bf211-155">조건부 액세스에는 Microsoft 365 E3 및 E5에 포함된 Azure AD Premium P1 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-155">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="bf211-156">자세한 내용은 [조건부 액세스 개요](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-156">For more information, see the [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="bf211-157">이 방법들을 함께 사용</span><span class="sxs-lookup"><span data-stu-id="bf211-157">Using these methods together</span></span>

<span data-ttu-id="bf211-158">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-158">Keep the following in mind:</span></span>

- <span data-ttu-id="bf211-159">조건부 액세스 정책을 사용하도록 설정한 경우에는 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-159">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="bf211-160">보안 기본값이 활성화되어 있으면 조건부 액세스 정책을 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-160">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="bf211-161">보안 기본값을 사용하면 모든 새 사용자에게 MFA 등록 및 Microsoft Authenticator 앱 사용을 요구하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-161">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="bf211-162">이 표는 보안 기본값 및 조건부 액세스 정책으로 MFA를 활성화한 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-162">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="bf211-163">메서드</span><span class="sxs-lookup"><span data-stu-id="bf211-163">Method</span></span> | <span data-ttu-id="bf211-164">사용</span><span class="sxs-lookup"><span data-stu-id="bf211-164">Enabled</span></span> | <span data-ttu-id="bf211-165">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="bf211-165">Disabled</span></span> | <span data-ttu-id="bf211-166">추가 인증 방법</span><span class="sxs-lookup"><span data-stu-id="bf211-166">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="bf211-167">**보안 기본값**</span><span class="sxs-lookup"><span data-stu-id="bf211-167">**Security defaults**</span></span>  | <span data-ttu-id="bf211-168">조건부 액세스 정책을 사용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="bf211-168">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="bf211-169">조건부 액세스 정책을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="bf211-169">Can use Conditional Access policies</span></span> | <span data-ttu-id="bf211-170">Microsoft Authenticator 앱</span><span class="sxs-lookup"><span data-stu-id="bf211-170">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="bf211-171">**조건부 액세스 정책**</span><span class="sxs-lookup"><span data-stu-id="bf211-171">**Conditional Access policies**</span></span> | <span data-ttu-id="bf211-172">이 중 하나가 사용되는 경우 보안 기본값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-172">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="bf211-173">상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한 </span><span class="sxs-lookup"><span data-stu-id="bf211-173">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="bf211-174">보안 기본값을 사용할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="bf211-174">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="bf211-175">ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="bf211-175">Identity and device access configurations</span></span>

<span data-ttu-id="bf211-176">ID 및 장치 액세스 설정과 정책은 권장되는 필수 기능 및 해당 설정이며, 이는 어떤 조건으로 지정된 액세스 요청이 부여되는지를 결정하는 조건부 액세스, Intune 및 Azure AD Identity Protection 정책과 함께 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-176">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="bf211-177">이 결정은 로그인의 사용자 계정, 사용 중인 장치, 사용자가 액세스하기 위해 사용하는 앱, 액세스 요청을 만든 위치, 요청 위험에 대한 평가를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-177">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="bf211-178">이 기능을 사용하여 승인된 사용자와 장치만 중요한 리소스에 액세스할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-178">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="bf211-179">Azure AD ID 보호 기능은 Microsoft 365 E5에 포함된 Azure AD Premium P2 라이선스를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-179">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="bf211-180">ID 및 장치 액세스 정책은 세 계층으로 사용하도록 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-180">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="bf211-181">기준 보호는 앱과 데이터에 액세스하는 ID와 장치에 대한 최소 수준의 보안입니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-181">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="bf211-182">중요 보호는 특정 데이터에 대한 추가 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-182">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="bf211-183">ID 및 장치에는 보안 및 장치 상태에 대해 더 높은 수준을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-183">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="bf211-184">규제가 엄격하거나 높은 수준으로 분류된 데이터를 포함하는 환경에 대한 보호는 높은 수준으로 분류되거나, 거래 비밀을 포함하거나, 데이터 규제가 적용되는 소량 데이터에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-184">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="bf211-185">ID 및 장치에는 높은 수준의 보안 및 장치 상태 요구 사항이 많이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-185">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="bf211-186">해당 계층과 관련 구성은 데이터, ID 및 장치에 대해 일관된 수준의 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-186">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="bf211-187">Microsoft Teams, Exchange Online 및 SharePoint에 대한 특정 설정을 포함하여 조직에서 ID 및 장치 액세스 정책을 구성하고 배포하는 것이 매우 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-187">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="bf211-188">자세한 내용은 [ID 및 장치 액세스 구성](../security/office-365-security/microsoft-365-policies-configurations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-188">For more information, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

## <a name="azure-ad-identity-protection"></a><span data-ttu-id="bf211-189">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="bf211-189">Azure AD Identity Protection</span></span>

<span data-ttu-id="bf211-190">이 섹션에서는 공격자가 조직의 클라우드 서비스 및 데이터에 액세스하기 위한 사용자의 계정 이름 및 암호를 파악한 경우에 발생하는 자격 증명 침해로부터 보호하는 정책 구성 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-190">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="bf211-191">Azure AD ID Protection은 공격자가 사용자 계정의 자격 증명을 손상시키지 못하도록 하는데 도움이 되는 다양한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-191">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="bf211-192">Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-192">With Azure AD Identity Protection, you can:</span></span>

|<span data-ttu-id="bf211-193">기능</span><span class="sxs-lookup"><span data-stu-id="bf211-193">Capability</span></span>|<span data-ttu-id="bf211-194">설명</span><span class="sxs-lookup"><span data-stu-id="bf211-194">Description</span></span>|
|:---------|:---------|
| <span data-ttu-id="bf211-195">조직의 ID에서 잠재적인 취약점 확인 및 해결</span><span class="sxs-lookup"><span data-stu-id="bf211-195">Determine and address potential vulnerabilities in your organization’s identities</span></span> | <span data-ttu-id="bf211-196">Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 변칙 및 의심스러운 활동을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-196">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="bf211-197">이 데이터를 사용하여 Azure AD ID 보호는 문제를 평가하고 조치를 취하는 데 도움이 되는 보고서 및 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-197">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="bf211-198">조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응</span><span class="sxs-lookup"><span data-stu-id="bf211-198">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="bf211-199">지정된 위험 수준에 도달했을 때 검색된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-199">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="bf211-200">Azure AD 및 Microsoft Intune에서 제공하는 다른 조건부 액세스 제어 외에도, 이러한 정책은 액세스를 자동으로 차단하거나 암호 재설정을 포함하는 수정 조치를 취하고, 후속 로그인에 대해 Azure 다단계 인증을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-200">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span> |
| <span data-ttu-id="bf211-201">의심스러운 사건을 조사하여 관리 작업으로 해결</span><span class="sxs-lookup"><span data-stu-id="bf211-201">Investigate suspicious incidents and resolve them with administrative actions</span></span> | <span data-ttu-id="bf211-p116">보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf211-p116">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span> |
|||

<span data-ttu-id="bf211-204">[Azure AD ID 보호에 대한 자세한 정보](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-204">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="bf211-205">[Azure AD ID 보호를 사용하도록 설정하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf211-205">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="bf211-206">MFA 및 보안 로그인에 대한 관리자 기술 리소스</span><span class="sxs-lookup"><span data-stu-id="bf211-206">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="bf211-207">Microsoft 365에 대한 MFA</span><span class="sxs-lookup"><span data-stu-id="bf211-207">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="bf211-208">Microsoft 365의 ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="bf211-208">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="bf211-209">Azure Academy Azure AD 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="bf211-209">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="bf211-210">Azure Multi-Factor Authentication 등록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="bf211-210">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="bf211-211">ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="bf211-211">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a><span data-ttu-id="bf211-212">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf211-212">Next step</span></span>

[<span data-ttu-id="bf211-213">사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="bf211-213">Manage your user accounts</span></span>](manage-microsoft-365-accounts.md)
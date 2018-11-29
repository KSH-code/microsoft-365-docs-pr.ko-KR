---
title: 일반적인 id 및 장치에 대 한 액세스 정책-Microsoft 365 Enterprise | Microsoft 문서
description: ID 및 장치 액세스 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870354"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="6f244-103">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6f244-103">Common identity and device access policies</span></span>
<span data-ttu-id="6f244-104">이 문서에서는 온-프레미스 응용 프로그램을 비롯 하 여 Azure AD 응용 프로그램 프록시를 사용 하 여 게시 클라우드 서비스에 대 한 액세스를 보호 하는 것에 대 한 정책 권장 공통을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="6f244-p101">이 지침은 새로 프로비전한 환경에 권장되는 정책을 배포하는 방법에 대해 설명합니다. 별도의 랩 환경에서 이러한 정책을 설정하면 프리 프로덕션 및 프로덕션 환경으로 롤아웃을 준비하기 전에 권장되는 정책을 이해하고 평가할 수 있습니다. 새로 프로비전한 환경은 클라우드 전용 또는 하이브리드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p101">This guidance discusses how to deploy the recommended policies in a newly provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your pre-production and production environments. Your newly provisioned environment may be cloud-only or Hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="6f244-108">정책 설정</span><span class="sxs-lookup"><span data-stu-id="6f244-108">Policy set</span></span> 

<span data-ttu-id="6f244-p102">다음 다이어그램에서는 권장 되는 정책 집합을 보여줍니다. 어떤 계층 보호를 적용 하는 각 정책 및 Pc, 휴대폰 및 태블릿 또는 장치의 두 범주에 정책이 적용 되는 있는지 여부를 표시 합니다. 또한 이러한 정책은 구성 된 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs, phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Id 및 장치에 대 한 액세스를 구성 하기 위한 일반적인 정책](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="6f244-113">이 문서의 나머지 부분에서는 이러한 정책을 구성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="6f244-p103">장치가 의도 한 사용자를 소유 하는 보증에 대 한 Intune로 장치를 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다. 및 장치 규정 준수 정책을 적용 하기 전에 Intune로 장치를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. And you must enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="6f244-p104">제공 하려면 이러한 작업을 수행 하기 위해 시간,이 표에 나열 된 순서 대로 기본 정책을 구현 하는 것이 좋습니다. 그러나 중요 한 및 높은 규제 보호에 대 한 MFA 정책 언제 든 지 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="6f244-118">보호 수준</span><span class="sxs-lookup"><span data-stu-id="6f244-118">Protection level</span></span>|<span data-ttu-id="6f244-119">Policies(정책)</span><span class="sxs-lookup"><span data-stu-id="6f244-119">Policies</span></span>|<span data-ttu-id="6f244-120">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6f244-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="6f244-121">**기준**</span><span class="sxs-lookup"><span data-stu-id="6f244-121">**Baseline**</span></span>|[<span data-ttu-id="6f244-122">로그인 위험 *보통* 또는 *높음* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="6f244-123">현대 인증을 지원 하지 않는 블록 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6f244-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="6f244-124">현대 인증을 사용 하지 않는 클라이언트는 이러한 차단 하는 것이 중요 하므로 조건부 액세스 규칙을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these.</span></span>|
|        |[<span data-ttu-id="6f244-125">높은 위험 수준 사용자 암호를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="6f244-126">자신의 계정에 대 한 높은 위험 수준 감지 되는 경우 로그인 할 때 암호를 변경 하도록 사용자를 강제로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-126">Forces users to change their password when signing in if high risk activity is detected for their account.</span></span>|
|        |[<span data-ttu-id="6f244-127">응용 프로그램 보호 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6f244-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="6f244-128">플랫폼 (iOS, Android, Windows) 당 하나의 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="6f244-129">승인 된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="6f244-130">전화 및 태블릿에 대 한 모바일 응용 프로그램 보호 강제 적용</span><span class="sxs-lookup"><span data-stu-id="6f244-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="6f244-131">장치 규정 준수 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6f244-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="6f244-132">각 플랫폼에 대 한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-132">One policy for each platform.</span></span>|
|        |[<span data-ttu-id="6f244-133">호환 Pc 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="6f244-134">Pc의 Intune 관리 강제 적용</span><span class="sxs-lookup"><span data-stu-id="6f244-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="6f244-135">**중요**</span><span class="sxs-lookup"><span data-stu-id="6f244-135">**Sensitive**</span></span>|[<span data-ttu-id="6f244-136">로그인 위험 *낮음*, *보통* , *높음* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="6f244-137">준수 Pc *및* 모바일 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="6f244-138">Pc 및 전화/태블릿 Intune 관리 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-138">Enforces Intune management for PCs and phone/tablets.</span></span>|
|<span data-ttu-id="6f244-139">**높은 규제**</span><span class="sxs-lookup"><span data-stu-id="6f244-139">**Highly regulated**</span></span>|[<span data-ttu-id="6f244-140">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="6f244-141">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6f244-141">Assigning policies to users</span></span>
<span data-ttu-id="6f244-p105">정책을 구성 하기 전에 각 계층 보호에 대 한를 사용 하는 Azure AD 그룹을 식별 합니다. 일반적으로 초기 보호 조직의 모든 사용자에 게에 적용 됩니다. 초기 계획 및 중요 한 보호를 모두 포함 된 사용자에 적용 된 모든 기본 정책 및 중요 한 정책을 갖습니다. 보호 누적 이며 가장 제한적인 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="6f244-p106">조건부 액세스 제외에 대 한 Azure AD 그룹을 만들려면는 것이 좋습니다. "제외" 아래에서 조건부 액세스 규칙의 모든이 그룹을 추가 합니다. 이렇게 하면 액세스 문제를 해결 하는 동안 사용자에 대 한 액세스를 제공 하는 방법입니다. 임시 솔루션만으로 이러한 것이 좋습니다. 변경 내용에 대 한이 그룹을 모니터링 하 고 제외 그룹은 의도 한 대로 사용 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="6f244-151">다음 다이어그램에서는 사용자 할당 및 제외 항목의 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![예제 사용자 할당 및 MFA 규칙에 대 한 제외](../images/identity-access-policies-assignment.png)

<span data-ttu-id="6f244-p107">그림의 "위쪽 비밀 프로젝트 X 팀" MFA *항상*필요로 하는 조건부 액세스 정책을 할당 됩니다. 사용자에 게 보다 높은 수준의 보호를 적용할 때 적절히를 수 있습니다. 이 프로젝트 팀의 구성원 매우 규제 콘텐츠를 표시 되지 않음 하는 경우에 로그온 할 때마다 두 형태의 인증을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly regulated content.</span></span>  

 <span data-ttu-id="6f244-p108">Office 365 그룹으로 이러한 지침의 일부로 만들어진 모든 Azure AD 그룹을 만들어야 합니다. 이 SharePoint Online에서 문서를 보호 하는 경우에 특히 Azure 정보 보호 (AIP)의 배포에 대 한 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Office 365 그룹을 만들기 위한 화면 캡처](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="6f244-159">로그인 위험에 따라 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="6f244-p109">MFA 요구를 하기 전에 먼저는 Identity 보호 MFA 등록 정책을 사용 하 여 MFA에 대 한 사용자를 등록 합니다. 사용자는 등록 한 후에 로그인에 대 한 MFA를 적용할 수 있습니다. [필수 구성 요소 작업](identity-access-prerequisites.md) MFA 통해 등록 하는 모든 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="6f244-163">새 조건부 액세스 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6f244-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="6f244-p110">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="6f244-166">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6f244-167">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6f244-168">다음 스크린샷은 같이 **새 정책** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-168">Choose **New policy** as shown in the screenshot below:</span></span>

![기준 CA 정책 만들기](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="6f244-170">다음 표에서이 정책을 구현 하기 위한 조건부 액세스 정책 설정을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="6f244-171">**할당**</span><span class="sxs-lookup"><span data-stu-id="6f244-171">**Assignments**</span></span>

|<span data-ttu-id="6f244-172">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-172">Type</span></span>|<span data-ttu-id="6f244-173">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-173">Properties</span></span>|<span data-ttu-id="6f244-174">값</span><span class="sxs-lookup"><span data-stu-id="6f244-174">Values</span></span>|<span data-ttu-id="6f244-175">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-176">사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="6f244-176">Users and groups</span></span>|<span data-ttu-id="6f244-177">포함</span><span class="sxs-lookup"><span data-stu-id="6f244-177">Include</span></span>|<span data-ttu-id="6f244-178">사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택</span><span class="sxs-lookup"><span data-stu-id="6f244-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="6f244-179">파일럿 사용자를 포함한 보안 그룹으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-179">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="6f244-180">제외</span><span class="sxs-lookup"><span data-stu-id="6f244-180">Exclude</span></span>|<span data-ttu-id="6f244-181">예외 보안 그룹; 서비스 계정(앱 ID)</span><span class="sxs-lookup"><span data-stu-id="6f244-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="6f244-182">필요에 따라 일시적으로 수정한 멤버 자격</span><span class="sxs-lookup"><span data-stu-id="6f244-182">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="6f244-183">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="6f244-183">Cloud apps</span></span>|<span data-ttu-id="6f244-184">포함</span><span class="sxs-lookup"><span data-stu-id="6f244-184">Include</span></span>|<span data-ttu-id="6f244-p111">이 규칙을 적용 하려면 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택합니다</span><span class="sxs-lookup"><span data-stu-id="6f244-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="6f244-187">조건</span><span class="sxs-lookup"><span data-stu-id="6f244-187">Conditions</span></span>|<span data-ttu-id="6f244-188">구성됨</span><span class="sxs-lookup"><span data-stu-id="6f244-188">Configured</span></span>|<span data-ttu-id="6f244-189">예</span><span class="sxs-lookup"><span data-stu-id="6f244-189">Yes</span></span>|<span data-ttu-id="6f244-190">사용자 환경 및 요구에 맞게 구성</span><span class="sxs-lookup"><span data-stu-id="6f244-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="6f244-191">로그인 위험</span><span class="sxs-lookup"><span data-stu-id="6f244-191">Sign-in risk</span></span>|<span data-ttu-id="6f244-192">위험 수준</span><span class="sxs-lookup"><span data-stu-id="6f244-192">Risk level</span></span>||<span data-ttu-id="6f244-193">다음 표에서의 지침을 참조 하십시오</span><span class="sxs-lookup"><span data-stu-id="6f244-193">See the guidance in the following table</span></span>|

<span data-ttu-id="6f244-194">**로그인 위험**</span><span class="sxs-lookup"><span data-stu-id="6f244-194">**Sign-in risk**</span></span>

<span data-ttu-id="6f244-195">대상으로 하는 보호 수준에 따라 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="6f244-196">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-196">Property</span></span>|<span data-ttu-id="6f244-197">보호 수준</span><span class="sxs-lookup"><span data-stu-id="6f244-197">Level of protection</span></span>|<span data-ttu-id="6f244-198">값</span><span class="sxs-lookup"><span data-stu-id="6f244-198">Values</span></span>|<span data-ttu-id="6f244-199">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-200">위험 수준</span><span class="sxs-lookup"><span data-stu-id="6f244-200">Risk level</span></span>|<span data-ttu-id="6f244-201">기준</span><span class="sxs-lookup"><span data-stu-id="6f244-201">Baseline</span></span>|<span data-ttu-id="6f244-202">높음, 중간</span><span class="sxs-lookup"><span data-stu-id="6f244-202">High, medium</span></span>|<span data-ttu-id="6f244-203">모두 선택</span><span class="sxs-lookup"><span data-stu-id="6f244-203">Check both</span></span>|
| |<span data-ttu-id="6f244-204">중요</span><span class="sxs-lookup"><span data-stu-id="6f244-204">Sensitive</span></span>|<span data-ttu-id="6f244-205">높음, 보통, 낮음</span><span class="sxs-lookup"><span data-stu-id="6f244-205">High, medium, low</span></span>|<span data-ttu-id="6f244-206">세 항목 모두 선택</span><span class="sxs-lookup"><span data-stu-id="6f244-206">Check all three</span></span>|
| |<span data-ttu-id="6f244-207">높은 규제</span><span class="sxs-lookup"><span data-stu-id="6f244-207">Highly regulated</span></span>| |<span data-ttu-id="6f244-208">모든 옵션을 항상 MFA을 적용 하도록 선택 하지 않은 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="6f244-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="6f244-209">**액세스 제어**</span><span class="sxs-lookup"><span data-stu-id="6f244-209">**Access controls**</span></span>

|<span data-ttu-id="6f244-210">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-210">Type</span></span>|<span data-ttu-id="6f244-211">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-211">Properties</span></span>|<span data-ttu-id="6f244-212">값</span><span class="sxs-lookup"><span data-stu-id="6f244-212">Values</span></span>|<span data-ttu-id="6f244-213">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-214">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6f244-214">Grant</span></span>|<span data-ttu-id="6f244-215">액세스 허가</span><span class="sxs-lookup"><span data-stu-id="6f244-215">Grant access</span></span>|<span data-ttu-id="6f244-216">True</span><span class="sxs-lookup"><span data-stu-id="6f244-216">True</span></span>|<span data-ttu-id="6f244-217">선택</span><span class="sxs-lookup"><span data-stu-id="6f244-217">Selected</span></span>|
||<span data-ttu-id="6f244-218">MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-218">Require MFA</span></span>|<span data-ttu-id="6f244-219">True</span><span class="sxs-lookup"><span data-stu-id="6f244-219">True</span></span>|<span data-ttu-id="6f244-220">Check</span><span class="sxs-lookup"><span data-stu-id="6f244-220">Check</span></span>|
||<span data-ttu-id="6f244-221">규격으로 표시 하는 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="6f244-222">False</span><span class="sxs-lookup"><span data-stu-id="6f244-222">False</span></span>||
||<span data-ttu-id="6f244-223">하이브리드 Azure AD 조인 된 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-223">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="6f244-224">False</span><span class="sxs-lookup"><span data-stu-id="6f244-224">False</span></span>||
||<span data-ttu-id="6f244-225">승인 된 클라이언트 응용 프로그램을 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-225">Require approved client app</span></span>|<span data-ttu-id="6f244-226">False</span><span class="sxs-lookup"><span data-stu-id="6f244-226">False</span></span>||
||<span data-ttu-id="6f244-227">선택된 컨트롤이 모두 필요함</span><span class="sxs-lookup"><span data-stu-id="6f244-227">Require all the selected controls</span></span>|<span data-ttu-id="6f244-228">True</span><span class="sxs-lookup"><span data-stu-id="6f244-228">True</span></span>|<span data-ttu-id="6f244-229">선택</span><span class="sxs-lookup"><span data-stu-id="6f244-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="6f244-p112">**클릭 하**여이 정책을 사용 하도록 설정 해야 합니다. 또한 정책을 테스트할 [경우에 어떻게](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 고려</span><span class="sxs-lookup"><span data-stu-id="6f244-p112">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="6f244-232">현대 인증을 지원 하지 않는 블록 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6f244-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="6f244-p113">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="6f244-235">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6f244-236">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6f244-237">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-237">Choose **New policy**.</span></span>

<span data-ttu-id="6f244-238">다음 표에서이 정책을 구현 하기 위한 조건부 액세스 정책 설정을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="6f244-239">**할당**</span><span class="sxs-lookup"><span data-stu-id="6f244-239">**Assignments**</span></span>

|<span data-ttu-id="6f244-240">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-240">Type</span></span>|<span data-ttu-id="6f244-241">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-241">Properties</span></span>|<span data-ttu-id="6f244-242">값</span><span class="sxs-lookup"><span data-stu-id="6f244-242">Values</span></span>|<span data-ttu-id="6f244-243">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-244">사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="6f244-244">Users and groups</span></span>|<span data-ttu-id="6f244-245">포함</span><span class="sxs-lookup"><span data-stu-id="6f244-245">Include</span></span>|<span data-ttu-id="6f244-246">사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택</span><span class="sxs-lookup"><span data-stu-id="6f244-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="6f244-247">파일럿 사용자를 포함한 보안 그룹으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-247">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="6f244-248">제외</span><span class="sxs-lookup"><span data-stu-id="6f244-248">Exclude</span></span>|<span data-ttu-id="6f244-249">예외 보안 그룹; 서비스 계정(앱 ID)</span><span class="sxs-lookup"><span data-stu-id="6f244-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="6f244-250">필요에 따라 일시적으로 수정한 멤버 자격</span><span class="sxs-lookup"><span data-stu-id="6f244-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="6f244-251">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="6f244-251">Cloud apps</span></span>|<span data-ttu-id="6f244-252">포함</span><span class="sxs-lookup"><span data-stu-id="6f244-252">Include</span></span>|<span data-ttu-id="6f244-p114">이 규칙을 적용 하려면 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택합니다</span><span class="sxs-lookup"><span data-stu-id="6f244-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="6f244-255">조건</span><span class="sxs-lookup"><span data-stu-id="6f244-255">Conditions</span></span>|<span data-ttu-id="6f244-256">구성됨</span><span class="sxs-lookup"><span data-stu-id="6f244-256">Configured</span></span>|<span data-ttu-id="6f244-257">예</span><span class="sxs-lookup"><span data-stu-id="6f244-257">Yes</span></span>|<span data-ttu-id="6f244-258">클라이언트 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="6f244-258">Configure Client apps</span></span>|
|<span data-ttu-id="6f244-259">클라이언트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6f244-259">Client apps</span></span>|<span data-ttu-id="6f244-260">구성됨</span><span class="sxs-lookup"><span data-stu-id="6f244-260">Configured</span></span>|<span data-ttu-id="6f244-261">예</span><span class="sxs-lookup"><span data-stu-id="6f244-261">Yes</span></span>|<span data-ttu-id="6f244-262">모바일 응용 프로그램 및 데스크톱 클라이언트를 다른 클라이언트 (두 항목 모두 선택)</span><span class="sxs-lookup"><span data-stu-id="6f244-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="6f244-263">**액세스 제어**</span><span class="sxs-lookup"><span data-stu-id="6f244-263">**Access controls**</span></span>

|<span data-ttu-id="6f244-264">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-264">Type</span></span>|<span data-ttu-id="6f244-265">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-265">Properties</span></span>|<span data-ttu-id="6f244-266">값</span><span class="sxs-lookup"><span data-stu-id="6f244-266">Values</span></span>|<span data-ttu-id="6f244-267">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-268">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6f244-268">Grant</span></span>|<span data-ttu-id="6f244-269">액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6f244-269">Block access</span></span>|<span data-ttu-id="6f244-270">True</span><span class="sxs-lookup"><span data-stu-id="6f244-270">True</span></span>|<span data-ttu-id="6f244-271">선택</span><span class="sxs-lookup"><span data-stu-id="6f244-271">Selected</span></span>|
||<span data-ttu-id="6f244-272">MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-272">Require MFA</span></span>|<span data-ttu-id="6f244-273">False</span><span class="sxs-lookup"><span data-stu-id="6f244-273">False</span></span>||
||<span data-ttu-id="6f244-274">규격으로 표시 하는 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="6f244-275">False</span><span class="sxs-lookup"><span data-stu-id="6f244-275">False</span></span>||
||<span data-ttu-id="6f244-276">하이브리드 Azure AD 조인 된 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-276">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="6f244-277">False</span><span class="sxs-lookup"><span data-stu-id="6f244-277">False</span></span>||
||<span data-ttu-id="6f244-278">승인 된 클라이언트 응용 프로그램을 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-278">Require approved client app</span></span>|<span data-ttu-id="6f244-279">False</span><span class="sxs-lookup"><span data-stu-id="6f244-279">False</span></span>||
||<span data-ttu-id="6f244-280">선택된 컨트롤이 모두 필요함</span><span class="sxs-lookup"><span data-stu-id="6f244-280">Require all the selected controls</span></span>|<span data-ttu-id="6f244-281">True</span><span class="sxs-lookup"><span data-stu-id="6f244-281">True</span></span>|<span data-ttu-id="6f244-282">선택</span><span class="sxs-lookup"><span data-stu-id="6f244-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="6f244-p115">**클릭 하**여이 정책을 사용 하도록 설정 해야 합니다. 또한 정책을 테스트할 [경우에 어떻게](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 고려</span><span class="sxs-lookup"><span data-stu-id="6f244-p115">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="6f244-285">높은 위험 수준 사용자 암호를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-285">High risk users must change password</span></span>
<span data-ttu-id="6f244-286">계정이 손상된 모든 높은 위험 사용자가 로그인할 때 암호 변경을 수행하게 하려면 다음 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-286">To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="6f244-287">에 로그인 하는 [Microsoft Azure 포털 (http://portal.azure.com) ](http://portal.azure.com/) 관리자 자격 증명으로 다음으로 이동 하 고 **Azure AD Id 보호 > 사용자 위험 정책**합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="6f244-288">**할당**</span><span class="sxs-lookup"><span data-stu-id="6f244-288">**Assignments**</span></span>

|<span data-ttu-id="6f244-289">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-289">Type</span></span>|<span data-ttu-id="6f244-290">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-290">Properties</span></span>|<span data-ttu-id="6f244-291">값</span><span class="sxs-lookup"><span data-stu-id="6f244-291">Values</span></span>|<span data-ttu-id="6f244-292">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-293">사용자</span><span class="sxs-lookup"><span data-stu-id="6f244-293">Users</span></span>|<span data-ttu-id="6f244-294">포함</span><span class="sxs-lookup"><span data-stu-id="6f244-294">Include</span></span>|<span data-ttu-id="6f244-295">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="6f244-295">All users</span></span>|<span data-ttu-id="6f244-296">선택</span><span class="sxs-lookup"><span data-stu-id="6f244-296">Selected</span></span>|
||<span data-ttu-id="6f244-297">제외</span><span class="sxs-lookup"><span data-stu-id="6f244-297">Exclude</span></span>|<span data-ttu-id="6f244-298">없음</span><span class="sxs-lookup"><span data-stu-id="6f244-298">None</span></span>||
|<span data-ttu-id="6f244-299">조건</span><span class="sxs-lookup"><span data-stu-id="6f244-299">Conditions</span></span>|<span data-ttu-id="6f244-300">사용자 위험</span><span class="sxs-lookup"><span data-stu-id="6f244-300">User risk</span></span>|<span data-ttu-id="6f244-301">높은</span><span class="sxs-lookup"><span data-stu-id="6f244-301">High</span></span>|<span data-ttu-id="6f244-302">선택</span><span class="sxs-lookup"><span data-stu-id="6f244-302">Selected</span></span>|

<span data-ttu-id="6f244-303">**컨트롤**</span><span class="sxs-lookup"><span data-stu-id="6f244-303">**Controls**</span></span>

| <span data-ttu-id="6f244-304">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-304">Type</span></span> | <span data-ttu-id="6f244-305">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-305">Properties</span></span> | <span data-ttu-id="6f244-306">값</span><span class="sxs-lookup"><span data-stu-id="6f244-306">Values</span></span>                  | <span data-ttu-id="6f244-307">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="6f244-308">액세스</span><span class="sxs-lookup"><span data-stu-id="6f244-308">Access</span></span>     | <span data-ttu-id="6f244-309">액세스 허용</span><span class="sxs-lookup"><span data-stu-id="6f244-309">Allow access</span></span>            | <span data-ttu-id="6f244-310">True</span><span class="sxs-lookup"><span data-stu-id="6f244-310">True</span></span>  |
|      | <span data-ttu-id="6f244-311">액세스</span><span class="sxs-lookup"><span data-stu-id="6f244-311">Access</span></span>     | <span data-ttu-id="6f244-312">암호 변경 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-312">Require password change</span></span> | <span data-ttu-id="6f244-313">True</span><span class="sxs-lookup"><span data-stu-id="6f244-313">True</span></span>  |

<span data-ttu-id="6f244-314">**검토:** 는 적용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6f244-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="6f244-p116">**클릭 하**여이 정책을 사용 하도록 설정 해야 합니다. 또한 정책을 테스트할 [경우에 어떻게](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 고려</span><span class="sxs-lookup"><span data-stu-id="6f244-p116">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="6f244-317">응용 프로그램 보호 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6f244-317">Define app protection policies</span></span>
<span data-ttu-id="6f244-p117">허용 되는 앱 app 보호 정책을 정의 하 고 조직 데이터에 적용할 수 있는 작업은 키를 누릅니다. Azure 포털 내에서 보호 정책을 Intune 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p117">App protection policies define which apps are allowed and the actions they can take with your organization data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="6f244-320">각 플랫폼에 대 한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="6f244-321">iOS</span><span class="sxs-lookup"><span data-stu-id="6f244-321">iOS</span></span>
- <span data-ttu-id="6f244-322">Android</span><span class="sxs-lookup"><span data-stu-id="6f244-322">Android</span></span>
- <span data-ttu-id="6f244-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f244-323">Windows 10</span></span>

<span data-ttu-id="6f244-p118">새 응용 프로그램 보호 정책을 만들려면 관리 자격 증명을 사용 하 여 Microsoft Azure 포털에 로그인 하 고 다음을 이동 **모바일 앱 > 앱 보호 정책**합니다. **정책 추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Click **Add a policy**.</span></span>

<span data-ttu-id="6f244-p119">IOS와 Android 간의 정책 옵션은 app 보호에 약간의 차이점이 있습니다. 특히 for Android는 정책 아래 있습니다. 다른 정책에 대 한 지침으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="6f244-329">앱의 권장된 목록에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="6f244-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6f244-330">PowerPoint</span></span>
- <span data-ttu-id="6f244-331">Excel</span><span class="sxs-lookup"><span data-stu-id="6f244-331">Excel</span></span>
- <span data-ttu-id="6f244-332">Word</span><span class="sxs-lookup"><span data-stu-id="6f244-332">Word</span></span>
- <span data-ttu-id="6f244-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f244-333">Microsoft Teams</span></span>
- <span data-ttu-id="6f244-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="6f244-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="6f244-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="6f244-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="6f244-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6f244-336">OneDrive</span></span>
- <span data-ttu-id="6f244-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="6f244-337">OneNote</span></span>
- <span data-ttu-id="6f244-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="6f244-338">Outlook</span></span>

<span data-ttu-id="6f244-339">다음 표에서 권장된 설정에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="6f244-340">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-340">Type</span></span>|<span data-ttu-id="6f244-341">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-341">Properties</span></span>|<span data-ttu-id="6f244-342">값</span><span class="sxs-lookup"><span data-stu-id="6f244-342">Values</span></span>|<span data-ttu-id="6f244-343">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-344">데이터 재배치</span><span class="sxs-lookup"><span data-stu-id="6f244-344">Data relocation</span></span>|<span data-ttu-id="6f244-345">Android 백업 차단</span><span class="sxs-lookup"><span data-stu-id="6f244-345">Prevent Android backup</span></span>|<span data-ttu-id="6f244-346">예</span><span class="sxs-lookup"><span data-stu-id="6f244-346">Yes</span></span>|<span data-ttu-id="6f244-347">iOS의 경우 iTunes 및 iCloud를 명시적으로 호출</span><span class="sxs-lookup"><span data-stu-id="6f244-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="6f244-348">앱이 다른 앱으로 데이터를 전송하도록 허용</span><span class="sxs-lookup"><span data-stu-id="6f244-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="6f244-349">정책 관리 앱</span><span class="sxs-lookup"><span data-stu-id="6f244-349">Policy managed apps</span></span>||
||<span data-ttu-id="6f244-350">앱에서 다른 앱의 데이터를 받을 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="6f244-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="6f244-351">정책 관리 앱</span><span class="sxs-lookup"><span data-stu-id="6f244-351">Policy managed apps</span></span>||
||<span data-ttu-id="6f244-352">"다른 이름으로 저장" 차단</span><span class="sxs-lookup"><span data-stu-id="6f244-352">Prevent "Save As"</span></span>|<span data-ttu-id="6f244-353">예</span><span class="sxs-lookup"><span data-stu-id="6f244-353">Yes</span></span>||
||<span data-ttu-id="6f244-354">회사 데이터를 저장할 수 있는 저장소 서비스 선택</span><span class="sxs-lookup"><span data-stu-id="6f244-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="6f244-355">SharePoint 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="6f244-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="6f244-356">다른 앱에서 잘라내기, 복사 및 붙여넣기 제한</span><span class="sxs-lookup"><span data-stu-id="6f244-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="6f244-357">정책에 붙여넣기와 함께 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="6f244-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="6f244-358">Managed Browser에서 표시할 수 있는 웹 콘텐츠 제한</span><span class="sxs-lookup"><span data-stu-id="6f244-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="6f244-359">아니요</span><span class="sxs-lookup"><span data-stu-id="6f244-359">No</span></span>||
||<span data-ttu-id="6f244-360">앱 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="6f244-360">Encrypt app data</span></span>|<span data-ttu-id="6f244-361">예</span><span class="sxs-lookup"><span data-stu-id="6f244-361">Yes</span></span>|<span data-ttu-id="6f244-362">iOS의 경우 옵션 선택: 장치가 잠긴 경우</span><span class="sxs-lookup"><span data-stu-id="6f244-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="6f244-363">장치를 사용할 때 app 암호화를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6f244-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="6f244-364">예</span><span class="sxs-lookup"><span data-stu-id="6f244-364">Yes</span></span>|<span data-ttu-id="6f244-365">이중 암호화 되지 않도록 하려면이 설정을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6f244-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="6f244-366">연락처 동기화 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6f244-366">Disable contacts sync</span></span>|<span data-ttu-id="6f244-367">아니요</span><span class="sxs-lookup"><span data-stu-id="6f244-367">No</span></span>||
||<span data-ttu-id="6f244-368">인쇄를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6f244-368">Disable printing</span></span>|<span data-ttu-id="6f244-369">아니요</span><span class="sxs-lookup"><span data-stu-id="6f244-369">No</span></span>||
|<span data-ttu-id="6f244-370">액세스</span><span class="sxs-lookup"><span data-stu-id="6f244-370">Access</span></span>|<span data-ttu-id="6f244-371">액세스 시 PIN 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-371">Require PIN for access</span></span>|<span data-ttu-id="6f244-372">예</span><span class="sxs-lookup"><span data-stu-id="6f244-372">Yes</span></span>||
||<span data-ttu-id="6f244-373">유형 선택</span><span class="sxs-lookup"><span data-stu-id="6f244-373">Select Type</span></span>|<span data-ttu-id="6f244-374">숫자</span><span class="sxs-lookup"><span data-stu-id="6f244-374">Numeric</span></span>||
||<span data-ttu-id="6f244-375">단순한 PIN 허용</span><span class="sxs-lookup"><span data-stu-id="6f244-375">Allow simple PIN</span></span>|<span data-ttu-id="6f244-376">아니요</span><span class="sxs-lookup"><span data-stu-id="6f244-376">No</span></span>||
||<span data-ttu-id="6f244-377">PIN 길이</span><span class="sxs-lookup"><span data-stu-id="6f244-377">PIN length</span></span>|<span data-ttu-id="6f244-378">6 </span><span class="sxs-lookup"><span data-stu-id="6f244-378">6</span></span>||
||<span data-ttu-id="6f244-379">PIN 대신 지문 허용</span><span class="sxs-lookup"><span data-stu-id="6f244-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="6f244-380">예</span><span class="sxs-lookup"><span data-stu-id="6f244-380">Yes</span></span>||
||<span data-ttu-id="6f244-381">장치 PIN 관리 되는 경우 PIN app를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6f244-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="6f244-382">예</span><span class="sxs-lookup"><span data-stu-id="6f244-382">Yes</span></span>||
||<span data-ttu-id="6f244-383">액세스에 대 한 회사 자격 증명을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-383">Require corporate credentials for access</span></span>|<span data-ttu-id="6f244-384">아니요</span><span class="sxs-lookup"><span data-stu-id="6f244-384">No</span></span>||
||<span data-ttu-id="6f244-385">액세스 요구 사항을 다시 확인할 시간(분)</span><span class="sxs-lookup"><span data-stu-id="6f244-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="6f244-386">30</span><span class="sxs-lookup"><span data-stu-id="6f244-386">30</span></span>||
||<span data-ttu-id="6f244-387">화면 캡처 및 Android Assistant 차단</span><span class="sxs-lookup"><span data-stu-id="6f244-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="6f244-388">아니요</span><span class="sxs-lookup"><span data-stu-id="6f244-388">No</span></span>|<span data-ttu-id="6f244-389">iOS의 경우 이 옵션을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6f244-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="6f244-390">로그인 보안 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f244-390">Sign-in security requirements</span></span>|<span data-ttu-id="6f244-391">최대 PIN 시도</span><span class="sxs-lookup"><span data-stu-id="6f244-391">Max PIN attempts</span></span>|<span data-ttu-id="6f244-392">5 </span><span class="sxs-lookup"><span data-stu-id="6f244-392">5</span></span>|<span data-ttu-id="6f244-393">Pin을 다시 설정</span><span class="sxs-lookup"><span data-stu-id="6f244-393">Reset Pin</span></span>|
||<span data-ttu-id="6f244-394">오프라인 유예 기간</span><span class="sxs-lookup"><span data-stu-id="6f244-394">Offline grace period</span></span>|<span data-ttu-id="6f244-395">720</span><span class="sxs-lookup"><span data-stu-id="6f244-395">720</span></span>|<span data-ttu-id="6f244-396">액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6f244-396">Block access</span></span>|
||<span data-ttu-id="6f244-397">앱 데이터가 초기화되기 전의 오프라인 간격(일)</span><span class="sxs-lookup"><span data-stu-id="6f244-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="6f244-398">90</span><span class="sxs-lookup"><span data-stu-id="6f244-398">90</span></span>|<span data-ttu-id="6f244-399">데이터를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-399">Wipe data</span></span>|
||<span data-ttu-id="6f244-400">Jailbroken/루트가 아닌 장치</span><span class="sxs-lookup"><span data-stu-id="6f244-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="6f244-401">데이터를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-401">Wipe data</span></span>|

<span data-ttu-id="6f244-p120">완료되면 반드시 “만들기"를 클릭하십시오. 위 단계를 반복하고 선택한 플랫폼(드롭다운)을 iOS로 바꿉니다. 그러면 앱 정책 두 개가 생성되므로 정책을 만든 다음 정책에 그룹을 할당하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p120">When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="6f244-405">정책을 편집 하 여 이러한 정책을 사용자에 게 할당 참조 하십시오 [만들고 app 보호 정책에 할당 하는 방법](https://docs.microsoft.com/intune/app-protection-policies)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="6f244-406">승인 된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-406">Require approved apps</span></span>
<span data-ttu-id="6f244-407">승인 된 앱을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-407">To require approved apps:</span></span>

1. <span data-ttu-id="6f244-p121">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="6f244-410">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6f244-411">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6f244-412">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="6f244-413">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="6f244-414">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="6f244-p122">**앱을 선택 합니다.** 를 선택, **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="6f244-418">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="6f244-p123">**클라이언트 응용 프로그램을 승인 필요**를 선택, **액세스 권한 부여를**선택 합니다.  여러 컨트롤에 대 한 **선택된 된 컨트롤 필요**를 선택 하 고 **선택**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p123">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="6f244-421">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-421">Click **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="6f244-422">장치 규정 준수 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6f244-422">Define device compliance policies</span></span>

<span data-ttu-id="6f244-p124">장치 규정 준수 정책에는 장치 규격으로 표시 하기 위해 준수 해야 하는 요구 사항을 정의 합니다. Azure 포털 내에서 규정 준수 정책 Intune 장치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p124">Device compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="6f244-425">각 플랫폼에 대 한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="6f244-426">Android</span><span class="sxs-lookup"><span data-stu-id="6f244-426">Android</span></span>
- <span data-ttu-id="6f244-427">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="6f244-427">Android enterprise</span></span>
- <span data-ttu-id="6f244-428">iOS</span><span class="sxs-lookup"><span data-stu-id="6f244-428">iOS</span></span>
- <span data-ttu-id="6f244-429">macOS</span><span class="sxs-lookup"><span data-stu-id="6f244-429">macOS</span></span>
- <span data-ttu-id="6f244-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="6f244-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="6f244-431">Windows 8.1 및 이상</span><span class="sxs-lookup"><span data-stu-id="6f244-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="6f244-432">Windows 10 이상</span><span class="sxs-lookup"><span data-stu-id="6f244-432">Windows 10 and later</span></span>

<span data-ttu-id="6f244-p125">장치 정책 준수를 만들려면 관리 자격 증명을 사용 하 여 Microsoft Azure 포털에 로그인 하 고 다음 이동 **Intune > 장치 준수**합니다. **정책 만들기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Click **Create policy**.</span></span>

<span data-ttu-id="6f244-435">Windows 10은 다음 설정은 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="6f244-436">**장치 상태: Windows 상태 증명 서비스 평가 규칙**</span><span class="sxs-lookup"><span data-stu-id="6f244-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="6f244-437">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-437">Properties</span></span>|<span data-ttu-id="6f244-438">값</span><span class="sxs-lookup"><span data-stu-id="6f244-438">Values</span></span>|<span data-ttu-id="6f244-439">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="6f244-440">BitLocker 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-440">Require BitLocker</span></span>|<span data-ttu-id="6f244-441">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-441">Require</span></span>||
|<span data-ttu-id="6f244-442">장치에서 사용 하도록 설정 하려면 보안 부팅 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="6f244-443">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-443">Require</span></span>||
|<span data-ttu-id="6f244-444">코드 무결성 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-444">Require code integrity</span></span>|<span data-ttu-id="6f244-445">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-445">Require</span></span>||


<span data-ttu-id="6f244-446">**장치 속성**</span><span class="sxs-lookup"><span data-stu-id="6f244-446">**Device properties**</span></span>

|<span data-ttu-id="6f244-447">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-447">Type</span></span>|<span data-ttu-id="6f244-448">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-448">Properties</span></span>|<span data-ttu-id="6f244-449">값</span><span class="sxs-lookup"><span data-stu-id="6f244-449">Values</span></span>|<span data-ttu-id="6f244-450">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-451">운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="6f244-451">Operating system version</span></span>|<span data-ttu-id="6f244-452">모두</span><span class="sxs-lookup"><span data-stu-id="6f244-452">All</span></span>|<span data-ttu-id="6f244-453">구성되지 않음</span><span class="sxs-lookup"><span data-stu-id="6f244-453">Not configured</span></span>||

<span data-ttu-id="6f244-p126">위의 모든 정책을 배포하는 것으로 간주하려면 사용자 그룹에서 이들을 대상으로 설정해야 합니다. 정책을 만들거나(저장 시) 나중에 정책 섹션에서 배포 관리를 선택하여 이 작업을 수행할 수 있습니다(추가와 같은 수준).</span><span class="sxs-lookup"><span data-stu-id="6f244-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).</span></span>

<span data-ttu-id="6f244-456">**시스템 보안**</span><span class="sxs-lookup"><span data-stu-id="6f244-456">**System security**</span></span>

|<span data-ttu-id="6f244-457">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-457">Type</span></span>|<span data-ttu-id="6f244-458">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-458">Properties</span></span>|<span data-ttu-id="6f244-459">값</span><span class="sxs-lookup"><span data-stu-id="6f244-459">Values</span></span>|<span data-ttu-id="6f244-460">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-461">암호</span><span class="sxs-lookup"><span data-stu-id="6f244-461">Password</span></span>|<span data-ttu-id="6f244-462">모바일 장치 잠금을 해제 하려면 암호 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="6f244-463">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-463">Require</span></span>||
||<span data-ttu-id="6f244-464">단순 암호</span><span class="sxs-lookup"><span data-stu-id="6f244-464">Simple passwords</span></span>|<span data-ttu-id="6f244-465">Block</span><span class="sxs-lookup"><span data-stu-id="6f244-465">Block</span></span>||
||<span data-ttu-id="6f244-466">암호 유형</span><span class="sxs-lookup"><span data-stu-id="6f244-466">Password type</span></span>|<span data-ttu-id="6f244-467">기본 장치</span><span class="sxs-lookup"><span data-stu-id="6f244-467">Device default</span></span>||
||<span data-ttu-id="6f244-468">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="6f244-468">Minimum password length</span></span>|<span data-ttu-id="6f244-469">6 </span><span class="sxs-lookup"><span data-stu-id="6f244-469">6</span></span>||
||<span data-ttu-id="6f244-470">암호를 입력 하기 전에 비활성 최대 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="6f244-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="6f244-471">15 </span><span class="sxs-lookup"><span data-stu-id="6f244-471">15</span></span>|<span data-ttu-id="6f244-p127">Android 버전 4.0 이상과이 설정이 지원 또는 KNOX 4.0 이상. IOS 장치에 대 한 iOS 8.0 및 위에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above.</span></span>|
||<span data-ttu-id="6f244-474">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="6f244-474">Password expiration (days)</span></span>|<span data-ttu-id="6f244-475">41</span><span class="sxs-lookup"><span data-stu-id="6f244-475">41</span></span>||
||<span data-ttu-id="6f244-476">재사용을 방지 하기 위해 이전 암호의 수</span><span class="sxs-lookup"><span data-stu-id="6f244-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="6f244-477">5 </span><span class="sxs-lookup"><span data-stu-id="6f244-477">5</span></span>||
||<span data-ttu-id="6f244-478">암호를 묻는 (모바일 및 Holographic) 유휴 상태에서 장치를 반환 하는 경우</span><span class="sxs-lookup"><span data-stu-id="6f244-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="6f244-479">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-479">Require</span></span>|<span data-ttu-id="6f244-480">Windows 10에 대 한 하 고 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-480">Available for Windows 10 and later.</span></span>|
|<span data-ttu-id="6f244-481">암호화</span><span class="sxs-lookup"><span data-stu-id="6f244-481">Encryption</span></span>|<span data-ttu-id="6f244-482">장치에서 데이터 저장소의 암호화</span><span class="sxs-lookup"><span data-stu-id="6f244-482">Encryption of data storage on device</span></span>|<span data-ttu-id="6f244-483">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-483">Require</span></span>||
|<span data-ttu-id="6f244-484">장치 보안</span><span class="sxs-lookup"><span data-stu-id="6f244-484">Device Security</span></span>|<span data-ttu-id="6f244-485">방화벽</span><span class="sxs-lookup"><span data-stu-id="6f244-485">Firewall</span></span>|<span data-ttu-id="6f244-486">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-486">Require</span></span>||
||<span data-ttu-id="6f244-487">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="6f244-487">Antivirus</span></span>|<span data-ttu-id="6f244-488">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-488">Require</span></span>||
||<span data-ttu-id="6f244-489">스파이웨어 방지</span><span class="sxs-lookup"><span data-stu-id="6f244-489">Antispyware</span></span>|<span data-ttu-id="6f244-490">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-490">Require</span></span>|<span data-ttu-id="6f244-491">이 설정은 Windows 보안 센터에 등록 하는 스파이웨어 방지 솔루션이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-491">This setting requires an Anti-Spyware solution registered with Windows Security Center.</span></span>|
|<span data-ttu-id="6f244-492">Defender</span><span class="sxs-lookup"><span data-stu-id="6f244-492">Defender</span></span>|<span data-ttu-id="6f244-493">Windows Defender 맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="6f244-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="6f244-494">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-494">Require</span></span>||
||<span data-ttu-id="6f244-495">Windows Defender 맬웨어 방지 최소 버전</span><span class="sxs-lookup"><span data-stu-id="6f244-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="6f244-p128">Windows 10 바탕 화면에 대해서만 지원 합니다. Microsoft는 버전 보다 최신 버전에서 뒤에 5 개를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version.</span></span>|
||<span data-ttu-id="6f244-498">Windows Defender 맬웨어 방지 서명을 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="6f244-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="6f244-499">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-499">Require</span></span>||
||<span data-ttu-id="6f244-500">끕니다</span><span class="sxs-lookup"><span data-stu-id="6f244-500">Real-time protection</span></span>|<span data-ttu-id="6f244-501">필수</span><span class="sxs-lookup"><span data-stu-id="6f244-501">Require</span></span>|<span data-ttu-id="6f244-502">Windows 10 바탕 화면에 대해서만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-502">Only supported for Windows 10 desktop.</span></span>|

<span data-ttu-id="6f244-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="6f244-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="6f244-504">유형</span><span class="sxs-lookup"><span data-stu-id="6f244-504">Type</span></span>|<span data-ttu-id="6f244-505">속성</span><span class="sxs-lookup"><span data-stu-id="6f244-505">Properties</span></span>|<span data-ttu-id="6f244-506">값</span><span class="sxs-lookup"><span data-stu-id="6f244-506">Values</span></span>|<span data-ttu-id="6f244-507">참고</span><span class="sxs-lookup"><span data-stu-id="6f244-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6f244-508">Windows Defender 고급 위협 보호 규칙</span><span class="sxs-lookup"><span data-stu-id="6f244-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="6f244-509">또는 그 컴퓨터 위험 점수 아래에서 되도록 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-509">Require the device to be at or under the machine risk score</span></span>|<span data-ttu-id="6f244-510">보통</span><span class="sxs-lookup"><span data-stu-id="6f244-510">Medium</span></span>||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="6f244-511">호환 Pc (하지만 규격이 아닙니다. 전화 및 태블릿) 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="6f244-p129">호환 Pc를 요구 하는 정책의 추가 하기 전에 Intune에 관리를 위한 장치를 등록 해야 합니다. 장치가 의도 한 사용자를 소유 하는 보증에 대 한 Intune로 장치를 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="6f244-514">호환 Pc를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="6f244-p130">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="6f244-517">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6f244-518">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6f244-519">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="6f244-520">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="6f244-521">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="6f244-p131">**앱을 선택 합니다.** 를 선택, **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="6f244-p132">호환 Pc 하지만 따르지 않는 전화와 태블릿을 요구 하려면 **조건** 및 **장치 플랫폼**을 선택 합니다. "Select 장치 플랫폼"를 선택 하 고 **Windows** 및 **macOS**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose "Select device platforms" and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="6f244-527">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="6f244-p133">**액세스 권한 부여를**선택, **규격이 것으로 표시 하는 장치 필요**를 선택 합니다.  여러 컨트롤에 대 한 **필요 선택한 모든 컨트롤**을 선택 하 고 **선택**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p133">Choose **Grant access**, select **Require device to be marked as compliant**.  For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="6f244-530">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-530">Click **Create**.</span></span>

<span data-ttu-id="6f244-p134">목표를 규격 Pc *및* 모바일 장치에 필요한 경우에 플랫폼을 선택 하지 마십시오. 이 모든 장치에 대 한 준수 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliant for all devices.</span></span> 




## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="6f244-533">준수 Pc *및* 모바일 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6f244-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="6f244-534">모든 장치에 대 한 규정 준수를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="6f244-p135">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="6f244-537">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6f244-538">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6f244-539">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="6f244-540">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="6f244-541">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="6f244-p136">**앱을 선택 합니다.** 를 선택, **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="6f244-545">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="6f244-p137">**액세스 권한 부여를**선택, **규격이 것으로 표시 하는 장치 필요**를 선택 합니다. 여러 컨트롤에 대 한 **필요 선택한 모든 컨트롤**을 선택 하 고 **선택**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="6f244-548">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-548">Click **Create**.</span></span>

<span data-ttu-id="6f244-p138">이 정책을 만들 때에 플랫폼을 선택 하지 마십시오. 호환 장치를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f244-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="6f244-551">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6f244-551">Next steps</span></span>

[<span data-ttu-id="6f244-552">메일을 보호하기 위한 정책 권장 사항에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="6f244-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)

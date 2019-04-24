---
title: 일반 id 및 장치 액세스 정책-Microsoft 365 Enterprise | Microsoft Docs
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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 9912b05c07599c5ad0c0ed7fec91ae2572bd2ead
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289340"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="6326f-103">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="6326f-103">Common identity and device access policies</span></span>
<span data-ttu-id="6326f-104">이 문서에서는 Azure AD 응용 프로그램 프록시를 통해 게시 된 온-프레미스 응용 프로그램을 포함 하 여 클라우드 서비스에 대 한 액세스를 보호 하기 위한 일반적인 권장 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="6326f-105">이 지침은 새로 프로 비전 된 환경에서 권장 정책을 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-105">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment.</span></span> <span data-ttu-id="6326f-106">별도의 랩 환경에서 이러한 정책을 설정 하면 프로덕션 전 및 프로덕션 환경에 대 한 롤아웃을 준비 하기 전에 권장 정책을 이해 하 고 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-106">Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments.</span></span> <span data-ttu-id="6326f-107">새로 프로 비전 된 환경은 클라우드 전용 환경이 나 하이브리드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-107">Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="6326f-108">정책 집합</span><span class="sxs-lookup"><span data-stu-id="6326f-108">Policy set</span></span> 

<span data-ttu-id="6326f-109">다음 다이어그램에서는 권장 되는 정책 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-109">The following diagram illustrates the recommended set of policies.</span></span> <span data-ttu-id="6326f-110">각 정책이 적용 되는 보호 계층과 정책이 pc 또는 휴대폰 및 태블릿에서 적용 되는지, 아니면 두 장치 범주 모두를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-110">It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices.</span></span> <span data-ttu-id="6326f-111">또한 이러한 정책이 구성 되는 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-111">It also indicates where these policies are configured.</span></span>

![id 및 장치 액세스 구성에 대 한 일반 정책](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="6326f-113">이 문서의 나머지 부분에서는 이러한 정책을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="6326f-114">장치가 원하는 사용자의 소유 인지 확인 하기 위해 장치를 Intune에 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-114">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> <span data-ttu-id="6326f-115">장치 준수 정책을 적용 하기 전에 장치를 Intune에 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-115">You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="6326f-116">이러한 작업을 완료 하는 데 필요한 시간을 제공 하려면이 표에 나열 된 순서 대로 기준 정책을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-116">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table.</span></span> <span data-ttu-id="6326f-117">그러나 중요 및 고도로 규제 된 보호에 대 한 MFA 정책은 언제 든 지 구현 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-117">However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="6326f-118">보호 수준</span><span class="sxs-lookup"><span data-stu-id="6326f-118">Protection level</span></span>|<span data-ttu-id="6326f-119">정책도</span><span class="sxs-lookup"><span data-stu-id="6326f-119">Policies</span></span>|<span data-ttu-id="6326f-120">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6326f-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="6326f-121">**기준은**</span><span class="sxs-lookup"><span data-stu-id="6326f-121">**Baseline**</span></span>|[<span data-ttu-id="6326f-122">로그인 위험이 *보통* 또는 *높을* 때 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="6326f-123">최신 인증을 지원 하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="6326f-124">최신 인증을 사용 하지 않는 클라이언트는 조건부 액세스 규칙을 무시할 수 있으므로 이러한 기능을 차단 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="6326f-125">높은 위험 사용자가 암호를 변경 해야 함</span><span class="sxs-lookup"><span data-stu-id="6326f-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="6326f-126">계정의 높은 위험 활동이 검색 되는 경우 로그인 시 사용자가 암호를 변경 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="6326f-127">앱 보호 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6326f-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="6326f-128">플랫폼 당 한 가지 정책 (iOS, Android, Windows)</span><span class="sxs-lookup"><span data-stu-id="6326f-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="6326f-129">승인 된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="6326f-130">휴대폰 및 태블릿에서 모바일 앱 보호를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="6326f-131">장치 준수 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6326f-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="6326f-132">각 플랫폼에 대 한 정책 1 개</span><span class="sxs-lookup"><span data-stu-id="6326f-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="6326f-133">준수 pc 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="6326f-134">Intune에서 pc 관리를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="6326f-135">**중요**</span><span class="sxs-lookup"><span data-stu-id="6326f-135">**Sensitive**</span></span>|[<span data-ttu-id="6326f-136">로그인 위험이 *낮은*경우 MFA 필요 \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="6326f-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="6326f-137">준수 pc *및* 모바일 장치 요구</span><span class="sxs-lookup"><span data-stu-id="6326f-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="6326f-138">pc 및 전화/태블릿에서 Intune 관리를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="6326f-139">**높은 규제**</span><span class="sxs-lookup"><span data-stu-id="6326f-139">**Highly regulated**</span></span>|[<span data-ttu-id="6326f-140">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="6326f-141">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6326f-141">Assigning policies to users</span></span>
<span data-ttu-id="6326f-142">정책을 구성 하기 전에 각 보호 계층에 사용 중인 Azure AD 그룹을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-142">Before configuring policies, identify the Azure AD groups you are using for each tier of protection.</span></span> <span data-ttu-id="6326f-143">일반적으로 기본 보호는 조직의 모든 사람에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-143">Typically, baseline protection applies to everybody in the organization.</span></span> <span data-ttu-id="6326f-144">기준 및 중요 보호 둘 다에 포함 된 사용자는 모든 기본 정책이 적용 되 고 중요 한 정책도 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-144">A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies.</span></span> <span data-ttu-id="6326f-145">보호는 누적 되며 가장 제한적인 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-145">Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="6326f-146">조건부 액세스 제외를 위해 Azure AD 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-146">A recommended practice is to create an Azure AD group for conditional access exclusion.</span></span> <span data-ttu-id="6326f-147">"제외" 아래의 모든 조건부 액세스 규칙에이 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-147">Add this group to all of your conditional access rules under "Exclude".</span></span> <span data-ttu-id="6326f-148">이렇게 하면 액세스 문제를 해결 하는 동안 사용자에 게 액세스 권한을 제공 하는 방법이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-148">This gives you a method to provide access to a user while you troubleshoot access issues.</span></span> <span data-ttu-id="6326f-149">이 방법은 임시 솔루션 으로만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-149">This is recommended as a temporary solution only.</span></span> <span data-ttu-id="6326f-150">이 그룹에서 변경 사항을 모니터링 하 고 제외 그룹이 의도 한 대로 사용 되 고 있는지 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="6326f-150">Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="6326f-151">다음 다이어그램에서는 사용자 할당과 제외의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![MFA 규칙에 대 한 사용자 할당 및 제외 예](../images/identity-access-policies-assignment.png)

<span data-ttu-id="6326f-153">그림에서 "최상위 비밀 프로젝트 X 팀"에는 MFA가 *항상*필요한 조건부 액세스 정책이 할당 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-153">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*.</span></span> <span data-ttu-id="6326f-154">사용자에 게 더 높은 수준의 보호를 적용할 때 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-154">Be judicious when applying higher levels of protection to users.</span></span> <span data-ttu-id="6326f-155">이 프로젝트 팀의 구성원은 고도로 규제 된 콘텐츠를 보지 않더라도 로그온 할 때마다 두 가지 유형의 인증을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-155">Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="6326f-156">이러한 권장 사항의 일부로 만들어진 모든 Azure AD 그룹은 Office 365 그룹으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-156">All Azure AD groups created as part of these recommendations must be created as Office 365 groups.</span></span> <span data-ttu-id="6326f-157">이 지침은 SharePoint에서 문서를 보호할 때 AIP(Azure Information Protection) 배포를 위해 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-157">This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Office 365 그룹을 만드는 화면 캡처](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="6326f-159">로그인 위험을 기반으로 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="6326f-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="6326f-160">mfa를 요청 하기 전에 먼저 id 보호 MFA 등록 정책을 사용 하 여 mfa에 대해 사용자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-160">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA.</span></span> <span data-ttu-id="6326f-161">사용자가 등록 되 면 로그인을 위해 MFA를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-161">After users are registered you can enforce MFA for sign-in.</span></span> <span data-ttu-id="6326f-162">[필수 구성 요소 작업](identity-access-prerequisites.md) 에는 모든 사용자를 MFA에 등록 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-162">The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="6326f-163">새 조건부 액세스 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6326f-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="6326f-164">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-164">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="6326f-165">성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-165">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="6326f-166">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6326f-167">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6326f-168">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-168">Choose **New policy**.</span></span>

![기준 CA 정책 만들기](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="6326f-170">다음 표에서는이 정책에 대해 구현 하기 위한 조건부 액세스 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="6326f-171">**할당**</span><span class="sxs-lookup"><span data-stu-id="6326f-171">**Assignments**</span></span>

|<span data-ttu-id="6326f-172">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-172">Type</span></span>|<span data-ttu-id="6326f-173">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-173">Properties</span></span>|<span data-ttu-id="6326f-174">값</span><span class="sxs-lookup"><span data-stu-id="6326f-174">Values</span></span>|<span data-ttu-id="6326f-175">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-176">사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="6326f-176">Users and groups</span></span>|<span data-ttu-id="6326f-177">포함</span><span class="sxs-lookup"><span data-stu-id="6326f-177">Include</span></span>|<span data-ttu-id="6326f-178">사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택</span><span class="sxs-lookup"><span data-stu-id="6326f-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="6326f-179">파일럿 사용자를 포함한 보안 그룹으로 시작</span><span class="sxs-lookup"><span data-stu-id="6326f-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="6326f-180">제외</span><span class="sxs-lookup"><span data-stu-id="6326f-180">Exclude</span></span>|<span data-ttu-id="6326f-181">예외 보안 그룹; 서비스 계정(앱 ID)</span><span class="sxs-lookup"><span data-stu-id="6326f-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="6326f-182">필요한 임시 기준으로 수정 된 멤버 자격</span><span class="sxs-lookup"><span data-stu-id="6326f-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="6326f-183">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="6326f-183">Cloud apps</span></span>|<span data-ttu-id="6326f-184">포함</span><span class="sxs-lookup"><span data-stu-id="6326f-184">Include</span></span>|<span data-ttu-id="6326f-185">이 규칙을 적용할 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-185">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="6326f-186">예를 들어 Office 365 Exchange Online을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-186">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="6326f-187">조건</span><span class="sxs-lookup"><span data-stu-id="6326f-187">Conditions</span></span>|<span data-ttu-id="6326f-188">구성됨</span><span class="sxs-lookup"><span data-stu-id="6326f-188">Configured</span></span>|<span data-ttu-id="6326f-189">예</span><span class="sxs-lookup"><span data-stu-id="6326f-189">Yes</span></span>|<span data-ttu-id="6326f-190">사용자 환경 및 요구에 맞게 구성</span><span class="sxs-lookup"><span data-stu-id="6326f-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="6326f-191">로그인 위험</span><span class="sxs-lookup"><span data-stu-id="6326f-191">Sign-in risk</span></span>|<span data-ttu-id="6326f-192">위험 수준</span><span class="sxs-lookup"><span data-stu-id="6326f-192">Risk level</span></span>||<span data-ttu-id="6326f-193">다음 표의 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6326f-193">See the guidance in the following table</span></span>|

<span data-ttu-id="6326f-194">**로그인 위험**</span><span class="sxs-lookup"><span data-stu-id="6326f-194">**Sign-in risk**</span></span>

<span data-ttu-id="6326f-195">대상으로 지정 하는 보호 수준에 따라 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="6326f-196">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-196">Property</span></span>|<span data-ttu-id="6326f-197">보호 수준</span><span class="sxs-lookup"><span data-stu-id="6326f-197">Level of protection</span></span>|<span data-ttu-id="6326f-198">값</span><span class="sxs-lookup"><span data-stu-id="6326f-198">Values</span></span>|<span data-ttu-id="6326f-199">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-200">위험 수준</span><span class="sxs-lookup"><span data-stu-id="6326f-200">Risk level</span></span>|<span data-ttu-id="6326f-201">기준</span><span class="sxs-lookup"><span data-stu-id="6326f-201">Baseline</span></span>|<span data-ttu-id="6326f-202">높음, 중간</span><span class="sxs-lookup"><span data-stu-id="6326f-202">High, medium</span></span>|<span data-ttu-id="6326f-203">모두 선택</span><span class="sxs-lookup"><span data-stu-id="6326f-203">Check both</span></span>|
| |<span data-ttu-id="6326f-204">중요</span><span class="sxs-lookup"><span data-stu-id="6326f-204">Sensitive</span></span>|<span data-ttu-id="6326f-205">높음, 중간, 낮음</span><span class="sxs-lookup"><span data-stu-id="6326f-205">High, medium, low</span></span>|<span data-ttu-id="6326f-206">세 항목 모두 선택</span><span class="sxs-lookup"><span data-stu-id="6326f-206">Check all three</span></span>|
| |<span data-ttu-id="6326f-207">높은 규제</span><span class="sxs-lookup"><span data-stu-id="6326f-207">Highly regulated</span></span>| |<span data-ttu-id="6326f-208">항상 MFA를 적용 하려면 모든 옵션을 선택 하지 않은 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="6326f-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="6326f-209">**액세스 제어**</span><span class="sxs-lookup"><span data-stu-id="6326f-209">**Access controls**</span></span>

|<span data-ttu-id="6326f-210">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-210">Type</span></span>|<span data-ttu-id="6326f-211">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-211">Properties</span></span>|<span data-ttu-id="6326f-212">값</span><span class="sxs-lookup"><span data-stu-id="6326f-212">Values</span></span>|<span data-ttu-id="6326f-213">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-214">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6326f-214">Grant</span></span>|<span data-ttu-id="6326f-215">액세스 허가</span><span class="sxs-lookup"><span data-stu-id="6326f-215">Grant access</span></span>|<span data-ttu-id="6326f-216">True</span><span class="sxs-lookup"><span data-stu-id="6326f-216">True</span></span>|<span data-ttu-id="6326f-217">선택됨</span><span class="sxs-lookup"><span data-stu-id="6326f-217">Selected</span></span>|
||<span data-ttu-id="6326f-218">MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-218">Require MFA</span></span>|<span data-ttu-id="6326f-219">True</span><span class="sxs-lookup"><span data-stu-id="6326f-219">True</span></span>|<span data-ttu-id="6326f-220">Check</span><span class="sxs-lookup"><span data-stu-id="6326f-220">Check</span></span>|
||<span data-ttu-id="6326f-221">장치가 호환 되는 것으로 표시 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="6326f-222">False</span><span class="sxs-lookup"><span data-stu-id="6326f-222">False</span></span>||
||<span data-ttu-id="6326f-223">하이브리드 Azure AD 가입 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="6326f-224">False</span><span class="sxs-lookup"><span data-stu-id="6326f-224">False</span></span>||
||<span data-ttu-id="6326f-225">승인 된 클라이언트 앱 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-225">Require approved client app</span></span>|<span data-ttu-id="6326f-226">False</span><span class="sxs-lookup"><span data-stu-id="6326f-226">False</span></span>||
||<span data-ttu-id="6326f-227">선택된 컨트롤이 모두 필요함</span><span class="sxs-lookup"><span data-stu-id="6326f-227">Require all the selected controls</span></span>|<span data-ttu-id="6326f-228">True</span><span class="sxs-lookup"><span data-stu-id="6326f-228">True</span></span>|<span data-ttu-id="6326f-229">선택됨</span><span class="sxs-lookup"><span data-stu-id="6326f-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="6326f-230">이 정책을 사용 하도록 설정 하려면을 선택 하 \*\*\*\* 는 것이 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-230">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="6326f-231">또한 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 정책을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-231">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="6326f-232">최신 인증을 지원 하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="6326f-233">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-233">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="6326f-234">성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-234">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="6326f-235">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6326f-236">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6326f-237">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-237">Choose **New policy**.</span></span>

<span data-ttu-id="6326f-238">다음 표에서는이 정책에 대해 구현 하기 위한 조건부 액세스 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="6326f-239">**할당**</span><span class="sxs-lookup"><span data-stu-id="6326f-239">**Assignments**</span></span>

|<span data-ttu-id="6326f-240">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-240">Type</span></span>|<span data-ttu-id="6326f-241">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-241">Properties</span></span>|<span data-ttu-id="6326f-242">값</span><span class="sxs-lookup"><span data-stu-id="6326f-242">Values</span></span>|<span data-ttu-id="6326f-243">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-244">사용자 및 그룹</span><span class="sxs-lookup"><span data-stu-id="6326f-244">Users and groups</span></span>|<span data-ttu-id="6326f-245">포함</span><span class="sxs-lookup"><span data-stu-id="6326f-245">Include</span></span>|<span data-ttu-id="6326f-246">사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택</span><span class="sxs-lookup"><span data-stu-id="6326f-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="6326f-247">파일럿 사용자를 포함한 보안 그룹으로 시작</span><span class="sxs-lookup"><span data-stu-id="6326f-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="6326f-248">제외</span><span class="sxs-lookup"><span data-stu-id="6326f-248">Exclude</span></span>|<span data-ttu-id="6326f-249">예외 보안 그룹; 서비스 계정(앱 ID)</span><span class="sxs-lookup"><span data-stu-id="6326f-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="6326f-250">필요에 따라 일시적으로 수정한 멤버 자격</span><span class="sxs-lookup"><span data-stu-id="6326f-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="6326f-251">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="6326f-251">Cloud apps</span></span>|<span data-ttu-id="6326f-252">포함</span><span class="sxs-lookup"><span data-stu-id="6326f-252">Include</span></span>|<span data-ttu-id="6326f-253">이 규칙을 적용할 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-253">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="6326f-254">예를 들어 Office 365 Exchange Online을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-254">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="6326f-255">조건</span><span class="sxs-lookup"><span data-stu-id="6326f-255">Conditions</span></span>|<span data-ttu-id="6326f-256">구성됨</span><span class="sxs-lookup"><span data-stu-id="6326f-256">Configured</span></span>|<span data-ttu-id="6326f-257">예</span><span class="sxs-lookup"><span data-stu-id="6326f-257">Yes</span></span>|<span data-ttu-id="6326f-258">클라이언트 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="6326f-258">Configure Client apps</span></span>|
|<span data-ttu-id="6326f-259">클라이언트 앱</span><span class="sxs-lookup"><span data-stu-id="6326f-259">Client apps</span></span>|<span data-ttu-id="6326f-260">구성됨</span><span class="sxs-lookup"><span data-stu-id="6326f-260">Configured</span></span>|<span data-ttu-id="6326f-261">예</span><span class="sxs-lookup"><span data-stu-id="6326f-261">Yes</span></span>|<span data-ttu-id="6326f-262">모바일 앱 및 데스크톱 클라이언트, 다른 클라이언트 (둘 다 선택)</span><span class="sxs-lookup"><span data-stu-id="6326f-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="6326f-263">**액세스 제어**</span><span class="sxs-lookup"><span data-stu-id="6326f-263">**Access controls**</span></span>

|<span data-ttu-id="6326f-264">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-264">Type</span></span>|<span data-ttu-id="6326f-265">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-265">Properties</span></span>|<span data-ttu-id="6326f-266">값</span><span class="sxs-lookup"><span data-stu-id="6326f-266">Values</span></span>|<span data-ttu-id="6326f-267">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-268">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6326f-268">Grant</span></span>|<span data-ttu-id="6326f-269">액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-269">Block access</span></span>|<span data-ttu-id="6326f-270">True</span><span class="sxs-lookup"><span data-stu-id="6326f-270">True</span></span>|<span data-ttu-id="6326f-271">선택됨</span><span class="sxs-lookup"><span data-stu-id="6326f-271">Selected</span></span>|
||<span data-ttu-id="6326f-272">MFA 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-272">Require MFA</span></span>|<span data-ttu-id="6326f-273">False</span><span class="sxs-lookup"><span data-stu-id="6326f-273">False</span></span>||
||<span data-ttu-id="6326f-274">장치가 호환 되는 것으로 표시 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="6326f-275">False</span><span class="sxs-lookup"><span data-stu-id="6326f-275">False</span></span>||
||<span data-ttu-id="6326f-276">하이브리드 Azure AD 가입 장치 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="6326f-277">False</span><span class="sxs-lookup"><span data-stu-id="6326f-277">False</span></span>||
||<span data-ttu-id="6326f-278">승인 된 클라이언트 앱 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-278">Require approved client app</span></span>|<span data-ttu-id="6326f-279">False</span><span class="sxs-lookup"><span data-stu-id="6326f-279">False</span></span>||
||<span data-ttu-id="6326f-280">선택된 컨트롤이 모두 필요함</span><span class="sxs-lookup"><span data-stu-id="6326f-280">Require all the selected controls</span></span>|<span data-ttu-id="6326f-281">True</span><span class="sxs-lookup"><span data-stu-id="6326f-281">True</span></span>|<span data-ttu-id="6326f-282">선택됨</span><span class="sxs-lookup"><span data-stu-id="6326f-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="6326f-283">이 정책을 사용 하도록 설정 하려면을 선택 하 \*\*\*\* 는 것이 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-283">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="6326f-284">또한 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 정책을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-284">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="6326f-285">높은 위험 사용자가 암호를 변경 해야 함</span><span class="sxs-lookup"><span data-stu-id="6326f-285">High risk users must change password</span></span>
<span data-ttu-id="6326f-286">로그인 할 때 모든 높은 위험 사용자의 손상 된 계정이 강제로 암호 변경을 수행 하 게 하려면 다음 정책을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="6326f-287">사용자의 관리자 자격 증명을 사용하여 [Microsoft Azure Portal(http://portal.azure.com)](http://portal.azure.com/)에 로그인한 다음 **Azure AD ID 보호 > 사용자 위험 정책**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="6326f-288">**할당**</span><span class="sxs-lookup"><span data-stu-id="6326f-288">**Assignments**</span></span>

|<span data-ttu-id="6326f-289">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-289">Type</span></span>|<span data-ttu-id="6326f-290">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-290">Properties</span></span>|<span data-ttu-id="6326f-291">값</span><span class="sxs-lookup"><span data-stu-id="6326f-291">Values</span></span>|<span data-ttu-id="6326f-292">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-293">사용자</span><span class="sxs-lookup"><span data-stu-id="6326f-293">Users</span></span>|<span data-ttu-id="6326f-294">포함</span><span class="sxs-lookup"><span data-stu-id="6326f-294">Include</span></span>|<span data-ttu-id="6326f-295">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="6326f-295">All users</span></span>|<span data-ttu-id="6326f-296">선택</span><span class="sxs-lookup"><span data-stu-id="6326f-296">Selected</span></span>|
||<span data-ttu-id="6326f-297">제외</span><span class="sxs-lookup"><span data-stu-id="6326f-297">Exclude</span></span>|<span data-ttu-id="6326f-298">없음</span><span class="sxs-lookup"><span data-stu-id="6326f-298">None</span></span>||
|<span data-ttu-id="6326f-299">조건</span><span class="sxs-lookup"><span data-stu-id="6326f-299">Conditions</span></span>|<span data-ttu-id="6326f-300">사용자 위험</span><span class="sxs-lookup"><span data-stu-id="6326f-300">User risk</span></span>|<span data-ttu-id="6326f-301">높은</span><span class="sxs-lookup"><span data-stu-id="6326f-301">High</span></span>|<span data-ttu-id="6326f-302">선택</span><span class="sxs-lookup"><span data-stu-id="6326f-302">Selected</span></span>|

<span data-ttu-id="6326f-303">**컨트롤**</span><span class="sxs-lookup"><span data-stu-id="6326f-303">**Controls**</span></span>

| <span data-ttu-id="6326f-304">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-304">Type</span></span> | <span data-ttu-id="6326f-305">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-305">Properties</span></span> | <span data-ttu-id="6326f-306">값</span><span class="sxs-lookup"><span data-stu-id="6326f-306">Values</span></span>                  | <span data-ttu-id="6326f-307">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="6326f-308">Access</span><span class="sxs-lookup"><span data-stu-id="6326f-308">Access</span></span>     | <span data-ttu-id="6326f-309">액세스 허용</span><span class="sxs-lookup"><span data-stu-id="6326f-309">Allow access</span></span>            | <span data-ttu-id="6326f-310">True</span><span class="sxs-lookup"><span data-stu-id="6326f-310">True</span></span>  |
|      | <span data-ttu-id="6326f-311">Access</span><span class="sxs-lookup"><span data-stu-id="6326f-311">Access</span></span>     | <span data-ttu-id="6326f-312">암호 변경 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-312">Require password change</span></span> | <span data-ttu-id="6326f-313">True</span><span class="sxs-lookup"><span data-stu-id="6326f-313">True</span></span>  |

<span data-ttu-id="6326f-314">**검토:** 해당 없음</span><span class="sxs-lookup"><span data-stu-id="6326f-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="6326f-315">이 정책을 사용 하도록 설정 하려면을 선택 하 \*\*\*\* 는 것이 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-315">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="6326f-316">또한 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 정책을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-316">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="6326f-317">앱 보호 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6326f-317">Define app protection policies</span></span>
<span data-ttu-id="6326f-318">앱 보호 정책은 허용 되는 앱과 조직 데이터로 수행할 수 있는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-318">App protection policies define which apps are allowed and the actions they can take with your organization's data.</span></span> <span data-ttu-id="6326f-319">Azure portal 내에서 Intune 앱 보호 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-319">Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="6326f-320">각 플랫폼에 대 한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="6326f-321">iOS</span><span class="sxs-lookup"><span data-stu-id="6326f-321">iOS</span></span>
- <span data-ttu-id="6326f-322">Android</span><span class="sxs-lookup"><span data-stu-id="6326f-322">Android</span></span>
- <span data-ttu-id="6326f-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6326f-323">Windows 10</span></span>

<span data-ttu-id="6326f-324">새 앱 보호 정책을 만들려면 관리자 자격 증명을 사용 하 여 Microsoft Azure portal에 로그인 한 다음 **모바일 앱 > 앱 보호 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-324">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**.</span></span> <span data-ttu-id="6326f-325">**정책 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-325">Choose **Add a policy**.</span></span>

<span data-ttu-id="6326f-326">iOS와 Android 간에 앱 보호 정책 옵션에 약간의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-326">There are slight differences in the app protection policy options between iOS and Android.</span></span> <span data-ttu-id="6326f-327">아래 정책은 명시적으로 Android용입니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-327">The below policy is specifically for Android.</span></span> <span data-ttu-id="6326f-328">이 방법을 사용 하 여 다른 정책에 대 한 지침을 제시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-328">Use this as a guide for your other policies.</span></span>

<span data-ttu-id="6326f-329">권장 앱 목록에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="6326f-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6326f-330">PowerPoint</span></span>
- <span data-ttu-id="6326f-331">Excel</span><span class="sxs-lookup"><span data-stu-id="6326f-331">Excel</span></span>
- <span data-ttu-id="6326f-332">Word</span><span class="sxs-lookup"><span data-stu-id="6326f-332">Word</span></span>
- <span data-ttu-id="6326f-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6326f-333">Microsoft Teams</span></span>
- <span data-ttu-id="6326f-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="6326f-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="6326f-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="6326f-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="6326f-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6326f-336">OneDrive</span></span>
- <span data-ttu-id="6326f-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="6326f-337">OneNote</span></span>
- <span data-ttu-id="6326f-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="6326f-338">Outlook</span></span>

<span data-ttu-id="6326f-339">다음 표에서는 권장 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="6326f-340">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-340">Type</span></span>|<span data-ttu-id="6326f-341">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-341">Properties</span></span>|<span data-ttu-id="6326f-342">값</span><span class="sxs-lookup"><span data-stu-id="6326f-342">Values</span></span>|<span data-ttu-id="6326f-343">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-344">데이터 재배치</span><span class="sxs-lookup"><span data-stu-id="6326f-344">Data relocation</span></span>|<span data-ttu-id="6326f-345">Android 백업 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-345">Prevent Android backup</span></span>|<span data-ttu-id="6326f-346">예</span><span class="sxs-lookup"><span data-stu-id="6326f-346">Yes</span></span>|<span data-ttu-id="6326f-347">iOS의 경우 iTunes 및 iCloud를 명시적으로 호출</span><span class="sxs-lookup"><span data-stu-id="6326f-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="6326f-348">앱이 다른 앱으로 데이터를 전송하도록 허용</span><span class="sxs-lookup"><span data-stu-id="6326f-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="6326f-349">정책 관리 앱</span><span class="sxs-lookup"><span data-stu-id="6326f-349">Policy managed apps</span></span>||
||<span data-ttu-id="6326f-350">앱에서 다른 앱의 데이터를 받을 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="6326f-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="6326f-351">정책 관리 앱</span><span class="sxs-lookup"><span data-stu-id="6326f-351">Policy managed apps</span></span>||
||<span data-ttu-id="6326f-352">"다른 이름으로 저장" 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-352">Prevent "Save As"</span></span>|<span data-ttu-id="6326f-353">예</span><span class="sxs-lookup"><span data-stu-id="6326f-353">Yes</span></span>||
||<span data-ttu-id="6326f-354">회사 데이터를 저장할 수 있는 저장소 서비스 선택</span><span class="sxs-lookup"><span data-stu-id="6326f-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="6326f-355">비즈니스용 OneDrive, SharePoint</span><span class="sxs-lookup"><span data-stu-id="6326f-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="6326f-356">다른 앱에서 잘라내기, 복사 및 붙여넣기 제한</span><span class="sxs-lookup"><span data-stu-id="6326f-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="6326f-357">붙여넣기에 정책 관리 된 앱</span><span class="sxs-lookup"><span data-stu-id="6326f-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="6326f-358">Managed Browser에서 표시할 수 있는 웹 콘텐츠 제한</span><span class="sxs-lookup"><span data-stu-id="6326f-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="6326f-359">아니요</span><span class="sxs-lookup"><span data-stu-id="6326f-359">No</span></span>||
||<span data-ttu-id="6326f-360">앱 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="6326f-360">Encrypt app data</span></span>|<span data-ttu-id="6326f-361">예</span><span class="sxs-lookup"><span data-stu-id="6326f-361">Yes</span></span>|<span data-ttu-id="6326f-362">iOS의 경우 옵션 선택: 장치가 잠긴 경우</span><span class="sxs-lookup"><span data-stu-id="6326f-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="6326f-363">장치를 사용 하도록 설정한 경우 앱 암호화 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6326f-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="6326f-364">예</span><span class="sxs-lookup"><span data-stu-id="6326f-364">Yes</span></span>|<span data-ttu-id="6326f-365">이중 암호화를 방지 하려면이 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="6326f-366">연락처 동기화 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6326f-366">Disable contacts sync</span></span>|<span data-ttu-id="6326f-367">아니요</span><span class="sxs-lookup"><span data-stu-id="6326f-367">No</span></span>||
||<span data-ttu-id="6326f-368">인쇄 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6326f-368">Disable printing</span></span>|<span data-ttu-id="6326f-369">아니요</span><span class="sxs-lookup"><span data-stu-id="6326f-369">No</span></span>||
|<span data-ttu-id="6326f-370">액세스</span><span class="sxs-lookup"><span data-stu-id="6326f-370">Access</span></span>|<span data-ttu-id="6326f-371">액세스 시 PIN 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-371">Require PIN for access</span></span>|<span data-ttu-id="6326f-372">예</span><span class="sxs-lookup"><span data-stu-id="6326f-372">Yes</span></span>||
||<span data-ttu-id="6326f-373">유형 선택</span><span class="sxs-lookup"><span data-stu-id="6326f-373">Select Type</span></span>|<span data-ttu-id="6326f-374">정수</span><span class="sxs-lookup"><span data-stu-id="6326f-374">Numeric</span></span>||
||<span data-ttu-id="6326f-375">단순한 PIN 허용</span><span class="sxs-lookup"><span data-stu-id="6326f-375">Allow simple PIN</span></span>|<span data-ttu-id="6326f-376">아니요</span><span class="sxs-lookup"><span data-stu-id="6326f-376">No</span></span>||
||<span data-ttu-id="6326f-377">PIN 길이</span><span class="sxs-lookup"><span data-stu-id="6326f-377">PIN length</span></span>|<span data-ttu-id="6326f-378">번</span><span class="sxs-lookup"><span data-stu-id="6326f-378">6</span></span>||
||<span data-ttu-id="6326f-379">PIN 대신 지문 허용</span><span class="sxs-lookup"><span data-stu-id="6326f-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="6326f-380">예</span><span class="sxs-lookup"><span data-stu-id="6326f-380">Yes</span></span>||
||<span data-ttu-id="6326f-381">장치 pin이 관리 될 때 앱 PIN 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6326f-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="6326f-382">예</span><span class="sxs-lookup"><span data-stu-id="6326f-382">Yes</span></span>||
||<span data-ttu-id="6326f-383">액세스를 위해 회사 자격 증명 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-383">Require corporate credentials for access</span></span>|<span data-ttu-id="6326f-384">아니요</span><span class="sxs-lookup"><span data-stu-id="6326f-384">No</span></span>||
||<span data-ttu-id="6326f-385">액세스 요구 사항을 다시 확인할 시간(분)</span><span class="sxs-lookup"><span data-stu-id="6326f-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="6326f-386">kb</span><span class="sxs-lookup"><span data-stu-id="6326f-386">30</span></span>||
||<span data-ttu-id="6326f-387">화면 캡처 및 Android Assistant 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="6326f-388">아니요</span><span class="sxs-lookup"><span data-stu-id="6326f-388">No</span></span>|<span data-ttu-id="6326f-389">iOS의 경우 이 옵션을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6326f-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="6326f-390">로그인 보안 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6326f-390">Sign-in security requirements</span></span>|<span data-ttu-id="6326f-391">최대 PIN 시도 횟수</span><span class="sxs-lookup"><span data-stu-id="6326f-391">Max PIN attempts</span></span>|<span data-ttu-id="6326f-392">2-5</span><span class="sxs-lookup"><span data-stu-id="6326f-392">5</span></span>|<span data-ttu-id="6326f-393">Pin 다시 설정</span><span class="sxs-lookup"><span data-stu-id="6326f-393">Reset Pin</span></span>|
||<span data-ttu-id="6326f-394">오프라인 유예 기간</span><span class="sxs-lookup"><span data-stu-id="6326f-394">Offline grace period</span></span>|<span data-ttu-id="6326f-395">720</span><span class="sxs-lookup"><span data-stu-id="6326f-395">720</span></span>|<span data-ttu-id="6326f-396">액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6326f-396">Block access</span></span>|
||<span data-ttu-id="6326f-397">앱 데이터가 초기화되기 전의 오프라인 간격(일)</span><span class="sxs-lookup"><span data-stu-id="6326f-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="6326f-398">90</span><span class="sxs-lookup"><span data-stu-id="6326f-398">90</span></span>|<span data-ttu-id="6326f-399">데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="6326f-399">Wipe data</span></span>|
||<span data-ttu-id="6326f-400">탈 옥/루 팅 된 장치</span><span class="sxs-lookup"><span data-stu-id="6326f-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="6326f-401">데이터 지우기</span><span class="sxs-lookup"><span data-stu-id="6326f-401">Wipe data</span></span>|

<span data-ttu-id="6326f-402">완료 되 면 "만들기"를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-402">When complete, remember to select "Create".</span></span> <span data-ttu-id="6326f-403">위 단계를 반복하고 선택한 플랫폼(드롭다운)을 iOS로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-403">Repeat the above steps and replace the selected platform (dropdown) with iOS.</span></span> <span data-ttu-id="6326f-404">그러면 앱 정책 두 개가 생성되므로 정책을 만든 다음 정책에 그룹을 할당하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-404">This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="6326f-405">정책을 편집 하 고 사용자에 게 이러한 정책을 할당 하려면 [How to create and assign app protection 정책도](https://docs.microsoft.com/intune/app-protection-policies)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6326f-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="6326f-406">승인 된 앱 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-406">Require approved apps</span></span>
<span data-ttu-id="6326f-407">승인 된 앱을 요청 하려면:</span><span class="sxs-lookup"><span data-stu-id="6326f-407">To require approved apps:</span></span>

1. <span data-ttu-id="6326f-408">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-408">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="6326f-409">성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-409">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="6326f-410">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6326f-411">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6326f-412">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="6326f-413">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="6326f-414">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="6326f-415">**앱 선택을**선택 하 고 **클라우드 앱** 목록에서 원하는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-415">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="6326f-416">예를 들어 Office 365 Exchange Online을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-416">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="6326f-417">**선택** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-417">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="6326f-418">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="6326f-419">**액세스 부여**를 선택 하 고 **승인 된 클라이언트 앱 필요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-419">Choose **Grant access**, select **Require approved client app**.</span></span> <span data-ttu-id="6326f-420">여러 컨트롤에 대해 **선택한 컨트롤 필요**를 선택한 다음 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-420">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="6326f-421">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="6326f-422">장치 준수 정책 정의</span><span class="sxs-lookup"><span data-stu-id="6326f-422">Define device-compliance policies</span></span>

<span data-ttu-id="6326f-423">장치 준수 정책은 장치가 준수로 표시 되기 위해 준수 해야 하는 요구 사항을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-423">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant.</span></span> <span data-ttu-id="6326f-424">Azure portal 내에서 Intune 장치 준수 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-424">Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="6326f-425">각 플랫폼에 대 한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="6326f-426">Android</span><span class="sxs-lookup"><span data-stu-id="6326f-426">Android</span></span>
- <span data-ttu-id="6326f-427">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="6326f-427">Android enterprise</span></span>
- <span data-ttu-id="6326f-428">iOS</span><span class="sxs-lookup"><span data-stu-id="6326f-428">iOS</span></span>
- <span data-ttu-id="6326f-429">macOS</span><span class="sxs-lookup"><span data-stu-id="6326f-429">macOS</span></span>
- <span data-ttu-id="6326f-430">이 설정은 다음과 같은 유형의 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="6326f-431">Windows 8.1 이상</span><span class="sxs-lookup"><span data-stu-id="6326f-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="6326f-432">Windows 10 이상</span><span class="sxs-lookup"><span data-stu-id="6326f-432">Windows 10 and later</span></span>

<span data-ttu-id="6326f-433">장치 준수 정책을 만들려면 관리자 자격 증명을 사용 하 여 Microsoft Azure portal에 로그인 한 다음 **Intune > 장치 준수**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-433">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**.</span></span> <span data-ttu-id="6326f-434">**정책 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-434">Select **Create policy**.</span></span>

<span data-ttu-id="6326f-435">다음은 Windows 10에 권장 되는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="6326f-436">**장치 상태: Windows 상태 증명 서비스 평가 규칙**</span><span class="sxs-lookup"><span data-stu-id="6326f-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="6326f-437">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-437">Properties</span></span>|<span data-ttu-id="6326f-438">값</span><span class="sxs-lookup"><span data-stu-id="6326f-438">Values</span></span>|<span data-ttu-id="6326f-439">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="6326f-440">BitLocker 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-440">Require BitLocker</span></span>|<span data-ttu-id="6326f-441">할</span><span class="sxs-lookup"><span data-stu-id="6326f-441">Require</span></span>||
|<span data-ttu-id="6326f-442">장치에서 보안 부팅이 사용 되도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="6326f-443">할</span><span class="sxs-lookup"><span data-stu-id="6326f-443">Require</span></span>||
|<span data-ttu-id="6326f-444">코드 무결성 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-444">Require code integrity</span></span>|<span data-ttu-id="6326f-445">할</span><span class="sxs-lookup"><span data-stu-id="6326f-445">Require</span></span>||


<span data-ttu-id="6326f-446">**장치 속성**</span><span class="sxs-lookup"><span data-stu-id="6326f-446">**Device properties**</span></span>

|<span data-ttu-id="6326f-447">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-447">Type</span></span>|<span data-ttu-id="6326f-448">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-448">Properties</span></span>|<span data-ttu-id="6326f-449">값</span><span class="sxs-lookup"><span data-stu-id="6326f-449">Values</span></span>|<span data-ttu-id="6326f-450">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-451">운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="6326f-451">Operating system version</span></span>|<span data-ttu-id="6326f-452">모두</span><span class="sxs-lookup"><span data-stu-id="6326f-452">All</span></span>|<span data-ttu-id="6326f-453">구성되지 않음</span><span class="sxs-lookup"><span data-stu-id="6326f-453">Not configured</span></span>||

<span data-ttu-id="6326f-454">위의 모든 정책을 배포하는 것으로 간주하려면 사용자 그룹에서 이들을 대상으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-454">For all the above policies to be considered deployed, they must be targeted at user groups.</span></span> <span data-ttu-id="6326f-455">이 작업은 저장 시 또는 나중에 **정책** 섹션 (추가와 같은 수준)에서 **배포 관리** 를 선택 하 여 정책을 만들어 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-455">You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="6326f-456">**시스템 보안**</span><span class="sxs-lookup"><span data-stu-id="6326f-456">**System security**</span></span>

|<span data-ttu-id="6326f-457">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-457">Type</span></span>|<span data-ttu-id="6326f-458">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-458">Properties</span></span>|<span data-ttu-id="6326f-459">값</span><span class="sxs-lookup"><span data-stu-id="6326f-459">Values</span></span>|<span data-ttu-id="6326f-460">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-461">암호</span><span class="sxs-lookup"><span data-stu-id="6326f-461">Password</span></span>|<span data-ttu-id="6326f-462">모바일 장치의 잠금을 해제 하는 데 암호 필요</span><span class="sxs-lookup"><span data-stu-id="6326f-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="6326f-463">할</span><span class="sxs-lookup"><span data-stu-id="6326f-463">Require</span></span>||
||<span data-ttu-id="6326f-464">단순 암호</span><span class="sxs-lookup"><span data-stu-id="6326f-464">Simple passwords</span></span>|<span data-ttu-id="6326f-465">정책의</span><span class="sxs-lookup"><span data-stu-id="6326f-465">Block</span></span>||
||<span data-ttu-id="6326f-466">암호 유형</span><span class="sxs-lookup"><span data-stu-id="6326f-466">Password type</span></span>|<span data-ttu-id="6326f-467">장치 기본값</span><span class="sxs-lookup"><span data-stu-id="6326f-467">Device default</span></span>||
||<span data-ttu-id="6326f-468">최소 암호 길이</span><span class="sxs-lookup"><span data-stu-id="6326f-468">Minimum password length</span></span>|<span data-ttu-id="6326f-469">번</span><span class="sxs-lookup"><span data-stu-id="6326f-469">6</span></span>||
||<span data-ttu-id="6326f-470">암호를 요구 하기 전까지 최대 비활성 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="6326f-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="6326f-471">15 </span><span class="sxs-lookup"><span data-stu-id="6326f-471">15</span></span>|<span data-ttu-id="6326f-472">이 설정은 Android 버전 4.0 이상 또는 KNOX 4.0 이상에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-472">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above.</span></span> <span data-ttu-id="6326f-473">ios 장치에서는 ios 8.0 이상에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-473">For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="6326f-474">암호 만료(일)</span><span class="sxs-lookup"><span data-stu-id="6326f-474">Password expiration (days)</span></span>|<span data-ttu-id="6326f-475">41</span><span class="sxs-lookup"><span data-stu-id="6326f-475">41</span></span>||
||<span data-ttu-id="6326f-476">다시 사용 하지 못하도록 할 이전 암호 수</span><span class="sxs-lookup"><span data-stu-id="6326f-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="6326f-477">2-5</span><span class="sxs-lookup"><span data-stu-id="6326f-477">5</span></span>||
||<span data-ttu-id="6326f-478">장치가 유휴 상태에서 반환 될 때 암호 필요 (Mobile 및 Holographic)</span><span class="sxs-lookup"><span data-stu-id="6326f-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="6326f-479">할</span><span class="sxs-lookup"><span data-stu-id="6326f-479">Require</span></span>|<span data-ttu-id="6326f-480">Windows 10 이상 버전에서 사용 가능</span><span class="sxs-lookup"><span data-stu-id="6326f-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="6326f-481">암호화</span><span class="sxs-lookup"><span data-stu-id="6326f-481">Encryption</span></span>|<span data-ttu-id="6326f-482">장치에서 데이터 저장소 암호화</span><span class="sxs-lookup"><span data-stu-id="6326f-482">Encryption of data storage on device</span></span>|<span data-ttu-id="6326f-483">할</span><span class="sxs-lookup"><span data-stu-id="6326f-483">Require</span></span>||
|<span data-ttu-id="6326f-484">장치 보안</span><span class="sxs-lookup"><span data-stu-id="6326f-484">Device Security</span></span>|<span data-ttu-id="6326f-485">방화벽이</span><span class="sxs-lookup"><span data-stu-id="6326f-485">Firewall</span></span>|<span data-ttu-id="6326f-486">할</span><span class="sxs-lookup"><span data-stu-id="6326f-486">Require</span></span>||
||<span data-ttu-id="6326f-487">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="6326f-487">Antivirus</span></span>|<span data-ttu-id="6326f-488">할</span><span class="sxs-lookup"><span data-stu-id="6326f-488">Require</span></span>||
||<span data-ttu-id="6326f-489">백신</span><span class="sxs-lookup"><span data-stu-id="6326f-489">Antispyware</span></span>|<span data-ttu-id="6326f-490">할</span><span class="sxs-lookup"><span data-stu-id="6326f-490">Require</span></span>|<span data-ttu-id="6326f-491">이 설정을 사용 하려면 Windows 보안 센터에 등록 된 스파이웨어 방지 솔루션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="6326f-492">Defender</span><span class="sxs-lookup"><span data-stu-id="6326f-492">Defender</span></span>|<span data-ttu-id="6326f-493">Windows Defender 맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="6326f-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="6326f-494">할</span><span class="sxs-lookup"><span data-stu-id="6326f-494">Require</span></span>||
||<span data-ttu-id="6326f-495">Windows Defender 맬웨어 방지 최소 버전</span><span class="sxs-lookup"><span data-stu-id="6326f-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="6326f-496">Windows 10 desktop에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-496">Only supported for Windows 10 desktop.</span></span> <span data-ttu-id="6326f-497">최신 버전에서 5 개 이하의 버전을 포함 하는 Microsoft 권장</span><span class="sxs-lookup"><span data-stu-id="6326f-497">Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="6326f-498">Windows Defender 맬웨어 방지 서명이 최신 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="6326f-499">할</span><span class="sxs-lookup"><span data-stu-id="6326f-499">Require</span></span>||
||<span data-ttu-id="6326f-500">실시간 보호</span><span class="sxs-lookup"><span data-stu-id="6326f-500">Real-time protection</span></span>|<span data-ttu-id="6326f-501">할</span><span class="sxs-lookup"><span data-stu-id="6326f-501">Require</span></span>|<span data-ttu-id="6326f-502">Windows 10 desktop에만 지원 됨</span><span class="sxs-lookup"><span data-stu-id="6326f-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="6326f-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="6326f-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="6326f-504">유형</span><span class="sxs-lookup"><span data-stu-id="6326f-504">Type</span></span>|<span data-ttu-id="6326f-505">속성</span><span class="sxs-lookup"><span data-stu-id="6326f-505">Properties</span></span>|<span data-ttu-id="6326f-506">값</span><span class="sxs-lookup"><span data-stu-id="6326f-506">Values</span></span>|<span data-ttu-id="6326f-507">참고</span><span class="sxs-lookup"><span data-stu-id="6326f-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="6326f-508">Windows Defender Advanced Threat Protection 규칙</span><span class="sxs-lookup"><span data-stu-id="6326f-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="6326f-509">장치가 컴퓨터 위험 점수에 있거나 그 아래에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="6326f-510">보통</span><span class="sxs-lookup"><span data-stu-id="6326f-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="6326f-511">준수 pc 필요 (준수 전화 및 태블릿 제외)</span><span class="sxs-lookup"><span data-stu-id="6326f-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="6326f-512">준수 pc를 요구 하는 정책을 추가 하기 전에 관리를 위한 장치를 Intune에 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-512">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune.</span></span> <span data-ttu-id="6326f-513">장치가 원하는 사용자의 소유 인지 확인 하기 위해 장치를 Intune에 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-513">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="6326f-514">준수 pc를 요구 하려면:</span><span class="sxs-lookup"><span data-stu-id="6326f-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="6326f-515">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-515">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="6326f-516">성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-516">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="6326f-517">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6326f-518">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6326f-519">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="6326f-520">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="6326f-521">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="6326f-522">**앱 선택을**선택 하 고 **클라우드 앱** 목록에서 원하는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-522">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="6326f-523">예를 들어 Office 365 Exchange Online을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-523">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="6326f-524">**선택** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-524">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="6326f-525">준수 pc를 요구 하 되, 호환 되는 휴대폰 및 태블릿은 제외 하려면 **조건** 및 **장치 플랫폼**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-525">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**.</span></span> <span data-ttu-id="6326f-526">**장치 플랫폼 선택을** 선택 하 고 **Windows** 및 **macos**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-526">Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="6326f-527">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="6326f-528">**액세스 권한 부여**를 선택 하 고 **준수 하도록 표시할 장치 필요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-528">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="6326f-529">여러 컨트롤의 경우 **선택한 모든 컨트롤 필요**를 선택한 다음 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-529">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="6326f-530">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-530">Choose **Create**.</span></span>

<span data-ttu-id="6326f-531">준수 pc *와* 모바일 장치를 요구 하는 목표 인 경우 플랫폼을 선택 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6326f-531">If your objective is to require compliant PCs *and* mobile devices, do not select platforms.</span></span> <span data-ttu-id="6326f-532">이렇게 하면 모든 장치에 대 한 준수가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-532">This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="6326f-533">준수 pc *및* 모바일 장치 요구</span><span class="sxs-lookup"><span data-stu-id="6326f-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="6326f-534">모든 장치에 대 한 준수를 요구 하려면:</span><span class="sxs-lookup"><span data-stu-id="6326f-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="6326f-535">[Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-535">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="6326f-536">성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-536">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="6326f-537">왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="6326f-538">**보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="6326f-539">**새 정책**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="6326f-540">정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="6326f-541">**클라우드 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="6326f-542">**앱 선택을**선택 하 고 **클라우드 앱** 목록에서 원하는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-542">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="6326f-543">예를 들어 Office 365 Exchange Online을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-543">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="6326f-544">**선택** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-544">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="6326f-545">**액세스 제어** 섹션에서 **권한 부여**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="6326f-546">**액세스 권한 부여**를 선택 하 고 **준수 하도록 표시할 장치 필요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-546">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="6326f-547">여러 컨트롤의 경우 **선택한 모든 컨트롤 필요**를 선택한 다음 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-547">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="6326f-548">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-548">Choose **Create**.</span></span>

<span data-ttu-id="6326f-549">이 정책을 만들 때 플랫폼을 선택 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6326f-549">When creating this policy, do not select platforms.</span></span> <span data-ttu-id="6326f-550">이렇게 하면 호환 되는 장치가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6326f-550">This enforces compliant devices.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6326f-551">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6326f-551">Next steps</span></span>

[<span data-ttu-id="6326f-552">메일을 보호하기 위한 정책 권장 사항에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="6326f-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)

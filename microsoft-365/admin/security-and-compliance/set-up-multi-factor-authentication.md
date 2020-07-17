---
title: 사용자에 대한 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 조직에 대한 다단계 인증을 설정하는 방법에 대해 알아 보십시오.
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083541"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="00f59-103">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="00f59-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="00f59-104">[다단계 인증(MFA)에 대한 이해와 Microsoft 365](multi-factor-authentication-microsoft-365.md)에서의 지원을 바탕으로, 이제 이를 설정하고 조직에 롤아웃할 시기입니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="00f59-105">시작하기 전에 다음과 같은 특수 조건이 자신에게 적용되는지 확인하고 적절한 조치를 취하십시오.</span><span class="sxs-lookup"><span data-stu-id="00f59-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="00f59-106">Windows 디바이스에 Office 2013 클라이언트가 있는 경우 [최신 인증](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="00f59-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="00f59-107">AD FS(Active Directory Federation Services)를 사용하는 타사 디렉터리 서비스가 있는 경우 Azure MFA 서버를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="00f59-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="00f59-108">자세한 내용은 [Azure 다단계 인증 및 타사 VPN 솔루션을 사용한  고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00f59-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="00f59-109">필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="00f59-110">자세한 내용은 [2단계 인증 방법 및 설정](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)을 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="00f59-111">1단계: 사용자에게 MFA를 사용하도록 요구하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="00f59-112">MFA를 설정하거나 수정하려면 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="00f59-113">사용자가 로그인하기 위해 MFA를 사용하도록 요구하는 세 가지 방법이 있습니다. 자세한 내용은 [Microsoft 365의 MFA 지원](multi-factor-authentication-microsoft-365.md)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="00f59-114">보안 기본값(소규모 기업에 권장)입니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="00f59-115">2019년 10월 21일 이후에 구독 또는 평가판을 구입한 경우 예기치 않게 MFA 메시지가 표시되면 [보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)이 구독에 대해 자동으로 사용되도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="00f59-116">모든 새 Microsoft 365 제품에는 보안 기본값이 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="00f59-117">즉, 모든 사용자는 MFA를 설정하고 모바일 장치에 Microsoft 인증자 앱을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="00f59-118">추가 확인 방법 및 레거시 인증이 차단되므로 모든 사용자는 Microsoft 인증자 앱을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="00f59-119">조건부 액세스 정책(기업용으로 권장)</span><span class="sxs-lookup"><span data-stu-id="00f59-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="00f59-120">사용자는 MFA 등록 시 추가 확인 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="00f59-121">사용자별 계정(권장하지 않음)</span><span class="sxs-lookup"><span data-stu-id="00f59-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="00f59-122">사용자는 MFA 등록 시 추가 확인 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="00f59-123">2단계.</span><span class="sxs-lookup"><span data-stu-id="00f59-123">Step 2.</span></span> <span data-ttu-id="00f59-124">파일럿 사용자를 대상으로 MFA를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="00f59-125">조건부 액세스 정책 또는 사용자별 MFA(권장하지 않음)를 사용하는 경우 기업 또는 조직의 파일럿 사용자를 선택하여 MFA 등록 및 로그인을 테스트합니다. 예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="00f59-126">조건부 액세스 정책의 경우 그룹 구성원과 모든 앱에 대해 MFA가 필요한 정책 및 파일럿 사용자 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="00f59-127">그런 다음 파일럿 사용자의 계정을 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="00f59-128">사용자별 MFA의 경우 파일럿 사용자의 사용자 계정에 대해 한 번에 한 번씩 MFA를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="00f59-129">파일럿 사용자와 함께 질문 및 문제를 해결하여 조직에 원활한 롤아웃을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="00f59-130">3단계</span><span class="sxs-lookup"><span data-stu-id="00f59-130">Step 3.</span></span> <span data-ttu-id="00f59-131">MFA가 곧 시행될 것임을 조직에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="00f59-132">전자 메일 알림, 복도 포스터, 팀 회의 또는 공식 교육을 통해 직원들이 다음을 이해할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="00f59-133">로그인 시 MFA가 필요한 이유</span><span class="sxs-lookup"><span data-stu-id="00f59-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="00f59-134">추가 확인 방법을 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="00f59-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="00f59-135">등록 후 로그인하는 방법</span><span class="sxs-lookup"><span data-stu-id="00f59-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="00f59-136">추가 확인 방법을 변경하는 방법</span><span class="sxs-lookup"><span data-stu-id="00f59-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="00f59-137">새 스마트폰과 같은 상황에 대처하는 방법</span><span class="sxs-lookup"><span data-stu-id="00f59-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="00f59-138">가장 중요한 것은 ***MFA 요구 사항이 부과될 때*** 직원이 놀라지 않도록 직원들에게 이를 이해하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="00f59-139">4단계</span><span class="sxs-lookup"><span data-stu-id="00f59-139">Step 4.</span></span> <span data-ttu-id="00f59-140">조직 또는 사용자에게 MFA 요구사항을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="00f59-141">선택한 MFA 요구 사항 방법에 따라 파일럿 테스터 이외의 직원에게 MFA 인증을 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="00f59-142">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="00f59-142">Security defaults</span></span>

<span data-ttu-id="00f59-143">Azure 포털의 Azure Active Directory(Azure AD)에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="00f59-144">전역  관리자 자격 증명으로 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="00f59-145">[Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="00f59-146">페이지 하단에서 **보안 기본값 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="00f59-147">보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택한 다음 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="00f59-148">[기준 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)을 사용해 온 경우 보안 기본값을 사용하여 이동하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="00f59-149">[조건 액세스 - 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="00f59-150">**켜짐** 상태인 각 기준선 정책을 선택하고 **정책 사용**을 **끔**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="00f59-151">[Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="00f59-152">페이지 하단에서 **보안 기본값 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="00f59-153">보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택한 다음 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="00f59-154">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="00f59-154">Conditional Access policies</span></span>

<span data-ttu-id="00f59-155">로그인을 위해 MFA가 필요한 사용자 그룹을 포함하는 적절한 정책을 만들고 구성하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="00f59-156">사용자별 MFA(권장하지 않음)</span><span class="sxs-lookup"><span data-stu-id="00f59-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="00f59-157">롤아웃에 해당하는 MFA에 대해 사용자 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="00f59-158">직원 지원</span><span class="sxs-lookup"><span data-stu-id="00f59-158">Supporting your employees</span></span>

<span data-ttu-id="00f59-159">직원이 MFA에 등록하고 로그인하기 시작할 때 IT 전문가, IT 부서 또는 헬프데스크에서 질문에 신속하게 답변하고 문제를 해결할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="00f59-160">[MFA 로그인 문제 해결에 대한 정보](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)를 확인하려면 이 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="00f59-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 



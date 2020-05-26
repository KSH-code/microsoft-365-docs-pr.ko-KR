---
title: 사용자를 위한 대한 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
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
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 조직에 대해 multi-factor authentication을 설정 하는 방법을 알아봅니다.
monikerRange: o365-worldwide
ms.openlocfilehash: ca1a8bd47e2fa5bbd7b7aed396debefaad10ea5e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351718"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="61893-103">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="61893-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="61893-104">[Microsoft 365에서 MFA (multi-factor authentication) 및 해당 지원](multi-factor-authentication-microsoft-365.md)에 대 한 이해를 바탕으로이를 설정 하 고 조직에 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61893-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="61893-105">시작 하기 전에 이러한 특수 조건이 사용자에 게 적용 되는지 확인 하 고 적절 한 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="61893-106">Windows 장치에 Office 2013 클라이언트가 있는 경우 [최신 인증을 사용 하도록 설정](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="61893-107">AD FS (Active Directory Federation Services)와 타사 디렉터리 서비스를 사용 하는 경우에는 Azure MFA 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="61893-108">자세한 내용은 [Azure Multi-factor Authentication 및 타사 VPN 솔루션의 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61893-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="61893-109">1 단계: 사용자에 게 MFA를 사용 하도록 요구 하는 방법 결정</span><span class="sxs-lookup"><span data-stu-id="61893-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="61893-110">사용자가 로그인을 위해 MFA를 사용 하도록 요구 하는 방법에는 세 가지가 있습니다. 자세한 내용은 [Microsoft 365에서 MFA 지원를](multi-factor-authentication-microsoft-365.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61893-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="61893-111">보안 기본값 (small 비즈니스에 대해 권장)</span><span class="sxs-lookup"><span data-stu-id="61893-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="61893-112">2019 년 10 월 21 일 이후에 구독 또는 평가판을 구매한 경우 MFA를 예기치 않게 묻는 메시지가 표시 되 면 구독에 대해 [보안 기본값이](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 자동으로 사용 하도록 설정 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61893-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="61893-113">모든 새 Microsoft 365 구독에는 자동으로 보안 기본값이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61893-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="61893-114">즉, 모든 사용자가 자신의 모바일 장치에 MFA를 설정 하 고 Microsoft Authenticator 앱을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="61893-115">모든 사용자는 Microsoft Authenticator 앱을 추가 확인 방법으로 사용 해야 하며 레거시 인증은 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61893-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="61893-116">조건부 액세스 정책 (엔터프라이즈에 대해 권장)</span><span class="sxs-lookup"><span data-stu-id="61893-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="61893-117">사용자는 MFA 등록 중에 추가 확인 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="61893-118">사용자별 계정 (권장 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="61893-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="61893-119">사용자는 MFA 등록 중에 추가 확인 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="61893-120">2단계.</span><span class="sxs-lookup"><span data-stu-id="61893-120">Step 2.</span></span> <span data-ttu-id="61893-121">파일럿 사용자에 대해 MFA 테스트</span><span class="sxs-lookup"><span data-stu-id="61893-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="61893-122">조건부 액세스 정책 또는 사용자별 MFA (권장 하지 않음)를 사용 하는 경우에는 회사나 조직의 파일럿 사용자를 선택 하 여 MFA 등록 및 로그인을 테스트 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="61893-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="61893-123">조건부 액세스 정책에 대해 파일럿 사용자 그룹 및 그룹 구성원과 모든 앱에 대해 MFA를 요구 하는 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61893-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="61893-124">그런 다음 파일럿 사용자 계정을 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="61893-125">사용자 단위 MFA의 경우 파일럿 사용자의 사용자 계정에 대해 한 번에 하나씩 MFA를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="61893-126">파일럿 사용자와 협력 하 여 조직의 원활한 롤아웃을 준비할 수 있도록 질문과 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="61893-127">3단계.</span><span class="sxs-lookup"><span data-stu-id="61893-127">Step 3.</span></span> <span data-ttu-id="61893-128">사용자에 게 MFA가 출시 되었음을 조직에 알리기</span><span class="sxs-lookup"><span data-stu-id="61893-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="61893-129">다음과 같이 직원 들이 이해할 수 있도록 전자 메일 알림, hallway 포스터, 팀 회의 또는 공식적인 교육을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="61893-130">로그인에 MFA가 필요한 이유</span><span class="sxs-lookup"><span data-stu-id="61893-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="61893-131">추가 확인 방법에 등록 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61893-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="61893-132">등록 후 로그인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61893-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="61893-133">추가 확인 방법을 변경 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61893-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="61893-134">새 smart 전화와 같은 상황을 처리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61893-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="61893-135">가장 중요 한 점은 ***MFA 요구 사항을*** 예기치 않게 설정 하는 경우 직원이이를 이해 하 고 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61893-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="61893-136">4단계.</span><span class="sxs-lookup"><span data-stu-id="61893-136">Step 4.</span></span> <span data-ttu-id="61893-137">조직 또는 사용자에 게 MFA 요구 사항 롤아웃</span><span class="sxs-lookup"><span data-stu-id="61893-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="61893-138">선택한 MFA 요구 사항 방법을 기반으로 파일럿 테스터가 아닌 직원에 게 MFA 인증을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="61893-139">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="61893-139">Security defaults</span></span>

<span data-ttu-id="61893-140">Azure portal의 azure Active Directory (Azure AD)에 대 한 **속성** 창에서 보안 기본값을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="61893-141">전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="61893-142">[Azure Active Directory-속성 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="61893-143">페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="61893-144">보안 기본값을 사용 하려면 **예** 를 선택 하 고 보안 기본값을 사용 하지 않으려면 **아니요** 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="61893-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="61893-145">[기준 조건부 액세스 정책을](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)사용 하 고 있는 경우 보안 기본값을 사용 하 여 이동 하는 방법이 여기에 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61893-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="61893-146">[조건부 액세스-정책 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="61893-147">설정 된 각 기본 정책을 선택 **하 고** **정책 사용** 을 **해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="61893-148">[Azure Active Directory-속성 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="61893-149">페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="61893-150">보안 기본값을 사용 하려면 **예** 를 선택 하 고 보안 기본값을 사용 하지 않으려면 **아니요** 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="61893-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="61893-151">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="61893-151">Conditional Access policies</span></span>

<span data-ttu-id="61893-152">로그인을 위해 MFA를 필요로 하는 사용자 그룹을 포함 하는 적절 한 정책을 만들고 구성 하 고 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="61893-153">사용자별 MFA (권장 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="61893-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="61893-154">롤아웃에 해당 하는 MFA에 대해 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="61893-155">직원 지원</span><span class="sxs-lookup"><span data-stu-id="61893-155">Supporting your employees</span></span>

<span data-ttu-id="61893-156">직원이 MFA에 등록 하 고 로그인을 시작할 때 IT 전문가, IT 부서 또는 지원 자가 질문에 답하고 문제를 빠르게 해결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="61893-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="61893-157">[MFA 로그인 문제 해결에 대 한 자세한 내용은](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)이 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61893-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 



---
title: Office 365 사용자에 대해 다단계 인증 설정
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
description: 보안 기본값을 사용하여 Office 365 사용자의 다단계 인증을 설정하는 방법을 알아봅니다.
monikerRange: o365-worldwide
ms.openlocfilehash: 4dc52c25c3a9351be1a9f4d094d664bc4ed527f9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361049"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="f744f-103">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="f744f-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="f744f-104">모든 새 비즈니스용 Office 365 또는 Microsoft 365 Business 구독에는 자동으로 보안 기본값이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="f744f-105">즉, 모든 사용자는 MFA(다단계 인증)를 설정하고 모바일 장치에 인증자 앱을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="f744f-106">자세한 내용은 [Office 365에 대해 2단계 인증 설정](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f744f-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="f744f-107">다음 9개의 관리자 역할은 로그인할 때마다 추가 인증을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="f744f-108">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-108">Global administrator</span></span>
- <span data-ttu-id="f744f-109">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-109">SharePoint administrator</span></span>
- <span data-ttu-id="f744f-110">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-110">Exchange administrator</span></span>
- <span data-ttu-id="f744f-111">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-111">Conditional Access administrator</span></span>
- <span data-ttu-id="f744f-112">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-112">Security administrator</span></span>
- <span data-ttu-id="f744f-113">헬프데스크 관리자 또는 암호 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="f744f-114">청구 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-114">Billing administrator</span></span>
- <span data-ttu-id="f744f-115">사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-115">User administrator</span></span>
- <span data-ttu-id="f744f-116">인증 관리자</span><span class="sxs-lookup"><span data-stu-id="f744f-116">Authentication administrator</span></span>

<span data-ttu-id="f744f-117">필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="f744f-118">자세한 내용은 [보안 기본값이란?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f744f-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="f744f-p103">다단계 인증을 설정하거나 수정하려면 Office 365 전역 관리자이어야 합니다. </span><span class="sxs-lookup"><span data-stu-id="f744f-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="f744f-120">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="f744f-121">이전에 기본 정책을 사용 하여 MFA를 설정한 경우 [ 이를 해제하고 보안 기본값](#move-from-baseline-policies-to-security-defaults)을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="f744f-122">그러나 Microsoft 365 Business 또는 구독에 [Azure Active Directory Premium 1 또는 Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)가 포함되어 있는 경우에도 [조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="f744f-123">조건부 액세스 정책을 사용하려면 [최신 인증이 사용 ](#enable-multi-factor-authentication-for-your-organization)되고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="f744f-124">보안 기본값 관리</span><span class="sxs-lookup"><span data-stu-id="f744f-124">Manage security defaults</span></span>

1. <span data-ttu-id="f744f-125">전역 관리자 자격 증명을 사용하여 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="f744f-126">[Azure Active Directory 속성](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="f744f-127">페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="f744f-128">보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="f744f-129">기본 정책에서 보안 기본값으로 이동</span><span class="sxs-lookup"><span data-stu-id="f744f-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="f744f-130">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에서 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="f744f-131">**로그인 및 보안**옆의 **더욱 안전하게 로그인**에서 **보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="f744f-132">**더욱 안전하게 로그인**에서 **관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="f744f-133">**Azure 포털 조건부 액세스 정책** 페이지에서 **켬**으로 되어 있는 각 기본 정책을 선택하고 이 정책들을 **끔**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="f744f-134">[Azure Active Directory 속성](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="f744f-135">페이지 맨 하단에서 **보안 기본값** 관리를 선택하고 **보안 기본값 사용** 창에서 **보안 기본값** 토글을 **예**로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="f744f-136">조직에 대 한 최신 인증을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f744f-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="f744f-137">모든 Office 2016 클라이언트 응용 프로그램은 ADAL(Active Directory Authentication Library)을 사용하여 MFA를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="f744f-138">즉, Office 2016 클라이언트에는 앱 암호가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="f744f-139">그러나 Office 365 구독이 ADAL 또는 최신 인증을 사용하도록 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="f744f-140">최신 인증을 사용하도록 설정하려면 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)의 **설정** \> **설정**을 선택하고 **서비스**탭의 목록에서 **최신 인증**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="f744f-141">**최신 인증** 패널에서 **최신 인증 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![사용 확인란이 선택된 최신 인증 패널](../../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="f744f-143">조직이 Azure 다단계 인증을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f744f-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="f744f-144">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에서 **사용자** 및 **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="f744f-145">**활성 사용자** 섹션에서 **다단계 인증**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="f744f-146">**다단계 인증** 페이지에서 한 명의 사용자에 대해이 기능을 사용 하도록 설정 하는 경우 **사용자** 를 선택 하거나 다중 사용자를 사용 하도록 설정 하려면 **대량 업데이트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="f744f-147">**빠른 단계**에서 **사용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="f744f-148">팝업 창에서 **다단계 인증 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="f744f-149">조직에 대한 다단계 인증을 설정한 후에는 사용자가 장치에서 2단계 인증을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="f744f-150">자세한 내용은 [Office 365에 대해 2단계 인증 설정](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f744f-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="f744f-151">사용자에게 인증자 앱을 설정하는 방법을 설명하려면 [Office 365에서 Microsoft Authenticator 사용](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)을 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="f744f-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f744f-152">2017년 8월을 기준으로 비즈니스용 Skype Online 및 Exchange Online을 포함하는 모든 새 Office 365 테넌트는 기본적으로 최신 인증을 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="f744f-153">비즈니스용 Skype Online의 최신 인증 상태를 확인하려면 전역 관리자 자격 증명을 사용하여 비즈니스용 Skype Online PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="f744f-154">Get-CsOAuthConfiguration을 실행하여ClientADALAuthOverride의 결과물을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="f744f-155">ClientADALAuthOverride가 '허용'인 경우 최신 인증이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f744f-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="f744f-156">Exchange Online의 MA 상태를 확인하려면 [Exchange Online에서 최신 인증을 사용하도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f744f-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="f744f-157">관련 문서</span><span class="sxs-lookup"><span data-stu-id="f744f-157">Related articles</span></span>

[<span data-ttu-id="f744f-158">Office 365 및 Microsoft 365 Business 플랜을 보호하는 10가지 주요 방법</span><span class="sxs-lookup"><span data-stu-id="f744f-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="f744f-159">Windows 장치에서 Office 2013를 사용하기 위한 최신 인증의 사용</span><span class="sxs-lookup"><span data-stu-id="f744f-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)

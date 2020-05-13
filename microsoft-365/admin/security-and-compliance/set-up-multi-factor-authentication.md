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
description: 보안 기본값을 사용 하 여 사용자에 대해 multi-factor authentication을 설정 하는 방법을 알아봅니다.
monikerRange: o365-worldwide
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213013"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="5eee1-103">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="5eee1-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5eee1-104">2019 년 10 월 21 일 이후에 구독 또는 평가판을 구매한 경우 MFA (다단계 인증)를 위해 예기치 않게 메시지가 표시 되는 경우 구독에 대해 [보안 기본값이](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 자동으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="5eee1-105">모든 새 Microsoft 365 구독에는 자동으로 [보안 기본값이](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="5eee1-106">즉, 모든 사용자는 MFA (multi-factor authentication)를 설정 하 고 모바일 장치에 Microsoft Authenticator 앱을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="5eee1-107">자세한 내용은 [Microsoft 365 계정에 대 한 MFA 설정을](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5eee1-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="5eee1-108">다음 9개의 관리자 역할은 로그인할 때마다 추가 인증을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="5eee1-109">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-109">Global administrator</span></span>
- <span data-ttu-id="5eee1-110">SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-110">SharePoint administrator</span></span>
- <span data-ttu-id="5eee1-111">Exchange 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-111">Exchange administrator</span></span>
- <span data-ttu-id="5eee1-112">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-112">Conditional Access administrator</span></span>
- <span data-ttu-id="5eee1-113">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-113">Security administrator</span></span>
- <span data-ttu-id="5eee1-114">헬프데스크 관리자 또는 암호 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="5eee1-115">청구 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-115">Billing administrator</span></span>
- <span data-ttu-id="5eee1-116">사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-116">User administrator</span></span>
- <span data-ttu-id="5eee1-117">인증 관리자</span><span class="sxs-lookup"><span data-stu-id="5eee1-117">Authentication administrator</span></span>

<span data-ttu-id="5eee1-118">필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="5eee1-119">MFA를 설정 하거나 수정 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="5eee1-120">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="5eee1-121">기본 정책을 사용 하 여 이전에 MFA를 설정한 경우 [보안 기본값을 설정 하려면 해당 화면을 꺼야 합니다](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="5eee1-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="5eee1-122">그러나 Microsoft 365 Business 또는 구독에 [Azure Active Directory Premium P1 또는 Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)가 포함 되어 있는 경우 [조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="5eee1-123">조건부 액세스 정책을 사용 하려면 보안 기본값을 사용 하지 않도록 설정 하 고 [최신 인증](#enable-modern-authentication-for-your-organization) 을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="5eee1-124">사용자에 게 Microsoft Authenticator 앱을 설정 하는 방법을 설명 하려면 [Use Microsoft authenticator With Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5eee1-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="5eee1-125">보안 기본값 관리</span><span class="sxs-lookup"><span data-stu-id="5eee1-125">Manage security defaults</span></span>

1. <span data-ttu-id="5eee1-126">전역 관리자 자격 증명을 사용하여 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="5eee1-127">[Azure Active Directory-속성 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="5eee1-128">페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="5eee1-129">보안 기본값을 사용 하려면 **예** 를 선택 하 고 보안 기본값을 사용 하지 않으려면 **아니요** 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5eee1-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="5eee1-130">기본 정책에서 보안 기본값으로 이동</span><span class="sxs-lookup"><span data-stu-id="5eee1-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="5eee1-131">[조건부 액세스-정책 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="5eee1-132">설정 된 각 기본 정책을 선택 **하 고** **정책 사용** 을 **해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="5eee1-133">[Azure Active Directory-속성 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="5eee1-134">페이지 맨 아래에서 **보안 기본값 관리**를 선택 하 **고 보안 기본값 사용 창에서** **보안 기본값 사용** 을 설정/해제를 선택한 다음 **저장** **을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="5eee1-135">조직에 대 한 최신 인증을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5eee1-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="5eee1-136">모든 Office 2016 클라이언트 응용 프로그램은 ADAL(Active Directory Authentication Library)을 사용하여 MFA를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="5eee1-137">즉, Office 2016 클라이언트에는 앱 암호가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="5eee1-138">자세한 내용은 [이 문서](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5eee1-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="5eee1-139">그러나 Microsoft 365 구독이 ADAL 또는 최신 인증을 사용 하도록 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="5eee1-140">최신 인증을 사용하도록 설정하려면 [관리 센터](https://go.microsoft.com/fwlink/p/?linkid=834822)의 **설정** \> **설정**을 선택하고 **서비스**탭의 목록에서 **최신 인증**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="5eee1-141">**최신** 인증 패널에서 **최신 인증 사용 (권장)** 상자를 선택 하 고 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![사용 확인란이 선택된 최신 인증 패널](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="5eee1-143">2017 년 8 월 현재 비즈니스용 Skype online 및 Exchange online을 포함 하는 모든 새 Microsoft 365 구독에는 기본적으로 최신 인증이 사용 되도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="5eee1-144">비즈니스용 Skype Online의 최신 인증 상태를 확인하려면 전역 관리자 자격 증명을 사용하여 비즈니스용 Skype Online PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="5eee1-145">Get-CsOAuthConfiguration을 실행하여ClientADALAuthOverride의 결과물을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="5eee1-146">ClientADALAuthOverride가 '허용'인 경우 최신 인증이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eee1-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="5eee1-147">Exchange Online의 MA 상태를 확인하려면 [Exchange Online에서 최신 인증을 사용하도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5eee1-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="5eee1-148">관련 문서</span><span class="sxs-lookup"><span data-stu-id="5eee1-148">Related articles</span></span>

[<span data-ttu-id="5eee1-149">Microsoft 365 비즈니스 계획을 보호 하는 10 가지 주요 방법</span><span class="sxs-lookup"><span data-stu-id="5eee1-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="5eee1-150">Windows 장치에서 Office 2013를 사용하기 위한 최신 인증의 사용</span><span class="sxs-lookup"><span data-stu-id="5eee1-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)

---
title: 사용자에 대한 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.openlocfilehash: 5ea367e64108e80ee7429ec700cf2ac0551aeab2
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105154"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="402df-103">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="402df-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="402df-104">[다단계 인증(MFA) 및 Microsoft 365에서의 MFA의 지원](multi-factor-authentication-microsoft-365.md)에 대한 이해를 바탕으로, 이제 설정을 하고 조직에 배포할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="402df-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402df-105">2019년 10월 21일 이후에 구독 또는 평가판을 구매하였고 로그인할 때 MFA 메시지가 표시되면 [보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)이 구독에 대해 자동으로 사용되도록 설정된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="402df-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="402df-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="402df-106">Before you begin</span></span>

- <span data-ttu-id="402df-107">MFA를 관리하려면 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="402df-108">자세한 내용은 [관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="402df-109">레거시 사용자별 MFA가 켜진 경우, [레거시 사용자별 MFA를 해제합니다](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="402df-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="402df-110">Windows 장치에 Office 2013 클라이언트가 있는 경우, [Office 2013 클라이언트에 대한 최신 인증을 설정하세요](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="402df-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="402df-111">고급: AD FS(Active Directory Federation Services)를 사용하는 타사 디렉터리 서비스가 있는 경우 Azure MFA 서버를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="402df-112">자세한 내용은 [Azure 다단계 인증 및 타사 VPN 솔루션을 사용한 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="402df-113">보안 기본값 설정 또는 해제하기</span><span class="sxs-lookup"><span data-stu-id="402df-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="402df-114">대부분의 조직에서 보안 기본값은 적절한 수준의 추가 로그인 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="402df-115">자세한 내용은 [보안 기본값이란?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="402df-116">신규 구독이면 보안 기본값이 이미 자동으로 설정되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402df-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="402df-117">Azure 포털의 Azure Active Directory(Azure AD)에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402df-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="402df-118">전역  관리자 자격 증명으로 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="402df-119">왼쪽 탐색 모음에서 **모두 표시** 를 선택하고 **관리 센터** 에서 **Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="402df-120">**Azure Active Directory 관리 센터** 에서 **Azure Active Directory** \> **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="402df-121">페이지 하단에서 **보안 기본값 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="402df-122">보안 기본값을 사용하도록 설정하려면 **예** 를 선택하고 사용하지 않도록 설정하려면 **아니요** 를 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="402df-123">[기준 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)을 사용해 온 경우 보안 기본값을 사용하기 위해 이동하기 전에 정잭을 해제하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="402df-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="402df-124">[조건 액세스 - 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="402df-125">**켜짐** 상태인 각 기준선 정책을 선택하고 **정책 사용** 을 **끔** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="402df-126">[Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="402df-127">페이지 하단에서 **보안 기본값 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="402df-128">보안 기본값을 사용하도록 설정하려면 **예** 를 선택하고 사용하지 않도록 설정하려면 **아니요** 를 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="402df-129">조건부 액세스 정책 사용하기</span><span class="sxs-lookup"><span data-stu-id="402df-129">Use Conditional Access policies</span></span>

<span data-ttu-id="402df-130">조직에 더 세분화된 로그인 보안 요구 사항이 있으면 조건부 액세스 정책에서 더 많은 제어권을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402df-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="402df-131">조건부 액세스를 사용하면 사용자에게 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 로그인 이벤트에 반응하고 추가 작업을 요청하는 정책을 만들고 정의할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="402df-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402df-132">조건부 액세스 정책을 사용하기 전에 사용자별 MFA와 보안 기본값을 모두 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="402df-133">조건부 액세스는 Azure AD Premium P1 또는 이를 포함하는 라이선스(예: Microsoft 365 Business Premium 및 Microsoft 365 E3)를 구매한 고객이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402df-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="402df-134">자세한 내용은 [조건부 액세스 정책 만들기](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="402df-135">위험 기반 조건부 액세스는 Azure AD Premium P2 라이선스 또는 Microsoft 365 E5와 같이 이를 포함하는 라이선스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402df-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="402df-136">자세한 내용은 [위험에 기반한 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="402df-137">Azure AD P1 및 P2에 대한 자세한 내용은 [Azure Active Directory 가격](https://azure.microsoft.com/pricing/details/active-directory/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402df-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="402df-138">조직에 대한 최신 인증 설정하기</span><span class="sxs-lookup"><span data-stu-id="402df-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="402df-139">대부분의 구독에서 최신 인증이 자동으로 설정되어 있지만 오래전에 구독을 구매한 경우에는 설정되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402df-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="402df-140">이는 MFA가 Office 앱에서 제대로 작동하려면 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="402df-141">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정** \> **조직 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-141">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
1. <span data-ttu-id="402df-142">**서비스** 탭에서 **최신 인증** 을 선택하고, **최신 인증** 창에서 **최신 인증 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="402df-143">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="402df-144">레거시 사용자별 MFA 해제</span><span class="sxs-lookup"><span data-stu-id="402df-144">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="402df-145">이전에 사용자별 MFA를 설정한 경우, 보안 기본값을 사용하기 전에 먼저 이 기능을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-145">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="402df-146">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **사용자** \> **활성 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-146">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="402df-147">**활성 사용자** 페이지에서 **다단계 인증** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="402df-148">다단계 인증 페이지에서 각 사용자를 선택하고 다단계 인증 상태를 **사용 안 함** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="402df-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="402df-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="402df-149">Next steps</span></span>

- [<span data-ttu-id="402df-150">추가 확인 방법을 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="402df-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="402df-151">다단계 인증이란</span><span class="sxs-lookup"><span data-stu-id="402df-151">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="402df-152">등록 후 로그인하는 방법</span><span class="sxs-lookup"><span data-stu-id="402df-152">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="402df-153">추가 확인 방법을 변경하는 방법</span><span class="sxs-lookup"><span data-stu-id="402df-153">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-topics"></a><span data-ttu-id="402df-154">관련 주제</span><span class="sxs-lookup"><span data-stu-id="402df-154">Related topics</span></span>

[<span data-ttu-id="402df-155">비디오: 다단계 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="402df-155">Video: Turn on multi-factor authentication</span></span>](https://docs.microsoft.com/microsoft-365/business-video/turn-on-mfa)

[<span data-ttu-id="402df-156">비디오: 휴대폰의 다단계 인증 켜기</span><span class="sxs-lookup"><span data-stu-id="402df-156">Video: Turn on multi-factor authentication for your phone</span></span>](https://docs.microsoft.com/microsoft-365/business-video/set-up-mfa)
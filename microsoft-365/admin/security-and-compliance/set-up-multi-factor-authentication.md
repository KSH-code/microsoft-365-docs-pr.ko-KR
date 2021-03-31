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
ms.openlocfilehash: de5f8ffbc5c26015f6ff0eb2863b622273f96ca1
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408516"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="07220-103">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="07220-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="07220-104">[다단계 인증(MFA) 및 Microsoft 365에서의 MFA의 지원](multi-factor-authentication-microsoft-365.md)에 대한 이해를 바탕으로, 이제 설정을 하고 조직에 배포할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="07220-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07220-105">2019년 10월 21일 이후에 구독 또는 평가판을 구매하였고 로그인할 때 MFA 메시지가 표시되면 [보안 기본값](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)이 구독에 대해 자동으로 사용되도록 설정된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07220-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="07220-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="07220-106">Before you begin</span></span>

- <span data-ttu-id="07220-107">MFA를 관리하려면 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="07220-108">자세한 내용은 [관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="07220-109">레거시 사용자별 MFA가 켜진 경우, [레거시 사용자별 MFA를 해제합니다](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="07220-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="07220-110">Windows 장치에 Office 2013 클라이언트가 있는 경우, [Office 2013 클라이언트에 대한 최신 인증을 설정하세요](./enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="07220-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](./enable-modern-authentication.md).</span></span>
- <span data-ttu-id="07220-111">고급: AD FS(Active Directory Federation Services)를 사용하는 타사 디렉터리 서비스가 있는 경우 Azure MFA 서버를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="07220-112">자세한 내용은 [Azure 다단계 인증 및 타사 VPN 솔루션을 사용한 고급 시나리오](/azure/active-directory/authentication/howto-mfaserver-nps-vpn)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="07220-113">보안 기본값 설정 또는 해제하기</span><span class="sxs-lookup"><span data-stu-id="07220-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="07220-114">대부분의 조직에서 보안 기본값은 적절한 수준의 추가 로그인 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="07220-115">자세한 내용은 [보안 기본값이란?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-115">For more information, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="07220-116">신규 구독이면 보안 기본값이 이미 자동으로 설정되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07220-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="07220-117">Azure 포털의 Azure Active Directory(Azure AD)에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07220-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="07220-118">전역  관리자 자격 증명으로 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="07220-119">왼쪽 탐색 모음에서 **모두 표시** 를 선택하고 **관리 센터** 에서 **Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="07220-120">**Azure Active Directory 관리 센터** 에서 **Azure Active Directory** \> **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="07220-121">페이지 하단에서 **보안 기본값 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="07220-122">보안 기본값을 사용하도록 설정하려면 **예** 를 선택하고 사용하지 않도록 설정하려면 **아니요** 를 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="07220-123">[기준 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-baseline-protection)을 사용해 온 경우 보안 기본값을 사용하기 위해 이동하기 전에 정잭을 해제하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07220-123">If you have been using [baseline Conditional Access policies](/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="07220-124">[조건 액세스 - 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="07220-125">**켜짐** 상태인 각 기준선 정책을 선택하고 **정책 사용** 을 **끔** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="07220-126">[Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="07220-127">페이지 하단에서 **보안 기본값 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="07220-128">보안 기본값을 사용하도록 설정하려면 **예** 를 선택하고 사용하지 않도록 설정하려면 **아니요** 를 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="07220-129">조건부 액세스 정책 사용하기</span><span class="sxs-lookup"><span data-stu-id="07220-129">Use Conditional Access policies</span></span>

<span data-ttu-id="07220-130">조직에 더 세분화된 로그인 보안 요구 사항이 있으면 조건부 액세스 정책에서 더 많은 제어권을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07220-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="07220-131">조건부 액세스를 사용하면 사용자에게 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 로그인 이벤트에 반응하고 추가 작업을 요청하는 정책을 만들고 정의할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="07220-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07220-132">조건부 액세스 정책을 사용하기 전에 사용자별 MFA와 보안 기본값을 모두 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="07220-133">조건부 액세스는 Azure AD Premium P1 또는 이를 포함하는 라이선스(예: Microsoft 365 Business Premium 및 Microsoft 365 E3)를 구매한 고객이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07220-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="07220-134">자세한 내용은 [조건부 액세스 정책 만들기](/azure/active-directory/authentication/tutorial-enable-azure-mfa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-134">For more information, see [create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="07220-135">위험 기반 조건부 액세스는 Azure AD Premium P2 라이선스 또는 Microsoft 365 E5와 같이 이를 포함하는 라이선스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07220-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="07220-136">자세한 내용은 [위험에 기반한 조건부 액세스](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-136">For more information, see [risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="07220-137">Azure AD P1 및 P2에 대한 자세한 내용은 [Azure Active Directory 가격](https://azure.microsoft.com/pricing/details/active-directory/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07220-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="07220-138">조직에 대한 최신 인증 설정하기</span><span class="sxs-lookup"><span data-stu-id="07220-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="07220-139">대부분의 구독의 경우 최신 인증이 자동으로 설정되지만 2017년 8월 이전에 구독을 구입한 경우 Outlook과 같은 Windows 클라이언트에서 작동하기 위해 다단계 인증과 같은 기능을 사용하려면 최신 인증을 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07220-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multi-Factor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="07220-140">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정** \> **조직 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="07220-141">**서비스** 탭에서 **최신 인증** 을 선택하고, **최신 인증** 창에서 **최신 인증 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="07220-142">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="07220-143">레거시 사용자별 MFA 해제</span><span class="sxs-lookup"><span data-stu-id="07220-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="07220-144">이전에 사용자별 MFA를 설정한 경우, 보안 기본값을 사용하기 전에 먼저 이 기능을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="07220-145">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **사용자** \> **활성 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="07220-146">**활성 사용자** 페이지에서 **다단계 인증** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="07220-147">다단계 인증 페이지에서 각 사용자를 선택하고 다단계 인증 상태를 **사용 안 함** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07220-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="07220-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="07220-148">Next steps</span></span>

- [<span data-ttu-id="07220-149">추가 확인 방법을 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="07220-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="07220-150">다단계 인증이란</span><span class="sxs-lookup"><span data-stu-id="07220-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="07220-151">등록 후 로그인하는 방법</span><span class="sxs-lookup"><span data-stu-id="07220-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="07220-152">추가 확인 방법을 변경하는 방법</span><span class="sxs-lookup"><span data-stu-id="07220-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a><span data-ttu-id="07220-153">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="07220-153">Related content</span></span>

<span data-ttu-id="07220-154">[다단계 인증 켜기](../../business-video/turn-on-mfa.md)(비디오)</span><span class="sxs-lookup"><span data-stu-id="07220-154">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>

<span data-ttu-id="07220-155">[휴대폰의 다단계 인증 켜기](../../business-video/set-up-mfa.md)(비디오)</span><span class="sxs-lookup"><span data-stu-id="07220-155">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>
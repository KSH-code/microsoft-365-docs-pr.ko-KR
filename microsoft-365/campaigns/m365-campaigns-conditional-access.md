---
title: 보안 기본값 켜기
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 보안 기본값이 미리 구성한 보안 설정을 제공하여 ID 관련 공격으로부터 조직을 보호하는 데 어떻게 도움이 될 수 있는지 확인합니다.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398299"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="c2877-103">보안 기본값 켜기</span><span class="sxs-lookup"><span data-stu-id="c2877-103">Turn on security defaults</span></span>

<span data-ttu-id="c2877-104">보안 기본값은 Microsoft가 조직을 대신하여 관리하는 미리 구성한 보안 설정을 제공하여 ID 관련 공격으로부터 조직을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="c2877-105">이러한 설정에는 모든 관리자 및 사용자 계정에 대해 MFA(다단계 인증)를 사용하도록 설정하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="c2877-106">대부분의 조직에서 보안 기본값은 좋은 수준의 추가 로그인 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="c2877-107">보안 기본값 및 적용하는 정책에 대한 자세한 내용은 [보안 기본값이란?을 참조하세요.](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="c2877-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="c2877-108">2019년 10월 22일 이후에 구독을 만든 경우 보안 기본값이 자동으로 사용하도록 설정되어 있을 수 &mdash; 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="c2877-109">Azure AD(Azure Active Directory)에서 보안 기본값을 사용하도록 설정하거나 이미 활성화되어 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="c2877-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="c2877-110">전역 관리자 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">자격 증명으로</a> Microsoft 365 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="c2877-111">왼쪽 창에서 모두  표시를 선택한 다음 관리 센터에서 를 **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="c2877-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="c2877-112">Azure Active Directory 센터의 왼쪽 창에서 **를** **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="c2877-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="c2877-113">대시보드의 왼쪽 메뉴에 있는 관리 **섹션에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c2877-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="속성 메뉴 Azure Active Directory 위치를 보여주는 Azure Active Directory 관리 센터의 스크린샷입니다.":::

5. <span data-ttu-id="c2877-115">속성 페이지의 맨 **아래에서** **보안 기본값 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c2877-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="c2877-116">오른쪽 창에 보안 기본값 사용 **설정이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="c2877-117">**예를** 선택하면 보안 기본값이 이미 사용하도록 설정되어 있으며 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="c2877-118">보안 기본값을 현재 사용하도록 설정하지  않은 경우 예를 선택하여 사용하도록 설정한 다음 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c2877-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c2877-119">조건부 액세스 정책을 사용한 경우 보안 기본값을 사용하려면 먼저 정책을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="c2877-120">보안 기본값 또는 조건부 액세스 정책을 사용할 수 있지만 두 정책을 동시에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="c2877-121">조건부 액세스 사용 고려</span><span class="sxs-lookup"><span data-stu-id="c2877-121">Consider using Conditional Access</span></span>

<span data-ttu-id="c2877-122">조직에 복잡한 보안 요구 사항이 있는 경우 또는 보안 정책에 대해 좀 더 세부적인 제어가 필요한 경우 보안 기본값 대신 조건부 액세스를 사용하여 유사하거나 더 높은 보안 상태를 달성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="c2877-123">조건부 액세스를 사용하면 사용자가 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 로그인 이벤트에 반응하는 정책을 만들고 정의하고 추가 작업을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="c2877-124">조건부 액세스 정책은 세분화되어 구체적일 수 있으며, 사용자가 언제 어디서나 생산성을 발휘할 수 있도록 하지만 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="c2877-125">모든 고객이 보안 기본값을 사용할 수 있습니다. 조건부 액세스에는 다음 계획 중 하나에 대한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="c2877-126">Azure Active Directory Premium P1 또는 P2</span><span class="sxs-lookup"><span data-stu-id="c2877-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="c2877-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c2877-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="c2877-128">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c2877-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="c2877-129">Enterprise 모바일 & E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="c2877-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="c2877-130">조건부 액세스를 사용하여 기본적으로 보안이 설정된 정책과 동등한 정책을 구성하려는 경우 다음 단계별 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2877-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="c2877-131">관리자에게 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="c2877-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="c2877-132">Azure 관리를 위한 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="c2877-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="c2877-133">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="c2877-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="c2877-134">모든 사용자에게 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="c2877-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="c2877-135">[Azure AD MFA](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) 등록 필요 - P2의 일부인 Azure AD ID 보호가 Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="c2877-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="c2877-136">조건부 액세스에 대한 자세한 내용은 [조건부 액세스란?을 참조하세요.](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="c2877-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="c2877-137">조건부 액세스 정책을 만드는 데 대한 자세한 내용은 [Create a Conditional Access policy를 참조하십시오.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)</span><span class="sxs-lookup"><span data-stu-id="c2877-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="c2877-138">조건부 액세스를 제공하지만 아직 조건부 액세스 정책을 만들지 않은 계획이나 라이선스가 있는 경우 보안 기본값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="c2877-139">그러나 조건부 액세스 정책을 사용하려면 먼저 보안 기본값을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2877-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>

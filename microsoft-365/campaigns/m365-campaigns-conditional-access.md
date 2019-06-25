---
title: 조건부 액세스 정책 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business에 대해 MFA를 요구 하 고 조건부 액세스 정책을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 08e9365e8aad37e2412a6d739b41f2328c1aa277
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183376"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="0e53f-103">다단계 인증 필요 및 조건부 액세스 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e53f-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="0e53f-104">다단계 인증 및 조건부 액세스 정책을 사용 하 여 데이터에 대 한 액세스를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="0e53f-105">이러한 추가 보안은 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-105">These add substantial additional security.</span></span> <span data-ttu-id="0e53f-106">Microsoft는 모든 고객에 게 권장 되는 기본 조건부 액세스 정책 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="0e53f-107">기본 정책은 일반적인 여러 공격 으로부터 조직을 보호 하는 데 도움이 되는 미리 정의 된 정책의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="0e53f-108">이러한 일반적인 공격에는 암호 스프레이, replay 및 피싱이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="0e53f-109">이러한 정책을 사용 하려면 관리자 및 사용자가 특정 조건에 맞을 때 두 번째 인증 형태 (다단계 인증) 또는 MFA를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="0e53f-110">예를 들어 조직의 사용자가 다른 국가나 알 수 없는 장치에서 Microsoft 365에 로그인 하려고 하면 로그인이 위험한 것으로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="0e53f-111">사용자는 id를 증명 하기 위해 추가 인증 형식 (예: 지문 또는 코드)을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="0e53f-112">현재 기본 정책에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="0e53f-113">Microsoft 365 관리 센터에서 설정:</span><span class="sxs-lookup"><span data-stu-id="0e53f-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="0e53f-114">관리자 **에 대해 MFA 필요** -전역 관리자를 비롯 하 여 권한이 가장 높은 관리자 역할에 대해 multi-factor authentication이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="0e53f-115">**최종 사용자 보호** -로그인이 위험한 경우에만 사용자에 대해 multi-factor authentication을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="0e53f-116">Azure Active Directory 포털에서 설정:</span><span class="sxs-lookup"><span data-stu-id="0e53f-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="0e53f-117">**레거시 인증 차단** -오래 된 클라이언트 앱과 일부 새 앱은 더 최신의 비보안 인증 프로토콜을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="0e53f-118">이러한 이전 앱은 조건부 액세스 정책을 우회 하 여 환경에 대 한 무단 액세스를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="0e53f-119">이 정책은 조건부 액세스를 지원 하지 않는 클라이언트의 액세스를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="0e53f-120">**서비스 관리를 위해 MFA 필요** -Azure portal을 포함 하 여 관리 도구에 액세스 하기 위한 다단계 인증 필요 (기준 정책 구성).</span><span class="sxs-lookup"><span data-stu-id="0e53f-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="0e53f-121">이러한 모든 기본 정책을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-121">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="0e53f-122">이러한 정책을 사용 하도록 설정한 후에는 관리자 및 사용자에 게 Azure Multi-factor authentication을 등록 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="0e53f-123">이러한 정책에 대 한 자세한 내용은 [기본 정책 이란](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e53f-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="0e53f-124">MFA 필요</span><span class="sxs-lookup"><span data-stu-id="0e53f-124">Require MFA</span></span>

<span data-ttu-id="0e53f-125">모든 사용자에 게 다른 ID 형태의 로그인을 요구 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="0e53f-126">관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 하 여 **설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="0e53f-127">설정 페이지의 **고급 보안 설정** 카드에서 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![더 안전 하 게 로그인 카드를 만듭니다.](media/setupmfa.png)
3. <span data-ttu-id="0e53f-129">더 안전 하 게 로그인 하기 페이지에서 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="0e53f-130">로그인 보안 강화 창에서 **관리자에 대 한 다단계 인증 필요** 옆의 확인란을 선택 하 고, **위험이 감지 되 면 사용자에 게 다단계 인증을 등록 하 고 액세스를 차단 하도록 요구**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-130">On the Strengthen sign-in security pane, check the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="0e53f-131">**사용자 찾기** 상자에서 MFA 요구 사항 으로부터 [응급](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) 또는 "투명 효과" 관리자 계정을 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![공동으로 보안 페이지를 강화 합니다.](media/requiremfa.png)

5. <span data-ttu-id="0e53f-133">페이지 아래쪽에서 **정책 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="0e53f-134">기본 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e53f-134">Set up baseline policies</span></span>

1. <span data-ttu-id="0e53f-135">[Azure 포털로](https://portal.azure.com)이동한 다음 **azure Active Directory** \> **조건부 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="0e53f-136">기본 정책은 페이지에 나열 되며, [mfa](#require-mfa)에 대 한 mfa 필요의 단계를 완료 한 후에는 관리자 및 최종 사용자 보호를 사용 하도록 설정 해야 한다는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-136">The baseline policies are listed on the page, and you can see that Require MFA for admins and End user protection are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![조건부 액세스에 대 한 기준 정책을 나열 하는 페이지입니다.](media/casettings.png)
2. <span data-ttu-id="0e53f-138">각 정책에 대해 다음과 같은 구체적인 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e53f-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="0e53f-139">관리자를 위해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="0e53f-139">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

       
    -   [<span data-ttu-id="0e53f-140">사용자에 대해 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="0e53f-140">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="0e53f-141">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="0e53f-141">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="0e53f-142">서비스 관리를 위해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="0e53f-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="0e53f-143">승인 된 클라이언트 앱을 요구 하는 등 추가 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e53f-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="0e53f-144">자세한 내용은 [조건부 액세스 설명서](https://docs.microsoft.com/azure/active-directory/conditional-access/) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e53f-144">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>

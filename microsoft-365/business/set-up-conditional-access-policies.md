---
title: Microsoft 365 캠페인에 대 한 조건부 액세스 정책 설정
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 캠페인에 대 한 조건부 액세스 정책을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 31f3b7f3678671af3b5ca3947dec37041b226fac
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575641"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="a2539-103">조건부 액세스 정책 설정</span><span class="sxs-lookup"><span data-stu-id="a2539-103">Set up conditional access policies</span></span>

<span data-ttu-id="a2539-104">[조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 정책은 substancial 추가 보안을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="a2539-105">Microsoft는 모든 고객에 게 권장 되는 기본 조건부 액세스 정책 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="a2539-106">기본 정책은 일반적인 여러 공격 으로부터 조직을 보호 하는 데 도움이 되는 미리 정의 된 정책의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="a2539-107">이러한 일반적인 공격에는 암호 스프레이, replay 및 피싱이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="a2539-108">관리자 및 사용자는 이러한 정책을 통해 특정 조건이 충족 될 때 다단계 인증 또는 MFA 라는 두 번째 인증 양식을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="a2539-109">예를 들어 사용자가 다른 국가에서 로그인 하는 경우 로그인이 위험한 것으로 간주 될 수 있으며 사용자는 추가 인증 양식을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="a2539-110">현재 기본 정책에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="a2539-111">관리자 **에 대해 MFA 필요** -전역 관리자를 비롯 하 여 권한이 가장 높은 관리자 역할에 대해 multi-factor authentication이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="a2539-112">**최종 사용자 보호** -로그인이 위험한 경우에만 사용자에 대해 multi-factor authentication을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="a2539-113">**레거시 인증 차단** -오래 된 클라이언트 앱과 일부 새 앱은 더 최신의 비보안 인증 프로토콜을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="a2539-114">이러한 이전 앱은 조건부 액세스 정책을 우회 하 여 환경에 대 한 무단 액세스를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="a2539-115">이 정책은 조건부 액세스를 지원 하지 않는 클라이언트의 액세스를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="a2539-116">**서비스 관리를 위해 MFA 필요** -Azure portal을 포함 하 여 관리 도구에 액세스 하기 위한 다단계 인증 필요 (기준 정책 구성).</span><span class="sxs-lookup"><span data-stu-id="a2539-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="a2539-117">이러한 모든 기본 정책을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="a2539-118">이러한 정책을 사용 하도록 설정 하 고 나면 관리자 및 사용자에 게 Azure Multii-요인 인증을 등록 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="a2539-119">이러한 정책에 대 한 자세한 내용은 [기본 정책 이란](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2539-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="a2539-120">기본 정책 설정</span><span class="sxs-lookup"><span data-stu-id="a2539-120">Set up baseline policies</span></span>

1. <span data-ttu-id="a2539-121">[Azure 포털로](https://portal.azure.com)이동한 다음 **azure Active Directory** \> **조건부 액세스**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="a2539-122">기본 정책은 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="a2539-123">![조건부 액세스에 대 한 기준 정책을 나열 하는 페이지입니다.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="a2539-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="a2539-124">각 정책에 대해 다음과 같은 구체적인 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2539-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="a2539-125">관리자를 위해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="a2539-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="a2539-126">사용자에 대해 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="a2539-126">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="a2539-127">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="a2539-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="a2539-128">서비스 관리를 위해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="a2539-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="a2539-129">승인 된 클라이언트 앱을 요구 하는 등의 다양 한 추가 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2539-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="a2539-130">자세한 내용은 [조건부 액세스 설명서](https://docs.microsoft.com/azure/active-directory/conditional-access/) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2539-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>
---
title: '2단계: 암호 보호'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에 암호를 강력하고 관리하기 쉽도록 설정해야 합니다.
ms.openlocfilehash: 375f4a678e85dccb544ffaf56f648e98609841d9
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746514"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="197af-103">2단계: 암호 보호</span><span class="sxs-lookup"><span data-stu-id="197af-103">Step 2: Secure your passwords</span></span>

![2단계-ID](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="197af-105">잘못된 암호 방지</span><span class="sxs-lookup"><span data-stu-id="197af-105">Prevent bad passwords</span></span>

<span data-ttu-id="197af-106">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="197af-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="197af-107">모든 사용자가 [Microsoft의 암호 지침](https://www.microsoft.com/research/publication/password-guidance/) 을 사용하여 사용자 계정 암호를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="197af-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="197af-108">사용자가 쉽게 확인할 수 있는 암호를 만들지 못하도록 하려면 전역 금지 암호 목록과 사용자가 지정한 선택적 사용자 지정 금지 암호 목록을 사용하는 Azure AD 암호 보호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="197af-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="197af-109">예를 들어, 다음과 같이 조직에 맞는 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="197af-110">브랜드 이름</span><span class="sxs-lookup"><span data-stu-id="197af-110">Brand names</span></span>
- <span data-ttu-id="197af-111">제품 이름</span><span class="sxs-lookup"><span data-stu-id="197af-111">Product names</span></span>
- <span data-ttu-id="197af-112">위치(예: 본사)</span><span class="sxs-lookup"><span data-stu-id="197af-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="197af-113">회사 관련 내부 조건</span><span class="sxs-lookup"><span data-stu-id="197af-113">Company-specific internal terms</span></span>
- <span data-ttu-id="197af-114">특정 회사 의미를 갖는 약어</span><span class="sxs-lookup"><span data-stu-id="197af-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="197af-115">[클라우드](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 및 [온-프레미스 AD DS(Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)에 대해 잘못된 암호를 금지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="197af-116">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-password-prot)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="197af-117">암호 재설정 간소화</span><span class="sxs-lookup"><span data-stu-id="197af-117">Simplify password resets</span></span>

<span data-ttu-id="197af-118">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="197af-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="197af-119">이 부문에서 셀프 서비스 암호 재설정은 사용자가 암호 혹은 계정을 재설정 혹은 잠금을 해제하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="197af-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="197af-120">오용 또는 남용에 대한 경고로 사용자가 시스템에 언제 액세스하는지 추적하는 상세한 보고서와 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="197af-121">암호 재설정 전에 암호 쓰기 저장을 사용할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="197af-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="197af-122">[암호 재설정을 시작하기 위한 지침](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="197af-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="197af-124">테스트 랩 가이드: 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="197af-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="197af-125">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-reset)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="197af-126">사용자 로그인 간소화</span><span class="sxs-lookup"><span data-stu-id="197af-126">Simplify user sign-in</span></span>

<span data-ttu-id="197af-127">*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="197af-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="197af-128">이 부문에서 사용자 암호 및 사용자 이름을 입력할 필요없이 Azure AD 사용자 계정을 사용하는 서비스에 로그인 할 수 있도록 PHS(Password Hash Synchronization) 및 PTA(Pass-Through Authentication)와 함께 작동하는 Azure AD Seamless SSO(Azure Active Directory Seamless Single Sign-On)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="197af-129">이는 사용자의 계정이 Office 365와 같은 클라우드 기반 응용 프로그램에 identity 페더레이션 서버와 같은 추가적인 온 프레미스 구성 요소 필요없이 더 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="197af-130">Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="197af-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="197af-131">[Azure AD Seamless SSO 구성 지침](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="197af-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="197af-133">테스트 랩 가이드: Azure AD Seamless Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="197af-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="197af-134">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sso)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="197af-135">Microsoft Office 365 로그인 페이지 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="197af-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="197af-136">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전을 위한 것입니다.*</span><span class="sxs-lookup"><span data-stu-id="197af-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="197af-137">이 부문에서 회사 이름, 로고 및 기타 인식 가능한 요소를 추가하여 사용자가 조직의 로그인 페이지를 인식하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="197af-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="197af-138">Microsoft 365 Enterprise를 사용하는 경우 회사 로고, 색 구성표 및 사용자 지정 사용자 정보를 포함하도록 로그인 및 액세스 패널 페이지의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="197af-139">자세한 내용은 [Office 365 로그인 페이지에 회사 브랜딩 추가](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="197af-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="197af-140">구성 지침은 [로그인 및 액세스 패널에 회사 브랜딩 추가](https://aka.ms/aadpaddbranding)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="197af-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="197af-141">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-custom-sign-in)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197af-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="197af-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="197af-142">Next step</span></span>

|||
|:-------|:-----|
|![3단계](./media/stepnumbers/Step3.png)| [<span data-ttu-id="197af-144">사용자 로그인 보안 및 관리</span><span class="sxs-lookup"><span data-stu-id="197af-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |

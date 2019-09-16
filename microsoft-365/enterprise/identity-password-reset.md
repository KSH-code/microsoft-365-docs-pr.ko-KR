---
title: '5단계: 사용자에 대한 액세스 간소화'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD(Microsoft Azure Active Directory)에 대한 SSPR(셀프 서비스 암호 재설정)을 이해하고 구성하십시오.
ms.openlocfilehash: ec81b2931fd4ad599ffcf983ea8a7d764c56404a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981799"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="d2a9e-103">5단계: 사용자에 대한 액세스 간소화</span><span class="sxs-lookup"><span data-stu-id="d2a9e-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="d2a9e-104">암호 업데이트 간소화</span><span class="sxs-lookup"><span data-stu-id="d2a9e-104">Simplify password updates</span></span>

<span data-ttu-id="d2a9e-105">*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d2a9e-105">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d2a9e-106">이 부문에서 사용자는 Azure 액티브 디렉토리(Azure AD-Microsoft Azure Active Directory)를 통해 암호를 재설정할 수 있으며 로컬 액티브 디렉토리 도메인 서비스(AD DS-Active Directory Domain Services)로 복제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="d2a9e-107">이 과정을 암호 쓰기 저장이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-107">This process is known as password writeback.</span></span> <span data-ttu-id="d2a9e-108">암호 쓰기 저장에서 사용자는 사용자 계정과 속성이 저장된 온 프레미스 AD DS를 통한 암호의 업데이트가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="d2a9e-109">온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="d2a9e-110">암호 쓰기 저장은 계정 손상의 높은 위험이 감지된 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 Azure AD ID 보호 기능을 최대한 활용하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="d2a9e-111">추가 정보 및 구성 지침은 [암호 쓰기 저장을 지원하는 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="d2a9e-p102">가능한 최상의 환경 및 새로운 기능(릴리스될 때)을 유지하도록 최신 버전의 Azure AD Connect로 업그레이드하세요. 자세한 내용은 [Azure AD Connect의 사용자 지정 설치](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d2a9e-115">테스트 랩 가이드: 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="d2a9e-115">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d2a9e-116">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-writeback)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="d2a9e-117">암호 재설정 간소화</span><span class="sxs-lookup"><span data-stu-id="d2a9e-117">Simplify password resets</span></span>

<span data-ttu-id="d2a9e-118">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d2a9e-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d2a9e-119">이 부문에서 셀프 서비스 암호 재설정은 사용자가 암호 혹은 계정을 재설정 혹은 잠금을 해제하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="d2a9e-120">오용 또는 남용에 대한 경고로 사용자가 시스템에 언제 액세스하는지 추적하는 상세한 보고서와 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="d2a9e-121">암호 재설정 전에 암호 쓰기 저장을 사용할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="d2a9e-122">[암호 재설정을 시작하기 위한 지침](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d2a9e-124">테스트 랩 가이드: 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="d2a9e-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d2a9e-125">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-reset)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="d2a9e-126">사용자 로그인 간소화</span><span class="sxs-lookup"><span data-stu-id="d2a9e-126">Simplify user sign-in</span></span>

<span data-ttu-id="d2a9e-127">*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d2a9e-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d2a9e-128">이 부문에서 사용자 암호 및 사용자 이름을 입력할 필요없이 Azure 사용자 계정을 사용하는 서비스에 로그인 할 수 있도록 Azure 액티브 디렉토리 심리스 Single Sign-On(Azure AD Seamless SSO) 를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="d2a9e-129">이는 사용자의 계정이 Office 365와 같은 클라우드 기반 응용 프로그램에 identity 페더레이션 서버와 같은 추가적인 온 프레미스 구성 요소 필요없이 더 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="d2a9e-130">Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="d2a9e-131">[Azure AD Seamless SSO 구성 지침](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d2a9e-133">테스트 랩 가이드: Azure AD Seamless Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="d2a9e-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d2a9e-134">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sso)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="d2a9e-135">Microsoft Office 365 로그인 페이지 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d2a9e-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="d2a9e-136">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전을 위한 것입니다.*</span><span class="sxs-lookup"><span data-stu-id="d2a9e-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d2a9e-137">이 부문에서 회사 이름, 로고 및 기타 인식 가능한 요소를 추가하여 사용자가 조직의 로그인 페이지를 인식하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="d2a9e-138">Microsoft 365 Enterprise를 사용하는 경우 회사 로고, 색 구성표 및 사용자 지정 사용자 정보를 포함하도록 로그인 및 액세스 패널 페이지의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="d2a9e-139">자세한 내용은 [Office 365 로그인 페이지에 회사 브랜딩 추가](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="d2a9e-140">구성 지침은 [로그인 및 액세스 패널에 회사 브랜딩 추가](http://aka.ms/aadpaddbranding)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="d2a9e-141">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-custom-sign-in)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="d2a9e-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d2a9e-142">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="d2a9e-143">더 쉬운 관리를 위한 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="d2a9e-143">Use groups for easier management</span></span>](identity-self-service-group-management.md) |



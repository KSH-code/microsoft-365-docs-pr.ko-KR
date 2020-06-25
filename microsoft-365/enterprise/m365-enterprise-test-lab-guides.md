---
title: Microsoft 365 Enterprise 테스트 랩 가이드
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 다음 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise의 데모, 개념 증명 또는 개발/테스트 환경을 설정합니다.
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818744"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="85798-103">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="85798-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="85798-104">*이는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="85798-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="85798-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span><span class="sxs-lookup"><span data-stu-id="85798-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="85798-106">They provide prescriptive instructions to configure simplified but representative test environments.</span><span class="sxs-lookup"><span data-stu-id="85798-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="85798-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span><span class="sxs-lookup"><span data-stu-id="85798-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="85798-108">TLGs are designed to be modular.</span><span class="sxs-lookup"><span data-stu-id="85798-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="85798-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span><span class="sxs-lookup"><span data-stu-id="85798-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="85798-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span><span class="sxs-lookup"><span data-stu-id="85798-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="85798-111">또한, TLG는 응용 프로그램의 개발 및 테스트를 위한 대표적 환경(개발/테스트 환경이라고도 함)을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85798-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="85798-113">[테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)으로 이동하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85798-113">Go to the [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="85798-114">[![Microsoft 365 Enterprise 테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="85798-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="85798-115">기본 구성</span><span class="sxs-lookup"><span data-stu-id="85798-115">Base configuration</span></span>

<span data-ttu-id="85798-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="85798-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span></span> <span data-ttu-id="85798-117">You can create two different types of base configurations:</span><span class="sxs-lookup"><span data-stu-id="85798-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="85798-118">온-프레미스 구성 요소를 포함하지 않는 클라우드 전용 환경에서 Microsoft 365 Enterprise 기능을 구성하고 시연하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="85798-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="85798-119">액티브 디렉토리 도메인 서비스(AD DS - Active Directory Domain Services) 도메인과 같이 온-프레미스 구성 요소를 사용하는 하이브리드 클라우드 환경에서 Microsoft 365 Enterprise 기능 및 성능을 구성하고 시연하려면 [시뮬레이트된 엔터프라이즈 기본 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="85798-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="85798-120">평가판 또는 프로덕션 테스트 환경에 Microsoft 365 E5 라이선스를 추가하지 않고 Office 365 E5에 대한 테스트 환경을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85798-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="85798-121">ID</span><span class="sxs-lookup"><span data-stu-id="85798-121">Identity</span></span>

<span data-ttu-id="85798-122">ID 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85798-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="85798-123">암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="85798-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="85798-124">AD DS 도메인 컨트롤러에서 암호 해시 기반 디렉터리 동기화를 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="85798-125">통과 인증</span><span class="sxs-lookup"><span data-stu-id="85798-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="85798-126">AD DS 도메인 컨트롤러에 대한 통과 인증을 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="85798-127">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="85798-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="85798-128">AD DS 도메인 컨트롤러에 대한 페더레이션 인증을 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="85798-129">Azure AD Seamless Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="85798-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="85798-130">AD DS 도메인 컨트롤러를 사용하여 Azure AD Seamless SSO(Single Sign-On)를 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="85798-131">Multi-Factor authentication</span><span class="sxs-lookup"><span data-stu-id="85798-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="85798-132">특정 사용자 계정에 대해 휴대폰 기반 다단계 인증을 사용하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="85798-133">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="85798-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="85798-134">조건부 액세스 정책을 사용하여 글로벌 관리자 계정을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="85798-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="85798-135">암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="85798-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="85798-136">Azure AD에서 AD DS 사용자 계정 암호를 변경하려면 암호 쓰기 저장을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="85798-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="85798-137">암호 재설정</span><span class="sxs-lookup"><span data-stu-id="85798-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="85798-138">SSPR(셀프 서비스 암호 재설정)을 사용하여 암호를 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="85798-139">자동 라이선싱 및 그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="85798-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="85798-140">자동 라이선싱 및 동적 그룹 등록으로 새 계정을 이전보다 더 쉽게 관리하도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85798-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="85798-141">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="85798-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="85798-142">현재 사용자 계정의 취약성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="85798-143">ID 및 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="85798-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="85798-144">권장된 ID 및 장치 액세스 구성 및 조건부 액세스 정책을 테스트할 수 있는 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85798-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="85798-145">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="85798-145">Mobile device management</span></span>

<span data-ttu-id="85798-146">모바일 장치 관리와 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85798-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="85798-147">장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="85798-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="85798-148">Windows 10 장치에 대한 사용자 그룹 및 장치 준수 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85798-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="85798-149">iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="85798-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="85798-150">iOS 또는 Android 장치를 등록하고 원격으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="85798-151">정보 보호</span><span class="sxs-lookup"><span data-stu-id="85798-151">Information protection</span></span>

<span data-ttu-id="85798-152">정보 보호 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85798-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="85798-153">강화된 Microsoft 365 보안</span><span class="sxs-lookup"><span data-stu-id="85798-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="85798-154">Microsoft 365 보안을 개선하도록 설정을 구성하고 기본 제공 보안 도구를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="85798-155">데이터 분류</span><span class="sxs-lookup"><span data-stu-id="85798-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="85798-156">SharePoint Online 팀 사이트에서 레이블을 구성하고 문서에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="85798-157">권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="85798-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="85798-158">조직의 권한 상승이 필요한 작업 및 권한이 부여된 작업에 대한 JIT(Just-In-Time) 액세스를 위해 권한이 부여된 액세스 관리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85798-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>



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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 다음 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise의 데모, 개념 증명 또는 개발/테스트 환경을 설정합니다.
ms.openlocfilehash: 4190eb4619f4732310786b5a7dde6bb590a969c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067062"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="bf82b-103">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="bf82b-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="bf82b-104">*이는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="bf82b-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bf82b-p101">TLS(테스트 랩 가이드)는 Microsoft 제품을 빠르게 알아보도록 지원합니다. 그리고 간소하지만 대표적인 테스트 환경을 구성하기 위한 지침을 제공합니다. 평가 기간 또는 유료 구독 기간 동안 데모, 사용자 지정 또는 복잡한 개념 증명 생성을 위해 이러한 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="bf82b-p102">TLS는 모듈 방식으로 설계되었습니다. 따라서 각 모듈을 조합하여 학습 또는 테스트 구성 요구에 좀 더 가깝게 일치하는 여러 구성을 만들 수 있습니다. "직접 구축 후 정상 작동 확인" 실습을 통해 새로운 제품 또는 시나리오의 배포 요구 사항을 이해할 수 있으므로 프로덕션에서 호스팅을 더욱 잘 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="bf82b-111">또한, TLG는 응용 프로그램의 개발 및 테스트를 위한 대표적 환경(개발/테스트 환경이라고도 함)을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="bf82b-113">[여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="bf82b-114">[![Microsoft 365 Enterprise 테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="bf82b-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="bf82b-115">기본 구성</span><span class="sxs-lookup"><span data-stu-id="bf82b-115">Base configuration</span></span>

<span data-ttu-id="bf82b-p103">먼저 Office 365 E5, Enterprise Mobility + Security (EMS) E5 및 Windows 10 Enterprise가 포함되는 [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)의 테스트 환경을 만듭니다. 다음의 두 가지 유형의 기본 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-p103">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="bf82b-118">온-프레미스 구성 요소를 포함하지 않는 클라우드 전용 환경에서 Microsoft 365 Enterprise 기능을 구성하고 시연하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf82b-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="bf82b-119">액티브 디렉토리 도메인 서비스(AD DS - Active Directory Domain Services) 도메인과 같이 온-프레미스 구성 요소를 사용하는 하이브리드 클라우드 환경에서 Microsoft 365 Enterprise 기능 및 성능을 구성하고 시연하려면 [시뮬레이트된 엔터프라이즈 기본 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf82b-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="bf82b-120">평가판 또는 프로덕션 테스트 환경에 Microsoft 365 E5 라이선스를 추가하지 않고 Office 365 E5에 대한 테스트 환경을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="bf82b-121">ID</span><span class="sxs-lookup"><span data-stu-id="bf82b-121">Identity</span></span>

<span data-ttu-id="bf82b-122">ID 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf82b-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bf82b-123">암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="bf82b-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="bf82b-124">AD DS 도메인 컨트롤러에서 암호 해시 기반 디렉터리 동기화를 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf82b-125">통과 인증</span><span class="sxs-lookup"><span data-stu-id="bf82b-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="bf82b-126">AD DS 도메인 컨트롤러에 대한 통과 인증을 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf82b-127">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="bf82b-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="bf82b-128">AD DS 도메인 컨트롤러에 대한 페더레이션 인증을 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf82b-129">Azure AD Seamless Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="bf82b-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="bf82b-130">AD DS 도메인 컨트롤러를 사용하여 Azure AD Seamless SSO(Single Sign-On)를 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf82b-131">Multi-Factor authentication</span><span class="sxs-lookup"><span data-stu-id="bf82b-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="bf82b-132">특정 사용자 계정에 대해 휴대폰 기반 다단계 인증을 사용하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="bf82b-133">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="bf82b-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="bf82b-134">조건부 액세스 정책을 사용하여 글로벌 관리자 계정을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="bf82b-135">암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="bf82b-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="bf82b-136">Azure AD에서 AD DS 사용자 계정 암호를 변경하려면 암호 쓰기 저장을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf82b-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="bf82b-137">암호 재설정</span><span class="sxs-lookup"><span data-stu-id="bf82b-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="bf82b-138">SSPR(셀프 서비스 암호 재설정)을 사용하여 암호를 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="bf82b-139">자동 라이선싱 및 그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="bf82b-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="bf82b-140">자동 라이선싱 및 동적 그룹 등록으로 새 계정을 이전보다 더 쉽게 관리하도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="bf82b-141">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="bf82b-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="bf82b-142">현재 사용자 계정의 취약성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="bf82b-143">ID 및 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="bf82b-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="bf82b-144">권장된 ID 및 장치 액세스 구성 및 조건부 액세스 정책을 테스트할 수 있는 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="bf82b-145">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="bf82b-145">Mobile device management</span></span>

<span data-ttu-id="bf82b-146">모바일 장치 관리와 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf82b-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bf82b-147">장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="bf82b-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf82b-148">Windows 10 장치에 대한 사용자 그룹 및 장치 준수 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="bf82b-149">iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="bf82b-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="bf82b-150">iOS 또는 Android 장치를 등록하고 원격으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="bf82b-151">정보 보호</span><span class="sxs-lookup"><span data-stu-id="bf82b-151">Information protection</span></span>

<span data-ttu-id="bf82b-152">정보 보호 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf82b-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bf82b-153">Office 365 보안 강화</span><span class="sxs-lookup"><span data-stu-id="bf82b-153">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf82b-154">Office 365 보안 향상을 위한 설정을 구성하고 기본 제공 보안 도구를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-154">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="bf82b-155">데이터 분류</span><span class="sxs-lookup"><span data-stu-id="bf82b-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf82b-156">SharePoint Online 팀 사이트에서 Office 365 레이블을 구성하고 문서에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-156">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="bf82b-157">권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="bf82b-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf82b-158">Office 365 조직의 권한 상승이 필요한 작업 및 권한이 부여된 작업에 대한 JIT(Just-In-Time) 액세스를 위해 권한이 부여된 액세스 관리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf82b-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>



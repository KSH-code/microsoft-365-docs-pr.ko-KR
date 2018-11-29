---
title: Microsoft 365 Enterprise 테스트 랩 가이드
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 다음 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise의 데모, 개념 증명 또는 개발/테스트 환경을 설정합니다.
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870219"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="2b516-103">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="2b516-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="2b516-p101">TLS(테스트 랩 가이드)는 Microsoft 제품을 빠르게 알아보도록 지원합니다. 그리고 간소하지만 대표적인 테스트 환경을 구성하기 위한 지침을 제공합니다. 평가 기간 또는 유료 구독 기간 동안 데모, 사용자 지정 또는 복잡한 개념 증명 생성을 위해 이러한 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="2b516-p102">TLS는 모듈 방식으로 설계되었습니다. 따라서 각 모듈을 조합하여 학습 또는 테스트 구성 요구에 좀 더 가깝게 일치하는 여러 구성을 만들 수 있습니다. "직접 구축 후 정상 작동 확인" 실습을 통해 새로운 제품 또는 시나리오의 배포 요구 사항을 이해할 수 있으므로 프로덕션에서 호스팅을 더욱 잘 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="2b516-110">또한, TLG는 응용 프로그램의 개발 및 테스트를 위한 대표적 환경(개발/테스트 환경이라고도 함)을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2b516-112">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="2b516-113">기본 구성</span><span class="sxs-lookup"><span data-stu-id="2b516-113">Base configuration</span></span>

<span data-ttu-id="2b516-p103">먼저 Office 365 E5, Enterprise Mobility + Security (EMS) E5 및 Windows 10 Enterprise가 포함되는 [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)의 테스트 환경을 만듭니다. 다음의 두 가지 유형의 기본 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="2b516-116">온-프레미스 구성 요소를 포함하지 않는 클라우드 전용 환경에서 Microsoft 365 Enterprise 기능을 구성하고 시연하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b516-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="2b516-117">Windows Server Active Directory(AD) 도메인과 같이 온-프레미스 구성 요소를 사용하는 하이브리드 클라우드 환경에서 Microsoft 365 Enterprise 기능을 구성하고 시연하려면 [시뮬레이트된 엔터프라이즈 기본 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b516-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="2b516-118">ID</span><span class="sxs-lookup"><span data-stu-id="2b516-118">Identity</span></span>

<span data-ttu-id="2b516-119">ID 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b516-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="2b516-120">암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="2b516-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="2b516-121">Windows Server AD 도메인 컨트롤러에서 암호 해시 기반 디렉터리 동기화를 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="2b516-122">경유 인증</span><span class="sxs-lookup"><span data-stu-id="2b516-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="2b516-123">Windows Server AD 도메인 컨트롤러에 대한 통과 인증을 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="2b516-124">Azure AD Seamless Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="2b516-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="2b516-125">Windows Server AD 도메인 컨트롤러를 사용하여 Azure AD Seamless SSO(Single Sign-On)를 사용하도록 설정하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="2b516-126">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="2b516-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="2b516-127">특정 사용자 계정에 대해 휴대폰 기반 다단계 인증을 사용하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="2b516-128">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="2b516-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="2b516-129">Office 365 Cloud App Security 및 조건부 액세스 정책을 사용하여 전역 관리자 계정을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="2b516-130">암호 재설정</span><span class="sxs-lookup"><span data-stu-id="2b516-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="2b516-131">SSPR(셀프 서비스 암호 재설정)을 사용하여 암호를 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="2b516-132">자동 라이선싱 및 그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="2b516-132">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="2b516-133">자동 라이선싱 및 동적 그룹 등록으로 새 계정을 이전보다 더 쉽게 관리하도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-133">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="2b516-134">Azure AD ID 보호</span><span class="sxs-lookup"><span data-stu-id="2b516-134">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="2b516-135">현재 사용자 계정의 취약성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-135">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="2b516-136">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="2b516-136">Mobile device management</span></span>

<span data-ttu-id="2b516-137">모바일 장치 관리와 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b516-137">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="2b516-138">MAM 정책</span><span class="sxs-lookup"><span data-stu-id="2b516-138">MAM policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2b516-139">iOS 및 Android 장치용 MAM(모바일 응용 프로그램 관리) 정책 및 사용자 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-139">Create user groups and mobile application management (MAM) policies for iOS and Android devices.</span></span>
    
- [<span data-ttu-id="2b516-140">iOS 및 Android 장치 등록</span><span class="sxs-lookup"><span data-stu-id="2b516-140">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="2b516-141">iOS 또는 Android 장치를 등록하고 원격으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-141">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="2b516-142">정보 보호</span><span class="sxs-lookup"><span data-stu-id="2b516-142">Information protection</span></span>

<span data-ttu-id="2b516-143">정보 보호 관련 기능을 시연하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b516-143">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="2b516-144">Office 365 보안 강화</span><span class="sxs-lookup"><span data-stu-id="2b516-144">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2b516-145">Office 365 보안 향상을 위한 설정을 구성하고 기본 제공 보안 도구를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-145">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="2b516-146">데이터 분류</span><span class="sxs-lookup"><span data-stu-id="2b516-146">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2b516-147">SharePoint Online 팀 사이트에서 Office 365 레이블을 구성하고 문서에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-147">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="2b516-148">Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="2b516-148">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="2b516-149">Office 365 조직의 권한 상승이 필요한 작업 및 권한이 부여된 작업에 대한 JIT(Just-In-Time) 액세스를 위해 권한이 부여된 액세스 관리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2b516-149">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b516-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b516-150">See also</span></span>

[<span data-ttu-id="2b516-151">클라우드 도입 테스트 랩 가이드를 통해 Microsoft 클라우드 사용해보기</span><span class="sxs-lookup"><span data-stu-id="2b516-151">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="2b516-152">단일 Microsoft Cloud 테스트 랩 가이드 스택</span><span class="sxs-lookup"><span data-stu-id="2b516-152">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)

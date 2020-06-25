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
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Microsoft 365 Enterprise 테스트 랩 가이드

*이는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription. 

TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.

또한, TLG는 응용 프로그램의 개발 및 테스트를 위한 대표적 환경(개발/테스트 환경이라고도 함)을 만들 수도 있습니다.
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

[테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)으로 이동하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

[![Microsoft 365 Enterprise 테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>기본 구성

First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:

- 온-프레미스 구성 요소를 포함하지 않는 클라우드 전용 환경에서 Microsoft 365 Enterprise 기능을 구성하고 시연하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.

- 액티브 디렉토리 도메인 서비스(AD DS - Active Directory Domain Services) 도메인과 같이 온-프레미스 구성 요소를 사용하는 하이브리드 클라우드 환경에서 Microsoft 365 Enterprise 기능 및 성능을 구성하고 시연하려면 [시뮬레이트된 엔터프라이즈 기본 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)을 사용하십시오.

평가판 또는 프로덕션 테스트 환경에 Microsoft 365 E5 라이선스를 추가하지 않고 Office 365 E5에 대한 테스트 환경을 만들 수도 있습니다.
    
## <a name="identity"></a>ID

ID 관련 기능을 시연하려면 다음을 참조하세요.

- [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)
  
   AD DS 도메인 컨트롤러에서 암호 해시 기반 디렉터리 동기화를 사용하도록 설정하고 테스트합니다.

- [통과 인증](pass-through-auth-m365-ent-test-environment.md)
  
   AD DS 도메인 컨트롤러에 대한 통과 인증을 사용하도록 설정하고 테스트합니다.

- [페더레이션 인증](federated-identity-for-your-office-365-dev-test-environment.md)
  
   AD DS 도메인 컨트롤러에 대한 페더레이션 인증을 사용하도록 설정하고 테스트합니다.

- [Azure AD Seamless Single Sign-on](single-sign-on-m365-ent-test-environment.md)
  
   AD DS 도메인 컨트롤러를 사용하여 Azure AD Seamless SSO(Single Sign-On)를 사용하도록 설정하고 테스트합니다.

- [Multi-Factor authentication](multi-factor-authentication-microsoft-365-test-environment.md)
  
   특정 사용자 계정에 대해 휴대폰 기반 다단계 인증을 사용하고 테스트합니다.

- [전역 관리자 계정 보호](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   조건부 액세스 정책을 사용하여 글로벌 관리자 계정을 잠급니다.

- [암호 쓰기 저장](password-writeback-m365-ent-test-environment.md)

   Azure AD에서 AD DS 사용자 계정 암호를 변경하려면 암호 쓰기 저장을 사용하십시오.

- [암호 재설정](password-reset-m365-ent-test-environment.md)

   SSPR(셀프 서비스 암호 재설정)을 사용하여 암호를 재설정합니다.

- [자동 라이선싱 및 그룹 구성원](automate-licenses-group-membership-microsoft-365-test-environment.md)

   자동 라이선싱 및 동적 그룹 등록으로 새 계정을 이전보다 더 쉽게 관리하도록 만듭니다.

- [Azure AD ID 보호](azure-ad-identity-protection-microsoft-365-test-environment.md)

   현재 사용자 계정의 취약성을 검사합니다.

- [ID 및 장치 액세스](identity-device-access-m365-test-environment.md)

   권장된 ID 및 장치 액세스 구성 및 조건부 액세스 정책을 테스트할 수 있는 환경을 만듭니다.


## <a name="mobile-device-management"></a>모바일 장치 관리

모바일 장치 관리와 관련 기능을 시연하려면 다음을 참조하세요.

- [장치 준수 정책](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Windows 10 장치에 대한 사용자 그룹 및 장치 준수 정책을 만듭니다.
    
- [iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   iOS 또는 Android 장치를 등록하고 원격으로 관리합니다.


## <a name="information-protection"></a>정보 보호

정보 보호 관련 기능을 시연하려면 다음을 참조하세요.

- [강화된 Microsoft 365 보안](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Microsoft 365 보안을 개선하도록 설정을 구성하고 기본 제공 보안 도구를 조사합니다.
  
- [데이터 분류](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   SharePoint Online 팀 사이트에서 레이블을 구성하고 문서에 적용합니다.
    
- [권한이 부여된 액세스 관리](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   조직의 권한 상승이 필요한 작업 및 권한이 부여된 작업에 대한 JIT(Just-In-Time) 액세스를 위해 권한이 부여된 액세스 관리를 구성합니다.



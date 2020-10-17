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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 다음 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise의 데모, 개념 증명 또는 개발/테스트 환경을 설정합니다.
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487473"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Microsoft 365 Enterprise 테스트 랩 가이드

*이는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

TLS(테스트 랩 가이드)는 Microsoft 제품을 빠르게 알아보도록 지원합니다. 그리고 간소하지만 대표적인 테스트 환경을 구성하기 위한 지침을 제공합니다. 평가 기간 또는 유료 구독 기간 동안 데모, 사용자 지정 또는 복잡한 개념 증명 생성을 위해 이러한 환경을 사용할 수 있습니다.

TLGs는 모듈식으로 설계 되었습니다. 두 사용자는 서로를 구성 하 여 학습 또는 테스트 요구 사항에 보다 근접 한 여러 구성을 만듭니다. 실무 환경에서 제공 하는 "직접 작성 한"를 사용 하 여 새로운 제품 또는 시나리오의 배포 요구 사항을 이해 하는 데 도움을 줄 수 있으므로 프로덕션 환경의 호스팅 계획을 보다 효율적으로 개선할 수도 있습니다.

또한 TLGs를 사용 하 여 개발/테스트 환경이 라고도 하는 응용 프로그램 개발과 테스트를 위한 대표 환경을 만들 수 있습니다.
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 다음 그래픽을 확장 하거나 [microsoft 365 for Enterprise Test Lab Guide stack를 참조](../downloads/Microsoft365EnterpriseTLGStack.pdf)하세요.

[![Microsoft 365 Enterprise 테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>기본 구성

먼저, [엔터프라이즈에 대해 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)에 대 한 테스트 환경을 만듭니다. 다음과 같은 두 가지 유형의 기본 구성을 만들 수 있습니다.

- [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md) -온-프레미스 구성 요소를 포함 하지 않는 클라우드 전용 환경에서 엔터프라이즈 기능에 대 한 Microsoft 365을 구성 하 고 시연 하려면이를 사용 합니다.

- [시뮬레이트된 엔터프라이즈 기반 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md) -AD DS (Active Directory 도메인 서비스) 도메인과 같은 온-프레미스 구성 요소를 사용 하는 하이브리드 클라우드 환경의 enterprise 기능 및 기능에 대 한 Microsoft 365를 구성 하 고 시연 하려면이 구성을 사용 합니다.

평가판 또는 프로덕션 테스트 환경에 Microsoft 365 E5 라이선스를 추가하지 않고 Office 365 E5에 대한 테스트 환경을 만들 수도 있습니다.
    
## <a name="identity"></a>ID

ID 관련 기능을 시연하려면 다음을 참조하세요.

- [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)
  
   AD DS 도메인 컨트롤러에서 암호 해시 기반 디렉터리 동기화를 사용하도록 설정하고 테스트합니다.

- [통과 인증](pass-through-auth-m365-ent-test-environment.md)
  
   AD DS 도메인 컨트롤러에 대한 통과 인증을 사용하도록 설정하고 테스트합니다.

- [페더레이션 인증](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   AD DS 도메인 컨트롤러에 대한 페더레이션 인증을 사용하도록 설정하고 테스트합니다.

- [Azure AD Seamless Single Sign-on](single-sign-on-m365-ent-test-environment.md)
  
   AD DS 도메인 컨트롤러를 사용 하 여 Azure AD 원활한 Single Sign-on (원활한 SSO)을 설정 하 고 테스트 합니다.

- [Multi-Factor authentication](multi-factor-authentication-microsoft-365-test-environment.md)
  
   특정 사용자 계정에 대해 휴대폰 기반 다단계 인증을 사용하고 테스트합니다.

- [전역 관리자 계정 보호](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   조건부 액세스 정책을 사용하여 글로벌 관리자 계정을 잠급니다.

- [암호 쓰기 저장](password-writeback-m365-ent-test-environment.md)

   Azure AD에서 AD DS 사용자 계정 암호를 변경하려면 암호 쓰기 저장을 사용하십시오.

- [암호 재설정](password-reset-m365-ent-test-environment.md)

   셀프 서비스 암호 재설정을 사용 하 여 암호를 다시 설정 합니다.

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

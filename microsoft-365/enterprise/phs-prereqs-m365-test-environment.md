---
title: Microsoft 365 테스트 환경에서 암호 해시 동기화를 위한 ID 및 장치 액세스 필수 구성 요소
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 암호 해시 동기화를 위한 필수 구성 요소를 사용하여 ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: ab43fc4a41a5faba703cb20fd707fcd18909f42a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210582"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경에서 암호 해시 동기화를 위한 ID 및 장치 액세스 필수 구성 요소

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*

[ID 및 장치 액세스](../security/office-365-security/microsoft-365-policies-configurations.md) 구성은 Azure AD(Azure AD)와 통합된 엔터프라이즈용 Microsoft 365 모든 서비스에 대한 액세스를 보호하기 위한 구성 및 조건부 액세스 Azure Active Directory 집합입니다.

이 문서에서는 ID 및 장치 액세스에 Microsoft 365 암호 해시 [](../security/office-365-security/identity-access-prerequisites.md#prerequisites) 동기화 인증 필요 구성을 사용하여 하이브리드의 요구 사항을 충족하는 테스트 환경을 구성하는 방법을 설명합니다.

이 테스트 환경을 설정하는 데는 10단계가 있습니다.

1. 암호 해시 동기화 테스트 환경에서 시뮬레이션된 엔터프라이즈 만들기
2. Azure AD Seamless Single Sign-On 구성
3. 명명된 위치 구성
4. 암호 쓰기 저장 구성
5. 모든 사용자 계정에 사용할 수 있는 셀프 서비스 암호 재설정 구성
6. 모든 사용자 계정을 위한 다단계 인증 구성
7. 도메인에 가입된 컴퓨터의 자동 장치 Windows 사용
8. Azure AD 암호 보호 구성 
9. Azure AD Identity Protection 사용
10. Exchange Online 및 비즈니스용 Skype Online에 대한 최신 인증을 실행합니다.

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>1단계: 암호 해시 동기화 Microsoft 365 테스트 환경을 사용하여 시뮬레이션된 엔터프라이즈 빌드

암호 해시 동기화 테스트 랩 가이드의 [지침을](password-hash-sync-m365-ent-test-environment.md) 따릅니다.
구성 결과는 다음과 같습니다.

![암호 해시 동기화 테스트 환경을 사용하여 시뮬레이트된 엔터프라이즈입니다.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>2단계: Azure AD Seamless Single Sign-on를 구성합니다.

[Azure AD Seamless Single Sign-on 테스트 랩 가이드의 2 단계](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 지침을 따릅니다.

## <a name="phase-3-configure-named-locations"></a>3단계: 명명된 위치 구성

먼저 조직에서 사용하는 공개 IP 주소 또는 주소 범위를 결정합니다.

그 다음 [Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)에서 명명된 위치 구성의 지침에 따라 주소 또는 주소 범위를 명명된 위치로 추가합니다. 

## <a name="phase-4-configure-password-writeback"></a>4단계: 비밀번호 쓰기 저장 구성

[암호 재작성 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 테스트 랩 가이드의 지침을 따릅니다.

## <a name="phase-5-configure-self-service-password-reset"></a>5단계: 셀프 서비스 암호 재설정 구성

[암호 재설정 3단계](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 테스트 랩 가이드의 지침을 따릅니다. 

특정 Azure AD 그룹의 계정에 대한 비밀번호 재설정을 활성화 할 때 다음 계정을 **비밀번호 재설정** 그룹에 추가합니다.

- 사용자 2
- 사용자 3
- 사용자 4
- 사용자 5

사용자 2 계정에 대해서만 암호 재설정을 테스트합니다.

## <a name="phase-6-configure-multi-factor-authentication"></a>6단계: Multi-Factor Authentication 구성

다음 사용자 계정에 대해 [다중 요소 인증 테스트 랩 가이드의  2 단계](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) 지침을 따르십시오.

- 사용자 2
- 사용자 3
- 사용자 4
- 사용자 5

사용자 2 계정에 대해서만 다중 요소 인증을 테스트하십시오.

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>7단계: 도메인에 가입된 컴퓨터의 자동 장치 Windows 사용 

다음 [지침에 따라](/azure/active-directory/devices/hybrid-azuread-join-plan) 도메인에 가입된 컴퓨터의 자동 장치 등록을 Windows.

## <a name="phase-8-configure-azure-ad-password-protection"></a>8단계: Azure AD 암호 보호 구성 

다음 [지침에 따라](/azure/active-directory/authentication/concept-password-ban-bad) 알려진 약한 암호 및 해당 변형을 차단합니다.

## <a name="phase-9-enable-azure-ad-identity-protection"></a>9단계: Azure AD ID 보호 사용

[Azure Active Directory Identity Protection 테스트 랩 가이드의 2단계](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection)에 있는 지침을 따릅니다. 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>10단계: 온라인 및 Exchange Online 비즈니스용 Skype 사용하도록 설정

Exchange Online의 경우에는 [이 지침](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)을 따릅니다. 

Online 비즈니스용 Skype의 경우:

1. [온라인 비즈니스를 위한 Skype에 연결](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. 이 명령을 실행합니다.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. 이 명령을 사용하여 변경되었는지 확인합니다.

  ```powershell
  Get-CsOAuthConfiguration
  ```

결과는 ID와 장치 액세스를 위해 [암호 해시 동기화 필수 구성을 사용하여 Active Directory](../security/office-365-security/identity-access-prerequisites.md#prerequisites)의 요구 사항을 충족하는 테스트 환경입니다. 

## <a name="next-step"></a>다음 단계

[일반 ID 및 장치 액세스 정책](../security/office-365-security/identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치를 보호하는 정책을 구성합니다.

## <a name="see-also"></a>참고 항목

[추가 ID 테스트 랩 가이드](m365-enterprise-test-lab-guides.md#identity)

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)

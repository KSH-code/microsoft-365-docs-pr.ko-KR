---
title: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On을 구성하고 테스트합니다.'
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083807"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On

*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*

Azure AD Seamless SSO(Single Sign-On)는 조직 네트워크에 연결된 PC 또는 장치에서 사용하는 사용자를 자동으로 로그인합니다. Azure AD Seamless SSO는 추가 온-프레미스 구성 요소를 요구하지 않고 클라우드 기반 응용 프로그램에 쉽게 액세스할 수 있도록 합니다.

이 문서에서는 Azure AD Seamless SSO에 대해 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.

이러한 기능을 설정하는 과정은 다음 두 단계로 진행됩니다.

1.  암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.
2.  APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect를 구성합니다.
    
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다. 
  
- Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 
- Azure AD Connect는 테스트 랩 AD DS(Active Directory 도메인 서비스) 도메인을 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>2단계: APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect 구성

이 단계에서는 APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect를 구성한 다음, 작동하는지 확인합니다.

### <a name="configure-azure-ad-connect-on-app1"></a>APP1에서 Azure AD Connect 구성

1. [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2. APP1의 데스크톱에서 Azure AD Connect를 실행합니다.

3. **시작** 페이지에서 **구성**을 클릭합니다.

4. **추가 작업** 페이지에서 **사용자 로그인 변경**을 클릭한 후 **다음**을 클릭합니다.

5. **Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음**을 클릭합니다.

6. **사용자 로그인** 페이지에서 **Single Sign-On 사용**을 선택한 후 **다음**을 클릭합니다.

7. **Single Sign-On 사용** 페이지에서 **자격 증명 입력**을 클릭합니다.

8. **Windows 보안** 대화 상자에 **user1** 및 user1 계정의 암호를 입력하고 **확인**을 클릭합니다. **다음**을 클릭합니다.

9. **구성 준비 완료** 페이지에서 **구성**을 클릭합니다.

10. **구성 완료** 페이지에서 **끝내기**를 클릭합니다.

11. Azure Portal의 왼쪽 창에서 **Azure Active Directory > Azure AD Connect**를 클릭합니다. **Seamless Single Sign-On** 기능이 **사용**으로 표시되는지 확인합니다.

다음으로, user1 계정의 <strong>user1@testlab.</strong>\<사용자의 공용 도메인> 사용자 이름으로 구독에 로그인하는 기능을 테스트합니다.

1. APP1의 Internet Explorer에서 설정 아이콘을 클릭하고 **인터넷 옵션**을 클릭합니다.
 
2. **인터넷 옵션**에서 **보안** 탭을 클릭합니다.

3. **로컬 인트라넷**을 클릭하고 **사이트**를 클릭합니다.

4. **로컬 인트라넷**에서 **고급**을 클릭합니다.

5. **영역에 이 웹 사이트 추가**에서 **https<span>://</span>autologon.microsoftazuread sso.com**을 입력하고 **추가 > 닫기 > 확인 > 확인**을 클릭합니다.

6. 로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.

7. 로그인하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<공용 도메인> 이름을 지정한 다음 **다음**을 클릭합니다. 암호를 묻는 창이 뜨지 않고 User1로 성공적으로 로그인해야 합니다. 이는 Azure AD Seamless SSO가 제대로 작동하고 있음을 증명합니다.

User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 Azure AD 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
이 구성은 다음으로 이루어집니다.

- Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독(DNS 도메인 Test Lab 포함).\<도메인 이름> 등록됨.
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 
- Azure AD Connect는 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 테스트 랩 AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다. 
- Azure AD Seamless SSO는 시뮬레이트된 인트라넷의 컴퓨터가 사용자 계정 암호를 지정하지 않아도 Microsoft 365 클라우드 리소스에 로그온할 수 있도록 하기 위해 설정됩니다.

프로덕션 환경에서 Azure AD Seamless SSO를 구성하기 위한 정보 및 단계에 대해서는 ID 단계의 [사용자 로그인 간소화](identity-secure-your-passwords.md#identity-sso) 단계를 참조하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)



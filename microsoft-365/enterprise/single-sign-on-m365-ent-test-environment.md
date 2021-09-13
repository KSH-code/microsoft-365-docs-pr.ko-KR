---
title: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On을 구성하고 테스트합니다.'
ms.openlocfilehash: f6fb0ac24f571c329070dd1667f6370c2067d4fd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187892"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On

*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*

Azure AD Seamless Single Sign-On(Seamless SSO)는 사용자가 조직 네트워크에 연결된 PC 또는 장치에 있는 경우 자동으로 로그인합니다. Azure AD Seamless SSO는 추가 사내 구성 요소 없이 클라우드 기반 응용 프로그램에 쉽게 액세스할 수 있도록 합니다.

이 문서에서는 Azure AD Seamless SSO에 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.

Azure AD Seamless SSO 설정에는 다음 두 단계가 있습니다.
- [1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2단계: APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect 구성](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

에 대한 암호 [해시 동기화의 지침을 Microsoft 365.](password-hash-sync-m365-ent-test-environment.md) 

구성 결과는 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경을 사용하여 시뮬레이트된 엔터프라이즈입니다.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다.
  
- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.
- Azure AD 커넥트 APP1에서 실행되어 TESTLAB AD DS(Active Directory 도메인 서비스) 도메인을 구독의 Azure AD 테넌트와 Microsoft 365 동기화합니다.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>2단계: APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect 구성

이 단계에서는 APP1 for Azure AD Seamless 커넥트 Azure AD 2013을 구성한 다음 작동하는지 확인해야 합니다.

### <a name="configure-azure-ad-connect-on-app1"></a>APP1에서 Azure AD Connect 구성

1. [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2. APP1 데스크톱에서 Azure AD 앱을 커넥트.

3. 시작 **페이지에서 구성을** **선택합니다.**

4. 추가 **작업 페이지에서** 사용자 로그인 변경을 선택하고 다음 을 **선택합니다.**

5. Azure **커넥트** 로그인 페이지에서 전역 관리자 계정 자격 증명을 입력하고 다음 을 **선택합니다.**

6. 사용자 **로그인 페이지에서** Single **Sign-On** 사용 을 선택하고 다음 을 **선택합니다.**

7. Single **Sign-On 사용 페이지에서** 자격 증명 **입력 을 선택합니다.**

8. Windows 보안 **대화** 상자에서 user1 및 **user1** 계정의 암호를 입력하고 확인을 선택한 후 다음 을 **선택합니다.**

9. 구성 **준비 완료 페이지에서** 구성을 **선택합니다.**

10. 구성 **완료 페이지에서** 끝내기 **를 선택합니다.**

11. Azure Portal의 왼쪽 창에서 Azure AD Azure Active Directory  >  **를 커넥트.** **Seamless Single Sign-On** 기능이 사용으로 **나타나는지 확인합니다.**

다음으로, 구독에 로그인하는 기능을 테스트하고 구독을 <strong>user1@testlab.</strong>\<*your public domain*> 기능을 테스트합니다.

1. APP1의 Internet Explorer 에서 설정 아이콘을 선택한 다음 인터넷 **옵션 을 선택합니다.**
 
2. 인터넷 **옵션에서** 보안 **탭을** 선택합니다.

3. 로컬 **인트라넷 을** 선택한 다음 사이트를 **선택합니다.**

4. 로컬 **인트라넷에서** 고급 을 **선택합니다.**

5. 이 웹 사이트를 영역 **에 추가에서** **https <span>://</span>** autologon.microsoftazuread-sso.com 를 입력하고 **닫기 확인을**  >    >    >  **선택합니다.**

6. 로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.

7. 로그인하라는 메시지가 표시될 때 로그인을 <strong>user1@testlab.</strong>\<*your public domain*> 이름을 지정한 후 다음 을 **선택합니다.** 암호를 묻는 창이 뜨지 않고 User1로 성공적으로 로그인해야 합니다. 이는 Azure AD Seamless SSO가 제대로 작동하고 있음을 증명합니다.

User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 Azure AD 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경을 사용하는 시뮬레이트된 엔터프라이즈입니다.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

이 구성은 다음으로 이루어집니다.

- DNS Microsoft 365 E5 평가판 또는 유료 구독입니다.\<*your domain name*> 유료 구독.
- 인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.
- Azure AD Connect는 Microsoft 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 TESTLAB AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.
- Azure AD Seamless SSO는 시뮬레이트된 인트라넷의 컴퓨터가 사용자 계정 암호를 지정하지 않고 Microsoft 365 클라우드 리소스에 로그인할 수 있도록 합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)
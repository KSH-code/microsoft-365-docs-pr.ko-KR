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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On을 구성하고 테스트합니다.'
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487609"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On

*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*

Azure AD 원활한 단일 Sign-On (원활한 SSO)은 사용자가 조직 네트워크에 연결 된 Pc 또는 장치에 있는 경우 자동으로 로그인 합니다. Azure AD 원활한 SSO는 추가 온-프레미스 구성 요소 없이도 클라우드 기반 응용 프로그램에 쉽게 액세스할 수 있도록 합니다.

이 문서에서는 Azure AD 원활한 SSO 용 Microsoft 365 테스트 환경을 구성 하는 방법을 설명 합니다.

Azure AD 원활한 SSO를 설정 하는 작업은 다음 두 단계로 이루어집니다.
- [1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2단계: APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect 구성](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

[Microsoft 365에 대 한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)의 지침을 따릅니다. 

구성 결과는 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다.
  
- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.
- Azure AD Connect는 APP1에서 실행 되며, 주기적으로 TESTLAB AD DS (Active Directory 도메인 서비스) 도메인을 Microsoft 365 구독의 Azure AD 테 넌 트와 동기화 합니다.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>2단계: APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect 구성

이 단계에서는 APP1에서 azure AD 원활한 SSO에 대 한 Azure AD Connect를 구성한 다음 작동 하는지 확인 합니다.

### <a name="configure-azure-ad-connect-on-app1"></a>APP1에서 Azure AD Connect 구성

1. [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2. APP1 데스크톱에서 Azure AD Connect를 실행 합니다.

3. **시작 페이지**에서 **구성을**선택 합니다.

4. **추가 작업** 페이지에서 **사용자 로그인 변경을**선택 하 고 **다음**을 선택 합니다.

5. **AZURE AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력 하 고 **다음**을 선택 합니다.

6. **사용자 로그인** 페이지에서 **single sign-on 사용**을 선택 하 고 **다음**을 선택 합니다.

7. **Single Sign-on 사용** 페이지에서 **자격 증명 입력**을 선택 합니다.

8. **Windows 보안** 대화 상자에서 **user1** 과 user1 계정의 암호를 입력 하 고 **확인**을 선택한 후 **다음**을 선택 합니다.

9. **구성 준비 완료** 페이지에서 **구성을**선택 합니다.

10. **구성 완료** 페이지에서 **끝내기**를 선택 합니다.

11. Azure portal의 왼쪽 창에서 **azure Active Directory**  >  **azure AD Connect**를 선택 합니다. **원활한 single sign-on** 기능이 **사용**으로 표시 되는지 확인 합니다.

다음으로 user1@testlab를 사용 하 여 구독에 로그인 하는 기능을 테스트 합니다 <strong>.</strong>\<*your public domain*> 기능을 테스트합니다.

1. APP1의 Internet Explorer에서 설정 아이콘을 선택한 다음 **인터넷 옵션**을 선택 합니다.
 
2. **인터넷 옵션**에서 **보안** 탭을 선택 합니다.

3. **로컬 인트라넷**을 선택한 다음 **사이트**를 선택 합니다.

4. **로컬 인트라넷**에서 **고급**을 선택 합니다.

5. **영역에이 웹 사이트 추가**에서 **https<span>://</span>autologon.microsoftazuread-sso.com**를 입력 하 고 **Add**  >  **닫기**  >  **확인**을 클릭  >  **OK**합니다 .를 선택 합니다.

6. 로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.

7. 로그인 하 라는 메시지가 표시 되 면 <strong>user1@testlab를 지정 합니다.</strong>\<*your public domain*> 이름을 선택한 후 **다음**을 선택 합니다. 암호를 묻는 창이 뜨지 않고 User1로 성공적으로 로그인해야 합니다. 이는 Azure AD Seamless SSO가 제대로 작동하고 있음을 증명합니다.

User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 Azure AD 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

이 구성은 다음으로 이루어집니다.

- DNS 도메인 testlab과 함께 Microsoft 365 E5 평가판 또는 유료 구독입니다.\<*your domain name*> 유료 구독.
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.
- Azure AD Connect는 Microsoft 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 TESTLAB AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.
- Azure AD 원활한 SSO는 시뮬레이트된 인트라넷의 컴퓨터가 사용자 계정 암호를 지정 하지 않고 Microsoft 365 클라우드 리소스에 로그인 할 수 있도록 하기 위해 사용 하도록 설정 됩니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)

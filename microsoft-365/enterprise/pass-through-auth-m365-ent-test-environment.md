---
title: Microsoft 365 테스트 환경을 위한 통과 인증
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 통과 인증을 구성합니다.'
ms.openlocfilehash: dcc23662683ffaf65a0ec5fa3698f729dc215af7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163363"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 통과 인증

*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*

Microsoft 클라우드 기반 서비스 및 응용 프로그램에 대한 인증을 위해 AD DS (Active Directory 도메인 서비스) 인프라를 직접 사용하려는 조직은 통과 인증을 사용할 수 있습니다. 이 문서에서는 통과 인증에 대해 Microsoft 365 테스트 환경을 구성하여 다음과 같은 결과를 얻는 방법을 설명합니다.
  
![통과 인증 테스트 환경을 사용하는 시뮬레이트된 엔터프라이즈입니다.](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
이 테스트 환경의 2가지 주요 설정 단계는 다음과 같습니다.

1.    암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.
2.    통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.
    
![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](../downloads/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경을 사용하여 시뮬레이트된 엔터프라이즈입니다.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다. 
  
- Microsoft 365 E5 구독 또는 유료 구독을 선택합니다.
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. Azure AD Connect는 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>2단계: 통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.

이 단계에서는 통과 인증을 사용하도록 APP1에서 Azure AD Connect를 구성한 다음 작동하는지 확인합니다.

### <a name="configure-azure-ad-connect-on-app1"></a>APP1에 Azure AD Connect 설치

1.    [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2.    APP1의 데스크톱에서 Azure AD Connect를 실행합니다.

3.    **시작** 페이지에서 **구성** 을 클릭합니다.

4.    추가 작업 페이지에서 **사용자 로그인 변경** 을 클릭한 후 **다음** 을 클릭합니다.

5.    **Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음** 을 클릭합니다.

6.    **사용자 로그인** 페이지에서 **통과 인증** 를 클릭한 다음, **다음** 을 클릭합니다.

7.    **구성 준비 완료** 페이지에서 **구성** 을 클릭합니다.

8.    **구성 완료** 페이지에서 **끝내기** 를 클릭합니다.

9.    Azure Portal의 왼쪽 창에서 **Azure Active Directory > Azure AD Connect** 를 클릭합니다. **통과 인증** 기능이 **사용** 으로 표시되는지 확인합니다.

10.    **통과 인증** 을 클릭하세요. **통과 인증** 창에는 인증 에이전트가 설치된 서버가 나열됩니다. 목록에 APP1이 표시되었는지 확인해야 합니다. 그 다음 **통과 인증** 창을 닫습니다.

다음으로, 구독에 로그인하는 기능을 테스트하고 구독을 <strong>user1@testlab.</strong>\<your public domain> 기능을 테스트합니다.

1. APP1에서 로그아웃한 다음 다른 계정을 지정하여 다시 로그인합니다.

2. 사용자 이름 및 암호를 입력하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<your public domain> 및 User1 암호를 입력합니다. User1으로 성공적으로 로그인해야 합니다.

User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경을 사용하는 시뮬레이트된 엔터프라이즈입니다.](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
이 구성은 다음으로 이루어집니다.

- DNS Microsoft 365 E5 평가판 또는 유료 구독입니다.\<your domain name> 유료 구독.
- 인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 인증 에이전트는 APP1에서 실행되어 Microsoft 365 구독의 Azure AD 테넌트의 통과 인증 요청을 처리합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)
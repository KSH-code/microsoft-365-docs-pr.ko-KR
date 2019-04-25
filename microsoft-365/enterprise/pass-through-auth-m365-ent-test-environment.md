---
title: Microsoft 365 테스트 환경을 위한 통과 인증
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 통과 인증을 구성합니다.'
ms.openlocfilehash: e925f0b48194c94993e7bf3e08f1f18650b19a23
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290947"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 통과 인증

Microsoft 클라우드 기반 서비스 및 응용 프로그램에 대한 인증을 위해 AD DS (Active Directory 도메인 서비스) 인프라를 직접 사용하려는 조직은 통과 인증을 사용할 수 있습니다. 이 문서에서는 통과 인증에 대해 Microsoft 365 테스트 환경을 구성하여 다음과 같은 결과를 얻는 방법을 설명합니다.
  
![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
이 테스트 환경의 2가지 주요 설정 단계는 다음과 같습니다.

1.  암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.
2.  통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.
    
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다. 
  
- Office 365 E5 및 EMS E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. Azure AD Connect는 테스트 랩 AD DS(Active Directory 도메인 서비스) 도메인을 Office 365 및 EMS E5 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>2단계: 통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.

이 단계에서는 통과 인증을 사용하도록 APP1에서 Azure AD Connect를 구성한 다음 작동하는지 확인합니다.

### <a name="configure-azure-ad-connect-on-app1"></a>APP1에 Azure AD Connect 설치

1.  [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2.  APP1의 데스크톱에서 Azure AD Connect를 실행합니다.

3.  **시작** 페이지에서 **구성**을 클릭합니다.

4.  추가 작업 페이지에서 **사용자 로그인 변경**을 클릭한 후 **다음**을 클릭합니다.

5.  **Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음**을 클릭합니다.

6.  **사용자 로그인** 페이지에서 **통과 인증**를 클릭한 다음, **다음**을 클릭합니다.

7.  **구성 준비 완료** 페이지에서 **구성**을 클릭합니다.

8.  **구성 완료** 페이지에서 **끝내기**를 클릭합니다.

9.  Azure Portal의 왼쪽 창에서 **Azure Active Directory > Azure AD Connect**를 클릭합니다. **통과 인증** 기능이 **사용**으로 표시되는지 확인합니다.

10. **통과 인증**을 클릭하세요. **통과 인증** 창에는 인증 에이전트가 설치된 서버가 나열됩니다. 목록에 APP1이 표시되었는지 확인해야 합니다. 그 다음 **통과 인증** 창을 닫습니다.

다음으로, user1 계정의 <strong>user1@testlab.</strong>\<사용자의 공용 도메인> 사용자 이름으로 Office 365 구독에 로그인하는 기능을 테스트합니다.

1. APP1에서 Office 365로부터 로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.

2. 사용자 이름 및 암호를 지정하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<사용자의 공용 도메인> 및 User1 암호를 입력합니다. User1으로 성공적으로 로그인해야 합니다.

User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 Office 365 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
이 구성은 다음으로 이루어집니다.

- Office 365 E5 및 EMS E5 평가판 또는 DNS 도메인 TESTLAB.\<도메인 이름>이 등록된 유료 구독.
- 인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 인증 에이전트는 APP1에서 실행되어 Office 365 및 EMS E5 구독의 Azure AD 테넌트로부터의 통과 인증 요청을 처리합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)



---
title: Microsoft 365 테스트 환경을 위한 암호 해시 동기화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 및 로그인을 구성하고 보여 줍니다.'
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487461"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 암호 해시 동기화

*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*

다수의 조직은 Azure AD Connect와 암호 해시 동기화를 사용하여 온-프레미스 AD DS(Active Directory Domain Services) 포리스트의 계정 집합을 Microsoft 365 구독의 Azure AD 테넌트의 계정 집합과 동기화합니다. 

이 문서에서는이 구성을 통해 Microsoft 365 테스트 환경에 암호 해시 동기화를 추가 하는 방법에 대해 설명 합니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
이 테스트 환경에 대 한 설정에는 다음 세 단계가 포함 됩니다.
- [1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [2단계: 테스트 랩 도메인 만들기 및 등록](#phase-2-create-and-register-the-testlab-domain)
- [3단계: APP1에 Azure AD Connect 설치](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기

[Microsoft 365에 대해 시뮬레이트된 엔터프라이즈 기반 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다. 구성 결과는 다음과 같습니다.
  
![시뮬레이트된 엔터프라이즈 기본 구성](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다.
  
- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 DC1, APP1 및 CLIENT1 가상 머신으로 구성 됩니다. DC1은 testlab의 도메인 컨트롤러입니다. *공용 도메인 이름을* <AD DS domain> 합니다.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>2단계: 테스트 랩 도메인 만들기 및 등록

이 단계에서 공용 DNS 도메인을 추가 하 고 구독에 추가 합니다.

먼저 공용 DNS 등록 공급자와 함께 사용 하 여 현재 도메인 이름을 기반으로 하는 새 공용 DNS 도메인 이름을 만든 다음 구독에 추가 합니다. Testlab 이름을 사용 하는 것이 좋습니다 ( ** *공용 도메인* > <합니다.** 예를 들어 공용 도메인 이름이 ** <span>contoso</span>.com**인 경우 공용 도메인 이름: ** <span>testlab</span>** 를 추가 합니다.
  
다음으로, testlab을 추가 합니다. 도메인 등록 프로세스를 진행 하 여 Microsoft 365 평가판 또는 유료 구독에 대 한 ** *공용 도메인* > 도메인 <합니다.** 이는 testlab에 DNS 레코드를 추가 하는 것으로, ** *공용 도메인* > 도메인 <합니다.** 자세한 내용은 [365 Microsoft에 도메인 추가](../admin/setup/add-domain.md)를 참조 하세요.

구성 결과는 다음과 같습니다.
  
![테스트 랩 도메인 이름 등록](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
이 구성은 다음으로 이루어집니다.

- DNS 도메인 testlab을 사용한 Microsoft 365 E5 평가판 또는 유료 구독 <등록 된> *공용 도메인 이름* 입니다.
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.

Testlab이 <> 현재 *공용 도메인 이름* 입니다.

- 공용 DNS 레코드에서 지원도비니다.
- Microsoft 365 구독에 등록되었습니다.
- 시뮬레이트된 인트라넷의 AD DS 도메인입니다.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>3단계: APP1에 Azure AD Connect 설치

이 단계에서는 APP1에서 Azure AD Connect 도구를 설치 및 구성 하 고, 작동 하는지 확인 합니다.
  
먼저 APP1에서 Azure AD Connect를 설치 하 고 구성 합니다.

1. [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\\User1 계정을 사용하여 APP1에 연결합니다.
    
2. APP1의 바탕 화면에서 관리자 수준 Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행하여 Internet Explorer 강화 보안을 사용하지 않습니다.
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. 작업 표시줄에서 **Internet Explorer** 를 선택 하 고로 이동 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 합니다.
    
4. Microsoft Azure Active Directory 연결 페이지에서 **다운로드**를 선택 하 고 **실행**을 선택 합니다.
    
5. **AZURE AD Connect 시작** 페이지에서 **동의 함**을 선택 하 고 **계속**을 선택 합니다.
    
6. **빠른 설정** 페이지에서 **빠른 설정 사용**을 선택 합니다.
    
7. **AZURE AD에 연결** 페이지에서 **사용자 이름** 에 전역 관리자 계정 이름을 입력 하 고 **암호**에 암호를 입력 한 후 **다음**을 선택 합니다.
    
8. **AD DS에 연결** 페이지에서 **사용자 이름** 에 **testlab \\ User1** 을 입력 하 고 **암호**에 암호를 입력 한 후 **다음**을 선택 합니다.
    
9. **구성 준비 완료** 페이지에서 **설치**를 선택 합니다.
    
10. **구성 완료** 페이지에서 **끝내기**를 선택 합니다.
    
11. Internet Explorer에서 Microsoft 365 관리 센터([https://portal.microsoft.com](https://portal.microsoft.com))로 이동합니다.
    
12. 왼쪽 탐색 창에서 **사용자 > 활성 사용자**를 선택 합니다.
    
    **User1**이라는 계정을 유의합니다. 이 계정은 TESTLAB AD DS 도메인의 계정이며 디렉터리 동기화가 성공했다는 증거입니다.
    
13. **User1** 계정을 선택한 다음 **라이선스 및 앱**을 선택 합니다.
    
14. **제품 라이선스**에서 사용자의 위치를 선택 하 고 (필요한 경우) **Office 365 e5** 라이선스를 사용 하지 않도록 설정한 다음 **Microsoft 365 e5** 라이선스를 사용 하도록 설정 합니다. 

15. 페이지 아래쪽에서 **저장** 을 선택한 다음 **닫기를**선택 합니다.
    
다음으로, user1@testlab 사용 하 여 구독에 로그인 하는 기능을 테스트 **합니다. <사용자의 *도메인 이름* > ** user1 계정의 사용자 이름입니다.

1. APP1에서 로그아웃한 다음 다른 계정을 지정하여 다시 로그인합니다.

2. 사용자 이름 및 암호를 입력 하 라는 메시지가 표시 되 면 user1@testlab를 지정 하 고 ** *도메인 이름* > ** 및 user1 암호를 <합니다. User1으로 성공적으로 로그인해야 합니다.
 
User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다. 

구성 결과는 다음과 같습니다.

![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

이 구성은 다음으로 이루어집니다. 
  
- DNS 도메인 TESTLAB을 사용한 Microsoft 365 E5 또는 Office 365 E5 평가판 또는 유료 구독 <등록 된 *도메인 이름*> 합니다.
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다. Azure AD Connect는 APP1에서 실행 되며, 주기적으로 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테 넌 트와 동기화 합니다.
- TESTLAB AD DS 도메인의 User1 계정이 Azure AD 테넌트와 동기화되었습니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)

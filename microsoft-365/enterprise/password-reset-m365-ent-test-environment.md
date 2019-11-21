---
title: Microsoft 365 테스트 환경을 위한 암호 재설정
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
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
description: '요약: Microsoft 365 테스트 환경을 위한 암호 재설정을 구성하고 테스트합니다.'
ms.openlocfilehash: 100db14b7940d68a185c3f6065df053aed7fbf73
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757715"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 암호 재설정

*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*

Azure AD(Azure Active Directory) SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다. 

이 문서에서는 Microsoft 365 테스트 환경에서 암호 재설정을 구성 및 테스트하는 방법을 세 단계로 설명합니다.

1.  Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2.  암호 쓰기 저장을 사용하도록 설정
3.  사용자 2 계정에 대한 암호 재설정을 구성하고 테스트합니다.
    
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

먼저 [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다. 
  
- Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 
- Azure AD Connect는 테스트 랩 AD DS(Active Directory 도메인 서비스) 도메인을 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.


## <a name="phase-2-enable-password-writeback"></a>2단계: 암호 쓰기 저장을 사용하도록 설정

[암호 쓰기 저장 테스트 랩 가이드의 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)에 있는 지침을 따릅니다.

암호 쓰기 저장을 사용하려면 암호를 재설정할 수 있도록 지정해야 합니다.
  
## <a name="phase-3-configure-and-test-password-reset"></a>3단계: 암호 재설정 구성 및 테스트

이 단계에서는 그룹 구성원 자격을 통해 Azure 테넌트에서 암호 재설정을 구성한 후 작동하는지 확인합니다.

먼저, 특정 Azure AD 그룹에서 계정에 대해 암호 재설정을 사용하도록 설정합니다.

1. 브라우저의 비공개 인스턴스에서 [https://portal.azure.com](https://portal.azure.com)을 열고 전역 관리자 계정의 자격 증명으로 로그인합니다.
2. Azure Portal에서 **Azure Active Directory > 그룹 > 새 그룹**을 차례로 클릭합니다.
3. **그룹 유형**을 **보안**으로, **그룹 이름**을 **PWReset**으로, **구성원 자격 유형**을 **할당됨**으로 설정합니다. **만들기**를 클릭합니다.
5. 목록에서 **PWReset** 그룹을 클릭한 후 **구성원**을 클릭합니다.
6. **구성원 추가**를 클릭하고 **사용자 2**를 클릭한 후 **선택**을 클릭합니다. **PWReset** 및 **그룹** 페이지를 닫습니다.
7. Azure Active Directory 페이지에서 **암호 재설정**을 클릭합니다.
8. **속성** 페이지의 옵션 **셀프 서비스 암호 재설정이 사용하도록 설정됨**에서 **선택됨**을 선택합니다.
9. **그룹 선택**에서 **PWReset**을 선택한 후 **저장**을 클릭합니다.
10. 비공개 브라우저 인스턴스를 닫습니다.

다음으로, 사용자 2 계정에 대한 암호 재설정을 테스트합니다.

1. 새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)으로 이동합니다.
2. 사용자 2 계정 자격 증명으로 로그인합니다.
3. **Don’t lose access to your account**(계정에 대한 액세스 유지)에서 인증 전화를 휴대폰 번호로, 인증 이메일을 회사 또는 개인 이메일 계정으로 설정합니다.
4. 둘 다 확인되면 **정상**을 클릭하고 브라우저의 비공개 인스턴스를 닫습니다.
5. 새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/sspr](https://aka.ms/sspr)로 이동합니다.
6. 사용자 2 계정 자격 증명으로 로그인하고 CAPTCHA의 문자를 입력한 후 **다음**을 클릭합니다.
8. **확인 단계 1**에서 **Email my alternate email**(다른 이메일로 메일 보내기)를 클릭한 다음, **이메일**을 클릭합니다. 이메일을 받으면 확인 코드를 입력하고 **다음**을 클릭합니다.
9. **Get back into your account(계정에 다시 접속)** 에서 사용자 2 계정에 대한 새 암호를 입력하고 **마침**을 클릭합니다. 사용자 2 계정의 변경된 암호를 적어 안전한 위치에 저장합니다.
10. 동일한 브라우저의 별도 탭에서 [https://portal.office.com](https://portal.office.com)으로 이동한 후 사용자 2 계정 이름과 해당 새 암호로 로그인합니다. **Microsoft Office 홈** 페이지가 표시됩니다.

프로덕션 환경에서 암호 재설정을 구성하기 위한 정보 및 단계에 대해서는 ID 단계의 [암호 재설정 간소화](identity-secure-your-passwords.md#identity-pw-reset) 단계를 참조하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

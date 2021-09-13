---
title: Microsoft 365 테스트 환경을 위한 암호 재설정
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/13/2019
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
description: '요약: Microsoft 365 테스트 환경을 위한 암호 재설정을 구성하고 테스트합니다.'
ms.openlocfilehash: aa332b2778aefa84948a9bc57d20d28f117a4df3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213805"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 암호 재설정

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*

Azure AD(Azure Active Directory) SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다.

이 문서에서는 테스트 환경에서 암호 재설정을 구성하고 테스트하는 Microsoft 365 설명합니다.

SSPR 설정에는 다음 세 단계가 있습니다.
- [1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2단계: 암호 쓰기 저장을 사용하도록 설정](#phase-2-enable-password-writeback)
- [3단계: 암호 재설정 구성 및 테스트](#phase-3-configure-and-test-password-reset)
    
![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

먼저 암호 해시 [동기화의 지침을 따릅니다.](password-hash-sync-m365-ent-test-environment.md) 

구성 결과는 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경을 사용하여 시뮬레이트된 엔터프라이즈입니다.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다.
  
- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.
- Azure AD Connect는 TESTLAB AD DS(Active Directory Domain Services) 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-enable-password-writeback"></a>2단계: 암호 쓰기 저장을 사용하도록 설정

[암호 쓰기 저장 테스트 랩 가이드의 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)에 있는 지침을 따릅니다.

암호 쓰기 저장을 사용하려면 암호를 재설정할 수 있도록 지정해야 합니다.
  
## <a name="phase-3-configure-and-test-password-reset"></a>3단계: 암호 재설정 구성 및 테스트

이 단계에서는 그룹 구성원 자격을 통해 Azure AD 테넌트에서 암호 재설정을 구성한 다음 작동하는지 확인해야 합니다.

먼저, 특정 Azure AD 그룹에서 계정에 대해 암호 재설정을 사용하도록 설정합니다.

1. 브라우저의 비공개 인스턴스에서 [https://portal.azure.com](https://portal.azure.com)을 열고 전역 관리자 계정의 자격 증명으로 로그인합니다.
2. Azure Portal에서 그룹 **Azure Active Directory**  >    >  **그룹을 선택합니다.**
3. **그룹 유형** 을 **보안** 으로, **그룹 이름** 을 **PWReset** 으로, **구성원 자격 유형** 을 **할당됨** 으로 설정합니다.
4. 구성원을 **선택하고** 사용자 **3을 찾아 선택하고** 선택 을 선택한 다음 만들기를  **선택합니다.**
5. **그룹** 창을 닫습니다.
6. 왼쪽 Azure Active Directory 창에서 암호 **재설정을** 선택합니다.
7. **암호 재설정 속성** 창의 옵션 **셀프 서비스 암호 재설정이 사용하도록 설정됨** 에서 **선택됨** 을 선택합니다.
8. 그룹 **선택을 선택하고** **PWReset** 그룹을 선택한 다음 **저장을**  >  **선택합니다.**
9. 비공개 브라우저 인스턴스를 닫습니다.

다음으로 사용자 3 계정에 대한 암호 재설정을 테스트합니다.

1. 새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)으로 이동합니다.
1. 사용자 3 계정 자격 증명으로 로그인합니다.
1. 필요한 **추가 정보에서** 다음 을 **선택합니다.** 
1. **계정에 대한 액세스 유지** 에서 인증 전화를 휴대폰 번호로, 인증 이메일을 회사 또는 개인 이메일 계정으로 설정합니다.
1. 두 가지를 모두 확인한 후 **양호한** 모양을 선택한 다음 브라우저의 개인 인스턴스를 닫습니다.
1. 새 개인 브라우저 인스턴스에서 로 [https://aka.ms/sspr](https://aka.ms/sspr) 이동하세요.
1. 사용자 3 계정 이름을 입력하고 CAPTCHA의 문자를 입력한 후 다음 을 **선택합니다.**
1. 확인 **1단계에서** 내 대체 전자 **메일 전자 메일을** 선택한 다음 전자 메일을 **선택합니다.** 전자 메일을 받으면 확인 코드를 입력하고 다음 을 **선택합니다.**
1. 계정으로 **돌아가기에서** 사용자 3 계정에 대한 새 암호를 입력하고 마친 을 **선택합니다.** 사용자 3 계정의 변경된 암호를 적어놓고 안전한 장소에 저장합니다.
1. 동일한 브라우저의 별도 탭에서 [https://admin.microsoft.com](https://admin.microsoft.com)으로 이동한 후 사용자 3 계정 이름과 해당 새 암호로 로그인합니다. **Microsoft Office 홈** 페이지가 표시됩니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)
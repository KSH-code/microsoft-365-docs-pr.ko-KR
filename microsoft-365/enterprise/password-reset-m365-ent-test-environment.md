---
title: Microsoft 365 테스트 환경을 위한 암호 재설정
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487427"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 암호 재설정

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

Azure AD(Azure Active Directory) SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다.

이 문서에서는 Microsoft 365 테스트 환경에서 암호 재설정을 구성 및 테스트 하는 방법을 설명 합니다.

SSPR을 설정 하는 단계는 다음 세 단계로 이루어집니다.
- [1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2단계: 암호 쓰기 저장을 사용하도록 설정](#phase-2-enable-password-writeback)
- [3단계: 암호 재설정 구성 및 테스트](#phase-3-configure-and-test-password-reset)
    
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

먼저 [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)의 지침을 따릅니다. 

구성 결과는 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다.
  
- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.
- Azure AD Connect는 TESTLAB AD DS(Active Directory Domain Services) 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-enable-password-writeback"></a>2단계: 암호 쓰기 저장을 사용하도록 설정

[암호 쓰기 저장 테스트 랩 가이드의 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)에 있는 지침을 따릅니다.

암호 쓰기 저장을 사용하려면 암호를 재설정할 수 있도록 지정해야 합니다.
  
## <a name="phase-3-configure-and-test-password-reset"></a>3단계: 암호 재설정 구성 및 테스트

이 단계에서는 그룹 멤버 자격을 통해 Azure AD 테 넌 트에서 암호 재설정을 구성한 다음 작동 하는지 확인 합니다.

먼저, 특정 Azure AD 그룹에서 계정에 대해 암호 재설정을 사용하도록 설정합니다.

1. 브라우저의 비공개 인스턴스에서 [https://portal.azure.com](https://portal.azure.com)을 열고 전역 관리자 계정의 자격 증명으로 로그인합니다.
2. Azure portal에서 **azure Active Directory**  >  **그룹**  >  **새 그룹**을 선택 합니다.
3. **그룹 유형**을 **보안**으로, **그룹 이름**을 **PWReset**으로, **구성원 자격 유형**을 **할당됨**으로 설정합니다.
4. **구성원**을 선택 하 고 **사용자 3**을 찾아서 선택한 다음, **선택을**선택 하 고 **만들기**를 선택 합니다.
5. **그룹** 창을 닫습니다.
6. Azure Active Directory 창의 왼쪽 탐색 창에서 **암호 재설정** 을 선택 합니다.
7. **암호 재설정 속성** 창의 옵션 **셀프 서비스 암호 재설정이 사용하도록 설정됨**에서 **선택됨**을 선택합니다.
8. **그룹 선택을**선택 하 고 **PWReset** 그룹을 선택한 다음 **Select**  >  **저장**선택을 선택 합니다.
9. 비공개 브라우저 인스턴스를 닫습니다.

다음으로 사용자 3 계정에 대 한 암호 재설정을 테스트 합니다.

1. 새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)으로 이동합니다.
1. 사용자 3 계정 자격 증명으로 로그인합니다.
1. **필요한 추가 정보**에서 **다음**을 선택 합니다. 
1. **계정에 대한 액세스 유지**에서 인증 전화를 휴대폰 번호로, 인증 이메일을 회사 또는 개인 이메일 계정으로 설정합니다.
1. 둘 다 확인 되 면 **정상 모양**을 선택 하 고 브라우저의 비공개 인스턴스를 닫습니다.
1. 새 개인 브라우저 인스턴스에서로 이동 [https://aka.ms/sspr](https://aka.ms/sspr) 합니다.
1. 사용자 3 계정 이름을 입력 하 고 CAPTCHA의 문자를 입력 한 후 **다음**을 선택 합니다.
1. **확인 하려면 1 단계** **대체 전자 메일**을 선택한 후 **전자**메일을 선택 합니다. 전자 메일을 받으면 확인 코드를 입력 하 고 **다음**을 선택 합니다.
1. **계정으로 다시 돌아가**사용자 3 계정의 새 암호를 입력 하 고 **마침을**선택 합니다. 사용자 3 계정의 변경된 암호를 적어놓고 안전한 장소에 저장합니다.
1. 동일한 브라우저의 별도 탭에서 [https://portal.office.com](https://portal.office.com)으로 이동한 후 사용자 3 계정 이름과 해당 새 암호로 로그인합니다. **Microsoft Office 홈** 페이지가 표시됩니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)

---
title: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: '요약: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장을 구성합니다.'
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487131"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 암호 쓰기 저장

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

사용자는 암호 쓰기 저장을 사용 하 여 Azure Active Directory (Azure AD)를 통해 암호를 업데이트할 수 있으며, 그러면 로컬 AD DS (Active Directory 도메인 서비스)에 복제 됩니다. 암호 쓰기 저장을 사용 하는 경우 사용자는 원래 사용자 계정이 저장 되는 온-프레미스 AD DS를 통해 암호를 업데이트할 필요가 없습니다. 이는 온-프레미스 네트워크에 대 한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에 게 도움이 됩니다.

이 문서에서는 암호 쓰기 저장을 위해 Microsoft 365 테스트 환경을 구성 하는 방법을 설명 합니다.

암호 쓰기 저장을 위한 테스트 환경을 구성 하는 작업은 다음 두 단계로 이루어집니다.
- [1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

먼저 [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)의 지침을 따릅니다. 구성 결과는 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다.
  
- Microsoft 365 E5 평가판 또는 유료 구독
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.
- Azure AD Connect는 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정

먼저 User 1 계정이 전역 관리자 역할을 가지도록 구성합니다.

1. [Microsoft 365 관리 센터](https://portal.microsoft.com)에서 글로벌 관리자 계정으로 로그인합니다.

2. **활성 사용자**를 선택 합니다.
 
3. **활성 사용자** 페이지에서 **user1** 계정을 선택 하 고,

4. **User1** 창에서 **역할**옆에 있는 **편집** 을 선택 합니다.

5. User1에 대 한 **사용자 역할 편집** 창에서 **전역 관리자**를 선택 하 고 **저장**을 선택한 다음 **닫기를**선택 합니다.

다음으로, 사용자 1 계정을 테스트 랩 AD DS 도메인의 다른 사용자를 대신하여 암호를 변경할 수 있는 보안 설정으로 구성합니다.

1. [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2. APP1의 바탕 화면에서 **시작**을 선택 하 고 **활성**을 입력 한 후 **active Directory 사용자 및 컴퓨터**를 선택 합니다.

3. 메뉴 모음에서 **보기**를 선택 합니다. **고급 기능이** 설정 되어 있지 않은 경우이를 선택 하 여 사용 하도록 설정 합니다.

4. 트리 창에서 도메인을 선택 하 고 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **보안** 탭을 선택 합니다.

5. **고급**을 선택 합니다.

6. **사용 권한** 탭에서 **추가**를 선택 합니다.

7. **보안 주체 선택을**선택 하 고 **User1**을 입력 한 다음 **확인**을 선택 합니다.

8. **적용 대상**에서 **하위 항목 사용자 개체**를 선택합니다.

9. **사용 권한**에서 다음을 선택합니다.

    - **암호 변경**
    - **암호 다시 설정**

10. **속성**에서 다음을 선택합니다.
    - **lockoutTime 쓰기**
    - **pwdLastSet 쓰기**

11. **확인** 을 세 번 선택 하 여 변경 내용을 저장 합니다.

12. **Active Directory 사용자 및 컴퓨터**를 닫습니다.

다음으로 암호 쓰기 저장을 위해 APP1에서 Azure AD Connect를 구성합니다.

1. 필요한 경우 TESTLAB\User1 계정으로 APP1에 연결합니다.

2. APP1의 데스크톱에서 **Azure AD Connect**를 두 번 클릭합니다.

3. **시작 페이지**에서 **구성을**선택 합니다.

4. **추가 작업** 페이지에서 **동기화 옵션 사용자 지정**을 선택 하 고 **다음**을 선택 합니다.

5. **AZURE AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력 하 고 **다음**을 선택 합니다.

6. **디렉터리 연결** 및 **도메인/OU 필터링** 페이지에서 **다음**을 선택 합니다.

7. **선택적 기능** 페이지에서 **암호 쓰기 저장**을 선택 하 고 **다음**을 선택 합니다.

8. **구성 준비 완료** 페이지에서 **구성을** 선택 하 고 프로세스가 완료 될 때까지 기다립니다.

9. 구성 완료가 표시 되 면 **끝내기**를 선택 합니다.

이제 시뮬레이트된 인트라넷의 가상 네트워크에 연결 되지 않은 컴퓨터의 사용자에 대 한 암호 쓰기 저장을 테스트할 준비가 되었습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

이 구성은 다음으로 이루어집니다.

- DNS 도메인 TESTLAB과 함께 Microsoft 365 E5 평가판 또는 유료 구독입니다.\<*your domain name*> 유료 구독.
- 인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.
- Azure AD Connect는 Microsoft 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 TESTLAB AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.
- 암호 쓰기 저장 기능은 사용자가 간소화된 인트라넷에 연결하지 않고도 Azure AD를 통해 암호를 변경할 수 있도록 합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)



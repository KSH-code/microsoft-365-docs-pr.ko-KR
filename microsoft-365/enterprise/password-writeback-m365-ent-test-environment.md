---
title: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장을 구성합니다.'
ms.openlocfilehash: 748ccaf8601d9e9564d176f2368e3cc71f926208
ms.sourcegitcommit: fec2c756121006069dc3e5b8dbd6c4abe7a3c63c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "27214436"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경을 위한 암호 쓰기 저장

암호 쓰기 저장은 Azure AD(Active Directory)를 통해 자신의 암호를 업데이트하도록 허용합니다. 이는 로컬 Windows Server AD(Active Directory)에 복제됩니다. 암호 쓰기 저장을 사용하면 사용자가 원래 사용자 계정이 저장된 온-프레미스 Windows Server AD를 통해 암호를 업데이트할 필요가 없습니다. 이는 온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 도움이 됩니다.

이 문서에서는 암호 쓰기 저장에 대해 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.

이러한 기능을 설정하는 과정은 다음 두 단계로 진행됩니다.

1.  암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.
2.  테스트 랩 Windows Server AD 도메인에 대한 암호 쓰기 저장을 사용하도록 설정합니다.
    
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성

[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
이 구성은 다음으로 이루어집니다. 
  
- Office 365 E5 및 EMS E5 평가판 또는 영구 구독
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 
- Azure AD Connect는 테스트 랩 Windows Server AD 도메인을 Office 365 및 EMS E5 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a>2단계: 테스트 랩 Windows Server AD 도메인에 대한 암호 쓰기 저장을 사용하도록 설정합니다.

먼저 User 1 계정이 전역 관리자 역할을 가지도록 구성합니다.

1. [Office 포털](https://office.com)에서 전역 관리자 계정으로 로그인합니다.

2. **관리자** 타일을 클릭합니다. 브라우저의 새 **Microsoft 365 관리 센터** 탭에서 **활성 사용자**를 클릭합니다.
 
3. **활성 사용자** 페이지에서 **user1** 계정을 클릭하고,

4. **user1** 창에서 **역할** 옆의 **편집**을 클릭합니다.

5. user1의 **사용자 역할 편집** 창에서 **전역 관리자**를 클릭합니다. **저장**을 클릭한 다음 **닫기**를 클릭합니다.

다음으로, 사용자 1 계정을 테스트 랩 Windows Server AD 도메인의 다른 사용자를 대신하여 암호를 변경할 수 있는 보안 설정으로 구성합니다.

1. [Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.

2.  APP1의 바탕 화면에서 **시작**을 클릭하고 **활성**을 입력한 후 **Active Directory 사용자 및 컴퓨터**를 클릭합니다.

3. 메뉴 모음에서 **보기**를 클릭합니다. **고급 기능**이 사용 안 함으로 되어 있으면 사용하도록 설정합니다.

4. 트리 창에서 도메인을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭한 다음 **보안** 탭을 클릭합니다.

5. **고급**을 클릭합니다.

6. **사용 권한** 탭에서 **추가**를 클릭합니다.

7. **보안 주체 선택**을 클릭하고 **User1**을 입력 한 다음 **확인**을 클릭합니다.

8. **적용 대상**에서 **하위 항목 사용자 개체**를 선택합니다.

9. **사용 권한**에서 다음을 선택합니다.

    - 암호 변경
    - 암호 다시 설정

10. **속성**에서 다음을 선택합니다.
    - lockoutTime 쓰기
    - pwdLastSet 쓰기

11. **확인**을 세 번 클릭하여 변경 내용을 저장합니다.

12. **Active Directory 사용자 및 컴퓨터**를 닫습니다.

다음으로 암호 쓰기 저장을 위해 APP1에서 Azure AD Connect를 구성합니다.

1. 필요한 경우 TESTLAB\User1 계정으로 APP1에 연결합니다.

2. APP1의 데스크톱에서 **Azure AD Connect**를 두 번 클릭합니다.

3. **시작** 페이지에서 **구성**을 클릭합니다.

4. **추가 작업** 페이에서 **동기화 옵션 사용자 지정**을 클릭한 다음 **다음**을 클릭합니다.

5. **Azure AD에 연결** 페이지에서 사용자 1 계정 자격 증명을 입력한 후 **다음**을 클릭합니다.

6. **디렉터리 연결** 및 **도메인/OU 필터링** 페이지에서 **다음**을 클릭합니다.

7. **선택적 기 ** 페이지에서 **암호 쓰기 저장**을 선택하고 다음을 클릭합니다. 

8. **구성 준비** 페이지에서 **구성**을 클릭하고 프로세스가 완료될 때까지 기다립니다.

9. 구성이 완료되면 **종료**를 클릭합니다.

이제 시뮬레이션된 인트라넷의 가상 네트워크에 연결되지 않은 컴퓨터의 사용자에 대한 암호 쓰기 저장을 테스트할 준비가 되었습니다.

구성 결과는 다음과 같습니다.

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

이 구성은 다음으로 이루어집니다.

- Office 365 E5 및 EMS E5 평가판 또는 DNS 도메인 TESTLAB.\<도메인 이름>이 등록된 영구 구독
- 인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 
- Azure AD Connect는 Office 365 및 EMS E5 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 테스트 랩 Windows Server AD 도메인과 동기화하기 위해 APP1에서 실행됩니다. 
- 암호 쓰기 저장 기능은 사용자가 간소화된 인트라넷에 연결하지 않고도 Azure AD를 통해 암호를 변경할 수 있도록 합니다.

프로덕션 환경에서 암호 업데이트를 구성하기 위한 정보 및 단계에 대해서는 ID 단계의 [암호 쓰기 저장 간소화](identity-password-writeback.md) 단계를 참조하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)



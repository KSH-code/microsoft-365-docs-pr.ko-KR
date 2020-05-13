---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 다단계 인증
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 Enterprise 테스트 환경에서 스마트 전화로 전송 되는 텍스트 메시지를 사용 하 여 다단계 인증을 구성 합니다.
ms.openlocfilehash: ae8cab25a20cc75992eecc600219d9f1dd869b63
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213143"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대 한 다단계 인증

*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*

Microsoft 365 또는 구독에 대해 Azure AD 테 넌 트를 사용 하는 모든 서비스 또는 응용 프로그램에 로그인 하기 위한 추가 보안 수준에 대 한 자세한 내용은 계정을 확인 하기 위해 사용자 이름 및 암호 뿐 아니라 Azure multi-factor authentication을 사용 하도록 설정할 수 있습니다. 

다단계 인증을 사용 하는 경우 사용자는 전화 통화를 승인 하거나, 문자 메시지로 보낸 확인 코드를 입력 하거나, 암호를 올바르게 입력 한 후 스마트 전화에서 앱을 사용 하 여 인증을 확인 해야 합니다. 사용자는 이 두 번째 인증 요소를 충족해야 로그인할 수 있습니다. 
  
이 문서에서는 특정 사용자 계정에 대해 텍스트 메시지 기반 인증을 사용 하 고 테스트 하는 방법에 대해 설명 합니다.
  
Microsoft 365 Enterprise 테스트 환경에서는 계정에 대해 multi-factor authentication을 설정 하는 두 단계가 있습니다.
  
1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
    
2. 사용자 2 계정에 대해 multi-factor authentication을 사용 하도록 설정 하 고 테스트 합니다.

3. 조건부 액세스 정책을 사용 하 여 다단계 인증을 사용 하도록 설정 하 고 테스트 합니다 (선택 사항).

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항과 함께 경량 방식으로 multi-factor authentication을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 multi-factor authentication을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 다단계 인증을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 다단계 인증을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>2 단계: 사용자 2 계정에 대해 multi-factor authentication 사용 및 테스트

사용자 2 계정에 대해 다단계 인증을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.
  
1. 별도의 브라우저 전용 인스턴스를 열고 Microsoft 365 관리 센터 ()로 이동한 [https://portal.microsoft.com](https://portal.microsoft.com) 후 전역 관리자 계정으로 로그인 합니다.
    
2. 왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.
    
3. 활성 사용자 창에서 **다단계 인증**을 클릭 합니다.
    
4. 목록에서 **사용자 2** 계정을 선택 합니다.
    
5. **사용자 2** 섹션의 **빠른 단계**에서 **사용**을 클릭 합니다.
    
6. **다단계 인증 사용** 대화 상자에서 **다단계 인증 사용**을 클릭 합니다.
    
7. **업데이트 완료** 대화 상자에서 **닫기를**클릭 합니다.
    
8. **Microsoft 365 관리 센터** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 클릭 한 다음 **로그 아웃**을 클릭 합니다.
    
9. 브라우저 인스턴스를 닫습니다.
   
사용자 2 계정에 대 한 구성을 완료 하 여 유효성 검사에 텍스트 메시지를 사용 하 고 다음 단계를 사용 하 여 테스트 합니다.
  
1. 브라우저의 새 개인 인스턴스를 엽니다.
    
2. Office 365 portal ()로 이동 [https://portal.office.com](https://portal.office.com) 하 여 사용자 2 계정 이름 및 암호를 사용 하 여 로그인 합니다.
    
3. 로그인 한 후에는 계정을 설정 하 라는 메시지가 표시 됩니다. **다음**을 클릭합니다.
    
4. **추가 보안 확인** 페이지에서 다음을 수행 합니다.
    
   - 국가 또는 지역을 선택 합니다.
    
   - 텍스트 메시지를 받을 스마트 폰의 전화 번호를 입력 합니다.
    
   - **방법**에서 **문자 메시지로 코드 보내기를**클릭 합니다.
    
5. **다음**을 클릭합니다.
    
6. 스마트 폰에서 받은 문자 메시지의 확인 코드를 입력 하 고 **확인**을 클릭 합니다.
    
7. **3 단계: 기존 응용 프로그램 유지** 페이지에서 **완료**를 클릭 합니다.
    
8. 사용자 2 계정으로 처음 로그인 하는 경우 암호를 변경 하 라는 메시지가 표시 됩니다. 원래 암호와 새 암호를 두 번 입력 한 다음 **암호 업데이트 및 로그인**을 클릭 합니다. 새 암호를 안전한 위치에 기록 합니다.
    
    브라우저의 **Microsoft Office 홈** 탭에 사용자 2에 대 한 Office 포털이 표시 됩니다.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>3 단계: 조건부 액세스 정책을 사용 하 여 다단계 인증을 사용 하도록 설정 및 테스트

*이 단계는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*

이 단계에서는 그룹 및 조건부 액세스 정책을 사용 하 여 사용자 3 계정에 대해 multi-factor authentication을 사용 하도록 설정 합니다.

다음으로 MFAUsers 라는 새 그룹을 만들고 사용자 3 계정을 추가 합니다.

1. **Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 **그룹** 을 클릭 하 고 **그룹**을 클릭 합니다.
2. **그룹 추가를**클릭 합니다.
3. **그룹 유형 선택** 창에서 **보안**을 선택 하 고 **다음**을 클릭 합니다.
4. **기본 설정** 창에서 **그룹 만들기**를 클릭 한 다음 **닫기를**클릭 합니다.
5. **그룹 추가 검토 및 완료** 창에서 **mfausers**를 입력 한 후 **다음**을 클릭 합니다.
6. 그룹 목록에서 **Mfausers** 그룹을 클릭 합니다.
7. **Mfausers** 창에서 **구성원**을 클릭 하 고 **모두 보기 및 구성원 관리를**클릭 합니다.
8. **Mfausers** 창에서 **구성원 추가**를 클릭 하 고 **사용자 3** 계정을 선택한 다음 **저장 > 닫기를 클릭 > 닫기**합니다.

다음으로 MFAUsers 그룹의 구성원에 대해 다단계 인증을 요구 하는 조건부 액세스 정책을 만듭니다.

1. 브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com) 합니다.
2. **Azure Active Directory > 보안 > 조건부 액세스**를 클릭 합니다.
3. **조건부 액세스 – 정책** 창에서 **새 정책을**클릭 합니다.
4. **새로 만들기** 창에서 **이름**에 **사용자 계정의 MFA** 를 입력 합니다.
5. **할당** 섹션에서 **사용자 및 그룹**을 클릭 합니다.
6. **사용자 및 그룹** 창의 **포함** 탭에서 사용자 및 그룹 **선택 > >** 합니다.
7. **선택** 창에서 **mfausers** 그룹을 클릭 한 다음 **완료 > 선택을**클릭 합니다.
8. **새** 창의 **액세스 제어** 섹션에서 **부여**를 클릭 합니다.
9. **부여** 창에서 **다단계 인증 필요**를 클릭 한 다음 **선택을**클릭 합니다.
10. **새로 만들기** 창에서 **정책 사용** **을 클릭 하** 고 **만들기**를 클릭 합니다.
11. **Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.

이 정책을 테스트 하려면 로그 아웃 하 고 사용자 3 계정으로 로그인 합니다. MFA를 구성 하 라는 메시지가 표시 되어야 합니다. 이는 MFAUsers 정책이 적용 되는 것을 보여 줍니다.

프로덕션 환경에서 다단계 인증을 배포 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [multi-factor Authentication 설정](identity-secure-user-sign-ins.md#identity-mfa) 단계를 참조 하세요.
    
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

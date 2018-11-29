---
title: 다단계 인증 Microsoft 365 기업에 대 한 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 기업 테스트 환경에서 스마트폰으로 전송 하는 텍스트 메시지를 사용 하 여 다단계 인증을 구성 합니다.
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869721"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>다단계 인증 Microsoft 365 기업에 대 한 테스트 환경

추가 된 Office 365 또는 모든 서비스 또는 조직에 대 한 Azure AD 테 넌 트를 사용 하는 응용 프로그램에 로그인 하는 것에 대 한 보안 수준을 대 한 사용자 이름 및 암호 확인 하기 위해 단순한 필요 Azure 다단계 인증을 사용할 수 있습니다는 계정입니다. 다단계 인증을 사용 하면 사용자가 전화 통화, 텍스트 메시지를 열고 전송 확인 코드를 입력 하거나 올바르게 자신의 암호를 입력 한 후 스마트 전화 앱 암호를 지정 해야 합니다. 이 두번째 인증 요소를 충족 된 후에에 로그인 수 있습니다. 
  
이 문서에서는 설정 하 고 특정 계정에 대 한 텍스트 메시지 기반 인증을 테스트 하는 방법에 설명 합니다.
  
Microsoft 365 기업 테스트 환경에서 계정에 대 한 다단계 인증을 설정 하는 두 단계로 가지가 있습니다.
  
1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
    
2. 사용 하도록 설정 하 고 사용자 2 계정에 대 한 다단계 인증을 테스트 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 다단계 인증을 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 다단계 인증을 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.
  
> [!NOTE]
> 다단계 인증을 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공은 다단계 인증을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>2 단계: 사용 하도록 설정 하 고 사용자 2 계정에 대 한 다단계 인증 테스트

다음이 단계를 사용 하 여 사용자 2 계정에 대 한 다단계 인증을 사용 하도록 설정 합니다.
  
1. 브라우저의 개인 별도 인스턴스를 열고, Office 365 포털에 이동 ([https://portal.office.com](https://portal.office.com)), 전역 관리자 계정을 사용 하 여 다음에 서명 하 고 있습니다.
    
2. 기본 포털 페이지에서 **관리자**를 클릭합니다.
    
3. 왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.
    
4. 현재 사용자가 창에서 클릭 **더 > 다단계 인증 설정**합니다.
    
5. 목록에서 **사용자 2** 계정을 선택 합니다.
    
6. **사용자 2** 섹션에서 **빠른 단계** **사용**을 클릭 합니다.
    
7. **다단계 인증을 사용 하도록 설정 하는 방법에 대 한** 대화 상자에서 **다단계 인증 사용**을 클릭 합니다.
    
8. **성공적으로 업데이트 하는** 대화 상자에서 **닫기를**클릭 합니다.
    
9. **Microsoft Office 홈** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 클릭 하 고 **로그 아웃**을 클릭 합니다.
    
10. 브라우저 인스턴스를 닫습니다.
   
유효성 검사에 대 한 텍스트 메시지를 사용 하 고 이러한 단계를 테스트 하는 사용자 2 계정에 대 한 구성을 완료 합니다.
  
1. 브라우저의 개인 새 인스턴스를 엽니다.
    
2. Office 365 포털에 이동 ([https://portal.office.com](https://portal.office.com))와 사용자 2 계정 사용 하 여 로그인 (@ 사용자 2가\<조직 이름 >. onmicrosoft.com) 및 암호입니다.
    
3. 로그인 한 후 자세한 정보에 대 한 계정을 설정 하 라는 메시지가 표시 됩니다. **다음**을 클릭 합니다.
    
4. **추가 보안 확인** 페이지 수행 합니다.
    
   - 국가 또는 지역을 선택 합니다.
    
   - 텍스트 메시지를 받을 스마트 전화의 전화번호를 입력 합니다.
    
   - **메서드**를 **보내기 나에 게 텍스트 메시지를 여는 코드를**클릭 합니다.
    
5. **다음**을 클릭합니다.
    
6. 스마트 전화기에서 받은 텍스트 메시지에서 확인 코드를 입력 한 다음 **확인**을 클릭 합니다.
    
7. **3 단계: 기존 응용 프로그램을 유지** 페이지를 안전한 위치에 2 사용자 계정에 대 한 표시 된 앱 암호를 기록 하 고 다음 **완료**를 클릭 합니다.
    
8. 이것은 처음으로 하는 경우 귀하가 사용자 2 계정을 사용 하 여 메시지가 표시 되는 암호를 변경 해야 합니다. 원래 암호와 새 암호를을 두번 입력 하 고 **암호를 업데이트 하 고 로그인**을 클릭 합니다. 안전한 위치에 새 암호를 기록 합니다.
    
    브라우저의 **Microsoft Office Home** 탭에는 Office 365 포털 사용자 2에 대 한 표시 됩니다.


정보 및 프로덕션 환경에서 다단계 인증을 배포에 대 한 링크에 대 한 Identity 단계에서 [다단계 인증을 설정](identity-multi-factor-authentication.md) 하는 단계를 참조 하십시오.
    
## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 엔터프라이즈 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

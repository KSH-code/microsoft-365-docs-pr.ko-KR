---
title: 엔터프라이즈용 Microsoft 365 테스트 환경 다단계 인증
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
- seo-marvel-apr2020
description: 엔터프라이즈용 Microsoft 365 테스트 환경에서 스마트폰으로 전송된 문자 메시지를 사용하여 다단계 인증을 구성합니다.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558445"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경에 대한 다단계 인증

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 및 Office 365 Enterprise 테스트 환경에 모두 사용할 수 있습니다.*

Microsoft 365 또는 구독에 대해 Azure AD 테넌트를 사용하는 서비스 또는 응용 프로그램에 로그인하기 위한 추가 보안 수준을 위해 계정 확인을 위해 사용자 이름과 암호 이상이 필요한 Azure AD 다단계 인증을 사용하도록 설정할 수 있습니다.

다단계 인증을 사용하는 경우 사용자는 전화 통화를 확인하거나, 문자 메시지로 전송된 확인 코드를 입력하거나, 암호를 올바르게 입력한 후 스마트폰의 앱으로 인증을 확인해야 합니다. 이 두 번째 인증 요소가 충족된 후에만 로그인할 수 있습니다.
  
이 문서에서는 특정 사용자 계정에 대해 문자 메시지 기반 인증을 사용하도록 설정하고 테스트하는 방법을 설명합니다.
  
엔터프라이즈용 Microsoft 365 테스트 환경에서 계정에 대해 다단계 인증을 설정하려면 다음 두 단계와 세 번째 선택적 단계가 있습니다.
- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: 사용자 2 계정에 대해 다단계 인증 사용 및 테스트](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [3단계: 조건부 액세스 정책을 사용하여 다단계 인증 사용 및 테스트](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항과 경량 방식으로 다단계 인증을 테스트하려는 경우 경량 기본 구성의 [지침을 따르세요.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 다단계 인증을 테스트하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 다단계 인증을 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기서는 다단계 인증을 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>2단계: 사용자 2 계정에 대해 다단계 인증 사용 및 테스트

다음 단계를 사용하여 사용자 2 계정에 대해 다단계 인증을 사용하도록 설정할 수 있습니다.
  
1. 별도의 개인 브라우저 인스턴스를 열고 Microsoft 365 관리 센터()로 이동한 다음 전역 관리자 계정으로 [https://portal.microsoft.com](https://portal.microsoft.com) 로그인합니다.
    
2. 왼쪽 탐색에서 사용자   >  **활성 사용자를 선택합니다.**
    
3. 활성 사용자 창에서 다단계 **인증을 선택합니다.**
    
4. 목록에서 사용자 **2 계정을** 선택합니다.
    
5. 사용자 **2 섹션의** 빠른 **단계 아래에서** 사용 을 **선택합니다.**
    
6. 다단계  인증 사용에 대한 대화 상자에서 다단계 인증 **사용을 선택합니다.**
    
7. 업데이트 성공 **대화** 상자에서 닫기 **를 선택합니다.**
    
8. Microsoft **365** 관리 센터 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 선택한 다음 **로그인을 선택합니다.**
    
9. 브라우저 인스턴스를 닫습니다.
   
유효성 검사에 문자 메시지를 사용하려면 사용자 2 계정의 구성을 완료하고 다음 단계를 사용하여 테스트합니다.
  
1. 브라우저의 새 개인 인스턴스를 여는 경우
    
2. [Microsoft 365](https://admin.microsoft.com) 관리 센터로 이동하여 사용자 2 계정 이름과 암호로 로그인합니다.
    
3. 로그인한 후 자세한 정보를 위해 계정을 설정하라는 메시지가 표시됩니다. **다음** 을 선택합니다.
    
4. 추가 **보안 확인 페이지에서 다음을** 진행합니다.
    
   - 국가 또는 지역을 선택합니다.
    
   - 문자 메시지를 받을 스마트폰의 전화 번호를 입력합니다.
    
   - **메서드에서** 문자 **메시지로 코드 보내기를 선택합니다.**
    
5. **다음** 을 선택합니다.
    
6. 스마트폰에서 받은 문자 메시지의 확인 코드를 입력한 다음 확인을 **선택합니다.**
    
7. **3단계:** 기존 응용 프로그램 유지 페이지에서 완료를 **선택합니다.**
    
8. 사용자 2 계정으로 처음 로그인한 경우 암호를 변경하라는 메시지가 표시됩니다. 원래 암호와 새 암호를 두 번 입력한 다음 암호 업데이트 **및 로그인을 선택합니다.** 새 암호를 안전한 위치에 기록합니다.
    
    브라우저의 홈 탭에 있는 Microsoft Office **Office 포털이** 표시됩니다.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>3단계: 조건부 액세스 정책을 사용하여 다단계 인증 사용 및 테스트

*이 단계는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

이 단계에서는 그룹 및 조건부 액세스 정책을 사용하여 사용자 3 계정에 대해 다단계 인증을 사용하도록 설정할 수 있습니다.

그런 다음 MFAUsers라는 새 그룹을 만들고 사용자 3 계정을 추가합니다.

1. Microsoft **365** 관리 센터 탭의 왼쪽 탐색 창에서 그룹을 선택한 다음 **그룹을 선택합니다.** 
2. 그룹 **추가를 선택합니다.**
3. 그룹 유형 **선택 창에서** 보안을 **선택하고** 다음을 **선택합니다.**
4. 기본 설정 **창에서** 그룹 만들기를 선택한 다음 **닫기 를 선택합니다.**
5. 검토 및 **그룹** 창 추가를 완료하려면 **MFAUsers를** 입력하고 다음을 **선택합니다.**
6. 그룹 목록에서 **MFAUsers 그룹을** 선택합니다.
7. **MFAUsers** 창에서 구성원을 **선택한** 다음 모두 보기를 선택하고 **구성원을 관리합니다.**
8. **MFAUsers** 창에서 구성원 **추가를** 선택하고 사용자 **3** 계정을 선택한 다음 닫기   >  **저장을**  >  **선택합니다.**

그런 다음 MFAUsers 그룹의 구성원에 대해 다단계 인증을 요구하는 조건부 액세스 정책을 생성합니다.

1. 브라우저의 새 탭에서 [https://portal.azure.com](https://portal.azure.com) .
2. **Azure Active Directory 보안**  >    >  **조건부 액세스를 선택합니다.**
3. 조건부 **액세스 - 정책** 창에서 새 정책을 **선택합니다.**
4. 새 **창에서** 이름 상자에 사용자 계정에 **대한 MFA를** **입력합니다.**
5. 배정 **섹션에서** 사용자 및 **그룹을 선택합니다.**
6. 사용자 **및** 그룹  창의 포함 탭에서 사용자 및 그룹 사용자 **및 그룹**  >  **선택을**  >  **선택합니다.**
7. 선택 **창에서** **MFAUsers** 그룹을 선택한 다음 완료   >  **선택을 선택합니다.**
8. 새 **창의 Access** 컨트롤  섹션에서 부여를 **선택합니다.**
9. 부여 **창에서** 다단계 인증 필요를 선택한 다음 선택을 **선택합니다.**
10. 새 **창에서** 정책 사용에  **대해 설정을** 선택한 다음 만들기를 **선택합니다.**
11. Azure **Portal 및** **Microsoft 365** 관리 센터 탭을 닫습니다.

해당 정책을 테스트하려면 사용자 3 계정으로 로그인합니다. MFA를 구성하라는 메시지가 표시해야 합니다. MFAUsers 정책이 적용되고 있는 것을 보여줄 수 있습니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

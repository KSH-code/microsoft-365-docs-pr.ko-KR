---
title: Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호
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
description: 다음 단계를 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정을 보호 합니다.
ms.openlocfilehash: 32e5983532c89c6ada106ed32d8ef3eabd5dc569
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801393"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호

*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*

관리자 계정이 최대한 안전한 지 확인 하 여 조직에서 디지털 공격을 방지할 수 있습니다. 이 문서에서는 Azure Active Directory (Azure AD) 조건부 액세스 정책을 사용 하 여 전역 관리자 계정을 보호 하는 방법을 설명 합니다.

Microsoft 365 Enterprise 테스트 환경에서는 다음과 같은 두 가지 단계를 통해 전역 관리자 계정을 보호 합니다.

1.  Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2.  전용 전역 관리자 계정을 보호 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방법으로 전역 관리자 계정 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 전역 관리자 계정 보호를 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스)에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서이를 시험해 볼 수 있도록 여기에 제공 되는 옵션입니다. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>2 단계: 조건부 액세스 정책 구성

먼저 새 사용자 계정을 전용 전역 관리자로 만듭니다.

1. 별도의 탭에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/)를 엽니다.
2. **활성 사용자 >** 사용자를 클릭 한 다음 **사용자 추가**를 클릭 합니다.
3. **사용자 추가** 창에서 **이름**, **표시 이름**및 **사용자 이름**에 **DedicatedAdmin** 을 입력 합니다.
4. **암호**를 클릭 하 고 **암호 만들기**를 클릭 한 다음 강력한 암호를 입력 합니다. 이 새 계정의 암호를 안전한 위치에 기록 합니다.
5. **다음**을 클릭합니다.
6. **제품 라이선스 할당** 창에서 **Microsoft 365 e5** 또는 **Office 365 E5**를 선택 하 고 **다음**을 클릭 합니다.
7. **선택적 설정** 창에서 **역할**을 클릭 한 다음 **관리 센터 액세스** 및 **전역 관리자**를 선택 합니다. **다음**을 클릭 합니다.
8. **거의 완료** 된 창에서 **추가 완료**를 클릭 한 다음 **닫기를**클릭 합니다.

그런 다음 GlobalAdmins 라는 새 그룹을 만들고 여기에 DedicatedAdmin 계정을 추가 합니다.

1. **Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 **그룹** 을 클릭 하 고 **그룹**을 클릭 합니다.
2. **그룹 추가를**클릭 합니다.
3. **그룹 유형 선택** 창에서 **보안**을 선택 하 고 **다음**을 클릭 합니다.
4. **기본 설정** 창에서 **그룹 만들기**를 클릭 한 다음 **닫기를**클릭 합니다.
5. **검토 및 그룹 추가 완료** 창에서 **globaladmins**를 입력 하 고 **다음**을 클릭 합니다.
7. 그룹 목록에서 **Globaladmins** 그룹을 클릭 합니다.
8. **Globaladmins** 창에서 **구성원**을 클릭 하 고 **모두 보기 및 구성원 관리를**클릭 합니다.
9. **Globaladmins** 창에서 **구성원 추가**를 클릭 하 고 **DedicatedAdmin** 계정 및 전역 관리자 계정을 선택한 다음 **저장 > 닫기 >** 닫기를 클릭 합니다.

그런 다음 전역 관리자 계정에 대해 다단계 인증을 요구 하 고 로그인 위험이 중간 또는 높은 경우 인증을 거부 하도록 조건부 액세스 정책을 만듭니다.

이 첫 번째 정책에서는 모든 전역 관리자 계정에서 MFA를 사용 해야 합니다.

1. 브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.
2. **Azure Active Directory > 보안 > 조건부 액세스**를 클릭 합니다.
3. **조건부 액세스 – 정책** 창에서 **기본 정책: 관리자에 게 MFA 필요 (미리 보기)** 을 클릭 합니다.
4. **기본 정책** 창에서 **정책 즉시 사용 > 저장**을 클릭 합니다.

이 두 번째 정책은 로그인 위험이 보통 또는 높음 인 경우 전역 관리자 계정 인증에 대 한 액세스를 차단 합니다.

1. **조건부 액세스 – 정책** 창에서 **새 정책을**클릭 합니다.
2. **새로 만들기** 창에서 **이름**에 **전역 관리자** 를 입력 합니다.
3. **할당** 섹션에서 **사용자 및 그룹**을 클릭 합니다.
4. **사용자 및 그룹** 창의 **포함** 탭에서 사용자 및 그룹 **선택 > >** 합니다.
5. **선택** 창에서 **globaladmins** 그룹을 클릭 한 다음 **완료 > 선택을**클릭 합니다.
6. **배정** 섹션에서 **조건을**클릭 합니다.
7. **조건** 창에서 **로그인 위험**을 클릭 하 고 **구성**에 대해 **예** 를 클릭 한 다음 **높음** 및 **중간**을 클릭 하 고 **선택** 및 **완료**를 클릭 합니다.
8. **새** 창의 **액세스 제어** 섹션에서 **부여**를 클릭 합니다.
9. **부여** 창에서 **액세스 차단**, **선택을**차례로 클릭 합니다.
10. **새로 만들기** 창에서 **정책 사용** **을 클릭 하** 고 **만들기**를 클릭 합니다.
11. **Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.

첫 번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다. MFA를 구성 하 라는 메시지가 표시 되어야 합니다. 이는 첫 번째 정책을 적용 하는 것을 보여 줍니다.

프로덕션에서 전역 관리자 계정을 보호 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [전역 관리자 계정 보호](identity-create-protect-global-admins.md#identity-global-admin) 단계를 참조 하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

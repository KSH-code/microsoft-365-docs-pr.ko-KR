---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에서 전역 관리자 계정 보호
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
description: 다음 단계에 따라 엔터프라이즈용 Microsoft 365 테스트 환경에서 전역 관리자 계정을 보호합니다.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487639"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경에서 전역 관리자 계정 보호

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

관리자 계정을 최대한 안전하게 보호하여 조직에 대한 디지털 공격을 방지할 수 있습니다. 

이 문서에서는 Azure AD(Azure Active Directory) 조건부 액세스 정책을 사용하여 전역 관리자 계정을 보호하는 방법을 설명합니다.

엔터프라이즈용 Microsoft 365 테스트 환경에서 전역 관리자 계정을 보호하는 단계는 다음 두 단계로 진행됩니다.
- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: 조건부 액세스 정책 구성](#phase-2-configure-conditional-access-policies)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항과 경량 방식으로 전역 관리자 계정 보호를 테스트하려면 간단한 기본 구성의 [지침을 따르세요.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트하려면 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 전역 관리자 계정 보호를 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스)에 대한 디렉터리 동기화가 포함됩니다. 전역 관리자 계정 보호를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 여기에 옵션으로 제공됩니다. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>2단계: 조건부 액세스 정책 구성

먼저 새 사용자 계정을 전용 전역 관리자로 생성합니다.

1. 별도의 탭에서 Microsoft [365 관리 센터를 니다.](https://admin.microsoft.com/)
2. 사용자 **활성 사용자를** 선택한 다음 사용자  >   **추가를 선택합니다.**
3. 사용자 추가 **창에서** 이름, 표시 이름 및 사용자 이름 상자에 **DedicatedAdmin을** **입력합니다.**
4. Select **Password,** select **Let me create the password,** and then enter a strong password. 이 새 계정의 암호를 안전한 위치에 기록합니다.
5. **다음** 을 선택합니다.
6. 제품 라이선스 **할당** 창에서 **Microsoft 365 E5를** 선택하고 다음을 **선택합니다.**
7. 선택적 **설정 창에서** **역할** 관리 센터  >  **액세스** 전역  >  **관리자 다음을**  >  **선택합니다.**
8. On the **You're almost done** pane, select **Finish adding,** and then select **Close**.

다음으로 GlobalAdmins라는 새 그룹을 만들고 DedicatedAdmin 계정을 추가합니다.

1. Microsoft **365** 관리 센터 탭의 왼쪽 탐색 창에서 그룹을 선택한 다음 **그룹을 선택합니다.** 
2. 그룹 **추가를 선택합니다.**
3. 그룹 **유형 선택 창에서** 보안을 **선택하고** 다음을 **선택합니다.**
4. 기본 설정 **창에서** 그룹 만들기를 선택한 다음 **닫기 를 선택합니다.**
5. 검토 **및** 그룹 창 추가를 마쳤습니다. **GlobalAdmins를** 입력하고 다음을 **선택합니다.**
7. 그룹 목록에서 **GlobalAdmins 그룹을** 선택합니다.
8. **GlobalAdmins 창에서** **구성원을** 선택한 다음 모두 보기를 선택하고 **구성원을 관리합니다.**
9. **GlobalAdmins** 창에서 구성원 **추가를** 선택하고 **DedicatedAdmin 계정** 및 전역 관리자 계정을 선택한 다음 닫기   >  **저장을**  >  **선택합니다.**

다음으로, 전역 관리자 계정에 대해 다단계 인증을 요구하고 로그인 위험이 중간 또는 높음인 경우 인증을 거부하는 조건부 액세스 정책을 생성합니다.

이 첫 번째 정책을 사용하려면 모든 전역 관리자 계정이 MFA를 사용해야 합니다.

1. 브라우저의 새 탭에서 [https://portal.azure.com](https://portal.azure.com) .
2. **Azure Active Directory 보안**  >    >  **조건부 액세스를 클릭합니다.**
3. 조건부 **액세스 -** 정책 창에서 기준 정책을 **선택합니다. 관리자에 대한 MFA 필요(미리 보기)입니다.**
4. 기본 정책 **창에서** 저장 후 즉시 정책 **> 선택합니다.**

이 두 번째 정책은 로그인 위험이 보통 또는 높을 때 전역 관리자 계정 인증에 대한 액세스를 차단합니다.

1. 조건부 **액세스 - 정책** 창에서 새 정책을 **선택합니다.**
2. 새 **창에서** 전역 **관리자를 이름에** **입력합니다.**
3. 배정 **섹션에서** 사용자 및 **그룹을 선택합니다.**
4. 사용자 **및** 그룹  창의 포함 탭에서 사용자 및 그룹 사용자 **및 그룹**  >  **선택을**  >  **선택합니다.**
5. 선택 **창에서** **GlobalAdmins** 그룹을 선택한 다음 **완료**  >  **선택을 선택합니다.**
6. 배정 **섹션에서** 조건을 **선택합니다.**
7. 조건 **창에서** 로그인 위험을 선택하고 **구성할** **예,** 높음 및 보통을 선택한 다음 선택 **및** 완료를 **선택합니다.**  
8. 새 **창의 Access** 컨트롤  섹션에서 부여를 **선택합니다.**
9. 부여 **창에서** 액세스 차단을 선택한 다음 선택을 **선택합니다.**
10. 새 **창에서** 정책 사용에  **대해 설정을** 선택한 다음 만들기를 **선택합니다.**
11. Azure **Portal 및** **Microsoft 365** 관리 센터 탭을 닫습니다.

첫 번째 정책을 테스트하려면 전용Admin 계정으로 로그인합니다. MFA를 구성하라는 메시지가 표시해야 합니다. 이는 첫 번째 정책이 적용되고 있는 것을 보여 주며,

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

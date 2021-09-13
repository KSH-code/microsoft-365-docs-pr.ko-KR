---
title: 엔터프라이즈 테스트 환경에 대한 사용자 Microsoft 365 라이선스 및 그룹 구성원 자동화
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 엔터프라이즈 테스트 환경에 대한 사용자 Microsoft 365 그룹 기반 라이선싱 및 동적 그룹 구성원을 구성합니다.
ms.openlocfilehash: 7d754b937296fbd852904022c45492b6890f2f04
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216082"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경에 대한 사용자 Microsoft 365 라이선스 및 그룹 구성원 자동화

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*

그룹 기반 라이선스는 그룹 구성원 자격에 따라 사용자 계정에 대한 라이선스를 자동으로 할당하거나 제거합니다. 동적 그룹 구성원은 부서 또는 국가와 같은 사용자 계정 속성에 따라 그룹에 구성원을 **추가하거나** **제거합니다.** 이 문서에서는 엔터프라이즈 테스트 환경의 사용자 환경에서 그룹 구성원을 추가 및 제거하는 방법을 Microsoft 365 단계에 대해 단계적으로 다단계합니다.

엔터프라이즈 테스트 환경에 대한 Microsoft 365 라이선스 및 동적 그룹 구성원 자격을 설정하는 단계는 다음 두 단계로 진행됩니다.

- [1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: 동적 그룹 구성원 자격 및 자동 라이선싱 구성 및 테스트](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 클라우드용 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축

최소 요구 사항과 함께 간단한 방식으로만 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하려면 [Lightweight base configuration의](lightweight-base-configuration-microsoft-365-enterprise.md)지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화를 포함하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기서는 옵션으로 제공되어 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하고 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>2단계: 동적 그룹 구성원 자격 및 자동 라이선싱 구성 및 테스트

먼저 Sales라는 새 그룹을 만들고, 부서가 **Sales로** 설정된 사용자  계정이 Sales 그룹에 자동으로 가입하도록 동적 그룹 구성원 규칙을 추가합니다.

1. 인터넷 브라우저의 개인 인스턴스에서 테스트 랩 [](https://admin.microsoft.com) Microsoft 365 관리 센터 전역 관리자 계정으로 Microsoft 365 E5 로그인합니다.
2. 브라우저의 별도 탭에서 의 Azure Portal로 [https://portal.azure.com](https://portal.azure.com) 이동하세요.
3. Azure Portal에서 **검색** 상자에 그룹을 입력한 다음 그룹을 **선택합니다.**
4. 모든 **그룹 창에서** 새 그룹을 **선택합니다.**
5. 그룹 **유형에서 를** **선택합니다Microsoft 365.**
6. 그룹 **이름에** Sales 를 **입력합니다.**
7. 멤버 **자격 유형에서** 동적 **사용자 를 선택합니다.**
8. 동적 **사용자 구성원 을 선택합니다.**
9. 동적 구성원 **규칙 창에서 다음을** 합니다. 
   - 부서 **속성을** 선택합니다.
   - **같음 연산자를** 선택합니다.
   - 값 **상자에** Sales 를 **입력합니다.**
10. **저장** 을 선택합니다.
11. **만들기** 를 선택합니다.

그런 다음 구성원에게 라이선스 라이선스가 자동으로 할당될 수 있도록 Sales Microsoft 365 E5 구성합니다.

1. Sales **그룹을 선택한** 다음 라이선스 **를 선택합니다.**
2. 라이선스 **할당 업데이트** 창에서 를 선택하고 **Microsoft 365 E5** 를 선택한 다음 **저장을 선택합니다.**
3. 브라우저에서 Azure Portal 탭을 닫습니다.

다음으로, 사용자 4 계정에서 동적 그룹 구성원 자격 및 자동 라이선싱을 테스트합니다.

1. 브라우저의 **Microsoft Office 홈** 탭에서 관리자 를 **선택합니다.**
2. Microsoft 365 관리 센터 **탭에서** 활성 **사용자를 선택합니다.**
3. 활성 **사용자 페이지에서** 사용자 **4 계정을** 선택합니다.
4. 사용자 **4 창에서** 제품 **라이선스에** 대해 **편집을 선택합니다.**
5. 제품 라이선스 **창에서** Microsoft 365 E5 라이선스를 사용하지 않도록 설정한 다음 저장 **닫기** **를**  >  **선택합니다.**
6. 사용자 4 계정의 속성에서 제품 라이선스가 할당되지 않은지와 그룹 구성원 자격이 없는지 확인해야 합니다.
7. 연락처 **정보에 대해** 편집 **을 선택합니다.**
8. 연락처 **정보 편집 창에서** 연락처 **정보를 선택합니다.**
9. 부서 **상자에** 판매 를 **입력하고** 저장 **닫기 를**  >  **선택합니다.**
10. 몇 분 정도 기다렸다가 사용자  4 계정 창의 오른쪽 위에 있는 새로 고침 아이콘을 주기적으로 선택합니다.

시간의 경우 다음이 표시해야 합니다.

- **Group memberships** 속성이 **Sales** 그룹으로 업데이트되었습니다.
- **제품 라이선스 속성이** Microsoft 365 E5 **업데이트되었습니다.**

다음 문서를 참조하여 프로덕션에서 동적 그룹 구성원 자격 및 자동 라이선싱을 배포합니다.

- [그룹의 그룹 기반 라이선싱 Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [그룹의 동적 Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)
---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 라이선싱 및 그룹 구성원을 자동화 합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 Enterprise 테스트 환경에서 그룹 기반 라이선싱 및 동적 그룹 구성원을 구성 합니다.
ms.openlocfilehash: c3b515a9b453275f9b79ba2b90d5a4c14611c2aa
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639798"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대 한 라이선싱 및 그룹 구성원을 자동화 합니다.

그룹 기반 라이선스는 그룹 구성원을 기반으로 사용자 계정에 대 한 라이선스를 자동으로 할당 하거나 제거 합니다. 동적 그룹 구성원 자격은 사용자 계정 속성 (예: 부서 또는 국가)을 기반으로 그룹에 구성원을 추가 하거나 제거 합니다. 이 문서에서는 Microsoft 365 Enterprise 테스트 환경 모두에 대 한 데모를 안내 합니다.

Microsoft 365 Enterprise 테스트 환경에서 자동 라이선싱 및 동적 그룹 멤버 자격을 설정 하는 두 가지 단계가 있습니다.

1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2. 동적 그룹 구성원 자격 및 자동 라이선스를 구성 하 고 테스트 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방법으로 자동 라이선싱 및 그룹 구성원을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 자동화 된 라이선싱 및 그룹 구성원을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 자동 라이선싱 및 그룹 구성원을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>2 단계: 동적 그룹 구성원 자격 및 자동 라이선스 구성 및 테스트

먼저 새 Sales 그룹을 만들고 부서가 Sales로 설정 된 사용자 계정이 Sales 그룹에 자동으로 추가 되도록 동적 그룹 구성원 규칙을 추가 합니다.

1. 인터넷 브라우저의 개인 인스턴스를 사용 하 여 office 365 E5 테스트 랩 구독의 전역 관리자 [https://portal.office.com](https://portal.office.com) 계정으로 office 365 포털에 로그인 합니다.
2. 브라우저의 별도 탭에서 Azure portal ()로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.
3. Azure Portal에서 **Azure Active Directory > 사용자 및 그룹 > 모든 그룹**을 클릭합니다.
4. **모든 그룹** 블레이드에서 **새 그룹**을 클릭 합니다.
5. **그룹 유형에**서 **Office 365**을 선택 합니다.
6. **그룹 이름**에 **Sales**를 입력 합니다.
7. **멤버 자격 유형에**서 **동적 사용자** 를 선택 합니다.
8. **동적 쿼리 추가**를 클릭합니다.
9. **사용자를 추가할 위치**에서 **부서**를 선택합니다.
10. 다음 필드에서 **같음**을 선택합니다.
11. 다음 필드에 **Sales**를 입력 합니다.
12. **쿼리 추가**를 클릭한 다음, **만들기**를 클릭합니다.
13. **그룹** 및 그룹 **(모든 그룹 날개)** 을 닫습니다.

다음으로, 구성원에 게 Office 365 E5 및 Enterprise Mobility + Security E5 라이선스가 자동으로 할당 되도록 Sales 그룹을 구성 합니다.

1. Azure Active Directory의 **개요** 블레이드에서 **모든 제품 > 라이선스**를 클릭 합니다.
2. 목록에서 **Enterprise Mobility + Security E5** 및 **Office 365 Enterprise E5**를 선택하고 **할당**을 클릭합니다.
3. **라이선스 할당** 블레이드에서 **사용자 및 그룹**을 클릭 합니다.
4. 그룹 목록에서 **Sales** 그룹을 선택 합니다.
5. **선택**을 클릭하고 **할당**을 클릭합니다.
6. 브라우저에서 Azure Portal 탭을 닫습니다.

다음으로, 사용자 4 계정에서 동적 그룹 구성원 자격 및 자동 라이선싱을 테스트 합니다. 

1. 브라우저의 **Microsoft Office 홈** 탭에서 **관리자**를 클릭 합니다.
2. **Microsoft 365 관리 센터** 탭에서 **활성 사용자**를 클릭 합니다.
3. **활성 사용자** 페이지에서 **사용자 4** 계정을 클릭 합니다.
4. **사용자 4** 창에서 **제품 라이선스**에 대 한 **편집** 을 클릭 합니다.
5. **제품 라이선스** 창에서 **Enterprise Mobility + Security E5** 및 **Office 365 enterprise E5** 라이선스를 해제 한 다음 **저장 > 닫기를**클릭 합니다.
6. 사용자 4 계정의 속성에서 제품 라이선스가 할당 되어 있지 않으며 그룹 구성원 자격이 없음을 확인 합니다.
7. **연락처 정보**에 대해 **편집** 을 클릭 합니다.
8. **연락처 정보 편집** 창에서 **연락처 정보**를 클릭 합니다.
9. **부서** 필드에 **Sales**를 입력 하 고 **닫기를 > 저장**을 클릭 합니다.
10. 몇 분 정도 기다린 다음 사용자 4 계정 창의 오른쪽 위에 있는 새로 고침 아이콘을 클릭 합니다. 

다음을 확인할 수 있습니다.

- **Sales** 그룹으로 업데이트 된 **그룹 멤버 자격** 속성
- **Enterprise Mobility + Security e5** 및 **Office 365 Enterprise E5** 라이선스로 업데이트 된 **제품 라이선스** 속성

프로덕션 환경에서 동적 그룹 구성원 자격 및 자동 라이선싱을 배포 하는 방법에 대 한 자세한 내용과 링크는 Identity 단계에서 다음 단계를 참조 하세요.

- [자동 라이선싱 설정](identity-use-group-management.md#identity-group-license)
- [동적 그룹 구성원 설정](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

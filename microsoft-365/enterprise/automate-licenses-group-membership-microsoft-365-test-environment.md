---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 라이선싱 및 그룹 멤버 자격 자동화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
description: Microsoft 365에서 엔터프라이즈 테스트 환경용으로 그룹 기반 라이선싱 및 동적 그룹 구성원을 구성 합니다.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487579"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 라이선싱 및 그룹 멤버 자격 자동화

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

그룹 기반 라이선스는 그룹 구성원을 기반으로 사용자 계정에 대 한 라이선스를 자동으로 할당 하거나 제거 합니다. 동적 그룹 구성원 자격은 사용자 계정 속성 (예: **부서** 또는 **국가**)을 기반으로 그룹에 구성원을 추가 하거나 제거 합니다. 이 문서에서는 엔터프라이즈 테스트 환경용 Microsoft 365에서 그룹 구성원을 추가 하 고 제거 하는 과정을 단계별로 안내 합니다.

엔터프라이즈 테스트 환경에 대 한 Microsoft 365에서 자동 라이선싱 및 동적 그룹 구성원을 설정 하는 작업은 다음 두 단계로 구성 됩니다.

- [1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2 단계: 동적 그룹 구성원 자격 및 자동 라이선스 구성 및 테스트](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축

최소 요구 사항에 따라 간단한 방법으로 자동 라이선싱 및 그룹 구성원을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 자동화 된 라이선싱 및 그룹 구성원을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 자동 라이선싱 및 그룹 구성원을 테스트 하려면 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 옵션으로 제공 됩니다.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>2 단계: 동적 그룹 구성원 자격 및 자동 라이선스 구성 및 테스트

먼저 Sales 라는 새 그룹을 만들고 **부서가** 있는 사용자 **계정이 sales 그룹에 자동으로** 참가 하도록 동적 그룹 구성원 규칙을 추가 합니다.

1. 인터넷 브라우저의 개인 인스턴스에서 microsoft 365 E5 테스트 랩 구독의 전역 관리자 계정으로 [microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.
2. 브라우저의 별도 탭에서 Azure portal ()로 이동 [https://portal.azure.com](https://portal.azure.com) 합니다.
3. Azure portal에서 검색 상자에 **그룹** 을 입력 한 다음 **그룹**을 선택 합니다.
4. **모든 그룹** 창에서 **새 그룹**을 선택 합니다.
5. **그룹 유형에**서 **Microsoft 365**을 선택 합니다.
6. **그룹 이름**에 **Sales**를 입력 합니다.
7. **멤버 자격 유형에**서 **동적 사용자**를 선택 합니다.
8. **동적 사용자 구성원**을 선택 합니다.
9. **동적 멤버 자격 규칙** 창에서 다음을 수행 합니다. 
   - **부서** 속성을 선택 합니다.
   - **같음** 연산자를 선택 합니다.
   - **값** 상자에 **Sales**를 입력 합니다.
10. **저장**을 선택합니다.
11. **만들기**를 선택합니다.

다음으로, 구성원에 게 Microsoft 365 E5 라이선스가 자동으로 할당 되도록 Sales 그룹을 구성 합니다.

1. **Sales** 그룹을 선택한 다음 **라이선스**를 선택 합니다.
2. **라이선스 할당 업데이트** 창에서 **Microsoft 365 E5**를 선택한 다음 **저장**을 선택 합니다.
3. 브라우저에서 Azure portal 탭을 닫습니다.

다음으로, 사용자 4 계정에서 동적 그룹 구성원 자격 및 자동 라이선싱을 테스트 합니다.

1. 브라우저의 **Microsoft Office 홈** 탭에서 **관리**를 선택 합니다.
2. **Microsoft 365 관리 센터** 탭에서 **활성 사용자**를 선택 합니다.
3. **활성 사용자** 페이지에서 **사용자 4** 계정을 선택 합니다.
4. **사용자 4** 창에서 **제품 라이선스**에 대해 **편집** 을 선택 합니다.
5. **제품 라이선스** 창에서 **Microsoft 365 E5** 라이선스를 사용 하지 않도록 설정 하 고 닫기 **저장**을 선택  >  **Close**합니다.
6. 사용자 4 계정의 속성에서 제품 라이선스가 할당 되어 있지 않으며 그룹 구성원 자격이 없음을 확인 합니다.
7. **연락처 정보**를 보려면 **편집**을 선택 합니다.
8. **연락처 정보 편집** 창에서 **연락처 정보**를 선택 합니다.
9. **부서** 상자에 **Sales**를 입력 한 다음 닫기 **저장**을 선택  >  **Close**합니다.
10. 몇 분 정도 기다린 다음 사용자 4 계정 창의 오른쪽 위에서 **새로 고침** 아이콘을 선택 합니다.

이때 다음이 표시 됩니다.

- **Sales** 그룹으로 업데이트 된 **그룹 멤버 자격** 속성
- **Microsoft 365 E5** 라이선스로 **제품 라이선스** 속성을 업데이트 했습니다.

다음 문서를 참조 하 여 프로덕션 환경에서 동적 그룹 구성원 자격 및 자동 라이선싱을 배포 합니다.

- [Azure Active Directory의 그룹 기반 라이선싱](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory의 동적 그룹](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[Id 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)

---
title: Microsoft 365 기업 테스트 환경에 대 한 라이선스 및 그룹 구성원 자격을 자동화 합니다.
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
description: Microsoft 365 기업 테스트 환경에서 라이선스 그룹 기반 및 동적 그룹 구성원 자격을 구성 합니다.
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870107"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 기업 테스트 환경에 대 한 라이선스 및 그룹 구성원 자격을 자동화 합니다.

자동으로 라이선스 그룹 기반 할당 하거나 그룹 구성원 자격을 기준으로 사용자 계정에 대 한 라이선스를 제거 합니다. 동적 그룹 구성원 자격을 추가 또는 부서 또는 국가/지역 등의 사용자 계정 속성을 기준으로 그룹에 구성원을 제거 합니다. 이 문서에서는 Microsoft 365 기업 테스트 환경에서 모두의 데모를 안내합니다.

Microsoft 365 기업 테스트 환경에서 자동 라이선스 및 동적 그룹 구성원 자격을 설정 하는 두 단계로 가지가 있습니다.

1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2. 구성 하 고 동적 그룹 멤버 자격 및 자동 라이선스를 테스트 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.
  
> [!NOTE]
> 라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>2 단계: 구성 및 테스트 동적 그룹 멤버 자격 및 자동 라이선스

첫째, 새 Sales 그룹을 만들고 Sales 그룹에 사용자 계정을 매출으로 설정 하는 부서와 함께 자동으로 추가 되도록 동적 그룹 멤버 자격 규칙을 추가 합니다.

1. Office 포털에 로그인 인터넷 브라우저의 전용 인스턴스를 사용 하 여 [https://office.com](https://office.com) Office 365 E5 평가판 구독의 전역 관리자 계정을 사용 하 여 합니다.
2. 브라우저의 개별 탭에 있는 포털로 이동 하 여 Azure에서 [https://portal.azure.com](https://portal.azure.com)합니다.
3. Azure Portal에서 **Azure Active Directory > 사용자 및 그룹 > 모든 그룹**을 클릭합니다.
4. **모든 그룹** 블레이드에서 **새 그룹**을 클릭 합니다.
5. **그룹 종류** **Office 365**를 선택 합니다.
6. **그룹 이름** **판매**를 입력 합니다.
7. **멤버 자격 형식** **동적 사용자** 를 선택 합니다.
8. **동적 쿼리 추가**를 클릭합니다.
9. **사용자를 추가할 위치**에서 **부서**를 선택합니다.
10. 다음 필드에서 **같음**을 선택합니다.
11. 다음 필드에서 **Sales**를 입력 합니다.
12. **쿼리 추가**를 클릭한 다음, **만들기**를 클릭합니다.
13. **그룹** 및 **그룹 모든 그룹** 블레이드를 닫습니다.

다음으로, Office 365 e 5 및 Enterprise 이동성 + 보안 E5 라이선스 구성원은 자동으로 할당 되도록 Sales 그룹을 구성 합니다.

1. Azure Active Directory에 대 한 **개요** 블레이드, 클릭 **라이선스 > 모든 제품**합니다.
2. 목록에서 **Enterprise Mobility + Security E5** 및 **Office 365 Enterprise E5**를 선택하고 **할당**을 클릭합니다.
3. **라이선스를 할당** 블레이드 **사용자 및 그룹을**클릭 합니다.
4. 그룹 목록에서 **Sales** 그룹을 선택 합니다.
5. **선택**을 클릭하고 **할당**을 클릭합니다.
6. 브라우저에서 Azure Portal 탭을 닫습니다.

다음으로, 동적 그룹 멤버 자격 및 사용자 4 계정에 자동 라이선스 테스트 합니다. 

1. 브라우저에서 **Microsoft Office 홈** 탭에서 **관리**를 클릭 합니다.
2. **Office 관리 센터** 탭에서 **활성 사용자**를 클릭 합니다.
3. **현재 사용자** 페이지에서 **사용자 4** 계정을 클릭 합니다.
4. **사용자 4** 창에서 **제품 라이선스**에 대 한 **편집** 을 클릭 합니다.
5. **제품 라이선스** 창에는 **엔터프라이즈 이동성 + 보안 e 5를** 설정 하 고 **Office 365 Enterprise e 5** 라이선스를 해제 하 고 다음을 클릭 **저장 > 닫기**합니다.
6. 4 사용자 계정 속성에 없는 제품 라이선스를 할당 하 고는 없는 그룹 구성원 자격을 확인 합니다.
7. **연락처 정보**에 대 한 **편집** 을 클릭 합니다.
8. **연락처 편집 정보** 창에서 **연락처 정보**를 클릭 합니다.
9. **부서** 필드에서 **Sales**를 입력 하 고 클릭 **저장 > 닫기**합니다.
10. 몇분 기다린 다음 업그레이드를 주기적으로 사용자 4 계정 창의 오른쪽 위에서에서 새로고침 아이콘을 클릭 합니다. 

시간에 표시 되어야는:

- **그룹 구성원 자격** 속성 **Sales** 그룹을 사용 하 여 업데이트 합니다.
- **제품 라이선스** 속성 **Enterprise 이동성 + 보안 e 5** 및 **Office 365 Enterprise E5** 라이선스를 사용 하 여 업데이트 합니다.

정보 및 동적 그룹 멤버 자격 및 프로덕션 환경에서 자동 라이선스 배포에 대 한 링크에 대 한 Identity 단계에서 다음이 단계를 참조 하십시오.

- [자동 라이선싱 설정](identity-group-based-licensing.md)
- [동적 그룹 구성원 설정](identity-automatic-group-membership.md)

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 엔터프라이즈 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

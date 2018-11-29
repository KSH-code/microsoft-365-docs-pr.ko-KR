---
title: 전역 관리자 계정을 Microsoft 365 기업 테스트 환경에서 보호
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
description: Microsoft 365 기업 테스트 환경에서 전역 관리자 계정을 보호 하기 위해 다음이 단계를 사용 합니다.
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869742"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>전역 관리자 계정을 Microsoft 365 기업 테스트 환경에서 보호

관리자 계정 보안을 최대한 확인 하 여 조직에 대 한 디지털 공격을 방지할 수 있습니다. 이 문서에서는 전역 관리자 계정을 보호 하기 위해 Office 365 클라우드 응용 프로그램 보안 및 Azure AD 조건부 액세스 정책을 사용 하는 방법에 설명 합니다.

전역 관리자 계정을 Microsoft 365 기업 테스트 환경에서 보호 하는 두 단계로 가지가 있습니다.

1.  Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2.  전용된 전역 관리자 계정을 보호 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 전역 관리자 계정 보호를 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.
  
> [!NOTE]
> 인터넷에 연결 된 전역 관리자 계정 보호 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 필요 하지 않은 테스트 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공은 전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>2 단계: 클라우드 응용 프로그램 보안 및 조건부 액세스 정책 구성

먼저, 전역 관리자 계정 활동을 모니터링 하 고 전역 관리자 계정의 전자 메일 주소로 경고를 보내도록 하는 Office 365 클라우드 응용 프로그램 보안 정책을 만듭니다. 

1. Office 365 포털에 로그인 [http://portal.office.com](http://portal.office.com) 전역 관리자 계정을 사용 하 여 합니다.
2. **Admin** 타일을 클릭 합니다. **Office 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.
3. 왼쪽된 탐색 창의 클릭 **알림 > 고급 알림 관리**합니다.
4. **고급 알림 관리** 페이지에서 **Office 365 클라우드 응용 프로그램 보안 설정**를 클릭 한 다음 **Office 365 클라우드 응용 프로그램 보안으로 이동**를 클릭 합니다.
5. 새 **대시보드** 탭을 클릭 **제어 > 정책**합니다.
6. **정책** 페이지에서 **정책 만들기**클릭 한 다음 **활동 정책**을 클릭 합니다.
7. **정책 이름** **관리 작업**을 입력 합니다.
8. **정책 심각도**에서 **높음**을 클릭합니다.
9. **범주** **권한이 부여 된 계정**을 클릭 합니다.
10. **정책에 대 한 만들기 필터**에 **일치 하는 다음의 모든 활동**을에서 **관리 작업**을 클릭 합니다.
11. **경고**에서 **전자 메일로 경고 보내기**를 클릭합니다. **받는 사람**에서 전역 관리자 계정의 전자 메일 주소를 입력합니다.
12. 페이지 하단에서 **만들기**를 클릭합니다.
13. **대시보드** 탭을 닫습니다.
    
다음으로 전용된 전역 관리자 권한으로 새 사용자 계정을 만듭니다.

1. **Office 관리 센터** 탭에서 **현재 사용자** **사용자 추가**클릭 합니다.
2. **새 사용자** 페이지에서 **성**, **표시 이름**및 **사용자 이름**에 **DedicatedAdmin** 를 입력 합니다.
3. **암호**를클릭하고 **나에 게 암호를 만들 수 있도록**를 클릭 한 다음 강력한 암호를 입력 합니다. 안전한 위치에 새이 계정의 암호를 기록 합니다.
4. **처음 로그인 할 때 자신의 암호를 변경 하는이 사용자를 확인 합니다.** 의 선택을 취소 합니다.
5. **역할**클릭 하 고 **전역 관리자**를 클릭 합니다.
6. **제품 라이선스**클릭 하 고 **엔터프라이즈 이동성 + 보안 e 5** 및 **Office 365 Enterprise E5 라이선스** 를 설정 합니다.
7. **추가**를 클릭합니다.
8. **사용자가 페이지를 추가**에서 **보내는 전자 메일에 암호를**지우고 **닫기**를 클릭 합니다.

다음으로, GlobalAdmins 이라는 새 그룹을 만들고 DedicatedAdmin 계정을 추가 합니다.

1. **Office 관리 센터** 탭의 왼쪽된 탐색 영역에서 그룹 아이콘을 클릭 하 고 **그룹**을 클릭 합니다.
2. **그룹 추가**클릭 합니다.
3. **새 그룹** 페이지에서 **GlobalAdmins**를 입력 합니다.
4. 전역 관리자 계정을 **선택 소유자** 클릭을 클릭 하 고 다음을 클릭 **추가 > 닫기**합니다.
5. 그룹 목록에서 **GlobalAdmins** 그룹을 클릭 합니다.
6. **GlobalAdmins** 페이지에서 **구성원에 대 한 편집**을 클릭 하 고 **구성원 추가**클릭 합니다.
7. 목록에서 **DedicatedAdmin** 계정을 클릭 하 고 다음을 클릭 **저장 > 닫기 > 닫기 > 관리 센터**합니다.

다음으로, 전역 관리자 계정에 대 한 다단계 인증을 요구 하도록 하 고 로그인 위험 중간 또는 높은 경우 인증을 거부 하려면 조건부 액세스 정책을 만듭니다.

이 첫번째 정책 MFA 모든 전역 관리자 계정을 사용 하 여는 필요 합니다.

1. 브라우저의 새 탭에서로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.
2. 클릭 **Azure Active Directory > 조건부 액세스**합니다.
3. **조건부 액세스-정책** 블레이드 클릭 **기본 정책: admins (미리 보기)에 대 한 필요 MFA**합니다.
4. **초기 계획 정책...** 블레이드 클릭 **즉시 정책을 사용 하 여 > 저장**합니다.

이 두번째 정책 블록에 대 한 액세스 로그인 위험 중간 규모 또는 높은 경우 전역 관리자 계정 인증 합니다.

1. **조건부 액세스-정책** 블레이드 **새 정책**을 클릭 합니다.
2. **새로운** 블레이드 **전역 관리자** **이름**에 입력 합니다.
3. **배정** 섹션에서 **사용자 및 그룹을**클릭 합니다.
4. **사용자 및 그룹** 블레이드 **포함** 탭에서 클릭 **사용자 및 그룹 선택 > 사용자 및 그룹 > 선택**합니다.
5. **선택** 블레이드 클릭은 **GlobalAdmins > 선택 > 완료**합니다.
6. **배정** 섹션에서 **조건**을 클릭 합니다.
7. **조건** 블레이드에서 **로그인 위험**을 클릭, **구성**에 대 한 **예** 를 클릭 합니다., **높음** 및 **중간**규모를 클릭 하 고 **을 선택** 하 고 **완료**를 클릭 합니다.
8. **새로운** 블레이드의 **액세스 제어** 섹션에서 **권한 부여**를 클릭 합니다.
9. **부여** 블레이드에서 **블록 액세스**클릭 한 다음 **선택**을 클릭 합니다.
10. **새로운** 블레이드 **정책을 사용 하도록 설정**하는 것에 대 한 **에서** 클릭 하 고 **만들기**를 클릭 합니다.
11. **Azure 포털** 및 **Office 관리 센터** 탭을 닫습니다.

첫번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다. MFA 사용자 계정을 구성 하 라는 메시지가 나타납니다. 이 첫번째 정책이 적용 되는 것을 보여줍니다.

정보 및 프로덕션 환경에서 전역 관리자 계정을 보호 하기 위해 링크에 대 한 Identity 단계에서 [암호로 보호 전역 관리자 계정](identity-designate-protect-admin-accounts.md) 단계를 참조 합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 엔터프라이즈 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

---
title: Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 다음 단계를 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정을 보호 합니다.
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290861"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호

관리자 계정이 최대한 안전한 지 확인 하 여 조직에서 디지털 공격을 방지할 수 있습니다. 이 문서에서는 Office 365 Cloud App Security 및 Azure AD 조건부 액세스 정책을 사용 하 여 전역 관리자 계정을 보호 하는 방법을 설명 합니다.

Microsoft 365 Enterprise 테스트 환경에서는 다음과 같은 두 가지 단계를 통해 전역 관리자 계정을 보호 합니다.

1.  Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2.  전용 전역 관리자 계정을 보호 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

> [!NOTE]
> Microsoft 365 Enterprise 테스트 환경에서는 E5 버전의 Office 365 및 EMS (엔터프라이즈 관리 + Security)가 사용 됩니다. office 365 Cloud App Security 기능은 E5 버전 Office 365 에서만 사용할 수 있습니다. 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방법으로 전역 관리자 계정 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.

  
> [!NOTE]
> 전역 관리자 계정 보호를 테스트 하는 경우에는 AD DS (Active directory 도메인 서비스)에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서이를 시험해 볼 수 있도록 여기에 제공 되는 옵션입니다. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>2 단계: Cloud App Security and 조건부 액세스 정책 구성

먼저 전역 관리자 계정 작업을 모니터링 하 고 전역 관리자 계정의 전자 메일 주소로 알림을 보내도록 Office 365 Cloud App Security policy를 만듭니다. 

1. 전역 관리자 계정을 사용 하 여 [Office 365 Security & 준수 포털](https://protection.office.com/) 에 로그인 합니다.
2. 왼쪽 탐색 창에서 **경고 > 고급 알림 관리**를 클릭 합니다.
3. **고급 알림 관리** 페이지에서 **office 365 cloud app security 사용**을 클릭 하 고 **office 365 cloud app security로 이동을**클릭 합니다.
4. 새 **대시보드** 탭에서 **> 정책 제어**를 클릭 합니다.
5. **정책** 페이지에서 **정책 만들기**를 클릭 한 다음 **활동 정책을**클릭 합니다.
6. **정책 이름**에 **관리 활동**을 입력 합니다.
7. **정책 심각도**에서 **높음**을 클릭합니다.
8. **범주**에서 **권한이 부여 된 계정을**클릭 합니다.
9. **정책에 대 한 필터 만들기**의 **다음 작업과 일치 하는 작업**의 **관리 작업**을 클릭 합니다.
10. **경고**에서 **전자 메일로 경고 보내기**를 클릭합니다. **받는 사람**에서 전역 관리자 계정의 전자 메일 주소를 입력합니다.
11. 페이지 하단에서 **만들기**를 클릭합니다.
12. **대시보드** 탭을 닫습니다.
    
다음으로, 새 사용자 계정을 전용 전역 관리자로 만듭니다.

1. 별도의 탭에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/)를 엽니다.
2. **활성 사용자**에서 **사용자 추가**를 클릭 합니다.
3. **새 사용자** 페이지에서 **이름**, **표시 이름**및 **사용자 이름**에 **DedicatedAdmin** 을 입력 합니다.
4. **암호**를 클릭 하 고 **암호 만들기**를 클릭 한 다음 강력한 암호를 입력 합니다. 이 새 계정의 암호를 안전한 위치에 기록 합니다.
5. **이 사용자가 처음 로그인 할 때 암호를 변경 하도록**합니다 .를 선택 합니다.
6. **역할**을 클릭 하 고 **전역 관리자**를 클릭 합니다.
7. **제품 라이선스**를 클릭 하 고 **enterprise Mobility + Security e5** 및 **Office 365 enterprise E5 라이선스** 를 켭니다.
8. **추가**를 클릭합니다.
9. **사용자 추가 됨 페이지**에서 **전자 메일로 암호 보내기를**선택 취소 하 고 **닫기를**클릭 합니다.

그런 다음 globaladmins 라는 새 그룹을 만들고 여기에 DedicatedAdmin 계정을 추가 합니다.

1. **Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 그룹 아이콘을 클릭 한 다음 **그룹**을 클릭 합니다.
2. **그룹 추가를**클릭 합니다.
3. **새 그룹** 페이지에서 **globaladmins**를 입력 합니다.
4. **소유자 선택을** 클릭 하 고 전역 관리자 계정을 클릭 한 후에 **> 닫기 추가**를 클릭 합니다.
5. 그룹 목록에서 **globaladmins** 그룹을 클릭 합니다.
6. **globaladmins** 페이지에서 **구성원에 대해 편집**을 클릭 한 다음 **구성원 추가**를 클릭 합니다.
7. 목록에서 **DedicatedAdmin** 계정을 클릭 한 다음 **> 닫기 > 닫기 > 관리 센터**를 클릭 합니다.

그런 다음 전역 관리자 계정에 대해 다단계 인증을 요구 하 고 로그인 위험이 중간 또는 높은 경우 인증을 거부 하도록 조건부 액세스 정책을 만듭니다.

이 첫 번째 정책에서는 모든 전역 관리자 계정에서 MFA를 사용 해야 합니다.

1. 브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.
2. **Azure Active Directory > 조건부 액세스**를 클릭 합니다.
3. **조건부 액세스 – 정책** 블레이드에서 **기본 정책: 관리자에 게 MFA 필요 (미리 보기)** 을 클릭 합니다.
4. **기본 정책 ...** 블레이드에서 **정책 즉시 사용 > 저장**을 클릭 합니다.

이 두 번째 정책은 로그인 위험이 보통 또는 높음 인 경우 전역 관리자 계정 인증에 대 한 액세스를 차단 합니다.

1. **조건부 액세스 – 정책** 블레이드에서 **새 정책을**클릭 합니다.
2. **새** 블레이드에서 **이름**에 **전역 관리자** 를 입력 합니다.
3. **할당** 섹션에서 **사용자 및 그룹**을 클릭 합니다.
4. **사용자 및 그룹** 블레이드에서 **포함** 탭에서 사용자 및 **그룹 > 사용자 및 그룹 > 선택**을 클릭 합니다.
5. **Select** 블레이드에서 **globaladmins > Select > Done**을 클릭 합니다.
6. **배정** 섹션에서 **조건을**클릭 합니다.
7. **조건** 블레이드에서 **로그인 위험**을 클릭 하 고, **구성**에 대해 **예** 를 클릭 하 고, **높음** 및 **중간**을 차례로 클릭 한 다음 **선택** 및 **완료**를 클릭 합니다.
8. **새** 블레이드의 **액세스 제어** 섹션에서 **부여**를 클릭 합니다.
9. **허용** 블레이드에서 **액세스 차단을**클릭 한 다음 **선택을**클릭 합니다.
10. **새** 블레이드에서 **정책을 사용 하도록 설정을**클릭 하 고 **만들기**를 클릭 합니다. ****
11. **Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.

첫 번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다. 사용자 계정에서 MFA를 구성 하 라는 메시지가 표시 됩니다. 이는 첫 번째 정책을 적용 하는 것을 보여 줍니다.

프로덕션에서 전역 관리자 계정을 보호 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [전역 관리자 계정 보호](identity-designate-protect-admin-accounts.md#identity-global-admin) 단계를 참조 하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 엔터프라이즈 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)

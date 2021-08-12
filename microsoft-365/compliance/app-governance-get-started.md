---
title: 앱 거버넌스 시작
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱을 관리하는 앱 거버넌스 기능을 시작하세요.
ms.openlocfilehash: dc07acab3d58f8449f01f09f45c3bc78b66d0e3e
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541208"
---
# <a name="get-started-with-app-governance-in-preview"></a>앱 거버넌스 시작(미리 보기)

Microsoft Cloud App Security에서 앱 거버넌스 추가 항목 사용을 시작하려면 다음을 수행합니다.

1. 계정이 적절한 수준의 라이선스를 보유하고 있는지 확인합니다. 앱 거버넌스는 MCAS(Microsoft Cloud App Security)의 추가 기능이므로 계정은 MCAS는 독립 실행형 제품 또는 아래에 나열된 다양한 라이선스 패키지의 일부를 통해 라이선스를 보유하고 있어야 합니다.
1. 포털에서 앱 거버넌스 페이지에 액세스하려면 아래에 나열된 관리자 역할 중 하나가 있어야 합니다.
1. 조직의 테넌트 등록은 [북미, 유럽 또는 아프리카의 지원 대상 지역](app-governance-countries.md) 중 하나여야 합니다.

## <a name="licensing-for-app-governance"></a>앱 거버넌스 라이선싱

앱 거버넌스를 시작하기 전에 [Microsoft 365 관리 센터 구독](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions) 및 추가 기능을 확인해야 합니다. 앱 거버넌스에 액세스하고 사용하려면 조직에 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

- Microsoft Cloud App Security
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 개발자(Windows 및 오디오 회의 제외)
- Microsoft 365 E5 Information Protection 및 거버넌스
- Microsoft 365 E5 Security
- Microsoft 365 E5(통화 시간 포함)
- Microsoft 365 E5(오디오 회의 제외)
- 교직원용 Microsoft 365 A5 규정 준수
- 학생용 Microsoft 365 A5 규정 준수
- 교직원용 Microsoft 365 A5
- 학생용 Microsoft 365 A5
- 교직원용 Microsoft 365 A5 Information Protection 및 거버넌스
- 학생용 Microsoft 365 A5 Information Protection 및 거버넌스
- 교직원용 Microsoft 365 A5 Security
- 학생용 Microsoft 365 A5 Security
- 학생용 Microsoft 365 A5 사용 혜택
- 교직원용 Microsoft 365 A5(통화 시간 포함)
- 학생용 Microsoft 365 A5(통화 시간 포함)
- 교직원용 Microsoft 365 A5(오디오 회의 제외)
- 학생용 Microsoft 365 A5(오디오 회의 제외)
- 학생용 Microsoft 365 A5(오디오 회의 제외) 사용 혜택

## <a name="administrator-roles"></a>관리자 역할

앱 거버넌스 페이지를 보거나 정책 및 설정을 관리하려면 다음 관리자 역할 중 하나가 필요합니다.

- 응용 프로그램 관리자
- 클라우드 응용 프로그램 관리자
- 회사 관리자
- 규정 준수 관리자
- 규정 준수 데이터 관리자
- 규정 준수 읽기 권한자(읽기 전용)
- 전역 읽기 권한자
- 보안 관리자
- 보안 운영자
- 보안 읽기 권한자(읽기 전용)

> [!NOTE]
> 전역 관리자만이 앱 거버넌스 무료 평가판을 활성화할 수 있습니다.

각 역할의 기능은 다음과 같습니다.

| 역할 | 대시보드 읽기 | 모든 앱 읽기 |정책 읽기 | 정책 만들기, 업데이트 또는 삭제 | 경고 읽기 | 경고 업데이트 | 설정 읽기 | 설정 업데이트 | 수정 사항 읽기 | 수정 사항 업데이트 |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| 애플리케이션 관리자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| 클라우드 애플리케이션 관리자 | ![확인 표시](..\media\checkmark.png) | | | | | | | | | |
| 회사 관리자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| 규정 준수 관리자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 규정 준수 데이터 관리자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 규정 준수 읽기 권한자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | | |
| 전역 읽기 권한자  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | | |
| 보안 관리자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 보안 운영자 | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 보안 읽기 권한자  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | |
|||||||||| | |

각 역할에 대한 자세한 내용은 [관리자 역할 권한](/azure/active-directory/roles/permissions-reference)을 참조하십시오.

## <a name="add-app-governance-to-your-microsoft-365-account"></a>Microsoft 365 계정에 앱 거버넌스 추가

기존 Microsoft 365 고객:

1. [Microsoft 365 관리 센터](https://admin.microsoft.com),**청구 - 구매 서비스** 로 이동하여 **추가 기능** 을 클릭합니다.
1. 앱 거버넌스 카드에서 **세부 정보** 를 클릭합니다.
1. **무료 평가판** 을 클릭합니다.
1. 선택한 테넌트에 앱 거버넌스를 추가하기 위해 요청된 정보를 작성합니다. 새 고객인 경우 먼저 계정을 만들기 위해 정보를 제공한 후 평가판 기간 동안 사용할 테넌트를 생성합니다. 이 작업이 완료되면 평가판에 앱 거버넌스를 추가할 수 있습니다.

신규 Microsoft 365 고객:

1. 이 페이지 상단에 **무료 계정** 버튼을 클릭합니다.
1. **비즈니스용 Microsoft 365 체험** 아래 **1개월 무료 체험** 을 클릭합니다.

모두:

1. 등록 포털에서 평가판에 사용할 전자 메일 주소를 입력합니다. 기존 고객인 경우 계정과 연결된 전자 메일을 사용합니다. **다음** 클릭
1. 로그인한 후 **지금 체험** 을 클릭하여 무료 평가판을 받으세요.
1. **계속** 을 클릭하여 페이지를 닫고 평가판 설정을 시작합니다. 새 앱 거버넌스 고객의 경우 앱 거버넌스 인스턴스를 사용할 수 있을 때까지 최대 2시간이 걸립니다. 기존 고객의 경우 기존 서비스가 중단되지 않습니다.

  > [!NOTE]
  아직 계정이 없는 경우 평가판을 진행하기 전에 새 계정을 설정하라는 메시지가 표시됩니다.

1. AAD 테넌트에서 사용 가능한 도메인 이름을 입력하고 **사용이 가능한지 확인** 을 클릭합니다. 자동으로 관리자 역할이 할당되고(앱 거버넌스에서 기존 역할이 없는 경우) 언제든지 도메인 이름을 변경하거나 나중에 Microsoft 365 관리 센터를 통해 더 많은 테넌트를 구매할 수 있습니다.
1. 계정에 로그인하는 데 사용할 사용자 이름과 암호를 입력합니다. **등록** 을 클릭합니다.
1. **시작** 을 클릭하여 앱 거버넌스 포털로 이동하거나 **구독 관리** 를 클릭하여 Microsoft 365 관리 센터로 이동합니다.

## <a name="add-integration-with-mcas"></a>MCAS와의 통합 추가 

필수 구성 요소:

- Office 365는 Cloud App Security에 연결되어 있습니다.
- Office 365 Azure AD 앱이 사용 설정되었습니다.

Cloud App Security와 앱 거버넌스 동기화를 활성화하려면 다음 단계를 따르세요.

1. Microsoft Cloud App Security 포털로 이동 – [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. 톱니바퀴 아이콘(오른쪽 상단)을 클릭하고 **설정** 을 선택합니다.
1. **위협 보호** 에서 **앱 거버넌스** 를 선택합니다.
1. **앱 거버넌스 통합 사용** 을 클릭한 다음 **저장** 을 선택합니다.

다음으로 MCAS에서 새로 활성화된 정책을 검토합니다. 통합 기능을 사용하도록 설정하면 새 정책이 표시되는 데 몇 분 정도 걸릴 수 있습니다.

- Microsoft 365 OAuth 앱 평판
- Microsoft 365 OAuth 피싱 감지
- Microsoft 365 OAuth 앱 거버넌스
- MCAS 대시보드에서 앱 거버넌스 위젯 검토
- MCAS 알림에서 새로 생성된 앱 거버넌스 알림 검토
- 앱 거버넌스 정책 목록에서 MCAS M365 OAuth 정책 검토
- 앱 거버넌스 알림에서 새로 생성된 MCAS M365 OAuth 알림 검토

## <a name="canceling-your-trial"></a>평가판 취소

비공개 미리 보기에 참여하지 않았고 앱 거버넌스 평가판을 취소하려는 경우 CXE 담당자와 통신하거나 다음 단계를 사용할 수 있습니다.

1. Microsoft 365 관리 센터에서 **청구** > **내 제품** 으로 이동합니다.
1. 앱 거버넌스 평가판으로 이동하여 점 3개를 클릭하고 **구독 취소** 를 선택합니다.
1. 결과 플라이아웃 창에서 취소 이유와 추가 피드백을 제공하고 **구독 취소** 를 선택합니다.
1. 표시되는 팝업 화면에서 **구독 취소** 를 선택합니다. 평가판이 취소되고 앱 거버넌스에 액세스할 수 없으며 앱 거버넌스 데이터가 삭제됩니다(앱 거버넌스 인사이트 및 탐지를 생성하는 데 사용되는 로그 데이터 - 이메일 또는 기타 파일은 영향을 받지 않음).

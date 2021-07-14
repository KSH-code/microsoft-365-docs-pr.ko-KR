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
ms.openlocfilehash: 0fc00819947d3d472de9199b0381c6f33de0acd6
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420317"
---
# <a name="get-started-with-app-governance-in-preview"></a>앱 거버넌스 시작(미리 보기)

Microsoft Cloud App Security 앱 거버넌스 기능 사용을 시작하려면 다음을 수행합니다.

1. 계정이 적절한 수준의 라이선스를 보유하고 있는지 확인합니다. 앱 거버넌스는 MCAS(Microsoft Cloud App Security)의 추가 기능이므로 계정은 MCAS는 독립 실행형 제품 또는 아래에 나열된 다양한 라이선스 패키지의 일부로 라이선스를 보유하고 있어야 합니다.
1. 포털에서 앱 거버넌스 페이지에 액세스하려면 아래에 나열된 관리자 역할 중 하나가 있어야 합니다.

## <a name="licensing-for-app-governance"></a>앱 거버넌스 라이선싱

앱 거버넌스를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 및 추가 기능을 확인해야 합니다. 앱 거버넌스에 액세스하고 사용하려면 조직에 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

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

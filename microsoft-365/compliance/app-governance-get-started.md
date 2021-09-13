---
title: 앱 거버넌스 시작
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.custom: admindeeplinkMAC
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱을 관리하는 앱 거버넌스 기능을 시작하세요.
ms.openlocfilehash: 35a04beb04f22558ca150294ebb566a8284d5270
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190032"
---
# <a name="get-started-with-app-governance-in-preview"></a>앱 거버넌스 시작(미리 보기)

Microsoft Cloud App Security에 대한 앱 거버넌스 추가 기능 사용을 시작하려면 다음 세 단계를 실행해야 합니다.

## <a name="step-1-meet-the-licensing-and-administrator-role-prerequisites"></a>1단계: 라이선스 및 관리자 역할 필수 구성 요소 충족

1. 계정이 [적절한 수준의 라이선스](#licensing-for-app-governance)를 보유하고 있는지 확인합니다. 앱 거버넌스는 MCAS(Microsoft Cloud App Security)의 추가 기능이므로 계정은 MCAS는 독립 실행형 제품 또는 다양한 라이선스 패키지의 일부로 라이선스를 보유하고 있어야 합니다.
1. 포털에서 앱 거버넌스 페이지에 액세스하려면 아래에 나열된 [관리자 역할](#administrator-roles) 중 하나가 있어야 합니다.
1. 무료 평가판을 활성화하려면 조직의 청구 주소가 [북미, 유럽 또는 아프리카에서 지원되는 지역](app-governance-countries.md) 중 하나여야 합니다.

## <a name="step-2-sign-up-for-free-trial-of-app-governance"></a>2단계: 앱 거버넌스 무료 평가판에 등록

신규 Microsoft 365 고객용:

1. 이 페이지 맨 위에서  **무료 계정** 버튼을 선택합니다.
1.  **비즈니스용 Microsoft 365 체험** 아래에서 **1개월 무료 체험** 을 선택합니다.
1. 등록 단계별 실행을 완료합니다.
1. 기존 Microsoft 365 고객용 단계별 실행을 계속 진행합니다.

기존 Microsoft 365 고객용:

1. [평가판 등록 페이지](https://admin.microsoft.com/Commerce/Trial.aspx?OfferId=20be85b6-b196-402c-82b4-36b4e72862dc)로 이동합니다. 
1. 앱 거버넌스를 추가하는 단계별 실행을 완료합니다. 다음 그래픽에 표시된 바와 같이 간단하게 등록할 수 있습니다.

:::image type="content" source="../media/manage-app-protection-governance/app-governance-signup2.gif" alt-text="계정에 앱 거버넌스를 추가하는 간단한 단계별 실행":::

## <a name="step-3-add-integration-with-mcas"></a>3단계: MCAS와의 통합 추가

필수 조건:

- Office 365는 Cloud App Security에 연결되어 있습니다.
- Office 365 Azure AD 앱이 사용 설정되었습니다.

Cloud App Security와 앱 거버넌스 동기화를 사용하려면 다음 단계별 실행을 따르세요.

1. Microsoft Cloud App Security 포털 – [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)(으)로 이동합니다.
1. 톱니 바퀴형 아이콘(오른쪽 상단)을 선택하고 **설정** 을 선택합니다.
1. **위협 보호** 에서 **앱 거버넌스** 를 선택합니다.
1. **앱 거버넌스 통합 사용** 을 선택한 다음 **저장** 을 선택합니다.

다음으로 MCAS에서 새로 활성화된 정책을 검토합니다. 통합 기능을 사용하도록 설정하면 새 정책이 표시되는 데 몇 분 정도 걸릴 수 있습니다.

- Microsoft 365 OAuth 앱 평판
- Microsoft 365 OAuth 피싱 감지
- Microsoft 365 OAuth 앱 거버넌스
- MCAS 대시보드에서 앱 거버넌스 위젯 검토
- MCAS 알림에서 새로 생성된 앱 거버넌스 알림 검토
- 앱 거버넌스 정책 목록에서 MCAS Microsoft 365 OAuth 정책 검토
- 앱 거버넌스 알림에서 새로 생성된 MCAS Microsoft 365 OAuth 알림 검토

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

> [!NOTE]
> 전역 관리자 역할만 앱 거버넌스 무료 평가판을 활성화할 수 있습니다.

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
| 애플리케이션 관리자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| 클라우드 애플리케이션 관리자 | ![확인 표시](..\media\checkmark.png) | | | | | | | | | |
| 회사 관리자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| 규정 준수 관리자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 규정 준수 데이터 관리자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 규정 준수 읽기 권한자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | | |
| 전역 읽기 권한자  | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | | |
| 보안 관리자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 보안 운영자 | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | |
| 보안 읽기 권한자  | ![확인 표시입니다.](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) |  | ![확인 표시](..\media\checkmark.png) | |
|||||||||| | |

각 역할에 대한 자세한 내용은 [관리자 역할 권한](/azure/active-directory/roles/permissions-reference)을 참조하십시오.

## <a name="canceling-your-trial"></a>평가판 취소

비공개 미리 보기에 참여하지 않았고 앱 거버넌스 평가판을 취소하려는 경우 CXE 담당자와 통신하거나 다음 단계를 사용할 수 있습니다.

1. Microsoft 365 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">**제품**</a> 페이지로 이동합니다.
1. 앱 거버넌스 평가판으로 이동하여 점 3개를 클릭하고 **구독 취소** 를 선택합니다.
1. 결과 플라이아웃 창에서 취소 이유와 추가 피드백을 제공하고 **구독 취소** 를 선택합니다.
1. 표시되는 팝업 화면에서 **구독 취소** 를 선택합니다. 평가판이 취소되고 앱 거버넌스에 액세스할 수 없으며 앱 거버넌스 데이터가 삭제됩니다(앱 거버넌스 인사이트 및 탐지를 생성하는 데 사용되는 로그 데이터 - 이메일 또는 기타 파일은 영향을 받지 않음).

## <a name="known-issues-for-the-public-preview"></a>공개 미리 보기의 알려진 문제

앱 거버넌스 팀은 미리 보기에 대해 다음과 같은 알려진 문제를 확인했습니다. 

- Microsoft Defender와 앱 거버넌스 경고 간의 양방향 동기화 - 현재 Defender에서 해결된 경고는 앱 거버넌스에서도 수동으로 해결해야 합니다.

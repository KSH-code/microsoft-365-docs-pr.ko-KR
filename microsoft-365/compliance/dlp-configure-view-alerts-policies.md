---
title: 데이터 손실 방지 정책에 대한 경고 구성 및 보기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 데이터 손실 방지 정책에 대한 경고를 정의하고 관리하는 방법을 학습합니다.
ms.openlocfilehash: 629f0e84b1118313d6968a07a24d4e27b12f0bce
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785453"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>데이터 손실 방지에 대한 경고 구성 및 보기

DLP(데이터 손실 방지) 정책은 중요한 항목의 의도하지 않은 공유를 방지하기 위해 보호 조치를 취할 수 있습니다. 중요한 항목에 대해 작업을 수행하면 DLP에 대한 알림을 구성하여 알림을 알 수 있습니다. 이 문서에서는 DLP(데이터 손실 방지) 정책에 연결된 다양한 경고 정책을 정의하는 방법을 보여줍니다. 새 DLP 경고 관리 대시보드를 사용하여 DLP <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a> 정책 위반에 Microsoft 365 규정 준수 센터, 이벤트 및 관련 메타데이터를 보는 방법을 볼 수 있습니다.

<!-- LEFT OFF HERE-->

## <a name="features"></a>기능

이 기능의 일부로는 다음과 같은 기능이 있습니다.

-   **DLP 경고** <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">관리</a>대시보드: Microsoft 365 규정 준수 센터 에서 이 대시보드에는 다음 워크로드에 적용된 DLP 정책에 대한 경고가 표시됩니다.

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   디바이스
-   **고급 경고 구성 옵션:** 이러한 옵션은 DLP 정책 제작 흐름의 일부입니다. 다양한 경고 구성을 만드는 데 사용할 수 있습니다. 이벤트 수 또는 유출된 데이터의 크기에 따라 단일 이벤트 경고 또는 집계된 경고를 만들 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

시작하기 전에 다음 필수 필수가 있는지 확인하세요.

-   DLP 경고 관리 대시보드에 대한 라이선스
-   경고 구성 옵션에 대한 라이선싱
-   역할

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드에 대한 라이선스

DLP의 모든 적합한 Office 365 새 DLP 경고 관리 대시보드에 액세스할 수 있습니다. 시작을 위해 Office 365, SharePoint Online 및 Exchange Online DLP를 비즈니스용 OneDrive. Office 365 DLP의 라이선스 요구 사항에 대한 자세한 내용은 사용자에게 서비스를 혜택을 제공할 수 있는 권한을 제공하는 라이선스를 [참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

Teams DLP를 사용할 수 있는 끝점 [DLP를](endpoint-dlp-learn-about.md) 사용하는 고객에게는 끝점 DLP 정책 경고 및 [DLP](dlp-microsoft-teams.md) Teams 관리 대시보드에서 DLP 정책 경고가 표시됩니다.

### <a name="licensing-for-alert-configuration-options"></a>경고 구성 옵션에 대한 라이선싱

- **단일 이벤트** 경고 구성: E1, F1 또는 G1 구독이 있는 조직이나 E3 또는 G3 구독이 있는 조직은 활동이 발생할 때마다 경고가 트리거되는 경우만 경고 정책을 만들 수 있습니다.
- **집계된 경고 구성:** 임계값을 기준으로 집계 경고 정책을 구성하려면 다음 구성 중 하나를 설정해야 합니다.
  - E5 또는 G5 구독
  - E1, F1 또는 G1 구독 또는 다음 기능 중 하나를 포함하는 E3 또는 G3 구독
    - Office 365 Advanced Threat Protection Plan 2
    - Microsoft 365 E5 Compliance
    - Microsoft 365 및 추가 기능 라이선스 감사

### <a name="roles"></a>역할

DLP 경고 관리 대시보드를 보거나 DLP 정책에서 경고 구성 옵션을 편집하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.

-   규정 준수 관리자
-   규정 준수 데이터 관리자
-   보안 관리자
-   보안 운영자
-   보안 읽기 권한자

DLP 경고 관리 대시보드에 액세스하려면 경고 관리 역할 및 다음 역할 중 하나가 필요합니다.

-   DLP 규정 준수 관리
-   View-Only DLP 준수 관리

## <a name="alert-configuration-experience"></a>경고 구성 환경

집계된 경고 구성 [](#licensing-for-alert-configuration-options)옵션을 사용할 수 있는 자격이 있는 경우 DLP 정책 작성 환경의 다음 옵션이 인라인으로 표시됩니다.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="집계된 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

이러한 경고 구성 옵션을 사용하여 경고가 트리거되기 전에 DLP 규칙 일치가 발생할 수 있는 방법을 정의하는 설정을 구성할 수 있습니다. 이 구성을 사용하면 활동이 정책 조건과 일치하거나 활동 수 또는 유출된 데이터의 볼륨에 따라 특정 임계값을 초과할 때마다 경고를 생성하도록 정책을 설정할 수 있습니다.

단일 이벤트 경고 구성 [](#licensing-for-alert-configuration-options)옵션을 사용할 수 있는 경우 DLP 정책 작성 환경의 다음 경고 구성 옵션이 표시됩니다. 이 옵션을 사용하여 사용자 활동으로 인하여 DLP 규칙 일치가 발생할 때마다 발생하는 경고를 만들 수 있습니다.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="단일 이벤트 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드

DLP 경고 관리 대시보드에서 작업하는 경우:

1.  에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>데이터 손실 **방지로 이동하십시오.**

2.  경고 **탭을 선택하여** DLP 경고 대시보드를 볼 수 있습니다.

    -   필터를 선택하면 경고 목록을 구체화할 수 있습니다. 열 **사용자 지정을 선택하면** 표시하려는 속성이 나열됩니다. 모든 열에서 경고를 오차 또는 내선 순서로 정렬할 수도 있습니다.
    -   경고를 선택하여 세부 정보를 봐야 합니다.

        :::image type="content" source="../media/alert-details.png" alt-text="Screenshot showing alert details on the DLP alert management dashboard." border="false":::

1.  경고와  연결된 모든 이벤트를 표시하려면 이벤트 탭을 선택합니다. 특정 이벤트를 선택하면 세부 정보를 볼 수 있습니다. 다음 표에는 일부 이벤트 세부 정보가 표시됩니다.
    
    | 범주          | 속성 이름                 | 설명                                                                | 적용 가능한 이벤트 유형                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*이벤트 세부 정보*||
    |      | Id                            | 이벤트와 연결된 고유 ID                                        | 모든 이벤트                               |
    |                   | 위치                      | 이벤트가 검색된 워크로드                                      | 모든 이벤트                               |
    |                   | 활동 시간              | DLP 위반을 일으운 사용자 활동 시간                    | 모든 이벤트                               |
    |*영향을 미치는 엔터티*||
    |  | 사용자                          | DLP 위반을 유발한 사용자                                          | 모든 이벤트                               |
    |                   | Hostname(호스트 이름)                      | DLP 위반이 검색된 컴퓨터의 호스트 이름입니다.              | 장치 이벤트                           |
    |                   | IP 주소                    | 컴퓨터의 IP 주소                                                  | 장치 이벤트                           |
    |                   | 파일 경로                     | 위반과 관련된 파일의 절대 경로                        | SharePoint, OneDrive 및 장치 이벤트 |
    |                   | 전자 메일 받는 사람              | DLP 정책을 위반한 전자 메일의 받는 사람                       | Exchange 이벤트                          |
    |                   | 전자 메일 제목                 | DLP 정책을 위반한 전자 메일의 제목                          | Exchange 이벤트                          |
    |                   | 전자 메일 첨부 파일             | DLP 정책을 위반한 전자 메일의 첨부 파일 이름         | Exchange 이벤트                          |
    |                   | 사이트 소유자                    | 사이트 소유자의 이름                                                     | SharePoint 및 OneDrive 이벤트           |
    |                   | 사이트 URL                      | 사이트 또는 SharePoint 사이트의 OneDrive URL입니다.                                | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일을 만들었음                  | 파일 만들기 시간                                                      | SharePoint 및 OneDrive 이벤트           |
    |                   | 마지막으로 수정한 파일            | 파일을 마지막으로 수정한 시간                                  | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일 크기                     | 파일 크기                                                           | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일 소유자                    | 파일의 소유자                                                          | SharePoint 및 OneDrive 이벤트           |
    |*정책 세부 정보*||
    |     | 일치하는 DLP 정책            | 일치하는 DLP 정책의 이름                                    | 모든 이벤트                               |
    |                   | 일치하는 규칙                  | 일치하는 DLP 정책의 DLP 규칙 이름                    | 모든 이벤트                               |
    |                   | 검색된 중요한 정보 유형 | DLP 정책의 일부로 검색된 중요한 정보 유형 | 모든 이벤트                               |
    |                   | 수행한 작업                 | 일치하는 DLP 정책의 일부로 수행된 작업                          | 모든 이벤트                               |
    |                   | 사용자 과도 정책          | 사용자가 정책 팁을 통해 정책을 오버로이드할지 여부                | 모든 이벤트                               |
    |                   | 정당성 텍스트에 대한 의구성   | 정책 팁을 오버라이드하기 위해 제공된 사당성                          | 모든 이벤트                               |
    
1.  중요한 정보 **유형 탭을 선택하여** 콘텐츠에서 검색된 중요한 정보 유형에 대한 세부 정보를 볼 수 있습니다. 세부 정보에는 신뢰도 및 개수가 포함됩니다.

2.  경고를 조사한 후  경고 관리를 선택하고 **상태(활성,** 조사 **중,** **해지** 또는 **해결)를 변경합니다.** 조직의 다른 사용자에게 설명을 추가하고 알림을 할당할 수도 있습니다.

    -   워크플로 관리 기록을 확인하려면 관리 로그 **를 선택하세요.**
    -   경고에 대해 필요한 작업을 수행한 후 경고 상태를 해결된 으로 **설정하십시오.**

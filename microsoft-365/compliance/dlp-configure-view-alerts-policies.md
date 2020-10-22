---
title: DLP 정책에 대 한 경고 구성 및 보기 (미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: DLP 정책에 대 한 알림을 정의 하 고 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651476"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>DLP 정책에 대 한 경고 구성 및 보기 (미리 보기)

이 문서에서는 DLP (데이터 손실 방지) 정책에 연결 된 다양 한 경고 정책을 정의 하는 방법을 설명 합니다. [Microsoft 365 준수 센터](https://compliance.microsoft.com/) 의 새 DLP 경고 관리 대시보드를 사용 하 여 DLP 정책 위반에 대 한 경고, 이벤트 및 관련 메타 데이터를 확인 하는 방법을 확인할 수 있습니다.

## <a name="features"></a>기능

이 미리 보기에는 다음과 같은 기능이 포함 됩니다.

-   **DLP 경고 관리 대시보드**: [Microsoft 365 준수 센터](https://compliance.microsoft.com/)에서이 대시보드에는 다음 작업에 적용 되는 DLP 정책에 대 한 경고가 표시 됩니다.

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   장치
-   **고급 경고 구성 옵션**: 이러한 옵션은 DLP 정책 제작 흐름의 일부입니다. 이를 통해 다양 한 경고 구성을 만들 수 있습니다. 이벤트 수 또는 누수 된 데이터의 크기에 따라 단일 이벤트 경고나 집계 된 경고를 만들 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

시작 하기 전에 필요한 필수 구성 요소가 있는지 확인 합니다.

-   DLP 경고 관리 대시보드 용 라이선스
-   경고 구성 옵션에 대 한 라이선스
-   역할

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드 라이선스

Office 365 DLP에 적합 한 모든 테 넌 트는 새 DLP 경고 관리 대시보드에 액세스할 수 있습니다. 시작 하려면 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에 대 한 Office 365 DLP를 사용할 수 있어야 합니다. Office 365 DLP의 라이선스 요구 사항에 대 한 자세한 내용은 [사용자에 게 서비스를 제공할 수 있는 권한을 제공](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)하는 라이선스를 참조 하세요.

[끝점 dlp](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) 공개 미리 보기에 참여 하거나 [팀 dlp](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) 에 적합 한 고객은 dlp 경고 관리 대시보드에서 끝점 Dlp 정책 알림 및 팀 dlp 정책 경고를 볼 수 있습니다.

### <a name="licensing-for-alert-configuration-options"></a>경고 구성 옵션에 대 한 라이선스

-   **단일 이벤트 경고 구성**: E1, F1 또는 G1 구독 또는 E3 또는 G3 구독이 있는 조직은 활동이 발생할 때마다 경고가 트리거되는 경우에만 경고 정책을 만들 수 있습니다.
-   **집계 된 경고 구성**: 임계값을 기반으로 집계 경고 정책을 구성 하려면 다음 구성 중 하나를 수행 해야 합니다.
    -   E5 또는 G5 구독
    -   다음 기능 중 하나를 포함 하는 E1, F1 또는 G1 구독 또는 E3 또는 G3 구독
        -   Office 365 Advanced Threat Protection Plan 2
        -   Microsoft 365 E5 Compliance
        -   Microsoft 365 eDiscovery 및 감사 추가 기능 라이선스

### <a name="roles"></a>역할

Dlp 경고 관리 대시보드를 보거나 DLP 정책에서 경고 구성 옵션을 편집 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

-   준수 관리자
-   준수 데이터 관리자
-   보안 관리자
-   보안 운영자
-   보안 읽기 권한자

DLP 경고 관리 대시보드에 액세스 하려면 다음 역할 및 경고 관리 역할이 필요 합니다.

-   DLP 준수 관리
-   DLP 준수 관리 View-Only

## <a name="alert-configuration-experience"></a>경고 구성 환경

[집계 된 경고 구성 옵션](#licensing-for-alert-configuration-options)을 사용할 수 있는 경우 DLP 정책 제작 환경에서 다음 옵션을 인라인으로 볼 수 있습니다.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="집계 된 경고 구성 옵션을 사용할 수 있는 사용자에 대 한 문제 보고서 옵션을 보여 주는 스크린샷" border="false":::

이러한 경고 구성 옵션을 사용 하 여 경고가 트리거되기 전에 DLP 규칙 일치 빈도를 정의 하는 설정을 구성할 수 있습니다. 이 구성을 사용 하면 활동이 정책 조건과 일치 하거나 활동 수에 따라 또는 노출 되었습니다 데이터의 볼륨을 기반으로 하는 특정 임계값을 초과 하는 경우에 경고를 생성 하는 정책을 설정할 수 있습니다.

[단일 이벤트 경고 구성 옵션](#licensing-for-alert-configuration-options)을 사용할 수 있는 경우 DLP 정책 제작 환경에서 다음과 같은 경고 구성 옵션을 확인할 수 있습니다. 이 옵션을 사용 하면 사용자 활동으로 인해 DLP 규칙 일치가 발생할 때마다 발생 하는 경고를 만들 수 있습니다.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="집계 된 경고 구성 옵션을 사용할 수 있는 사용자에 대 한 문제 보고서 옵션을 보여 주는 스크린샷" border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드

DLP 경고 관리 대시보드를 사용 하려면 다음을 수행 합니다.

1.  [Microsoft 365 준수 센터](https://www.compliance.microsoft.com)에서 **데이터 손실 방지**로 이동 합니다.

2.  DLP 경고 대시보드를 보려면 **알림** 탭을 선택 합니다.

    -   필터를 선택 하 여 경고 목록을 구체화 합니다. **열 사용자 지정** 을 선택 하 여 보려는 속성을 나열 합니다. 열에서 오름차순 이나 내림차순으로 경고를 정렬할 수도 있습니다.
    -   세부 정보를 확인 하려면 경고를 선택 합니다.

        :::image type="content" source="../media/alert-details.png" alt-text="집계 된 경고 구성 옵션을 사용할 수 있는 사용자에 대 한 문제 보고서 옵션을 보여 주는 스크린샷" border="false":::

1.  경고와 연결 된 모든 이벤트를 보려면 **이벤트** 탭을 선택 합니다. 특정 이벤트를 선택 하 여 해당 세부 정보를 볼 수 있습니다.
    다음 표에서는 몇 가지 이벤트 세부 정보를 보여 줍니다.
    
    | 범주          | 속성 이름                 | 설명                                                                | 적용 가능한 이벤트 유형                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*이벤트 세부 정보*||
    |      | Id                            | 이벤트와 연결 된 고유 ID입니다.                                        | 모든 이벤트                               |
    |                   | 위치                      | 이벤트가 검색 된 작업                                      | 모든 이벤트                               |
    |                   | 활동 시간              | DLP 위반을 일으킨 사용자 활동의 시간                    | 모든 이벤트                               |
    |*영향을 받는 엔터티*||
    |  | 사용자                          | DLP 위반을 일으킨 사용자                                          | 모든 이벤트                               |
    |                   | Hostname(호스트 이름)                      | DLP 위반이 검색 된 컴퓨터의 호스트 이름입니다.              | Devices 이벤트                           |
    |                   | IP 주소                    | 컴퓨터의 IP 주소                                                  | Devices 이벤트                           |
    |                   | 파일 경로                     | 위반에 관련 된 파일의 절대 경로입니다.                        | SharePoint, OneDrive 및 장치 이벤트 |
    |                   | 전자 메일 받는 사람              | DLP 정책을 위반한 전자 메일의 받는 사람                       | Exchange 이벤트                          |
    |                   | 전자 메일 제목                 | DLP 정책을 위반한 전자 메일의 제목입니다.                          | Exchange 이벤트                          |
    |                   | 전자 메일 첨부 파일             | DLP 정책을 위반한 전자 메일에 있는 첨부 파일의 이름입니다.         | Exchange 이벤트                          |
    |                   | 사이트 소유자                    | 사이트 소유자의 이름입니다.                                                     | SharePoint 및 OneDrive 이벤트           |
    |                   | 사이트 URL                      | SharePoint 또는 OneDrive 사이트의 전체 URL                                | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일을 만들었음                  | 파일 생성 시간                                                      | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일을 마지막으로 수정한 날짜            | 파일을 마지막으로 수정한 시간입니다.                                  | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일 크기                     | 파일 크기                                                           | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일 소유자                    | 파일 소유자                                                          | SharePoint 및 OneDrive 이벤트           |
    |*정책 세부 정보*||
    |     | 일치 하는 DLP 정책            | 일치 했던 DLP 정책의 이름입니다.                                    | 모든 이벤트                               |
    |                   | 규칙과 일치 됨                  | DLP 정책에서 일치 된 DLP 규칙의 이름입니다.                    | 모든 이벤트                               |
    |                   | 검색 된 중요 한 정보 유형 | DLP 정책의 일부로 검색 된 중요 한 정보 유형 | 모든 이벤트                               |
    |                   | 수행한 작업                 | 일치 하는 DLP 정책의 일부로 수행 되는 작업                          | 모든 이벤트                               |
    |                   | 사용자 과잉 제거 정책          | 사용자가 정책 팁을 통해 정책을 제거 했는지 여부                | 모든 이벤트                               |
    |                   | 양쪽 맞춤 텍스트 재정의   | 정책 팁을 재정의 하기 위해 제공 된 사유                          | 모든 이벤트                               |
    
1.  중요 한 정보 **유형** 탭을 선택 하 여 콘텐츠에서 검색 된 중요 한 정보 유형에 대 한 세부 정보를 볼 수 있습니다. 세부 정보에 신뢰도 및 개수가 포함 됩니다.

2.  알림을 조사한 후에는 **알림 관리** 를 선택 하 여 상태 (**활성**, **조사** **, 해제**또는 **확인 됨**)를 변경 합니다. 또한 의견을 추가 하 고 조직의 다른 사람에 게 경고를 할당할 수 있습니다.

    -   워크플로 관리 기록을 보려면 **관리 로그**를 선택 합니다.
    -   경고에 대 한 필수 작업을 수행한 후에는 경고의 상태를 **해결 됨으로**설정 합니다.

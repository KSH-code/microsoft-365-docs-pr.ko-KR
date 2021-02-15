---
title: DLP 정책에 대한 경고 구성 및 보기(미리 보기)
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
description: DLP 정책에 대한 경고를 정의하고 관리하는 방법을 학습합니다.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651476"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>DLP 경찰에 대한 경고 구성 및 보기(미리 보기)

이 문서에서는 DLP(데이터 손실 방지) 정책에 연결된 다양한 경고 정책을 정의하는 방법을 보여줍니다. [Microsoft 365](https://compliance.microsoft.com/) 규정 준수 센터에서 새 DLP 경고 관리 대시보드를 사용하여 DLP 정책 위반에 대한 경고, 이벤트 및 관련 메타데이터를 보는 방법을 볼 수 있습니다.

## <a name="features"></a>기능

다음 기능은 이 미리 보기의 일부입니다.

-   **DLP 경고 관리** 대시보드: [Microsoft 365](https://compliance.microsoft.com/)규정 준수 센터에서 이 대시보드에는 다음 워크로드에 적용된 DLP 정책에 대한 경고가 표시됩니다.

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   디바이스
-   **고급 경고 구성 옵션:** 이러한 옵션은 DLP 정책 제작 흐름의 일부입니다. 이러한 구성을 사용하여 다양한 경고 구성을 만들 수 있습니다. 이벤트 수 또는 누출된 데이터의 크기에 따라 단일 이벤트 경고 또는 집계된 경고를 만들 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

시작하기 전에 다음 필수 필수가 있는지 확인하세요.

-   DLP 경고 관리 대시보드 라이선스
-   경고 구성 옵션에 대한 라이선싱
-   역할

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드 라이선스

Office 365 DLP에 적합한 모든 테넌트는 새 DLP 경고 관리 대시보드에 액세스할 수 있습니다. 시작을 위해 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에 대한 Office 365 DLP를 사용할 수 있습니다. Office 365 DLP의 라이선스 요구 사항에 대한 자세한 내용은 사용자에게 서비스 혜택을 받을 수 있는 권한을 제공하는 라이선스를 [참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

[끝점 DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) 공개 미리 보기에 참여하거나 Teams [DLP를](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) 사용할 자격이 있는 고객은 DLP 경고 관리 대시보드에서 끝점 DLP 정책 경고 및 Teams DLP 정책 경고를 볼 수 있습니다.

### <a name="licensing-for-alert-configuration-options"></a>경고 구성 옵션에 대한 라이선싱

-   **단일** 이벤트 경고 구성: E1, F1 또는 G1 구독 또는 E3 또는 G3 구독이 있는 조직은 활동이 발생할 때마다 경고가 트리거되는 경고 정책만 만들 수 있습니다.
-   **집계된 경고 구성:** 임계값에 따라 집계 경고 정책을 구성하려면 다음 구성 중 하나를 설정해야 합니다.
    -   E5 또는 G5 구독
    -   다음 기능 중 하나를 포함하는 E1, F1 또는 G1 구독 또는 E3 또는 G3 구독
        -   Office 365 Advanced Threat Protection Plan 2
        -   Microsoft 365 E5 Compliance
        -   Microsoft 365 eDiscovery 및 추가 기능 감사 라이선스

### <a name="roles"></a>역할

DLP 경고 관리 대시보드를 보거나 DLP 정책에서 경고 구성 옵션을 편집하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.

-   준수 관리자
-   준수 데이터 관리자
-   보안 관리자
-   보안 운영자
-   보안 읽기 권한자

DLP 경고 관리 대시보드에 액세스하려면 경고 관리 역할과 다음 역할 중 하나가 필요합니다.

-   DLP 규정 준수 관리
-   View-Only DLP 규정 준수 관리

## <a name="alert-configuration-experience"></a>경고 구성 환경

집계된 경고 구성 [](#licensing-for-alert-configuration-options)옵션을 사용할 수 있는 경우 DLP 정책 작성 환경의 다음 옵션이 인라인으로 표시됩니다.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="집계된 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

이러한 경고 구성 옵션을 사용하여 경고가 트리거되기 전에 DLP 규칙 일치가 발생할 수 있는 자주를 정의하는 설정을 구성할 수 있습니다. 이 구성을 사용하면 활동이 정책 조건과 일치할 때마다 또는 활동 수 또는 유출된 데이터 볼륨에 따라 특정 임계값을 초과할 때마다 경고를 생성하도록 정책을 설정할 수 있습니다.

단일 이벤트 경고 구성 [](#licensing-for-alert-configuration-options)옵션을 사용할 수 있는 경우 DLP 정책 작성 환경의 다음 경고 구성 옵션이 표시됩니다. 이 옵션을 사용하여 사용자 활동으로 인하여 DLP 규칙 일치가 발생할 때마다 발생하는 경고를 만들 수 있습니다.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드

DLP 경고 관리 대시보드에서 작업하는 경우:

1.  Microsoft [365 규정 준수](https://www.compliance.microsoft.com)센터에서 데이터 손실 **방지로 이동하십시오.**

2.  경고 **탭을 선택하여** DLP 경고 대시보드를 볼 수 있습니다.

    -   경고 목록을 구체화할 필터를 선택합니다. 열 **사용자 지정을 선택하면** 표시하려는 속성이 나열됩니다. 모든 열에서 경고를 오차 또는 내선 순서로 정렬할 수도 있습니다.
    -   경고를 선택하여 세부 정보를 볼 수 있습니다.

        :::image type="content" source="../media/alert-details.png" alt-text="Screenshot showing alert details on the DLP alert management dashboard." border="false":::

1.  이벤트 **탭을 선택하여** 경고와 연결된 모든 이벤트를 볼 수 있습니다. 특정 이벤트를 선택하면 해당 세부 정보를 볼 수 있습니다.
    다음 표에는 일부 이벤트 세부 정보가 표시됩니다.
    
    | 범주          | 속성 이름                 | 설명                                                                | 적용 가능한 이벤트 유형                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*이벤트 세부 정보*||
    |      | Id                            | 이벤트와 연결된 고유 ID                                        | 모든 이벤트                               |
    |                   | 위치                      | 이벤트가 검색된 작업량                                      | 모든 이벤트                               |
    |                   | 활동 시간              | DLP 위반을 일으운 사용자 작업 시간                    | 모든 이벤트                               |
    |*영향을 미치는 엔터티*||
    |  | 사용자                          | DLP 위반을 유발한 사용자                                          | 모든 이벤트                               |
    |                   | Hostname(호스트 이름)                      | DLP 위반이 감지된 컴퓨터의 호스트 이름              | 장치 이벤트                           |
    |                   | IP 주소                    | 컴퓨터의 IP 주소                                                  | 장치 이벤트                           |
    |                   | 파일 경로                     | 위반과 관련된 파일의 절대 경로                        | SharePoint, OneDrive 및 장치 이벤트 |
    |                   | 전자 메일 받는 사람              | DLP 정책을 위반한 전자 메일의 받는 사람                       | Exchange 이벤트                          |
    |                   | 전자 메일 제목                 | DLP 정책을 위반한 전자 메일의 제목                          | Exchange 이벤트                          |
    |                   | 전자 메일 첨부 파일             | DLP 정책을 위반한 전자 메일의 첨부 파일 이름         | Exchange 이벤트                          |
    |                   | 사이트 소유자                    | 사이트 소유자의 이름                                                     | SharePoint 및 OneDrive 이벤트           |
    |                   | 사이트 URL                      | SharePoint 또는 OneDrive 사이트의 전체 URL                                | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일을 만들었음                  | 파일 만들기 시간                                                      | SharePoint 및 OneDrive 이벤트           |
    |                   | 마지막으로 수정한 파일            | 파일을 마지막으로 수정한 시간입니다.                                  | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일 크기                     | 파일 크기                                                           | SharePoint 및 OneDrive 이벤트           |
    |                   | 파일 소유자                    | 파일의 소유자                                                          | SharePoint 및 OneDrive 이벤트           |
    |*정책 세부 정보*||
    |     | 일치하는 DLP 정책            | 일치하는 DLP 정책의 이름                                    | 모든 이벤트                               |
    |                   | 일치하는 규칙                  | 일치하는 DLP 정책의 DLP 규칙 이름                    | 모든 이벤트                               |
    |                   | 검색된 중요한 정보 유형 | DLP 정책의 일부로 검색된 중요한 정보 유형 | 모든 이벤트                               |
    |                   | 수행한 작업                 | 일치하는 DLP 정책의 일부로 수행된 작업                          | 모든 이벤트                               |
    |                   | 사용자 오버로드 정책          | 사용자가 정책 팁을 통해 정책을 오버로이드하는지 여부                | 모든 이벤트                               |
    |                   | 정당성 텍스트에 대한 의문을 드리우기   | 정책 팁을 오버라이드하기 위해 제공된 사당성                          | 모든 이벤트                               |
    
1.  중요한 정보 **유형 탭을 선택하여** 콘텐츠에서 검색된 중요한 정보 유형에 대한 세부 정보를 볼 수 있습니다. 세부 정보에는 신뢰도와 개수가 포함됩니다.

2.  경고를 조사한 후  경고 **관리(활성,** 조사 **중,** 해지 또는 해결)를 **변경합니다.** 조직의 다른 사용자에게 설명을 추가하고 알림을 할당할 수도 있습니다.

    -   워크플로 관리 기록을 확인하려면 관리 **로그를 선택하십시오.**
    -   경고에 대해 필요한 작업을 수행한 후 경고 상태를 해결된 것으로 **설정하십시오.**

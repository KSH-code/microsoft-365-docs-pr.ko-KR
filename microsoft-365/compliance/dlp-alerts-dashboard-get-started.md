---
title: 데이터 손실 방지 경고 대시보드 시작
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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 데이터 손실 방지 정책에 대한 경고 정의 및 관리부터 시작하십시오.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193129"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>데이터 손실 방지 경고 대시보드 시작

DLP(데이터 손실 방지) 정책은 중요한 항목의 의도하지 않은 공유를 방지하기 위해 보호 조치를 취할 수 있습니다. 중요한 항목에 대해 작업을 수행하면 DLP에 대한 알림을 구성하여 알림을 알 수 있습니다. 이 문서에서는 DLP(데이터 손실 방지) 정책에 연결된 다양한 경고 정책을 정의하는 방법을 보여줍니다. DLP 정책 위반에 대한 [경고,](https://compliance.microsoft.com/) 이벤트 및 관련 메타데이터를 보기 위해 Microsoft 365 규정 준수 센터 [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) 경고 관리 대시보드를 사용하는 방법을 볼 수 있습니다.

DLP 경고를 새로 사용하는 경우 데이터 손실 방지 경고에 대한 자세한 정보 대시보드를 [검토해야 합니다.](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>시작하기 전에

시작하기 전에 다음 필수 필수가 있는지 확인하세요.

-   DLP 경고 관리 대시보드에 대한 라이선스
-   경고 구성 옵션에 대한 라이선싱
-   역할

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 경고 관리 대시보드에 대한 라이선스

DLP의 모든 적합한 Office 365 DLP 경고 관리 대시보드에 액세스할 수 있습니다. 시작을 위해 Office 365, SharePoint Online 및 Exchange Online DLP를 비즈니스용 OneDrive. Office 365 DLP의 라이선스 요구 사항에 대한 자세한 내용은 사용자에게 서비스를 혜택을 제공할 수 있는 권한을 제공하는 라이선스를 [참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

Teams DLP를 사용할 수 있는 끝점 [DLP를](endpoint-dlp-learn-about.md) 사용하는 고객에게는 끝점 DLP 정책 경고 및 [DLP](dlp-microsoft-teams.md) Teams 관리 대시보드에서 DLP 정책 경고가 표시됩니다.

콘텐츠 **미리 보기 기능은** 다음 라이선스에서만 사용할 수 있습니다.

- Microsoft 365 (E5)
- Office 365 (E5)
- E5(고급 규정 준수) 추가 기능
- Microsoft 365 E5/A5 정보 보호 및 거버넌스
- 마이크로소프트 365 E5/A5 규정 준수

### <a name="licensing-for-alert-configuration-options"></a>경고 구성 옵션에 대한 라이선싱

**단일 이벤트** 경고 구성: E1, F1 또는 G1 구독이 있는 조직이나 E3 또는 G3 구독이 있는 조직은 활동이 발생할 때마다 경고가 트리거되는 경우만 경고 정책을 만들 수 있습니다.

**집계된 경고 구성:** 임계값을 기반으로 집계 경고 정책을 구성하려면 다음 라이선스 구성 중 하나를 구성해야 합니다.

- E5 또는 G5 구독
- E1, F1 또는 G1 구독 또는 다음 기능 중 하나를 포함하는 E3 또는 G3 구독
    - Office 365 Advanced Threat Protection Plan 2
    - Microsoft 365 E5 Compliance
    - Microsoft 365 및 추가 기능 라이선스 감사

### <a name="roles"></a>역할


DLP 경고 관리 대시보드를 보거나 DLP 정책에서 경고 구성 옵션을 편집하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.

- 규정 준수 관리자
- 규정 준수 데이터 관리자
- 보안 관리자
- 보안 운영자
- 보안 읽기 권한자

DLP 경고 관리 대시보드에 액세스하려면 다음이 필요합니다.

- 경고 관리

및 다음 두 역할 중 하나:

- DLP 규정 준수 관리
- View-Only DLP 준수 관리

콘텐츠 미리 보기 기능 및 일치하는 중요한 콘텐츠 및 컨텍스트 기능에 액세스하려면 다음의 구성원이 되어야 합니다.

- 콘텐츠 탐색기 콘텐츠 뷰어 역할 그룹

데이터 분류 콘텐츠 뷰어 역할이 미리 할당되어 있습니다.

## <a name="dlp-alert-configuration"></a>DLP 경고 구성

DLP 정책에서 경고를 구성하는 방법에 대한 자세한 내용은 데이터 손실 방지로 시작하는 [위치를 참조합니다.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)

### <a name="aggregate-event-alert-configuration"></a>집계 이벤트 경고 구성

집계된 경고 구성 옵션에 대한 사용이 허가된 경우 DLP 정책을 만들거나 편집할 때 이러한 옵션이 표시됩니다. [](#licensing-for-alert-configuration-options)

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="집계된 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

이 구성을 사용하면 활동이 정책 조건과 일치하거나 활동 수 또는 유출된 데이터의 볼륨에 따라 특정 임계값을 초과할 때마다 경고를 생성하도록 정책을 설정할 수 있습니다.

### <a name="single-event-alert-configuration"></a>단일 이벤트 경고 구성

단일 이벤트 경고 구성 [](#licensing-for-alert-configuration-options)옵션에 대한 사용이 허가된 경우 DLP 정책을 만들거나 편집할 때 이러한 옵션이 표시됩니다. DLP 규칙 일치가 발생할 때마다 발생하는 경고를 만들 때 이 옵션을 사용합니다.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="단일 이벤트 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

## <a name="investigate-a-dlp-alert"></a>DLP 경고 조사

DLP 경고 관리 대시보드에서 작업하는 경우:

1. 에서 [Microsoft 365 규정 준수 센터](https://www.compliance.microsoft.com)데이터 손실 **방지로 이동하십시오.**
2. 경고 **탭을 선택하여** DLP 경고 대시보드를 볼 수 있습니다.
3. 경고를 선택하여 세부 정보를 봐야 합니다.

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot showing alert details on the DLP alert management dashboard." border="false":::

4. 경고와  연결된 모든 이벤트를 표시하려면 이벤트 탭을 선택합니다. 특정 이벤트를 선택하면 세부 정보를 볼 수 있습니다. 사용 가능한 이벤트 세부 정보의 목록은 데이터 손실 방지 경고 대시보드에 대한 자세한 [정보를 참조하세요.](dlp-alerts-dashboard-learn.md)
5. 세부 **정보를 선택하여** 경고에 대한 **개요** 페이지를 열 수 있습니다. 개요 페이지에서는 다음과 같은 요약 정보를 제공합니다.
    1. 발생된 일
    1. 정책 일치를 유발한 작업을 수행한 사람
    1. 일치하는 정책에 대한 정보 등 

6. 이벤트 **탭을 선택하고** 다음에 액세스합니다.
    1. 관련된 콘텐츠
    1. 일치하는 중요한 정보 유형
    1. 메타데이터

7. 중요한 정보 **유형 탭을 선택하여** 콘텐츠에서 검색된 중요한 정보 유형에 대한 세부 정보를 볼 수 있습니다. 세부 정보에는 신뢰도, 개수 및 중요한 정보 유형과 일치하는 콘텐츠가 포함됩니다.

8. 경고를 조사한 후 개요  탭으로 돌아와서 경고의 경과를 관리하고 설명을 추가할 수 있습니다.

- 워크플로 관리 기록을 확인하려면 관리 로그 **를 선택하세요.**
- 경고에 대해 필요한 작업을 수행한 후 경고 상태를 해결된 으로 **설정하십시오.**

## <a name="see-also"></a>참고 항목

- [데이터 손실 방지 경고 및 경고 대시보드에 대한 자세한 정보](dlp-alerts-dashboard-learn.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
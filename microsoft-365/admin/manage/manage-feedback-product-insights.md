---
title: 조직에 대한 Microsoft 제품 NPS 피드백 및 인사이트
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 최종 사용자의 NPS(Net Promoter Score)를 사용하여 Microsoft 제품 및 서비스에 대한 느낌을 볼 수 있습니다.
ms.openlocfilehash: afde0abf85cca682a5cda3206fa78d24cafc8cb8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168125"
---
# <a name="microsoft-product-nps-feedback-and-insights-for-your-organization"></a>조직에 대한 Microsoft 제품 NPS 피드백 및 인사이트

조직의 관리자는 Microsoft 365 사용자가 생성한 인사이트 및 데이터를 볼 수 있습니다.

NPS(Net Promoter Score) 설문 조사는 사용자 피드백을 수집하고 사용자가 친구 및 동료에게 제품 및 서비스를 추천할 가능성이 얼마나 높은지 측정합니다. 이 데이터는 조직 수준에서 채택 및 출시 전략을 결정하는 데 사용할 수 있습니다.

Microsoft는 최종 사용자의 NPS 설문 조사 및 피드백을 사용하여 Microsoft 제품 및 서비스에 대한 인사이트를 제공합니다. 이 정보는 조직의 최종 사용자가 사용하는 제품 및 서비스를 파악하는 데 도움이 될 뿐만 아니라 문제를 식별하고 신속하게 해결하는 데 도움이 될 수 있습니다. 이 정보를 사용하여 다음을 할 수 있습니다.

<!--See location of users who have submitted feedback-->
- 사용 중일 운영 체제 또는 플랫폼 보기
- 키워드를 사용하여 제품, 플랫폼 및 검색 필터링
- 상위 제품 및 문제에 대한 최종 사용자 의견 참조
- 추가 조사를 위해 피드백 및 설문 조사 정보를 CSV 파일로 내보내기

## <a name="before-you-begin"></a>시작하기 전에

설문 조사 보고서를 보고 [읽으기](../add-users/about-admin-roles.md) 위해 관리자인 것이 필요합니다. 조직에서 설문 조사 보고서를 보고 읽으기 위해 피드백 설문 조사를 설정해야 합니다. 자세한 내용은 [조직에 대한 Microsoft 피드백 관리를](manage-feedback-ms-org.md) 확인 합니다.

## <a name="survey-insights"></a>설문 조사 정보

1. 관리 센터에서 건강 제품 피드백 NPS 설문 조사  >    >  **정보 로 이동하세요.**
2. NPS 설문 조사 **인사이트 페이지에서** 페이지를 탐색하여 조직의 NPS와 관련된 설문 조사 정보를 봐야 합니다.

:::image type="content" source="../../media/prosight-product-feedback.png" alt-text="Screenshot: Microsoft 365 Nps survey insights":::

### <a name="chart-information"></a>차트 정보

**총 피드백은** 최종 사용자가 제출한 총 NPS 피드백 응답 수를 보여 주며 주석과 주석 없이 NPS 피드백을 포함합니다.

**설명은** 최종 사용자가 제출한 총 NPS 피드백 응답 수(주석 포함)를 보여줍니다.

**응용 프로그램당 볼륨은** 응용 프로그램당 총 NPS 피드백 응답 볼륨을 보여줍니다.

**월별** 피드백 볼륨은 월별 총 NPS 피드백 응답 볼륨을 보여줍니다.

:::image type="content" source="../../media/prosight-charts-area.png" alt-text="Screenshot: Microsoft 365 survey insights":::

### <a name="top-topic-filters"></a>상위 항목 필터

항목은 NPS 설문 조사 피드백의 설명, 구 및 구문을 분석하여 최상위 수준에서 가장 일반적인 테마에 대한 액세스를 제공하는 기계 학습 모델입니다. 상위 항목 필터에는 가장 많은 수의 대면 피드백이 있는 상위 5개 항목을 표시합니다.

:::image type="content" source="../../media/prosight-top-topic-filters-2.png" alt-text="Screenshot: Top topic filters on NPS survey data":::

> [!NOTE]
> 주제 전문가와 협력하고 최소 품질 표시줄을 충족한 후에만 지능형 항목을 게시합니다. 정밀도 및 회수 메트릭은 동일을 결정하는 데 사용됩니다.

**Verbatim precision** is how likely that a verbatim classified in this topic is correct.

**Verbatim Recall** is how likely that a verbatim related to this topic is classified in this topic.

현재 사용 가능한 항목은 다음과 같습니다.

**탐색에는** 앱 탐색 및 사용 가능성에 대한 고객 의견이 포함됩니다.

- Verbatim Precision - 93%
- Verbatim Recall- 98%

**공동** 작업이란 사용자가 Microsoft 앱을 사용하여 공동 작업할 수 있는 방법을 지어보는 것입니다.

- Verbatim Precision - 92%
- Verbatim Recall-91%

**값은** 가격 책정 및 결제 기본 설정을 포함한 항목에 대한 고객 인식을 지니는 것입니다.

- Verbatim Precision - 86%
- Verbatim Recall- 100%

**안정성에는** 예기치 않은 종료를 초래하는 앱 및 시스템 동작에 대한 고객 의견이 포함됩니다.

- Verbatim Precision - 97%
- Verbatim Recall- 94%

**성능은** Microsoft 제품을 사용하는 동안 사용자가 경험하는 작업 속도 인식 속도와 관련된 문제를 해결하는 고객 의견을 참조합니다. 이 항목에서는 크래시 또는 더 광범위한 안정성 문제 영역에 대해 다루지 않습니다.

- Verbatim Precision - 92%
- Verbatim Recall- 98%

**User Education** 피드백에는 도움말 설명서, 자습서, 가이드 및 기타 제품 내 또는 온라인 학습 콘텐츠에 대한 고객 의견이 포함되어 있습니다.

- Verbatim Precision - 83%
- Verbatim Recall- 87%

**복잡성은** 앱이 복잡하거나 사용하기 좋게 느껴지는지 여부에 대한 고객 피드백을 참조합니다.

- Verbatim Precision - 92%
- Verbatim Recall- 89%

**일반 칭찬하기** 의견은 긍정적인 정서가 있으며 다른 항목과는 맞지 않는 고객 의견을 참조합니다.

- Verbatim Precision - 93%
- Verbatim Recall- 98%

### <a name="export-to-csv-and-search"></a>CSV 및 검색으로 내보내기

CSV로 내보내기 기능을 사용하여 추가 분석을 위해 원시 데이터를 내보낼 수 있습니다.

> [!NOTE]
> 원시 데이터에는 NPS가 아닌 피드백을 포함하여 모든 유형의 피드백이 포함됩니다.

### <a name="filters"></a>필터

채널, **제품,** 플랫폼 및 **피드백 유형으로 필터링할 수 있습니다.** 

**조직은** 채널을 통해 조직의 채널에 대한 기능 업데이트를 받을 Office. 자세한 내용은 [Overview of update channels for Microsoft 365 앱.](/deployoffice/overview-update-channels) 이 필터를 사용하면 특정 채널의 사용자가 제출한 피드백으로 필터링할 수 있습니다.

피드백은 Android,  iOS, Mac 및 앱과 같은 다양한 플랫폼에서 제출할 Windows. 이 필터를 사용하면 제출된 플랫폼에 따라 피드백을 필터링할 수 있습니다.

비즈니스용 Microsoft 365 대부분의 제품은  이 필터에서 찾을 수 있습니다. 이 필터를 사용하여 피드백이 제출된 제품을 선택합니다.

피드백 **유형(NPS** 피드백 유형으로만 설정)을 사용하여 수집하는 피드백을 필터링합니다.

:::image type="content" source="../../media/prosight-filters.png" alt-text="Screenshot: Microsoft 365 NPS survey insights filters":::

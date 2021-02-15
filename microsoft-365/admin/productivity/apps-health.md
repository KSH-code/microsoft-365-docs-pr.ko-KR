---
title: Microsoft 생산성 점수 - Microsoft 365 앱 상태
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Microsoft 365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Microsoft 365 앱 상태의 세부 정보 - 기술 환경 생산성 점수.
ms.openlocfilehash: a84e919ce01775b8791ed7a1992464e4f52c7234
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562946"
---
# <a name="microsoft-365-apps-health--technology-experiences"></a>Microsoft 365 Apps 상태 - 기술 경험

생산성 점수는 Microsoft 365를 활용하고 이를 지원하는 기술 환경을 통해 조직의 디지털 변환 여정에 대한 인사이트를 제공합니다. 조직의 점수는 사용자 및 기술 환경 측정값을 반영하며 사용자와 유사한 조직의 벤치마크와 비교할 수 있습니다. 앱 상태 범주는 기술 경험에 속하는 측정의 일부입니다. 자세한 내용은 생산성 점수 [](productivity-score.md) 개요를 확인하고 Microsoft의 개인 정보 [취급 방침을 읽어보십시오.](https://privacy.microsoft.com/privacystatement)

## <a name="why-your-organization39s-microsoft-365-apps-health-score-matters"></a>조직에서 Microsoft&#39;상태 점수가 중요한 이유

조직의 생산성은 정상 상태의 응용 프로그램 환경에 따라 달라집니다. 권장 채널에서 최신 버전의 Microsoft 365 앱을 실행하는 장치는 더 안전하며 조직의 사람들이 Microsoft 365의 기능을 가장 잘 사용할 수 있도록 합니다.

## <a name="how-we-calculate-the-microsoft-365-apps-health-score"></a>Microsoft 365 앱 상태 점수를 계산하는 방법

각 업데이트 채널의 장치 수를 측정하여 Microsoft 365 앱 상태 점수를 계산합니다. 또한 디바이스가 지원되는 버전과 Microsoft 365 앱의 최신 릴리스를 실행 중인지 여부도 파악합니다.

이 범주에 대한 주요 메트릭을 포함하는 환경의 기본 정보를 제공합니다. 그런 다음 다음 섹션에 자세히 설명된 점수 프레임워크를 사용하여 점수를 계산합니다.

### <a name="primary-insight"></a>기본 인사이트

기본 인사이트는 권장 업데이트된 채널에서 Microsoft 365 앱을 실행하는 장치에서 계산됩니다.

:::image type="content" source="../../media/appshealth-primary.png" alt-text="Microsoft 365 앱에 대한 주요 시야 시각화입니다.":::

여기에는 디바이스에서 실행되는 Microsoft 365 앱 채널, 빌드 및 버전이 포함됩니다.

1. **헤더:**  권장 업데이트 채널의 장치 백분율 표시
1. **본문:**  권장 업데이트 채널에서 디바이스를 실행하면 장치에서 최신 업데이트를 받고 현재 버전을 실행하는 데 도움이 되는 방법에 대한 자세한 정보를 제공합니다.
1. **시각화(현재 상태):**
    - 파란색 부분이 권장 업데이트된 채널을 실행하는 장치의 백분율을 나타내는 가로 막대입니다.
    - 가로 막대로 표시된 백분율을 계산하는 데 사용되는 분수의 숫자/분모를 강조합니다.
    - 권장 업데이트된 채널에서 실행되는 디바이스에 대한 피어 벤치마크 값도 백분율로 표시됩니다.

#### <a name="trend-visualization-of-the-primary-insight"></a>기본 정보의 추세 시각화

다음 차트는 지난 180일 동안의 권장 업데이트 채널의 장치 수를 보여 주며, 라인 차트의 데이터 포인트는 지난 28일 동안의 활동 집계입니다.

:::image type="content" source="../../media/appshealth-primarytrend.png" alt-text="권장 업데이트 채널을 실행하는 장치의 추세를 보여주는 차트입니다.":::

### <a name="scoring-framework"></a>점수 매기기 프레임워크

Microsoft 365 앱 상태 점수는 장치가 권장 채널 및 최신 버전에서 Microsoft 365 앱을 실행 중인지 여부를 측정합니다.

## <a name="explore-your-organization-microsoft-365-app-channels-and-versions"></a>조직 Microsoft 365 앱 채널 및 버전 살펴보기

또한 조직의 어떤 채널 및 버전 장치가 현재 실행되고 있는지 추가로 쉽게 알 수 있도록 지원 정보를 제공합니다. 이러한 추가 메트릭은 생산성 점수에 기여하지 않지만 장치가 권장 채널에서 Microsoft 365 앱을 실행하게 하여 Microsoft 365 앱 상태 점수를 높이는 작업 계획을 세우는 데 도움이 될 수 있습니다.

### <a name="devices-on-current-channel-and-running-supported-versions"></a>현재 채널의 장치 및 지원되는 버전 실행

:::image type="content" source="../../media/devices-current-suppported-channel.png" alt-text="지원되는 현재 채널의 장치 수를 보여 주는 차트입니다.":::

1. **헤더:**  현재 채널에서 지원되는 버전의 Microsoft 365 앱을 실행하는 장치의 백분율을 강조합니다.
1. **본문:**  권장 채널에서 Microsoft 365 앱을 실행하는 장치의 값에 대한 정보를 제공합니다.
1. **시각화:**  시각화의 분석은 다음과 같이 다양한 채널에서 지원되는 최신 버전의 Microsoft 365 앱에 있는 장치의 백분율 정도를 나타냅니다.
    - **지원되는 버전:** 파란색 막대는 지원되는 버전의 Microsoft 365 앱에서 실행되는 장치의 백분율을 나타내며,
    - **최신 릴리스:** 녹회색 막대는 최신 릴리스의 장치의 백분율을 나타내는 색 막대입니다.
1. **자세한 내용은 다음을 통해 자세히 알아보시고,**   도움말 콘텐츠를 확인하려면 이 링크를 선택합니다.

### <a name="devices-running-latest-and-supported-versions"></a>지원되는 최신 버전을 실행하는 장치

:::image type="content" source="../../media/device-supported-versions.png" alt-text="지원되는 최신 버전의 앱을 실행하는 장치 수를 보여 주는 차트입니다.":::

1. **헤더:**  지원되는 버전을 실행하는 장치와 최신 버전을 실행하는 장치의 백분율을 강조합니다.
1. **본문:**  권장 채널 및 지원되는/최신 버전에서 디바이스를 실행하는 값에 대한 정보를 제공합니다.
1. **시각화:** 시각화의 분석은 지원되는 버전 및 최신 버전의 Microsoft 365 앱을 실행하는 장치의 수를 보여 주기 위한 것입니다.
    - **지원되는 버전:** 막대의 파랑(색) 부분과 막대의 분수(숫자/분모)는 지원되는 버전의 Microsoft 365 앱을 실행하는 장치의 백분율을 나타내는 것입니다.
        - 숫자: 지난 28일 동안 지원되는 버전의 Microsoft 365 앱에 있는 장치 수
        - 디노이터: 지난 28일 이내에 Microsoft 365 앱을 사용하는 장치 수
    - **가장 최근 버전:** 막대의 녹차(색) 부분과 막대의 분수(숫자/분모)는 최신 버전의 Microsoft 365 앱을 실행하는 장치의 백분율을 나타내는 것입니다.
        - 숫자: 지난 28일 이내에 최근 버전의 Microsoft 365 앱에 있는 장치 수
        - 디노이터: 지난 28일 이내에 Microsoft 365 앱을 사용하는 장치 수
1. **자세한 내용은 다음을 통해 자세히 알아보시고,**   도움말 콘텐츠를 확인하려면 이 링크를 선택합니다.

#### <a name="trend-visualization-of-the-devices"></a>장치의 추세 시각화

이 차트는 지난 180일 동안 지원되는 버전 및 최신 버전의 Microsoft 365 앱을 실행하는 장치의 추세선입니다.

:::image type="content" source="../../media/trendline-devices-supportedversions.png" alt-text="지원되는 앱 및 최신 버전의 앱을 실행한 디바이스 수를 보여 준 차트입니다.":::

## <a name="devices-in-your-organization"></a>조직의 장치

이 섹션에서는 Microsoft 365 앱 상태 - 기술 환경의 모든 메트릭에 관련 정보를 제공하여 집중하려는 메트릭에 대해 행동할 수 있습니다.

다음 열은 채널/버전 수준의 표에 표시됩니다.

- **채널** : 디바이스의 현재 Microsoft 365 앱 채널입니다.
- **상태:**   Microsoft 365 앱은 현재 채널 및 버전에 따라 장치의 상태를 지원합니다.
- **버전:**   디바이스의 현재 Microsoft 365 앱 버전입니다.
- **장치 #**  장치 수입니다.

## <a name="related-content"></a>관련 콘텐츠

[커뮤니케이션 - 사람](communication.md) 환경(문서)\
[콘텐츠 공동 작업 - 사람](content-collaboration.md) 환경(문서)\
[모임 - 사람](meetings.md) 환경(문서)\
[이동성 - 사람](mobility.md) 환경(문서)\
[생산성 점수에 대한](privacy.md) 개인 정보 보호 컨트롤(문서)\
[팀워크 - 사람](teamwork.md) 환경(문서)
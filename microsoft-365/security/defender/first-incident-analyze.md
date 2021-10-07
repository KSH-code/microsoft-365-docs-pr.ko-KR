---
title: 1단계. 첫 번째 인시던트의 세분화 및 분석
description: 2013에서 첫 번째 인시던트의 분석을 세분화하고 시작하는 Microsoft 365 Defender.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365, 인시던트 대응, 사이버 공격
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d539f34f72b5fe6c26325646452a15b5df76a5a7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199552"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>1단계. 첫 번째 인시던트의 세분화 및 분석

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

조직의 표준에 따라 보안 조치를 설정, 구현 및 유지 관리하는 데 시간을 소비할 때 보안 솔루션을 설정하여 보안 위험과 위협을 빠르게 식별할 수 있습니다. Microsoft 365 Defender 사용하여 적시에 결정을 내리는 데 필요한 정보를 찾을 수 있는 단일 창 환경을 통해 인시던트 감지, 판정 및 조사를 할 수 있습니다.

보안 인시던트가 감지되면 Microsoft 365 Defender 다른 인시던트보다 인시던트나 인시던트의 우선 순위를 지정하거나 우선 순위를 지정하는 데 필요한 세부 정보를 제공합니다. 우선 순위를 결정한 후 분석가가 할당된 사례를 조사하는 데 집중할 수 있습니다.

## <a name="detection-by-microsoft-365-defender"></a>검색된 Microsoft 365 Defender

Microsoft 365 Defender Microsoft 보안 플랫폼에서 경고 및 이벤트를 검색 원본으로 수신하여 악의적인 활동의 전체적인 그림과 컨텍스트를 만들 수 있습니다. 다음은 가능한 검색 원본입니다.

- [끝점용 Microsoft Defender는](../defender-endpoint/microsoft-defender-endpoint.md) Microsoft Defender 바이러스 백신과 Microsoft 보안 기능을 사용하는 클라우드 사용 고급 위협 방지를 사용하는 끝점 감지 및 응답 솔루션(EDR)Graph. Endpoint용 Defender는 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. 사이버 위협으로부터 끝점을 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하며, 보안 자세를 개선합니다.
- [Id용 Microsoft Defender는](/defender-for-identity/what-is) 클라우드 기반 보안 솔루션으로, 조직에 대한 고급 위협, ID 손상 및 악의적인 내부자 작업을 식별, 감지 및 조사하기 위해 AD DS(Active Directory 도메인 서비스) 신호를 사용하는 클라우드 기반 보안 솔루션입니다.
- [Microsoft Cloud App Security](/cloud-app-security/) 위치와 사용 디바이스에 관계없이 엔터프라이즈 사용자와 사용하는 클라우드 리소스 간의 액세스를 실시간으로 브로커하는 게이트키퍼 역할을 합니다.
- [Microsoft Defender for Office 365](../office-365-security/overview.md) 전자 메일 메시지, 링크(URL) 및 공동 작업 도구의 악의적인 위협에 대해 조직을 보호합니다.
- [Azure Security Center는](/azure/security-center/security-center-introduction) 데이터 센터의 보안 환경이 강화되고 클라우드와 사내의 하이브리드 워크로드에서 고급 위협 보호를 제공하는 통합 인프라 보안 관리 시스템입니다.

이 Microsoft 365 Defender [인시던트는](incidents-overview.md) 이러한 다양한 검색 원본의 경고를 상호 연결하여 식별됩니다. 리소스를 함께 문자열화하거나 여러 개의 경고를 해당 인시던트로 구분하는 대신 인시던트 큐를 바로 Microsoft 365 Defender 있습니다. 이를 통해 끝점, ID, 전자 메일 및 응용 프로그램 전반에서 인시던트의 효율적인 방식으로 인시던트의 선을 들이고 공격으로 인한 손상을 줄일 수 있습니다.

## <a name="triage-your-incidents"></a>인시던트 세분화

조직의 Microsoft 365 Defender 우선 순위 지정 방법을 사용하여 인시던트 목록을 조사하면 인시던트 대응이 시작됩니다. 인시던트에 중요도나 긴급성을 할당하는 것은 인시던트가 조사되는 순서를 결정하는 것입니다.

심각도 + 영향 = 우선 순위 Microsoft 365 Defender 수식으로 요약할 수 있는 인시던트의 우선 순위를 결정하는 유용한 샘플 *가이드입니다.*

- **심각도는** 보안 구성 요소와 Microsoft 365 Defender 지정된 수준입니다.
- **영향은** 조직에 의해 결정하며 일반적으로 영향을 받는 사용자, 장치, 영향을 받는 서비스(또는 이러한 조합) 및 경고 유형에 대한 임계값 수를 포함하지만 이에 국한되지는 않습니다.

그런 다음 분석가가 조직에서 설정한 **우선** 순위 기준에 따라 조사를 시작합니다.

인시던트 우선 순위는 조직에 따라 다를 수 있습니다. 또한 인시던트의 기능 및 정보 영향 및 복구 가능성도 고려하는 것이 좋습니다.

다음은 한 가지 접근 방식에 불과합니다.

1. [인시던트 페이지로](incidents-overview.md) 이동하여 재판을 시작하세요. 조직에 영향을 주는 인시던트 목록을 볼 수 있습니다. 기본적으로 가장 최근 인시던트부터 가장 오래된 인시던트까지 정렬됩니다. 여기에서 각 인시던트의 심각도, 범주, 활성 경고 수 및 영향을 미치는 엔터티를 보여 미치는 각 인시던트에 대한 다양한 열을 볼 수도 있습니다. 열 집합을 사용자 지정하고 열 이름을 선택하여 이러한 열을 사용하여 인시던트 큐를 정렬할 수 있습니다. 요구에 따라 인시던트 큐를 필터링할 수도 있습니다. 사용 가능한 필터의 전체 목록은 인시던트 [우선 순위 지정을 참조하세요.](incident-queue.md#available-filters)

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="인시던트 큐의 예입니다.":::

    이 인시던트 집합에 대해 순위를 지정하는 방법의 한 가지 예는 더 많은 사용자 및 장치에 영향을 주는 인시던트의 우선 순위를 지정하는 것입니다. 이 예에서는 인시던트 ID 6769가 최대 엔터티 수(장치 7개, 사용자 6명 및 사서함 2개)에 영향을 주어 인시던트 ID 6769의 우선 순위를 지정할 수 있습니다. 또한 인시던트는 ID 기반 경고 및 가능한 자격 증명 도난을 나타내는 Id에 대한 Microsoft Defender의 경고를 포함하는 것으로 나타납니다.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="영향력이 큰 인시던트의 예":::

2. 인시던트 이름 옆의 원을 선택하여 세부 정보를 검토합니다. 왼쪽 창이 오른쪽에 표시될 수 있습니다. 이 창에는 추가 정보를 포함해 더 많은 정보를 사용할 수 있습니다.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="인시던트 쪽 창의 예입니다.":::

   예를 들어 [MITRE ATT&CK에서](https://attack.mitre.org/) 공격자가 인시던트의 범주에 따라 사용하는 전술을 보고, 공격자가 훔친 자격 증명을 사용, 설정한 명령 및 제어, 측면 이동을 수행하고 일부 데이터를 유출하기 때문에 이 인시던트의 우선 순위를 지정할 수 있습니다. 이는 공격자가 이미 네트워크로 깊숙이 들어간 후 기밀 정보를 훔친 것일 수 있습니다.

   또한 조직에서 Zero Trust 프레임워크를 구현한 경우 자격 증명 액세스는 우선 순위를 정하는 데 중요한 보안 위반으로 고려할 수 있습니다.

   왼쪽 창 아래로 스크롤하면 사용자, 장치 및 사서함과 같은 영향을 받는 특정 엔터티가 표시됩니다. 각 장치 및 영향을 받는 사서함의 소유자의 노출 수준을 확인할 수 있습니다.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="인시던트 쪽 창 세부 정보의 예입니다.":::

3. 왼쪽 창 아래에서 관련 경고를 찾을 수 있습니다. Microsoft 365 Defender 경고의 상관 관계가 이미 수행되어 공격을 수정하는 데 필요한 시간 및 리소스를 절약할 수 있습니다. 경고는 의심스러우며 네트워크에서 공격자가 존재할 수 있는 악성 시스템 이벤트일 수 있습니다.

   이 예에서는 87개 개별 경고가 하나의 보안 인시던트의 일부로 결정했습니다. 모든 경고를 보고 공격이 어떻게 재생된 방식에 대한 빠른 보기를 얻을 수 있습니다.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="인시던트 쪽 창에 있는 경고의 예입니다.":::

## <a name="analyze-your-first-incident"></a>첫 번째 인시던트 분석

경고를 둘러싼 컨텍스트를 이해하는 것은 똑같이 중요합니다. 경고는 단일 독립 이벤트가 아닌 경우가 종종 있습니다. 동시에 발생하지 않을 수 있는 프로세스, 명령 및 작업의 체인이 있습니다. 따라서 분석가가 장치 타임라인에서 의심스러운 엔터티의 첫 번째 및 마지막 활동을 찾아 경고의 컨텍스트를 이해해야 합니다.

여러 가지 방법으로 데이터를 읽고 분석할 수 Microsoft 365 Defender 분석가의 최종 목표는 가능한 한 빠르게 인시던트에 대응하는 것입니다. 이 Microsoft 365 Defender 업계 최고의 자동화된 조사 및 응답 기능을 통해 [MTTR(평균](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) 재구성 시간)을 크게 줄일 수 있는 반면, 수동 분석이 필요한 사례는 항상 있습니다. [](m365d-autoir.md)

다음은 예입니다.

1. 우선 순위가 결정되면 분석가가 인시던트 이름을 선택하여 심층 분석을 시작합니다. 이 페이지에서는 분석을 **지원하기** 위해 데이터가 탭에 표시되는 인시던트 요약을 표시합니다. 경고 **탭 아래에** 경고 유형이 표시됩니다. 분석가가 각 경고를 클릭하여 각 검색 원본으로 드릴다운할 수 있습니다.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="인시던트의 요약 탭 예":::

    각 검색 원본에서 다루는 도메인에 대한 빠른 가이드를 확인하려면 이 문서의 [검색](#detection-by-microsoft-365-defender) 섹션을 참조하세요.

2. 경고 **탭에서** 분석가가 검색 원본에 피벗하여 보다 심층적인 조사 및 분석을 수행 할 수 있습니다. 예를 들어 검색 원본으로 Microsoft Cloud App Security 맬웨어 검색을 선택하면 분석가가 해당 경고 페이지로 이동합니다.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="인시던트 경고를 선택하는 예입니다.":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="에 있는 해당 페이지의 Microsoft Cloud App Security.":::

3. 예제를 더 조사하려면 페이지 맨 아래로 스크롤하여 영향을 받은 **사용자를 를 니다.** 맬웨어 검색을 둘러싼 활동 및 컨텍스트를 확인하려면 AnnetteEtte의 사용자 페이지를 선택합니다.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="사용자 페이지의 예입니다.":::

4. 사용자 페이지에는 TOR 네트워크 IP 주소 경고에서 위험한 로그인으로 시작하는 이벤트의 연대기 *목록이* 있습니다. 활동의 의심스러운 가능성은 조직이 비즈니스를 수행한 방식의 특성에 따라 달라지지만, 대부분의 경우 사용자가 웹을 익명으로 탐색할 수 있는 네트워크인 TOR(Onion 라우터)을 사용하는 경우 엔터프라이즈 환경에서는 일반 온라인 작업의 경우 매우 가능성 높고 불필요한 것으로 간주될 수 있습니다.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="사용자에 대한 이벤트의 연도 목록의 예입니다.":::

5. 각 경고를 선택하면 활동에 대한 자세한 정보를 얻을 수 있습니다. 예를 들어 **Tor IP 주소** 경고에서 활동을 선택하면 해당 경고의 자체 페이지로 연결됩니다. Annette는 관리자로서 Office 365 권한이 상승되어 원본 인시던트가 기밀 정보에 액세스하게 됐을 수 있습니다.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="에 대한 경고 세부 정보 Microsoft Cloud App Security.":::

6. 다른 경고를 선택하면 분석가가 공격의 전체적인 그림을 얻을 수 있습니다.

## <a name="next-step"></a>다음 단계

[![2단계: 인시던트 수정 방법을 배워야 합니다.](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

인시던트 [수정 방법을 학습합니다.](first-incident-remediate.md)

## <a name="see-also"></a>참고 항목

- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)

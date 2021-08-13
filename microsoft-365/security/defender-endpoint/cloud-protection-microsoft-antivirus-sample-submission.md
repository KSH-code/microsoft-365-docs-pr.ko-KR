---
title: 클라우드 제공 보호 Microsoft Defender 바이러스 백신 샘플 제출
description: 클라우드 제공 보호 및 보호에 대해 Microsoft Defender 바이러스 백신
keywords: Microsoft Defender 바이러스 백신, 차세대 기술, 바이러스 백신 샘플 제출, 차세대 av, 기계 학습, 맬웨어 방지, 보안, defender, 클라우드, 클라우드 제공 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: jweston-1
ms.author: v-jweston
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 07/22/2021
ms.openlocfilehash: 520f500ce6e0ec10f7d37d1d08efcc91c8910352cdf551ee6e37e4904c459688
ms.sourcegitcommit: 14a8a80aa85d501d3a77f6cdd3aba6750e6775e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "57834634"
---
# <a name="cloud-delivered-protection-antivirus-sample-submission"></a>클라우드 제공 보호 바이러스 백신 샘플 제출

Endpoint 바이러스 백신용 Microsoft Defender(Defender for Endpoint 바이러스 백신)는 맬웨어를 검색하기 위한 많은 지능형 메커니즘을 사용 합니다. 가장 강력한 기능 중 하나는 클라우드의 기능을 적용하여 맬웨어를 감지하는 기능입니다. Defender for Endpoint antivirus Cloud Protection은 끝점에서 Endpoint 바이러스 백신 Defender와 함께 작동하여 결정을 내리고 새로운 위협으로부터 끝점을 보호합니다.

## <a name="microsoft-defender-for-endpoint-antivirus-cloud-protection-overview"></a>Endpoint 바이러스 백신용 Microsoft Defender 클라우드 보호 개요

클라우드 보호는 기본적으로 Endpoint 바이러스 백신용 Defender에서 사용하도록 설정되어 있습니다. 고객이 Endpoint 바이러스 백신용 Defender의 클라우드 보호를 사용하지 않도록 설정하지 않는 것이 좋습니다.  클라우드 보호를 사용하도록 설정한 경우 클라우드에 제공할 끝점 바이러스 백신용 Defender 정보(샘플 제출 포함)를 구성할 수 있습니다. 클라우드 보호 사용은 다른 특성에 따라 높은 신뢰도의 결정이 만들어질 수 없는 경우 유용합니다.
샘플 제출 구성은 작동 방식에 대한 의문을 제기합니다. 예를 들어 데이터를 저장하고 사용하는 방법을 예로 들 수 있습니다. 가장 많은 의문을 제기하는 세 가지 클라우드 보호 샘플 제출 옵션은 다음과 같습니다.

- "안전한 샘플 자동 보내기"(기본 동작)
- "모든 샘플을 자동으로 보내기",  
- "샘플을 보내지 않습니다."  

Intune, Configuration Manager, GPO 또는 PowerShell을 사용하는 구성 옵션에 대한 자세한 내용은 에서 클라우드 제공 보호 [Microsoft Defender 바이러스 백신.](enable-cloud-protection-microsoft-defender-antivirus.md)  

## <a name="customer-data-cloud-protection-and-sample-submission"></a>고객 데이터, 클라우드 보호 및 샘플 제출

Endpoint용 Defender에 온보딩할 때 Endpoint용 Defender는 모든 파일 샘플을 고객 데이터로 취급하며, 고객이 선택한 지역 및 데이터 보존 선택을 모두 존중합니다. 지리적 및 데이터 보존 선택은 Endpoint 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender에 설명되어 있습니다.](data-storage-privacy.md#data-storage-location)
이 제품은 여러 규정 준수 인증을 받았고 정교한 규정 준수 컨트롤 집합을 계속 준수하고 있는 것으로 나타냈습니다.

- ISO 27001
- ISO 27018
- SOC I, II, III
- 및 PCI

[Azure 규정 준수 서비스는](/azure/storage/common/storage-compliance-offerings) 이러한 인증에 대한 자세한 정보를 제공합니다. 끝점용 Microsoft Defender의 모든 인증 아티팩트는 연결된 각 Azure 인증 보고서 내에서 Microsoft의 [Service Trust Portal에서](https://servicetrust.microsoft.com/) 찾을 수 있습니다.

## <a name="cloud-protection-mechanisms"></a>클라우드 보호 메커니즘

Microsoft 지능형 Graph 네트워크의 위협 데이터를 모니터링합니다. 지능형 보안 센터에서 클라이언트의 신호와 방대한 센서 및 데이터의 네트워크를 기반으로 평가를 할 수 있는 클라우드 기반 기계 학습 모델을 Graph. 이 모델은 끝점에 대해 Defender가 전에 볼 수 없는 많은 위협을 차단할 수 있는 기능을 제공합니다.

Endpoint 바이러스 백신 및 클라우드 보호용 Defender는 다음 방법을 사용하여 가장 전에 볼 수 없는 가장 새로운 위협을 자동으로 차단합니다.

1. 새 맬웨어 및 알 수 없는 맬웨어를 차단하는 경량 클라이언트 기반 기계 학습 모델입니다.

2. 로컬 동작 분석, 파일 기반 및 파일 비포일 공격 중지

3. 일반 및 지론 기술을 통해 일반적인 맬웨어를 감지하는 고정밀 바이러스 백신입니다.

4. 끝점에서 실행되는 끝점 바이러스 백신에 대한 Defender가 의심스러운 파일의 의도를 확인하기 위해 더 많은 인텔리전스가 필요한 경우 고급 클라우드 기반 보호가 제공됩니다.

   1. Microsoft Defender for Endpoint 바이러스 백신이 명확한 확인을 할 수 없는 경우 파일 메타데이터가 클라우드 보호 서비스로 전송됩니다. 일반적으로 클라우드 보호 서비스는 파일이 안전한지 또는 악성인지를 밀리초 내에 확인할 수 있습니다.  
      - 파일 메타데이터의 클라우드 쿼리는 동작, 웹 표시 또는 명확한 결과가 결정되지 않은 기타 특성의 결과일 수 있습니다.
      - 클린 vs 맬웨어 판정에 도달하기 위해 작은 메타데이터 페이로드가 전송됩니다.
      - 메타데이터에는 PE 특성, 정적 파일 특성, 동적 및 상황적 특성 등을 포함할 수 있습니다(그림 1).
      - PII(개인 식별 정보)는 포함하지 않습니다. 파일 이름 등의 정보는 해시됩니다.
      - 동기식 또는 비동기식일 수 있습니다. 동기식의 경우 클라우드에서 판정을 렌더링할 때까지 파일이 열립니다. 비동기의 경우 클라우드에서 분석을 수행하는 동안 파일이 열립니다.

   2. 메타데이터를 검사한 후 Endpoint 바이러스 백신 클라우드 보호에 대한 Defender가 결정적 판정에 도달할 수 없는 경우 추가 검사를 위해 파일의 샘플을 요청할 수 있습니다. 이 요청은 샘플 제출에 대한 설정 구성을 존중합니다.

      1. **안전한 샘플 자동 보내기(기본값)**
         - 금고 샘플은 일반적으로 PII 데이터를 포함하지 않는 것으로 간주되는 샘플로, .bat, .scr, .dll, .exe.
         - 파일에 PII가 포함될 가능성이 있는 경우 사용자는 파일 샘플 제출을 허용하도록 요청합니다.
         - 이는 Windows, macOS 및 Linux에서 기본값입니다.

      2. **항상 프롬프트**
         - 구성된 경우 파일 제출 전에 항상 사용자에게 동의를 요청하라는 메시지가 표시됩니다.
         - MacOS 클라우드 보호에서는 이 설정을 사용할 수 없습니다.

      3. **모든 샘플 자동 보내기**
         - 구성된 경우 모든 샘플이 자동으로 전송됩니다.
         - Word docs에 포함된 매크로를 샘플 제출에 포함하려면 "모든 샘플을 자동으로 보내기"를 선택해야 합니다.  
         - MacOS 클라우드 보호에서는 이 설정을 사용할 수 없습니다.

      4. **보내지 않습니다.**
         - 파일 샘플 분석을 기반으로 "모든 시 차단"을 방지합니다.
         - "보내지 않습니다."는 macOS 정책의 "사용 안 하게" 설정과 동일합니다.
         - 샘플 제출을 사용하지 않도록 설정한 경우에도 검색을 위해 메타데이터가 전송됩니다.

   3. 메타데이터 및/또는 파일이 Endpoint 클라우드용 Defender에 제출된 후  **샘플,** 데토네이터 또는 빅 데이터 분석 기계 학습 모델을 사용하여 판정에 도달할 수 있습니다.  이 모델은 그림 3에 설명되어 있습니다. 클라우드 제공 보호를 해제하면 클라이언트가 로컬 기계 학습 모델 및 유사한 기능을 통해 제공할 수 있는 기능으로만 분석이 제한됩니다.

_그림 1 - Microsoft Defender 클라우드 보호로 전송된 메타데이터의 예_

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="그림 1. Microsoft Defender 클라우드 보호로 전송된 메타데이터의 예":::

_그림 2. 클라우드 제공 보호 흐름_

:::image type="content" source="images/cloud-protection-flow.png" alt-text="그림 2. 클라우드 제공 보호 흐름":::

_그림 3. 클라우드 제공 보호 및 계층적 기계 학습_

:::image type="content" source="images/cloud-protection-detection-layered-machine-learning.png" lightbox="images/cloud-protection-detection-layered-machine-learning.png" alt-text="그림 3. 클라우드 제공 보호 및 계층적 기계 학습":::

> [!Note]
>
> "BAFS(최초 차단)"라는 구문도 들어 있을 수 있습니다. BAFS는 더 정확한 결과를 제공하기 위해 데토네이터와 같은 정보를 포함하여 클라우드에서 제공할 수 있는 보다 광범위한 분석을 지어보입니다. 여기에는 클라우드 보호에 의해 중간에 있는 파일의 열기 지연이 판결에 도달할 때까지 지연할 수 있습니다. "샘플 제출"을 사용하지 않도록 설정하면 BAFS가 사용하지 않도록 설정되고 보다 광범위한 분석을 할 수 없습니다. 파일 메타데이터만 분석하는 것으로 제한됩니다.

## <a name="cloud-delivered-protection-levels"></a>클라우드 제공 보호 수준

맬웨어 검색을 사용하려면 최대한 강력한 보호를 제공하는 동시에 가식성 수를 최소화해야 합니다. 서로 다른 환경은 보호에 대한 허용 범위와 가짓 긍정 위험에 대한 허용 오차가 있을 수 있습니다. 클라우드 제공 보호 수준을 통해 고객은 특정 환경에 적합한 허용 오차 수준을 정의할 수 있습니다. 클라우드 제공 보호를 사용하도록 설정하면 합법적인 파일을 검색할 위험을 늘리지 않고 강력한 검색을 제공하도록 보호 수준이 자동으로 구성됩니다. 다른 보호 수준을 구성하려는 경우 에 대한 클라우드 제공 보호 [수준 지정을 Microsoft Defender 바이러스 백신.](specify-cloud-protection-level-microsoft-defender-antivirus.md)  

> [!Note]
>
> 보호 수준을 변경하면 가긍정 수준이 높아지며 변경하기 전에 신중하게 평가해야 합니다.
>

## <a name="other-file-sample-submission-scenarios"></a>기타 파일 샘플 제출 시나리오

끝점용 Defender가 위에서 설명한 클라우드 보호 설정과 관련이 없는 파일 샘플을 요청할 수 있는 두 가지 시나리오가 더 있습니다.  

### <a name="manual-file-sample-collection-by-security-admin-from-defender-for-endpoint-management-portal"></a>Endpoint Management Portal용 Defender의 보안 관리자에 의해 수동 파일 샘플 수집

디바이스를 끝점용 Microsoft Defender로 온보딩할 EDR 장치에서 샘플 컬렉션을 사용하도록 설정하는 설정이 있습니다. 이 설정은 위에서 설명한 설정과 혼동될 수 있습니다. 이 설정은 Endpoint 관리 포털용 Defender를 통해 요청된 경우 장치에서 파일 샘플 수집을 제어합니다. 이미 설정한 역할 및 사용 권한이 적용될 수 있습니다. 이 설정은 끝점 포털용 Defender에서 심층 분석과 같은 기능을 위해 끝점에서 파일 수집을 허용하거나 차단할 수 있습니다. 이 설정이 구성되지 않은 경우 기본값은 샘플 수집을 사용하도록 설정하는 것입니다.

끝점 구성 설정에 대한 Defender에 대한 자세한 내용은 [Endpoint용 Defender의](configure-endpoints.md) Windows 10 도구 및 방법을 참조하세요.

### <a name="automated-investigation-and-response-content-analysis"></a>자동화된 조사 및 응답 콘텐츠 분석

자동화된 조사가 장치에서 실행되는 경우(경고 또는 수동으로 실행에 응답하여 자동으로 실행하도록 구성된 경우) 이후 검사를 위해 끝점에서 의심스러운 파일을 수집할 수 있습니다. 자동화된 조사에 대한 파일 콘텐츠 분석 기능은 끝점용 Defender 포털에서 사용하지 않도록 설정할 수 있습니다. 자동화된 조사 중에 자동으로 제출되는 다른 파일 형식의 확장명을 추가하거나 제거하기 위해 파일 확장명 이름을 수정할 수도 있습니다.

[자동화 파일 업로드 관리](manage-automation-file-uploads.md)

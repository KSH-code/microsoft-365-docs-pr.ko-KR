---
title: 전자 메일 보호의 순서 및 우선 순위
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 보호의 응용 프로그램 순서와 보호 정책의 우선 순위 값이 적용 되는 정책을 결정 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: ed4806bad6299dc5a5380bec2f6e1247f9d6b448
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633969"
---
# <a name="order-and-precedence-of-email-protection"></a>전자 메일 보호의 순서 및 우선 순위

Microsoft 365 사용자는 인바운드 전자 메일에 여러 보호 형태의 플래그를 지정 했을 수 있습니다. 예를 들어 모든 Microsoft 365 고객이 사용할 수 있는 기본 제공 EOP 피싱 방지 정책과 Office 365 Advanced Threat Protection 고객도 사용할 수 있는 더욱 견고한 ATP 피싱 방지 정책 또한 메시지는 맬웨어, 스팸, 피싱 등에 대해 여러 검색 검사를 통과 합니다. 이 모든 활동이 제공 되는 경우 적용 되는 정책과 같은 혼동이 있을 수 있습니다.

일반적으로 메시지에 적용 되는 정책은 **CAT (Category)** 속성의 **스팸 방지-Report** 헤더에서 식별 됩니다. 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.

메시지에 적용 되는 정책을 결정 하는 두 가지 주요 요인은 다음과 같습니다.

- **전자 메일 보호 유형의 우선 순위**:이 순서는 구성할 수 없으며 다음 표에 설명 되어 있습니다.

  |||||
  |---|---|---|---|
  |**Priority(우선 순위)**|**전자 메일 보호**|**범주**|**관리할 위치**|
  |1 |맬웨어|CAT: MALW|[Office 365에서 맬웨어 방지 정책 구성](configure-anti-malware-policies.md)|
  |2 |피싱|CAT: PHSH|[Office 365에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |3 |높은 정확도 스팸|CAT: HSPM|[Office 365에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |4 |스푸핑|CAT: 스푸핑|[Office 365에서 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)|
  |5 |스팸|CAT: SPM|[Office 365에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |6 |대량|CAT: 대량|[Office 365에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |연중<sup>\*</sup>|도메인 가장 (보호 된 사용자)|DIMP|[Office 365에서 ATP 피싱 방지 정책 구성](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|사용자 가장 (보호 된 도메인)|UIMP|[Office 365에서 ATP 피싱 방지 정책 구성](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>이러한 기능은 ATP 피싱 방지 정책 에서만 사용할 수 있습니다.

- **정책의 우선 순위**: 각 보호 유형 (스팸 방지, 맬웨어 방지, 피싱 방지 등)에 대해 모든 사용자에 게 적용 되는 기본 정책이 있지만 특정 사용자에 게 적용 되는 사용자 지정 정책을 종종 만들 수 있습니다. 각 사용자 지정 정책에는 정책이 적용 되는 순서를 결정 하는 우선 순위 값이 있습니다. 기본 정책은 항상 마지막으로 적용 됩니다.

  사용자가 같은 유형의 여러 정책에서 정의 된 경우에는 우선 순위가 가장 높은 정책만 적용 됩니다. 해당 유형의 나머지 정책은 사용자에 대해 평가 되지 않습니다 (기본 정책 포함).

예를 들어 **동일한 사용자에 게 적용 되**는 다음 ATP 피싱 방지 정책 및 사용자 가장 및 스푸핑으로 식별 되는 메시지를 고려해 야 합니다.

  |||||
  |---|---|---|---|
  |**ATP 피싱 방지 정책**|**Priority(우선 순위)**|**사용자 가장**|**스푸핑 방지**|
  |정책 A|1 |켜짐|해제|
  |정책 B|2 |해제|켜짐|
  |

1. 스푸핑 우선 순위 (4)가 사용자 가장 (8) 보다 높기 때문에 메시지가 스푸핑로 표시 되 고 처리 됩니다.
2. 정책 A는 정책 B 보다 우선 순위가 높기 때문에 사용자에 게 적용 됩니다.
3. 정책 A의 설정을 기반으로 하 여 스푸핑 방지 기능이 해제 되었기 때문에 메시지에 아무 작업도 수행 되지 않습니다.
4. 정책 처리가 중지 되므로 정책 B는 사용자에 게 적용 되지 않습니다.

동일한 사용자가 같은 유형의 여러 사용자 지정 정책에 고의적으로 포함 될 수도 있으므로 사용자 지정 정책에 대 한 다음 디자인 지침을 사용 합니다.

- 소수의 사용자에 게 적용 되는 정책에 더 높은 우선 순위를 할당 하 고 많은 사용자에 게 적용 되는 정책의 우선 순위를 낮춥니다. 기본 정책은 항상 마지막에 적용 됩니다.
- 우선 순위가 낮은 정책 보다 더 엄격한 설정이 되도록 우선 순위가 높은 정책을 구성 합니다.
- 보다 짧은 사용자 지정 정책을 사용 하는 것이 좋습니다 (보다 엄격한 설정이 필요한 사용자에 대해서만 사용자 지정 정책 사용).

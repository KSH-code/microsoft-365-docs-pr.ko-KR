---
title: 전자 메일 보호 순서 및 우선 순위
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 보호 순서와 보호 정책에서 의지 여부 값이 적용되는 정책을 결정하는 방법에 대해 학습할 수 있습니다.
ms.openlocfilehash: 9556d2262eb59224357e20027a1f0e63404081f2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827412"
---
# <a name="order-and-precedence-of-email-protection"></a>전자 메일 보호 순서 및 우선 순위

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 전자 메일은 여러 형제 유형의 보호에 의해 플래그 지정될 수 있습니다. 예를 들어 모든 Microsoft 365 고객이 사용할 수 있는 기본 제공 EOP 피싱 방지 정책과 Office 365 ATP(Advanced Threat Protection) 고객에게 제공되는 더 강력한 ATP 피싱 방지 정책을 사용할 수 있습니다. 또한 메시지가 맬웨어, 스팸, 피싱 등에 대한 여러 탐지 검사를 통과합니다. 해당 활동이 모두 지정된 경우 어떤 정책이 적용되는지에 대해 다를 수 있습니다.

일반적으로 메시지에 적용되는 정책은 **CAT(범주)** **속성의 X-Forefront-Antispam-Report** 헤더에서 식별됩니다. 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.

메시지에 적용되는 정책을 결정할 때는 다음과 같은 두 가지 주요 요소가 있습니다.

- **전자 메일 보호 유형의 우선순위:** 이 순서는 구성할 수 없습니다. 이 표는 다음 표에 설명되어 있습니다.

  ****

  |우선 순위|전자 메일 보호|범주|관리할 위치|
  |---|---|---|---|
  |1|맬웨어|CAT:MALW|[EOP에서 맬웨어 방지 정책 구성](configure-anti-malware-policies.md)|
  |2|피싱|CAT:PHSH|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |3|높은 정확도 스팸|CAT:HSPM|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |4 |스푸핑|CAT:SPOOF|[EOP에서 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)|
  |5 |스팸|CAT:SPM|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |6 |대량|CAT:BULK|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|도메인 가장(보호된 사용자)|DIMP|[ATP 피싱 방지 정책 구성](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|사용자 가장(보호된 도메인)|UIMP|[ATP 피싱 방지 정책 구성](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup> 이러한 기능은 ATP 피싱 방지 정책에서만 사용할 수 있습니다.

- **정책의 우선순위:** 각 보호 유형(스팸 방지, 맬웨어 방지, 피싱 등)에 대해, 모든 사용자에게 적용되는 기본 정책이 있지만, 특정 사용자에게 적용되는 사용자 지정 정책을 만들 수 있습니다. 각 사용자 지정 정책에는 정책이 적용되는 순서를 결정하는 우선 순위 값이 있습니다. 기본 정책은 항상 마지막에 적용됩니다.

  사용자가 동일한 유형의 여러 정책에서 정의된 경우 우선 순위가 가장 높은 정책만 적용됩니다. 해당 유형의 나머지 정책은 사용자에 대해 평가되지 않습니다(기본 정책 포함).

예를 들어 동일한 사용자에게 적용되는 다음과 같은 ATP 피싱 방지 **정책과**사용자 가장 및 스푸핑으로 식별되는 메시지를 고려해 보세요.

  ****

  |ATP 피싱 방지 정책|우선 순위|사용자 가장|스푸핑 방지|
  |---|---|---|---|
  |정책 A|1|켜짐|해제|
  |정책 B|2|해제|켜짐|
  |

1. 스푸핑의 우선 순위가 사용자 가장(8)보다 높기 때문에 메시지가 스푸핑으로 표시되고 처리됩니다.
2. 정책 A는 정책 B보다 우선 순위가 높기 때문에 사용자에게 적용됩니다.
3. 정책 A의 설정에 따라 정책에서 스푸핑 방지가 해제되므로 정책 A의 설정에 따라 메시지에 대해 아무 작업도 수행되지 않습니다.
4. 정책 처리가 중지되므로 정책 B가 사용자에게 적용되지 않습니다.

같은 유형의 여러 사용자 지정 정책에 의도적으로 또는 의도적으로 같은 사용자가 포함될 수 있습니다. 사용자 지정 정책에 대해 다음 디자인 지침을 따르세요.

- 소수의 사용자에게 적용할 수 높은 우선 순위를 할당하고 많은 수의 사용자에게 적용되는 정책에 낮은 우선 순위를 할당합니다. 기본 정책은 항상 마지막에 적용됩니다.
- 우선 순위가 낮은 정책보다 우선 순위가 높은 정책을 더 전보다 또는 더 구체적으로 설정하도록 구성합니다.
- 더 많은 사용자 지정 정책을 사용하는 것이 좋습니다(더 강격한 또는 보다 전화된 설정을 필요로 하는 사용자의 경우에만 사용자 지정 정책을 사용).

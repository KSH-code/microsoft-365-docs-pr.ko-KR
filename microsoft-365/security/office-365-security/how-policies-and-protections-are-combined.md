---
title: 전자 메일 보호의 순서 및 우선 순위
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, Microsoft 365 Defender 포털, 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, ID용 Microsoft Defender
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection 보호)의 응용 프로그램 순서와 보호 정책의 우선 순위 값이 적용되는 정책을 결정하는 방법을 알 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fbccec656e0508535c2fbdaa055777a07968878
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210440"
---
# <a name="order-and-precedence-of-email-protection"></a>전자 메일 보호의 순서 및 우선 순위

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection)에 사서함이 있는 Exchange Online 조직에서 인바운드 전자 메일은 여러 형태의 보호로 플래그가 지정될 수 있습니다. 예를 들어 모든 Microsoft 365 고객에게 제공되는 EOP의 기본 제공 피싱 방지 정책과 Microsoft Defender에서 사용할 수 있는 보다 강력한 피싱 방지 정책이 Office 365 있습니다. 또한 메시지는 맬웨어, 스팸, 피싱 등에 대한 여러 검색 검색을 통과합니다. 이 모든 활동이 제공될 경우 어떤 정책이 적용되는지 혼동될 수 있습니다.

일반적으로 메시지에 적용되는 정책은 **CAT(Category)** 속성의 **X-Forefront-Antispam-Report** 헤더에서 식별됩니다. 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.

메시지에 적용되는 정책을 결정하는 주요 요인에는 다음 두 가지가 있습니다.

- 전자 메일 보호 유형의 **우선 순위:** 이 순서는 구성할 수 없습니다. 다음 표에 설명되어 있습니다.

  <br>

  ****

  |우선 순위|전자 메일 보호|범주|관리할 위치|
  |---|---|---|---|
  |1|맬웨어|CAT:MALW|[EOP에서 맬웨어 방지 정책 구성](configure-anti-malware-policies.md)|
  |2|피싱|CAT:PHSH|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |3 |높은 정확도 스팸|CAT:HSPM|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |4 |스푸핑|CAT:SPOOF|[EOP의 스푸핑 인텔리전스 정보](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|사용자 가장(보호된 사용자)|UIMP|[Microsoft Defender에서 피싱 방지 정책 Office 365](configure-mdo-anti-phishing-policies.md)|
  |6<sup>\*</sup>|도메인 가장(보호된 도메인)|DIMP|[Microsoft Defender에서 피싱 방지 정책 Office 365](configure-mdo-anti-phishing-policies.md)|
  |7 |스팸|CAT:SPM|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |8 |대량|CAT:BULK|[EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup>이러한 기능은 Microsoft Defender for Office 365.

- **정책 우선** 순위: 각 정책 유형(스팸 방지, 맬웨어 방지, 피싱 방지 등)에 대해 모든 사용자에게 적용되는 기본 정책이 있지만 특정 사용자에게 적용되는 사용자 지정 정책을 만들 수 있습니다. 각 사용자 지정 정책에는 정책이 적용되는 순서를 결정하는 우선 순위 값이 있습니다. 기본 정책은 항상 마지막에 적용됩니다.

  > [!IMPORTANT]
  > 사용자가 동일한 유형의 여러 정책에 정의되어 있는 경우 우선 순위가 가장 높은 정책만 적용됩니다. 해당 유형의 나머지 정책은 사용자에 대해 평가되지 않습니다(기본 정책 포함).

예를 들어 동일한 사용자에게 적용되는 Office 365 Microsoft Defender의 다음 피싱 방지 정책과 사용자 가장 및 스푸핑으로 식별된 메시지를 고려합니다. 

<br>

****

|정책 이름|우선 순위|사용자 가장|스푸핑 방지|
|---|---|---|---|
|정책 A|1|켜짐|해제|
|정책 B|2|해제|켜짐|
|

1. 스푸핑의 우선 순위가 사용자 가장(5)보다 높기 때문에 메시지가 스푸핑으로 표시되어 처리됩니다.
2. 정책 A는 정책 B보다 우선 순위가 높기 때문에 사용자에게 적용됩니다.
3. 정책 A의 설정에 따라 정책에서 스푸핑 방지가 꺼져 있기 때문에 메시지에 대한 작업이 수행하지 않습니다.
4. 정책 처리가 중지되고 사용자에게 정책 B가 적용되지 않습니다.

동일한 사용자가 같은 유형의 여러 사용자 지정 정책에 의도적으로 또는 의도하지 않은 것으로 포함될 수 있기 때문에 사용자 지정 정책에 대해 다음 디자인 지침을 사용하세요.

- 적은 수의 사용자에게 적용되는 정책에 더 높은 우선 순위를 할당하고 많은 수의 사용자에게 적용되는 정책에 낮은 우선 순위를 할당합니다. 기본 정책은 항상 마지막으로 적용됩니다.
- 우선 순위가 높은 정책이 우선 순위가 낮은 정책보다 더 엄격하거나 더 전문화된 설정을 하도록 구성합니다.
- 더 적은 수의 사용자 지정 정책을 사용하는 것이 좋습니다(더 엄격하거나 더 전문화된 설정이 필요한 사용자에 대해 사용자 지정 정책만 사용).

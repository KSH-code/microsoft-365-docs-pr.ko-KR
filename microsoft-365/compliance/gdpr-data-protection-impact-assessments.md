---
title: 데이터 보호 영향 평가
description: 이 문서는 정보와 데이터 컨트롤러를 제공하여 DPIA 필요 여부, 필요한 경우 포함할 세부 사항을 결정할 수 있도록 지원합니다.
keywords: 데이터 보호 영향 평가, DPIA, Dynamics 365, Microsoft Professional Services, Microsoft 365, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 612c2c310a337b38ab654c7465fad1d284c60903
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305078"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>GDPR에 대한 데이터 보호 영향 평가

GDPR(일반 데이터 보호 규제)는 EU(유럽 연합) 회원국 국민에게 제품과 서비스를 제공하거나 귀하 또는 귀사가 어디에 있는지 관계없이 EU 거주자의 데이터를 수집하고 분석하는 조직에 새로운 규칙을 도입합니다.  추가 세부 정보는 [GDPR 요약 항목](gdpr.md)에 있습니다. 이 문서에서는 Microsoft 제품 및 서비스를 사용하는 경우 GDPR 하의 DPIAs(데이터 보호 영향 평가)에 대한 정보를 안내합니다.

## <a name="terminology"></a>용어

이 문서에서 사용된 GDPR 용어에 대한 유용한 정의:

- *데이터 컨트롤러(컨트롤러)*: 개인 데이터 처리의 목적과 수단을 결정하는 법인, 공공 기관, 에이전시 또는 다른 사람과 독립적으로 또는 공동으로 작업하는 기타 단체입니다.  
- *개인 데이터* 및 *데이터 주체*: 식별되거나 식별 가능한 자연인(데이터 주체)과 관련된 모든 정보. 식별 가능한 자연인은 직접 또는 간접적으로 식별될 수 있는 사람입니다.  
- *프로세서*: 컨트롤러를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 에이전시 또는 기타 단체입니다.  
- *고객 데이터*: 비즈니스 운영의 일상적인 작업에서 생성되고 저장되는 데이터입니다.

## <a name="what-is-a-dpia"></a>DPIA란 무엇인가요?

GDPR은 ‘자연인의 권리와 자유에 대한 높은 위험을 초래할 가능성이 있는’ 작업에 대해 컨트롤러가 DPIA(데이터 보호 영향 평가)를 준비하도록 요구합니다. DPIA를 만들어야 하는 Microsoft 제품 및 서비스에는 아무것도 내제되어 있지 않습니다. 그러나 Microsoft 제품 및 서비스는 사용자 지정할 수 있기 때문에 Microsoft 구성의 세부 사항에 따라 DPIA가 필요할 수 있습니다. Microsoft는 그러한 정보에 대한 통제권이 없으며 그러한 정보에 대한 인사이트를 거의 또는 전혀 가지고 있지 않습니다. 사용자는 데이터 컨트롤러로서 데이터의 적절한 사용을 결정해야 합니다.

## <a name="dpia-in-action"></a>DPIA 실행

DPIA 지침은 Office 365, Azure, Dynamics 365 및 Microsoft 지원 및 전문 서비스에 적용됩니다. 해당 지침에는 다음 사항을 고려해야 합니다.

**DPIA는 언제 필요한가요?**

DPIA 완료 여부를 고려할 때 아래에 나열된 위험 요소를 해결해야 합니다. 그 밖의 잠재적인 요소 및 기타 세부 정보는 각 가이드의 1부에 있습니다.  

- 자동화된 프로세스를 기반으로하는 체계적이고 광범위한 데이터 평가.  
- 다양한 특정 범주의 데이터(자연인을 고유하게 식별하는 정보를 나타내는 데이터) 또는 범죄 전과 및 위법 행위와 관련된 개인 데이터 대규모 처리.
- 공개적으로 액세스할 수 있는 영역을 대규모로 체계적으로 모니터링.

GDPR에서는 다음을 명확하게 제시합니다. ‘처리 작업에서 개인 담당 의사, 다른 의료 전문가 또는 법률가가 환자 또는 클라이언트의 개인 데이터를 우려할 경우 개인 데이터 처리는 대규모로 간주되지 않습니다. 그러한 경우 데이터 보호 영향 평가는 필수 사항이 아닙니다.’

**DPIA를 완료하는 데 필요한 것은 무엇인가요?**

DPIA는 의도된 프로세스에 대한 특정 정보를 제공해야 합니다. 이는 가이드 2부에 자세히 설명되어 있습니다. 해당 정보에는 다음이 포함됩니다.

- DPIA의 목적과 관련한 데이터 처리의 필요성 및 비례의 원칙 평가  
- 자연인의 권리와 자유에 대한 위험 평가;
- 안전 조치, 보안 조치 및 개인 정보 보호를 보장하고 GDPR 준수를 입증하는 메커니즘을 포함하여 위험을 해결하기 위한 의도된 조치.
- 처리 목적  
- 처리된 개인 데이터의 범주  
- 데이터 보존  
- 개인 데이터의 위치 및 전송  
- 타사 하위 프로세서와 데이터 공유  
- 독립 타사와 데이터 공유  
- 데이터 주체 권리

## <a name="additional-considerations"></a>추가 고려 사항

Microsoft 구현에 관련된 구체적인 세부 정보는 아래에 있습니다.

- [Office 365](gdpr-dpia-office365.md):이 문서는 Exchange Online, SharePoint online, Yammer, 비즈니스용 Skype, Power BI를 비롯하여 Office 365 응용 프로그램 및 서비스에 적용됩니다. 자세한 내용은 표 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) 및 [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) 를 참조하세요.  
- [Azure](gdpr-dpia-azure.md): 고객은 개인 정보 책임자와 관리 담당자 및 법적 자문과 함께 Microsoft Azure 사용과 관련된 DPIA의 필요 여부 및 내용을 결정하는 것이 좋습니다.  
- [Dynamics 365](gdpr-dpia-dynamics.md): DPIA의 내용은 사용하고 있는 Dynamics 365 도구에 따라 다를 수 있습니다. 자세한 내용은 [2부 DPIA의 내용](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)를 참조하세요.
- [Microsoft 지원 및 전문 서비스](gdpr-dpia-prof-services.md): 전문 서비스는 특정 루틴이나 자동화된 데이터 처리를 수행하지 않으며 특수 범주를 처리하거나 공개적으로 액세스할 수 있는 데이터를 모니터링하거나 필요로 하는 작업을 수행하지 않습니다. 자세한 내용은 [1부 — DPIA 필요 여부 결정](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)을 참조하세요. 컨트롤러는 컨트롤러의 특정 구현 및 프로페셔널 서비스 사용과 관련하여 위에서 설명한 DPIA 요소를 기타 관련 요소와 함께 고려해야 합니다. 전문 서비스에 대한 자세한 내용은 [2부 — DPIA의 내용](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)을 참조하세요.

## <a name="learn-more"></a>자세한 정보

- [Microsoft 보안 센터](https://www.microsoft.com/trust-center/privacy/gdpr-overview)

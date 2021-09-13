---
title: 고급 헌팅에서 오류를 처리합니다Microsoft 365 Defender
description: 고급 헌팅을 사용할 때 표시되는 오류 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema, kusto, 시간 제한, 리소스, 오류, 알 수 없는 오류, 제한, 할당량, 매개 변수, 할당량
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 32d50103c6476a89f24568edeea75a206e37e227
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211925"
---
# <a name="handle-advanced-hunting-errors"></a>고급 헌팅 오류 처리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender


고급 헌팅은 구문 실수를 알리는 오류를 표시하고 쿼리가 미리 정의된 할당량 및 사용 매개 변수에 적중될 때마다 를 [나타냅니다.](advanced-hunting-limits.md) 오류를 해결하거나 방지하는 방법에 대한 팁은 아래 표를 참조하세요.

| 오류 유형 | 원인 | 해결 방법 | 오류 메시지 예제 |
|--|--|--|--|
| 구문 오류 | 이 쿼리에는, 없는 연산자, 열, 함수 또는 표에 대한 참조를 포함하여 인식할 수 없는 이름이 포함되어 있습니다. | [Kusto](/azure/data-explorer/kusto/query/) 연산자 및 함수에 대한 참조가 올바른지 확인합니다. 올바른 [고급 헌팅](advanced-hunting-schema-tables.md) 열, 함수 및 표에 대한 자세한 정보를 확인할 수 있습니다. 변수 문자열을 인식할 수 있도록 따옴표로 묶습니다. 쿼리를 작성하는 동안에는 IntelliSense의 자동 완성 제안을 사용합니다. | `A recognition error occurred.` |
| 의미 오류 | 쿼리에서 유효한 연산자, 열, 함수 또는 표 이름을 사용하는 동안 해당 구조와 결과 논리에 오류가 발생했습니다. 경우에 따라 고급 헌팅은 오류를 일으신 특정 연산자를 식별합니다. | 쿼리 구조에서 오류를 검사합니다. 지침은 [Kusto 설명서를](/azure/data-explorer/kusto/query/) 참조하세요. 쿼리를 작성하는 동안에는 IntelliSense의 자동 완성 제안을 사용합니다. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 시간 제한 | 쿼리는 제한 시간 내에만 실행될 [수](advanced-hunting-limits.md)있습니다. 이 오류는 복잡한 쿼리를 실행하는 경우 더 자주 발생할 수 있습니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 스로틀 | 동일한 테넌트의 쿼리가 테넌트 크기에 따라 할당된 [CPU](advanced-hunting-limits.md) 리소스를 초과했습니다. | 이 서비스는 15분마다, 그리고 매일 CPU 리소스 사용량을 확인하고 할당된 할당량에서 10%를 초과한 후에 경고를 표시합니다. 사용률이 100%에 도달하면 서비스에서 다음 '매일' 또는 '15분' 주기가 지날 때까지 쿼리를 차단합니다. [CPU 할당량에 부적격하지 않도록 쿼리 최적화](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 결과 크기 제한 초과  | 쿼리에 대한 결과 집합의 집계 크기가 최대 크기를 초과했습니다. 이 오류는 결과 집합이 너무 커서 10,000 레코드 제한에서 잘라 내어 허용되는 크기로 줄일 수 없는 경우 발생할 수 있습니다. 크기를 조정할 수 있는 콘텐츠가 포함된 여러 열이 있는 결과는 이 오류의 영향을 더 많이 받게 됩니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 과도한 리소스 소비 | 쿼리에서 과도한 양의 리소스를 사용하며 완료가 중지되었습니다. 경우에 따라 고급 헌팅은 최적화되지 않은 특정 연산자를 식별합니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 알 수 없는 오류 | 알 수 없는 이유로 인해 쿼리가 실패했습니다. | 쿼리를 다시 실행해 보세요. 쿼리에서 알 수 없는 오류가 계속 반환될 경우 포털을 통해 Microsoft에 문의하세요. | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a>관련 항목
- [고급 헌팅 모범 사례](advanced-hunting-best-practices.md)
- [할당량 및 사용량 매개 변수](advanced-hunting-limits.md)
- [스키마에 대한 이해](advanced-hunting-schema-tables.md)
- [Kusto 쿼리 언어 개요](/azure/data-explorer/kusto/query/)
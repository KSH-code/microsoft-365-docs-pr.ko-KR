---
title: Microsoft 365 Defender의 고급 헌팅 오류 처리
description: 고급 헌팅을 사용할 때 표시되는 오류 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema, kusto, timeout, resources, errors, unknown error, limits, quota, parameter, allocation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929649"
---
# <a name="handle-advanced-hunting-errors"></a>고급 헌팅 오류 처리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


고급 헌팅은 구문 실수를 알리는 오류를 표시하고 쿼리가 미리 정의한 할당량 및 사용 매개 변수에 적중될 때마다 [표시됩니다.](advanced-hunting-limits.md) 오류를 해결하거나 방지하는 방법에 대한 팁은 아래 표를 참조하세요.

| 오류 유형 | 원인 | 해결 방법 | 오류 메시지 예제 |
|--|--|--|--|
| 구문 오류 | 이 쿼리에는 없는 연산자, 열, 함수 또는 테이블에 대한 참조를 포함하여 인식할 수 없는 이름이 들어 있습니다. | Kusto 연산자 및 함수에 대한 [참조가 올바른지](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 확인합니다. 올바른 [고급 헌팅](advanced-hunting-schema-tables.md) 열, 함수 및 표에 대한 스마마를 확인합니다. 변수 문자열을 인식할 수 있도록 따옴표로 묶습니다. 쿼리를 작성하는 동안 쿼리의 자동 IntelliSense. | `A recognition error occurred.` |
| 시맨틱 오류 | 쿼리에서 유효한 연산자, 열, 함수 또는 테이블 이름을 사용하면서 해당 구조와 결과 논리에 오류가 있습니다. 경우에 따라 고급 헌팅은 오류를 일으신 특정 연산자를 식별합니다. | 쿼리 구조에서 오류를 검사합니다. 지침은 [Kusto 설명서를](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 참조하세요. 쿼리를 작성하는 동안 쿼리의 자동 IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 시간 제한 | 쿼리는 제한 시간 내에만 실행될 [수 있습니다.](advanced-hunting-limits.md) 이 오류는 복잡한 쿼리를 실행하는 경우 더 자주 발생할 수 있습니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 스로틀 | 동일한 테넌트의 쿼리가 테넌트 크기에 따라 할당된 [CPU](advanced-hunting-limits.md) 리소스를 초과했습니다. | 이 서비스는 15분마다 매일 CPU 리소스 사용량을 확인하고 할당된 할당량 중 10%를 초과하면 경고를 표시합니다. 사용률이 100%에 도달하면 서비스에서 다음 일별 또는 15분 주기가 끝날 때까지 쿼리를 차단합니다. [CPU 할당량에 부과되는 것을 방지하도록 쿼리 최적화](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 결과 크기 제한 초과  | 쿼리에 대한 결과 집합의 집계 크기가 최대 크기를 초과했습니다. 이 오류는 결과 집합이 너무 커서 10,000개 레코드 제한에서 잘라서 허용되는 크기로 줄일 수 없는 경우 발생할 수 있습니다. 콘텐츠가 세분화될 수 있는 여러 열이 있는 결과는 이 오류의 영향을 더 많이 하게 됩니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 과도한 리소스 소비 | 쿼리에서 리소스를 과도하게 사용하며 완료가 중지되었습니다. 경우에 따라 고급 헌팅은 최적화되지 않은 특정 연산자를 식별합니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 알 수 없는 오류 | 알 수 없는 이유로 인해 쿼리가 실패했습니다. | 쿼리를 다시 실행하십시오. 쿼리에서 알 수 없는 오류를 계속 반환하는 경우 포털을 통해 Microsoft에 문의합니다. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 모범 사례](advanced-hunting-best-practices.md)
- [할당량 및 사용량 매개 변수](advanced-hunting-limits.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [Kusto 쿼리 언어 개요](https://docs.microsoft.com/azure/data-explorer/kusto/query/)

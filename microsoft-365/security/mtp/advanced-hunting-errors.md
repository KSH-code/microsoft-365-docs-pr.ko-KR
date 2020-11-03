---
title: Microsoft 365 Defender에 대 한 고급 구하기의 오류 처리
description: 고급 구하기 사용 시 표시 되는 오류 이해
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, kusto, timeout, 리소스, 오류, 알 수 없는 오류, 제한, 할당량, 매개 변수, 할당
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: a5379db66034ecfe537f7d9effdd83f6c41bfd58
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846895"
---
# <a name="handle-advanced-hunting-errors"></a>고급 구하기 오류 처리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


고급 구하기 쿼리를 통해 [미리 정의 된 할당량 및 사용 매개 변수가](advanced-hunting-limits.md)적중 될 때마다 구문 실수를 알리는 오류를 표시 합니다. 오류를 해결 하거나 방지 하는 방법에 대 한 팁을 보려면 아래 표를 참조 하세요.

| 오류 유형 | 원인 | 해결 방법 | 오류 메시지 예 |
|--|--|--|--|
| 구문 오류 | 존재 하지 않는 연산자, 열, 함수 또는 테이블에 대 한 참조를 포함 하 여 쿼리에 인식할 수 없는 이름이 있습니다. | [Kusto 연산자 및 함수](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 에 대 한 참조가 올바른지 확인 합니다. [스키마에서](advanced-hunting-schema-tables.md) 올바른 고급 구하기 열, 함수 및 테이블을 확인 합니다. 변수 문자열을 따옴표로 묶어 인식 합니다. 쿼리를 작성 하는 동안 IntelliSense에서 자동 완성 추천을 사용 합니다. | `A recognition error occurred.` |
| 의미 오류 | 쿼리에 유효한 operator, column, function 또는 table 이름이 사용 되는 동안 구조 및 결과 논리에 오류가 발생 합니다. 고급 구하기에서 오류를 일으킨 특정 연산자를 식별 하는 경우도 있습니다. | 쿼리 구조에서 오류를 확인 합니다. 자세한 내용은 [Kusto 설명서](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 를 참조 하십시오. 쿼리를 작성 하는 동안 IntelliSense에서 자동 완성 추천을 사용 합니다. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 짧으면 | 쿼리는 [제한 된 기간](advanced-hunting-limits.md)이내에만 실행할 수 있습니다. 복잡 한 쿼리를 실행할 때이 오류가 더 자주 발생할 수 있습니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 제한 | 같은 테 넌 트의 쿼리가 테 넌 트 크기에 따라 할당 된 [CPU 리소스](advanced-hunting-limits.md) 를 초과 했습니다. | 이 서비스는 CPU 리소스 사용량을 15 분 마다 확인 하 고 사용량이 할당 된 할당량의 10%를 초과 하면 경고를 표시 합니다. 사용률이 100%가 되 면 서비스가 다음 일별 또는 15 분 주기로 진행 될 때까지 쿼리를 차단 합니다. [CPU 할당량의 적중을 방지 하기 위해 쿼리 최적화](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 결과 크기 제한 초과  | 쿼리에 대 한 결과 집합의 집계 크기가 최대 크기를 초과 했습니다. 이 오류는 결과 집합이 너무 커서 1만 레코드 제한에서 잘릴 때 허용 되는 크기로 축소할 수 없는 경우에 발생 합니다. 콘텐츠가 크기를 조정할 수 있는 열이 여러 개 포함 된 결과는이 오류의 영향을 받을 가능성이 높습니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 과도 한 리소스 소비 | 쿼리에 많은 양의 리소스가 사용 되었으며 완료 되지 않았습니다. 고급 구하기에서 최적화 되지 않은 특정 연산자를 식별 하는 경우도 있습니다. | [쿼리 최적화](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 알 수 없는 오류 | 알 수 없는 이유로 쿼리가 실패 했습니다. | 쿼리를 다시 실행 해 보십시오. 쿼리가 계속 해 서 알 수 없는 오류를 반환 하는 경우 포털을 통해 Microsoft에 문의 합니다. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>관련 항목
- [고급 구하기 모범 사례](advanced-hunting-best-practices.md)
- [할당량 및 사용량 매개 변수](advanced-hunting-limits.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [Kusto 쿼리 언어 개요](https://docs.microsoft.com/azure/data-explorer/kusto/query/)

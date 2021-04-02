---
title: Microsoft Defender ATP의 고급 헌팅 제한
description: 고급 헌팅 서비스를 응답하도록 유지하는 다양한 서비스 제한 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp, 검색, 쿼리, 원격 분석, schema, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499536"
---
# <a name="advanced-hunting-service-limits"></a>고급 헌팅 서비스 제한

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

서비스 성능이 뛰어난 응답성을 유지하기 위해 고급 헌팅은 사용자 지정 검색 규칙에 따라 수동으로 실행되는 쿼리에 대한 다양한 [제한을 설정합니다.](custom-detection-rules.md) 이러한 제한을 이해하기 위해 다음 표를 참조합니다.

| 제한 유형 | Size | 새로 고침 주기 | 설명 |
|--|--|--|--|
| 데이터 범위 | 30일 | 모든 쿼리 | 각 쿼리는 최대 30일 동안의 데이터를 조회할 수 있습니다. |
| 결과 집합 | 행 10,000개 | 모든 쿼리 | 각 쿼리는 최대 10,000개 레코드를 반환할 수 있습니다. |
| 시간 제한 | 10분 | 모든 쿼리 | 각 쿼리는 최대 10분 동안 실행할 수 있습니다. 10분 내에 완료되지 않은 경우 서비스에 오류가 표시됩니다.
| CPU 리소스 | 테넌트 크기 기반 | - 시간 및 15분마다<br>- 매일 자정 12시 | 이 서비스는 일별 및 15분 제한을 별도로 적용합니다. 각 제한에 [](advanced-hunting-errors.md) 대해 포털은 쿼리가 실행될 때마다 테넌트가 할당된 리소스의 10% 이상을 소비할 때마다 오류를 표시합니다. 테넌트가 매일 또는 15분 주기가 끝날 때까지 100%에 도달하면 쿼리가 차단됩니다. |

>[!NOTE] 
>API를 통해 수행되는 고급 헌팅 쿼리에는 별도의 제한 집합이 적용됩니다. [고급 헌팅 API에 대한 읽기](run-advanced-query-api.md)

여러 쿼리를 정기적으로 실행하는 고객은 [](advanced-hunting-best-practices.md) 사용량을 추적하고 최적화 모범 사례를 적용하여 이러한 제한을 초과하여 발생하는 중단을 최소화해야 합니다.

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 모범 사례](advanced-hunting-best-practices.md)
- [고급 헌팅 오류 처리](advanced-hunting-errors.md)
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [사용자 지정 검색 규칙](custom-detection-rules.md)

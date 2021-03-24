---
title: Microsoft 365 Defender의 고급 헌팅 할당량 및 사용 매개 변수
description: 고급 헌팅 서비스를 응답하도록 유지하는 다양한 할당량 및 사용 매개 변수(서비스 제한) 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과, 할당량, 매개 변수, 할당량
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 19606b06ff1a1369614bab533a949bc383c90ad3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072772"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>고급 헌팅 할당량 및 사용 매개 변수

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

서비스 성능을 유지하기 위해 고급 헌팅은 다양한 할당량 및 사용 매개 변수("서비스 제한"이라고도 알려)를 설정합니다. 이러한 할당량 및 매개 변수는 수동으로 실행된 쿼리 및 사용자 지정 검색 [규칙에 적용됩니다.](custom-detection-rules.md) 여러 쿼리를 정기적으로 실행하는 고객은 [](advanced-hunting-best-practices.md) 사용법을 추적하고 최적화 모범 사례를 적용하여 중단을 최소화해야 합니다.

기존 할당량 및 사용 매개 변수를 이해하기 위해 다음 표를 참조합니다.

| 할당량 또는 매개 변수 | Size | 새로 고침 주기 | 설명 |
|--|--|--|--|
| 데이터 범위 | 30일 | 모든 쿼리 | 각 쿼리는 최대 30일 동안의 데이터를 조회할 수 있습니다. |
| 결과 집합 | 행 10,000개 | 모든 쿼리 | 각 쿼리는 최대 10,000개 레코드를 반환할 수 있습니다. |
| 시간 제한 | 10분 | 모든 쿼리 | 각 쿼리는 최대 10분 동안 실행할 수 있습니다. 10분 내에 완료되지 않은 경우 서비스에 오류가 표시됩니다.
| CPU 리소스 | 테넌트 크기 기반 | - 시간 및 15분마다<br>- 매일 자정 12시 | 이 서비스는 매일 및 15분 할당량은 별도로 적용합니다. 각 할당량에 대해 [](advanced-hunting-errors.md) 포털은 쿼리가 실행될 때마다 테넌트가 할당된 리소스의 10% 이상을 소비할 때마다 오류를 표시합니다. 테넌트가 매일 또는 15분 주기가 끝날 때까지 100%에 도달하면 쿼리가 차단됩니다. |

>[!NOTE] 
>별도의 할당량 및 매개 변수 집합은 API를 통해 수행되는 고급 헌팅 쿼리에 적용됩니다. [고급 헌팅 API에 대한 읽기](./api-advanced-hunting.md)

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 모범 사례](advanced-hunting-best-practices.md)
- [고급 헌팅 오류 처리](advanced-hunting-errors.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)
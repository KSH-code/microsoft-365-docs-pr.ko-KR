---
title: Microsoft Threat Protection의 고급 구하기 제한
description: Advanced 사냥 서비스의 응답성을 유지 하는 다양 한 서비스 제한 이해
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3fbe29076d541df68dc39754960386fe935c7bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950952"
---
# <a name="advanced-hunting-service-limits"></a>고급 구하기 서비스 제한

**적용 대상:**
- Microsoft 위협 방지

서비스의 성능과 응답성을 유지 하기 위해 고급 구하기에서는 수동으로 실행 되는 쿼리와 [사용자 지정 검색 규칙](custom-detection-rules.md)에 따라 다양 한 제한이 설정 됩니다. 이러한 제한을 이해 하려면 다음 표를 참조 하세요.

| 제한 유형 | 크기 | 새로 고침 주기 | 설명 |
|--|--|--|--|
| 데이터 범위 | 30일 | 모든 쿼리 | 각 쿼리는 최근 30 일까지 데이터를 조회할 수 있습니다. |
| 결과 집합 | 1만 행 | 모든 쿼리 | 각 쿼리는 최대 1만 개의 레코드를 반환할 수 있습니다. |
| 대기 | 10분 | 모든 쿼리 | 각 쿼리를 최대 10 분까지 실행할 수 있습니다. 10 분 이내에 완료 되지 않으면 서비스에서 오류를 표시 합니다.
| CPU 리소스 | 테 넌 트 크기 기반 | -1 시간 후 15 분 마다<br>-매일 자정 12 시 | 서비스는 매일 및 15 분 제한을 개별적으로 적용 합니다. 각 제한에 대해 쿼리를 실행 하 고 테 넌 트에서 할당 된 리소스의 10%를 초과 하 여 사용 하는 경우에는 [포털에 오류가 표시 됩니다](advanced-hunting-errors.md) . 다음 매일 또는 15 분 주기로 인해 테 넌 트가 다음 시간까지 100%에 도달 하면 쿼리가 차단 됩니다. |

>[!NOTE] 
>별도의 제한 집합은 API를 통해 수행 되는 고급 구하기 쿼리에 적용 됩니다. [고급 구하기 Api에 대 한 정보](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

정기적으로 여러 쿼리를 실행 하는 고객은 사용을 추적 하 고 [최적화 모범 사례를 적용](advanced-hunting-best-practices.md) 하 여 이러한 제한을 초과 하지 못하도록 하는 장애를 최소화 합니다.

## <a name="related-topics"></a>관련 항목

- [고급 구하기 모범 사례](advanced-hunting-best-practices.md)
- [고급 구하기 오류 처리](advanced-hunting-errors.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)

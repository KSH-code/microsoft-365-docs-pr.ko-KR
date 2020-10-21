---
title: Microsoft Threat Protection의 고급 구하기 할당량 및 사용 현황 매개 변수
description: 고급 구하기 서비스의 응답성을 유지 하는 다양 한 할당량 및 사용 매개 변수 (서비스 제한) 이해
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, kusto, CPU 제한, 쿼리 제한, 리소스, 최대 결과, 할당량, 매개 변수, 할당
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
ms.openlocfilehash: 192fb47aafdd20bd5e1f0774a64ec3215f1203d1
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636908"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>고급 구하기 할당량 및 사용 현황 매개 변수

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

서비스의 성능과 응답성을 유지 하기 위해 고급 사냥은 다양 한 할당량 및 사용 현황 매개 변수 ("서비스 제한"이 라고도 함)를 설정 합니다. 이러한 할당량 및 매개 변수는 수동으로 실행 되는 쿼리와 [사용자 지정 검색 규칙](custom-detection-rules.md)에 따라 적용 됩니다. 정기적으로 여러 쿼리를 실행 하는 고객은 소비를 추적 하 고, 중단을 최소화 하기 위한 [최적화 모범 사례를 적용](advanced-hunting-best-practices.md) 해야 합니다

기존 할당량과 사용 매개 변수를 이해 하려면 다음 표를 참조 하십시오.

| Quota 또는 parameter | 크기 | 새로 고침 주기 | 설명 |
|--|--|--|--|
| 데이터 범위 | 30일 | 모든 쿼리 | 각 쿼리는 최근 30 일까지 데이터를 조회할 수 있습니다. |
| 결과 집합 | 1만 행 | 모든 쿼리 | 각 쿼리는 최대 1만 개의 레코드를 반환할 수 있습니다. |
| 대기 | 10분 | 모든 쿼리 | 각 쿼리를 최대 10 분까지 실행할 수 있습니다. 10 분 이내에 완료 되지 않으면 서비스에서 오류를 표시 합니다.
| CPU 리소스 | 테 넌 트 크기 기반 | -1 시간 후 15 분 마다<br>-매일 자정 12 시 | 이 서비스는 매일 및 15 분의 할당량을 개별적으로 적용 합니다. 각 할당량에 대해 쿼리를 실행 하 고 테 넌 트가 할당 된 리소스의 10%를 초과 하는 경우 [portal에서 오류를 표시](advanced-hunting-errors.md) 합니다. 다음 매일 또는 15 분 주기로 인해 테 넌 트가 다음 시간까지 100%에 도달 하면 쿼리가 차단 됩니다. |

>[!NOTE] 
>별도의 할당량 및 매개 변수 집합은 API를 통해 수행 되는 고급 구하기 쿼리에 적용 됩니다. [고급 구하기 Api에 대 한 정보](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>관련 항목

- [고급 구하기 모범 사례](advanced-hunting-best-practices.md)
- [고급 구하기 오류 처리](advanced-hunting-errors.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)
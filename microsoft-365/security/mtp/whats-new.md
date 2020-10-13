---
title: Microsoft Threat Protection의 새로운 기능
description: Microsoft Threat Protection의 새로운 기능을 소개 합니다.
keywords: microsoft threat protection의 새로운 기능, ga, 일반적으로 사용 가능, 기능, 사용 가능, 신규
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 1b3cc273b61fcdff3c01b30c9ef64619a0e7a368
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430400"
---
# <a name="whats-new-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


일반적으로 Microsoft Threat Protection의 최신 릴리스에서는 다음 기능을 사용할 수 있습니다.

RSS 피드: 다음 URL을 복사 하 여 피드 판독기에 붙여 넣어이 페이지를 업데이트 하면 알림을 받습니다.
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a>2020년 9월
- [IdentityDirectoryEvents 테이블](advanced-hunting-identitydirectoryevents-table.md) <br> AD (Active Directory)를 실행 하는 온-프레미스 도메인 컨트롤러를 포함 하는 이벤트를 찾습니다. 이 [고급 구하기](advanced-hunting-overview.md) 스키마 테이블은 도메인 컨트롤러의 id 관련 이벤트 및 시스템 이벤트 범위를 다룹니다.
- [AssignedIPAddresses () 함수](advanced-hunting-assignedipaddresses-function.md) <br> 고급 구하기 쿼리에이 함수를 사용 하 여 특정 시간에 장치에 할당 된 최신 IP 주소 또는 가장 최근 IP 주소를 빠르게 가져올 수 있습니다.

## <a name="july-2020"></a>2020년 7월
- [FileProfile () 함수](advanced-hunting-fileprofile-function.md) <br> 고급 구하기 쿼리에서이 함수를 사용 하 여 광범위 한 파일 정보가 포함 된 결과를 보강 합니다.
- [Identity 및 app 테이블](advanced-hunting-schema-tables.md)<br> 고급 구하기 스키마에서 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)및 [appfileevents](advanced-hunting-appfileevents-table.md) 테이블을 사용 하 여 인증 이벤트, Active Directory 쿼리 및 앱 관련 작업에 대 한 가시성을 확인할 수 있습니다.
- [탐색](advanced-hunting-go-hunt.md)<br> 고급 사냥에서 특정 이벤트, 사용자, 장치 또는 기타 엔터티 유형을 검사 하는 인시던트를 조사 하는 것을 빠르게 피벗 합니다.

## <a name="june-2020"></a>2020년 6월
- Twitter 피드 <br> 대시보드 내에서 최신 보안 연구, 위협 인텔리전스, 제품 소식 등을 확인 하세요.
- [EmailPostDeliveryEvents schema 테이블](advanced-hunting-emailpostdeliveryevents-table.md) <br> 고급 구하기 쿼리의 전자 메일 메시지에 대해 수행 된 배달 후 작업에 대 한 정보를 통합 합니다.
- [고급 구하기에서 레코드 검사](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 새 세부 정보 패널을 사용 하 여 쿼리 결과의 레코드를 빠르게 검사 합니다.

## <a name="may-2020"></a>2020년 5월
- [사용자 지정 검색](custom-detections-overview.md) <br> 고급 검색 쿼리를 사용 하 여 보안 이벤트 및 시스템 상태에 대해 자동으로 모니터링 하 고 응답 하는 사용자 지정 검색 규칙을 만듭니다.

## <a name="february-2020"></a>2020년 2월
- [인시던트](incidents-overview.md) <br> 공격이 시작 된 위치와 공격 범위를 확인 하는 데 도움이 되는 기타 세부 정보를 정확히 파악 합니다.
- [자동화된 조사 및 응답](mtp-autoir.md) <br> AIR을 사용하면 보안 운영팀에서 보안 경고와 인시던트를 처리하는 조직의 용량을 획기적으로 늘릴 수 있습니다.
- [고급 구하기 향상](advanced-hunting-overview.md) <br> 현재 작업 영역에서 Kusto 쿼리 언어 및 보안 최적화 스키마를 통해 위협을 사전에 사냥 합니다.

## <a name="march-2019"></a>2019년 3월
- 고급 헌팅 <br> 전자 메일 및 데이터, 장치 및 id에 영향을 주는 위협을 사전에 찾을 수 있게 해 주는 다양 한 검색 기능에 대 한 랜딩 페이지입니다.
- [Microsoft 보안 점수](microsoft-secure-score.md) <br> 더 많은 향상 작업을 나타내는 더 높은 번호를 사용 하 여 조직의 보안 상황 측정 보안 점수 권장 사항을 따르면 위협 으로부터 조직을 보호할 수 있습니다. 
- [보고서](monitoring-and-reporting.md) <br>  기능은 보안 분석가와 관리자가 일상 작업의 일부로 추적 하는 다양 한 영역을 다루는 카드의 호스트입니다.

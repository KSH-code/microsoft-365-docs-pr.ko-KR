---
title: Microsoft 365 Defender의 새로운 기능
description: Microsoft 365 Defender의 새로운 기능을 나열합니다.
keywords: Microsoft 위협 방지, ga, 일반적으로 사용 가능, 기능, 사용 가능, 새로운 기능의 새로운 기능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932025"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender를 경험하고 싶나요? 랩 [환경에서 평가하거나](https://aka.ms/mtp-trial-lab) 프로덕션 [환경에서 파일럿](https://aka.ms/m365d-pilotplaybook)프로젝트를 실행할 수 있습니다.
>

다음 기능은 Microsoft 365 Defender의 최신 릴리스에서 일반적으로 사용할 수 있습니다(GA).

RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> Microsoft 365 Defender를 경험하고 싶나요? 랩 [환경에서](https://aka.ms/mtp-trial-lab) 평가하거나 프로덕션 환경에서 파일럿 프로젝트를 [실행할 수 있습니다.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="september-2020"></a>2020년 9월
- [IdentityDirectoryEvents 테이블](advanced-hunting-identitydirectoryevents-table.md) <br> AD(Active Directory)를 실행하는 On-프레미스 도메인 컨트롤러와 관련된 이벤트를 검색합니다. 이 [고급 헌팅](advanced-hunting-overview.md) 체계표에는 도메인 컨트롤러의 다양한 ID 관련 이벤트 및 시스템 이벤트가 포함됩니다.
- [AssignedIPAddresses() 함수](advanced-hunting-assignedipaddresses-function.md) <br> 고급 헌팅 쿼리에서 이 기능을 사용하여 장치에 할당된 최신 IP 주소 또는 특정 시간의 최신 IP 주소를 빠르게 얻을 수 있습니다.

## <a name="july-2020"></a>2020년 7월
- [FileProfile() 함수](advanced-hunting-fileprofile-function.md) <br> 고급 헌팅 쿼리에서 이 기능을 사용하여 포괄적인 파일 정보로 결과를 향상합니다.
- [ID 및 앱 테이블](advanced-hunting-schema-tables.md)<br> 고급 헌팅 계획에서 [IdentityLogonEvents, IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)및 [AppFileEvents](advanced-hunting-appfileevents-table.md) 테이블을 사용하여 인증 이벤트, Active Directory 쿼리 및 앱 관련 활동을 확인할 수 있습니다. [](advanced-hunting-identityqueryevents-table.md)
- [탐색](advanced-hunting-go-hunt.md)<br> 인시던트 조사에서 고급 헌팅에 대한 특정 이벤트, 사용자, 장치 또는 기타 엔터티 유형을 검사하는 데 신속하게 피벗합니다.

## <a name="june-2020"></a>2020년 6월
- Twitter 피드 <br> 대시보드 내에서 최신 보안 연구, 위협 인텔리전스, 제품 뉴스 등 자세한 정보를 얻을 수 있습니다.
- [EmailPostDeliveryEvents schema 테이블](advanced-hunting-emailpostdeliveryevents-table.md) <br> 고급 헌팅 쿼리에서 전자 메일 메시지에 대해 수행된 배달 후 작업에 대한 정보를 통합합니다.
- [고급 헌팅의 레코드 검사](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 새 세부 정보 패널을 사용하여 쿼리 결과의 레코드를 빠르게 검사합니다.

## <a name="may-2020"></a>2020년 5월
- [사용자 지정 검색](custom-detections-overview.md) <br> 고급 헌팅 쿼리를 사용하여 보안 이벤트 및 시스템 상태의 자동 모니터링 및 응답을 하는 사용자 지정 검색 규칙을 만들 수 있습니다.

## <a name="february-2020"></a>2020년 2월
- [인시던트](incidents-overview.md) <br> 공격이 시작된 위치와 공격의 범위를 보는 데 도움이 되는 기타 세부 정보를 정확하게 알 수 있습니다.
- [자동화된 조사 및 응답](mtp-autoir.md) <br> AIR을 사용하면 보안 운영팀에서 보안 경고와 인시던트를 처리하는 조직의 용량을 획기적으로 늘릴 수 있습니다.
- [고급 헌팅 기능 향상](advanced-hunting-overview.md) <br> Kusto 쿼리 언어 및 보안 최적화된 스마마를 사용하여 최신 작업 영역의 위협을 사전 예방적으로 헌팅합니다.

## <a name="march-2019"></a>2019년 3월
- 고급 헌팅 <br> 전자 메일 및 데이터, 장치 및 ID에 영향을 주는 위협을 능동적으로 찾을 수 있는 다양한 헌팅 기능에 대한 방문 페이지입니다.
- [Microsoft 보안 점수](microsoft-secure-score.md) <br> 개선 작업이 더 많이 수행되었음을 나타내는 수치가 높은 조직의 보안 자세를 측정합니다. 보안 점수 권장 사항을 따라 조직을 위협으로부터 보호할 수 있습니다. 
- [보고서](monitoring-and-reporting.md) <br>  보안 분석가와 관리자가 매일 작업의 일부로 추적하는 다양한 영역을 다루는 카드 호스트를 제공합니다.

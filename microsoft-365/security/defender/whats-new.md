---
title: Microsoft 365 Defender의 새로운 기능
description: 새 기능을 나열합니다Microsoft 365 Defender
keywords: Microsoft 365 Defender, ga, 일반적으로 사용 가능, 기능, 사용 가능, 새로운 기능의 새로운 기능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ca008206e30b6e7d13638379322238d3bb7b79d6
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58256659"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender를 경험해 보고 싶으신가요? [랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

다음 기능은 일반적으로 최신 버전의 GA(Ga)에서 사용할 수 Microsoft 365 Defender.

RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```
## <a name="august-2021"></a>2021년 8월
- (미리 보기) 고급 헌팅에서 사용할 Office 365 Microsoft Defender for Office 365 데이터
<br>전자 메일 테이블의 새 열을 통해 고급 헌팅을 사용하여 보다 철저한 조사를 위해 전자 메일 기반 위협에 대한 더 많은 정보를 얻을 수 있습니다. 이제 `AuthenticationDetails` [EmailEvents](./advanced-hunting-emailevents-table.md), `FileSize` [EmailAttachmentInfo](./advanced-hunting-emailattachmentinfo-table.md)및 `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents](./advanced-hunting-emailpostdeliveryevents-table.md) 테이블에 열을 포함할 수 있습니다. 

## <a name="july-2021"></a>2021년 7월
- [Professional 서비스 카탈로그](https://sip.security.microsoft.com/interoperability/professional_services)<br>지원되는 파트너 연결을 사용하여 플랫폼의 검색, 조사 및 위협 인텔리전스 기능을 향상합니다.
    

## <a name="may-2021"></a>2021년 5월

- [Microsoft 365 Defender 포털의 새 경고 페이지](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> 공격에 대한 컨텍스트에 대한 향상된 정보를 제공합니다. 현재 경고를 유발한 다른 트리거된 경고와 파일, 사용자 및 사서함을 포함하여 공격에 관련된 모든 엔터티 및 활동을 볼 수 있습니다. 자세한 [내용은 경고 조사를](/microsoft-365/security/defender/investigate-alerts) 참조하세요.
- [추세 포털의 인시던트 및 경고에 대한 Microsoft 365 Defender 그래프](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> 단일 인시던트에 대한 여러 경고가 있는지 또는 조직이 여러 다른 인시던트로 공격을 당하고 있는지를 파악합니다. 자세한 [내용은 인시던트 우선](/microsoft-365/security/defender/incident-queue) 순위 지정을 참조하세요.


## <a name="april-2021"></a>2021년 4월
- Microsoft 365 Defender<br> 이제 [향상된](https://security.microsoft.com) Microsoft 365 Defender 포털을 사용할 수 있습니다. 이 새로운 환경은 Endpoint용 Defender, Office 365, ID용 Defender 등 여러 정보를 단일 포털로 통합합니다. 보안 제어를 관리하는 새로운 홈입니다. [새로운 기능에 대해 알아보세요](./overview-security-center.md).

- [Microsoft 365 Defender 위협 분석 보고서](threat-analytics.md)<br>
 위협 분석을 사용하면 활성 공격에 대응하고 영향을 최소화할 수 있습니다. 또한 솔루션 솔루션에 의해 차단되는 공격 시도에 대해 Microsoft 365 Defender 추가 노출 및 탄력성 증가 위험을 완화하는 예방 조치를 취할 수 있습니다. 통합 보안 환경의 일부로, 이제 Microsoft Defender for Endpoint 및 Microsoft Defender for Office 사용할 수 있습니다.

## <a name="march-2021"></a>2021년 3월
- [CloudAppEvents 테이블](advanced-hunting-cloudappevents-table.md) <br>다양한 클라우드 앱 및 서비스에서 이벤트에 대한 정보를 Microsoft Cloud App Security. 이 표에는 이전에 에서 사용 가능한 정보도 포함되어 `AppFileEvents` 있습니다.
## <a name="february-2021"></a>2021년 2월
- (미리 보기) 향상된 Microsoft 365 Defender [ https://security.microsoft.com) 포털(이제](https://security.microsoft.com) 공개 미리 보기에서 사용할 수 있습니다. 이 새로운 환경은 끝점용 Defender와 중앙에 Office 365 Defender를 제공합니다. [변경 사항에 대한 자세한 정보](./overview-security-center.md).

## <a name="september-2020"></a>2020년 9월
- [IdentityDirectoryEvents 테이블](advanced-hunting-identitydirectoryevents-table.md) <br> AD(Active Directory)를 실행하는 사내 도메인 컨트롤러와 관련된 이벤트를 검색합니다. 이 [고급 헌팅](advanced-hunting-overview.md) 체계표에는 도메인 컨트롤러의 ID 관련 이벤트 및 시스템 이벤트가 포함됩니다.
- [AssignedIPAddresses() 함수](advanced-hunting-assignedipaddresses-function.md) <br> 고급 헌팅 쿼리에서 이 기능을 사용하여 장치에 할당된 최신 IP 주소 또는 특정 시간의 최신 IP 주소를 빠르게 얻을 수 있습니다.

## <a name="july-2020"></a>2020년 7월
- [FileProfile() 함수](advanced-hunting-fileprofile-function.md) <br> 고급 헌팅 쿼리에서 이 함수를 사용하여 포괄적인 파일 정보로 결과를 향상합니다.
- [ID 및 앱 테이블](advanced-hunting-schema-tables.md)<br> 고급 헌팅 계획의 [IdentityLogonEvents, IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)및 [AppFileEvents](advanced-hunting-appfileevents-table.md) 테이블을 사용하여 인증 이벤트, Active Directory 쿼리 및 앱 관련 활동을 확인할 수 있습니다. [](advanced-hunting-identityqueryevents-table.md)
- [탐색](advanced-hunting-go-hunt.md)<br> 인시던트 조사에서 고급 헌팅에 대한 특정 이벤트, 사용자, 장치 또는 기타 엔터티 유형을 검사하는 데 빠르게 피벗합니다.

## <a name="june-2020"></a>2020년 6월
- Twitter 피드 <br> 대시보드 내에서 최신 보안 연구, 위협 인텔리전스, 제품 뉴스 등 정보를 얻을 수 있습니다.
- [EmailPostDeliveryEvents schema 테이블](advanced-hunting-emailpostdeliveryevents-table.md) <br> 고급 헌팅 쿼리에서 전자 메일 메시지에 대해 수행된 배달 후 작업에 대한 정보를 통합합니다.
- [고급 헌팅의 레코드 검사](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 새 세부 정보 패널을 사용하여 쿼리 결과의 레코드를 빠르게 검사합니다.

## <a name="may-2020"></a>2020년 5월
- [사용자 지정 검색](custom-detections-overview.md) <br> 고급 헌팅 쿼리를 사용하여 보안 이벤트 및 시스템 상태의 모니터링 및 응답을 자동으로 모니터링하는 사용자 지정 검색 규칙을 만들 수 있습니다.

## <a name="february-2020"></a>2020년 2월
- [인시던트](incidents-overview.md) <br> 공격이 시작된 위치와 공격 범위를 보는 데 도움이 되는 기타 세부 정보를 정확하게 알 수 있습니다.
- [자동화된 조사 및 응답](m365d-autoir.md) <br> AIR을 사용하면 보안 운영팀에서 보안 경고와 인시던트를 처리하는 조직의 용량을 획기적으로 늘릴 수 있습니다.
- [고급 헌팅 기능 향상](advanced-hunting-overview.md) <br> Kusto 쿼리 언어 및 보안 최적화된chema를 사용하여 최신 작업 영역의 위협을 사전 예방적으로 헌팅합니다.

## <a name="march-2019"></a>2019년 3월
- 고급 헌팅 <br> 전자 메일 및 데이터, 장치 및 ID에 영향을 주는 위협을 사전 대응적으로 찾을 수 있는 다양한 헌팅 기능에 대한 방문 페이지입니다.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> 조직의 보안 자세 측정값으로, 수치가 높을수록 개선 작업이 더 많이 수행됩니다. 보안 점수 권장 사항을 따르면 조직을 위협으로부터 지킬 수 있습니다. 
- [보고서](overview-security-center.md) <br>  보안 분석가와 관리자가 매일 작업의 일부로 추적하는 다양한 영역을 다루는 카드 호스트를 제공합니다.

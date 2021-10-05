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
ms.openlocfilehash: 5ebd798baa9b9c4fb759defbf0a650d4835568b8
ms.sourcegitcommit: d1eb1c26609146ff5a59b2a1b005dd7ac43ae64e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60099792"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender의 새로운 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender를 경험하고 싶으신가요? [실험실 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

다음 기능은 미리 보기에 제공되거나 최신 릴리스의 GA(일반 사용 가능)에 Microsoft 365 Defender.

RSS 피드: 다음 URL을 복사하여 피드 읽기에 붙여 넣는 방법을 통해 이 페이지가 업데이트될 때 알림을 받을 수 있습니다.
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

다른 Microsoft Defender 보안 제품과 함께 새로운 제품에 대한 자세한 내용은 다음을 참조하세요.

- [Microsoft Defender for Office 365](../office-365-security/whats-new-in-defender-for-office-365.md)
- [엔드포인트용 Microsoft Defender의 새로운 기능](../defender-endpoint/whats-new-in-microsoft-defender-atp.md)
- [ID용 Microsoft Defender의 새로운](/defender-for-identity/whats-new)
- [새로운 Microsoft Cloud App Security](/cloud-app-security/release-notes)



## <a name="september-2021"></a>2021년 9월
- (GA) Microsoft Defender for Office 365 이벤트 데이터는 Microsoft 365 Defender 스트리밍 API에서 사용할 수 있습니다. 스트리밍 API의 Supported Microsoft 365 Defender 이벤트 유형에서 이벤트 [유형의 가용성과 상태를](supported-event-types.md)확인할 수 있습니다.
- (GA) Microsoft Defender for Office 365 고급 헌팅에서 사용할 수 있는 데이터를 이제 일반적으로 사용할 수 있습니다.
- (미리 보기) 사용자 계정에 인시던트 및 경고 할당 <br> 인시던트 및 인시던트와 관련된 모든 경고를 할당에서 사용자 계정에  할당할 수 **있습니다.**  인시던트의 인시던트 관리 창 또는 경고의 경고 관리 창에 할당할 수 있습니다.


## <a name="august-2021"></a>2021년 8월
- (미리 보기) 고급 헌팅에서 사용할 Office 365 Microsoft Defender for Office 365 데이터
<br>전자 메일 테이블의 새 열을 통해 고급 헌팅을 사용하여 보다 철저한 조사를 위해 전자 메일 기반 위협에 대한 더 많은 정보를 얻을 수 있습니다. 이제 `AuthenticationDetails` [EmailEvents](./advanced-hunting-emailevents-table.md), `FileSize` [EmailAttachmentInfo](./advanced-hunting-emailattachmentinfo-table.md)및 `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents](./advanced-hunting-emailpostdeliveryevents-table.md) 테이블에 열을 포함할 수 있습니다. 

- (미리 보기) 인시던트 그래프 <br>  인시던트의 요약 **탭에** 있는 새로운 Graph 탭에는 공격의 전체 범위, 공격이 시간의에 따라 네트워크를 통해 확산되는 방법, 공격이 시작된 위치 및 공격자가 얼마나 이동한 거리가 표시됩니다. 

## <a name="july-2021"></a>2021년 7월
- [Professional 서비스 카탈로그](https://sip.security.microsoft.com/interoperability/professional_services)<br>지원되는 파트너 연결을 사용하여 플랫폼의 검색, 조사 및 위협 인텔리전스 기능을 향상합니다.

## <a name="june-2021"></a>2021년 6월
- (미리 보기) [위협 태그당 보고서 보기](threat-analytics.md#view-reports-per-threat-tags)<br> 위협 태그를 사용하면 특정 위협 범주에 집중하고 가장 관련성이 높은 보고서를 검토할 수 있습니다.
- (미리 보기) [스트리밍 API](../defender-endpoint/raw-data-export.md)<br> Microsoft 365 Defender 고급 헌팅을 통해 사용할 수 있는 모든 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍할 수 있습니다.
- (미리 보기) [고급 헌팅에 대한 작업 수행](advanced-hunting-take-action.md)<br> 고급 헌팅에서 찾은 위협을 빠르게 포함하거나 손상된 자산을 [해결합니다.](advanced-hunting-overview.md)
- (미리 보기) [포털 내 Schema 참조](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)<br> 보안 센터에서 직접 고급 헌팅 스마 테이블에 대한 정보를 얻습니다. 테이블 및 열 설명 외에도 이 참조에는 지원되는 이벤트 유형(값) 및 `ActionType` 예제 쿼리가 포함됩니다.
- (미리 보기) [DeviceFromIP() 함수](advanced-hunting-devicefromip-function.md)<br> 지정된 시간 범위에서 특정 IP 주소 또는 주소가 할당된 장치에 대한 정보를 얻습니다.
    

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
- **[(미리 보기) Microsoft 365 Defender](api-overview.md)** API - 최상위 Microsoft 365 Defender API를 사용하면 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화할 수 있습니다. 

---
title: 이동 헌트를 사용 하 여 엔터티에 대 한 관련 정보 가져오기
description: "\"이동 헌트\" 도구를 사용 하 여 고급 검색을 사용 하는 엔터티나 이벤트에 대 한 관련 정보를 빠르게 쿼리 하는 방법을 알아봅니다."
keywords: 고급 구하기, 인시던트, 피벗, 엔터티, 이동 헌트, 관련 이벤트, 위협 요소 찾기, 사이버 위협 구하기, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: b9afecb3d0efce93ae5d5725bba71d8d9719d17f
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430414"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>이동 헌트로 엔터티나 이벤트 정보를 빠르게 사냥

**적용 대상:**
- Microsoft 위협 방지

*이동 헌트* 작업을 사용 하면 강력한 쿼리 기반 [고급 구하기](advanced-hunting-overview.md) 기능을 사용 하 여 이벤트 및 다양 한 엔터티 유형을 빠르게 조사할 수 있습니다. 이 작업을 수행 하면 고급 검색 쿼리를 자동으로 실행 하 여 선택한 이벤트 또는 엔터티에 대 한 관련 정보를 찾습니다.

*이동 헌트* 작업은 이벤트 또는 엔터티 세부 정보가 표시 될 때마다 보안 센터의 여러 섹션에서 사용할 수 있습니다. 예를 들어 다음 섹션의 *이동 헌트* 를 사용할 수 있습니다.

- 인시던트 [페이지](investigate-incidents.md#incident-overview)에서 문제와 관련 된 사용자, 장치 및 기타 여러 엔터티에 대 한 세부 정보를 검토할 수 있습니다. 엔터티를 선택 하면 해당 entitity에 대해 수행할 수 있는 다양 한 작업 뿐만 아니라 추가 정보도 제공 됩니다. 아래 예에서 사서함에 대 한 세부 정보 및 사서함에 대 한 자세한 정보를 사냥 하기 위한 옵션을 보여 주는 사서함이 선택 됩니다.

    ![이동 헌트 옵션을 사용 하 여 사서함 세부 정보를 보여 주는 이미지](../../media/mtp-ah/go-hunt-email.png)

- 인시던트 페이지에서 증거 탭 아래의 엔터티 목록에 액세스할 수도 있습니다. 이러한 엔터티 중 하나를 선택 하면 해당 엔터티에 대 한 정보를 빠르게 검색할 수 있는 옵션이 제공 됩니다.

    ![증거 탭의 이동 헌트 옵션을 사용 하 여 선택한 파일을 보여 주는 이미지](../../media/mtp-ah/go-hunt-evidence-file.png)


- 장치에 대 한 시간 표시줄을 볼 때 시간 표시 막대에서 이벤트를 선택 하 여 해당 이벤트에 대 한 추가 정보를 볼 수 있습니다. 이벤트가 선택 되 면 고급 구하기에서 기타 관련 이벤트를 찾을 수 있는 옵션이 제공 됩니다.

    ![이동 헌트 옵션을 사용한 이벤트 세부 정보를 보여 주는 이미지](../../media/mtp-ah/go-hunt-event.png)

엔터티 또는 이벤트를 선택 했는지에 따라, **관련 이벤트에 대 한** **찾기** 또는 헌트 선택이 서로 다른 쿼리를 통과 합니다.

## <a name="query-for-entity-information"></a>엔터티 정보 쿼리
*Go* to를 사용 하 여 사용자, 장치 또는 다른 유형의 엔터티에 대 한 정보를 쿼리할 때 쿼리는 해당 엔터티와 관련 된 모든 이벤트에 대 한 관련 스키마 테이블을 모두 확인 합니다. 결과를 관리 가능 하 게 유지 하기 위해 쿼리는 지난 30 일 동안의 해당 엔터티와 관련 된 가장 빠른 작업과 해당 인시던트에 연결 되는 것과 같은 기간으로 범위가 지정 됩니다.

다음은 장치에 대 한 이동 헌트 쿼리의 예입니다.

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>지원 되는 엔터티 유형
다음 엔터티 유형을 선택한 후 *이동 헌트* 를 사용할 수 있습니다.

- 파일
- 전자 메일
- 전자 메일 클러스터
- 사서함
- 사용자
- 장치
- IP 주소
- URL

## <a name="query-for-event-information"></a>이벤트 정보 쿼리
*To 헌트* 을 사용 하 여 시간 표시 막대 이벤트에 대 한 정보를 쿼리할 때 쿼리는 선택한 이벤트의 시간에 관련 된 다른 이벤트에 대 한 해당 하는 모든 스키마 테이블을 확인 합니다. 예를 들어 다음 쿼리는 동일한 장치에서 같은 기간에 발생 한 다양 한 스키마 테이블의 이벤트를 나열 합니다.

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>쿼리 조정
[쿼리 언어](advanced-hunting-query-language.md)에 대 한 일부 지식이 있으면 원하는 대로 쿼리를 조정할 수 있습니다. 예를 들어 시간 창의 크기를 결정 하는 다음 줄을 조정할 수 있습니다.

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

보다 관련성이 높은 결과를 얻기 위해 쿼리를 수정 하는 것 외에 다음과 같은 작업도 수행할 수 있습니다.
- [결과를 차트로 보기](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [사용자 지정 검색 규칙 만들기](custom-detection-rules.md)

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [사용자 지정 검색 규칙](custom-detection-rules.md)
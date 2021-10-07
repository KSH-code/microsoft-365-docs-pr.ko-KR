---
title: 할당된 사용자에 대한 고급 헌팅의 AssignedIPAddresses() Microsoft 365 Defender
description: AssignedIPAddresses() 함수를 사용하여 장치에 할당된 최신 IP 주소를 다운로드하는 방법을 학습합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, FileProfile, 파일 프로필, 기능, 향상
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 48dda6faf9d0cfc5b301a766dd07f8cb4e15d394
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174558"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅 쿼리의 기능을 사용하여 장치에 할당된 최신 IP 주소를 빠르게 `AssignedIPAddresses()` 얻습니다. [](advanced-hunting-overview.md) 타임스탬프 인수를 지정하면 이 함수는 지정된 시간의 가장 최근 IP 주소를 얻습니다. 

이 함수는 다음 열이 있는 표를 반환합니다.

| 열 | 데이터 형식 | 설명 |
|------------|-------------|-------------|
| `Timestamp` | datetime | IP 주소를 사용하여 장치가 관찰된 최신 시간 |
| `IPAddress` | 문자열 | 장치에서 사용하는 IP 주소 |
| `IPType` | 문자열 | IP 주소가 공용 주소인지 개인 주소인지를 나타냅니다. |
| `NetworkAdapterType` | int | IP 주소가 할당된 장치에서 사용하는 네트워크 어댑터 유형입니다. 가능한 값은 이 [열거를 참조하세요.](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 할당된 IP 주소가 있는 어댑터가 연결된 네트워크입니다. 각 JSON 배열에는 네트워크 이름, 범주(공용, 개인 또는 도메인), 설명 및 인터넷에 공개적으로 연결되어 있는지를 나타내는 플래그가 포함되어 있습니다. |

## <a name="syntax"></a>구문

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>인수

- **x**- `DeviceId` `DeviceName` 또는 디바이스를 식별하는 값
- **y**- (datetime) 특정 시간에서 가장 최근에 할당된 IP 주소를 구하도록 `Timestamp` 함수에 지시하는 값입니다. 지정하지 않으면 함수는 최신 IP 주소를 반환합니다.

## <a name="examples"></a>예

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>24시간 전 디바이스에서 사용하는 IP 주소 목록 표시

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>장치에서 사용하는 IP 주소를 찾고 장치와 통신하는 장치 찾기
이 쿼리는 함수를 사용하여 특정 날짜()에 또는 그 이전의 디바이스에 할당된 `AssignedIPAddresses()` IP 주소()를 `example-device-name` `example-date` 얻습니다. 그런 다음 IP 주소를 사용하여 다른 장치에서 시작한 디바이스에 대한 연결을 확인합니다. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
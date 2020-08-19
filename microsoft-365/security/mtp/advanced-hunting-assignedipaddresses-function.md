---
title: Microsoft Threat Protection에 대 한 고급 구하기의 AssignedIPAddresses () 함수
description: AssignedIPAddresses () 함수를 사용 하 여 장치에 할당 된 최신 IP 주소를 가져오는 방법에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, FileProfile, file profile, function, 향상
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
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794234"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`AssignedIPAddresses()`장치에 할당 된 최신 ip 주소 또는 지정 된 시점에서 가장 최근 ip 주소를 빠르게 가져오려면이 함수를 사용 합니다. 이 함수는 다음과 같은 열이 있는 table을 반환 합니다.

| 열 | 데이터 형식 | 설명 |
|------------|-------------|-------------|
| 타임 스탬프 | datetime | IP 주소를 사용 하 여 장치를 확인 한 최근 시간 |
| IPAddress | 문자열 | 장치에서 사용 하는 IP 주소 |
| IPType | 문자열 | IP 주소가 공용 또는 개인 주소 인지 여부를 나타냅니다. |
| NetworkAdapterType | int | IP 주소가 할당 된 장치에서 사용 하는 네트워크 어댑터 유형입니다. 가능한 값은 [this 열거형](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) 을 참조 하십시오.  |
| ConnectedNetworks | int | 할당 된 IP 주소가 있는 어댑터가 연결 되는 네트워크입니다. 각 JSON 배열에는 네트워크 이름, 범주 (공용, 개인 또는 도메인), 설명 및 공용이 인터넷에 연결 되어 있는지 여부를 나타내는 플래그가 포함 됩니다. |


## <a name="syntax"></a>구문과

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>인수나

- **x** - `DeviceId` `DeviceName` 장치를 식별 하는 값입니다.
- **y** - `Timestamp` (datetime) 가장 최근 IP 주소를 가져올 특정 시점을 나타내는 값입니다. 이를 지정 하지 않으면이 함수는 최신 IP 주소를 반환 합니다.

## <a name="examples"></a>예

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a>24 시간 전 장치에서 사용 하는 IP 주소 목록 가져오기

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>장치에서 사용 하는 IP 주소 가져오기 및 it와 통신 하는 장치 찾기
이 쿼리는 함수를 사용 하 여 `AssignedIPAddresses()` `example-device-name` 특정 날짜 또는 그 이전에 장치에 할당 된 IP 주소를 가져옵니다 `example-date` . 그런 다음 IP 주소를 사용 하 여 다른 장치가 시작한 장치에 대 한 연결을 찾습니다. 

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
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
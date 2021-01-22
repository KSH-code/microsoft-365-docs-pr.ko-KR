---
title: Microsoft 365 Defender에 대한 고급 헌팅의 DeviceFromIP() 기능
description: DeviceFromIP() 함수를 사용하여 특정 IP 주소가 할당된 디바이스를 구하는 방법을 학습
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931305"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


고급 헌팅 쿼리의 기능을 사용하여 지정된 시점에 특정 IP 주소에 할당된 장치 목록을 빠르게 `DeviceFromIP()` 얻을 수 있습니다. [](advanced-hunting-overview.md) 

이 함수는 다음 열이 있는 표를 반환합니다.

| 열 | 데이터 형식 | 설명 |
|------------|-------------|-------------|
| `IP` | 문자열 | IP 주소  |
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |


## <a name="syntax"></a>구문

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>인수

이 함수는 쿼리의 일부로 호출됩니다.

- **x**-첫 번째 매개 변수는 일반적으로 이미 쿼리의 열입니다. 이 경우 이 열은 할당된 장치 목록을 보게 할 IP 주소라는 `IP` 열입니다. 로컬 IP 주소입니다. 외부 IP 주소는 지원되지 않습니다.
- **y**- 두 번째 선택적 매개 변수는 함수가 특정 시간에서 가장 최근에 할당된 디바이스를 `Timestamp` 구하도록 지시하는 매개 변수입니다. 이 함수를 지정하지 않으면 사용 가능한 최신 레코드가 반환됩니다.

## <a name="example"></a>예시


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>특정 IP 주소가 할당된 최신 장치 다운로드

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)

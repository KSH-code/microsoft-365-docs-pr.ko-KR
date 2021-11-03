---
title: 디바이스에 대한 고급 헌팅의 DeviceFromIP() Microsoft 365 Defender
description: DeviceFromIP() 함수를 사용하여 특정 IP 주소가 할당된 디바이스를 사용하는 방법을 학습
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 장치, devicefromIP, 기능, 향상
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c2482c83eef315c390e2748e371ddf26dcb3c012
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60705354"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


고급 헌팅 쿼리의 기능을 사용하여 지정된 시점에 특정 IP 주소에 할당된 장치 목록을 빠르게 얻을 `DeviceFromIP()` 수 있습니다. [](advanced-hunting-overview.md) 

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

- **x**-첫 번째 매개 변수는 일반적으로 이미 쿼리의 열입니다. 이 경우 이 열은 이라는 열로, 할당된 장치 목록을 보게 할 `IP` IP 주소입니다. 로컬 IP 주소입니다. 외부 IP 주소는 지원되지 않습니다.
- **y**-두 번째 선택적 매개 변수는 이며, 이 매개 변수는 특정 시간에서 가장 최근에 할당된 장치를 구하도록 `Timestamp` 함수에 지시합니다. 이 함수를 지정하지 않으면 사용 가능한 최신 레코드가 반환됩니다.

## <a name="example"></a>예시


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>특정 IP 주소가 할당된 최신 장치 다운로드

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)

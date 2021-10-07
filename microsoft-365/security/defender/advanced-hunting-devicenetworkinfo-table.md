---
title: 고급 헌팅chema의 DeviceNetworkInfo 테이블
description: 고급 헌팅 schema의 DeviceNetworkInfo 표에서 네트워크 구성 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, machinenetworkinfo, DeviceNetworkInfo, 장치, 컴퓨터, mac, ip, 어댑터, dns, dhcp, 게이트웨이, 터널
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
ms.openlocfilehash: 5b7bd42a8d9cbfd93a45d36a8236fb858eeb0436
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209252"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender



고급 `DeviceNetworkInfo` 헌팅 schema의 표에는 네트워크 어댑터, IP 및 MAC 주소, 연결된 네트워크 또는 도메인을 비롯한 컴퓨터의 네트워킹 구성에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `NetworkAdapterName` | 문자열 | 네트워크 어댑터의 이름 |
| `MacAddress` | 문자열 | 네트워크 어댑터의 MAC 주소 |
| `NetworkAdapterType` | 문자열 | 네트워크 어댑터 유형입니다. 가능한 값은 이 [열거를 참조하세요.](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `NetworkAdapterStatus` | 문자열 | 네트워크 어댑터의 작동 상태입니다. 가능한 값은 이 [열거를 참조하세요.](/dotnet/api/system.net.networkinformation.operationalstatus) |
| `TunnelType` | 문자열 | 터널링 프로토콜( 인터페이스가 이 용도로 사용되는 경우(예: 6to4, Teredo, ISATAP, PPTP, SSTP 및 SSH) |
| `ConnectedNetworks` | 문자열 | 어댑터가 연결된 네트워크입니다. 각 JSON 배열에는 네트워크 이름, 범주(공용, 개인 또는 도메인), 설명 및 인터넷에 공개적으로 연결되어 있는지를 나타내는 플래그가 포함되어 있습니다. |
| `DnsAddresses` | 문자열 | JSON 배열 형식의 DNS 서버 주소 |
| `IPv4Dhcp` | 문자열 | DHCP 서버의 IPv4 주소 |
| `IPv6Dhcp` | 문자열 | DHCP 서버의 IPv6 주소 |
| `DefaultGateways` | 문자열 | JSON 배열 형식의 기본 게이트웨이 주소 |
| `IPAddresses` | 문자열 | 어댑터에 할당된 모든 IP 주소와 해당 서브넷 접두사 및 IP 주소 공간(예: 공용, 개인 또는 링크 로컬)을 포함하는 JSON 배열 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
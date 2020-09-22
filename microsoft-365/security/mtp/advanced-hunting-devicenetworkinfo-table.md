---
title: 고급 구하기 스키마의 DeviceNetworkInfo 테이블
description: 고급 구하기 스키마의 DeviceNetworkInfo 테이블에 있는 네트워크 구성 정보에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, 어댑터, dns, dhcp, 게이트웨이, 터널
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
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197076"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지



`DeviceNetworkInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 네트워크 어댑터, IP 및 MAC 주소, 연결 된 네트워크 또는 도메인을 비롯 하 여 컴퓨터의 네트워킹 구성에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다. |
| `NetworkAdapterName` | 문자열 | 네트워크 어댑터의 이름입니다. |
| `MacAddress` | 문자열 | 네트워크 어댑터의 MAC 주소 |
| `NetworkAdapterType` | 문자열 | 네트워크 어댑터 유형입니다. 가능한 값은 [this 열거형](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) 을 참조 하십시오. |
| `NetworkAdapterStatus` | 문자열 | 네트워크 어댑터의 작동 상태입니다. 가능한 값은 [this 열거형](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) 을 참조 하십시오. |
| `TunnelType` | 문자열 | 인터페이스를이 용도로 사용 하는 경우 (예: 6to4, Teredo, ISATAP, PPTP, SSTP 및 SSH) 터널링 프로토콜 |
| `ConnectedNetworks` | 문자열 | 어댑터가 연결 되는 네트워크입니다. 각 JSON 배열에는 네트워크 이름, 범주 (공용, 개인 또는 도메인), 설명 및 공용이 인터넷에 연결 되어 있는지 여부를 나타내는 플래그가 포함 됩니다. |
| `DnsAddresses` | 문자열 | JSON 배열 형식의 DNS 서버 주소 |
| `IPv4Dhcp` | 문자열 | DHCP 서버의 IPv4 주소 |
| `IPv6Dhcp` | 문자열 | DHCP 서버의 IPv6 주소 |
| `DefaultGateways` | 문자열 | JSON 배열 형식의 기본 게이트웨이 주소 |
| `IPAddresses` | 문자열 | 해당 하는 서브넷 접두사와 IP 주소 공간 (예: 공용, 개인 또는 링크 로컬)과 함께 어댑터에 할당 된 모든 IP 주소를 포함 하는 JSON 배열 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

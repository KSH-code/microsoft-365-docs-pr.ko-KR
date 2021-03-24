---
title: 고급 헌팅chema의 AppFileEvents 테이블
description: 고급 헌팅 계획의 AppFileEvents 표에서 클라우드 앱 및 서비스와 관련된 파일 관련 이벤트에 대해 자세히 알아보시고
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, AppFileEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071639"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅 계획의 표에는 Microsoft Cloud App Security에서 모니터링하는 클라우드 앱 및 서비스의 파일 관련 활동에 대한 `AppFileEvents` 정보가 포함되어 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!WARNING]
>이 테이블은 곧 사용 중지될 예정입니다. 2021년 3월 7일 현재 테이블은 더 이상 `AppFileEvents` 기록되지 않습니다. 클라우드 서비스에서 파일 관련 활동을 찾은 사용자는 클라우드 서비스에서 해당 날짜 이상을 찾기 위해 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 테이블을 대신 사용해야 합니다. <br><br>테이블을 계속 사용하는 쿼리 및 사용자 지정 검색 규칙을 검색하고 테이블을 사용하여 `AppFileEvents` 편집해야 `CloudAppEvents` 합니다. 영향을 받는 쿼리를 변환하는 방법에 대한 자세한 지침은 [Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)고급 헌팅을 사용하여 클라우드 앱 활동에서 헌트에서 찾을 수 있습니다.


고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동의 유형입니다. 자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다. |
| `Application` | 문자열 | 기록된 작업을 수행한 응용 프로그램 |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FolderPath` | 문자열 | 기록된 작업이 적용된 파일이 들어 있는 폴더 |
| `PreviousFileName` | 문자열 | 작업의 결과로 이름이 변경된 파일의 원래 이름입니다. |
| `PreviousFolderPath` | 문자열 | 기록된 작업이 적용되기 전 파일이 들어 있는 원본 폴더 |
| `Protocol` | 문자열 | 사용된 네트워크 프로토콜 |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `AccountObjectId` | 문자열 | Azure AD에서 계정의 고유 식별자 |
| `AccountDisplayName` | 문자열 | 주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `DeviceType` | 문자열 | 디바이스 유형 | 
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `IPAddress` | 문자열 | 끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소 |
| `Port` | 문자열 | 통신 중에 사용되는 TCP 포트  |
| `DestinationDeviceName` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다. |
| `DestinationIPAddress` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소 |
| `DestinationPort` | 문자열 | 관련 네트워크 통신의 대상 포트 |
| `Location` | 문자열 | 이벤트와 관련된 도시, 국가 또는 기타 지리적 위치 |
| `Isp` | 문자열 | 끝점 IP 주소와 연결된 ISP(인터넷 서비스 공급자) |
| `ReportId` | long | 이벤트의 고유 식별자 |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대한 추가 정보 |

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.


## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

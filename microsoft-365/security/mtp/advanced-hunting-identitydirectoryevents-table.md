---
title: 고급 구하기 스키마의 IdentityDirectoryEvents 테이블
description: 고급 구하기 스키마의 IdentityDirectoryEvents 테이블에 있는 도메인 컨트롤러 및 Active Directory 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, IdentityDirectoryEvents, 도메인 컨트롤러, Active Directory, Azure ATP, id
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d93ef3eb3bbf6def0f633aa0f69032e37d10c4c9
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430382"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

`IdentityDirectoryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 AD (Active Directory)를 실행 하는 온-프레미스 도메인 컨트롤러 관련 이벤트가 포함 되어 있습니다. 이 테이블은 암호 변경, 암호 만료, UPN (사용자 계정 이름) 변경 등의 다양 한 id 관련 이벤트를 캡처합니다. 또한 작업 예약 및 PowerShell 작업 같은 도메인 컨트롤러에 시스템 이벤트를 캡처합니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 작업의 유형입니다. 자세한 내용은 [portal 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 참조 하세요. |
| `Application` | 문자열 | 기록 된 작업을 수행한 응용 프로그램 |
| `TargetAccountUpn` | 문자열 | 기록 된 작업이 적용 된 계정의 UPN (사용자 계정 이름) |
| `TargetAccountDisplayName` | 문자열 | 기록 된 작업이 적용 된 계정의 표시 이름입니다. |
| `TargetDeviceName` | 문자열 | 기록 된 작업을 적용 한 장치의 FQDN (정규화 된 도메인 이름)입니다. |
| `DestinationDeviceName` | 문자열 | 기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 이름입니다. |
| `DestinationIPAddress` | 문자열 | 기록 된 작업을 처리 한 서버 응용 프로그램을 실행 하는 장치의 IP 주소 |
| `DestinationPort` | 문자열 | 활동의 대상 포트 |
| `Protocol` | 문자열 | 통신 중에 사용 되는 프로토콜 |
| `AccountName` | 문자열 | 계정의 사용자 이름입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountUpn` | 문자열 | 계정의 UPN (사용자 계정 이름) |
| `AccountSid` | 문자열 | 계정의 SID (보안 식별자) |
| `AccountObjectId` | 문자열 | Azure Active Directory의 계정에 대 한 고유 식별자입니다. |
| `AccountDisplayName` | 문자열 | 주소록에 표시 되는 계정 사용자의 이름입니다. 일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `DeviceName` | 문자열 | 장치의 FQDN (정규화 된 도메인 이름) |
| `IPAddress` | 문자열 | 통신 중에 장치에 할당 되는 IP 주소 |
| `Port` | 문자열 | 통신 중에 사용 되는 TCP 포트 |
| `Location` | 문자열 | 이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치 |
| `ISP` | 문자열 | IP 주소와 연결 된 인터넷 서비스 공급자 |
| `ReportId` | long | 이벤트에 대 한 고유 식별자입니다. |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대 한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

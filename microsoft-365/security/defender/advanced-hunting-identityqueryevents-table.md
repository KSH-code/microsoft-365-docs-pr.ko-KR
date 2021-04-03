---
title: 고급 헌팅 스케마의 IdentityQueryEvents 테이블
description: 고급 헌팅 스케마의 IdentityQueryEvents 테이블에서 Active Directory 쿼리 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, ID, LDAP 쿼리
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 40383524ffe26326800369570856499d149e31c3
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500390"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 `IdentityQueryEvents` 헌팅 schema의 표에는 사용자, 그룹, 장치 및 도메인과 같은 Active Directory 개체에 대해 수행되는 쿼리에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동의 유형입니다. 자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다. |
| `Application` | 문자열 | 기록된 작업을 수행한 응용 프로그램 |
| `QueryType` | 문자열 | QueryGroup, QueryUser 또는 EnumerateUsers와 같은 쿼리 유형 |
| `QueryTarget` | 문자열 | 사용자, 그룹, 장치, 도메인 또는 다른 엔터티 유형이 검색되는 이름 |
| `Query` | 문자열 | 쿼리를 실행하는 데 사용되는 문자열 |
| `Protocol` | 문자열 | 통신 중에 사용되는 프로토콜 |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `AccountObjectId` | 문자열 | Azure AD에서 계정의 고유 식별자 |
| `AccountDisplayName` | 문자열 | 주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `DeviceName` | 문자열 | 끝점의 FQDN(FQDN) |
| `IPAddress` | 문자열 | 끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소 |
| `Port` | 문자열 | 통신 중에 사용되는 TCP 포트 |
| `DestinationDeviceName` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다. |
| `DestinationIPAddress` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소 |
| `DestinationPort` | 문자열 | 관련 네트워크 통신의 대상 포트 |
| `TargetDeviceName` | 문자열 | 기록된 작업이 적용된 장치의 FQDN(FQDN) |
| `TargetAccountUpn` | 문자열 | 기록된 작업이 적용된 계정의 UPN(사용자 계정 이름) |
| `TargetAccountDisplayName` | 문자열 | 기록된 작업이 적용된 계정의 표시 이름 |
| `Location` | 문자열 | 이벤트와 관련된 도시, 국가 또는 기타 지리적 위치 |
| `ReportId` | long | 이벤트의 고유 식별자 |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

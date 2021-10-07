---
title: 고급 헌팅Chema의 IdentityDirectoryEvents 테이블
description: 고급 헌팅 구조의 IdentityDirectoryEvents 테이블에서 도메인 컨트롤러 및 Active Directory 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, IdentityDirectoryEvents, 도메인 컨트롤러, Active Directory, ID용 Microsoft Defender, ID
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
ms.openlocfilehash: 40f8804c40236e680543d199e3dc6294fefa1414
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159141"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅 계획의 표에는 AD(Active Directory)를 실행하는 사내 도메인 컨트롤러와 관련된 `IdentityDirectoryEvents` 이벤트가 포함되어 [](advanced-hunting-overview.md) 있습니다. 이 표에서는 암호 변경, 암호 만료 및 UPN(사용자 계정 이름) 변경과 같은 다양한 ID 관련 이벤트를 캡처합니다. 또한 작업 일정 및 PowerShell 활동과 같은 도메인 컨트롤러의 시스템 이벤트를 캡처합니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동의 유형입니다. 자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다. |
| `Application` | 문자열 | 기록된 작업을 수행한 응용 프로그램 |
| `TargetAccountUpn` | 문자열 | 기록된 작업이 적용된 계정의 UPN(사용자 계정 이름) |
| `TargetAccountDisplayName` | 문자열 | 기록된 작업이 적용된 계정의 표시 이름 |
| `TargetDeviceName` | 문자열 | 기록된 작업이 적용된 장치의 FQDN(FQDN) |
| `DestinationDeviceName` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다. |
| `DestinationIPAddress` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소 |
| `DestinationPort` | 문자열 | 활동의 대상 포트 |
| `Protocol` | 문자열 | 통신 중에 사용되는 프로토콜 |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `AccountObjectId` | 문자열 | 계정의 고유 식별자입니다Azure Active Directory |
| `AccountDisplayName` | 문자열 | 주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `IPAddress` | 문자열 | 통신 중 장치에 할당된 IP 주소 |
| `Port` | 문자열 | 통신 중에 사용되는 TCP 포트 |
| `Location` | 문자열 | 이벤트와 관련된 도시, 국가 또는 기타 지리적 위치 |
| `ISP` | 문자열 | IP 주소와 연결된 인터넷 서비스 공급자 |
| `ReportId` | long | 이벤트의 고유 식별자 |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

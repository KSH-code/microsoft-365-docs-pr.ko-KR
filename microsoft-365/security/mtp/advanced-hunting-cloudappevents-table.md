---
title: 고급 구하기 스키마의 CloudAppEvents 테이블
description: 고급 구하기 스키마의 CloudAppEvents 테이블에 있는 클라우드 앱 및 서비스의 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087773"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

현재 미리 보기에서 사용할 수 있는 `CloudAppEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 특히 Microsoft 팀 및 Exchange Online과 같은 다양 한 클라우드 앱 및 서비스의 활동에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

이 테이블은 Microsoft Cloud App Security에서 모니터링 하는 활동을 더 포함 하기 위해 확장 됩니다. 최종적으로이 테이블에는 [Appfileevents](advanced-hunting-appfileevents-table.md) 테이블에 현재 저장 된 파일 활동이 포함 됩니다. Microsoft는이 표로의 데이터 이동에 대 한 추가 지침을 제공 합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 작업의 유형입니다. |
| `Application` | 문자열 | 기록 된 작업을 수행한 응용 프로그램 |
| `ApplicationId` | 문자열 | 응용 프로그램의 고유 식별자입니다. |
| `AccountObjectId` | 문자열 | Azure Active Directory의 계정에 대 한 고유 식별자입니다. |
| `AccountDisplayName` | 문자열 | 주소록에 표시 되는 계정 사용자의 이름입니다. 일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `IsAdminOperation` | 문자열 | 관리자가 활동을 수행 했는지 여부를 나타냅니다. |
| `DeviceType` | 문자열 | 용도 및 기능을 기반으로 하는 장치 유형 (예: "네트워크 장치", "워크스테이션", "서버", "모바일", "게임 콘솔" 또는 "프린터") | 
| `OSPlatform` | 문자열 | 장치에서 실행 되는 운영 체제의 플랫폼입니다. 이 열은 Windows 10 및 Windows 7과 같은 같은 제품군 내의 변형을 비롯 하 여 특정 운영 체제를 나타냅니다. |
| `IPAddress` | 문자열 | 끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소 |
| `IsAnonymousProxy` | 문자열 | IP 주소가 알려진 익명 프록시에 속하는지 여부를 나타냅니다. |
| `CountryCode` | 문자열 | 클라이언트 IP 주소가 geolocated 국가를 나타내는 두 문자로 된 코드입니다. |
| `City` | 문자열 | 클라이언트 IP 주소가 geolocated 구/군/시 |
| `Isp` | 문자열 | IP 주소와 연결 된 ISP (인터넷 서비스 공급자) |
| `UserAgent` | 문자열 | 웹 브라우저나 다른 클라이언트 응용 프로그램의 사용자 에이전트 정보 |
| `ActivityType` | 문자열 | 이벤트를 트리거한 작업의 유형입니다. |
| `ActivityObjects` | 문자열 | 기록 된 활동에 포함 된 파일 또는 폴더 등의 개체 목록 |
| `ObjectName` | 문자열 | 기록 된 작업이 적용 된 개체의 이름입니다. |
| `ObjectType` | 문자열 | 기록 된 작업이 적용 된 파일 또는 폴더와 같은 개체의 유형입니다. |
| `ObjectId` | 문자열 | 기록 된 작업이 적용 된 개체의 고유 식별자입니다. |
| `ReportId` | 문자열 | 이벤트에 대 한 고유 식별자입니다. |
| `RawEventData` | 문자열 | 소스 응용 프로그램 또는 서비스의 원시 이벤트 정보 (JSON 형식) |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대 한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

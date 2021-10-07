---
title: 고급 헌팅Chema의 CloudAppEvents 테이블
description: 고급 헌팅 스위마의 CloudAppEvents 표에 있는 클라우드 앱 및 서비스의 이벤트에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: eff066610d87dd637a861906b8f6a4a4c73ae2ae
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162401"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



고급 `CloudAppEvents` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 다양한 클라우드 앱 및 서비스에서 지원되는 활동에 대한 정보가 Microsoft Cloud App Security. 전체 목록을 위해 를 다루는 [앱 및 서비스로 이동하세요.](#apps-and-services-covered) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다. 

>[!IMPORTANT]
>이 표에는 표에서 사용할 수 있는 정보가 `AppFileEvents` 포함되어 있습니다. 2021년 3월 7일 이후 클라우드 서비스에서 파일 관련 활동을 찾은 사용자는 대신 이 표를 사용해야 `CloudAppEvents` 합니다. <br><br>테이블을 계속 사용하는 쿼리 및 사용자 지정 검색 규칙을 검색하고 테이블을 사용하여 `AppFileEvents` 편집해야 `CloudAppEvents` 합니다. 영향을 받는 쿼리 변환에 대한 자세한 지침은 고급 헌팅을 사용하여 클라우드 앱 활동에서 헌트에서 [Microsoft 365 Defender 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동 유형 |
| `Application` | 문자열 | 기록된 작업을 수행한 응용 프로그램 |
| `ApplicationId` | 문자열 | 응용 프로그램의 고유 식별자 |
| `AccountObjectId` | 문자열 | 계정의 고유 식별자입니다Azure Active Directory |
| `AccountDisplayName` | 문자열 | 주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `IsAdminOperation` | 문자열 | 관리자가 활동을 수행한지 여부를 나타냅니다. |
| `DeviceType` | 문자열 | "네트워크 장치", "Workstation", "Server", "모바일", "게임 콘솔" 또는 "프린터" 등의 목적 및 기능에 기반한 디바이스 유형 | 
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이 열은 Windows 11, Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `IPAddress` | 문자열 | 끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소 |
| `IsAnonymousProxy` | 문자열 | IP 주소가 알려진 익명 프록시에 속하는지 여부를 나타냅니다. |
| `CountryCode` | 문자열 | 클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드 |
| `City` | 문자열 | 클라이언트 IP 주소가 지리적으로 위치가 지정되는 구 |
| `Isp` | 문자열 | IP 주소와 연결된 ISP(인터넷 서비스 공급자) |
| `UserAgent` | 문자열 | 웹 브라우저 또는 기타 클라이언트 응용 프로그램의 사용자 에이전트 정보 |
| `ActivityType` | 문자열 | 이벤트를 트리거한 활동 유형 |
| `ActivityObjects` | 문자열 | 기록된 활동에 관련된 파일 또는 폴더와 같은 개체 목록 |
| `ObjectName` | 문자열 | 기록된 동작이 적용된 개체의 이름입니다. |
| `ObjectType` | 문자열 | 기록된 작업이 적용된 개체 유형(예: 파일 또는 폴더)입니다. |
| `ObjectId` | 문자열 | 기록된 작업이 적용된 개체의 고유 식별자입니다. |
| `ReportId` | 문자열 | 이벤트의 고유 식별자 |
| `RawEventData` | 문자열 | 원본 응용 프로그램 또는 서비스의 원시 이벤트 정보(JSON 형식) |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대한 추가 정보 |

## <a name="apps-and-services-covered"></a>적용된 앱 및 서비스

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- 비즈니스용 OneDrive
- Power Automate
- Power BI
- SharePoint Online
- 비즈니스용 Skype
- Office 365
- Yammer 

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

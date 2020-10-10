---
title: 고급 구하기 스키마의 AlertEvidence 테이블
description: 고급 구하기 스키마의 AlertEvidence 테이블에서 경고와 관련 된 정보에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, search, query, 원격 분석, 스키마 참조, kusto, table, column, AlertInfo, account, address,, file, machine, user, account
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413201"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

`AlertEvidence` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App SECURITY 및 Azure ATP의 알림과 관련 된 다양 한 엔터티에 대 한 정보 (파일, IP 주소, url, 사용자 또는 장치)가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `AlertId` | 문자열 | 경고의 고유 식별자입니다. |
| `ServiceSource` | 문자열 | 경고 정보를 제공한 제품 또는 서비스 |
| `EntityType` | 문자열 | 파일, 프로세스, 장치 또는 사용자와 같은 개체의 유형입니다. |
| `EvidenceRole` | 문자열 | 관계가 영향을 받는 지 또는 관련이 있는지를 나타내는 경고에 포함 되는 방법 |
| `EvidenceDirection` | 문자열 | 엔터티가 네트워크 연결의 원본 또는 대상 인지를 나타냅니다. |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FolderPath` | 문자열 | 기록 된 작업이 적용 된 파일을 포함 하는 폴더 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 이 필드는 대개 채워지지 않으며, 가능한 경우 SHA1 열을 사용 합니다. |
| `FileSize` | int | 파일 크기 (바이트)입니다. |
| `ThreatFamily` | 문자열 | 의심 스러운 또는 악성 파일 또는 프로세스가 분류 된 맬웨어 패밀리 |
| `RemoteIP` | 문자열 | 연결된 IP 주소 |
| `RemoteUrl` | 문자열 | 연결된 URL 또는 FQDN(정규화된 도메인 이름) |
| `AccountName` | 문자열 | 계정의 사용자 이름입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountSid` | 문자열 | 계정의 SID (보안 식별자) |
| `AccountObjectId` | 문자열 | Azure Active Directory의 계정에 대 한 고유 식별자입니다. |
| `DeviceId` | 문자열 | 서비스의 장치에 대 한 고유 식별자입니다. |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `LocalIP` | 문자열 | 통신 중에 사용 되는 로컬 장치에 할당 된 IP 주소 |
| `NetworkMessageId` | 문자열 | Office 365에서 생성되는 전자 메일의 고유 식별자 |
| `EmailSubject` | 문자열 | 전자 메일 제목 |
| `ApplicationId` | 문자열 | 응용 프로그램의 고유 식별자입니다. |
| `Application` | 문자열 | 기록 된 작업을 수행한 응용 프로그램 |
| `ProcessCommandLine` | 문자열 | 새 프로세스를 만드는 데 사용 되는 명령줄 |
| `AdditionalFields` | 문자열 | JSON 배열 형식의 이벤트에 대 한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

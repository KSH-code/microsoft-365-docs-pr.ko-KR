---
title: 고급 헌팅chema의 AlertEvidence 테이블
description: 고급 헌팅 스파이마의 AlertEvidence 표에서 경고와 관련된 정보에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, AlertInfo, 경고, 엔터티, 증거, 파일, IP 주소, 장치, 컴퓨터, 사용자, 계정
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
ms.openlocfilehash: 2edd6bf9f713ea93c2bddcbca39acd333293718a
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60700352"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅 계획의 표에는 끝점용 Microsoft Defender, Office 365, Microsoft Cloud App Security 및 ID용 Microsoft Defender의 경고와 관련된 다양한 엔터티(파일, IP 주소, URL, 사용자 또는 장치)에 대한 정보가 포함되어 `AlertEvidence` 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `AlertId` | 문자열 | 경고의 고유 식별자입니다. |
| `ServiceSource` | 문자열 | 경고 정보를 제공한 제품 또는 서비스 |
| `EntityType` | 문자열 | 파일, 프로세스, 장치 또는 사용자와 같은 개체 유형 |
| `EvidenceRole` | 문자열 | 엔터티가 경고에 관여하는 방법, 영향이 있는지 아니면 그와만 관련이 있는지를 나타내는 알림 |
| `EvidenceDirection` | 문자열 | 엔터티가 네트워크 연결의 원본인지 아니면 대상인지를 나타냅니다. |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FolderPath` | 문자열 | 기록된 작업이 적용된 파일이 들어 있는 폴더 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 이 필드는 일반적으로 채워지지 않습니다. 사용 가능한 경우 SHA1 열을 사용 합니다. |
| `FileSize` | int | 파일 크기(bytes)입니다. |
| `ThreatFamily` | 문자열 | 의심스러운 파일 또는 악의적인 파일 또는 프로세스가 분류된 맬웨어 패밀리 |
| `RemoteIP` | 문자열 | 연결된 IP 주소 |
| `RemoteUrl` | 문자열 | 연결된 URL 또는 FQDN(정규화된 도메인 이름) |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `AccountObjectId` | 문자열 | 계정의 고유 식별자입니다Azure Active Directory |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `LocalIP` | 문자열 | 통신 중에 사용되는 로컬 장치에 할당된 IP 주소 |
| `NetworkMessageId` | 문자열 | Office 365에서 생성되는 전자 메일의 고유 식별자 |
| `EmailSubject` | 문자열 | 전자 메일 제목 |
| `ApplicationId` | 문자열 | 응용 프로그램의 고유 식별자 |
| `Application` | 문자열 | 기록된 작업을 수행한 응용 프로그램 |
| `ProcessCommandLine` | 문자열 | 새 프로세스를 만드는 데 사용되는 명령줄 |
| `AdditionalFields` | 문자열 | JSON 배열 형식의 이벤트에 대한 추가 정보 |
| `RegistryKey` |문자열 | 기록된 작업이 적용된 레지스트리 키 |
| `RegistryValueName` |문자열 | 기록된 작업이 적용된 레지스트리 값의 이름입니다. |
| `RegistryValueData` |문자열 | 기록된 작업이 적용된 레지스트리 값의 데이터 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

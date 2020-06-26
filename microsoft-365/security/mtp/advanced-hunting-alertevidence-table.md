---
title: 고급 구하기 스키마의 AlertEvidence 테이블
description: 고급 구하기 스키마의 AlertEvidence 테이블에서 생성 된 경고와 관련 된 파일, 네트워크 주소, 사용자 또는 장치 정보에 대해 알아봅니다.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899354"
---
# <a name="alertevidence"></a>AlertEvidence

**적용 대상:**
- Microsoft 위협 방지

`AlertEvidence` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App SECURITY 및 Azure ATP의 알림과 관련 된 다양 한 엔터티에 대 한 정보 (파일, IP 주소, url, 사용자 또는 장치)가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `AlertId` | 문자열 | 경고의 고유 식별자입니다. |
| `EntityType` | 문자열 | 파일, 프로세스, 장치 또는 사용자와 같은 개체의 유형입니다. |
| `EvidenceRole` | 문자열 | 관계가 영향을 받는 지 또는 관련이 있는지를 나타내는 경고에 포함 되는 방법 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `RemoteIP` | 문자열 | 연결된 IP 주소 |
| `RemoteUrl` | 문자열 | 연결된 URL 또는 FQDN(정규화된 도메인 이름) |
| `AccountName` | 문자열 | 계정의 사용자 이름입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountSid` | 문자열 | 계정의 SID (보안 식별자) |
| `AccountObjectId` | 문자열 | Azure AD의 계정에 대 한 고유 식별자입니다. |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `ThreatFamily` | 문자열 | 의심 스러운 또는 악성 파일 또는 프로세스가 분류 된 맬웨어 패밀리 |
| `EvidenceDirection` | 문자열 | 엔터티가 네트워크 연결의 원본 또는 대상 인지를 나타냅니다. |
| `AdditionalFields` | 문자열 | JSON 배열 형식의 이벤트에 대 한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

---
title: 고급 헌팅 스키마의 EmailUrlInfo 표
description: 고급 헌팅 스키마의 EmailUrlInfo 표에서 URL 또는 링크 정보에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, EmailUrlInfo, 네트워크 메시지 ID, URL, 링크
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
ms.openlocfilehash: 51182f87eae4a26153b08c934c3f77e0164f4b8b
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60702064"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅 schema의 표에는 Microsoft Defender에서 고급 헌팅을 위해 처리한 전자 메일 및 첨부 파일에 대한 `EmailUrlInfo` Office 365. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다. 

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `NetworkMessageId` | 문자열 | 전자 메일에서 생성되는 전자 메일의 고유 Microsoft 365 |
| `Url` | 문자열 | 전자 메일 제목, 본문 또는 첨부 파일의 전체 URL |
| `UrlDomain` | 문자열 | URL의 도메인 이름 또는 호스트 이름 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

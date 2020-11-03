---
title: 고급 헌팅 스키마의 EmailUrlInfo 표
description: 고급 헌팅 스키마의 EmailUrlInfo 표에서 URL 또는 링크 정보에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description
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
ms.openlocfilehash: 6684f2d56cb30c909cae57e7b3e6593377449f6b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842563"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

`EmailUrlInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft Defender for Office 365에서 처리 하는 전자 메일 및 첨부 파일의 url에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `UrlId` | 문자열 | 전자 메일 제목, 본문 또는 첨부 파일의 URL에 대한 고유 식별자 |
| `NetworkMessageId` | 문자열 | Microsoft 365에서 생성 된 전자 메일에 대 한 고유 식별자입니다. |
| `Url` | 문자열 | 전자 메일 제목, 본문 또는 첨부 파일의 전체 URL |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

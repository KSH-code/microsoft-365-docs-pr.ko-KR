---
title: 고급 헌팅 스키마의 EmailUrlInfo 표
description: 고급 헌팅 스키마의 EmailUrlInfo 표에서 URL 또는 링크 정보에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, 표, 열, 데이터 형식, 설명, EmailUrlInfo, 네트워크 메시지 ID, URL, 링크
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 10cf82667fd97eebe66c376e0539db000f20b1c2
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911450"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**적용 대상:**
- Microsoft 위협 방지

[!include[Prerelease information](prerelease.md)]

[고급 헌팅](advanced-hunting-overview.md) 스키마의 `EmailUrlInfo` 표에는 Office 365 ATP에서 처리된 전자 메일의 URL 및 첨부 파일에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `EventTime` | datetime | 이벤트가 기록된 날짜와 시간 |
| `UrlId` | 문자열 | 전자 메일 제목, 본문 또는 첨부 파일의 URL에 대한 고유 식별자 |
| `NetworkMessageId` | 문자열 | Office 365에서 생성되는 전자 메일의 고유 식별자 |
| `Url` | 문자열 | 전자 메일 제목, 본문 또는 첨부 파일의 전체 URL |

## <a name="related-topics"></a>관련 항목
- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
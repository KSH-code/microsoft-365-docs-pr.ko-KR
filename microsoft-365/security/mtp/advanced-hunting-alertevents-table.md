---
title: 고급 헌팅 스키마의 AlertEvents 표
description: 고급 헌팅 스키마의 AlertEvents 표에서 경고 생성 이벤트 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, alertevents, alert, 심각도, 범주
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: f72658e552bcb7ce351eafa43ad950c0bc11cb69
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515829"
---
# <a name="alertevents"></a>AlertEvents

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[고급 헌팅](advanced-hunting-overview.md) 스키마의 `AlertEvents` 표에는 Microsoft Defender ATP 경고에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `AlertId` | 문자열 | 경고의 고유 식별자입니다. |
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `Severity` | 문자열 | 경고로 식별되는 위협 표시기 또는 위반 활동의 잠재적인 영향(높음, 중간 또는 낮음)을 표시합니다. |
| `Category` | 문자열 | 경고로 식별되는 위협 표시기 또는 위반 활동 유형 |
| `Title` | 문자열 | 경고의 제목입니다. |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `RemoteUrl` | 문자열 | 연결된 URL 또는 FQDN(정규화된 도메인 이름) |
| `RemoteIP` | 문자열 | 연결된 IP 주소 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다. |
| `Table` | 문자열 | 이벤트에 대한 세부 정보를 포함하는 표 |

## <a name="related-topics"></a>관련 항목
- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

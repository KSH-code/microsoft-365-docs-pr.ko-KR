---
title: 고급 헌팅Chema의 DeviceAlertEvents 테이블
description: 고급 헌팅 스위마의 DeviceAlertEvents 테이블에서 경고 생성 이벤트에 대해 자세히 알아보시고
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 끝점용 Microsoft Defender, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: bb2350fed5fadee359695743989e02a3b3e44fb2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935344"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

고급 `DeviceAlertEvents` 헌팅 [Schema의](advanced-hunting-overview.md) 표에는 Microsoft Defender 보안 센터의 경고에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `AlertId` | 문자열 | 경고의 고유 식별자입니다. |
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `Severity` | 문자열 | 경고로 식별되는 위협 표시기 또는 위반 활동의 잠재적인 영향(높음, 중간 또는 낮음)을 표시합니다. |
| `Category` | 문자열 | 경고로 식별되는 위협 표시기 또는 위반 활동 유형 |
| `Title` | 문자열 | 경고의 제목입니다. |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `RemoteUrl` | 문자열 | 연결된 URL 또는 FQDN(정규화된 도메인 이름) |
| `RemoteIP` | 문자열 | 연결된 IP 주소 |
| `AttackTechniques` | 문자열 | MITRE ATT&트리거한 활동과 관련된 CK 기술입니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다. |
| `Table` | 문자열 | 이벤트에 대한 세부 정보를 포함하는 표 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)

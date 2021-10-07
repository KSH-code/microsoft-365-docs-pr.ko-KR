---
title: 고급 헌팅 schema의 EmailPostDeliveryEvents 테이블
description: 고급 헌팅 Microsoft 365 EmailPostDeliveryEvents 표에서 전자 메일에 대해 수행한 배달 후 작업에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, EmailPostDeliveryEvents, 네트워크 메시지 ID, 보낸 사람, 받는 사람, 첨부 파일 ID, 첨부 파일 이름, 맬웨어 판정, 피싱 결과, 첨부 파일 수, 링크 수, URL 개수
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
ms.openlocfilehash: 5de874a75763152422fb1cd84e90bc9fed716e6a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199564"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 `EmailPostDeliveryEvents` 헌팅 schema의 표에는 고급 헌팅에서 처리된 전자 메일 메시지에 대해 수행된 배달 후 작업에 대한 정보가 Microsoft 365. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.

개별 전자 메일 메시지에 대한 자세한 정보를 얻기 위해 , 및 테이블을 [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) 사용할 수도 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) 있습니다. 고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `NetworkMessageId` | 문자열 | 전자 메일에서 생성되는 전자 메일의 고유 Microsoft 365 |
| `InternetMessageId` | 문자열 | 보내는 전자 메일 시스템에서 설정한 전자 메일의 공개 식별자 |
| `Action` | 문자열 | 엔터티에 대한 작업 |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동 유형: 수동 수정, 피싱 ZAP, 맬웨어 ZAP |
| `ActionTrigger` | 문자열 | 관리자가 작업을 트리거(수동 또는 보류 중인 자동 작업 승인을 통해) 또는 ZAP 또는 동적 배달과 같은 몇 가지 특수 메커니즘에 의해 트리거된 것인지를 나타냅니다. |
| `ActionResult` | 문자열 | 작업 결과 |
| `RecipientEmailAddress` | 문자열 | 받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소 |
| `DeliveryLocation` | 문자열 | 전자 메일이 전송된 위치: 받은 편지함/폴더, 온-프레미스/외부, 정크, 격리, 실패, 중단, 삭제된 항목 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |
| `ThreatTypes` | 문자열 | 전자 메일에 맬웨어, 피싱 또는 기타 위협이 포함되어 있는지 여부에 대한 전자 메일 필터링 스택의 판정 |
| `DetectionMethods` | 문자열 | 전자 메일에 있는 맬웨어, 피싱 또는 기타 위협을 감지하는 데 사용되는 방법 |

## <a name="supported-event-types"></a>지원되는 이벤트 유형
이 표에서는 다음 값으로 이벤트를 `ActionType` 캡처합니다.

- **수동 수정** - 관리자가 사용자 사서함으로 배달된 후 전자 메일 메시지에 대한 작업을 수동으로 수행했습니다. 여기에는 위협 탐색기를 [통해](../office-365-security/threat-explorer.md) 수동으로 수행한 작업 또는 자동화된 조사 및 대응(AIR) 작업의 [승인이 포함됩니다.](m365d-autoir-actions.md)
- **피싱 ZAP** – 배달 후 피싱 전자 메일에 [대한 ZAP(제로](../office-365-security/zero-hour-auto-purge.md) 아워 자동 제거)가 작업을 수행했습니다.
- **맬웨어 ZAP** - ZAP(제로 아워 자동 제거)는 배달 후 맬웨어가 포함된 전자 메일 메시지에 대해 작업을 수행했습니다.

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

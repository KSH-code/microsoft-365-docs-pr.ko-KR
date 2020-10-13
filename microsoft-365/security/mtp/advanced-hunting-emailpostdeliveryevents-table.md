---
title: 고급 구하기 스키마의 EmailPostDeliveryEvents 테이블
description: 고급 구하기 스키마의 EmailPostDeliveryEvents 테이블에서 Microsoft 365 전자 메일에 대해 수행 된 배달 후 작업에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, 첨부 파일 이름, 맬웨어 결과, 피싱 결과, 첨부 파일 수, 링크 수, url 개수
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
ms.openlocfilehash: ea54f6b312c473240dba07eae95733d2ea610fe5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430552"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

`EmailPostDeliveryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft 365에서 처리 되는 전자 메일 메시지에 대해 수행 된 배달 후 작업에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.

개별 전자 메일 메시지에 대 한 자세한 내용을 보려면 [`EmailEvents`](advanced-hunting-emailevents-table.md) , 및 테이블을 사용할 수도 있습니다 [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . 고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `EventId` | 문자열 | 이벤트에 대 한 고유 식별자입니다. |
| `NetworkMessageId` | 문자열 | Microsoft 365에서 생성 된 전자 메일에 대 한 고유 식별자입니다. |
| `InternetMessageId` | 문자열 | 보내는 전자 메일 시스템에서 설정한 전자 메일의 공개 식별자 |
| `Action` | 문자열 | 엔터티에 대해 수행 된 작업 |
| `ActionType` | 문자열 | 이벤트를 트리거한 작업의 유형: 수동 재구성, 피싱 ZAP, 맬웨어 ZAP |
| `ActionTrigger` | 문자열 | 작업이 관리자에 의해 트리거된 지 (수동으로 또는 보류 중인 자동 작업의 승인를 통해) 또는 ZAP 또는 동적 배달과 같은 특수 메커니즘을 통해 트리거 되었는지를 나타냅니다. |
| `ActionResult` | 문자열 | 작업 결과 |
| `RecipientEmailAddress` | 문자열 | 받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소 |
| `DeliveryLocation` | 문자열 | 전자 메일이 전송된 위치: 받은 편지함/폴더, 온-프레미스/외부, 정크, 격리, 실패, 중단, 삭제된 항목 |

## <a name="supported-event-types"></a>지원 되는 이벤트 유형
이 테이블은 다음과 같은 값을 갖는 이벤트를 캡처합니다 `ActionType` .

- **수동 재구성** – 관리자가 사용자 사서함으로 배달 된 후 수동으로 전자 메일 메시지에 대 한 작업을 수행 했습니다. 여기에는 [위협 탐색기](../office-365-security/threat-explorer.md) 를 통해 수동으로 수행 하거나 [자동화 된 조사 및 응답 (AIR) 작업](mtp-autoir-actions.md)을 승인 하는 작업이 포함 됩니다.
- **피싱 zap** -배달 후 피싱 전자 메일에 대해 [제로 시간 자동 삭제 (ZAP)](../office-365-security/zero-hour-auto-purge.md) 가 수행 되었습니다.
- **맬웨어 ZAP** -배달 후 맬웨어가 포함 된 전자 메일 메시지에 대해 제로 시간 자동 삭제 (ZAP)가 수행 되었습니다.

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

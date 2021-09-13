---
title: 고급 헌팅 스키마의 EmailAttachmentInfo 표
description: 고급 헌팅 스키마의 EmailAttachmentInfo 표에서 전자 메일 첨부 파일 정보에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, EmailAttachmentInfo, 네트워크 메시지 ID, 보낸 사람, 받는 사람, 첨부 파일 ID, 첨부 파일 이름, 맬웨어 결과
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
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b38953c5f57b13e7aa13c62da926552c3d45c74b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211935"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



고급 `EmailAttachmentInfo` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 Microsoft Defender에서 고급 헌팅을 위해 처리한 전자 메일의 첨부 파일에 대한 Office 365. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `NetworkMessageId` | 문자열 | 전자 메일에서 생성되는 전자 메일의 고유 Microsoft 365 |
| `SenderFromAddress` | 문자열 | 전자 메일 클라이언트의 전자 메일 수신자에게 표시되는 FROM 머리글의 발신자 전자 메일 주소  |
| `SenderDisplayName` | 문자열 | 주소장에 표시되는 보낸 사람 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 이니셜 및 성 또는 성의 조합입니다. |
| `SenderObjectId` | 문자열 | Azure AD에서 보낸 사람 계정의 고유 식별자 |
| `RecipientEmailAddress` | 문자열 | 받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소 |
| `RecipientObjectId` | 문자열 | Azure AD에서 전자 메일 받는 사람의 고유 식별자 |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FileType` | 문자열 | 파일 확장명 유형 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `ThreatTypes` | 문자열 | 전자 메일에 맬웨어, 피싱 또는 기타 위협이 포함되어 있는지 여부에 대한 전자 메일 필터링 스택의 판정 |
| `ThreatNames` | 문자열 | 맬웨어 또는 기타 위협이 발견된 검색 이름 |
| `DetectionMethods` | 문자열 | 전자 메일에 있는 맬웨어, 피싱 또는 기타 위협을 감지하는 데 사용되는 방법 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |
| `FileSize` | 문자열 | 파일 크기(bytes)입니다. |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

---
title: 고급 헌팅 스키마의 EmailAttachmentInfo 표
description: 고급 헌팅 스키마의 EmailAttachmentInfo 표에서 전자 메일 첨부 파일 정보에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malwaredictdict
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d4c72d78fc6a31ec3075d4e7a889e191e639829
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029377"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



고급 헌팅 과정의 표에는 `EmailAttachmentInfo` Office 365용 Microsoft Defender에서 처리한 전자 메일의 첨부 파일에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | 날짜/시간 | 이벤트가 기록된 날짜와 시간 |
| `NetworkMessageId` | 문자열 | Microsoft 365에서 생성되는 전자 메일의 고유 식별자 |
| `SenderFromAddress` | 문자열 | 전자 메일 클라이언트의 전자 메일 수신자에게 표시되는 FROM 머리글의 발신자 전자 메일 주소  |
| `RecipientEmailAddress` | 문자열 | 받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소 |
| `RecipientObjectId` | 문자열 | Azure AD에서 전자 메일 받는 사람에 대한 고유 식별자 |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FileType` | 문자열 | 파일 확장명 유형 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `MalwareFilterVerdict` | 문자열 | 전자 메일이 맬웨어를 포함하는지 여부에 대한 전자 메일 필터링 스택의 결과. Malware. malware 아님. |
| `MalwareDetectionMethod` | 문자열 | 전자 메일에서 맬웨어를 감지하는 데 사용되는 방법: 맬웨어 방지 엔진, 파일 신뢰도, 안전한 첨부 파일 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다. |
| `SenderDisplayName` | 문자열 | 주소부에 표시되는 보낸 사람 이름( 일반적으로 지정한 이름 또는 이름, 중간 이니셜 및 성 또는 성의 조합) |
| `SenderObjectId` | 문자열 | Azure AD에서 보낸 사람 계정의 고유 식별자 |
| `ThreatTypes` | 문자열 | 전자 메일에 맬웨어, 피싱 또는 기타 위협이 포함되어 있는지 여부에 대한 전자 메일 필터링 스택의 판정 |
| `ThreatNames` | 문자열 | 맬웨어 또는 기타 위협이 발견된 검색 이름 |
| `DetectionMethods` | 문자열 | 전자 메일에서 맬웨어, 피싱 또는 기타 위협을 감지하는 데 사용되는 방법 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

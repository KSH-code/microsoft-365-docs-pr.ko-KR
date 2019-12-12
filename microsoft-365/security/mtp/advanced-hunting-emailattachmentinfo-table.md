---
title: 고급 헌팅 스키마의 EmailAttachmentInfo 표
description: 고급 헌팅 스키마의 EmailAttachmentInfo 표에서 전자 메일 첨부 파일 정보에 대해 알아봅니다.
keywords: 고급 현팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, 표, 열, 데이터 형식, 설명, EmailAttachmentInfo, 네트워크 메시지 id, 보낸 사람, 받는 사람, 첨부 파일 id, 첨부 파일 이름, 맬웨어 판정
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
ms.openlocfilehash: 9f6a4aa68826133bee0437116b2fbf3fde4e7e00
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911435"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**적용 대상:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

[고급 헌팅](advanced-hunting-overview.md) 스키마의 `EmailAttachmentInfo` 표에는 Office 365 ATP에서 처리된 전자 메일의 첨부 파일에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `EventTime` | 날짜/시간 | 이벤트가 기록된 날짜와 시간 |
| `AttachmentId` | 문자열 | 고유한 전자 메일 첨부 파일 식별자 |
| `NetworkMessageId` | 문자열 | Office 365에서 생성되는 전자 메일의 고유 식별자 |
| `SenderFromAddress` | 문자열 | 전자 메일 클라이언트의 전자 메일 수신자에게 표시되는 FROM 머리글의 발신자 전자 메일 주소  |
| `RecipientEmailAddress` | 문자열 | 받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소 |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FileType` | 문자열 | 파일 확장명 유형 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `MalwareFilterVerdict` | 문자열 | 전자 메일이 맬웨어를 포함하는지 여부에 대한 전자 메일 필터링 스택의 결과. Malware. malware 아님. |
| `MalwareDetectionMethod` | 문자열 | 전자 메일에서 맬웨어를 검색하는 데 사용하는 방법: Antimalware engine, File reputation, ATP Safe Attachments |

## <a name="related-topics"></a>관련 항목
- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
---
title: 고급 헌팅 스위마의 IdentityInfo 테이블
description: 고급 헌팅 스위마의 IdentityInfo 표에서 사용자 계정 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, AccountInfo, IdentityInfo, 계정
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
ms.openlocfilehash: 3b961990d7826a7e1d58586fcc5bf2e016fa5d37
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704304"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 `IdentityInfo` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 고급 헌팅을 비롯한 다양한 서비스에서 얻은 사용자 계정에 대한 Azure Active Directory. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!NOTE]
>이 테이블의 이름을 에서 `AccountInfo` 으로했습니다. 이름을 변경하는 동안 포털에 저장된 모든 쿼리가 자동으로 업데이트됩니다. 다른 곳에 저장한 쿼리를 검사합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `AccountObjectId` | 문자열 | Azure AD에서 계정의 고유 식별자 |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `OnPremSid` | 문자열 | 계정의 SID(사내 보안 식별자)입니다. |
| `CloudSid` | 문자열 | 계정의 클라우드 보안 식별자 |
| `GivenName` | 문자열 | 계정 사용자의 이름 또는 지정한 이름 |
| `Surname` | 문자열 | 계정 사용자의 성, 가족 이름 또는 성 |
| `AccountDisplayName` | 문자열 | 주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `Department` | 문자열 | 계정 사용자가 속한 부서의 이름 |
| `JobTitle` | 문자열 | 계정 사용자의 직위 |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `EmailAddress` | 문자열 | 계정의 SMTP 주소 |
| `SipProxyAddress` | 문자열 | 계정의 VOIP(Voice over IP) SIP(Session Initiation Protocol) 주소 |
| `City` | 문자열 | 계정 사용자가 있는 구 |
| `Country` | 문자열 | 계정 사용자가 있는 국가/지역 |
| `IsAccountEnabled` | 부울 | 계정이 활성화되어 있는지 여부를 나타냅니다. |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

---
title: 고급 구하기 스키마의 IdentityInfo 테이블
description: 고급 구하기 스키마의 IdentityInfo 테이블에서 사용자 계정 정보에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, description, AccountInfo, IdentityInfo, account
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3d59f987ae4d670e3d7c6f1638f8090ffc3ba7fe
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649310"
---
# <a name="identityinfo"></a>IdentityInfo

**적용 대상:**
- Microsoft 위협 방지

`IdentityInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Azure Active Directory를 비롯 하 여 다양 한 서비스에서 가져온 사용자 계정에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!NOTE]
>이 테이블의 이름은에서 변경 되었습니다 `AccountInfo` . 이름을 변경 하는 동안에는 포털에 저장 된 모든 쿼리가 자동으로 업데이트 됩니다. 다른 위치에서 저장 한 쿼리를 확인 합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `AccountObjectId` | 문자열 | Azure AD의 계정에 대 한 고유 식별자입니다. |
| `AccountUpn` | 문자열 | 계정의 UPN (사용자 계정 이름) |
| `OnPremSid` | 문자열 | 계정의 온-프레미스 SID (보안 식별자) |
| `CloudSid` | 문자열 | 계정의 클라우드 보안 식별자 |
| `GivenName` | 문자열 | 계정 사용자의 이름이 나 이름을 지정 합니다. |
| `Surname` | 문자열 | 계정 사용자의 성, 패밀리 이름 또는 성 |
| `AccountDisplayName` | 문자열 | 주소록에 표시 되는 계정 사용자의 이름입니다. 일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `Department` | 문자열 | 계정 사용자가 속한 부서의 이름입니다. |
| `JobTitle` | 문자열 | 계정 사용자의 직함 |
| `AccountName` | 문자열 | 계정의 사용자 이름입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `EmailAddress` | 문자열 | 계정의 SMTP 주소입니다. |
| `SipProxyAddress` | 문자열 | 계정의 SIP (Voice over IP) session (세션 시작 프로토콜) 주소 |
| `City` | 문자열 | 계정 사용자가 있는 구/군/시 |
| `Country` | 문자열 | 계정 사용자가 있는 국가/지역 |
| `IsAccountEnabled` | 부울 | 계정을 사용할 수 있는지 여부를 나타냅니다. |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 id 간 헌트](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

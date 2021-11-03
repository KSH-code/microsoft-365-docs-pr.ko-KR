---
title: 고급 헌팅의 FileProfile() Microsoft 365 Defender
description: FileProfile()을 사용하여 고급 헌팅 쿼리 결과의 파일에 대한 정보를 강화하는 방법에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, FileProfile, 파일 프로필, 기능, 향상
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
ms.openlocfilehash: c7ad9678f797fd3e8df34b40fe39fea5672e13d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60670609"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

이 함수는 쿼리에서 찾은 파일에 다음 데이터를 추가하는 고급 헌팅의 `FileProfile()` 향상 함수입니다. [](advanced-hunting-overview.md)

| 열 | 데이터 형식 | 설명 |
|------------|---------------|-------------|
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `SHA256` | 문자열 | 기록된 작업이 적용된 파일의 SHA-256 |
| `MD5` | 문자열 | 기록된 작업이 적용된 파일의 MD5 해시입니다. |
| `FileSize` | int | 파일 크기(bytes)입니다. |
| `GlobalPrevalence` | int | Microsoft에서 전역적으로 관찰하는 엔터티의 인스턴스 수 |
| `GlobalFirstSeen` | datetime | Microsoft에서 엔터티를 전역적으로 처음 관찰한 날짜 및 시간 |
| `GlobalLastSeen` | datetime | Microsoft에서 엔터티를 마지막으로 관찰한 날짜 및 시간 |
| `Signer` | 문자열 | 파일의 서명자에 대한 정보 |
| `Issuer` | 문자열 | 발급 CA(인증 기관)에 대한 정보 |
| `SignerHash` | 문자열 | 서명자를 식별하는 고유 해시 값 |
| `IsCertificateValid` | 부울 | 파일에 서명하는 데 사용된 인증서가 유효한지 여부 |
| `IsRootSignerMicrosoft` | 부울 | 루트 인증서의 서명자인지 여부를 나타냅니다. |
| `SignatureState` | 문자열 | 파일 서명 상태: SignedValid - 파일이 유효한 서명으로 서명되었습니다. SignedInvalid - 파일이 서명되지만 인증서가 잘못되었거나 서명되지 않았습니다. 파일이 서명되지 않았고 알 수 없음 - 파일에 대한 정보를 검색할 수 없습니다.
| `IsExecutable` | 부울 | 파일이 PE(Portable Executable) 파일인지 여부 |
| `ThreatName` | 문자열 | 발견된 맬웨어 또는 기타 위협에 대한 검색 이름 |
| `Publisher` | 문자열 | 파일을 게시한 조직의 이름입니다. |
| `SoftwareName` | 문자열 | 소프트웨어 제품의 이름 |

## <a name="syntax"></a>구문

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>인수

- **x**-사용할 파일 ID 열: `SHA1` , , 또는 ; `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` 함수가 `SHA1` 선택하지 않은 경우 사용
- **y**- 보강할 레코드 수로 제한, 1-1000; 함수가 100을 사용하는 경우


>[!TIP]
> 향상 함수는 사용할 수 있는 경우만 추가 정보를 보여 주게 됩니다. 정보의 가용성은 다양한 요소에 따라 다릅니다. 쿼리에서 FileProfile()을 사용하거나 사용자 지정 검색을 만들 때 이를 고려해야 합니다. 최상의 결과를 얻기 위해 FileProfile() 함수를 SHA1과 함께 사용하는 것이 좋습니다.

## <a name="examples"></a>예제

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project SHA1 열만 추가하고 강화

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>처음 500개 레코드 보강 및 낮은 보전 파일 목록

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마에 대한 이해](advanced-hunting-schema-tables.md)
- [더 많은 쿼리 예제 보기](advanced-hunting-shared-queries.md)

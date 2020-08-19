---
title: Microsoft Threat Protection의 FileProfile () 함수 고급 구하기
description: FileProfile ()을 사용 하 여 고급 구하기 쿼리 결과의 파일에 대 한 정보를 보강 하는 방법을 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, FileProfile, file profile, function, 향상
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
ms.openlocfilehash: d0fd359bb6f56f7c20b0a39b7fd45ec551e7e49e
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797785"
---
# <a name="fileprofile"></a>FileProfile()

**적용 대상:**
- Microsoft 위협 방지

`FileProfile()`이 함수는 [고급](advanced-hunting-overview.md) 검색에서 쿼리에 의해 찾은 파일에 다음 데이터를 추가 하는 향상 함수입니다.

| 열 | 데이터 형식 | 설명 |
|------------|-------------|-------------|
| SHA1 | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| SHA256 | 문자열 | 기록 된 작업이 적용 된 파일의 SHA-256 |
| MD5 | 문자열 | 기록 된 작업이 적용 된 파일의 MD5 해시 |
| FileSize | int | 파일 크기 (바이트)입니다. |
| GlobalPrevalence | int | Microsoft에서 전역적으로 관찰 한 엔터티 인스턴스 수 |
| GlobalFirstSeen 경우 | datetime | Microsoft에서 처음으로 엔터티를 관측 한 날짜 및 시간입니다. |
| GlobalLastSeen | datetime | Microsoft에서 전역적으로 엔터티를 마지막으로 관찰 한 날짜 및 시간입니다. |
| 받은 | 문자열 | 파일의 서명자에 대 한 정보 |
| 발급 | 문자열 | 발급 CA (인증 기관)에 대 한 정보 |
| SignerHash | 문자열 | 서명자를 식별 하는 고유한 해시 값 |
| IsCertificateValid | 부울 | 파일 서명에 사용 된 인증서가 유효한 지 여부 |
| IsRootSignerMicrosoft | 부울 | 루트 인증서의 서명자가 Microsoft 인지 여부를 나타냅니다. |
| IsExecutable | 부울 | PE (이식 가능한 실행) 파일 인지 여부 |
| Mail.threatname | 문자열 | 발견 된 맬웨어 또는 기타 위협에 대 한 검색 이름 |
| Publisher | 문자열 | 파일을 게시 한 조직의 이름입니다. |
| SoftwareName | 문자열 | 소프트웨어 제품의 이름 |

## <a name="syntax"></a>구문과

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>인수나

- **x** -다음을 사용할 파일 ID 열: `SHA1` , `SHA256` , `InitiatingProcessSHA1` 또는 `InitiatingProcessSHA256` ; function이 `SHA1` 지정 되지 않은 경우 사용 합니다.
- **y** -보강할 레코드 수에 대 한 제한 1-1000; 함수가 지정 되지 않은 경우 100을 사용 합니다.

## <a name="examples"></a>예

### <a name="project-only-the-sha1-column-and-enrich-it"></a>SHA1 열만 프로젝트 및 보강

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>처음 500 레코드를 보강 하 고 낮은 전파 파일 목록 표시

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 예제 더 보기](advanced-hunting-shared-queries.md)
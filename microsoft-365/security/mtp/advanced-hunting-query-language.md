---
title: Microsoft Threat Protection에서 고급 헌팅 쿼리 언어 알아보기
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격, 사용자 지정 감지, 스키마, kusto, and, data types, powershell 다운로드, 쿼리 예제
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
ms.openlocfilehash: 5715baaccd95d975f7d15196906a6326177bbc2e
ms.sourcegitcommit: 242f051c4cf3683f8c1a5da20ceca81bde212cfc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982014"
---
# <a name="learn-the-advanced-hunting-query-language"></a>고급 헌팅 쿼리 언어 알아보기

**적용 대상:**
- Microsoft Threat Protection

고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 합니다. Kusto 구문 및 연산자를 사용하여 고급 헌팅을 위해 특별히 구성된 [스키마](advanced-hunting-schema-tables.md)에서 정보를 찾는 쿼리를 만들 수 있습니다. 이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.

## <a name="try-your-first-query"></a>첫 번째 쿼리 시도하기

Microsoft 365 보안 센터에서 **검색으로 이동 하 여** 첫 번째 쿼리를 실행 합니다. 다음 예제를 사용합니다.

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

이는 고급 헌팅에서 표시되는 모습입니다.

![Microsoft Threat Protection 고급 구하기 쿼리 이미지](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>쿼리 설명 및 검색할 테이블 지정
쿼리의 시작 부분에 요약 설명이 추가 되어 해당 내용을 설명 합니다. 이렇게 하면 나중에 쿼리를 저장 하 고 조직의 다른 사용자와 공유할 수 있습니다. 

```kusto
// Finds PowerShell execution events that could involve a download
```

일반적으로 쿼리 자체는 표 이름으로 시작하고 다음으로 파이프(`|`)로 시작되는 일련의 요소가 옵니다. 이 예제에서는 먼저 두 개의 테이블 `DeviceProcessEvents` `DeviceNetworkEvents`을 통합 하 고 필요에 따라 파이프 된 요소를 추가 합니다.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>시간 범위 설정
첫 번째 파이프 요소는 이전 7 일간 범위가 지정 된 시간 필터입니다. 시간 범위를 가능한 한 좁게 유지하면 쿼리가 제대로 수행되고 관리 가능한 결과를 반환하며 시간 초과되지 않습니다.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>특정 프로세스 확인
시간 범위 바로 뒤에 PowerShell 응용 프로그램을 나타내는 프로세스 파일 이름을 검색 합니다.

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>특정 명령 문자열 검색
나중에이 쿼리는 PowerShell을 사용 하 여 파일을 다운로드 하는 데 일반적으로 사용 되는 명령줄에서 문자열을 찾습니다.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a>결과 열 및 길이 사용자 지정 
쿼리에서 찾으려고 하는 데이터를 명확하게 식별하므로 결과 모양을 정의하는 요소를 추가할 수 있습니다. `project`특정 열을 반환 하 `top` 고 결과 수를 제한 합니다. 이러한 연산자를 사용 하면 결과의 형식이 적절 하 고 상당히 크고 프로세스를 간편 하 게 수행할 수 있습니다.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

**쿼리 실행**을 클릭하여 결과를 확인합니다. 검색 쿼리와 결과에 중점을 두기 위해 쿼리 편집기의 오른쪽 위에 있는 확장 아이콘을 선택 합니다. 

![고급 구하기 쿼리 편집기의 확장 컨트롤 이미지](../../media/advanced-hunting-expand.png)

>[!TIP]
>쿼리 결과를 차트로 보고 필터를 빠르게 조정할 수 있습니다. 지침을 보려면 [쿼리 결과 작업에 대 한 내용을 읽어보십시오](advanced-hunting-query-results.md) .

## <a name="learn-common-query-operators-for-advanced-hunting"></a>고급 헌팅에 대한 일반적인 쿼리 연산자 살펴보기

첫 번째 쿼리를 실행하고 해당 구성 요소에 대한 일반적인 아이디어를 얻었으므로 약간 되돌아가서 몇 가지 기본 사항을 배울 차례입니다. 고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.

| 연산자 | 설명 및 사용법 |
|--|--|
| `where` | 조건자를 충족하는 행의 하위 집합으로 표를 필터링합니다. |
| `summarize` | 입력 표의 내용을 집계하는 표를 생성합니다. |
| `join` | 각 표에서 지정된 열의 값을 일치시켜 새 표를 구성하는 두 테이블의 행을 병합합니다. |
| `count` | 입력 레코드 집합의 레코드 수를 반환합니다. |
| `top` | 지정된 열을 기준으로 정렬된 처음 N개의 레코드를 반환합니다. |
| `limit` | 지정된 수의 행까지 반환합니다. |
| `project` | 포함할 열을 선택하고 이름을 바꾸거나 삭제하고 새 계산된 열을 삽입합니다. |
| `extend` | 계산된 열을 만들고 결과 집합에 추가합니다. |
| `makeset` |  Expr이 그룹에서 사용하는 고유한 값 집합의 동적(JSON) 배열을 반환합니다. |
| `find` | 표 집합에서 조건자와 일치하는 행을 찾습니다. |

이러한 연산자의 실제 예제를 보려면 고급 헌팅의 **시작** 섹션에서 해당 연산자를 실행합니다.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>데이터 형식 및 해당 쿼리 구문의 영향 이해

고급 헌팅 표에서 데이터는 일반적으로 다음과 같은 데이터 형식으로 분류됩니다.

| 데이터 형식 | 설명 및 쿼리 의미 |
|--|--|
| `datetime` | 일반적으로 이벤트 타임 스탬프를 나타내는 데이터 및 시간 정보 |
| `string` | 문자열 |
| `bool` | True 또는 False |
| `int` | 32비트 숫자 값  |
| `long` | 64비트 숫자 값 |

## <a name="use-sample-queries"></a>샘플 쿼리 사용

**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다. 이러한 쿼리를 실행하고 약간 수정해 보세요.

![고급 헌팅 창 이미지](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다. 페이지의 왼쪽에 있는 공유 쿼리 또는 GitHub 쿼리 리포지토리를 탐색합니다.

## <a name="access-query-language-documentation"></a>쿼리 언어 설명서에 액세스

Kusto 쿼리 언어와 지원되는 연산자에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서](https://docs.microsoft.com/azure/kusto/query/)를 참조하세요.

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

---
title: Microsoft 365 Defender에서 고급 구하기 쿼리 언어 알아보기
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 threat 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격, 사용자 지정 감지, 스키마, kusto, operators, 데이터 형식, powershell 다운로드, 쿼리 예제
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
ms.openlocfilehash: bb3caff642e752cb6d3941b697820fbad69ae23c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841979"
---
# <a name="learn-the-advanced-hunting-query-language"></a>고급 헌팅 쿼리 언어 알아보기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)를 기반으로 합니다. Kusto 연산자와 문을 사용 하 여 특수화 된 [스키마](advanced-hunting-schema-tables.md)에서 정보를 찾는 쿼리를 생성할 수 있습니다. 이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.

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

**[고급 구하기에서이 쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>쿼리 설명 및 검색할 테이블 지정
쿼리의 시작 부분에 요약 설명이 추가 되어 해당 내용을 설명 합니다. 이 설명은 나중에 쿼리를 저장 하 고 조직의 다른 사용자와 공유할 수 있도록 결정 하는 데 도움이 됩니다. 

```kusto
// Finds PowerShell execution events that could involve a download
```

일반적으로 쿼리 자체는 테이블 이름 다음에 파이프 ()로 시작 하는 여러 개의 요소로 시작 합니다 `|` . 이 예제에서는 먼저 두 개의 테이블을 통합 하 고  `DeviceProcessEvents` `DeviceNetworkEvents` 필요에 따라 파이프 된 요소를 추가 합니다.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>시간 범위 설정
첫 번째 파이프 요소는 이전 7 일간 범위가 지정 된 시간 필터입니다. 시간 범위를 제한 하면 쿼리가 제대로 실행 되 고 관리 가능한 결과가 반환 되며 시간 초과 되지 않습니다.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>특정 프로세스 확인
시간 범위 바로 뒤에 PowerShell 응용 프로그램을 나타내는 프로세스 파일 이름을 검색 합니다.

```kusto
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
쿼리에서 찾으려는 데이터를 명확 하 게 식별 하기 때문에 결과의 모양을 정의할 수 있습니다. `project` 특정 열을 반환 하 고 `top` 결과 수를 제한 합니다. 이러한 연산자를 사용 하면 결과의 형식이 적절 하 고 상당히 크고 프로세스를 간편 하 게 수행할 수 있습니다.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

**쿼리 실행** 을 선택 하 여 결과를 확인 합니다. 쿼리 편집기의 오른쪽 위에 있는 확장 아이콘을 사용 하 여 검색 쿼리와 결과에 초점을 집중 시킬 수 있습니다. 

![고급 구하기 쿼리 편집기의 확장 컨트롤 이미지](../../media/advanced-hunting-expand.png)

>[!TIP]
>쿼리 결과를 차트로 보고 필터를 빠르게 조정할 수 있습니다. 지침을 보려면 [쿼리 결과 작업에 대 한 내용을 읽어보십시오](advanced-hunting-query-results.md) .

## <a name="learn-common-query-operators"></a>일반적인 쿼리 연산자 학습

첫 번째 쿼리를 실행 하 고 해당 구성 요소에 대 한 일반적인 개념을 배웠습니다. 약간 역 추적 하 여 몇 가지 기본 사항을 배울 시간입니다. 고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.

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

## <a name="understand-data-types"></a>데이터 형식 이해

고급 구하기에서는 다음과 같은 일반적인 형식을 비롯 하 여 데이터 형식에 대 한 Kusto 지원 합니다.

| 데이터 형식 | 설명 및 쿼리 의미 |
|--|--|
| `datetime` | 일반적으로 이벤트 타임 스탬프를 나타내는 데이터 및 시간 정보입니다. [지원 되는 datetime 형식 참조](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | 작은따옴표 () 나 큰따옴표 ()로 묶인 u t f-8의 문자열 `'` `"` 입니다. [문자열에 대해 자세히 읽기](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | 이 데이터 형식은 `true` 또는 `false` 상태를 지원 합니다. [지원 되는 리터럴 및 연산자를 참조 하세요.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32 비트 정수  |
| `long` | 64 비트 정수 |

이러한 데이터 형식에 대 한 자세한 내용을 보려면 [Kusto 스칼라 data types를 참조](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)하세요.

## <a name="get-help-as-you-write-queries"></a>쿼리 작성시 도움말 보기
다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.
- **Autosuggest** -쿼리를 작성할 때 고급 사냥은 IntelliSense의 추천 단어를 제공 합니다. 
- **스키마 트리** -테이블 및 해당 열 목록이 포함 된 스키마 표현이 작업 영역 옆에 제공 됩니다. 자세한 내용을 보려면 항목 위로 마우스를 가져갑니다. 항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.
- **[스키마 참조](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** -테이블 및 열 설명과 관련 된 포털 내 참조 및 지원 되는 이벤트 유형 ( `ActionType` 값) 및 예제 쿼리

## <a name="work-with-multiple-queries-in-the-editor"></a>편집기에서 여러 쿼리 작업
쿼리 편집기를 사용 하 여 여러 쿼리를 테스트해 볼 수 있습니다. 여러 쿼리를 사용 하려면 다음을 수행 합니다.

- 각 쿼리를 빈 줄로 구분 합니다.
- 쿼리를 실행 하기 전에 쿼리 부분에 커서를 놓고 선택 합니다. 이렇게 하면 선택한 쿼리만 실행 됩니다. 다른 쿼리를 실행 하려면 그에 따라 커서를 이동 하 고 **쿼리 실행** 을 선택 합니다.

![쿼리가 여러 개 있는 쿼리 편집기 이미지](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>샘플 쿼리 사용

**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다. 이러한 쿼리를 실행하고 약간 수정해 보세요.

![고급 헌팅 창 이미지](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다. 페이지의 왼쪽에 있는 공유 쿼리 또는 [GitHub 쿼리 저장소](https://aka.ms/hunting-queries)를 탐색 합니다.

## <a name="access-query-language-documentation"></a>쿼리 언어 설명서에 액세스

Kusto 쿼리 언어와 지원되는 연산자에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서](https://docs.microsoft.com/azure/kusto/query/)를 참조하세요.

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

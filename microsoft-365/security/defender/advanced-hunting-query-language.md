---
title: 헌팅 쿼리 언어의 고급 Microsoft 365 Defender
description: 첫 번째 위협 헌팅 쿼리를 만들고 고급 헌팅 쿼리 언어의 일반적인 연산자와 기타 요소에 대한 정보를 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 언어, 학습, 첫 번째 쿼리, 원격 분석, 이벤트, 원격 분석, 사용자 지정 검색, schema, kusto, 연산자, 데이터 형식, powershell 다운로드, 쿼리 예제
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a253d1224f1c7a0e0be0b5478efcc78204cb4a27
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214662"
---
# <a name="learn-the-advanced-hunting-query-language"></a>고급 헌팅 쿼리 언어 알아보기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender

고급 헌팅은 [Kusto 쿼리 언어](/azure/kusto/query/)를 기반으로 합니다. Kusto 연산자 및 문을 사용하여 특수한 Schema에서 정보를 찾는 [쿼리를 구성할 수 있습니다.](advanced-hunting-schema-tables.md) 이러한 개념을 보다 잘 이해하려면 첫 번째 쿼리를 실행합니다.

## <a name="try-your-first-query"></a>첫 번째 쿼리 시도하기

Microsoft 365 Defender 포털에서 헌팅으로  이동하여 첫 번째 쿼리를 실행합니다. 다음 예제를 사용합니다.

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

**[고급 헌팅에서 이 쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>쿼리를 설명하고 검색할 테이블 지정
쿼리의 시작부에 해당 설명을 설명하는 짧은 설명이 추가되었습니다. 이 설명은 나중에 쿼리를 저장하고 조직의 다른 사람들과 공유하기로 결정할 때 도움이 됩니다. 

```kusto
// Finds PowerShell execution events that could involve a download
```

쿼리 자체는 일반적으로 테이블 이름으로 시작하고 그 다음에 파이프()로 시작하는 여러 요소가 차례로 `|` 실행됩니다. 이 예제에서는 먼저 두 테이블의 조합을 만들고 , 및 파이프된 요소를 필요한 경우  `DeviceProcessEvents` `DeviceNetworkEvents` 추가합니다.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>시간 범위 설정
첫 번째 파이프된 요소는 이전 7일로 범위가 지정되는 시간 필터입니다. 시간 범위를 제한하면 쿼리가 잘 수행되고 관리 가능한 결과를 반환하며 시간 초과를 방지하는 데 도움이 됩니다.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>특정 프로세스 확인
시간 범위 다음에 PowerShell 응용 프로그램을 나타내는 프로세스 파일 이름을 검색합니다.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>특정 명령 문자열 검색
그런 다음 쿼리는 일반적으로 PowerShell을 사용하여 파일을 다운로드하는 데 사용되는 명령줄에서 문자열을 검색합니다.

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
이제 쿼리가 찾고자 하는 데이터를 명확하게 식별하므로 결과 모양을 정의할 수 있습니다. `project` 특정 열을 반환하고 결과 `top` 수를 제한합니다. 이러한 연산자는 결과가 잘 형식화되어 있으며 상당히 크고 처리하기 쉬운지 보장하는 데 도움이 됩니다.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

결과를 **표시하려면** 쿼리 실행을 선택합니다. 쿼리 편집기 오른쪽 위에 있는 확장 아이콘을 사용하여 헌팅 쿼리 및 결과에 집중합니다. 

![고급 헌팅 쿼리 편집기에서 확장 컨트롤의 이미지입니다.](../../media/advanced-hunting-expand.png)

>[!TIP]
>쿼리 결과를 차트로 보고 필터를 빠르게 조정할 수 있습니다. 자세한 [지침은 쿼리 결과 사용에 대해 읽어 보시고](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>일반적인 쿼리 연산자 학습

첫 번째 쿼리를 실행하고 해당 구성 요소에 대한 일반적인 아이디어를 품고 있습니다. 이제 약간 뒤로 돌아가 몇 가지 기본을 배워야 합니다. 고급 헌팅에서 사용하는 Kusto 쿼리 언어는 다음을 포함하여 다양한 연산자를 지원합니다.

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

## <a name="understand-data-types"></a>데이터 유형 이해

고급 헌팅은 다음과 같은 일반적인 형식을 포함하여 Kusto 데이터 형식을 지원합니다.

| 데이터 형식 | 설명 및 쿼리 의미 |
|--|--|
| `datetime` | 일반적으로 이벤트 타임스탬프를 나타내는 데이터 및 시간 정보입니다. [지원되는 datetime 형식 참조](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | 작은 따옴표(`'`) 또는 큰 따옴표(`"`)로 묶인 UTF-8의 문자열입니다. [문자열에 대한 자세한 내용은](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | 이 데이터 유형은 `true` 또는 `false` 상태를 지원합니다. [지원되는 리터럴 및 연산자 참조](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32비트 정수  |
| `long` | 64비트 정수 |

이러한 데이터 형식에 대한 자세한 내용은 Kusto 스칼라 데이터 형식 [을 읽어 보아야 합니다.](/azure/data-explorer/kusto/query/scalar-data-types/)

## <a name="get-help-as-you-write-queries"></a>쿼리 작성시 도움말 보기
다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.
- **자동 제안**- 쿼리를 작성할 때 고급 헌팅은 쿼리의 제안을 IntelliSense. 
- **Schema tree**— 테이블 목록과 해당 열을 포함하는 Schema 표현이 작업 영역 옆에 제공됩니다. 자세한 내용을 보려면 항목 위로 마우스를 가져갑니다. 항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.
- **[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—테이블 및 열 설명과 함께 포털 내 참조와 지원되는 이벤트 유형(값) `ActionType` 및 샘플 쿼리

## <a name="work-with-multiple-queries-in-the-editor"></a>편집기에서 여러 쿼리 작업
쿼리 편집기를 사용하여 여러 쿼리를 실험할 수 있습니다. 여러 쿼리를 사용:

- 각 쿼리를 빈 줄로 구분합니다.
- 쿼리의 모든 부분에 커서를 배치하여 쿼리를 실행하기 전에 해당 쿼리를 선택합니다. 그러면 선택한 쿼리만 실행됩니다. 다른 쿼리를 실행하려면 그에 따라 커서를 이동하고 쿼리 **실행을 선택합니다.**

![쿼리가 여러 개 있는 쿼리 편집기 이미지입니다.](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>샘플 쿼리 사용

**시작** 섹션에서는 자주 사용하는 연산자를 사용하는 몇 가지 간단한 쿼리를 제공합니다. 이러한 쿼리를 실행하고 약간 수정해 보세요.

![고급 헌팅 창의 이미지입니다.](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>기본 쿼리 샘플과는 별도로 특정 위협 헌팅 시나리오에 대한 [공유 쿼리](advanced-hunting-shared-queries.md)에 액세스할 수도 있습니다. 페이지 또는 쿼리 리포지토리의 왼쪽에 있는 공유 [쿼리를 GitHub 탐색합니다.](https://aka.ms/hunting-queries)

## <a name="access-query-language-documentation"></a>쿼리 언어 설명서에 액세스

Kusto 쿼리 언어와 지원되는 연산자에 대한 자세한 내용은 [Kusto 쿼리 언어 설명서](/azure/kusto/query/)를 참조하세요.

>[!NOTE]
>이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다. [더 많은 Microsoft 365 Defender](m365d-enable.md) 사용하여 위협을 헌팅할 수 있습니다. Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 Defender [Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 쿼리 마이그레이션의 단계를 수행하여 고급 헌팅 워크플로를 끝점으로 이동할 수 있습니다.

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 결과로 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
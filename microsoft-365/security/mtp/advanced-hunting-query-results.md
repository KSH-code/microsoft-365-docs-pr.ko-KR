---
title: Microsoft Threat Protection의 고급 구하기 쿼리 결과 작업
description: Microsoft Threat Protection에서 상세하게 검색에 의해 반환 되는 쿼리 결과의 대부분 만들기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 스키마, kusto, microsoft 365, 마이크로소프트 Threat Protection, 시각화, 차트, 필터, 드릴 다운
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5d620a1c30466553470eec49d4f5ff8242d060bd
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412601"
---
# <a name="work-with-advanced-hunting-query-results"></a>고급 구하기 쿼리 결과 작업

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[고급 구하기](advanced-hunting-overview.md) 쿼리를 작성 하 여 매우 정확한 정보를 반환할 수 있지만 쿼리 결과를 사용 하 여 구체적인 작업과 지표를 보다 명확 하 게 파악 하 고 조사할 수도 있습니다. 쿼리 결과에 대해 다음 작업을 수행할 수 있습니다.

- 결과를 테이블 또는 차트로 보기
- 표 및 차트 내보내기
- 자세한 엔터티 정보 드릴 다운
- 쿼리를 결과에서 직접 조정 하거나 필터를 적용 합니다.

## <a name="view-query-results-as-a-table-or-chart"></a>쿼리 결과를 테이블 또는 차트로 보기
기본적으로 고급 구하기에서는 쿼리 결과를 테이블 형식 데이터로 표시 합니다. 차트와 같은 데이터를 표시할 수도 있습니다. 고급 구하기에서는 다음 보기를 지원 합니다.

| 보기 유형 | 설명 |
| -- | -- |
| **목차가** | 쿼리 결과를 테이블 형식으로 표시 합니다. |
| **세로 막대형 차트** | X 축에서 일련의 고유 항목을 해당 높이가 다른 필드의 숫자 값을 나타내는 세로 막대로 렌더링 합니다. |
| **누적 세로 막대형 차트** | X 축에 있는 일련의 고유한 항목을 해당 높이가 하나 이상의 다른 필드에 있는 숫자 값을 나타내는 누적 세로 막대로 렌더링 합니다. |
| **원형 차트** | 고유 항목을 나타내는 단면 원형을 렌더링 합니다. 각 원형의 크기는 다른 필드의 숫자 값을 나타냅니다. |
| **도넛형 차트** | 고유 항목을 나타내는 단면 원호를 렌더링 합니다. 각 호의 길이는 다른 필드의 숫자 값을 나타냅니다. |
| **꺾은선형 차트** | 일련의 고유한 항목에 숫자 값을 그리고 플롯 된 값을 연결 합니다. |
| **분산형 차트** | 일련의 고유한 항목에 숫자 값 그리기 |
| **영역형 차트** | 일련의 고유한 항목에 숫자 값을 그리고 플롯 된 값 아래에 섹션을 채웁니다. |

### <a name="construct-queries-for-effective-charts"></a>효율적인 차트 작성 쿼리
차트를 렌더링 하는 경우 고급 구하기에서는 관심 있는 열과 집계할 숫자 값을 자동으로 식별 합니다. 의미 있는 차트를 가져오려면 시각화 하려는 특정 값을 반환 하는 쿼리를 작성 합니다. 아래에는 몇 가지 예제 쿼리와 결과 차트가 나와 있습니다.

#### <a name="alerts-by-severity"></a>심각도 별 경고
연산자를 사용 `summarize` 하 여 차트로 표시할 값의 숫자를 가져옵니다. 아래 쿼리는 연산자를 사용 하 여 `summarize` 심각도 별 경고 수를 가져옵니다.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
결과를 렌더링 하는 경우 세로 막대형 차트에서 각 심각도 값은 개별 열로 표시 됩니다.

![열 차트로 표시 되는 ](../../media/advanced-hunting-column-chart.jpg)
 *심각도에 따라 열 차트 쿼리 결과로* 표시 되는 고급 구하기 쿼리 결과 이미지

#### <a name="alert-severity-by-operating-system"></a>운영 체제별 경고 심각도
또한 연산자를 사용 `summarize` 하 여 여러 필드의 차트 값에 대 한 결과를 준비할 수 있습니다. 예를 들어 여러 운영 체제 (OS)에서 경고 심각도가 분산 되는 방식을 이해할 수 있습니다. 

아래 쿼리는 연산자를 사용 하 여 `join` 테이블에서 OS 정보를 가져온 `DeviceInfo` 후 `summarize` 와 열에서 모두 값을 계산 하는 데 사용 됩니다 `OSPlatform` `Severity` .

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
이러한 결과는 누적 세로 막대형 차트를 사용 하 여 시각화 하는 것이 가장 좋습니다.

![OS에의 한 경고에 대 한 누적 된 차트 쿼리 결과로 표시 되는 고급 구하기 쿼리 결과 이미지 ](../../media/advanced-hunting-stacked-chart.jpg)
 *및 누적 차트로 표시 되는 심각도*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>상위 10 개의 보낸 사람 도메인에 걸친 피싱 전자 메일
유한 하지 않은 값의 목록을 처리 하는 경우 연산자를 사용 `Top` 하 여 대부분의 인스턴스가 있는 값만 차트로 만들 수 있습니다. 예를 들어 가장 많이 피싱 전자 메일을 사용 하 여 상위 10 개의 보낸 사람 도메인을 가져오려면 아래 쿼리를 사용 합니다.

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
원형 차트 보기를 사용 하 여 상위 도메인 전체에 분포를 효과적으로 표시 합니다.

![](../../media/advanced-hunting-pie-chart.jpg)
*상위 보낸 사람 도메인에 걸친 피싱 전자 메일의 분포를 보여 주는 원형 차트 원형 차트로* 표시 되는 고급 구하기 쿼리 결과 이미지

#### <a name="file-activities-over-time"></a>시간에 따른 파일 활동
함수에 연산자를 사용 하 여 `summarize` `bin()` 시간에 따른 특정 지표와 관련 된 이벤트를 확인할 수 있습니다. 아래 쿼리는 파일 `invoice.doc` 을 30 분 간격으로 포함 하는 이벤트 수를 계산 하 여 해당 파일과 관련 된 작업의 스파이크를 보여 줍니다.

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
아래의 꺽은선형 차트는 다음과 같은 작업을 포함 하는 시간 기간을 명확 하 게 강조 표시 합니다 `invoice.doc` . 

![](../../media/advanced-hunting-line-chart.jpg)
*시간에 따른 파일 관련 이벤트 수를 보여주는* 꺾은선형 차트 차트로 표시 되는 고급 구하기 쿼리 결과 이미지


## <a name="export-tables-and-charts"></a>표 및 차트 내보내기
쿼리를 실행 한 후에는 **내보내기를** 선택 하 여 결과를 로컬 파일에 저장 합니다. 선택한 보기에 따라 결과를 내보낼 방법이 결정 됩니다.

- **표 보기** — 쿼리 결과를 Microsoft Excel 통합 문서로 테이블 형식으로 내보내기
- **모든 차트** -쿼리 결과가 렌더링 된 차트의 JPEG 이미지로 내보내집니다.

## <a name="drill-down-from-query-results"></a>쿼리 결과에서 드릴 다운
쿼리 결과에서 레코드를 빠르게 조사 하려면 해당 행을 선택 하 여 **레코드 검사** 패널을 엽니다. 이 패널에는 선택한 레코드를 기반으로 하는 다음과 같은 정보가 제공 됩니다.

- **자산** -레코드에서 찾은 주 자산의 주요 자산 (사서함, 장치 및 사용자)에 대 한 요약 된 보기 이며, enriched에는 위험 및 노출 수준 같은 사용 가능한 정보가 있습니다.
- **프로세스 트리** -사용 가능한 컨텍스트 정보를 사용 하 여 프로세스 정보 및 enriched가 포함 된 레코드에 대해 생성 됩니다. 일반적으로 더 많은 열을 반환 하는 쿼리는 보다 다양 한 프로세스 트리를 만들 수 있습니다.
- **모든 세부 정보** -레코드에 있는 열의 모든 값  

![레코드를 검사 하기 위한 패널이 있는 선택한 레코드의 이미지](../../media/mtp-ah/inspect-record.png)

컴퓨터, 파일, 사용자, IP 주소 또는 URL과 같은 쿼리 결과의 특정 엔터티에 대 한 자세한 정보를 보려면 엔터티 식별자를 선택 하 여 해당 엔터티에 대 한 자세한 프로필 페이지를 엽니다.

## <a name="tweak-your-queries-from-the-results"></a>결과에서 쿼리 조정
결과 집합의 값을 마우스 오른쪽 단추로 클릭하면 쿼리가 빠르게 향상됩니다. 옵션을 사용하여 다음을 수행할 수 있습니다.

- 선택한 값을 명시적으로 찾습니다 (`==`)
- 쿼리에서 선택한 값을 제외합니다 (`!=`)
- 쿼리에 값을 추가하는 고급 연산자를 사용합니다 (예: `contains`, `starts with` 및 `ends with`) 

![고급 구하기 결과 집합 이미지](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>쿼리 결과 필터링
오른쪽에 표시되는 필터는 결과 집합에 대한 요약을 제공합니다. 각 열에는 해당 열에 대해 발견된 고유 값과 인스턴스 수를 나열하는 자체적인 섹션이 있습니다.

`+` `-` 포함 하거나 제외할 값의 또는 단추를 선택 하 고 **쿼리 실행**을 선택 하 여 쿼리를 구체화 합니다.

![고급 헌팅 필터 이미지](../../media/advanced-hunting-filter.png)

필터를 적용하여 쿼리를 수정한 다음 쿼리를 실행하면 그에 따라 결과가 업데이트됩니다.

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)

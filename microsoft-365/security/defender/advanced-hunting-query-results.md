---
title: 고급 헌팅 쿼리 결과를 사용하여 작업할 Microsoft 365 Defender
description: 고급 헌팅을 통해 반환된 쿼리 결과를 대부분 Microsoft 365 Defender
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, 시각화, 차트, 필터, 드릴다운
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f78234da247835da0ad9c1ecbdaa9702a206f942
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206688"
---
# <a name="work-with-advanced-hunting-query-results"></a>고급 헌팅 쿼리 결과 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 헌팅 [](advanced-hunting-overview.md) 쿼리를 구성하여 매우 정확한 정보를 반환할 수 있는 반면, 쿼리 결과를 사용하여 더 많은 정보를 얻고 특정 활동 및 지표를 조사할 수도 있습니다. 쿼리 결과에 대해 다음 작업을 수행할 수 있습니다.

- 결과를 표 또는 차트로 보기
- 표 및 차트 내보내기
- 자세한 엔터티 정보로 드릴다운
- 결과에서 직접 쿼리 조정 또는 필터 적용

## <a name="view-query-results-as-a-table-or-chart"></a>테이블 또는 차트로 쿼리 결과 보기
기본적으로 고급 헌팅은 쿼리 결과를 테이블형 데이터로 표시됩니다. 차트와 동일한 데이터를 표시할 수도 있습니다. 고급 헌팅은 다음과 같은 보기를 지원합니다.

| 보기 유형 | 설명 |
| -- | -- |
| **표** | 쿼리 결과를 테이블 형식 형식으로 표시 |
| **열 차트** | x 축에 있는 일련의 고유한 항목을 높이가 다른 필드의 숫자 값을 나타내는 세로 막대로 렌더링합니다. |
| **누적 세로형 차트** | x 축에 있는 일련의 고유한 항목을 높이가 하나 이상의 다른 필드의 숫자 값을 나타내는 누적 세로 막대로 렌더링합니다. |
| **파이 차트** | 고유한 항목을 나타내는 섹션 파이를 렌더링합니다. 각 파이의 크기는 다른 필드의 숫자 값을 나타냅니다. |
| **도넛형 차트** | 고유한 항목을 나타내는 섹션 호를 렌더링합니다. 각 호의 길이는 다른 필드의 숫자 값을 나타냅니다. |
| **꺾은선형 차트** | 일련의 고유한 항목에 대한 숫자 값을 그리며 그루팅된 값을 연결합니다. |
| **분산형 차트** | 일련의 고유 항목에 대한 숫자 값을 그리게 합니다. |
| **영역형 차트** | 일련의 고유 항목에 대한 숫자 값을 그리고 그림을 그리게 하는 값 아래에 구역을 채우는 경우 |

### <a name="construct-queries-for-effective-charts"></a>유효 차트에 대한 쿼리 생성
차트를 렌더링할 때 고급 헌팅은 자동으로 관심 열과 집계할 숫자 값을 식별합니다. 의미 있는 차트를 얻기 위해 시각화하려는 특정 값을 반환하는 쿼리를 생성합니다. 다음은 몇 가지 예제 쿼리와 결과 차트입니다.

#### <a name="alerts-by-severity"></a>심각도에 따라 알림
연산자를 사용하여 차트에 사용할 값의 `summarize` 수를 구할 수 있습니다. 아래 쿼리는 연산자를 사용하여 심각도에 따라 경고 `summarize` 수를 구합니다.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
결과를 렌더링할 때 열 차트에는 각 심각도 값이 별도의 열로 표시됩니다.

![열 차트로 표시되는 고급 헌팅 쿼리 결과의 이미지입니다. ](../../media/advanced-hunting-column-chart.jpg)
 *열 차트로 표시되는* 심각도에 따라 경고에 대한 쿼리 결과

#### <a name="alert-severity-by-operating-system"></a>운영 체제의 경고 심각도
연산자를 사용하여 여러 필드의 차트 값에 대한 `summarize` 결과를 준비할 수도 있습니다. 예를 들어 운영 체제(OS)에 경고 심각도가 분산되어 있는 방법을 이해해야 할 수 있습니다. 

아래 쿼리는 연산자를 사용하여 테이블에서 OS 정보를 끌어와서 및 열의 값을 계산하는 `join` `DeviceInfo` 데 `summarize` `OSPlatform` `Severity` 사용합니다.

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
이러한 결과는 누적 세로형 차트를 사용하여 가장 잘 시각화됩니다.

![누적 차트로 표시되는 고급 헌팅 쿼리 결과의 이미지입니다. ](../../media/advanced-hunting-stacked-chart.jpg)
 *누적 차트로 표시되는 OS의* 경고 및 심각도에 대한 쿼리 결과

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>상위 10개 보낸 사람 도메인의 피싱 전자 메일
유한하지 않은 값 목록을 다루는 경우 연산자를 사용하여 대부분의 인스턴스가 있는 값만 차트로 `Top` 만들 수 있습니다. 예를 들어 피싱 전자 메일이 가장 많은 상위 10개 보낸 사람 도메인을 얻은 경우 아래 쿼리를 사용합니다.

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
파이 차트 보기를 사용하여 최상위 도메인에 대한 배포를 효과적으로 보여 주면 됩니다.

![고급 헌팅 쿼리 결과가 파이 차트로 표시되는 이미지입니다. ](../../media/advanced-hunting-pie-chart.jpg)
 상위 보낸 사람 도메인에 걸쳐 피싱 전자 메일 *배포를 보여주는 파이 차트*

#### <a name="file-activities-over-time"></a>시간의에 대한 파일 활동
함수와 함께 연산자를 사용하면 시간이 지날 때 특정 표시기가 `summarize` 관련된 이벤트를 확인할 수 `bin()` 있습니다. 아래 쿼리는 해당 파일과 관련된 활동의 스파이크를 표시하기 위해 30분 간격으로 파일이 관련된 이벤트를 `invoice.doc` 계산합니다.

```kusto
CloudAppEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
아래 라인 차트는 관련 활동이 더 많은 기간을 명확하게 `invoice.doc` 강조합니다. 

![고급 헌팅 쿼리 결과가 라인 차트로 표시되는 이미지입니다. ](../../media/advanced-hunting-line-chart.jpg)
 시간의 지난 파일 관련 이벤트 *수를 보여 주는* 라인 차트


## <a name="export-tables-and-charts"></a>표 및 차트 내보내기
쿼리를 실행한 후 내보내기 를 **선택하여** 결과를 로컬 파일에 저장합니다. 선택한 보기에 따라 결과가 내보내는 방식이 결정됩니다.

- **테이블 보기** - 쿼리 결과가 테이블 형식의 통합 문서로 Microsoft Excel
- **모든 차트** - 쿼리 결과가 렌더링된 차트의 JPEG 이미지로 내보내집니다.

## <a name="drill-down-from-query-results"></a>쿼리 결과에서 드릴다운
쿼리 결과에서 레코드를 빠르게 검사하려면 해당 행을 선택하여 레코드 검사 **패널을 여는 방법을** 선택합니다. 패널은 선택한 레코드에 따라 다음 정보를 제공합니다.

- **자산** - 레코드에 있는 주요 자산(사서함, 장치 및 사용자)에 대한 요약된 보기, 위험 및 노출 수준과 같은 사용 가능한 정보로 향상
- **프로세스 트리** - 프로세스 정보가 있는 레코드에 대해 생성되어 사용 가능한 상황 정보를 사용하여 강화됩니다. 일반적으로 더 많은 열을 반환하는 쿼리의 경우 프로세스 트리가 더 다양할 수 있습니다.
- **모든 세부 정보** - 레코드의 열에 있는 모든 값  

![레코드를 검사하기 위한 패널이 있는 선택한 레코드의 이미지입니다.](../../media/mtp-ah/inspect-record.png)

컴퓨터, 파일, 사용자, IP 주소 또는 URL과 같은 쿼리 결과의 특정 엔터티에 대한 자세한 내용을 확인하려면 엔터티 식별자를 선택하여 해당 엔터티에 대한 자세한 프로필 페이지를 열 수 있습니다.

## <a name="tweak-your-queries-from-the-results"></a>결과에서 쿼리 조정
결과 집합의 값을 마우스 오른쪽 단추로 클릭하면 쿼리가 빠르게 향상됩니다. 옵션을 사용하여 다음을 수행할 수 있습니다.

- 선택한 값을 명시적으로 찾습니다 (`==`)
- 쿼리에서 선택한 값을 제외합니다 (`!=`)
- 쿼리에 값을 추가하는 고급 연산자를 사용합니다 (예: `contains`, `starts with` 및 `ends with`) 

![고급 헌팅 결과 집합의 이미지입니다.](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>쿼리 결과 필터링
오른쪽에 표시되는 필터는 결과 집합에 대한 요약을 제공합니다. 각 열에는 해당 열에 대해 발견된 고유 값과 인스턴스 수를 나열하는 자체적인 섹션이 있습니다.

포함하거나 제외하려는 값에서 또는 단추를 선택한 다음 쿼리 실행 을 선택하여 쿼리를 `+` `-` **구체화합니다.**

![고급 헌팅 필터의 이미지입니다.](../../media/advanced-hunting-filter.png)

필터를 적용하여 쿼리를 수정한 다음 쿼리를 실행하면 그에 따라 결과가 업데이트됩니다.

>[!NOTE]
>이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다. [더 많은 Microsoft 365 Defender](m365d-enable.md) 사용하여 위협을 헌팅할 수 있습니다. Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 Defender [Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 쿼리 마이그레이션의 단계를 수행하여 고급 헌팅 워크플로를 끝점으로 이동할 수 있습니다.

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)

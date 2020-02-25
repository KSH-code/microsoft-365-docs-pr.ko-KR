---
title: Microsoft Threat Protection의 고급 헌팅 모범 사례
description: 고급 헌팅을 사용할 때 빠르고 효과적 이며 오류가 없는 위협 헌팅 쿼리를 작성하는 방법을 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 스키마, kusto, timeout, 명령줄, 프로세스 id
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
ms.openlocfilehash: a859aa201b43813d6c66a797cbfee160051d5103
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235067"
---
# <a name="advanced-hunting-query-best-practices"></a>고급 헌팅 쿼리 모범 사례

**적용 대상:**
- Microsoft Threat Protection



## <a name="optimize-query-performance"></a>쿼리 성능 최적화
복잡한 쿼리를 실행하는 동안 이들 권장 사항을 수행하여 결과를 신속하게 확인하고 타임아웃을 방지하세요.
- 새 쿼리를 시도하는 경우에는 항상 `limit`를 사용 하여 매우 큰 결과 집합을 피해야 합니다. 또한 `count`를 사용하여 결과 집합의 크기를 초기에 평가할 수도 있습니다.
- 먼저 시간 필터를 사용합니다. 이상적으로는 쿼리를 짝수 일로 제한합니다.
- 쿼리의 처음부터 시간 필터 바로 다음에 대부분의 데이터를 제거할 것으로 예상되는 필터를 배치합니다.
- 전체 토큰을 찾는 경우 `contains`에서 `has` 연산자를 사용합니다.
- 모든 열에서 전체 텍스트 검색을 실행하는 대신 특정 열을 찾습니다.
- 테이블을 합치는 경우 먼저 행 수를 줄인 다음 표를 지정합니다.
- 합친 테이블의 필수 열만 `project`합니다.

>[!Tip]
>쿼리 성능을 개선하는 방법에 대한 자세한 내용은 [Kusto 쿼리 모범 사례](https://docs.microsoft.com/azure/kusto/query/best-practices)를 참조하세요.

## <a name="query-tips-and-pitfalls"></a>쿼리 팁 및 주의 사항

### <a name="queries-with-process-ids"></a>프로세스 ID가 포함된 쿼리
PID(프로세스 ID)는 Windows에서 재활용할 수 있으며 새 프로세스를 위해 다시 사용됩니다. 즉, 특정 프로세스에 대한 고유 식별자로는 사용할 수 없습니다.

특정 컴퓨터에서 프로세스에 대한 고유 식별자를 얻으려면 프로세스 생성 시간과 함께 프로세스 ID를 사용합니다. 프로세스 주변의 데이터를 합치거나 요약할 때는 컴퓨터 식별자에 대한 열 (`DeviceId` 또는 `DeviceName`), 프로세스 ID (`ProcessId` 또는 `InitiatingProcessId`), 프로세스 만들기 시간 (`ProcessCreationTime` 또는 `InitiatingProcessCreationTime`)을 포함합니다.

다음의 예제 쿼리는 포트 445(SMB)를 통해 10 개가 넘는 IP 주소에 액세스하는 프로세스를(잠정적으로 파일 공유를 검색하며) 찾습니다.

쿼리 예제:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

쿼리는 여러 프로세스를 동일한 프로세스 ID와 함께 사용하지 않고 단일 프로세스를 보여주는 `InitiatingProcessId`과 `InitiatingProcessCreationTime` 모두에 대해 요약을 합니다.

### <a name="queries-with-command-lines"></a>명령줄을 사용하는 쿼리

명령줄은 다양할 수 있습니다. 해당하는 경우 파일 이름을 필터링하고 유사 일치를 수행합니다.

여러 가지 방법으로 작업을 수행할 수 있는 명령줄을 만들 수 있습니다. 예를 들어 공격자는 환경 변수를 사용하거나 따옴표를 사용하여 파일 확장명이 없는 경로가 있거나 없는 이미지 파일을 참조할 수 있습니다. 또한 공격자는 매개 변수의 순서를 변경하거나 여러 개의 따옴표와 공백을 추가할 수도 있습니다.

명령줄을 사용하여 보다 영구적인 쿼리를 만들려면 다음의 방법을 적용합니다.

- 명령줄 필드에서 필터링하는 대신 파일 이름 필드에서 검색하여 알려진 프로세스(*net.exe* 또는 *psexec.exe* 등)를 식별합니다.
- 명령줄 인수에 대해 쿼리할 때 관련이 없는 여러 인수에서 특정 순서로 정확하게 일치하는 항목을 찾지 마세요. 대신 정규 표현식을 사용하거나 별도의 여러 포함 연산자를 사용합니다.
- 대/소문자를 구분하지 않는 일치 항목을 사용합니다. 예를 들어 `==`, `in`와 `contains_cs` 대신 `=~`, `in~` 그리고 `contains`을 사용합니다. 
- DOS 명령줄 난독 처리 기법을 완화하려면 따옴표를 제거, 쉼표를 공백으로 대체, 여러 개의 연속되는 공백을 하나의 공백으로 대체할 것을 고려합니다. 다른 접근 방법을 필요로 하는 더욱 복잡한 DOS 난독 기법이 있긴 하지만, 이들은 가장 일반적인 문제를 해결하는 데 도움이 될 수 있습니다.

다음의 예제에서는 *net.exe* 파일을 검색 하여 Windows Defender 방화벽 서비스를 중지하는 다양한 방법을 보여줍니다.

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a>관련 주제
- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 사냥](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)

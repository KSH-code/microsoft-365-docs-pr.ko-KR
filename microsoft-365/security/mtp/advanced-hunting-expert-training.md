---
title: 고급 헌팅에 대한 전문 교육을 받을 수 있습니다.
description: 고급 헌팅 전문가의 무료 교육 및 지침
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 언어, 교육, 시나리오, 고급 기본, 비디오, 단계별
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d7c2ccb12cb096359e558af9e1b4a962a9130be5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929637"
---
# <a name="get-expert-training-on-advanced-hunting"></a>고급 헌팅에 대한 전문 교육을 받을 수 있습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

새로운 보안 분석가 및 경험 있는 위협 헌터를 위한 웹캐스트 시리즈인 사도 추적을 통해 고급 헌팅에 대한 지식을 빠르게 향상합니다. 시리즈는 복잡한 쿼리를 만들기 위한 기본적인 방법을 안내합니다. 기본 사항에 대한 첫 번째 비디오로 시작하거나 환경 수준에 맞는 고급 비디오로 이동하세요.


| 제목 | 설명 | 감시 | 쿼리 | 
|--|--|--|--|
| 에피소드 1: KQL 기본 사항 | 이 에피소드는 Microsoft 365 Defender의 고급 헌팅의 기본을 다산합니다. 사용 가능한 고급 헌팅 데이터와 기본 KQL 구문 및 연산자에 대해 자세히 알아보고, | [](https://youtu.be/0D9TkGjeJwM?t=351) YouTube(54:14) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| 에피소드 2: 조인 | 고급 헌팅의 데이터와 표를 함께 조인하는 방법에 대해 계속 학습합니다. 기본 Kusto 조인에 대해 알아보고, 조인하고, 조인하고, 기본 Kusto 조인의 미주를 `inner` `outer` `unique` `semi` `innerunique` 이해합니다. | [](https://youtu.be/LMrO6K5TWOU?t=297) YouTube(53:33) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| 에피소드 3: 데이터 요약, 피벗 및 시각화 | 데이터를 필터링, 조작 및 조인하는 방법을 배웠습니다. 이제 데이터를 요약, 수량화, 피벗 및 시각화해야 합니다. 이 에피소드에서는 운영자 및 다양한 계산에 대해 설명하는 동시에 추가 테이블을 `summarize` 소개합니다. 또한 데이터 집합을 통찰력을 추출하는 데 도움이 되는 차트로 전환하는 방법을 배워야 합니다. | [](https://youtu.be/UKnk9U1NH6Y?t=296) YouTube(48:52) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| 에피소드 4: 헌트해 보세요! 인시던트 추적에 KQL 적용 | 이 에피소드에서 일부 공격자 활동을 추적하는 방법을 배워야 합니다. Kusto 및 고급 헌팅에 대한 향상된 이해를 사용하여 공격을 추적합니다. 사이버 보안 ABC를 포함하여 현장에서 사용되는 실제 트릭과 인시던트 대응에 적용하는 방법을 학습합니다. | [](https://youtu.be/2EUxOc_LNd8?t=291) YouTube(59:36) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>CSL 파일을 사용하는 방법
에피소드를 시작하기 전에 [GitHub에서 해당 Kusto CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) 파일에 액세스하고 해당 콘텐츠를 고급 헌팅 쿼리 편집기로 복사합니다. 에피소드를 볼 때 복사된 콘텐츠를 사용하여 스피커를 팔로우하고 쿼리를 실행할 수 있습니다. 

CSL 파일의 다음 발췌에는 주석으로 표시된 포괄적인 지침 집합이 `//` 표시됩니다.

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

동일한 CSL 파일에는 아래 표시된 설명 앞과 뒤의 쿼리가 포함됩니다. 편집기에서 쿼리가 여러 개 있는 특정 쿼리를 실행하려면 [커서를](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)해당 쿼리로 이동하고 쿼리 **실행을 선택합니다.**   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [고급 헌팅 쿼리 언어 알아보기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

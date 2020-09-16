---
title: 고급 구하기에 대 한 전문 교육 받기
description: 고급 구하기 전문가의 무료 교육 및 지침
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 언어, 교육, 시나리오, 기본에서 고급, 동영상, 단계별
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
ms.openlocfilehash: 23f35c087d55208f7251a6b921cfe7532616742a
ms.sourcegitcommit: 62a8c226422eac9c085cc886b4836b037f95ef6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47840766"
---
# <a name="get-expert-training-on-advanced-hunting"></a>고급 구하기에 대 한 전문 교육 받기

**적용 대상:**
- Microsoft 위협 방지

새 보안 분석가 및 seasoned threat hunters에 대 한 웹캐스트 시리즈를 추적 하 여 고급 구하기에 대 한 지식을 신속 하 게 개선 _합니다_. 계열에서는 사용자가 복잡 한 쿼리를 직접 만드는 모든 방법의 기본 개념을 안내 합니다. 기본 비디오로 시작 하거나 환경 수준에 적합 한 고급 비디오로 이동 합니다.


| 제목 | 설명 | 조사식 | 쿼리하도록 | 
|--|--|--|--|
| 에피소드 1: KQL 기본 | 이 에피소드에는 Microsoft Threat Protection의 고급 구하기에 대 한 기본 사항이 포함 되어 있습니다. 사용 가능한 고급 구하기 데이터 및 기본 KQL 구문 및 연산자에 대해 알아봅니다. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| 에피소드 2: 조인 | 고급 구하기의 데이터에 대해 배우고 테이블을 함께 조인 하는 방법을 계속 설명 합니다. `inner` `outer` `unique` `semi` 기본 kusto의 nuances에 대해 알아보고,, 및 참가를 이해 `innerunique` 합니다. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| 에피소드 3: 데이터 요약, 피벗 및 시각화 | 데이터를 필터링, 조작 및 조인 하는 방법을 배웠으므로 이제 요약, 수량화, 피벗 및 시각화를 확인 해야 합니다. 이 에피소드에서는 `summarize` 연산자 및 다양 한 계산에 대해 설명 하 고 스키마에 추가 테이블을 소개 합니다. 또한 데이터 집합을 정보를 추출 하는 데 도움이 되는 차트로 변환 하는 방법에 대해서도 알아봅니다. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| 에피소드 4: 이번에는 사냥을 사용 합니다. 인시던트 추적에 KQL 적용 | 이 에피소드에서는 일부 공격자 활동을 추적 하는 방법을 알아봅니다. 여기서는 Kusto 및 고급 사냥에 대 한 향상 된 이해를 통해 공격을 추적 합니다. Cybersecurity의 ABCs와이를 인시던트 응답에 적용 하는 방법을 비롯 하 여 필드에 사용 되는 실제 트릭에 대해 알아봅니다. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>CSL 파일을 사용 하는 방법
에피소드를 시작 하기 전에 [GitHub의 해당 Kusto CSL 파일](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) 에 액세스 하 여 해당 콘텐츠를 고급 구하기 쿼리 편집기에 복사 합니다. 에피소드를 볼 때 복사한 콘텐츠를 사용 하 여 스피커를 따르고 쿼리를 실행할 수 있습니다. 

CSL 파일에서 발췌 한 다음은 설명과 함께 표시 되는 포괄적인 지침 집합을 보여 줍니다 `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

동일한 CSL 파일에는 아래에 표시 된 것 처럼 설명의 전후에 쿼리가 포함 됩니다. [편집기에서 쿼리를 여러 개](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)사용 하 여 특정 쿼리를 실행 하려면 해당 쿼리로 커서를 이동 하 고 **쿼리 실행**을 선택 합니다.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
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
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
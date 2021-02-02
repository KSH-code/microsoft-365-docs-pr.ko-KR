---
title: Microsoft 365 Defender 고급 헌팅의 이름 변경 사항
description: 고급 헌팅chema에서 이름 변경 테이블 및 열 추적 및 검토
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066872"
---
# <a name="advanced-hunting-schema---naming-changes"></a>고급 헌팅 스마 - 이름 변경

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 [헌팅 스마는](advanced-hunting-schema-tables.md) 정기적으로 업데이트되어 새 테이블과 열을 추가합니다. 사용자 환경을 개선하기 위해 기존 열 이름을 바꾸거나 바꾸는 경우도 있습니다. 이 문서를 참조하여 쿼리에 영향을 줄 수 있는 이름 변경 내용을 검토하세요.

사용자 지정 검색 규칙에 사용되는 쿼리를 포함하여 보안 센터에 저장된 쿼리에 이름 변경 내용이 자동으로 적용됩니다. 이러한 쿼리를 수동으로 업데이트할 필요는 없습니다. 그러나 다음 쿼리를 업데이트해야 합니다.
- API를 사용하여 실행된 쿼리
- 보안 센터 외부에 저장된 쿼리

## <a name="december-2020"></a>2020년 12월

| 테이블 이름 | 원래 열 이름 | 새 열 이름 | 변경 이유
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | 고객 피드백 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | 고객 피드백 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | 고객 피드백 |

## <a name="january-2021"></a>2021년 1월

| 열 이름 | 원래 값 이름 | 새 값 이름 | 변경 이유
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | 바이러스 검사 | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  사용자 지정 TI | Rebranding |
| `DetectionSource` | OfficeATP | Office 365용 Microsoft Defender | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    ID용 Microsoft Defender | Rebranding |
| `DetectionSource` | CustomDetection   | 사용자 지정 검색 | Rebranding |
| `DetectionSource` | AutomatedInvestigation |자동화된 조사 | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft 위협 전문가 | Rebranding |
| `DetectionSource` | 제3자 TI | 제3자 센서 | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| 엔드포인트용 Microsoft Defender | Rebranding |
|`ServiceSource` |Microsoft 위협 방지   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Office 365용 Microsoft Defender | Rebranding |
| `ServiceSource` |Azure ATP    |ID용 Microsoft Defender | Rebranding |

`DetectionSource` 는 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다. `ServiceSource` 은 [AlertEvidence](advanced-hunting-alertevidence-table.md) 및 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다. 
## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
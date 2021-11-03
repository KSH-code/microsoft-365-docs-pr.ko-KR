---
title: 고급 헌팅 Microsoft 365 Defender 이름 변경
description: 고급 헌팅 스위마의 변경 테이블 및 열 이름 변경 추적 및 검토
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 데이터, 명명 변경, 이름 변경
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5006347ad8f4487c904fc6df4934bbaf612a1bdf
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60664239"
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
| `DetectionSource` | MCAS | Microsoft 클라우드 앱 보안 | Rebranding |
| `DetectionSource` | WindowsDefenderAtp| EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | 바이러스 검사 | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI | 사용자 지정 TI | Rebranding |
| `DetectionSource` | OfficeATP | Office 365용 Microsoft Defender | Rebranding |
| `DetectionSource` | MTP | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP | ID용 Microsoft Defender | Rebranding |
| `DetectionSource` | CustomDetection | 사용자 지정 검색 | Rebranding |
| `DetectionSource` | AutomatedInvestigation |자동화된 조사 | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft 위협 전문가 | Rebranding |
| `DetectionSource` | 제3자 TI | 제3자 센서 | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| 엔드포인트용 Microsoft Defender | Rebranding |
|`ServiceSource` |Microsoft 위협 방지 | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP |Office 365용 Microsoft Defender | Rebranding |
| `ServiceSource` |Azure ATP |ID용 Microsoft Defender | Rebranding |

`DetectionSource` 은 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다. `ServiceSource` 은 [AlertEvidence](advanced-hunting-alertevidence-table.md) 및 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다. 

## <a name="february-2021"></a>2021년 2월

1. [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) 및 [EmailEvents](advanced-hunting-emailevents-table.md) 테이블에서 및 열이 `MalwareFilterVerdict` `PhishFilterVerdict` 열로 `ThreatTypes` 대체됩니다. 및 `MalwareDetectionMethod` `PhishDetectionMethod` 열도 열로 `DetectionMethods` 대체했습니다. 이 간소화를 통해 새 열 아래에 추가 정보를 제공할 수 있습니다. 매핑은 아래에 제공됩니다.

    | 테이블 이름 | 원래 열 이름 | 새 열 이름 | 변경 이유
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | 추가 검색 방법 포함 |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 더 많은 위협 유형 포함 |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | 추가 검색 방법 포함 |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 더 많은 위협 유형 포함 |


2. 및 테이블에 전자 메일 위협에 대한 자세한 정보를 제공하기 위해 `EmailAttachmentInfo` `EmailEvents` `ThreatNames` 열이 추가되었습니다. 이 열에는 스팸 또는 피싱과 같은 값이 포함되어 있습니다.

3. [DeviceInfo](advanced-hunting-deviceinfo-table.md) 테이블에서 열은 고객 의견에 따라 `DeviceObjectId` `AadDeviceId` 열로 대체됩니다.

4. [DeviceEvents](advanced-hunting-deviceevents-table.md) 테이블에서는 작업 설명을 보다 잘 반영하기 위해 여러 ActionType 이름이 수정되었습니다. 변경 내용에 대한 자세한 내용은 아래에서 찾을 수 있습니다.

    | 테이블 이름 | Original ActionType 이름 | 새 ActionType 이름 | 변경 이유
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | 고객 피드백 |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | 고객 피드백 |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | 고객 피드백 |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | 고객 피드백 |

## <a name="march-2021"></a>2021년 3월

테이블이 `DeviceTvmSoftwareInventoryVulnerabilities` 사용되지 않습니다. 및 테이블을 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 바꾸는 것입니다.

## <a name="may-2021"></a>2021년 5월

테이블이 `AppFileEvents` 사용되지 않습니다. 이 표에는 테이블에 사용된 정보와 클라우드 서비스의 다른 `CloudAppEvents` `AppFileEvents` 활동이 포함되어 있습니다.

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [스키마에 대한 이해](advanced-hunting-schema-tables.md)
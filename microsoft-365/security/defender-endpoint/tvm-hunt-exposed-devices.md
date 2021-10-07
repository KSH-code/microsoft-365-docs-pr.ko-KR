---
title: 노출된 장치 헌팅
description: 보안 관리자위협 및 취약성 관리 IT 관리자 및 SecOps가 공동 작업을 하는 데 사용할 수 있는 방법에 대해 자세히 알아보습니다.
keywords: Endpoint-tvm 시나리오용 Microsoft Defender, 끝점용 Microsoft Defender, tvm, tvm 시나리오, 위협 & 취약성 노출 감소, 위협 및 취약성 감소, 보안 구성 향상, 장치용 Microsoft 보안 점수 증가, 장치용 Microsoft 보안 점수& 장치용 Microsoft 보안 점수, 노출 점수, 보안 제어
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3e413b511f080c23d76e616d83de0cb70a2f966f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210832"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>노출된 장치 헌트 - 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>고급 헌팅을 사용하여 취약성 있는 장치 찾기

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 위협 지표와 엔터티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스를 통해 알려진 위협과 잠재적 위협 모두에 대한 제약이 없는 헌팅을 할 수 있습니다. [고급 헌팅에 대해 자세히 알아보시다](advanced-hunting-overview.md)

### <a name="schema-tables"></a>스키마 표

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - 버전 정보 및 지원 종료 상태를 포함하여 장치에 설치된 소프트웨어 인벤토리입니다.

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - 장치에서 발견되는 소프트웨어 취약성 및 각 취약점을 해결 하는 사용 가능한 보안 업데이트 목록입니다.

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 악용 코드를 공개적으로 사용할 수 있는지 여부를 포함하여 공개적으로 공개된 취약성의 기술 자료입니다.

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - 위협 및 취약성 관리 장치의 다양한 보안 구성 상태를 나타내는 평가 이벤트입니다.

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - 위협 및 취약성 관리에서 장치를 평가하는 데 & 다양한 보안 구성의 기술 자료 다양한 표준 및 벤치마크에 대한 매핑 포함

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>높은 심각도 경고에 포함되는 장치 확인

1. 포털의  왼쪽 탐색 창에서 헌팅 \>  고급 헌팅으로 Microsoft 365 Defender 있습니다.

2. 열 이름에 익숙해지기 위해 TVM 고급 헌팅 스마마까지 아래로 스크롤합니다.

3. 다음 쿼리를 입력합니다.

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
let DeviceWithHighAlerts = AlertInfo
| where Severity == "High"
| project Timestamp, AlertId, Title, ServiceSource, Severity
| join kind=inner (AlertEvidence | where EntityType == "Machine" | project AlertId, DeviceId, DeviceName) on AlertId
| summarize HighSevAlerts = dcount(AlertId) by DeviceId;
let DeviceWithCriticalCve = DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId;
DeviceWithCriticalCve
| join kind=inner DeviceWithHighAlerts on DeviceId
| project DeviceId, DeviceName, NumOfVulnerabilities, HighSevAlerts
```

## <a name="related-topics"></a>관련 항목

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [보안 권장 사항](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [역할에 대한 위협 및 취약성 관리 액세스 구성](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [지능형 헌팅 개요](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [모든 고급 헌팅 테이블](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)

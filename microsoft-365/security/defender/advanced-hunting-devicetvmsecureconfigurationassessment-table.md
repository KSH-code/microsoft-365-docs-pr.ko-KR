---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessment 표
description: 고급 헌팅 계획의 DeviceTvmSecureConfigurationAssessment 표에서 보안 평가 이벤트에 대해 자세히 알아보습니다. 이러한 이벤트는 장치 정보, 보안 구성 세부 정보, 영향 및 규정 준수 정보를 제공합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 3487ced09cfd0bbd3a25f8e8124f84a05368d290
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2021
ms.locfileid: "61035973"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender


`DeviceTvmSecureConfigurationAssessment` 표의 각 행에는 [위협 및 취약성 관리](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)의 특정 보안 구성에 대한 평가 이벤트가 포함되어 있습니다. 이 참조를 사용하여 최신 평가 결과를 확인하고 장치가 호환되는지 확인합니다.

예를 들어 구성 평가 결과에서 표의 열에서 구성에 대한 텍스트 설명을 볼 수 있도록 이 테이블을 [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) 테이블과 함께 조인할 `ConfigurationId` `ConfigurationDescription` 수 `DeviceTvmSecureConfigurationAssessmentKB` 있습니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. Windows 11, Windows 10 및 Windows 같은 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.|
| `Timestamp` | 날짜 시간 | 레코드 생성 날짜 및 시간 |
| `ConfigurationId` | 문자열 | 특정 구성의 고유 식별자 |
| `ConfigurationCategory` | 문자열 | 구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어) |
| `ConfigurationSubcategory` | 문자열 | 구성이 속한 하위 범주나 하위 그룹 대부분의 경우 문자열은 특정 기능을 기술합니다. |
| `ConfigurationImpact` | 문자열 | 구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10) |
| `IsCompliant` | 부울 | 구성 또는 정책이 올바르게 구성되어 있는지 여부 |
| `IsApplicable` | 부울 | 구성 또는 정책이 장치에 적용되는지 여부를 나타냅니다. |
| `Context` | 문자열 | 구성 또는 정책에 대한 추가 상황 정보 |
| `IsExpectedUserImpact` | 부울 | 구성 또는 정책이 적용되는 경우 사용자에게 영향을 줄지 여부를 나타냅니다. |

이 예제 쿼리를 실행하여 비호환 바이러스 백신 구성이 있는 장치에 대한 정보를 표의 관련 구성 메타데이터와 함께 반환할 수 `DeviceTvmSecureConfigurationAssessmentKB` 있습니다.

```kusto
// Get information on devices with antivirus configurations issues
DeviceTvmSecureConfigurationAssessment
| where ConfigurationSubcategory == 'Antivirus' and IsApplicable == 1 and IsCompliant == 0
| join kind=leftouter (
    DeviceTvmSecureConfigurationAssessmentKB
    | project ConfigurationId, ConfigurationName, ConfigurationDescription, RiskDescription, Tags, ConfigurationImpact
) on ConfigurationId
| project DeviceName, OSPlatform, ConfigurationId, ConfigurationName, ConfigurationCategory, ConfigurationSubcategory, ConfigurationDescription, RiskDescription, ConfigurationImpact, Tags
```

## <a name="related-topics"></a>관련 주제

- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [위협 및 취약성 관리 개요](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
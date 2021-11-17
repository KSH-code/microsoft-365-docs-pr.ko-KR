---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표
description: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표에서 위협 및 취약성 관리로 평가되는 다양한 보안 구성에 대해 알아보세요.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 체계 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, MITRE ATT&CK 프레임워크, 기술 자료, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: bf65634e38d7676eaef20386b3effa828aa46f4b
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2021
ms.locfileid: "61035985"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender


고급 헌팅 계획의 표에는 위협 및 취약성 관리에서 확인한 다양한 보안 `DeviceTvmSecureConfigurationAssessmentKB` [구성에 대한 & 포함되어 있습니다.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 또한 위험 정보, 관련 산업 벤치마크 및 해당 MITRE ATT&CK 기법 및 전술을 포함합니다.

이 테이블은 이벤트나 레코드를 반환하지 않습니다. 반환된 평가에서 보안 구성에 대한 텍스트 정보를 보는 데 이 테이블을 [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) 테이블에 가입하는 `ConfigurationId` 것이 좋습니다.

예를 들어 테이블을 쿼리할 때 평가 결과에 나올 보안 구성을 `DeviceTvmSecureConfigurationAssessment` `ConfigurationDescription` 볼 수 있습니다. 이 테이블을 using 및 project에 조인하여 `DeviceTvmSecureConfigurationAssessment` 이 정보를 볼 수 `ConfigurationId` `ConfigurationDescription` 있습니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `ConfigurationId` | 문자열 | 특정 구성의 고유 식별자 |
| `ConfigurationImpact` | 문자열 | 구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10) |
| `ConfigurationName` | 문자열 | 구성 이름을 표시합니다. |
| `ConfigurationDescription` | 문자열 | 구성에 대한 설명 |
| `RiskDescription` | 문자열 | 관련 위험에 대한 설명 |
| `ConfigurationCategory` | 문자열 | 구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)|
| `ConfigurationSubcategory` | 문자열 |구성이 속한 하위 범주나 하위 그룹 대부분의 경우 이는 특정 기능이나 특징을 설명합니다. |
| `ConfigurationBenchmarks` | 문자열 | 동일하거나 유사한 구성을 제안하는 산업 벤치마크 목록 |
| `Tags` | 문자열 | 보안 구성을 식별하거나 분류하는 데 사용되는 다양한 특성을 나타내는 레이블 |
| `RemediationOptions` | 문자열 | 관련 위험을 줄이거나 해결하기 위해 권장되는 작업 |

이 예제 쿼리를 실행하여 관련 구성 메타데이터와 비호환 바이러스 백신 구성이 표에 있는 장치에 대한 정보를 반환할 수 `DeviceTvmSecureConfigurationAssessment` 있습니다.

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
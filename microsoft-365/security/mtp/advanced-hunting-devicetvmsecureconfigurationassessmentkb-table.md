---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표
description: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessmentKB 표에서 위협 및 취약성 관리로 평가되는 다양한 보안 구성에 대해 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description/threat & 취약성 관리, TVM, 장치 관리, 보안 구성, MITRE AT&T&접시 프레임 워크, 기술 자료, m b, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 2c16929555b3923086e249db61cebb3cf7af17c8
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648968"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**적용 대상:**
- Microsoft 위협 방지



고급 헌팅 스키마의 `DeviceTvmSecureConfigurationAssessmentKB` 표에는 [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)에서 확인되는 장치가 자동 업데이트를 보유하고 있는지에 대한 정보 등의 다양한 보안 구성 관련 정보가 포함되어 있습니다. 또한 위험 정보, 관련 산업 벤치마크 및 해당 MITRE ATT&CK 기법 및 전술을 포함합니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

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
| `RelatedMitreTechniques` | 문자열 | 구성과 관련된 Mitre ATT&CK 프레임워크 기법 목록 |
| `RelatedMitreTactics ` | 문자열 | 구성과 관련된 Mitre ATT&CK 프레임워크 전술 목록 |

## <a name="related-topics"></a>관련 항목

- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 id 간 헌트](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [위협 및 취약성 관리 개요](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

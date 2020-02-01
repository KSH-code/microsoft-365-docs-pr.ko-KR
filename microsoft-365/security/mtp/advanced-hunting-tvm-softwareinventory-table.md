---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareInventoryVulnerabilities 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareInventoryVulnerabilities 표에서 장치의 소프트웨어 인벤토리와 취약성에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, threat & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 보안 문제, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 92c06eb01abd13df22ae33e72d9663084b05f7ef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600295"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 헌팅 스키마의 `DeviceTvmSoftwareInventoryVulnerabilities` 표에는 이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 [위협 & 취약성 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 인벤토리가 포함되어 있습니다. 이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `OSPlatform` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 플랫폼 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `OSVersion` | 문자열 | 컴퓨터에서 실행 중인 운영 체제 버전 |
| `OSArchitecture` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 아키텍처 |
| `SoftwareVendor` | 문자열 | CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준 |
| `SoftwareName` | 문자열 | 소프트웨어 제품의 이름 |
| `SoftwareVersion` | 문자열 | 소프트웨어 제품의 버전 번호 |
| `CveId` | 문자열 | CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자 |
| `VulnerabilitySeverityLevel` | 문자열 | CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준 |



## <a name="related-topics"></a>관련 항목

- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [위협 및 취약성 관리 개요](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

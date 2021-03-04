---
title: 고급 헌팅의 DeviceTvmSoftwareVulnerabilities 테이블
description: 고급 헌팅 스위마의 DeviceTvmSoftwareVulnerabilities 표에 있는 각 취약점을 해결할 수 있는 사용 가능한 보안 업데이트 목록 및 장치에서 발견된 소프트웨어 취약점에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c5a143d835120339ade006dfd2dc394ec7c542d3
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423876"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

>[!IMPORTANT]
> 일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 시판된 제품과 관련이 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

고급 헌팅 계획의 표에는 설치된 소프트웨어 제품의 취약점에 대한 위협 & 취약성 관리 `DeviceTvmSoftwareVulnerabilities` 목록이 포함되어 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 있습니다. 이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다. 예를 들어 이 표를 사용하여 소프트웨어에 심각한 취약점이 있는 장치를 포함하는 이벤트를 헌팅할 수 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

>[!NOTE]
> 및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다. 처음 두 표에는 다양한 관리 활동을 알리거나 취약한 장치를 헌팅하는 데 도움이 되는 더 많은 열이 포함되어 있습니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `OSPlatform` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 플랫폼 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `OSVersion` | 문자열 | 컴퓨터에서 실행 중인 운영 체제 버전 |
| `OSArchitecture` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 아키텍처 |
| `SoftwareVendor` | 문자열 | 소프트웨어 공급업체의 이름 |
| `SoftwareName` | 문자열 | 소프트웨어 제품의 이름 |
| `SoftwareVersion` | 문자열 | 소프트웨어 제품의 버전 번호 |
| `CveId` | 문자열 | CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자 |
| `VulnerabilitySeverityLevel` | 문자열 | CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준 |
| `RecommendedSecurityUpdate` | 문자열 | 취약점을 해결하기 위해 소프트웨어 공급업체가 제공하는 보안 업데이트의 이름 또는 설명 |
| `RecommendedSecurityUpdateId` | 문자열 | 해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자 |



## <a name="related-topics"></a>관련 항목

- [사전 대응식 위협 탐지](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [위협 및 취약성 관리 개요](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

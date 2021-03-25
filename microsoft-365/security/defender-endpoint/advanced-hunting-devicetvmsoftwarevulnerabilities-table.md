---
title: 고급 헌팅의 DeviceTvmSoftwareVulnerabilities 테이블
description: 고급 헌팅 스위마의 DeviceTvmSoftwareVulnerabilities 표에 있는 각 취약점을 해결할 수 있는 사용 가능한 보안 업데이트 목록과 장치에서 발견된 소프트웨어 취약점에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076036"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

고급 헌팅 계획의 표에는 설치된 소프트웨어 제품의 취약점에 대한 위협 & 취약성 관리 `DeviceTvmSoftwareVulnerabilities` 목록이 포함되어 [](next-gen-threat-and-vuln-mgt.md) 있습니다. 이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다. 예를 들어 이 표를 사용하여 소프트웨어에 심각한 취약점이 있는 장치를 포함하는 이벤트를 헌팅할 수 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

>[!NOTE]
>및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다. 처음 두 표에는 취약점 관리 활동을 알리는 데 사용할 수 있는 열이 더 포함되어 있습니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `OSVersion` | 문자열 | 장치에서 실행되는 운영 체제 버전 |
| `OSArchitecture` | 문자열 | 장치에서 실행되는 운영 체제의 아키텍처 |
| `SoftwareVendor` | 문자열 | 소프트웨어 공급업체의 이름 |
| `SoftwareName` | 문자열 | 소프트웨어 제품의 이름 |
| `SoftwareVersion` | 문자열 | 소프트웨어 제품의 버전 번호 |
| `CveId` | 문자열 | CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자 |
| `VulnerabilitySeverityLevel` | 문자열 | CVSS 점수 및 위협 환경에 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준 |
| `RecommendedSecurityUpdate` | 문자열 | 취약점을 해결하기 위해 소프트웨어 공급업체가 제공하는 보안 업데이트의 이름 또는 설명 |
| `RecommendedSecurityUpdateId` | 문자열 | 해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자 |



## <a name="related-topics"></a>관련 항목

- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)

---
title: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표
description: 고급 헌팅 스키마의 DeviceTvmSoftwareVulnerabilitiesKB 표에서 위협 및 취약성 관리를 통해 추적하는 소프트웨어 취약성에 대해 알아봅니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 소프트웨어, 인벤토리, 취약성, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070924"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

고급 헌팅 스키마의 `DeviceTvmSoftwareVulnerabilitiesKB` 표에는 [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)에서 장치를 평가하는 취약성 목록이 포함되어 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-reference.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `CveId` | 문자열 | CVE(Common Vulnerabilities and Exposures) 시스템에서 보안 취약점에 할당된 고유 식별자 |
| `CvssScore` | 문자열 | CVSS(Common Vulnerability Scoring System)에서 보안 취약점에 할당된 심각도 점수 |
| `IsExploitAvailable` | 부울 | 취약점에 대한 악용 코드를 공개적으로 사용할 수 있는지 여부 |
| `VulnerabilitySeverityLevel` | 문자열 | CVSS 점수 및 위협의 영향을 받은 동적 요인에 따라 보안 취약성에 할당된 심각도 수준 |
| `LastModifiedTime` | 날짜/시간 | 항목 또는 관련된 메타 데이터가 마지막으로 수정된 날짜와 시간 |
| `PublishedDate` | 날짜/시간 | 취약점이 공개된 날짜 |
| `VulnerabilityDescription` | 문자열 | 취약점과 관련된 위험에 대한 설명 |
| `AffectedSoftware` | 문자열 | 취약점에 영향을 받는 모든 소프트웨어 제품 목록 |

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)

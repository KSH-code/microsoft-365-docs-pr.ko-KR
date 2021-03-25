---
title: 고급 헌팅 스키마의 DeviceTvmSecureConfigurationAssessment 표
description: 고급 헌팅 & DeviceTvmSecureConfigurationAssessment 표에서 위협 및 취약성 관리 보안 평가 이벤트에 대해 자세히 알아보습니다. 이러한 이벤트는 장치 정보와 보안 구성 세부 정보, 영향 및 규정 준수 정보를 제공합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 위협 & 취약성 관리, TVM, 장치 관리, 보안 구성, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075047"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

`DeviceTvmSecureConfigurationAssessment` 표의 각 행에는 [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)의 특정 보안 구성에 대한 평가 이벤트가 포함되어 있습니다. 이 참조를 사용하여 최신 평가 결과를 확인하고 장치가 호환되는지 확인합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.|
| `Timestamp` | 날짜 시간 |레코드 생성 날짜 및 시간 |
| `ConfigurationId` | 문자열 | 특정 구성의 고유 식별자 |
| `ConfigurationCategory` | 문자열 | 구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어) |
| `ConfigurationSubcategory` | 문자열 |구성이 속한 하위 범주나 하위 그룹 대부분의 경우 이는 특정 기능이나 특징을 설명합니다. |
| `ConfigurationImpact` | 문자열 | 구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10) |
| `IsCompliant` | 부울 | 구성 또는 정책이 올바르게 구성되어 있는지 여부 |
| `IsApplicable` | 부울 | 구성 또는 정책이 장치에 적용되는지 여부를 나타냅니다. |
| `Context` | 문자열 | 구성 또는 정책에 대한 추가 상황 정보 |
| `IsExpectedUserImpactCompliant` | 부울 | 구성 또는 정책이 적용되는 경우 사용자에게 영향을 줄지 여부를 나타냅니다. |

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
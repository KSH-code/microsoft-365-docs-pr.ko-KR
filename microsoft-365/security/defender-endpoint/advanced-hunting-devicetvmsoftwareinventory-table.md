---
title: 고급 헌팅 schema의 DeviceTvmSoftwareInventory 테이블
description: 고급 헌팅 스파이마의 DeviceTvmSoftwareInventory 표에서 장치의 소프트웨어 인벤토리에 대해 자세히 알아보습니다.
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408626"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

고급 헌팅 계획의 표에는 지원 종료 정보를 포함하여 현재 네트워크의 장치에 설치된 소프트웨어의 위협 및 취약성 관리 인벤토리가 `DeviceTvmSoftwareInventory` 포함되어 있습니다. [](next-gen-threat-and-vuln-mgt.md) 예를 들어 현재 취약한 소프트웨어 버전으로 설치된 장치와 관련된 이벤트를 헌팅할 수 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

DeviceTVMSoftwareInventory에는 위협 및 취약성 관리가 CPE(Common Platform Enumeration)와 일치할 수 있었던 모든 소프트웨어가 포함되어 있습니다.

>[!NOTE]
>및 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 테이블이 테이블을 `DeviceTvmSoftwareInventoryVulnerabilities` 대체했습니다. 처음 두 표에는 취약점 관리 활동을 알리는 데 사용할 수 있는 열이 더 포함되어 있습니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `DeviceId` | 문자열 | 서비스에서 장치의 고유 식별자입니다. |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN)입니다. |
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `OSVersion` | 문자열 | 장치에서 실행 중인 운영 체제의 버전입니다. |
| `OSArchitecture` | 문자열 | 장치에서 실행되는 운영 체제의 아키텍처입니다. |
| `SoftwareVendor` | 문자열 | 소프트웨어 공급업체의 이름입니다. |
| `SoftwareName` | 문자열 | 소프트웨어 제품의 이름입니다. |
| `SoftwareVersion` | 문자열 | 소프트웨어 제품의 버전 번호입니다. |
| `EndOfSupportStatus` | 문자열 | 지정된 EOS(지원 종료) 또는 EOL(수명 종료) 날짜를 상대로 소프트웨어 제품의 수명 주기 스테이지를 나타냅니다. |
| `EndOfSupportDate` | 문자열 | 소프트웨어 제품의 EOS(지원 종료) 또는 EOL(종료 날짜) |

## <a name="related-topics"></a>관련 항목

- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마에 대한 이해](advanced-hunting-schema-reference.md)
- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)

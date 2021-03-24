---
title: 고급 헌팅 스위마의 AlertInfo 테이블
description: 고급 헌팅 스커마의 AlertInfo 표에서 경고 생성 이벤트에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, 테이블, 열, 데이터 형식, 설명, AlertInfo, 경고, 심각도, 범주, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS 및 Azure ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bc81c9c8406a6e70df6ec38e3896ef9977a120e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071644"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



고급 `AlertInfo` 헌팅 schema의 표에는 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender의 경고에 대한 정보가 포함되어 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `AlertId` | 문자열 | 경고의 고유 식별자입니다. |
| `Title` | 문자열 | 경고의 제목입니다. |
| `Category` | 문자열 | 경고로 식별되는 위협 표시기 또는 위반 활동 유형 |
| `Severity` | 문자열 | 경고로 식별되는 위협 표시기 또는 위반 활동의 잠재적인 영향(높음, 중간 또는 낮음)을 표시합니다. |
| `ServiceSource` | 문자열 | 경고 정보를 제공한 제품 또는 서비스 |
| `DetectionSource` | 문자열 | 중요한 구성 요소 또는 활동을 식별한 감지 기술 또는 센서 |
| `AttackTechniques` | 문자열 | MITRE ATT&트리거한 활동과 관련된 CK 기술입니다. |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

---
title: 개요-고급 구하기
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365 및 microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e8f83b943e83c37ecf13af1221c043d413bd6b5
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347834"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 흥미로운 지표와 엔티티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스는 알려진 위협과 잠재적 위협 모두에 대한 제한없는 헌팅을 용이하게 합니다.

동일한 위협 검색 쿼리를 사용 하 여 사용자 지정 검색 규칙을 만들 수 있습니다. 이러한 규칙은 의심 스러운 위반 활동 및 잘못 된 컴퓨터를 포함 하 여 다양 한 이벤트 및 시스템 상태를 확인 하 고 응답 하기 위해 자동으로 실행 됩니다.

Microsoft 365 보안 센터에서 고급 구하기는 장치, 전자 메일, 앱 및 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security 및 Azure ATP의 id에 대 한 데이터를 포함 하 여 다양 한 작업 영역의 데이터를 확인 하는 쿼리를 지원 합니다. 고급 헌팅을 사용하려면 [Microsoft Threat Protection](mtp-enable.md)을 설정합니다.

## <a name="get-started-with-advanced-hunting"></a>고급 헌팅 시작

고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.

| 학습 목표 | 설명 | 리소스 |
|--|--|--|
| **언어에 대한 느낌을 받아보세요.** | 고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)을 기반으로 하며, 동일한 구문 및 연산자를 지원합니다. 첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다. | [쿼리 언어 개요](advanced-hunting-query-language.md) |
| **쿼리 결과 사용 방법 알아보기** | 결과를 보거나 내보낼 수 있는 다양 한 방법과 차트에 대해 알아봅니다. 쿼리를 신속 하 게 조정 하 고 드릴 다운 하 여 보다 다양 한 정보를 얻을 수 있는 방법을 알아봅니다. | [쿼리 결과 작업](advanced-hunting-query-results.md) |
| **스키마의 이해** | 스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요. 이는 데이터를 찾을 위치와 쿼리를 구성하는 방법을 결정하는 데 도움이 됩니다. | [스키마 참조](advanced-hunting-schema-tables.md) |
| **미리 정의 된 쿼리 활용** | 다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다. | [공유 쿼리 사용](advanced-hunting-shared-queries.md) |
| **쿼리 최적화** | 전자 메일 및 장치에서 데이터를 결합하는 효율적인 쿼리 및 쿼리를 만드는 방법에 대해 알아봅니다. | - [쿼리 모범 사례](advanced-hunting-shared-queries.md) <br>- [장치 및 전자 메일 간 헌트](advanced-hunting-best-practices.md) |
| **사용자 지정 검색 규칙 만들기** | 고급 구하기 쿼리를 사용 하 여 알림을 트리거하고 응답 작업을 자동으로 적용 하는 방법을 이해 합니다. | - [사용자 지정 검색 개요](custom-detections-overview.md)<br>- [사용자 지정 검색 규칙](custom-detection-rules.md) |

## <a name="get-access"></a>액세스 권한
고급 구하기 또는 기타 [Microsoft 위협 방지](microsoft-threat-protection.md) 기능을 사용 하려면 Azure AD에서 적절 한 역할을 할당 받아야 합니다. 끝점 데이터에 대 한 액세스는 Microsoft Defender ATP에서 역할 기반 액세스 제어 설정의 영향을 받습니다. [Microsoft Threat Protection 액세스 관리에 대해 자세히 알아봅니다.](mtp-permissions.md)

## <a name="get-help-as-you-write-queries"></a>쿼리 작성시 도움말 보기
다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.
- **Autosuggest** -쿼리를 작성할 때 고급 사냥은 IntelliSense의 추천 단어를 제공 합니다. 
- **스키마 참조** — 테이블 및 해당 열 목록이 포함된 스키마 참조가 작업 영역 옆에 제공됩니다. 자세한 내용을 보려면 항목 위로 마우스를 가져갑니다. 항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.

## <a name="related-topics"></a>관련 항목
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](custom-detections-overview.md)

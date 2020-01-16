---
title: Microsoft Threat Protection의 고급 헌팅 개요
description: Microsoft 365의 고급 검색 쿼리와 이를 사용하여 네트워크의 위협과 약점을 사전에 찾는 방법에 대해 알아보세요.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365 및 microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 791eee143c80e00a3fdb1fa4dbde8bbf41612e9a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210353"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다. 네트워크의 이벤트를 사전에 검사하여 흥미로운 지표와 엔티티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스는 알려진 위협과 잠재적 위협 모두에 대한 제한없는 헌팅을 용이하게 합니다.

Microsoft 365 보안 센터에서 고급 구하기는 전자 메일의 데이터를 제공 하 여 Microsoft Defender ATP, 등록 장치 및 Office 365 ATP의 데이터를 조회 하는 쿼리를 지원 합니다. 고급 헌팅을 사용하려면 [Microsoft Threat Protection](mtp-enable.md)을 설정합니다.

## <a name="get-started-with-advanced-hunting"></a>고급 헌팅 시작

고급 헌팅을 빠르게 시작하고 실행하려면 몇가지 단계를 수행하는 것이 좋습니다.

| 학습 목표 | 설명 | 리소스 |
|--|--|--|
| **언어에 대한 느낌을 받아보세요.** | 고급 헌팅은 [Kusto 쿼리 언어](https://docs.microsoft.com/azure/kusto/query/)을 기반으로 하며, 동일한 구문 및 연산자를 지원합니다. 첫 번째 쿼리를 실행하여 쿼리 언어 학습을 시작합니다. | [쿼리 언어 개요](advanced-hunting-query-language.md) |
| **스키마의 이해** | 스키마와 해당 열에 있는 테이블에 대한 이해를 높이세요. 이는 데이터를 찾을 위치와 쿼리를 구성하는 방법을 결정하는 데 도움이 됩니다. | [스키마 참조](advanced-hunting-schema-tables.md) |
| **미리 정의된 쿼리 사용** | 다양한 위협 헌팅 시나리오를 다루는 미리 정의된 쿼리 모음을 탐색합니다. | [공유 쿼리 사용](advanced-hunting-shared-queries.md)
| **쿼리 최적화** | 전자 메일 및 장치에서 데이터를 결합하는 효율적인 쿼리 및 쿼리를 만드는 방법에 대해 알아봅니다. | [쿼리 모범 사례](advanced-hunting-shared-queries.md), [여러 장치 및 전자 메일에서 헌팅](advanced-hunting-best-practices.md)

## <a name="get-help-as-you-write-queries"></a>쿼리 작성시 도움말 보기
다음 기능을 활용하여 쿼리를 더 빠르게 작성하세요.
- **자동 제안** — 쿼리를 작성할 때 고급 헌팅에서 제안을 제공합니다. 
- **스키마 참조** — 테이블 및 해당 열 목록이 포함된 스키마 참조가 작업 영역 옆에 제공됩니다. 자세한 내용을 보려면 항목 위로 마우스를 가져갑니다. 항목을 두 번 클릭하여 쿼리 편집기에 삽입합니다.

## <a name="drilldown-from-query-results"></a>쿼리 결과에서 드릴 다운
쿼리 결과에서 컴퓨터, 파일, 사용자, IP 주소 및 URL과 같은 엔터티에 대한 자세한 정보를 보려면 엔터티 식별자를 클릭하기만 하면 됩니다. 그러면 Microsoft Defender 보안 센터에서 선택한 엔터티에 대한 자세한 프로필 페이지가 열립니다.

## <a name="tweak-your-queries-from-the-results"></a>결과에서 쿼리 조정
결과 집합의 값을 마우스 오른쪽 단추로 클릭하면 쿼리가 빠르게 향상됩니다. 옵션을 사용하여 다음을 수행할 수 있습니다.

- 선택한 값을 명시적으로 찾습니다 (`==`)
- 쿼리에서 선택한 값을 제외합니다 (`!=`)
- 쿼리에 값을 추가하는 고급 연산자를 사용합니다 (예: `contains`, `starts with` 및 `ends with`) 

![Microsoft Defender ATP 고급 헌팅 결과 집합 이미지](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>쿼리 결과 필터링
오른쪽에 표시되는 필터는 결과 집합에 대한 요약을 제공합니다. 각 열에는 해당 열에 대해 발견된 고유 값과 인스턴스 수를 나열하는 자체적인 섹션이 있습니다.

포함하거나 제외하려는 값에서 "+" 또는 "-" 단추를 선택한 다음 **쿼리 실행**을 선택하여 쿼리를 구체화합니다.

![고급 헌팅 필터 이미지](../images/advanced-hunting-filter.png)

필터를 적용하여 쿼리를 수정한 다음 쿼리를 실행하면 그에 따라 결과가 업데이트됩니다.

## <a name="related-topics"></a>관련 항목
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
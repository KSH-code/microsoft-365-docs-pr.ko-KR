---
title: Advanced eDiscovery에서 사례에 대한 데이터 수집
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 검색 도구를 사용하여 조사에서 검토할 문서 집합을 식별하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751273"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Advanced eDiscovery에서 사례에 대한 데이터 수집

사례에 관심이 있는 보호자 및 데이터 원본을 식별한 다음에는 확인할 문서 집합을 식별해야 합니다. Advanced eDiscovery의 검색 도구를 사용하여 Microsoft 365의 상주 및 비보조 위치에서 관련 문서를 식별할 수 있습니다.

검색을 실행한 후 검색 쿼리와 일치하는 항목이 가장 많은 위치 등 검색된 항목에 대한 통계를 볼 수 있습니다. 결과의 하위 집합을 미리 볼 수 있습니다. 추가로 검사할 문서 집합을 확인한 경우 검색 결과를 검토 집합에 추가하여 수집 및 프로세스를 진행할 수 있습니다.

## <a name="create-a-search"></a>검색 만들기

검색 **탭에서** 새  검색을 선택하면 검색 만들기를 안내하는 마법사가 시작됩니다. 검색을 만드는 방법에 대한 자세한 내용은 검색 만들기를 참조하여 데이터를 [수집합니다.](create-search-to-collect-data.md)

검색을 만든 후 세부 정보가 있는 플라이아웃 페이지가 표시됩니다. **검색이** 아직  완료되지 않았기 때문에 통계 및 미리 보기 단추를 처음에 사용할 수 없습니다. 검색 탭에서 검색 진행률을 **추적할 수** 있습니다.

## <a name="view-search-results-and-statistics"></a>검색 결과 및 통계 보기

콘텐츠 검색에는 통계(예상치) 및 미리 보기의 두 가지 구성 요소가 있습니다. 이러한 각 구성 요소가 완료되면 검색 탭의 해당 열에 표시되는  상태가 **제출에서** 진행  중으로 **변경됩니다.**

검색 예상이 완료되면 검색을 선택하여 검색 결과에 대한 몇 가지 높은 수준의 통계를 표시하는 플라이아웃 페이지를 표시합니다. 이때 통계 단추가 활성화됩니다.  이 옵션을 선택하여 검색 통계를 볼 수 있습니다.

- 요약
- 상위 위치
- 쿼리

검색 통계에 대한 자세한 내용은 [검색 통계를 참조하세요.](search-statistics-in-advanced-ediscovery.md)

미리 보기가 완료되면 미리 **보기** 단추가 활성화됩니다. 결과의 샘플링된 하위 집합을 미리 확인하려면 선택합니다.

## <a name="add-search-results-to-a-review-set"></a>검색 결과를 검토 집합에 추가

검색의 전체 결과를 수집하고 처리하기 위해 준비되면 검토 집합에 추가하면 됩니다. 자세한 내용은 검토 [집합에 데이터 추가를 참조합니다.](add-data-to-review-set.md)

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>검토 집합에 비 Microsoft 365 데이터 추가

사례에 대한 수집 프로세스의 일부로, 비 Office 365 데이터를 검토 집합에 추가하고 검색 도구를 사용하여 수집한 Office 365 데이터와 함께 검토 및 분석할 수도 있습니다. 비 Office 365를 추가하는 경우 이 경우 해당 정보를 특정 보직원과 연결해야 합니다. 자세한 내용은 [검토 집합에 비 Microsoft 365 데이터 로드를 참조하세요.](load-non-Office-365-data-into-a-review-set.md)

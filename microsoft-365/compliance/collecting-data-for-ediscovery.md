---
title: Advanced eDiscovery에서 사례에 대 한 데이터 수집
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
description: 고급 eDiscovery의 검색 도구를 사용 하 여 검토를 위해 검토할 문서 집합을 식별 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956201"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Advanced eDiscovery에서 사례에 대 한 데이터 수집

해당 사례에 관심이 있는 custodians 및 데이터 원본을 식별 한 후에는 delve에 사용할 문서 집합을 식별 해야 합니다. 고급 eDiscovery의 검색 도구를 사용 하 여 Microsoft 365의 custodial 및 비 custodial 위치에서 관련 문서를 식별할 수 있습니다.

검색을 실행 한 후 검색 쿼리와 일치 하는 항목이 가장 많은 위치와 같은 검색 된 항목에 대 한 통계를 볼 수 있습니다. 또한 결과의 하위 집합을 미리 볼 수도 있습니다. 추가로 확인할 문서 집합을 식별 한 경우 수집 및 처리할 검토 집합에 검색 결과를 추가할 수 있습니다.

## <a name="create-a-search"></a>검색 만들기

**검색 탭에서** **새 검색** 을 선택 하는 마법사를 시작 하 여 search를 만드는 과정을 안내 합니다. 검색을 만드는 방법에 대 한 자세한 내용은 [create a search를 검색 하 여 데이터 수집](create-search-to-collect-data.md)을 참조 하십시오.

검색을 만든 후에는 세부 정보가 포함 된 플라이 아웃 페이지가 표시 됩니다. 검색이 아직 완료 되지 않았으므로 **통계** 및 **미리 보기** 단추가 처음에는 사용할 수 없습니다. 검색의 진행 상태를 추적할 수 있습니다 ( **검색 탭)** .

## <a name="view-search-results-and-statistics"></a>검색 결과 및 통계 보기

콘텐츠 검색에는 통계 (예측) 및 미리 보기의 두 가지 구성 요소가 있습니다. 이러한 각 구성 요소가 완료 되 면 **검색** 탭의 해당 열에 **제출** 됨에서 **진행 중** 으로 **완료**로 변경 된 상태가 표시 됩니다.

검색 예측이 완료 되 면 검색을 선택 하 여 검색 결과에 대 한 일부 고급 통계를 표시 하는 플라이 아웃 페이지를 표시 합니다. 이 시점에서 **통계** 단추가 활성화 됩니다. 이 도구를 선택 하 여 다음과 같은 검색 통계를 볼 수 있습니다.

- 요약
- 상위 위치
- 쿼리하도록

검색 통계에 대 한 자세한 내용은 [검색 통계](search-statistics.md)를 참조 하세요.

미리 보기가 완료 되 면 **미리 보기** 단추가 활성화 됩니다. 이 도구를 선택 하 여 샘플링 된 결과의 하위 집합을 미리 봅니다.

## <a name="add-search-results-to-a-review-set"></a>검색 결과를 검토 집합에 추가

검색의 전체 결과를 수집 하 고 처리할 준비가 되 면 검토 집합에 추가 하 여 검색할 수 있습니다. 자세한 내용은 [검토 집합에 데이터 추가](add-data-to-review-set.md)를 참조 하십시오.

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>검토 집합에 타사 365 데이터 추가

사례에 대 한 수집 프로세스의 일부로, Office 이외의 365 데이터를 검토 집합에 추가 하 고, 검색 도구를 사용 하 여 수집한 Office 365 데이터와 함께 검토 하 고 분석할 수도 있습니다. Office 이외의 365을 추가 하는 경우에는 케이스의 특정 custodian 연결 해야 합니다. 자세한 내용은 타사 [365 데이터를 검토 집합으로 로드](load-non-Office-365-data-into-a-review-set.md)를 참조 하세요.

---
title: Advance eDiscovery의 검색 통계
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 검색에서 컬렉션 검색을 실행한 후 생성되는 통계를 확인하여 검색 결과의 유효성을 Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59183964"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>검색 통계를 Advanced eDiscovery

검색 결과의 유효성을 검사할 수 있는 한 가지 방법은 결과와 관련한 통계를 확인하여 예상과 일치하도록 하는 것입니다. 검색이 완료되면 검색 세부 정보 플라이아웃에 높은 수준의 통계가 표시됩니다.

- 검색에 의해 검색된 항목의 수 및 볼륨

- 검색 위치에 있는 부분적으로 인덱싱되거나 인덱싱되지 않은 항목의 수 및 볼륨

- 검색된 사서함 및 위치의 수입니다.
더 자세한 통계를 보려면 검색 세부 정보 플라이아웃에서 "통계"를 클릭합니다.

## <a name="summary-view"></a>요약 보기

요약 보기에서 위치 유형(예: 검색 결과)별로 세분화된 검색 결과를 Exchange. 각 위치 유형에 대해 다음을 볼 수 있습니다.

- 검색 조건과 일치하는 항목이 있는 위치 수

- 검색 조건과 일치하는 이러한 위치의 항목 수

- 검색 조건과 일치하는 총 항목 볼륨입니다.

## <a name="top-locations-view"></a>상위 위치 보기

최상위 위치 보기에는 일치하는 위치가 가장 많은 개별 위치가 표시됩니다. 각 위치에 대해 다음이 표시됩니다.

- 위치 이름(예: SharePoint URL)

- 위치 종류

- 검색 조건과 일치하는 항목 수

- 검색 조건과 일치하는 총 항목 볼륨입니다.

## <a name="queries-view"></a>쿼리 보기

쿼리에 (c:s) 키워드 또는 키워드 행을 사용한 경우 위치 유형별 쿼리 보기에서 쿼리 분석 결과를 볼 수 있습니다. 각 위치 유형에 대해 다음이 표시됩니다.

- 파트: 이 열에는 "Primary" 또는 "Keyword"라는 단어가 있습니다. "기본"은 행이 전체 쿼리에 대한 통계를 제시하는 반면 "Keyword"는 쿼리 구성 요소 중 하나를 의미합니다.

- Query: 행이 참조하는 실제 쿼리 구성 요소입니다. Part이 "Primary"이면 전체 쿼리가 됩니다. Part이 "Keyword"이면 여기에서 쿼리 구성 요소 중 하나를 볼 수 있습니다.
  
  - 키워드를 지정하지 않으면서 모든 콘텐츠인 사서함을 검색할 때 모든 항목이 반환될 수 있도록 실제 쿼리(크기 >= 0)입니다.
  
  - 온라인 및 SharePoint 검색할 비즈니스용 OneDrive 다음 두 구성 요소가 추가됩니다.
    
    - NOT IsExternalContent:1 - 조직에서 모든 콘텐츠를 제외하는 SharePoint
    
    - NOT isOneNotePage: 1 - 검색 쿼리와 일치하는 OneNote 복제본이기 때문에 모든 OneNote 제외합니다.

- 검색 조건과 일치하는 항목이 있는 위치 수입니다.

- 검색 조건과 일치하는 이러한 위치의 항목 수입니다.

- 검색 조건과 일치하는 총 항목 볼륨입니다.

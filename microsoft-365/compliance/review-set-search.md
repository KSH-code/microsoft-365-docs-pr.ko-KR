---
title: 검토 집합에서 데이터 쿼리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 사례에서 보다 효율적인 검토를 위해 데이터를 구성 하기 위해 검토 집합에서 쿼리를 만들고 실행 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816571"
---
# <a name="query-the-data-in-a-review-set"></a>검토 집합에서 데이터 쿼리

대부분의 경우 검토 집합에서 데이터를 심층적으로 살펴보고 해당 데이터를 구성 하 여 보다 효율적인 검토를 용이 하 게 하는 것이 좋습니다. 검토 집합에서 쿼리를 사용 하면 검토 기준을 충족 하는 문서 하위 집합을 중심으로 작업할 수 있습니다.

## <a name="creating-and-running-a-query-in-a-review-set"></a>검토 집합에서 쿼리 만들기 및 실행

검토 집합의 문서에 대 한 쿼리를 만들고 실행 하려면 검토 집합에서 **새 쿼리** 를 선택 합니다. 쿼리 이름을 지정 하 고 조건을 정의한 후 **저장** 을 선택 하 여 쿼리를 저장 하 고 실행 합니다. 이전에 저장 한 쿼리를 실행 하려면 저장 된 쿼리를 선택 합니다.

![집합 쿼리 검토](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>검토 집합 쿼리 작성

키워드 조건에 키워드, 속성 및 조건을 조합해 서 사용 하 여 쿼리를 작성할 수 있습니다. 조건을 블록 ( *조건 그룹* 이라고 함)로 그룹화 하 여 좀 더 복잡 한 쿼리를 작성할 수도 있습니다. 검색할 수 있는 메타 데이터 속성의 목록 및 설명에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md)를 참조 하십시오.

### <a name="conditions"></a>조건

검토 집합의 모든 검색 가능 필드에는 쿼리를 작성 하는 데 사용할 수 있는 해당 조건이 있습니다.

여러 조건의 유형이 있습니다.

- Freetext: subject와 같은 텍스트 필드에 freetext 조건이 사용 됩니다. 여러 검색 용어를 쉼표로 구분 하 여 나열할 수 있습니다.

- 날짜: 마지막으로 수정한 날짜와 같은 날짜 필드에 날짜 조건이 사용 됩니다.

- 검색 옵션: 검색 옵션 조건에는 검토 집합의 특정 필드에 사용할 수 있는 값 목록이 제공 됩니다. 이 속성은 검토 집합에서 가능한 값의 수가 제한 되는 필드 (예: 보낸 사람)에 사용 됩니다.

- 키워드: 키워드 조건은에서 용어를 검색 하거나에서 KQL와 같은 쿼리 언어를 사용 하는 데 사용할 수 있는 freetext 조건의 특정 인스턴스입니다. 자세한 내용은 아래를 참조 하세요.

### <a name="query-language"></a>쿼리 언어

조건 외에도 키워드 조건에서 KQL 같은 쿼리 언어를 사용 하 여 쿼리를 작성할 수 있습니다. 검토 집합 쿼리 언어에서는 **AND** , **OR** , **NOT** 및 **NEAR** 과 같은 표준 부울 연산자를 지원 합니다. 또한 단일 문자 와일드 카드 (?) 및 여러 문자 와일드 카드 (*)를 지원 합니다.

## <a name="filters"></a>필터

검토할 수 있는 쿼리 외에도 검토 집합 필터를 사용 하 여 검토 집합 쿼리에 추가 조건을 빠르게 적용할 수 있습니다. 필터를 사용 하면 검토 집합 쿼리로 표시 되는 결과를 보다 구체화 하는 데 도움이 됩니다.

![집합 필터 검토](../media/AeDReviewSetFilters.png)

필터는 다음과 같은 두 가지 중요 한 방식으로 쿼리와 다릅니다.

- 필터가 일시적입니다. 기존 세션 보다는 지속 되지 않습니다. 즉, 필터를 저장할 수 없습니다. 쿼리가 검토 집합에 저장 되 고 검토 집합을 열 때마다이 쿼리에 액세스 합니다.

- 필터는 항상 추가 됩니다. 필터는 현재 검토 집합 쿼리와 함께 적용 됩니다. 다른 쿼리를 적용 하면 현재 쿼리에서 반환 된 결과가 대체 됩니다.

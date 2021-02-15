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
description: 고급 eDiscovery 사례에서 보다 효율적인 검토를 위해 데이터를 구성하기 위해 검토 집합에서 쿼리를 만들고 실행하는 방법을 학습합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816571"
---
# <a name="query-the-data-in-a-review-set"></a>검토 집합에서 데이터 쿼리

대부분의 경우 검토 집합의 데이터를 더 깊이 파고들어 보다 효율적으로 검토할 수 있도록 데이터를 구성할 수 있는 것이 유용할 것입니다. 검토 집합에서 쿼리를 사용하면 검토 조건을 충족하는 문서 하위 집합에 집중할 수 있습니다.

## <a name="creating-and-running-a-query-in-a-review-set"></a>검토 집합에서 쿼리 만들기 및 실행

검토 집합의 문서에 대한 쿼리를 만들고 실행하려면 검토 집합에서 새 쿼리를 선택합니다.  쿼리 이름을 지정하고 조건을 정의한  후 저장을 선택하여 쿼리를 저장하고 실행합니다. 이전에 저장한 쿼리를 실행하려면 저장된 쿼리를 선택합니다.

![쿼리 집합 검토](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>검토 집합 쿼리 작성

키워드 조건에서 키워드, 속성 및 조건의 조합을 사용하여 쿼리를 만들 수 있습니다. 조건 그룹이라고 하는 블록으로 조건을 그룹화하여 보다 복잡한 쿼리를 만들 수 있습니다. 검색할 수 있는 메타데이터 속성의 목록 및 설명은 [Advanced eDiscovery의](document-metadata-fields-in-Advanced-eDiscovery.md)문서 메타데이터 필드를 참조하세요.

### <a name="conditions"></a>조건

검토 집합의 모든 검색 가능한 필드에는 쿼리를 작성하는 데 사용할 수 있는 해당 조건이 있습니다.

조건에는 여러 가지가 있습니다.

- 자유 텍스트: 제목과 같은 텍스트 필드에 자유 텍스트 조건이 사용됩니다. 여러 검색 용어를 콤보로 구분하여 나열할 수 있습니다.

- 날짜: 마지막으로 수정한 날짜와 같은 날짜 필드에 날짜 조건이 사용됩니다.

- 검색 옵션: 검색 옵션 조건은 검토 집합의 특정 필드에 대해 가능한 값 목록을 제공합니다. 검토 집합에 가능한 값이 유한한 수의 보낸 사람과 같은 필드에 사용됩니다.

- 키워드: 키워드 조건은 용어를 검색하거나 KQL과 같은 쿼리 언어를 사용하는 데 사용할 수 있는 자유형 조건의 특정 인스턴스입니다. 자세한 내용은 아래를 참조하세요.

### <a name="query-language"></a>쿼리 언어

조건 외에도 키워드 조건에서 KQL과 같은 쿼리 언어를 사용하여 쿼리를 빌드할 수 있습니다. 검토 집합 쿼리의 쿼리 언어는 **AND,** **OR, NOT,** NEAR 등의 표준 부울 연산자를 **지원합니다.** 또한 단일 문자 와일드카드(?) 및 다중 문자 와일드카드(*)도 지원됩니다.

## <a name="filters"></a>필터

저장할 수 있는 쿼리 외에도 검토 집합 필터를 사용하여 검토 집합 쿼리에 추가 조건을 신속하게 적용할 수 있습니다. 필터를 사용하면 검토 집합 쿼리에 의해 표시되는 결과를 보다 구체화할 수 있습니다.

![필터 검토](../media/AeDReviewSetFilters.png)

필터는 두 가지 중요한 방식으로 쿼리와 다릅니다.

- 필터는 일시적입니다. 기존 세션을 넘어도 유지되지 않습니다. 즉, 필터를 저장할 수 없습니다. 쿼리는 검토 집합에 저장되고 검토 집합을 열 때마다 해당 쿼리에 액세스합니다.

- 필터는 항상 가산됩니다. 필터는 현재 검토 집합 쿼리와 함께 적용됩니다. 다른 쿼리를 적용하면 현재 쿼리에서 반환된 결과가 바집니다.

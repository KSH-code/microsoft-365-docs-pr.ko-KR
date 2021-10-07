---
title: 콘텐츠 검색을 다시 시도하여 콘텐츠 위치 오류 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 조사하는 동안 다시 시도 단추를 사용하여 콘텐츠 위치 오류가 있는 콘텐츠 검색을 해결할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3c433dfa6bf842f1d62350e3b518177d1bdca6d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192166"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>콘텐츠 검색을 다시 시도하여 콘텐츠 위치 오류 해결

보안 및 준수 센터에서 콘텐츠 검색을 사용하여 많은 수의 사서함을 검색하는 경우 오류와 유사한 검색 오류가 발생할 수 있습니다.

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

이러한 오류(CS001-002, CS003-002, CS008-009, CS012-002 및 CS0XX-0X 형식의 기타 오류)는 콘텐츠 검색에서 특정 콘텐츠 위치를 검색하지 못했습니다. 이 예에서는 두 개의 사서함을 검색하지 않았습니다. 이러한 오류는 콘텐츠 검색의 상태 세부 정보 플라이아웃 페이지에 표시됩니다.

## <a name="cause-of-content-location-errors"></a>콘텐츠 위치 오류의 원인

많은 수의 사서함을 검색할 때 검색은 Microsoft 데이터 센터에 있는 수천 대의 서버에 배포됩니다. 한 번은 특정 서버가 다시 시작 상태 또는 중복 복사본으로 장애 조치(fail over)하는 중일 수 있습니다. 이러한 경우 모두 데이터 검색에 대한 콘텐츠 검색 요청의 시간이 지날 수 있습니다. 이전 예에서 실패한 사서함에 대한 오류는 검색 시간 제한의 결과입니다.

## <a name="resolving-content-location-errors"></a>콘텐츠 위치 오류 해결

검색을 다시 시작하면 다른 서버에서 유사한 오류가 발생하는 경우가 종종 있습니다. 검색을 다시 시작하는 대신 검색  결과 페이지의 맨 위에 표시되는 다시 시도 단추를 클릭합니다.

![다시 시도 단추를 클릭하여 콘텐츠 위치 오류를 해결합니다.](../media/retrycontentsearch3.png)

이렇게 하면 실패한 사서함에 대한 검색만 다시 시도됩니다. 검색을 다시 시도하면 반환된 다른 결과가 보존됩니다.

## <a name="tips-to-avoid-content-location-errors"></a>팁 위치 오류를 방지하는 데 사용

다음은 콘텐츠 위치 오류의 몇 가지 추가 원인과 많은 수의 사서함을 검색할 때 이를 방지하는 데 도움이 되는 몇 가지 팁입니다.

- 사용자 활동으로 인해 검색되는 사서함이 사용 중일 수 있습니다. 이 경우 검색 서비스는 사서함을 사용할 수 없게 되기 위해 자체적으로 제한될 수 있습니다. 이러한 문제를 방지하기 위해 업무 시간 이 아닌 시간에 검색을 실행해 보아야 합니다.

- 검색 쿼리가 사서함에서 너무 많은 콘텐츠를 검색할 수 있습니다. 가능한 경우 키워드, 날짜 범위 및 검색 조건을 사용하여 검색 범위를 좁히십시오.

- 키워드 목록을 사용하여 검색 쿼리를 만들 때 키워드 또는 키워드 구가 너무 [많이 있습니다.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches) 키워드 목록을 사용하는 검색 쿼리를 실행하면 기본적으로 이 서비스는 통계를 생성하기 위해 키워드 목록의 각 행에 대해 별도의 검색을 실행합니다. 검색 쿼리에서 키워드 목록을 사용하는 경우 키워드 목록의 행 수를 최소화하거나 숫자 키워드를 더 작은 목록으로 나누고 각 키워드 목록에 대해 다른 검색을 만들 수 있습니다.

  > [!NOTE]
  > 큰 키워드 목록으로 인한 문제를 줄이기 위해 이제 검색 쿼리의 키워드 목록에서 최대 20개 행으로 제한됩니다.

- 같은 사서함에서 동시에 너무 많은 검색이 수행되고 있습니다. 가능한 경우 사서함 하나에 대해 한 번의 검색을 실행해 보아야 합니다.

- 단일 검색에서 너무 많은 사서함 검색 많은 수의 사서함을 검색할 때 콘텐츠 위치 오류가 발생할 확률이 높아집니다. 가능하면 각 검색에 조직에 사서함의 하위 집합이 포함될 수 있도록 여러 검색을 실행해 보아야 합니다.

- 사서함에서 필요한 유지 관리가 수행되고 있습니다. 이 원인은 거의 발생하지 않을 수 있습니다. 콘텐츠 위치 오류가 발생한 후 잠시 기다렸다가 검색을 다시 시도하십시오.

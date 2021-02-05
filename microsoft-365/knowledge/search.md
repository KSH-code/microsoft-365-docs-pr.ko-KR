---
title: Microsoft Search를 사용하여 Microsoft Viva 항목의 항목 찾기
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Microsoft Viva에서 항목을 검색하는 방법에 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108302"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Microsoft Search를 사용하여 Microsoft Viva 항목의 항목 찾기

Viva Topics 사용자는 SharePoint 사이트에서 주요 항목을 통해 항목을 찾을 수 있는 반면 Microsoft Search를 통해 항목을 찾을 수도 있습니다. 

## <a name="topic-answer"></a>항목 답변

Microsoft Search에서 특정 항목(예: "Saturn")을 검색하면 해당 주제가 존재하고 발견된 경우 응답 제안 형식으로 결과가 표시됩니다.

항목 답변에는 다음이 표시됩니다.
- 항목 이름
- 대체 이름: 항목의 대체 이름 또는 약어입니다.
- 정의: AI에서 제공하거나 사람이 수동으로 추가한 항목에 대한 설명입니다.
- 추천된 사람 또는 고정된 사람: AI에서 제안되거나 사람이 항목에 고정한 사람
- 추천 리소스 또는 고정 리소스: AI에서 제안하거나 사람이 항목에 고정한 파일, 페이지 또는 사이트. 

   ![검색 항목](../media/knowledge-management/search-topic-answer.png) 

항목 응답 카드가 나타나지 않는 경우에도 항목 페이지를 검색 결과에 표시할 수 있습니다.


## <a name="acronyms"></a>약어

Viva 항목에서는 항목에 대한 약어를 대체 이름으로 포함하기 위해 항목을 수동으로 <b>편집할 수 있습니다.</b> 이렇게 하면 항목의 약어로만 검색하는 사용자가 Microsoft Search를 통해 항목 답변을 찾을 수 있습니다.

[약어 답변은](https://docs.microsoft.com/microsoftsearch/manage-acronyms) Microsoft Search를 통해 제공되는 기능으로 Viva 항목과는 별도로 관리됩니다.

## <a name="bookmarks-and-topics"></a>책갈피 및 항목

[책갈피는](https://docs.microsoft.com/microsoftsearch/manage-bookmarks) 검색을 통해 중요한 사이트와 도구를 빠르게 찾을 수 있도록 하는 Microsoft 검색 기능입니다(예: Microsoft 365 테넌트 외부의 외부 사이트에 있는 여행 예약 도구). Microsoft 365 관리 센터의 검색 관리자가 생성합니다. 

출장 예약에 대한 정보를 찾고 있는 사용자의 경우:

- 일부 사용자가 여행 도구 이름(예: "Concur")을 알고 있는 경우 책갈피를 만들어 외부 사이트로 직접 이동하는 것이 더 쉽습니다.
- 일반적으로 "여행"을 검색하는 사용자의 경우 "여행"에 예상한 정보가 있는 항목을 만드시다. 항목 설명에서 동시 외부 사이트에 대한 링크를 추가하는 것이 좋습니다. 링크가 Microsoft 365 테넌트에 호스트된 내부 여행 예약 사이트에 대한 링크가 아닌 경우 "고정된 리소스"에 추가할 수 있습니다.
 
### <a name="search-results-priority"></a>검색 결과 우선 순위 
 
사용자 검색 환경의 경우 사용자가 "여행"이라는 용어를 검색하면 Microsoft Search에서 검색 결과가 다음 우선 순위로 표시됩니다.
1. 게시되거나 확인된 항목 
2. 책갈피
3. 추천 항목 




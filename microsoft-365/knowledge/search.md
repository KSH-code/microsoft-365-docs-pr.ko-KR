---
title: Microsoft Search를 사용하여 Microsoft Viva 항목에서 항목 찾기
ms.author: chuckedmonson
author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Microsoft Viva에서 항목을 검색하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: bce9309d27b76854b927922f39389c18e1c09449
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844734"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Microsoft Search를 사용하여 Microsoft Viva 항목에서 항목 찾기

Viva 항목 사용자는 자신의 SharePoint 항목을 통해 항목을 찾을 수 있는 반면, Microsoft Search를 통해 항목을 찾을 수도 있습니다. 

## <a name="topic-answer"></a>항목 답변

Microsoft Search에서 특정 항목(예: "Saturn")을 검색할 때 항목이 있으며 발견된 경우 항목 응답 제안 형식으로 결과가 표시됩니다.

이 항목의 답변은 다음을 표시합니다.
- 토픽 이름
- 대체 이름: 항목의 대체 이름 또는 약어입니다.
- 정의: AI에서 제공하거나 직접 추가한 항목에 대한 설명입니다.
- 추천된 사람 또는 고정된 사람: AI에서 제안하거나 사람이 항목에 고정한 사람
- 추천 리소스 또는 고정 리소스: AI에서 제안하거나 사람이 항목에 고정한 파일, 페이지 또는 사이트입니다. 

   ![검색의 항목](../media/knowledge-management/search-topic-answer.png) 

항목 응답 카드가 나타나지 않는 경우에도 항목 페이지를 검색 결과에 표시할 수 있습니다.

Word, PowerPoint, Outlook Excel 검색 결과가 발견될 때 항목 응답도 표시됩니다.


## <a name="acronyms"></a>머리글자어

Viva 항목에서는 항목을 수동으로 편집하여 이 항목의 약어를 대체 이름으로 <b>포함할 수 있습니다.</b> 이렇게 하면 항목의 약어로만 검색하는 사용자가 Microsoft Search를 통해 항목 답변을 찾을 수 있습니다.

[약어 답변은](/microsoftsearch/manage-acronyms) Microsoft Search를 통해 제공되는 기능으로 Viva 항목과는 별도로 관리됩니다.

## <a name="bookmarks-and-topics"></a>책갈피 및 항목

[책갈피는](/microsoftsearch/manage-bookmarks) 검색만 사용하여 중요한 사이트와 도구를 빠르게 찾을 수 있도록 하는 Microsoft 검색 기능입니다(예: Microsoft 365 테넌트 외부의 외부 사이트에 있는 여행 예약 도구). 검색 관리자는 Microsoft 365 관리 센터에서 만들어집니다. 

출장 예약에 대한 정보를 찾고 있는 사용자의 경우:

- 일부 사용자가 여행 도구 이름(예: "Concur")을 알고 있는 경우 책갈피를 만들어 외부 사이트로 바로 이동하는 것이 더 쉽습니다.
- 일반적으로 "여행"을 검색하는 사용자의 경우 예상 정보가 있는 "여행"에 대한 항목을 만들 수 있습니다. 항목 설명에서 Concur 외부 사이트에 대한 링크를 추가하는 것이 좋습니다. 해당 링크가 Microsoft 365 호스트되는 내부 여행 예약 사이트에 대한 링크인 경우 "고정된 리소스"에 추가할 수 있습니다.
 
### <a name="search-results-priority"></a>검색 결과 우선 순위 

사용자의 검색 환경에서 사용자가 "travel"이라는 용어를 검색하면 책갈피를 사용할 수 있는 경우 주제 대신 책갈피가 나타납니다.

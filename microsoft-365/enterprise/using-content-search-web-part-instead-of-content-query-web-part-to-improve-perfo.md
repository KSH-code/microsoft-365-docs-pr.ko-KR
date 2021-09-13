---
title: 콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 온라인에서 SharePoint 향상
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: SharePoint Server 2013 및 SharePoint Online에서 콘텐츠 쿼리 웹 파트를 콘텐츠 검색 웹 파트로 바꾸어 성능을 SharePoint 방법을 알아보겠습니다.
ms.openlocfilehash: 270019b59666c3f52d67648a88c453278149fccd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210432"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 온라인에서 SharePoint 향상

이 문서에서는 콘텐츠 쿼리 웹 파트를 SharePoint Server 2013 및 SharePoint Online의 콘텐츠 검색 웹 파트로 바꾸어 성능을 향상하는 방법에 대해 설명합니다.
  
SharePoint Server 2013 및 SharePoint Online의 가장 강력한 새로운 기능 중 하나는 CSWP(콘텐츠 검색 웹 파트)입니다. 이 웹 파트는 검색 인덱스를 사용하여 사용자에게 표시되는 결과를 빠르게 검색합니다. 페이지의 CQWP(콘텐츠 쿼리 웹 파트) 대신 콘텐츠 검색 웹 파트를 사용하여 사용자의 성능을 향상시킬 수 있습니다.
  
콘텐츠 쿼리 웹 파트를 통해 콘텐츠 검색 웹 파트를 사용하는 경우 거의 항상 온라인에서 페이지 로드 성능이 SharePoint 있습니다. 올바른 쿼리를 얻을 수 있도록 몇 가지 추가 구성이 있지만 성능이 향상되어 사용자가 더 기다렸다는 보상을 받을 수 있습니다.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 얻을 수 있는 성능 비교

다음 예제에서는 콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용할 때 얻을 수 있는 상대적인 성능 향상을 보여 제공합니다. 복잡한 사이트 구조와 매우 광범위한 콘텐츠 쿼리를 사용할 때의 효과는 더욱 명확합니다.
  
이 예제 사이트에는 다음과 같은 특성이 있습니다.
  
- 8개 하위 수준
    
- 사용자 지정 "열매" 콘텐츠 형식을 사용하는 목록입니다.
    
- 웹 파트에서 콘텐츠 쿼리는 광범위하여 콘텐츠 형식이 "fruit"인 모든 항목을 반환합니다.
    
- 이 예제에서는 8개 사이트에서 50개 항목만 사용하게 됩니다. 콘텐츠가 더 많은 사이트에서는 효과의 발음이 더욱 두드게 됩니다.
    
다음은 콘텐츠 쿼리 웹 파트의 결과 스크린샷입니다.
  
![웹 파트에 대한 콘텐츠 쿼리를 보여 주는 그래픽입니다.](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
이 Internet Explorer F12  개발자 도구의 네트워크 탭을 사용하여 응답 헤더에 대한 세부 정보를 확인합니다. 다음 스크린샷에서 이 페이지 로드의 **SPRequestDuration** 값은 924밀리초입니다. 
  
![Screenshot showing request duration of 924.](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration은** 서버에서 페이지를 준비하기 위해 수행되는 작업의 양을 나타냅니다. 쿼리로 콘텐츠를 웹 파트 검색을 통해 콘텐츠를 웹 파트 페이지를 렌더링하는 데 걸리는 시간이 크게 줄어듭니다. 반면 동일한 수의 결과를 반환하는 동등한 콘텐츠 검색 웹 파트가 있는 페이지에는 이 스크린샷과 같이 **SPRequestDuration** 값이 106밀리초입니다. 
  
![요청 기간이 106인 스크린샷](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>온라인에서 콘텐츠 검색 웹 파트 SharePoint 추가

콘텐츠 검색 웹 파트를 추가하는 것은 일반 콘텐츠 쿼리 웹 파트와 매우 유사합니다. 에서 콘텐츠 검색 웹 파트 구성의 "콘텐츠 검색 웹 파트 *추가"* [섹션을 SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>콘텐츠 검색 웹 파트에 적합한 검색 쿼리 만들기

콘텐츠 검색 웹 파트를 추가한 후 검색을 구체화하고 원하는 항목을 반환할 수 있습니다. 이 작업을 수행 하는 방법에 대한 자세한 내용은 에서 콘텐츠 검색 웹 파트 구성의 *"콘텐츠* 검색 웹 파트에서 고급 쿼리를 구성하여 콘텐츠 표시" [섹션을 SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)
  
## <a name="query-building-and-testing-tool"></a>쿼리 작성 및 테스트 도구

복잡한 쿼리를 작성하고 테스트하는 도구는 Codeplex의 검색 쿼리 [도구를](https://sp2013searchtool.codeplex.com/) 참조하세요. 
  


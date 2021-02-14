---
title: 콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 SharePoint Online의 성능 향상
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
description: SharePoint Server 2013 및 SharePoint Online에서 콘텐츠 쿼리 웹 파트를 콘텐츠 검색 웹 파트로 바꾸어 성능을 향상하는 방법을 알아보겠습니다.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692889"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="733bd-103">콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 SharePoint Online의 성능 향상</span><span class="sxs-lookup"><span data-stu-id="733bd-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="733bd-104">이 문서에서는 콘텐츠 쿼리 웹 파트를 SharePoint Server 2013 및 SharePoint Online의 콘텐츠 검색 웹 파트로 바꾸어 성능을 높이는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="733bd-105">SharePoint Server 2013 및 SharePoint Online의 가장 강력한 새로운 기능 중 하나는 CSWP(콘텐츠 검색 웹 파트)입니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="733bd-106">이 웹 파트는 검색 인덱스를 사용하여 사용자에게 표시되는 결과를 빠르게 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="733bd-107">페이지의 CQWP(콘텐츠 쿼리 웹 파트) 대신 콘텐츠 검색 웹 파트를 사용하여 사용자의 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="733bd-108">콘텐츠 쿼리 웹 파트를 통해 콘텐츠 검색 웹 파트를 사용하는 경우 SharePoint Online에서 페이지 로드 성능이 거의 항상 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="733bd-109">올바른 쿼리를 얻을 수 있는 몇 가지 추가 구성이 있지만 성능이 향상되어 사용자가 더 기다렸다는 보상을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="733bd-110">콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 얻을 수 있는 성능 비교</span><span class="sxs-lookup"><span data-stu-id="733bd-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="733bd-111">다음 예제에서는 콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용할 때 얻을 수 있는 상대적인 성능 향상을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="733bd-112">복잡한 사이트 구조와 매우 광범위한 콘텐츠 쿼리를 통해 그 효과가 더 명확해 졌다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="733bd-113">이 예제 사이트에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="733bd-114">8개 하위 수준</span><span class="sxs-lookup"><span data-stu-id="733bd-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="733bd-115">사용자 지정 "열매" 콘텐츠 형식을 사용하는 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="733bd-116">웹 파트에서 콘텐츠 쿼리는 광범위하여 콘텐츠 형식이 "fruit"인 모든 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="733bd-117">이 예제에서는 8개 사이트에서 50개 항목만 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="733bd-118">콘텐츠가 더 많은 사이트에서는 효과의 발음이 더욱 두드게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="733bd-119">다음은 콘텐츠 쿼리 웹 파트의 결과 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![웹 파트에 대한 콘텐츠 쿼리를 보여 주는 그래픽](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="733bd-121">이 Internet Explorer F12  개발자 도구의 네트워크 탭을 사용하여 응답 헤더에 대한 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="733bd-122">다음 스크린샷에서 이 페이지 로드에 대한 **SPRequestDuration의** 값은 924밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![924의 요청 기간을 보여 주는 스크린샷](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="733bd-124">**SPRequestDuration은** 서버에서 페이지를 준비하기 위해 수행되는 작업의 양을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="733bd-125">검색을 통해 쿼리 웹 파트 콘텐츠로 전환하면 웹 파트 렌더링하는 데 걸리는 시간이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="733bd-126">반면 동일한 수의 결과를 반환하는 동등한 콘텐츠 검색 웹 파트가 있는 페이지에는 이 스크린샷과 같이 **SPRequestDuration** 값이 106밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![106의 요청 기간을 보여 주는 스크린샷](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="733bd-128">SharePoint Online에서 콘텐츠 검색 웹 파트 추가</span><span class="sxs-lookup"><span data-stu-id="733bd-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="733bd-129">콘텐츠 검색 웹 파트를 추가하는 것은 일반 콘텐츠 쿼리 웹 파트와 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="733bd-130">SharePoint에서 콘텐츠 검색 웹 파트 구성에서 *"콘텐츠* 검색 웹 파트 [추가" 섹션을 참조하세요.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="733bd-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="733bd-131">콘텐츠 검색 웹 파트에 적합한 검색 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="733bd-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="733bd-132">콘텐츠 검색 웹 파트를 추가한 후 검색을 구체화하고 원하는 항목을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="733bd-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="733bd-133">이 작업을 하는 방법에 대한 자세한 내용은 SharePoint의 콘텐츠 검색 웹 파트 구성에서 "콘텐츠 검색 웹 파트에서 고급 쿼리를 구성하여 콘텐츠 *표시"* 섹션을 [참조하세요.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="733bd-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="733bd-134">쿼리 작성 및 테스트 도구</span><span class="sxs-lookup"><span data-stu-id="733bd-134">Query building and testing tool</span></span>

<span data-ttu-id="733bd-135">복잡한 쿼리를 작성하고 테스트하는 도구는 Codeplex의 검색 쿼리 [도구를](https://sp2013searchtool.codeplex.com/) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="733bd-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  


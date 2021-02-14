---
title: SharePoint online에서 개체 캐시 사용
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: 이 문서에서는 SharePoint Server 2013의 개체 캐시 사용과 SharePoint Online의 차이점에 대해 설명했습니다.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696361"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="beb4f-103">SharePoint online에서 개체 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="beb4f-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="beb4f-104">이 문서에서는 SharePoint Server 2013의 개체 캐시 사용과 SharePoint Online의 차이점에 대해 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="beb4f-105">SharePoint Online 배포에서 개체 캐시를 사용하게 될 경우 심각한 부정적인 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="beb4f-106">SharePoint Online의 개체 캐시에 종속하면 페이지의 안정성이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="beb4f-107">SharePoint Online 및 SharePoint Server 2013 개체 캐시의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="beb4f-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="beb4f-108">SharePoint Server 2013이 호스트되는 경우 고객에게 개체 캐시를 호스트하는 개인 프런트 엔드 웹 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="beb4f-109">즉, 캐시는 한 고객에게만 사용 가능하고 개체 캐시에 할당되는 메모리의 크기에 의해서만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="beb4f-110">프런트 엔드 웹 서버는 일반적으로 한 고객만이 동일한 사이트에 대한 요청을 여러 번 실행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="beb4f-111">즉, 캐시가 빠르게 가득 차고 사용자가 정기적으로 요청하는 목록 쿼리 결과 및 SharePoint 개체가 가득 차게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![온-프레미스 프런트 엔드 웹 서버에 대한 트래픽 및 로드 표시](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="beb4f-113">따라서 사용자가 두 번째 페이지를 방문하면 페이지 로드 시간이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="beb4f-114">같은 페이지의 부하가 4개 이상이면 페이지가 모든 프런트 엔드 웹 서버에 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="beb4f-115">반면, SharePoint Online에는 서버가 더 많지만 사이트도 더 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="beb4f-116">각 사용자는 캐시를 채우지 않은 다른 프런트 엔드 웹 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="beb4f-117">또는 서버에 대해 캐시가 채워지지만 해당 프런트 엔드 웹 서버의 다음 사용자가 다른 사이트에서 페이지를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="beb4f-118">또는 다음 사용자가 이전 방문 시와 동일한 페이지를 요청하는 경우에도 해당 페이지가 캐시에 없는 다른 프런트 엔드 웹 서버로 부하가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="beb4f-119">이 마지막 경우 캐싱은 사용자에게 전혀 도움이되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="beb4f-120">다음 그림에서 각 점은 사용자가 요청하는 페이지와 캐시된 페이지를 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="beb4f-121">각 색은 SaaS 인프라를 공유하는 다양한 고객을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![SharePoint Online의 개체 캐시 결과 표시](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="beb4f-123">다이어그램에서 볼 수 있 있든, 주어진 사용자가 캐시된 버전의 페이지를 사용하여 서버를 방문할 가능성은 배가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="beb4f-124">또한 많은 사이트 간에 서버가 공유되는 대용량의 데이터로 인해 캐시를 사용할 수 있는 공간이 너무 많기 때문에 캐시가 오래 지속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="beb4f-125">이러한 모든 이유로, 사용자가 캐시된 개체를 사용하게 하여 SharePoint Online에서 고품질 사용자 환경 및 페이지 로드 시간을 보장하는 효과적인 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="beb4f-126">SharePoint Online에서 성능을 향상하기 위해 개체 캐시를 사용할 수 없는 경우 대신 무엇을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="beb4f-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="beb4f-127">SharePoint Online에서는 캐싱을 사용하지 말아야 하기 때문에 개체 캐시를 사용하는 SharePoint 사용자 지정에 대한 대체 디자인 방법을 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="beb4f-128">즉, 사용자에게 좋은 결과를 생성하기 위해 개체 캐싱을 사용하지 않는 성능 문제에 접근 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="beb4f-129">이 문서는 이 시리즈의 일부 다른 문서에 설명되어 있으며 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="beb4f-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="beb4f-130">SharePoint Online에 대한 탐색 옵션</span><span class="sxs-lookup"><span data-stu-id="beb4f-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="beb4f-131">SharePoint Online의 축소 및 묶음</span><span class="sxs-lookup"><span data-stu-id="beb4f-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="beb4f-132">sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기</span><span class="sxs-lookup"><span data-stu-id="beb4f-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="beb4f-133">SharePoint Online에서 이미지 및 JavaScript 로드 지연</span><span class="sxs-lookup"><span data-stu-id="beb4f-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    


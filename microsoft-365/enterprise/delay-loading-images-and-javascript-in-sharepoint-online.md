---
title: SharePoint Online에서 이미지 및 JavaScript 로드 지연
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: JavaScript를 사용하여 이미지 및 필수가 아닌 JavaScript의 로드를 지연하여 SharePoint Online 페이지의 로드 시간을 줄이는 방법을 학습합니다.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919167"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="735f1-103">SharePoint Online에서 이미지 및 JavaScript 로드 지연</span><span class="sxs-lookup"><span data-stu-id="735f1-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="735f1-104">이 문서에서는 JavaScript를 사용하여 이미지 로드를 지연하고 페이지를 로드할 때까지 필수가 아닌 JavaScript를 로드할 때까지 기다려 SharePoint Online 페이지의 로드 시간을 줄이는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="735f1-105">이미지는 SharePoint Online의 페이지 로드 속도에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="735f1-106">기본적으로 대부분의 최신 인터넷 브라우저는 HTML 페이지를 로드할 때 이미지를 미리 페치합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="735f1-107">이로 인해 사용자가 아래로 스크롤할 때까지 이미지가 화면에 표시되지 않는 경우 페이지 로드 속도가 불필요하게 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="735f1-108">이미지는 브라우저에서 페이지의 표시되는 부분을 로드하지 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="735f1-109">이 문제를 해결하려면 JavaScript를 사용하여 먼저 이미지 로드를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="735f1-110">또한 필수가 아닌 JavaScript를 로드하면 SharePoint 페이지에서 다운로드 시간이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="735f1-111">이 항목에서는 SharePoint Online에서 JavaScript를 사용하여 페이지 로드 시간을 개선하는 데 사용할 수 있는 몇 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="735f1-112">JavaScript를 사용하여 SharePoint Online 페이지에서 이미지 로드를 지연하여 페이지 로드 시간 개선</span><span class="sxs-lookup"><span data-stu-id="735f1-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="735f1-113">JavaScript를 사용하여 웹 브라우저에서 이미지를 미리 페치하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="735f1-114">그러면 전체 문서 렌더링 속도가 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="735f1-115">이렇게하려면 태그에서 src 특성 값을 제거하고 데이터 특성의 파일 \<img\> 경로(예: data-src)로 바니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="735f1-116">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="735f1-117">이 방법을 사용하면 브라우저에서 즉시 이미지를 다운로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="735f1-118">이미지가 이미 뷰포트에 있는 경우 JavaScript는 브라우저에 데이터 특성에서 URL을 검색하고 src 특성의 값으로 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="735f1-119">이미지는 사용자가 스크롤할 때만 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="735f1-120">이러한 모든 기능을 사용하려면 JavaScript를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="735f1-121">텍스트 파일에서 **isElementInViewport()** 함수를 정의하여 요소가 사용자에게 표시되는 브라우저의 일부에 있는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

<span data-ttu-id="735f1-122">그런 다음 **loadItemsInView() 함수에 isElementInViewport()를** 사용 합니다. </span><span class="sxs-lookup"><span data-stu-id="735f1-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="735f1-123">**loadItemsInView()** 함수는 사용자가 볼 수 있는 브라우저의 일부에 있는 경우 data-src 특성 값이 있는 모든 이미지를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="735f1-124">텍스트 파일에 다음 함수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-124">Add the following function to the text file:</span></span>
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

<span data-ttu-id="735f1-125">마지막으로 다음 예제와 같이 **window.onscroll()** 내에서 **loadItemsInView()를** 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="735f1-126">이렇게 하면 뷰포트에 있는 모든 이미지가 사용자에게 필요하지만 이전과는 다른 것으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="735f1-127">텍스트 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="735f1-128">SharePoint Online의 경우 작업 영역 태그의 스크롤 이벤트에 다음 #s4 연결해야 \<div\> 합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="735f1-129">이는 리본 메뉴가 페이지 맨 위에 연결된 상태로 유지되도록 창 이벤트가 보다도기 때문에 그 이유는 바로 그 이유는 바로 창 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="735f1-130">텍스트 파일을 확장명 .js와 함께 JavaScript 파일로 delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="735f1-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="735f1-131">콘텐츠 작성을 delayLoadImages.js SharePoint Online의 마스터 페이지에 파일의 내용을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="735f1-132">이 작업을 위해 마스터 페이지의 헤더에 스크립트 링크를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="735f1-133">마스터 페이지에 있는 경우 JavaScript가 해당 마스터 페이지 레이아웃을 사용하는 SharePoint Online 사이트의 모든 페이지에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="735f1-134">또는 사이트의 한 페이지에서만 사용하려는 경우 스크립트 편집기 웹 파트를 사용하여 페이지에 JavaScript를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="735f1-135">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="735f1-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="735f1-136">방법: SharePoint 2013에서 사이트에 마스터 페이지 적용</span><span class="sxs-lookup"><span data-stu-id="735f1-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="735f1-137">방법: SharePoint 2013에서 페이지 레이아웃 만들기</span><span class="sxs-lookup"><span data-stu-id="735f1-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="735f1-138">예제: SharePoint Online의 delayLoadImages.js 페이지에서 JavaScript 파일 참조</span><span class="sxs-lookup"><span data-stu-id="735f1-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="735f1-139">이 작업을 위해서는 마스터 페이지에서 jQuery도 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="735f1-140">다음 예제에서는 초기 페이지 로드에서 로드된 이미지가 하나뿐이지만 페이지에 이미지가 여러 개 더 있는 경우를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![페이지에 로드된 하나의 이미지를 보여 주는 스크린샷](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="735f1-142">다음 스크린샷은 보기로 스크롤한 후 다운로드되는 나머지 이미지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![페이지에 로드된 여러 페이지를 보여 주는 스크린샷](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="735f1-144">JavaScript를 사용하여 이미지 로드를 지연하는 것이 성능을 높이는 효과적인 기술일 수 있습니다. 그러나 공개 웹 사이트에 이 기술을 적용하면 검색 엔진이 정기적으로 구성한 이미지를 크롤링하는 방법과 동일한 방식으로 이미지를 크롤링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="735f1-145">이 경우 페이지가 로드될 때까지 이미지 자체의 메타데이터가 실제로 없는 것이기 때문에 검색 엔진의 순위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="735f1-146">검색 엔진 크롤러는 HTML만 읽기만 하므로 페이지에 이미지가 콘텐츠로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="735f1-147">이미지는 검색 결과에서 페이지의 순위를 정하는 데 사용되는 요소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="735f1-148">이를 해결하는 한 가지 방법은 이미지에 소개 텍스트를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="735f1-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="735f1-149">GitHub 코드 샘플: 성능을 향상하기 위해 JavaScript 삽입</span><span class="sxs-lookup"><span data-stu-id="735f1-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="735f1-150">GitHub에 제공된 [JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) 삽입에 대한 문서 및 코드 샘플을 놓치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="735f1-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="735f1-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="735f1-151">See also</span></span>

[<span data-ttu-id="735f1-152">Office 2013 및 엔터프라이즈용 Microsoft 365 앱의 지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="735f1-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="735f1-153">방법: SharePoint 2013에서 사이트에 마스터 페이지 적용</span><span class="sxs-lookup"><span data-stu-id="735f1-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="735f1-154">방법: SharePoint 2013에서 페이지 레이아웃 만들기</span><span class="sxs-lookup"><span data-stu-id="735f1-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)
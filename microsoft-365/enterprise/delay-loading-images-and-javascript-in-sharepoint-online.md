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
description: JavaScript를 사용하여 이미지 및 필수가 아닌 JavaScript의 로드를 SharePoint 온라인 페이지의 로드 시간을 줄이는 방법을 배워야 합니다.
ms.openlocfilehash: 7be256db8bce115b130322d1dd34131d845ef165
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218572"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>SharePoint Online에서 이미지 및 JavaScript 로드 지연

이 문서에서는 JavaScript를 사용하여 이미지 로드를 지연하고 페이지를 로드할 때까지 필수가 아닌 JavaScript를 로드할 때까지 기다리는 등 SharePoint Online 페이지의 로드 시간을 줄이는 방법을 설명합니다.
  
이미지는 온라인에서 페이지 로드 속도에 부정적인 영향을 SharePoint 있습니다. 기본적으로 대부분의 최신 인터넷 브라우저는 HTML 페이지를 로드할 때 이미지를 미리 페치합니다. 이로 인해 사용자가 아래로 스크롤할 때까지 이미지가 화면에 표시되지 않는 경우 페이지 로드 속도가 불필요하게 느려질 수 있습니다. 이미지는 브라우저에서 페이지의 표시되는 부분을 로드하지 차단할 수 있습니다. 이 문제를 해결하려면 JavaScript를 사용하여 먼저 이미지 로드를 건너뛸 수 있습니다. 또한 필수가 아닌 JavaScript를 로드하면 앱 페이지의 다운로드 SharePoint 느려질 수 있습니다. 이 항목에서는 SharePoint Online에서 JavaScript를 사용하여 페이지 로드 시간을 개선하는 데 사용할 수 SharePoint 있습니다.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>JavaScript를 사용하여 온라인 SharePoint 이미지 로드를 지연하여 페이지 로드 시간 개선

JavaScript를 사용하여 웹 브라우저에서 이미지를 미리 페치하지 못하게 할 수 있습니다. 그러면 전체 문서 렌더링 속도가 향상됩니다. 이렇게하려면 태그에서 src 특성 값을 제거하고 데이터 특성의 파일 \<img\> 경로(예: data-src)로 바니다. 예시:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

이 방법을 사용하면 브라우저에서 즉시 이미지를 다운로드하지 않습니다. 이미지가 이미 뷰포트에 있는 경우 JavaScript는 브라우저에 데이터 특성에서 URL을 검색하고 src 특성의 값으로 삽입합니다. 이미지는 사용자가 스크롤할 때만 로드됩니다.
  
이러한 모든 기능을 사용하려면 JavaScript를 사용해야 합니다.
  
텍스트 파일에서 **isElementInViewport()** 함수를 정의하여 요소가 사용자에게 표시되는 브라우저의 일부에 있는지 여부를 검사합니다.
  
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

그런 다음 **loadItemsInView() 함수에 isElementInViewport()를** 사용 합니다.  **loadItemsInView()** 함수는 사용자가 볼 수 있는 브라우저의 일부에 있는 경우 data-src 특성 값이 있는 모든 이미지를 로드합니다. 텍스트 파일에 다음 함수를 추가합니다.
  
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

마지막으로 다음 예제와 같이 **window.onscroll()** 내에서 **loadItemsInView()를** 호출합니다. 이렇게 하면 뷰포트에 있는 모든 이미지가 사용자에게 필요하지만 이전과는 다른 것으로 로드됩니다. 텍스트 파일에 다음을 추가합니다.
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

SharePoint Online의 경우 작업 영역 태그의 스크롤 이벤트에 다음 #s4 연결해야 \<div\> 합니다. 이는 리본 메뉴가 페이지 맨 위에 연결된 상태로 유지되도록 창 이벤트가 보다도기 때문에 그 이유는 바로 그 이유는 바로 창 이벤트입니다.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

텍스트 파일을 확장명을 사용하여 JavaScript 파일로 .js 예로 delayLoadImages.js.
  
콘텐츠 작성을 마쳤으면 delayLoadImages.js Online의 마스터 페이지에 파일의 내용을 추가할 SharePoint 있습니다. 이 작업을 위해 마스터 페이지의 헤더에 스크립트 링크를 추가합니다. 마스터 페이지에 있는 경우 해당 마스터 페이지 레이아웃을 사용하는 SharePoint Online 사이트의 모든 페이지에 JavaScript가 적용됩니다. 또는 사이트의 한 페이지에서만 사용하려는 경우 스크립트 편집기 웹 파트를 사용하여 페이지에 JavaScript를 넣습니다. 자세한 내용은 다음 항목을 참조하세요.
  
- [How to: Apply a master page to a site in SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [How to: Create a page layout in SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>예제: delayLoadImages.js Online의 마스터 페이지에서 JavaScript SharePoint 참조
  
이 작업을 위해서는 마스터 페이지에서 jQuery도 참조해야 합니다. 다음 예제에서는 초기 페이지 로드에서 로드된 이미지가 하나뿐이지만 페이지에 이미지가 여러 개 더 있는 경우를 볼 수 있습니다.
  
![페이지에 로드된 하나의 이미지를 보여 주는 스크린샷.](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
다음 스크린샷은 보기로 스크롤한 후 다운로드되는 나머지 이미지를 보여줍니다.
  
![페이지에 로드된 여러 이미지를 보여 주는 스크린샷.](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
JavaScript를 사용하여 이미지 로드를 지연하는 것이 성능을 높이는 효과적인 기술일 수 있습니다. 그러나 공개 웹 사이트에 이 기술을 적용하면 검색 엔진이 정기적으로 구성한 이미지를 크롤링하는 방법과 동일한 방식으로 이미지를 크롤링할 수 없습니다. 이 경우 페이지가 로드될 때까지 이미지 자체의 메타데이터가 실제로 없는 것이기 때문에 검색 엔진의 순위에 영향을 줄 수 있습니다. 검색 엔진 크롤러는 HTML만 읽기만 하므로 페이지에 이미지가 콘텐츠로 표시되지 않습니다. 이미지는 검색 결과에서 페이지의 순위를 정하는 데 사용되는 요소 중 하나입니다. 이를 해결하는 한 가지 방법은 이미지에 소개 텍스트를 사용하는 것입니다.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>GitHub 코드 샘플: 성능을 향상하기 위해 JavaScript 삽입

JavaScript 삽입에서 제공되는 [문서](https://go.microsoft.com/fwlink/p/?LinkId=524759) 및 코드 샘플을 GitHub.
  
## <a name="see-also"></a>참고 항목

[2013 및 Office 지원되는 엔터프라이즈용 Microsoft 365 앱](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[How to: Apply a master page to a site in SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[How to: Create a page layout in SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)
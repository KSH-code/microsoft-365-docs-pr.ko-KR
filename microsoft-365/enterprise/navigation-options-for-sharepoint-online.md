---
title: SharePoint Online에 대한 탐색 옵션
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
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
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: 이 문서에서는 SharePoint Online에서 SharePoint 게시를 사용하도록 설정된 탐색 옵션 사이트에 대해 설명합니다.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696322"
---
# <a name="navigation-options-for-sharepoint-online"></a>SharePoint Online에 대한 탐색 옵션

이 문서에서는 SharePoint Online에서 SharePoint 게시를 사용하도록 설정된 탐색 옵션 사이트에 대해 설명합니다. 탐색 선택 및 구성은 SharePoint Online의 사이트 성능 및 확장성에 큰 영향을 미치게 됩니다. SharePoint 게시 사이트 서식 파일은 중앙 집중식 포털에 필요한 경우만 사용해야 합니다. 게시 기능은 특정 사이트에서만 사용하도록 설정해야 합니다. 잘못 사용될 경우 성능에 영향을 줄 수 있는 절대적으로 필요한 경우만 사용할 수 있습니다.

>[!NOTE]
>메가 메뉴, 계단식 탐색 또는 허브 탐색과 같은 최신 SharePoint 탐색 옵션을 사용하는 경우 이 문서는 사이트에 적용되지 않습니다. 최신 SharePoint 사이트 아키텍처는 보다 평면적인 사이트 계층 구조와 허브 및 스포크 모델을 활용합니다. 이렇게 하면 SharePoint 게시 기능을 사용할 필요가 없는 많은 시나리오를 얻을 수 있습니다.

## <a name="overview-of-navigation-options"></a>탐색 옵션 개요

탐색 공급자 구성은 전체 사이트의 성능에 큰 영향을 줄 수 있으며, SharePoint 사이트의 요구 사항에 따라 효과적으로 확장되는 탐색 공급자 및 구성을 선택하려면 신중하게 고려해야 합니다. 첫 실행형 탐색 공급자는 두 개와 사용자 지정 탐색 구현이 있습니다.

사이트에 대한 [](#using-structural-navigation-in-sharepoint-online)구조적 탐색 캐싱을 설정하는 경우 첫 번째 옵션인 구조 탐색은 클래식 Sharepoint 사이트에 대해 SharePoint Online에서 권장되는 탐색 **옵션입니다.** 이 탐색 공급자는 현재 사이트 아래에 탐색 항목을 표시하고 선택적으로 현재 사이트 및 해당 형제 항목을 표시됩니다. 보안 자르기 및 사이트 구조 열림과 같은 추가 기능을 제공합니다. 캐싱을 사용하지 않도록 설정하면 성능 및 확장성에 부정적인 영향을 미치며 조정이 적용될 수 있습니다.

두 번째 옵션인 [**관리되는(메타데이터) 탐색은**](#using-managed-navigation-and-metadata-in-sharepoint-online)관리되는 메타데이터 용어 집합을 사용하는 탐색 항목을 표현합니다. 필요한 경우를 위해 보안 트리밍을 사용하지 않도록 설정하는 것이 좋습니다. 보안 트리밍은 이 탐색 공급자에 대한 보안 기본 설정으로 사용됩니다. 그러나 대부분의 사이트에서는 탐색 요소가 사이트의 모든 사용자에게 일관성이 유지되는 경우가 많기 때문에 보안 자르기 오버헤드가 필요하지 않습니다. 보안 조정을 사용하지 않도록 설정하는 것이 권장되는 구성을 통해 이 탐색 공급자는 사이트 구조를 열0할 필요가 없습니다. 성능에 대한 영향을 적정 수준으로 확장할 수 있습니다.

첫 실행 탐색 공급자 외에도 많은 고객이 대체 사용자 지정 탐색 구현을 성공적으로 구현했습니다. 이 [문서의](#using-search-driven-client-side-scripting) 검색 기반 클라이언트 쪽 스크립팅을 참조하세요.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>SharePoint Online 탐색 옵션의 장단점

다음 표에서는 각 옵션의 장단을 요약하여 제공합니다.

|구조적 탐색  |관리 탐색  |검색 기반 탐색  |사용자 지정 탐색 공급자  |
|---------|---------|---------|---------|
|Pros:<br/><br/>간편한 유지 관리<br/>보안이 잘림<br/>콘텐츠가 변경될 때 24시간 이내에 자동으로 업데이트<br/>     |Pros:<br/><br/>간편한 유지 관리<br/>|Pros:<br/><br/>보안이 잘림<br/>사이트가 추가될 때 자동으로 업데이트<br/>빠른 로드 시간 및 로컬로 캐시된 탐색 구조<br/>|Pros:<br/><br/>사용 가능한 다양한 옵션<br/>캐싱이 올바르게 사용될 때 빠른 로드<br/>많은 옵션이 반응형 페이지 디자인에서 잘 작동<br/>|
|Cons:<br/><br/>**캐싱을 사용하지 않도록 설정한 경우 성능에 영향을 미치기**<br/>스로틀 적용 대상<br/>|Cons:<br/><br/>사이트 구조를 반영하기 위해 자동으로 업데이트되지 않습니다.<br/>**보안 트리밍을** 사용하도록 설정하거나 탐색 구조가 복잡한 경우 성능에 영향을 미치기<br/>|Cons:<br/><br/>사이트를 쉽게 주문할 수 없음<br/>마스터 페이지를 사용자 지정해야 합니다(기술 기술 필요).<br/>|Cons:<br/><br/>사용자 지정 개발이 필요합니다.<br/>외부 데이터 원본/저장된 캐시가 필요합니다(예: Azure).<br/>|

사이트에 가장 적합한 옵션은 사이트 요구 사항 및 기술 기능에 따라 다릅니다. 콘텐츠가 변경될 때 자동으로 업데이트되는 구성하기 쉬운 탐색 공급자를 [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) 원하는 경우 캐싱을 사용하는 구조적 탐색을 사용하는 것이 좋습니다.

>[!NOTE]
>전체 사이트 구조를 더 단순하고 계층적이지 않은 구조로 단순화하여 최신 SharePoint 사이트와 동일한 원칙을 적용하면 성능이 향상되고 최신 SharePoint 사이트로의 이동이 간소화됩니다. 즉, 수백 개의 사이트(하위 웹)가 있는 단일 사이트 모음을 사용할 수 있는 대신 하위 사이트(하위 웹)가 매우 적게 있는 많은 사이트 모음을 사용할 수 있습니다.

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>SharePoint Online에서 탐색 성능 분석

[SharePoint용](https://aka.ms/perftool) 페이지 진단 도구는 SharePoint Online 최신 포털 및 클래식 게시 사이트 페이지를 모두 분석하는 Microsoft Edge 및 Chrome 브라우저용 브라우저 확장입니다. 이 도구는 SharePoint Online에서만 작동하며 SharePoint 시스템 페이지에서는 사용할 수 없습니다.

이 도구는 분석된 각 페이지에 대해 미리 정의된 규칙 집합에 대해 페이지가 수행되는 방법을 보여 주며 테스트 결과가 기준 값에 맞지 않은 경우 자세한 정보를 표시하는 보고서를 생성합니다. SharePoint Online 관리자 및 디자이너는 이 도구를 사용하여 성능 문제를 해결하여 새 페이지를 게시하기 전에 최적화할 수 있습니다.

**특히 SPRequestDuration은** SharePoint에서 페이지를 처리하는 데 걸리는 시간입니다. 탐색에 페이지 포함, 복잡한 사이트 계층 및 기타 구성 및 토폴로지 옵션이 모두 긴 기간에 크게 기여할 수 있습니다.

## <a name="using-structural-navigation-in-sharepoint-online"></a>SharePoint Online에서 구조적 탐색 사용

이 탐색은 기본적으로 사용되는 기본 제공 탐색으로, 가장 간단한 솔루션입니다. 또한 사용자 지정이 필요 없이 비기술적인 사용자는 항목을 쉽게 추가하고, 항목을 숨기고, 설정 페이지에서 탐색을 관리할 수 있습니다. [캐싱을 사용하도록 설정하는](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)것이 좋습니다. 그렇지 않으면 성능이 많이 드는 것입니다.

### <a name="how-to-implement-structural-navigation-caching"></a>구조 탐색 캐싱을 구현하는 방법

사이트 **설정 모양** 및 느낌 탐색 아래에서 전역 탐색 또는 현재 탐색에 대해 구조적 탐색이 선택되어 있는지 확인할 수  >    >  있습니다. 페이지 **표시를 선택하면** 성능에 부정적인 영향을 미치게 됩니다.

![하위 페이지 표시가 선택된 구조 탐색](../media/SPONavOptionsStructuredShowSubsites.png)

사이트 모음 수준과 사이트 수준에서 캐싱을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있으며 기본적으로 둘 다에 대해 사용하도록 설정됩니다. 사이트 모음 수준에서 사용하도록 설정하려면 **사이트** 설정 사이트 모음 관리 사이트 모음 탐색 아래에서 캐싱 사용 확인란을  >    >   **선택합니다.**

![사이트 수준에서 캐싱 사용](../media/structural-nav/structural-nav-caching-site-coll.png)

사이트 수준에서 사용하도록 설정하려면 사이트 설정 탐색 아래에서 캐싱 사용  >   **확인란을 선택합니다.**

![사이트 수준에서 캐싱 사용](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>SharePoint Online에서 관리 탐색 및 메타데이터 사용

관리 탐색은 구조적 탐색과 동일한 대부분의 기능을 다시 사용하는 데 사용할 수 있는 또 다른 첫 번째 옵션입니다. 관리되는 메타데이터는 보안 트리밍을 사용하도록 구성하거나 사용하지 않도록 구성할 수 있습니다. 보안 자르기 기능을 사용하지 않도록 구성한 경우 관리 탐색은 일정한 수의 서버 호출로 모든 탐색 링크를 로드하기 때문에 매우 효율적입니다. 그러나 보안 트리밍을 사용하도록 설정하면 관리 탐색의 성능 이점 중 일부를 사용할 수 없습니다.

보안 트리밍을 사용하도록 설정해야 하는 경우 다음을 하는 것이 좋습니다.

- 모든 친숙한 URL 링크를 단순 링크로 업데이트
- 필요한 보안 트리밍 노드를 친숙한 URL로 추가
- 탐색 항목 수를 100개 이상 및 3개 수준 이상으로 제한

탐색 구조가 사이트의 모든 사용자에게 일관된 경우가 많기 때문에 많은 사이트에서는 보안 트리밍이 필요하지 않습니다. 보안 트리밍을 사용하지 않도록 설정하고 일부 사용자가 액세스할 수 없는 링크가 탐색에 추가된 경우 링크는 계속 표시되지만 액세스 거부 메시지가 표시됩니다. 콘텐츠에 부수적으로 액세스할 위험이 없습니다.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>관리 탐색 및 결과를 구현하는 방법

관리 탐색의 세부 docs.microsoft.com 문서가 몇 가지 있습니다. 예를 들어 [SharePoint Server의 관리 탐색 개요를 참조하세요.](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

관리 탐색을 구현하기 위해 사이트의 탐색 구조에 해당하는 URL을 사용하여 용어를 설정해야 합니다. 대부분의 경우 구조 탐색을 대체하기 위해 관리 탐색을 수동으로 구성할 수도 있습니다. 예시:

![SharePoint Online 사이트 구조](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>검색 기반 클라이언트 쪽 스크립팅 사용

한 가지 일반적인 사용자 지정 탐색 구현 클래스는 탐색 노드의 로컬 캐시를 저장하는 클라이언트 렌더링 디자인 패턴을 수용합니다.

이러한 탐색 공급자는 몇 가지 주요 이점을 제공합니다.

- 일반적으로 반응형 페이지 디자인에서 잘 작동됩니다.
- 리소스 비용 없는 렌더링(및 시간 제한 후 백그라운드에서 새로 고침)할 수 있기 때문에 매우 확장성이 높고 뛰어난 기능을 제공합니다.
- 이러한 탐색 공급자는 간단한 정적 구성에서 다양한 동적 데이터 공급자에 이르기까지 다양한 전략을 사용하여 탐색 데이터를 검색할 수 있습니다.

데이터 공급자의 예로는 탐색 노드를 열고 보안 트리밍을 효율적으로 처리할 수 있는 검색 기반 탐색을 사용하는 것이 있습니다.

사용자 지정 탐색 공급자를 빌드하는 다른 인기 **있는 옵션이 있습니다.** 사용자 지정 탐색 공급자를 구축하는 방법에 대한 자세한 지침은 [SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) 포털의 탐색 솔루션을 검토하세요.

검색을 사용하면 연속 크롤링을 사용하여 백그라운드에서 구축된 인덱스를 활용할 수 있습니다. 검색 결과는 검색 인덱스에서 끌어오며 결과는 보안이 잘림됩니다. 이는 일반적으로 보안 트리밍이 필요한 경우 첫 탐색 공급자보다 빠릅니다. 구조적 탐색 검색을 사용하면 특히 사이트 구조가 복잡한 경우 페이지 로드 시간이 상당히 빠를 수 있습니다. 관리 탐색에 대한 이 기능의 주요 이점은 보안 트리밍의 이점입니다.

이 방법은 사용자 지정 마스터 페이지를 만들고, 첫 실행 탐색 코드를 사용자 지정 HTML로 바꾸는 것입니다. 파일의 탐색 코드를 바꾸기 위해 다음 예제에 설명된 다음 절차에 따라 다음을 `seattle.html` 실행합니다. 이 예제에서는 파일을 열고 전체 요소를 사용자 지정 `seattle.html` `id="DeltaTopNavigation"` HTML 코드로 바립니다.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>예제: 마스터 페이지에서 첫 실행 탐색 코드 바꾸기

1. 사이트 설정 페이지로 이동합니다.
2. 마스터 페이지를 클릭하여 마스터 페이지 **갤러리를 열 수 있습니다.**
3. 여기에서 라이브러리를 탐색하고 파일을 다운로드할 수 `seattle.master` 있습니다.
4. 텍스트 편집기를 사용하여 코드를 편집하고 다음 스크린샷에서 코드 블록을 삭제합니다.<br/>![표시된 코드 블록 삭제](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. 코드와 태그 사이에 있는 코드를 제거하고 다음 코드 코드로 `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` 대체합니다.<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. 시작에 있는 로드 이미지 고정 태그의 URL을 사이트 모음의 로드 이미지에 대한 링크로 바니다. 변경한 후 파일 이름을 바 변경한 다음 마스터 페이지 갤러리에 업로드합니다. 그러면 새 .master 파일이 생성됩니다.<br/>
7. 이 HTML은 JavaScript 코드에서 반환된 검색 결과로 채워지는 기본 마크업입니다. 다음 코드 코드에서 설명한 var 루트 = "사이트 모음 URL"의 값을 변경하려면 코드를 편집해야 합니다.<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. 결과는 self.nodes 배열에 할당됩니다. 계층 구조는 배열 self.hierarchy에 출력을 linq.js 사용하여 개체에서 만들어집니다. 이 배열은 HTML에 바인딩된 개체입니다. 이는 toggleView() 함수에서 자체 개체를 ko.applyBinding() 함수에 전달하여 수행됩니다.<br/>그러면 계층 구조 배열이 다음 HTML에 바인딩됩니다.<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

이벤트 처리기 및 최상위 탐색에 추가되어 함수에서 수행되는 하위 페이지 드롭다운 메뉴를 `mouseenter` `mouseexit` `addEventsToElements()` 처리합니다.

복잡한 탐색 예제에서 로컬 캐싱 없이 새 페이지 로드는 관리 탐색 방식과 비슷한 결과를 얻기 위해 서버에서 소요된 시간을 벤치마크 구조 탐색에서 끊어졌다는 표시를 보여 주며,

### <a name="about-the-javascript-file"></a>JavaScript 파일...

>[!NOTE]
>사용자 지정 JavaScript를 사용하는 경우 공용 CDN이 사용하도록 설정되어 있으며 파일이 CDN 위치에 있는지 확인합니다.

전체 JavaScript 파일은 다음과 같습니다.

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

함수에 위에 표시된 코드를 요약하면 만들어진 다음 해당 개체에 대한 함수가 `jQuery $(document).ready` `viewModel object` `loadNavigationNodes()` 호출됩니다. 이 함수는 클라이언트 브라우저의 HTML5 로컬 저장소에 저장된 이전에 구축된 탐색 계층 구조를 로드하거나 함수를 `queryRemoteInterface()` 호출합니다.

`QueryRemoteInterface()` 스크립트의 앞부분에서 정의한 쿼리 매개 변수와 함께 함수를 사용하여 요청을 빌드한 다음 서버에서 데이터를 `getRequest()` 반환합니다. 이 데이터는 기본적으로 다양한 속성을 사용하여 데이터 전송 개체로 표현되는 사이트 모음의 모든 사이트의 배열입니다.

이 데이터는 이전에 정의한 개체로 구문 분석됩니다. 이 개체는 앞에서 정의한 HTML에 값을 데이터 바인딩하여 사용할 관찰 가능한 속성을 `SPO.Models.NavigationNode` `Knockout.js` 만드는 데 사용됩니다.

그런 다음 개체가 결과 배열에 추가됩니다. 이 배열은 Knockout을 사용하여 JSON으로 구문 분석되고 향후 페이지 로드 시 성능을 향상하기 위해 로컬 브라우저 저장소에 저장됩니다.

### <a name="benefits-of-this-approach"></a>이 방법의 이점

이 방법의 [](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) 주요 이점 중 하나는 HTML5 로컬 저장소를 사용하여 다음에 페이지를 로드할 때 탐색이 로컬에 저장됩니다. 구조 탐색에 검색 API를 사용할 때의 주요 성능 향상을 얻을 수 있습니다. 그러나 이 기능을 실행하고 사용자 지정하는 데는 몇 가지 기술적 기능이 있습니다.

예제 [구현에서](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)사이트는 첫 실행 구조 탐색과 동일한 방식으로 순서가 정해진 것입니다. 사전순 이 순서에서 을(를) 를(를) 를(를) 의하면 개발 및 유지 관리가 더 복잡합니다. 또한 이 방법을 사용하려면 지원되는 마스터 페이지에서 탈피해야 합니다. 사용자 지정 마스터 페이지가 유지 관리되지 않는 경우 사이트는 Microsoft에서 마스터 페이지를 업데이트 및 개선할 때 누락됩니다.

위의 [코드에는](#about-the-javascript-file) 다음과 같은 종속성이 있습니다.

- jQuery - https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ 또는 github.com/neuecc/linq.js

현재 버전의 LinqJS에는 위의 코드에 사용된 ByHierarchy 메서드가 포함되어 있지 않은 경우 탐색 코드가 중단됩니다. 이 문제를 해결하기 위해 줄 앞에 다음 Linq.js 메서드를 `Flatten: function ()` 추가합니다.

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>관련 항목

[SharePoint Server의 관리 탐색 개요](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[구조적 탐색 캐싱 및 성능](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)

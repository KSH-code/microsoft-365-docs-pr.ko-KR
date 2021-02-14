---
title: 검토 집합을 위한 고급 eDiscovery 대시보드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 대시보드를 사용하여 검토 집합을 신속하게 분석하여 검토 전략을 개발하는 데 도움이 되는 추세 또는 주요 통계를 식별합니다.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741703"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a><span data-ttu-id="a8106-103">검토 집합을 위한 고급 eDiscovery 대시보드</span><span class="sxs-lookup"><span data-stu-id="a8106-103">Advanced eDiscovery dashboard for review sets</span></span>

<span data-ttu-id="a8106-104">Advanced eDiscovery의 경우 검토해야 하는 많은 문서 및 전자 메일 메시지가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-104">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="a8106-105">검토 프로세스를 시작하기 전에 빠르게 코퍼스를 분석하여 검토 전략을 개발하는 데 도움이 되는 추세 또는 주요 통계를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-105">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="a8106-106">이를 위해 고급 eDiscovery 대시보드를 사용하여 검토 집합을 빠르게 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-106">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="a8106-107">1단계: 검토 집합 대시보드에 위젯 만들기</span><span class="sxs-lookup"><span data-stu-id="a8106-107">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="a8106-108">보안 & 준수 센터에서 **eDiscovery > Advanced eDiscovery로** 이동하여 조직의 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-108">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="a8106-109">기존 사례를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-109">Select an existing case.</span></span>
  
3. <span data-ttu-id="a8106-110">검토 집합 **탭을 클릭한** 다음 검토 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-110">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="a8106-111">개별 결과 **드롭다운** 목록에서 검색 프로필 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8106-111">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](../media/dashboardpivot.png)

   <span data-ttu-id="a8106-113">검색 **프로필 보기** 페이지가 표시됩니다. 이 페이지를 처음 표시하면 세 개의 기본 위젯이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-113">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![대시보드](../media/dashboardonly.png)
  
5. <span data-ttu-id="a8106-115">새 **위젯을 클릭한** 다음 다음 항목 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-115">Click the **New  widget** and then select one of the following items:</span></span>

   ![새 위젯 드롭다운 목록](../media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="a8106-117">**라이브러리에서 선택:** 위젯의 기본 라이브러리를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-117">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="a8106-118">위젯을 클릭한 다음  추가를 클릭하여 검색 프로필 보기 페이지의 위젯에 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8106-118">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="a8106-119">**사용자 지정 위젯 만들기:** 사용자 지정 위젯을 설정하는 데 사용할 수 있는 플라이아웃 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-119">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="a8106-120">사용자 지정 위젯을 만들하려면 위젯 플라이아웃 추가 페이지에서 **다음을** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-120">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![위젯 만들기](../media/addwidget.png)

    <span data-ttu-id="a8106-122">a.</span><span class="sxs-lookup"><span data-stu-id="a8106-122">a.</span></span> <span data-ttu-id="a8106-123">위젯 제목 표시줄에 표시되는 위젯의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-123">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="a8106-124">위젯 이름을 정해야 하지만 위젯 데이터를 식별하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-124">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="a8106-125">b.</span><span class="sxs-lookup"><span data-stu-id="a8106-125">b.</span></span> <span data-ttu-id="a8106-126">위젯 데이터에 사용할  피벗 선택 드롭다운 목록에서 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-126">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="a8106-127">이 목록의 항목은 검토 집합의 항목에 대한 검색 가능한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-127">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="a8106-128">이러한 속성에 대한 설명은 [Advanced eDiscovery의](document-metadata-fields-in-Advanced-eDiscovery.md)문서 메타데이터 필드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8106-128">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="a8106-129">위젯의 피벗 옵션은 이 항목의 검색 가능한 필드 이름 **열에** 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-129">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="a8106-130">c.</span><span class="sxs-lookup"><span data-stu-id="a8106-130">c.</span></span> <span data-ttu-id="a8106-131">차트 종류를 선택하여 선택한 피벗 속성의 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-131">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="a8106-132">**추가를** 클릭하여 사용자 지정 위젯을 만들고 검색 프로필 보기 페이지에 **표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8106-132">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="a8106-133">2단계: 검토 집합 검색 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="a8106-133">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="a8106-134">위젯 제목 표시줄에서 **...를** 클릭한 다음 조건 **적용을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8106-134">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![대시보드](../media/searchprofilehome.png)

2. <span data-ttu-id="a8106-136">플라이아웃 페이지에서 위젯 키 또는 위젯 차트의 요소를 클릭하여 필터를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="a8106-136">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![CreateFilter](../media/applyconditionfilter.png)

3. <span data-ttu-id="a8106-138">다른 위젯 여러 위젯에 대해 1-2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-138">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="a8106-139">완료되면 쿼리로 저장을  클릭하여 조건을 검토 집합에 대한 새 검색 쿼리로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-139">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![Query](../media/savequery.png)

5. <span data-ttu-id="a8106-141">검색 프로필 **보기를 닫아** 검색 결과 보기로 돌아오게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8106-141">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="a8106-142">시각적 필터를 만든 경우 결과 쿼리는 표시되는 검색 결과에 적용되고 4단계에서 저장한 검색 쿼리는 저장된 쿼리 아래에 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a8106-142">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="a8106-143">검토 집합 쿼리에 대한 자세한 내용은 검토 집합의 데이터 [쿼리를 참조하세요.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="a8106-143">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

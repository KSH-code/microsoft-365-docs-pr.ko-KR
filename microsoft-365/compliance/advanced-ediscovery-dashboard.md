---
title: 검토 집합에 대 한 고급 eDiscovery 대시보드
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
description: ''
ms.openlocfilehash: 127e2c9a04977bf6e902a1ce669fa9e4248e3ef2
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662256"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a><span data-ttu-id="938e5-102">검토 집합에 대 한 고급 eDiscovery 대시보드 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="938e5-102">Advanced eDiscovery dashboard for review sets (preview)</span></span>

<span data-ttu-id="938e5-103">고급 eDiscovery의 경우 검토 해야 하는 문서 및 전자 메일 메시지의 양이 많을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-103">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="938e5-104">검토 프로세스를 시작 하기 전에 모음를 빠르게 분석 하 여 검토 전략을 개발 하는 데 도움이 되는 추세 또는 주요 통계를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-104">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="938e5-105">이렇게 하려면 검토 집합에 대해 고급 eDiscovery 대시보드를 사용 하 여 모음를 빠르게 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-105">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="938e5-106">1 단계: 검토 집합 대시보드에 위젯 만들기</span><span class="sxs-lookup"><span data-stu-id="938e5-106">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="938e5-107">보안 & 준수 센터에서 **eDiscovery > Advanced eDiscovery** 로 이동 하 여 조직의 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-107">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="938e5-108">기존 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-108">Select an existing case.</span></span>
  
3. <span data-ttu-id="938e5-109">**검토 설정** 탭을 클릭 한 후 검토 집합을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-109">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="938e5-110">**개별 결과** 드롭다운 목록에서 **검색 프로필 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-110">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](media/dashboardpivot.png)

   <span data-ttu-id="938e5-112">**검색 프로필 보기** 페이지가 표시 됩니다. 이 페이지를 처음 표시할 때 세 개의 기본 위젯을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-112">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![대시보드](media/dashboardonly.png)
  
5. <span data-ttu-id="938e5-114">**새 위젯을** 클릭 하 고 다음 항목 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-114">Click the **New  widget** and then select one of the following items:</span></span>

   ![새 위젯 드롭다운 목록](media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="938e5-116">**라이브러리에서 선택:** 위젯의 기본 라이브러리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-116">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="938e5-117">위젯을 클릭 한 다음 **추가** 를 클릭 하 여 **검색 프로필 보기** 페이지의 위젯에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-117">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="938e5-118">**사용자 지정 위젯 만들기:** 사용자 지정 위젯을 설정 하는 데 사용할 수 있는 플라이 아웃 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-118">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="938e5-119">사용자 지정 위젯을 만들려면 위젯 플라이 아웃 **추가** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-119">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![위젯 만들기](media/addwidget.png)

    <span data-ttu-id="938e5-121">a.</span><span class="sxs-lookup"><span data-stu-id="938e5-121">a.</span></span> <span data-ttu-id="938e5-122">위젯 제목 표시줄에 표시 되는 위젯 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-122">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="938e5-123">Widget 이름은 필수 이지만 widget 데이터를 식별 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-123">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="938e5-124">b.</span><span class="sxs-lookup"><span data-stu-id="938e5-124">b.</span></span> <span data-ttu-id="938e5-125">위젯 데이터에 사용 될 속성을 **피벗 선택** 드롭다운 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-125">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="938e5-126">이 목록의 항목은 검토 집합의 항목에 대 한 검색 가능 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-126">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="938e5-127">이러한 속성에 대 한 자세한 내용은 [Advanced eDiscovery의 문서 메타 데이터 필드](document-metadata-fields-in-Advanced-eDiscovery.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="938e5-127">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="938e5-128">위젯의 피벗 옵션은이 항목의 **검색 가능한 필드 이름** 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-128">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="938e5-129">c.</span><span class="sxs-lookup"><span data-stu-id="938e5-129">c.</span></span> <span data-ttu-id="938e5-130">차트 종류를 선택 하 여 선택한 피벗 속성의 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-130">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="938e5-131">**추가** 를 클릭 하 여 사용자 지정 위젯을 만들고 **검색 프로필 보기** 페이지에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-131">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="938e5-132">2 단계: 검토 집합 검색 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="938e5-132">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="938e5-133">위젯 제목 표시줄에서 ... 조건을 클릭 한 다음 **조건 적용**을 **클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="938e5-133">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![대시보드](media/searchprofilehome.png)

2. <span data-ttu-id="938e5-135">플라이 아웃 페이지에서 위젯 키 또는 위젯 차트의 요소를 클릭 하 여 필터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-135">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![CreateFilter](media/applyconditionfilter.png)

3. <span data-ttu-id="938e5-137">다른 widget 여러 widget에 대해 1-2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-137">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="938e5-138">작업이 완료 되 면 **쿼리로 저장** 을 클릭 하 여 조건을 검토 집합에 대 한 새 검색 쿼리로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-138">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![Query](media/savequery.png)

5. <span data-ttu-id="938e5-140">**검색 프로필 보기** 를 닫아 검색 결과 보기로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-140">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="938e5-141">시각적 필터를 만든 경우 결과 쿼리가 표시 되는 검색 결과에 적용 되 고 4 단계에서 저장 한 검색 쿼리가 **저장 된 쿼리**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938e5-141">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="938e5-142">집합 쿼리 검토에 대 한 자세한 내용은 [Query the data in a review set](review-set-search.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="938e5-142">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

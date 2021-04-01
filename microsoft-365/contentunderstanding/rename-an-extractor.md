---
title: Microsoft SharePoint Syntex에서 추출기 이름 변경
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex에서 추출기를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445993"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="eaa61-103">Microsoft SharePoint Syntex에서 추출기 이름 변경</span><span class="sxs-lookup"><span data-stu-id="eaa61-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="eaa61-104">추출된 데이터 필드를 다른 이름으로 참조하려는 경우 어느 시점에서 추출기의 이름을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="eaa61-105">예를 들어, 조직에서 계약 문서를 변경하기로 결정하고 문서에서 "고객"을 "클라이언트"라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="eaa61-106">모델에서 "고객" 필드를 추출한 경우 이름을 "클라이언트"로 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="eaa61-107">업데이트된 모델을 SharePoint 문서 라이브러리에 동기화하면 문서 라이브러리 보기에 새로운 "클라이언트" 열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="eaa61-108">보기는 과거 활동의 경우 "고객" 열을 유지하지만, 모델에서 처리하는 모든 새 문서에 대한 새 "클라이언트" 열을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="eaa61-109">표시할 새 열 이름의 경우 이전에 적용한 문서 라이브러리에 업데이트된 모델을 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="eaa61-110">추출기 이름 변경</span><span class="sxs-lookup"><span data-stu-id="eaa61-110">Rename an extractor</span></span>

<span data-ttu-id="eaa61-111">다음 단계에 따라 엔터티 추출기 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="eaa61-112">콘텐츠 센터에서 모델 목록을 보려면 **모델** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="eaa61-113">**모델** 페이지의 **이름** 열에서 추출기의 이름을 변경할 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="eaa61-114">**엔터티 추출기** 에서 이름을 변경할 추출기의 이름을 선택한 다음 **이름 바꾸기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![이름 변경 옵션이 강조 표시된 일부 추출기를 보여주는 엔터티 추출기 섹션의 스크린 샷입니다.](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="eaa61-116">**엔터티 추출기 이름 변경** 패널에서:</span><span class="sxs-lookup"><span data-stu-id="eaa61-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="eaa61-117">a.</span><span class="sxs-lookup"><span data-stu-id="eaa61-117">a.</span></span> <span data-ttu-id="eaa61-118">**새 이름** 에서 추출기의 새 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![엔터티 추출기 패널을 보여주는 스크린샷](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="eaa61-120">b.</span><span class="sxs-lookup"><span data-stu-id="eaa61-120">b.</span></span> <span data-ttu-id="eaa61-121">(선택 사항) **고급 설정** 에서 기존 사이트 열을 연결할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="eaa61-122">**이름 변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa61-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaa61-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaa61-123">See Also</span></span>
[<span data-ttu-id="eaa61-124">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="eaa61-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="eaa61-125">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="eaa61-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="eaa61-126">모델 이름 변경</span><span class="sxs-lookup"><span data-stu-id="eaa61-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="eaa61-127">설명 유형</span><span class="sxs-lookup"><span data-stu-id="eaa61-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="eaa61-128">추출기를 만들 때 용어 저장소 분류 활용</span><span class="sxs-lookup"><span data-stu-id="eaa61-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="eaa61-129">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="eaa61-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="eaa61-130">모델 적용</span><span class="sxs-lookup"><span data-stu-id="eaa61-130">Apply a model</span></span>](apply-a-model.md) 

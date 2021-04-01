---
title: Microsoft SharePoint Syntex에서 모델 복제
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
description: Microsoft SharePoint Syntex에서 모델을 복제하는 방법과 이유에 대해 자세히 알 수 있습니다.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446039"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="e3ddd-103">Microsoft SharePoint Syntex에서 모델 복제</span><span class="sxs-lookup"><span data-stu-id="e3ddd-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="e3ddd-104">문서 이해 모델을 복제하면 새 모델을 만들어야 하하고 기존 모델이 필요한 모델과 매우 유사하다는 것을 알고 있는 경우에 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="e3ddd-105">예를 들어, "계약서"라는 기존 모델은 작업에 필요한 동일한 파일을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="e3ddd-106">새 모델은 기존 데이터의 일부를 추출하지만 일부 추가 데이터를 추출하려면 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="e3ddd-107">처음부터 새 모델을 만들고 교육하는 대신 모델 복제 기능을 사용하여 계약 모델의 복사본을 만들 수 있습니다. 이 복사본은 예제 파일 및 엔터티 추출기와 같은 모든 관련 교육 항목을 복사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="e3ddd-108">모델을 복제할 때 모델 이름을 변경한 후(예: "계약 갱신"으로) 모델을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="e3ddd-109">예를 들어, 필요 없는 기존의 추출된 필드 중 일부를 제거하도록 선택한 후 모델을 교육하여 새 필드("갱신 날짜")를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="e3ddd-110">모델 복제</span><span class="sxs-lookup"><span data-stu-id="e3ddd-110">Duplicate a model</span></span>

<span data-ttu-id="e3ddd-111">다음 단계에 따라 문서 이해 모델을 복제하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="e3ddd-112">콘텐츠 센터에서 모델 목록을 보려면 **모델** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="e3ddd-113">**모델** 페이지에서 복제할 모델을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="e3ddd-114">리본 또는 **작업 표시** 버튼(모델 이름 옆에 있음)을 사용하여 **복제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![복제 옵션이 강조 표시된 선택된 모델을 보여주는 모델 페이지의 스크린샷입니다.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="e3ddd-116">**모델 복제** 패널에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="e3ddd-117">a.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-117">a.</span></span> <span data-ttu-id="e3ddd-118">**이름** 에서 복제할 모델의 새 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![모델 복제 패널을 보여주는 스크린샷입니다.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="e3ddd-120">b.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-120">b.</span></span> <span data-ttu-id="e3ddd-121">**설명** 에서 새 모델에 대한 설명을 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="e3ddd-122">c.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-122">c.</span></span> <span data-ttu-id="e3ddd-123">(선택 사항) **고급 설정** 에서 기존 [콘텐츠 유형 ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)을 연결할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="e3ddd-124">**복제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ddd-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3ddd-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3ddd-125">See Also</span></span>
[<span data-ttu-id="e3ddd-126">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="e3ddd-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e3ddd-127">모델 이름 변경</span><span class="sxs-lookup"><span data-stu-id="e3ddd-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="e3ddd-128">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="e3ddd-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e3ddd-129">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="e3ddd-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="e3ddd-130">설명 유형</span><span class="sxs-lookup"><span data-stu-id="e3ddd-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="e3ddd-131">모델 적용</span><span class="sxs-lookup"><span data-stu-id="e3ddd-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="e3ddd-132">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="e3ddd-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
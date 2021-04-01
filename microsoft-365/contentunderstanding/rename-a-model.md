---
title: Microsoft SharePoint Syntex에서 모델 이름 변경
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
description: Microsoft SharePoint Syntex에서 모델 이름을 변경하는 방법과 그 이유에 대해 알아보세요.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446001"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="72288-103">Microsoft SharePoint Syntex에서 모델 이름 변경</span><span class="sxs-lookup"><span data-stu-id="72288-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="72288-104">문서 이해 모델의 이름을 변경하고 싶은 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72288-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="72288-105">일반적인 예로는 모델의 초기 초안을 작성할 때 최종 이름에 대해 많은 생각을 하지 않았을 수 있습니다(예: "AlexWilburModel1"이라는 이름을 붙였을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="72288-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="72288-106">모델을 마무리하고 사용하는 단계에 가까워져서 더 적절한 이름이 "계약 갱신"이라는 것을 알게 되고 이름을 바꾸고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="72288-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="72288-107">또 다른 예로는 조직에서 프로세스 또는 문서 유형을 다른 이름으로 참조하도록 결정할 때가 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="72288-108">예를 들어, 모델을 만들고 적용할 준비가 된 후에는 조직에서 모든 "계약"을 "계약"으로 공식 지칭하도록 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72288-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="72288-109">필요한 경우 모델 이름을 "계약 갱신"에서 "계약 갱신"으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72288-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72288-110">문서 라이브러리에 적용되지 않은 문서 이해 모델만 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72288-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="72288-111">모델 이름을 바꾸면 모델과 연결된 [ 컨텐츠 유형](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)의 이름도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="72288-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="72288-112">모델 이름 변경</span><span class="sxs-lookup"><span data-stu-id="72288-112">Rename a model</span></span>

<span data-ttu-id="72288-113">다음 단계에 따라 문서 이해 모델의 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="72288-114">콘텐츠 센터에서 모델 목록을 보려면 **모델** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="72288-115">**모델** 페이지에서 이름을 변경할 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="72288-116">리본 또는 **작업 표시** 버튼(모델 이름 옆에 있음)을 사용하여 **이름 변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![이름 변경 옵션이 강조 표시된 선택된 모델을 보여주는 모델 페이지의 스크린샷입니다.](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="72288-118">**모델 이름 변경** 패널에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="72288-119">a.</span><span class="sxs-lookup"><span data-stu-id="72288-119">a.</span></span> <span data-ttu-id="72288-120">**새 이름** 에서 이름을 변경할 모델의 새 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![모델 이름 변경 패널을 보여주는 스크린샷입니다.](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="72288-122">b.</span><span class="sxs-lookup"><span data-stu-id="72288-122">b.</span></span> <span data-ttu-id="72288-123">(선택 사항) **고급 설정** 에서 기존 [콘텐츠 유형 ](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)을 연결할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="72288-124">**기존 컨텐츠 유형 사용** 을 선택하면 선택한 컨텐츠 유형과 일치하도록 모델 이름이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="72288-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="72288-125">**이름 변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="72288-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="72288-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72288-126">See Also</span></span>
[<span data-ttu-id="72288-127">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="72288-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="72288-128">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="72288-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="72288-129">추출기 이름 변경</span><span class="sxs-lookup"><span data-stu-id="72288-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="72288-130">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="72288-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="72288-131">설명 유형</span><span class="sxs-lookup"><span data-stu-id="72288-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="72288-132">모델 적용</span><span class="sxs-lookup"><span data-stu-id="72288-132">Apply a model</span></span>](apply-a-model.md) 

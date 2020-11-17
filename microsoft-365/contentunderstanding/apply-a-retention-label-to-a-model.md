---
title: 문서 이해 모델에 보존 레이블 적용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 이 문서는 문서 이해 모델에 보존 레이블을 적용하는 방법에 대해 설명합니다.
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087478"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="bfcfa-103">문서 이해 모델에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="bfcfa-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="bfcfa-104">Microsoft SharePoint Syntex의 문서 이해 모델에 [보존 레이블](https://docs.microsoft.com/microsoft-365/compliance/retention)을 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="bfcfa-105">보존 레이블을 사용하여 문서 이해 모델이 식별하는 문서에 보존 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="bfcfa-106">예를 들어, 모델이 문서 라이브러리에 업로드된 *보험 통지* 문서를 식별할 뿐만 아니라, 지정된 기간 동안(예를 들어, 다음 5개월) 문서 라이브러리에서 이러한 문서를 삭제할 수 없도록 *비즈니스* 보존 태그를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="bfcfa-107">모델 홈페이지의 문서 설정을 통해 기존 보존 레이블을 문서 이해 모델에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="bfcfa-108">콘텐츠 이해 모델에 적용하기 위해 보존 레이블을 사용하려면 [Microsoft 365 준수 센터에서 만들고 게시](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="bfcfa-109">문서 이해 모델에 보존 레이블 추가</span><span class="sxs-lookup"><span data-stu-id="bfcfa-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="bfcfa-110">모델 홈페이지에서 **모델 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="bfcfa-111">**모델 설정** 의 **보안 및 준수** 섹션에서 **보존 레이블** 메뉴를 선택하여 모델에 적용 가능한 보존 레이블 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="bfcfa-112">![보존 레이블 메뉴](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="bfcfa-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="bfcfa-113">모델에 적용할 보존 레이블을 선택하고 **저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="bfcfa-114">모델에 보존 레이블을 적용한 후, 다음에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="bfcfa-115">새 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="bfcfa-115">New document library</span></span>
- <span data-ttu-id="bfcfa-116">모델이 이미 적용된 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="bfcfa-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="bfcfa-117">모델이 이미 적용된 문서 라이브러리에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="bfcfa-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="bfcfa-118">문서 이해 모델이 이미 문서 라이브러리에 적용된 경우, 다음을 수행하여 보존 레이블 업데이트를 동기화하여 문서 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="bfcfa-119">모델 홈페이지의 **이 모델을 사용하는 라이브러리** 섹션에서 보존 레이블 업데이트를 적용할 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="bfcfa-120">**동기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="bfcfa-121">![모델 동기화](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="bfcfa-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="bfcfa-122">업데이트를 적용한 후 모델에 동기화하면, 다음을 실행하여 이 업데이트가 적용되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="bfcfa-123">컨텐츠 센터의 **이 모델이있는 라이브러리** 섹션에서 업데이트된 모델이 적용된 라이브러리를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="bfcfa-124">문서 라이브러리 보기에서 정보 아이콘을 선택하여 모델 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="bfcfa-125">**활성 모델** 목록에서 업데이트된 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="bfcfa-126">**보존 레이블** 섹션에서 적용된 보존 레이블의 이름이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="bfcfa-127">문서 라이브러리의 모델 보기 페이지에서 새 **보존 레이블** 열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="bfcfa-128">모델이 해당 콘텐츠 유형에 속한 것으로 식별하는 파일을 분류 하고 라이브러리 보기에 나열하는 경우, 보존 레이블 열에 모델을 통해 적용된 보존 레이블 이름도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="bfcfa-129">예를 들어, 모델이 식별하는 모든 *보험 통지* 문서에는 *비지니스* 보존 레이블도 적용되어 문서 라이브러리에서 5개월 동안 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="bfcfa-130">문서 라이브러리에서 파일을 삭제하려는 경우, 보존 레이블이 적용되었기 때문에 삭제가 허용되지 않는다는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfcfa-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfcfa-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfcfa-131">See Also</span></span>
[<span data-ttu-id="bfcfa-132">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="bfcfa-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="bfcfa-133">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="bfcfa-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="bfcfa-134">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="bfcfa-134">Document Understanding overview</span></span>](document-understanding-overview.md)



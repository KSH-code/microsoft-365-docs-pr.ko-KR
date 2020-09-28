---
title: 문서에 보존 레이블 적용 모델 이해
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 이 문서에서는 문서에 보존 레이블을 적용 하는 방법을 설명 합니다.
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294926"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="f62f3-103">문서에 보존 레이블 적용 모델 이해</span><span class="sxs-lookup"><span data-stu-id="f62f3-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="f62f3-104">Microsoft SharePoint Syntex의 모델을 이해 하는 문서에 [보존 레이블을](https://docs.microsoft.com/microsoft-365/compliance/retention) 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="f62f3-105">보존 레이블을 사용 하면 문서에서 모델을 이해 하는 문서에 보존 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="f62f3-106">예를 들어 모델이 문서 라이브러리에 업로드 되는 *보험 공지* 문서를 식별 하 고, 지정 된 기간 (예: 다음 5 개월) 동안 문서 라이브러리에서 이러한 문서를 삭제할 수 없도록 *비즈니스* 보존 태그를 적용 하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="f62f3-107">모델의 홈 페이지에 있는 모델 설정을 통해 기존 보존 레이블을 문서에 대 한 이해 하기 위한 모델에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="f62f3-108">콘텐츠 이해 모델에 적용할 수 있는 보존 레이블을 [Microsoft 365 준수 센터에서 작성 하 고 게시](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="f62f3-109">문서에 보존 레이블을 추가 하려면 모델 이해</span><span class="sxs-lookup"><span data-stu-id="f62f3-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="f62f3-110">모델 홈 페이지에서 **모델 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="f62f3-111">**모델 설정**의 **보안 및 준수** 섹션에서 **보존 레이블** 메뉴를 선택 하 여 모델에 적용할 수 있는 보존 레이블 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="f62f3-112">![보존 레이블 메뉴](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="f62f3-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="f62f3-113">모델에 적용할 보존 레이블을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="f62f3-114">모델에 보존 레이블을 적용 한 후에는 다음에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="f62f3-115">새 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="f62f3-115">New document library</span></span>
- <span data-ttu-id="f62f3-116">모델이 이미 적용 된 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="f62f3-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="f62f3-117">모델이 이미 적용 된 문서 라이브러리에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="f62f3-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="f62f3-118">문서 라이브러리에 모델 이해 모델이 이미 적용 되어 있는 경우 다음을 수행 하 여 보존 레이블 업데이트를 동기화 하 여 문서 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="f62f3-119">모델 홈 페이지의 **이 모델을 가진 라이브러리** 섹션에서 보존 레이블 업데이트를 적용할 문서 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="f62f3-120">**동기화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="f62f3-121">![동기화 모델](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="f62f3-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="f62f3-122">업데이트를 적용 하 고 모델에 동기화 한 후에는 다음을 수행 하 여 해당 업데이트가 적용 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="f62f3-123">콘텐츠 센터의 **이 모델을 가진 라이브러리** 섹션에서 업데이트 된 모델이 적용 된 라이브러리를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="f62f3-124">문서 라이브러리 보기에서 정보 아이콘을 선택 하 여 모델 속성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="f62f3-125">**활성 모델** 목록에서 업데이트 된 모델을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="f62f3-126">**보존 레이블** 섹션에 적용 된 보존 레이블의 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="f62f3-127">문서 라이브러리의 모델 보기 페이지에 새 **보존 레이블** 열이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="f62f3-128">모델에서 해당 콘텐츠 형식에 속하는 것으로 식별 되는 파일을 분류 하 여 라이브러리 보기에 나열 하면 보존 레이블 열에 모델을 통해 적용 된 보존 레이블의 이름도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="f62f3-129">예를 들어 모델에서 식별 하는 모든 *보험 공지* 문서에는 *비즈니스* 보존 레이블도 적용 되므로 5 개월이 아닌 문서 라이브러리에서 삭제 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="f62f3-130">문서 라이브러리에서 파일을 삭제 하려고 하면 적용 된 보존 레이블로 인해 허용 되지 않는 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f62f3-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="f62f3-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f62f3-131">See Also</span></span>
[<span data-ttu-id="f62f3-132">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="f62f3-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="f62f3-133">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="f62f3-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="f62f3-134">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="f62f3-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="f62f3-135">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="f62f3-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  

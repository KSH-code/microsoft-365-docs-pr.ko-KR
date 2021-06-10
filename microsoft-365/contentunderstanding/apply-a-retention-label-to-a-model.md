---
title: 모델에 보존 레이블 적용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
description: 이 문서는 SharePoint Syntex에서 모델에 보존 레이블을 적용하는 방법에 대해 설명합니다.
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861614"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="e1043-103">SharePoint Syntex에서 모델에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="e1043-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="e1043-104">Microsoft SharePoint Syntex의 모델에 [보존 레이블](../compliance/retention.md)을 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="e1043-105">문서 이해 모델과 양식 처리 모델 모두에서 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="e1043-106">보존 레이블을 사용하여 모델이 식별하는 문서에 보존 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="e1043-107">예를 들어, 모델이 문서 라이브러리에 업로드된 *보험 통지* 문서를 식별할 뿐만 아니라, 지정된 기간 동안(예를 들어, 다음 5개월) 문서 라이브러리에서 이러한 문서를 삭제할 수 없도록 *비즈니스* 보존 태그를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="e1043-108">모델 홈페이지의 문서 설정을 통해 기존 보존 레이블을 모델에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="e1043-109">문서 이해 모델에 적용하기 위해 보존 레이블을 사용하려면 [Microsoft 365 준수 센터에서 만들고 게시](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="e1043-110">문서 이해 모델에 보존 레이블 추가</span><span class="sxs-lookup"><span data-stu-id="e1043-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="e1043-111">모델 홈페이지에서 **모델 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="e1043-112">**모델 설정** 의 **보안 및 준수** 섹션에서 **보존 레이블** 메뉴를 선택하여 모델에 적용 가능한 보존 레이블 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="e1043-113">![보존 레이블 메뉴](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="e1043-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="e1043-114">모델에 적용할 보존 레이블을 선택하고 **저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="e1043-115">모델에 보존 레이블을 적용한 후, 다음에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="e1043-116">새 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e1043-116">New document library</span></span>
- <span data-ttu-id="e1043-117">모델이 이미 적용된 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e1043-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="e1043-118">모델이 이미 적용된 문서 라이브러리에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="e1043-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="e1043-119">문서 이해 모델이 이미 문서 라이브러리에 적용된 경우, 다음을 수행하여 보존 레이블 업데이트를 동기화하여 문서 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="e1043-120">모델 홈페이지의 **이 모델을 사용하는 라이브러리** 섹션에서 보존 레이블 업데이트를 적용할 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="e1043-121">**동기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="e1043-122">![모델 동기화](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="e1043-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="e1043-123">업데이트를 적용한 후 모델에 동기화하면, 다음을 실행하여 이 업데이트가 적용되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="e1043-124">컨텐츠 센터의 **이 모델이있는 라이브러리** 섹션에서 업데이트된 모델이 적용된 라이브러리를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="e1043-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="e1043-125">문서 라이브러리 보기에서 정보 아이콘을 선택하여 모델 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="e1043-126">**활성 모델** 목록에서 업데이트된 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="e1043-127">**보존 레이블** 섹션에서 적용된 보존 레이블의 이름이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="e1043-128">문서 라이브러리의 모델 보기 페이지에서 새 **보존 레이블** 열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="e1043-129">모델이 해당 콘텐츠 유형에 속한 것으로 식별하는 파일을 분류 하고 라이브러리 보기에 나열하는 경우, 보존 레이블 열에 모델을 통해 적용된 보존 레이블 이름도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="e1043-130">예를 들어, 모델이 식별하는 모든 *보험 통지* 문서에는 *비지니스* 보존 레이블도 적용되어 문서 라이브러리에서 5개월 동안 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="e1043-131">문서 라이브러리에서 파일을 삭제하려는 경우, 보존 레이블이 적용되었기 때문에 삭제가 허용되지 않는다는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="e1043-132">양식 처리 모델에 보존 레이블을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="e1043-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="e1043-133">양식 처리 모델에 적용하기 위해 보존 레이블을 사용하려면 [Microsoft 365 준수 센터에서 만들고 게시](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="e1043-134">모델을 만들 때 양식 처리 모델에 보존 레이블을 적용하거나 기존 모델에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="e1043-135">양식 처리 모델을 만들 때 보존 레이블을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="e1043-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="e1043-136">[새 양식 처리 모델](./create-a-form-processing-model.md)을 만들 때 <b>고급 설정을 선택합니다.</b></span><span class="sxs-lookup"><span data-stu-id="e1043-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="e1043-137"><b>고급 설정</b>의 <b>보존 레이블</b> 섹션에서 메뉴를 선택하고 모델을 적용하려는 보존 레이블을 선택합니다.</b></span><span class="sxs-lookup"><span data-stu-id="e1043-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![새 양식 처리 모델에 추가](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="e1043-139">나머지 모델 설정을 완료한 후 <b>만들기</b>를 선택하요 모델을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="e1043-140">기존 양식 처리 모델에 보존 레이블을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="e1043-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="e1043-141">기존 양식 처리 모델에 보존 레이블을 다양한 방법으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="e1043-142">문서 라이브러리의 자동화 메뉴를 통해</span><span class="sxs-lookup"><span data-stu-id="e1043-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="e1043-143">문서 라이브러리의 모델 활성화 설정을 통해</span><span class="sxs-lookup"><span data-stu-id="e1043-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="e1043-144">자동화 메뉴를 통해 기존 양식 처리 모델에 보존 레이블을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="e1043-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="e1043-145">모델이 적용된 문서 라이브러리의 자동화 메뉴를 통해 소유한 기존 양식 처리 모델에 보존 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="e1043-146">양식 처리 모델이 적용된 문서 라이브러리에서 <b>자동화</b> 메뉴를 선택하고 <b>AI 작성기</b>를 선택한 다음 <b>양식 처리 모델 세부 정보 보기</b>를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![자동화 메뉴](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="e1043-148">모델 세부 정보의 <b>보존 레이블</b> 섹션에서 적용할 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="e1043-149">그런 다음 <b>저장</b>을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-149">Then select <b>Save</b>.</span></span>

     ![기존 양식 처리 모델에 추가](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="e1043-151">활성 모델 설정에서 기존 양식 처리 모델에 보존 레이블을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="e1043-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="e1043-152">모델이 적용된 문서 라이브러리의 모델 설정 활성화를 통해 소유한 기존 양식 처리 모델에 보존 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="e1043-153">모델이 적용된 SharePoint 문서 라이브러리에서 <b>활성 모델 보기</b> 아이콘을 선택하고 <b>활성 모델 보기</b>를 선택합니다.</b></span><span class="sxs-lookup"><span data-stu-id="e1043-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![활성 모델 보기](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="e1043-155"><b>활성 모델</b>에서 보존 레이블을 적용할 양식 처리 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![모델 세부 정보](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="e1043-157">모델 세부 정보의 <b>보존 레이블</b> 섹션에서 적용할 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="e1043-158">그런 다음 <b>저장</b>을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="e1043-159">모델 설정 창의 모델 소유자만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1043-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e1043-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1043-160">See Also</span></span>
[<span data-ttu-id="e1043-161">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="e1043-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e1043-162">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="e1043-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e1043-163">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="e1043-163">Document Understanding overview</span></span>](document-understanding-overview.md)

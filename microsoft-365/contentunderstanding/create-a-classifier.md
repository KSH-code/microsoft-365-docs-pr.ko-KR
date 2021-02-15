---
title: 분류자 만들기
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
localization_priority: Priority
description: 분류자를 만드는 방법 알아보기
ms.openlocfilehash: bff23807fce18bf4a585dbb1ec47c1502ab686f6
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242691"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d9d3a-103">Microsoft SharePoint Syntex에서 분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="d9d3a-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="d9d3a-104">분류자는 문서 유형의 식별 및 분류를 자동화하는 데 사용할 수 있는 모델 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="d9d3a-105">예를 들어 다음 그림과 같이 문서 라이브러리에 추가되는 모든 *계약 갱신* 문서를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![계약 갱신 문서](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="d9d3a-107">분류자를 만들면 모델에 연결되는 새 [SharePoint 콘텐츠 유형](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-107">Creating a classifier enables you to create a new [SharePoint content type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="d9d3a-108">분류자를 만들 때 모델을 정의하려면 *설명* 을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="d9d3a-109">이 기능을 통해 해당 문서 유형을 일관되게 찾을 수 있는 공통 데이터를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="d9d3a-110">문서 유형의 예제("example files")를 사용하여 콘텐츠 유형이 같은 파일을 식별하도록 모델을 "교육"합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="d9d3a-111">분류자를 만들려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="d9d3a-112">모델 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-112">Name your model.</span></span>
2. <span data-ttu-id="d9d3a-113">예제 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-113">Add your example files.</span></span>
3. <span data-ttu-id="d9d3a-114">예제 파일에 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-114">Label your example files.</span></span>
4. <span data-ttu-id="d9d3a-115">설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-115">Create an explanation.</span></span>
5. <span data-ttu-id="d9d3a-116">모델을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="d9d3a-117">모델이 분류자를 사용하여 문서 유형을 식별하고 분류하는 동안 모델에 의해 식별되는 각 파일에서 특정 정보를 가져오도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="d9d3a-118">모델에 추가할 **추출기** 를 만들어 해당 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="d9d3a-119">[추출기 만들기](create-an-extractor.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="d9d3a-120">모델 이름 지정</span><span class="sxs-lookup"><span data-stu-id="d9d3a-120">Name your model</span></span>

<span data-ttu-id="d9d3a-121">모델을 만들기 위한 첫 번째 단계는 이름을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="d9d3a-122">콘텐츠 센터에서 **새 모델** 을 선택한 다음 **모델 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-122">From the content center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="d9d3a-123">**새 문서 이해 모델** 창에서 **이름** 필드에 모델 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="d9d3a-124">예를 들어 계약 갱신 문서를 식별하려는 경우 *계약 갱신* 모델에 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="d9d3a-125">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-125">Choose **Create**.</span></span> <span data-ttu-id="d9d3a-126">이 작업을 통해 모델에 대한 홈페이지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-126">This creates a home page for the model.</span></span></br>

    ![분류자 모델 홈페이지](../media/content-understanding/model-home.png)

<span data-ttu-id="d9d3a-128">모델을 만들 때 새 사이트 콘텐츠 유형도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="d9d3a-129">콘텐츠 유형은 공통 특성을 가지는 문서의 범주를 나타내며 해당 특정 콘텐츠에 대한 열 또는 메타데이터 속성 모음을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="d9d3a-130">SharePoint 콘텐츠 유형은 [콘텐츠 유형 갤러리](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)를 통해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="d9d3a-131">이 예제에서는 모델을 만들 때 새 *계약 갱신* 콘텐츠 유형으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="d9d3a-132">SharePoint 콘텐츠 유형 갤러리에서 해당 모델을 기존 엔터프라이즈 콘텐츠 유형에 매핑하여 해당 스키마를 사용하려면 **고급 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="d9d3a-133">엔터프라이즈 콘텐츠 유형은 SharePoint 관리 센터의 콘텐츠 유형 허브에 저장되며 테넌트의 모든 사이트에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="d9d3a-134">기존 콘텐츠 유형을 사용하고 해당 스키마를 활용하여 식별 및 분류에 도움을 줄 수 있으나 모델이 식별하는 파일에서 정보를 추출하도록 교육해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![고급 설정](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="d9d3a-136">예제 파일 추가</span><span class="sxs-lookup"><span data-stu-id="d9d3a-136">Add your example files</span></span>

<span data-ttu-id="d9d3a-137">모델 홈페이지에서 모델을 교육하는 데 필요한 예제 파일을 추가하여 문서 유형을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="d9d3a-138">분류자와 [추출기 교육](create-an-extractor.md)에서 동일한 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="d9d3a-139">추후에 언제든지 추가하려는 옵션이 있을 수 있지만 일반적으로 전체 예제 파일 집합을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="d9d3a-140">일부 모델에 레이블을 지정하여 모델을 교육하고 레이블이 지정되지 않은 나머지 모델을 테스트하여 모델 적합성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="d9d3a-141">교육 설정의 경우 긍정 예제 및 부정 예제 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="d9d3a-142">긍정 예제: 문서 유형을 나타내는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="d9d3a-143">이러한 유형의 문서에 항상 포함되는 문자열과 정보를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="d9d3a-144">부정 예제: 분류하려는 문서를 나타내지 않는 기타 모든 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="d9d3a-145">모델을 교육하려면 5개 이상의 긍정 예제와 1개 이상의 부정 예제를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="d9d3a-146">교육 프로세스 이후 모델을 테스트하기 위해 추가 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="d9d3a-147">예제 파일을 추가하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-147">To add example files:</span></span>

1. <span data-ttu-id="d9d3a-148">모델 홈페이지의 **예제 파일 추가** 타일에서 **파일 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="d9d3a-149">**모델에 대한 예제 파일 선택** 페이지에서 콘텐츠 센터의 교육 파일 라이브러리에 있는 예제 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="d9d3a-150">아직 업로드되지 않은 경우에는 **업로드** 를 클릭하여 지금 파일 업로드를 선택하고 교육 파일 라이브러리에 해당 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="d9d3a-151">모델을 교육하는 데 사용할 예제 파일을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![예제 파일 선택](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="d9d3a-153">예제 파일 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="d9d3a-153">Label your example files</span></span>

<span data-ttu-id="d9d3a-154">예제 파일을 추가한 후에 해당 파일을 긍정 예제 또는 부정 예제 중 하나로 레이블을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="d9d3a-155">모델 홈페이지의 **파일 분류 및 교육 실행** 타일에서 **분류자 교육** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier**.</span></span>
   <span data-ttu-id="d9d3a-156">이를 통해 뷰어에 첫 번째 파일과 함께 예제 파일 목록이 표시되는 레이블 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="d9d3a-157">첫 번째 예제 파일의 맨 위에 있는 뷰어에서 파일이 사용자가 방금 만든 모델의 예제인지 묻는 텍스트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="d9d3a-158">긍정 예제인 경우 **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="d9d3a-159">부정 예제인 경우 **아니요** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="d9d3a-160">왼쪽에 있는 **레이블이 지정된 예제** 목록에서 예제로 사용하려는 추가 파일을 선택하고 해당 파일에 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![분류자 홈페이지](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="d9d3a-162">5개 이상의 긍정 예제를 레이블 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-162">Label at least five positive examples.</span></span> <span data-ttu-id="d9d3a-163">1개 이상의 부정 예제에도 레이블을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="d9d3a-164">설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-164">Create an explanation</span></span>

<span data-ttu-id="d9d3a-165">다음 단계에서는 교육 페이지에 대한 설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="d9d3a-166">설명은 모델이 문서를 인식하는 방법을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="d9d3a-167">예를 들어 계약 갱신 문서에는 항상 *추가 공개에 대한 요청* 텍스트 문자열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="d9d3a-168">추출기와 함께 사용하는 경우 설명을 통해 문서에서 추출하려는 문자열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="d9d3a-169">설명을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-169">To create an explanation:</span></span>

1. <span data-ttu-id="d9d3a-170">모델 홈페이지에서 **교육** 탭을 선택하여 교육 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="d9d3a-171">교육 페이지의 **교육된 파일** 섹션에서 이전에 레이블을 지정한 샘플 파일 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="d9d3a-172">목록에서 긍정 예제 파일 중 하나를 선택하여 뷰어에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="d9d3a-173">설명 섹션에서 **새 설명** 을 선택한 다음 **빈 항목** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="d9d3a-174">**설명 만들기** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="d9d3a-175">a.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-175">a.</span></span> <span data-ttu-id="d9d3a-176">**이름** 을 입력합니다. (예: "공개 차단")</span><span class="sxs-lookup"><span data-stu-id="d9d3a-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="d9d3a-177">b.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-177">b.</span></span> <span data-ttu-id="d9d3a-178">**유형** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-178">Select the **Type**.</span></span> <span data-ttu-id="d9d3a-179">샘플의 경우 텍스트 문자열을 추가하므로 **구 목록** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="d9d3a-180">c.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-180">c.</span></span> <span data-ttu-id="d9d3a-181">**여기에 입력** 상자에 문자열을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="d9d3a-182">샘플의 경우 "추가 공개 요청"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="d9d3a-183">문자열이 대/소문자를 구분해야 하는 경우 **대/소문자 구분** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="d9d3a-184">d.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-184">d.</span></span> <span data-ttu-id="d9d3a-185">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-185">Click **Save**.</span></span>

    ![설명 만들기](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="d9d3a-187">이제 콘텐츠 센터는 사용자가 만든 설명이 레이블이 지정된 남은 예제 파일을 긍정 예제 및 부정 예제로 올바르게 식별할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="d9d3a-188">교육된 파일 섹션에서 교육이 완료된 이후 **평가** 열을 점검하여 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="d9d3a-189">파일에는 사용자가 만든 설명이 긍정 또는 부정으로 레이블을 지정한 사항과 일치하는지 여부를 나타내는 **일치** 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![일치 값](../media/content-understanding/match.png) 

<span data-ttu-id="d9d3a-191">레이블이 지정된 파일에서 **불일치** 를 나타난 경우 모델에 문서 유형을 식별하기 위한 보다 자세한 정보를 제공하여 추가 설명을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="d9d3a-192">이 경우에는 파일을 클릭하여 불일치가 발생한 원인을 보다 자세하게 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="d9d3a-193">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="d9d3a-193">Test your model</span></span>

<span data-ttu-id="d9d3a-194">레이블이 지정된 샘플 파일에 일치가 나타난 경우 이제 해당 모델이 이전에 확인하지 못한 레이블이 지정되지 않은 남은 예제 파일에서 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="d9d3a-195">이는 선택 사항이지만, 모델을 전에 보지 못한 파일에서 테스트하여 모델 사용 전에 모델의 "적합성"이나 준비 상태를 평가하는 데 유용한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="d9d3a-196">모델 홈페이지에서 **테스트** 탭을 선택합니다. 이 경우 레이블이 지정되지 않은 샘플 파일에서 모델이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="d9d3a-197">**테스트 파일** 목록에서 예제 파일이 표시되고 모델이 해당 예제 파일을 긍정 예제로 예상하는지 부정 예제로 예상하는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="d9d3a-198">이 정보를 사용하여 문서를 식별하는 데 필요한 분류자 효율성을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d3a-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![레이블이 지정되지 않은 파일 테스트](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="d9d3a-200">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9d3a-200">See Also</span></span>
[<span data-ttu-id="d9d3a-201">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="d9d3a-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d9d3a-202">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="d9d3a-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d9d3a-203">설명 유형</span><span class="sxs-lookup"><span data-stu-id="d9d3a-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="d9d3a-204">모델 적용</span><span class="sxs-lookup"><span data-stu-id="d9d3a-204">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="d9d3a-205">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="d9d3a-205">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)

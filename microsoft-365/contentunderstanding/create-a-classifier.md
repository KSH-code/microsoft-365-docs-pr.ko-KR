---
title: 분류자 만들기 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 분류자를 만드는 방법을 설명 합니다.
ms.openlocfilehash: 718d904ca397d43644c578ff6f589b5e5b043e5a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950159"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="375c3-103">분류자 만들기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="375c3-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="375c3-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="375c3-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="375c3-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="375c3-106">분류자는 문서 형식의 식별 및 분류를 자동화 하는 모델 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="375c3-107">예를 들어 다음과 같이 문서 라이브러리에 추가 된 모든 *계약 갱신* 문서를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![계약 갱신 문서](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="375c3-109">분류자를 만들면 해당 모델과 연결 되는 새 [SharePoint 콘텐츠 형식이](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="375c3-110">분류자를 만들 때이 문서 유형에 대해 일관 되 게 예상 되는 일반적인 데이터를 확인 하 여 모델을 정의 하는 데 도움이 되는 *설명을* 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="375c3-111">문서 형식의 예 ("example files")를 사용 하 여 콘텐츠 형식이 같은 파일을 식별 하기 위해 모델을 "학습" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="375c3-112">분류자를 만들려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="375c3-113">모델 이름</span><span class="sxs-lookup"><span data-stu-id="375c3-113">Name your model</span></span>
2. <span data-ttu-id="375c3-114">예제 파일 추가</span><span class="sxs-lookup"><span data-stu-id="375c3-114">Add your example files</span></span>
3. <span data-ttu-id="375c3-115">예제 파일에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="375c3-115">Label your example files</span></span>
4. <span data-ttu-id="375c3-116">설명 만들기</span><span class="sxs-lookup"><span data-stu-id="375c3-116">Create an explanation</span></span>
5. <span data-ttu-id="375c3-117">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="375c3-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="375c3-118">모델에서 분류자를 사용 하 여 문서 형식을 식별 하 고 분류 하는 동안 모델에 의해 식별 되는 각 파일에서 특정 정보를 가져오도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="375c3-119">모델에 추가할 **추출기** 를 만들어이 작업을 수행 하면 [추출기 만들기](create-an-extractor.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="375c3-120">모델 이름</span><span class="sxs-lookup"><span data-stu-id="375c3-120">Name your model</span></span>

<span data-ttu-id="375c3-121">첫 번째 단계는 이름을 지정 하 여 콘텐츠 센터에 모델을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="375c3-122">콘텐츠 센터에서 **새로 만들기**를 클릭 한 다음 **모델 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="375c3-123">**새 문서 이해 모델** 창의 **이름** 필드에 모델의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="375c3-124">이 예에서는 계약 갱신 문서를 확인 하려는 경우이 모델 *계약 갱신*이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="375c3-125">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-125">Click **Create**.</span></span> <span data-ttu-id="375c3-126">이를 통해 모델에 대 한 홈 페이지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-126">This will create a home page for the model.</span></span></br>

    ![분류자 모델 홈 페이지](../media/content-understanding/model-home.png)

<span data-ttu-id="375c3-128">모델을 만들 때 새 SharePoint 콘텐츠 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="375c3-129">SharePoint 콘텐츠 형식은 공통 특성을 가지 며 특정 콘텐츠에 대 한 열 또는 메타 데이터 속성의 컬렉션을 공유 하는 문서 범주를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="375c3-130">SharePoint 콘텐츠 형식은 [콘텐츠 형식 갤러리]()를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="375c3-131">이 예제에서는 모델을 만들 때 새 *계약 갱신* 콘텐츠 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="375c3-132">이 모델을 SharePoint 콘텐츠 형식 갤러리의 기존 콘텐츠 형식에 매핑하려면 해당 스키마를 사용 하려면 **고급 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="375c3-133">기존 콘텐츠 형식을 사용 하 여 해당 스키마를 식별 하 고 분류 하는 데 도움이 되는 경우에도 식별 되는 파일에서 정보를 추출 하는 모델을 학습 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![고급 설정](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="375c3-135">예제 파일 추가</span><span class="sxs-lookup"><span data-stu-id="375c3-135">Add your example files</span></span>

<span data-ttu-id="375c3-136">모델 홈 페이지에서 모델을 학습 하 여 문서 형식을 식별 하는 데 필요한 예제 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="375c3-137">분류자 및 [추출기 학습](create-an-extractor.md)모두에 동일한 파일을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="375c3-138">나중에 추가 하는 옵션을 사용할 수 있지만 일반적으로는 전체 예제 파일 집합을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="375c3-139">모델에 대 한 적합성을 평가 하기 위해 레이블이 지정 되지 않은 나머지 항목을 테스트 하는 방법을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="375c3-140">교육을 위해 예제를 두 가지 방법으로 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="375c3-141">긍정적인 예: 문서 유형을 나타내는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="375c3-142">여기에는 해당 문서 유형에 서 항상 포함 되는 문자열 및 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="375c3-143">부정적 예: 문서 형식을 나타내지 않는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="375c3-144">이러한 유형의 문서에는 누락 된 문자열 및 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="375c3-145">모델을 학습 하려면 최소 5 개의 긍정 예와 하나의 네거티브 예제를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="375c3-146">훈련 후 모델을 테스트 하는 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="375c3-147">샘플 파일을 추가 하려면:</span><span class="sxs-lookup"><span data-stu-id="375c3-147">To add sample files:</span></span>

1. <span data-ttu-id="375c3-148">모델 홈 페이지의 **빌드 예제 라이브러리** 타일에서 **파일 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="375c3-149">**모델의 샘플 파일 선택** 페이지의 콘텐츠 센터에 있는 샘플 파일 라이브러리에서 예제 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="375c3-150">아직 업로드 하지 않은 경우 **업로드** 를 클릭 하 여 샘플 파일 라이브러리로 이동 하 여 업로드 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="375c3-151">모델을 학습 하는 데 사용할 예제 파일을 선택한 후 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![예제 파일 선택](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="375c3-153">예제 파일에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="375c3-153">Label your example files</span></span>

<span data-ttu-id="375c3-154">예제 파일을 추가한 후에는 양수 예제 또는 부정적 예로 레이블을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="375c3-155">모델 홈 페이지의 **파일 분류 및 교육 실행** 타일에서 **분류자 트레인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="375c3-156">이렇게 하면 첫 번째 파일이 보기에 표시 되는 예제 파일 목록을 보여 주는 레이블 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="375c3-157">Viewer의 첫 번째 예제 파일 맨 위에 파일이 방금 만든 모델의 예 인지 묻는 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="375c3-158">긍정적인 예 이면 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="375c3-159">음수 예 이면 **아니요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="375c3-160">왼쪽의 **레이블이 표시 된 예제** 목록에서 예제로 사용 하려는 추가 파일을 선택 하 고 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![분류자 모델 홈 페이지](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="375c3-162">레이블에는 5 개 이상의 양수 예제와 하나의 음수 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="375c3-163">설명 만들기</span><span class="sxs-lookup"><span data-stu-id="375c3-163">Create an explanation</span></span>

<span data-ttu-id="375c3-164">다음 단계에서는 열차 페이지에 설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="375c3-165">설명은 모델에서이 문서를 인식 하는 방법을 이해 하는 데 도움이 되는 힌트 또는 단서입니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="375c3-166">예를 들어 계약 갱신 문서에는 항상 *추가 공개 텍스트 문자열에 대 한 요청이* 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="375c3-167">추출기와 함께 사용 하는 경우 문서에서 추출 하려는 문자열을 식별 하기 위해 설명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="375c3-168">설명을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-168">To create an explanation:</span></span>

1. <span data-ttu-id="375c3-169">모델 홈 페이지에서 **학습** 탭을 클릭 하 여 열차 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="375c3-170">학습 페이지의 **숙련 된 파일** 섹션에 이전에 레이블이 지정 된 예제 파일 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="375c3-171">목록에서 양수 파일 중 하나를 선택 하면 뷰어에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="375c3-172">설명 섹션에서 **새로 만들기**를 클릭 하 고 **빈**항목을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="375c3-173">**설명 만들기** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="375c3-174">a.</span><span class="sxs-lookup"><span data-stu-id="375c3-174">a.</span></span> <span data-ttu-id="375c3-175">**이름** (예: "공개 블록")을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="375c3-176">b.</span><span class="sxs-lookup"><span data-stu-id="375c3-176">b.</span></span> <span data-ttu-id="375c3-177">**유형을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-177">Select the **Type**.</span></span> <span data-ttu-id="375c3-178">이 예제에서는 텍스트 문자열을 추가 하기 때문에 **구 목록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="375c3-179">c.</span><span class="sxs-lookup"><span data-stu-id="375c3-179">c.</span></span> <span data-ttu-id="375c3-180">여기에 **입력** 상자에 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="375c3-181">이 예에서는 "추가 공개 요청"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="375c3-182">문자열에서 대/소문자를 구분 해야 하는 경우 **대/소문자를 구분** 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="375c3-183">d.</span><span class="sxs-lookup"><span data-stu-id="375c3-183">d.</span></span> <span data-ttu-id="375c3-184">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-184">Click **Save**.</span></span>

    ![설명 만들기](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="375c3-186">이제 모델은 작성 한 설명이 더 확실 하 게 표시 되 고 나머지 레이블이 지정 된 예제 파일을 긍정적이 고 부정적 예로 정확 하 게 확인할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="375c3-187">숙련 된 파일 섹션에서 학습을 완료 한 후 **평가** 열을 확인 하 여 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="375c3-188">작성 한 설명에 대해 표시 된 것과 정확히 일치 하는 항목 (긍정 또는 부정)이 있는 경우 파일에 **일치** 값이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![설명 만들기](../media/content-understanding/match.png) 

<span data-ttu-id="375c3-190">레이블이 지정 된 파일이 **일치 하지 않는** 경우에는 추가 설명을 만들어 문서 형식을 식별 하는 데 필요한 자세한 정보를 모델에 제공 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="375c3-191">파일을 클릭 하 여 불일치가 발생 한 이유에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="375c3-192">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="375c3-192">Test your model</span></span>

<span data-ttu-id="375c3-193">레이블이 지정 된 예제 파일에서 일치 하는 항목을 받은 경우에는 레이블 없는 나머지 예제 파일에서 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="375c3-194">모델 홈 페이지에서 **테스트** 탭을 클릭 합니다.  이렇게 하면 레이블이 지정 되지 않은 예제 파일에서 모델이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="375c3-195">**테스트 파일** 목록에 예제 파일이 표시 되 고 모델이 양수 또는 음수 예제가 되도록 예측 한 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="375c3-196">이 정보를 사용 하 여 문서를 식별 하는 데 사용할 분류자의 효율성을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375c3-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![레이블이 지정 되지 않은 파일 테스트](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="375c3-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="375c3-198">See Also</span></span>
[<span data-ttu-id="375c3-199">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="375c3-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="375c3-200">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="375c3-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="375c3-201">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="375c3-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="375c3-202">모델 적용</span><span class="sxs-lookup"><span data-stu-id="375c3-202">Apply a model</span></span>](apply-a-model.md) 





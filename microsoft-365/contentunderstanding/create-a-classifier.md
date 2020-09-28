---
title: 분류자 만들기
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 분류자를 만드는 방법을 설명 합니다.
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294905"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="4326d-103">Microsoft SharePoint Syntex에서 분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="4326d-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="4326d-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="4326d-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="4326d-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="4326d-106">분류자는 문서 형식의 식별 및 분류를 자동화 하는 데 사용할 수 있는 모델 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="4326d-107">예를 들어 다음 그림에 나와 있는 것과 같이 문서 라이브러리에 추가 된 모든 *계약 갱신* 문서를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![계약 갱신 문서](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="4326d-109">분류자를 만들면 모델과 연결 될 새 [SharePoint 콘텐츠 형식을](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="4326d-110">분류자를 만들 때 모델을 정의 하는 *설명을* 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="4326d-111">이를 통해이 문서 유형을 일관 되 게 찾을 수 있는 일반적인 데이터를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="4326d-112">문서 형식의 예 ("example files")를 사용 하 여 모델을 "학습" 하 여 콘텐츠 형식이 같은 파일을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="4326d-113">분류자를 만들려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="4326d-114">모델 이름을 모델링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-114">Name your model.</span></span>
2. <span data-ttu-id="4326d-115">예제 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-115">Add your example files.</span></span>
3. <span data-ttu-id="4326d-116">예제 파일에 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-116">Label your example files.</span></span>
4. <span data-ttu-id="4326d-117">설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-117">Create an explanation.</span></span>
5. <span data-ttu-id="4326d-118">모델을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="4326d-119">모델에서 분류자를 사용 하 여 문서 형식을 식별 하 고 분류 하는 동안 모델에 의해 식별 되는 각 파일에서 특정 정보를 가져오도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="4326d-120">모델에 추가할 **추출기** 를 만들어이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="4326d-121">[추출기 만들기를](create-an-extractor.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4326d-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="4326d-122">모델 이름</span><span class="sxs-lookup"><span data-stu-id="4326d-122">Name your model</span></span>

<span data-ttu-id="4326d-123">모델을 만드는 첫 번째 단계는 이름을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="4326d-124">콘텐츠 센터에서 **새로 만들기**를 선택 하 고 **모델을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="4326d-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="4326d-125">**새 문서 이해 모델** 창의 **이름** 필드에 모델의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="4326d-126">예를 들어 계약 갱신 문서를 확인 하려면 모델 *계약 갱신*이름을 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="4326d-127">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-127">Choose **Create**.</span></span> <span data-ttu-id="4326d-128">이를 통해 모델에 대 한 홈 페이지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-128">This creates a home page for the model.</span></span></br>

    ![분류자 모델 홈 페이지](../media/content-understanding/model-home.png)

<span data-ttu-id="4326d-130">모델을 만들 때 새 SharePoint 콘텐츠 형식도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="4326d-131">SharePoint 콘텐츠 형식은 공통 특성을 가지 며 특정 콘텐츠에 대 한 열 또는 메타 데이터 속성의 컬렉션을 공유 하는 문서 범주를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="4326d-132">SharePoint 콘텐츠 형식은 [콘텐츠 형식 갤러리](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="4326d-133">이 예에서는 모델을 만들 때 새 *계약 갱신* 콘텐츠 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="4326d-134">이 모델을 SharePoint 콘텐츠 형식 갤러리의 기존 콘텐츠 형식에 매핑하려면 해당 스키마를 사용 하려면 **고급 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="4326d-135">기존 콘텐츠 형식을 사용 하 여 해당 스키마를 통해 식별 및 분류에 도움이 되는 경우에도 식별 되는 파일에서 정보를 추출 하는 모델을 학습 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![고급 설정](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="4326d-137">예제 파일 추가</span><span class="sxs-lookup"><span data-stu-id="4326d-137">Add your example files</span></span>

<span data-ttu-id="4326d-138">모델 홈 페이지에서 모델을 학습 하 여 문서 형식을 식별 하는 데 필요한 예제 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="4326d-139">분류자 및 [추출기 학습](create-an-extractor.md)에 동일한 파일을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="4326d-140">나중에 추가할 수 있지만 일반적으로는 전체 예제 파일 집합을 추가 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="4326d-141">레이블을 지정 하 여 모델을 학습 하 고, 레이블이 없는 나머지 항목을 테스트 하 여 모델 적합성을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="4326d-142">교육 집합의 경우 다음과 같은 긍정 및 부정 예를 모두 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="4326d-143">긍정적인 예: 문서 유형을 나타내는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="4326d-144">여기에는 해당 문서 유형에 서 항상 포함 되는 문자열 및 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="4326d-145">부정적 예: 문서 형식을 나타내지 않는 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="4326d-146">이러한 유형의 문서에는 누락 된 문자열 및 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="4326d-147">모델을 학습 하려면 최소한 5 개의 긍정 예와 하나 이상의 부정적 예제를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="4326d-148">교육 프로세스 후에 모델을 테스트 하기 위한 추가 작업을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="4326d-149">샘플 파일을 추가 하려면:</span><span class="sxs-lookup"><span data-stu-id="4326d-149">To add sample files:</span></span>

1. <span data-ttu-id="4326d-150">모델 홈 페이지의 **빌드 예제 라이브러리** 타일에서 **파일 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="4326d-151">**모델의 샘플 파일 선택** 페이지의 콘텐츠 센터에 있는 샘플 파일 라이브러리에서 예제 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="4326d-152">아직 업로드 하지 않은 경우 **업로드** 를 클릭 하 여 샘플 파일 라이브러리로 이동 하 여 업로드 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="4326d-153">모델을 학습 하는 데 사용할 예제 파일을 선택한 후 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![예제 파일 선택](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="4326d-155">예제 파일에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="4326d-155">Label your example files</span></span>

<span data-ttu-id="4326d-156">예제 파일을 추가한 후에는 양수 또는 음수 예제 중 하나로 레이블을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="4326d-157">모델 홈 페이지의 **파일 분류 및 교육 실행** 타일에서 **분류자 트레인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="4326d-158">이렇게 하면 첫 번째 파일이 보기에 표시 되는 예제 파일 목록을 보여 주는 레이블 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="4326d-159">첫 번째 예제 파일의 맨 위에 있는 뷰어에서 파일이 방금 만든 모델의 예 인지 묻는 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="4326d-160">긍정적인 예 이면 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="4326d-161">음수 예 이면 **아니요**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="4326d-162">왼쪽의 **레이블이 표시 된 예제** 목록에서 예제로 사용 하려는 추가 파일을 선택 하 고 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![분류자 홈 페이지](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="4326d-164">레이블에는 5 개 이상의 양수 예제와 하나의 음수 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="4326d-165">설명 만들기</span><span class="sxs-lookup"><span data-stu-id="4326d-165">Create an explanation</span></span>

<span data-ttu-id="4326d-166">다음 단계에서는 열차 페이지에 대 한 설명을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="4326d-167">설명은 모델에서 문서를 인식 하는 방법을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="4326d-168">예를 들어 계약 갱신 문서에는 *추가 공개 텍스트 문자열에 대 한 요청이* 항상 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="4326d-169">추출기와 함께 사용 하는 경우 문서에서 추출할 문자열이 설명에 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="4326d-170">설명을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-170">To create an explanation:</span></span>

1. <span data-ttu-id="4326d-171">모델 홈 페이지에서 **열차** 탭을 선택 하 여 열차 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="4326d-172">학습 페이지의 **숙련 된 파일** 섹션에 이전에 표시 한 예제 파일 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="4326d-173">목록에서 양수 파일 중 하나를 선택 하면 뷰어에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="4326d-174">설명 섹션에서 **새로 만들기** 를 선택 하 고 **비어**있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="4326d-175">**설명 만들기** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="4326d-176">a.</span><span class="sxs-lookup"><span data-stu-id="4326d-176">a.</span></span> <span data-ttu-id="4326d-177">**이름** (예: "공개 블록")을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="4326d-178">b.</span><span class="sxs-lookup"><span data-stu-id="4326d-178">b.</span></span> <span data-ttu-id="4326d-179">**유형을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-179">Select the **Type**.</span></span> <span data-ttu-id="4326d-180">예제에서 텍스트 문자열을 추가 하므로 **구 목록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="4326d-181">c.</span><span class="sxs-lookup"><span data-stu-id="4326d-181">c.</span></span> <span data-ttu-id="4326d-182">여기에 **입력** 상자에 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="4326d-183">예제를 보려면 "추가 공개 요청"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="4326d-184">문자열에서 대/소문자를 구분 해야 하는 경우 **대/소문자를 구분** 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="4326d-185">d.</span><span class="sxs-lookup"><span data-stu-id="4326d-185">d.</span></span> <span data-ttu-id="4326d-186">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-186">Click **Save**.</span></span>

    ![설명 만들기](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="4326d-188">이제 모델에서는 작성 한 설명이 긍정적이 고 부정적 예제와 같이 레이블이 지정 된 나머지 예제 파일을 정확 하 게 식별할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="4326d-189">숙련 된 파일 섹션에서 학습을 완료 한 후 **평가** 열을 확인 하 여 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="4326d-190">작성 한 설명이 양수나 음수로 표시 된 것과 일치 하기에 충분 한 경우 파일은 **match**값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Match 값](../media/content-understanding/match.png) 

<span data-ttu-id="4326d-192">레이블이 지정 된 파일이 **일치 하지 않는** 경우에는 추가 설명을 만들어 문서 형식을 식별 하는 데 필요한 자세한 정보를 모델에 제공 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="4326d-193">이 경우 파일을 클릭 하 여 불일치가 발생 한 이유에 대 한 자세한 정보를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4326d-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="4326d-194">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="4326d-194">Test your model</span></span>

<span data-ttu-id="4326d-195">레이블이 지정 된 샘플 파일에 대해 일치 하는 항목을 받은 경우에는 레이블 없는 나머지 예제 파일에서 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="4326d-196">모델 홈 페이지에서 **테스트** 탭을 선택 합니다.  이렇게 하면 레이블이 지정 되지 않은 샘플 파일에서 모델이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="4326d-197">**테스트 파일** 목록에서 예제 파일이 표시 되 고 모델에서 해당 파일을 양수나 음수로 예측 하는지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="4326d-198">이 정보를 사용 하 여 문서를 식별 하는 분류자의 유효성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4326d-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![레이블이 지정 되지 않은 파일 테스트](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="4326d-200">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4326d-200">See Also</span></span>
[<span data-ttu-id="4326d-201">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="4326d-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="4326d-202">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="4326d-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="4326d-203">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="4326d-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="4326d-204">모델 적용</span><span class="sxs-lookup"><span data-stu-id="4326d-204">Apply a model</span></span>](apply-a-model.md) 

---
title: 1단계. 사용자 SharePoint Syntex 사용하여 계약 파일을 식별하고 데이터 추출
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: 서비스 응용 SharePoint Syntex 사용하여 계약 파일을 식별하고 솔루션 솔루션을 사용하여 데이터를 추출하는 Microsoft 365 방법을 알아보십시오.
ms.openlocfilehash: c66e46aaaacd5000f1e0d18aa07df527ca8ab7dd
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054493"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="bb6dc-104">1단계.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-104">Step 1.</span></span> <span data-ttu-id="bb6dc-105">사용자 SharePoint Syntex 사용하여 계약 파일을 식별하고 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="bb6dc-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="bb6dc-106">조직에서는 받은 많은 파일에서 모든 계약 문서를 식별하고 분류하는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="bb6dc-107">또한 식별된 각 계약 파일의 여러 주요 요소(예: *클라이언트,* 계약자 및 수수료 금액)를 빠르게 볼 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bb6dc-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="bb6dc-108">이 작업을 위해 문서 이해 [모델을](index.md) SharePoint Syntex 라이브러리에 적용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="bb6dc-109">프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="bb6dc-109">Overview of the process</span></span>

<span data-ttu-id="bb6dc-110">[문서 이해는](document-understanding-overview.md) 인공 지능(AI) 모델을 사용하여 파일 분류 및 정보 추출을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="bb6dc-111">문서 이해 모델은 필요한 정보가 테이블이나 양식(예: 계약)에 포함되어 있지 않은 구조화되지 않은 문서 및 반구조적 문서에서 정보를 추출할 때도 최적의 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="bb6dc-112">먼저 식별하려는 콘텐츠 형식(계약)에 특정한 특성을 검색하기 위해 모델을 "학습"하는 데 사용할 수 있는 5개 이상의 예제 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="bb6dc-113">이 SharePoint Syntex 사용하여 새 문서 이해 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="bb6dc-114">예제 파일을 사용하여 분류자 [를 만들어야 합니다.](create-a-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="bb6dc-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="bb6dc-115">분류자에 예제 파일을 교육하여 회사 계약에서 볼 수 있는 특징을 검색하도록 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="bb6dc-116">예를 들어 서비스 계약, 계약 조건 및 보상과 같이 계약에 있는 특정 문자열을 검색하는 ["설명"을](create-a-classifier.md#create-an-explanation) *만들 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bb6dc-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="bb6dc-117">문서의 특정 섹션에서 또는 다른 문자열 옆에 있는 이러한 문자열을 검색하도록 설명을 교육할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="bb6dc-118">필요한 정보를 사용하여 분류자 교육을 했다고 생각되는 경우 예제 파일 예제 집합에서 모델을 테스트하여 효율성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="bb6dc-119">테스트 후 필요한 경우 설명을 보다 효율적으로 변경하기 위해 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="bb6dc-120">모델에서 각 계약에서 특정 데이터 조각을 끌어오는 추출기 만들기를 만들 수 있습니다. [](create-an-extractor.md)</span><span class="sxs-lookup"><span data-stu-id="bb6dc-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="bb6dc-121">예를 들어 각 계약에 대해 가장 우려되는 정보는 클라이언트의 사용자, 계약자 이름 및 총 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="bb6dc-122">모델을 성공적으로 만든 후 SharePoint [라이브러리에 적용합니다.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="bb6dc-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="bb6dc-123">문서 라이브러리에 문서를 업로드하면 문서 이해 모델이 실행되고 모델에서 정의한 계약 콘텐츠 형식과 일치하는 모든 파일을 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="bb6dc-124">계약으로 분류된 모든 파일은 사용자 지정 라이브러리 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="bb6dc-125">파일에는 추출기에서 정의한 각 계약의 값도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![문서 라이브러리의 계약](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="bb6dc-127">계약에 대한 보존 또는 보안 요구 사항이 있는 경우 모델을 [](apply-a-retention-label-to-a-model.md) 사용하여 보존 [](apply-a-sensitivity-label-to-a-model.md) 레이블 또는 민감도 레이블을 적용하여 지정된 기간 동안 계약이 삭제되지 않도록 방지하거나 계약에 액세스할 수 있는 사용자도 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-127">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="bb6dc-128">모델을 만들고 교육하는 단계</span><span class="sxs-lookup"><span data-stu-id="bb6dc-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="bb6dc-129">이러한 단계의 경우 계약 관리 솔루션 자산 리포지토리의 예제 [파일을 사용할 수 있습니다.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="bb6dc-129">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="bb6dc-130">이 리포지토리의 예제에는 문서 이해 모델 파일과 모델을 학습하는 데 사용되는 파일이 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-130">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="bb6dc-131">계약 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="bb6dc-131">Create a Contract model</span></span>

<span data-ttu-id="bb6dc-132">첫 번째 단계는 계약 모델을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="bb6dc-133">콘텐츠 센터에서 **새 모델** 을 선택한 다음 **모델 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="bb6dc-134">새 문서 **이해 모델** 창의 **이름** 필드에 모델 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="bb6dc-135">이 계약 관리 솔루션의 경우 모델 계약의 이름을 으로 할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bb6dc-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="bb6dc-136">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-136">Choose **Create**.</span></span> <span data-ttu-id="bb6dc-137">이 작업을 통해 모델에 대한 홈페이지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-137">This creates a home page for the model.</span></span></br>

    ![계약 홈 페이지의 스크린샷.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="bb6dc-139">파일 형식을 분류하기 위해 모델 교육</span><span class="sxs-lookup"><span data-stu-id="bb6dc-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="bb6dc-140">모델에 대한 예제 파일 추가</span><span class="sxs-lookup"><span data-stu-id="bb6dc-140">Add example files for your model</span></span>

<span data-ttu-id="bb6dc-141">계약 문서인 예제 파일과 계약 문서가 아닌 예제 파일(예: 작업 설명)을 5개 이상 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="bb6dc-142">모델 > **계약** 페이지의 주요 작업 예제 파일  >  추가에서 파일 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![예제 파일 추가 옵션이 강조 표시된 계약 페이지를 보여 주는 스크린샷.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="bb6dc-144">모델에 대한 예제 파일 선택 **페이지에서** 계약 폴더를 열고 사용할 파일을 선택한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="bb6dc-145">예제 파일이 없는 경우 추가하려면  업로드 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="bb6dc-146">파일에 양수 또는 음수 예제로 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="bb6dc-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="bb6dc-147">모델 > **계약 페이지의** 주요 작업 파일 분류 및 교육  >  **실행에서** **분류자 교육을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![파일 분류 및 교육 실행 옵션이 강조 표시된 계약 페이지를 보여 준 스크린샷.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="bb6dc-149">Models **> Contract > Contract 분류자** 페이지의 첫 번째 예제 파일 맨 위에 있는 뷰어에 파일이 만든 계약 모델의 예로 묻는 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="bb6dc-150">긍정 예제인 경우 **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="bb6dc-151">부정 예제인 경우 **아니요** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="bb6dc-152">왼쪽의 **레이블이 붙은** 예제 목록에서 예제로 사용할 다른 파일을 선택하고 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![분류자 홈페이지](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;bb6dc-154&quot;>분류자 교육을 위해 하나 이상의 설명 추가</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;bb6dc-155&quot;>모델 > **계약 > 분류자 페이지에서** 교육 **탭을** 선택합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;bb6dc-156&quot;>학습된 **파일 섹션에는** 이전에 레이블을 지정한 예제 파일 목록이 표시됩니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;bb6dc-157&quot;>목록에서 양수 파일 중 하나를 선택하여 보기에 표시합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;bb6dc-158&quot;>설명 **섹션에서** 새로 **고치고** 빈 을 **선택합니다.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;bb6dc-159&quot;>**설명 만들기** 페이지에서 다음을 수행합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;bb6dc-160&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;bb6dc-160&quot;>a.</span></span> <span data-ttu-id=&quot;bb6dc-161&quot;>이름 **필드에** 설명의 이름(예: &quot;계약")을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="bb6dc-162">b.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-162">b.</span></span> <span data-ttu-id="bb6dc-163">텍스트 **문자열을 추가하기 때문에 설명** 유형 필드에서 **구** 목록 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="bb6dc-164">c.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-164">c.</span></span> <span data-ttu-id="bb6dc-165">구 **목록 상자에** 문자열(예: "AGREEMENT")을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="bb6dc-166">문자열이 **대소문자** 구분을 필요로 하는 경우 대소문자 구분을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="bb6dc-167">d.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-167">d.</span></span> <span data-ttu-id="bb6dc-168">저장 **및 교육을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-168">Select **Save and train**.</span></span>

    ![설명 만들기 패널의 스크린샷.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="bb6dc-170">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="bb6dc-170">Test your model</span></span>

<span data-ttu-id="bb6dc-171">이전과는 다른 예제 파일에서 계약 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="bb6dc-172">이는 선택 사항이지만 유용한 모범 사례일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="bb6dc-173">모델 > **계약 > 분류자 페이지에서** 테스트 **탭을** 선택합니다. 이렇게 하여 모델이 사용되지 않는 예제 파일에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="bb6dc-174">테스트 **파일 목록에서** 예제 파일은 모델에서 양수 또는 음수로 예측한 파일을 표시하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="bb6dc-175">이 정보를 사용하여 문서를 식별하는 데 필요한 분류자 효율성을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![텍스트 파일 목록에 있는 표시되지 않은 파일의 스크린샷](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="bb6dc-177">완료되면 교육 **종료 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="bb6dc-178">추출기 만들기 및 교육</span><span class="sxs-lookup"><span data-stu-id="bb6dc-178">Create and train an extractor</span></span>

1. <span data-ttu-id="bb6dc-179">모델 > **계약 페이지의** 주요 작업 추출기 만들기  >  **및 교육에서** **추출기 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![추출기 만들기 및 교육 옵션이 강조 표시된 계약 페이지를 보여 주는 스크린샷.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="bb6dc-181">새 **엔터티 추출기 패널의** 새 **이름 필드에** 추출기 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="bb6dc-182">예를 들어 각 계약에서 클라이언트 이름을 추출하려는 경우 이름을 *Client로* 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="bb6dc-183">완료되면 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="bb6dc-184">추출할 엔터티에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="bb6dc-184">Label the entity you want to extract</span></span>

<span data-ttu-id="bb6dc-185">추출을 만들면 추출기 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="bb6dc-186">여기 뷰어에 표시된 목록의 첫번째 파일과 함께 샘플 파일 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Screenshot of the Client extractor Labeled examples page.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="bb6dc-188">엔터티에 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-188">To label the entity:</span></span>

1. <span data-ttu-id="bb6dc-189">뷰어에서 파일로부터 추출하려는 데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="bb6dc-190">예를 들어 클라이언트 를 추출하려면 첫 번째 파일(이 예에서는 Best *For You Organics)에서* 클라이언트 값을 강조 표시한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="bb6dc-191">레이블이 지정한 예제 목록의 레이블  열 아래에 파일에서 값이 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="bb6dc-192">자동 **저장하려면** 다음 파일을 선택하고 뷰어의 목록에서 다음 파일을 여는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="bb6dc-193">또는 **저장 을** 선택한 다음 레이블이 붙은 예제 목록에서 다른 **파일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="bb6dc-194">뷰어에서 1단계와 2단계를 반복한 다음 레이블을 모든 파일에 저장할 때까지 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="bb6dc-195">파일에 레이블을 지정하면 교육으로 이동을 알리는 알림 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="bb6dc-196">더 많은 문서에 레이블을 지정하거나 교육으로 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="bb6dc-197">설명 추가하기</span><span class="sxs-lookup"><span data-stu-id="bb6dc-197">Add an explanation</span></span>

<span data-ttu-id="bb6dc-198">엔터티 형식 자체 및 예제 파일에 있을 수 있는 변형에 대한 힌트를 제공하는 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="bb6dc-199">예를 들어 날짜 값은 다음과 같은 다양한 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="bb6dc-200">2019/10/14</span><span class="sxs-lookup"><span data-stu-id="bb6dc-200">10/14/2019</span></span>
- <span data-ttu-id="bb6dc-201">2019년 10월 14일</span><span class="sxs-lookup"><span data-stu-id="bb6dc-201">October 14, 2019</span></span>
- <span data-ttu-id="bb6dc-202">2019년 10월 14일 월요일</span><span class="sxs-lookup"><span data-stu-id="bb6dc-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="bb6dc-203">계약 시작 날짜를 식별하기 위해 *패턴* 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="bb6dc-204">설명 **섹션에서** 새로 **고치고** 빈 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="bb6dc-205">**설명 만들기** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="bb6dc-206">a.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-206">a.</span></span> <span data-ttu-id="bb6dc-207">이름 **필드에** 설명의 이름(예: 날짜)을 *입력합니다.*</span><span class="sxs-lookup"><span data-stu-id="bb6dc-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="bb6dc-208">b.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-208">b.</span></span> <span data-ttu-id="bb6dc-209">설명 유형 **필드에서** 패턴 **목록 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="bb6dc-210">c.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-210">c.</span></span> <span data-ttu-id="bb6dc-211">값 **필드에** 예제 파일에 나타나는 날짜 변형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="bb6dc-212">예를 들어 0000/00/0으로 표시되는 날짜 형식이 있는 경우 문서에 표시되는 모든 변형을 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="bb6dc-213">0000/0/0</span><span class="sxs-lookup"><span data-stu-id="bb6dc-213">0/0/0000</span></span>
    - <span data-ttu-id="bb6dc-214">0000/0/00</span><span class="sxs-lookup"><span data-stu-id="bb6dc-214">0/00/0000</span></span>
    - <span data-ttu-id="bb6dc-215">0000/00/0</span><span class="sxs-lookup"><span data-stu-id="bb6dc-215">00/0/0000</span></span>
    - <span data-ttu-id="bb6dc-216">0000/00/00</span><span class="sxs-lookup"><span data-stu-id="bb6dc-216">00/00/0000</span></span>

4. <span data-ttu-id="bb6dc-217">저장 **및 교육을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="bb6dc-218">모델 다시 테스트</span><span class="sxs-lookup"><span data-stu-id="bb6dc-218">Test your model again</span></span>

<span data-ttu-id="bb6dc-219">이전과는 다른 예제 파일에서 계약 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="bb6dc-220">이는 선택 사항이지만 유용한 모범 사례일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="bb6dc-221">모델 > **계약 > 분류자 페이지에서** 테스트 **탭을** 선택합니다. 이렇게 하여 모델이 사용되지 않는 예제 파일에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="bb6dc-222">테스트 **파일 목록에서** 예제 파일이 표시하고 모델에서 필요한 정보를 추출할 수 있는지 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="bb6dc-223">이 정보를 사용하여 문서를 식별하는 데 필요한 분류자 효율성을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="bb6dc-224">완료되면 교육 **종료 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="bb6dc-225">문서 라이브러리에 모델 적용</span><span class="sxs-lookup"><span data-stu-id="bb6dc-225">Apply your model to a document library</span></span>

<span data-ttu-id="bb6dc-226">모델을 문서 라이브러리에 SharePoint:</span><span class="sxs-lookup"><span data-stu-id="bb6dc-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="bb6dc-227">모델 > **계약** 페이지의 주요 작업 라이브러리에 모델  >  **적용에서** 모델 **적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Screenshot showing the Contracts page with Apply model to libraries option highlighted.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="bb6dc-229">계약 **추가** 패널에서 모델을 SharePoint 라이브러리가 포함된 사이트 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="bb6dc-230">사이트가 목록에 표시되지 않는 경우, 검색 상자를 사용하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="bb6dc-231">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb6dc-232">모델을 적용할 문서 라이브러리에 대한 *목록 관리* 권한 또는 *편집* 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="bb6dc-233">사이트를 선택한 후 모델을 적용할 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="bb6dc-234">모델이 콘텐츠 형식에 연결되어 있기 때문에 라이브러리에 모델을 적용하면 열로 표시하기 위해 추출한 레이블이 있는 콘텐츠 형식 및 보기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="bb6dc-235">이 보기는 기본적으로 라이브러리의 기본 보기이지만 선택적으로 고급 설정을 선택하고 이 새 보기를 기본 보기로  설정 확인란의 선택을 취소하여 기본 보기가 아니게 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="bb6dc-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="bb6dc-236">라이브러리에 모델을 적용하려면 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="bb6dc-237">모델 > **계약** 페이지의 이 모델이 있는 라이브러리 섹션에 나열된 모델 사이트의 URL이 SharePoint 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="bb6dc-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Screenshot of the Contract home page showing the Libraries with this model section.](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="bb6dc-239">라이브러리 **설정**  >  **아래에서**:</span><span class="sxs-lookup"><span data-stu-id="bb6dc-239">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="bb6dc-240">상태라는 **열을 추가하고** **선택을** 열 유형으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-240">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="bb6dc-241">검토 **중,** **승인됨** 및 **거부된 값을 적용합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb6dc-241">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="bb6dc-242">이 모델을 문서 라이브러리에 적용한 후 사이트에 문서 업로드를 시작하고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6dc-242">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="bb6dc-243">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bb6dc-243">Next step</span></span>

[<span data-ttu-id="bb6dc-244">2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="bb6dc-244">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
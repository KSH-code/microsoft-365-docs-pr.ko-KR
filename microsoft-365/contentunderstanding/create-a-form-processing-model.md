---
title: 양식 처리 모델 만들기
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntex에서 양식 처리 모델을 만듭니다.
ms.openlocfilehash: 27e80a7b3626170e45ceaa55f1269e50d8fdab9e
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337268"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="4e695-103">Microsoft SharePoint Syntex에서 양식 처리 모델을 만들기</span><span class="sxs-lookup"><span data-stu-id="4e695-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>


<span data-ttu-id="4e695-104">Microsoft PowerApps의 기능인 [AI Builder](https://docs.microsoft.com/ai-builder/overview)를 사용하여 SharePoint Syntex 사용자는 SharePoint 문서 라이브러리에서 직접 [양식 처리 모델](form-processing-overview.md)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="4e695-105">양식 처리 모델을 만드는 과정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="4e695-106">1 단계: 양식 처리 모델을 만들어 콘텐츠 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="4e695-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="4e695-107">2 단계: 예제 파일 추가 및 분석</span><span class="sxs-lookup"><span data-stu-id="4e695-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="4e695-108">3 단계: 양식 필드 선택</span><span class="sxs-lookup"><span data-stu-id="4e695-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="4e695-109">4 단계: 모델 교육 및 테스트</span><span class="sxs-lookup"><span data-stu-id="4e695-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="4e695-110">5 단계: 모델 게시</span><span class="sxs-lookup"><span data-stu-id="4e695-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="4e695-111">6 단계: 모델 사용</span><span class="sxs-lookup"><span data-stu-id="4e695-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="4e695-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e695-112">Requirements</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>


<span data-ttu-id="4e695-113">사용으로 설정된 SharePoint 문서 라이브러리에서만 양식 처리 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="4e695-114">양식 처리를 사용하는 경우, 문서 라이브러리의 **자동화** 메뉴에서 **AI Builder** **"양식 처리 모델 만들기”** 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="4e695-115">문서 라이브러리에서 프로세스를 사용하도록 설정해야 하는 경우 SharePoint 관리자에게 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![AI Builder 모델 만들기](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="4e695-117">1 단계: 양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="4e695-117">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="4e695-118">양식 처리 모델을 만드는 첫 단계는 이름을 지정하고 새 콘텐츠 유형을 정의하며 이를 위해 새 문서 라이브러리 보기를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="4e695-119">문서 라이브러리에서 **자동화** 메뉴를 선택하고 **AI Builder**를 선택한 다음, **양식 처리 모델 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![모델 만들기](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="4e695-121">**새 양식 처리 모델** 창에서 **이름** 필드에 모델 이름을 입력합니다(예: *구매 주문서*).</span><span class="sxs-lookup"><span data-stu-id="4e695-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![새 양식 처리 모델](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="4e695-123">양식 처리 모델을 만들 때 새 SharePoint 콘텐츠 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="4e695-124">SharePoint 콘텐츠 유형은 공통 특성을 가진 문서의 범주를 나타내며 해당 콘텐츠에 대한 열 또는 메타데이터 속성 모음을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="4e695-125">SharePoint 콘텐츠 유형은 [콘텐츠 형식 갤러리]()를 통해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="4e695-126">SharePoint 콘텐츠 형식 갤러리에서 이 모델을 기존 콘텐츠 형식에 매핑하여 해당 스키마를 사용하려면 **고급 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="4e695-127">모델은 추출된 데이터에 대한 문서 라이브러리에 새 보기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="4e695-128">기본 보기로 설정하지 않으려면 **보기를 기본값으로 설정**을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="4e695-129">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="4e695-130">2 단계: 문서 추가 및 분석</span><span class="sxs-lookup"><span data-stu-id="4e695-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="4e695-131">새 양식 처리 모델을 만든 후에, 브라우저가 새 PowerApps AI Builder 양식 처리 모델 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="4e695-132">이 페이지에서 예제 문서를 추가하 고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="4e695-133">사용할 예제 파일을 찾을 때는 [양식 처리 모델 입력 문서 요구 사항 및 최적화 팁](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e695-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="4e695-135">추출할 수 있는 이름 지정된 값 쌍의 확인을 위해 분석된 예제 문서 추가를 시작하려면 **문서 추가**를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="4e695-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="4e695-136">그런 다음 **로컬 저장소에서 업로드**, **SharePoint**, 또는 **Azure Blob 저장소** 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="4e695-137">교육용으로 5개 이상의 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="4e695-138">파일을 추가한 후 **분석**을 선택하여 모든 파일이 공통인 모든 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="4e695-139">완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-139">This may take several minutes to complete.</span></span></br> 
 
    ![파일 분석](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="4e695-141">파일을 분석한 후 **저장할 양식 필드를 선택** 페이지에서 감지된 필드를 볼 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![양식 필드 선택](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="4e695-143">3 단계: 양식 필드 선택</span><span class="sxs-lookup"><span data-stu-id="4e695-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="4e695-144">필드에 대한 문서를 분석한 후, 찾은 필드를 확인하고 저장할 필드를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="4e695-145">저장된 필드는 모델의 문서 라이브러리 보기에 열로 표시되고 각 문서에서 추출된 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="4e695-146">다음 페이지는 샘플 파일 중 하나를 표시하고 시스템에서 자동으로 탐지한 모든 공통 필드를 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![필드 페이지 선택](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="4e695-148">저장하려는 필드를 선택하고 확인란을 선택하여 선택 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="4e695-149">예를 들어, 구매 주문서 모델에서 *날짜*, *PO*, *전체* 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="4e695-150">원하는 경우 필드 이름을 바꾸도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![PO# 선택](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="4e695-152">필드가 분석에 의해 감지되지 않았다면, 추가하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="4e695-153">추출하려는 정보를 강조 표시하고 이름 상자에 원하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="4e695-154">그런 다음 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-154">Then select the check box.</span></span> <span data-ttu-id="4e695-155">나머지 샘플 파일에서 감지되지 않는 필드를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="4e695-156">저장하려는 필드를 선택한 후, **필드 확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![필드를 선택한 후 필드를 확인](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="4e695-158">**저장할 양식 필드를 선택** 페이지에서 선택한 필드 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="4e695-159">**완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="4e695-160">4 단계: 모델 교육 및 테스트</span><span class="sxs-lookup"><span data-stu-id="4e695-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="4e695-161">저장할 필드를 선택한 후 **모델 요약** 페이지를 통해 모델을 학습하고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="4e695-162">**모델 요약 페이지**에서 저장된 필드가 **선택한 필드** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="4e695-163">**교육**을 선택하여 예제 파일에 대한 교육을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="4e695-164">완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-164">Note that this may take a few minutes to complete.</span></span></br>

     ![필드 교육 선택](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="4e695-166">교육이 완료되었다는 알림이 표시되면 **세부 정보 페이지로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="4e695-167">**모델 세부 정보** 페이지에서 **빠른 테스트**를 선택하여 모델 작동 방식을 테스트하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="4e695-168">이렇게 페이지에 파일을 끌어서 놓으면 필드가 탐지되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![필드 확인](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="4e695-170">교육이 완료되었다는 알림이 표시되면 **세부 정보 페이지로 이동**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="4e695-171">**모델 세부 정보** 페이지에서 **빠른 테스트**를 선택하여 모델 작동 방식을 테스트하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="4e695-172">이렇게 페이지에 파일을 끌어서 놓으면 필드가 탐지되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="4e695-173">5 단계: 모델 게시</span><span class="sxs-lookup"><span data-stu-id="4e695-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="4e695-174">모델의 결과가 만족스러우면 **게시**를 선택하여 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="4e695-175">모델이 게시되면 **모델 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="4e695-176">그러면 SharePoint 문서 라이브러리에서 실행할 수 있는 PowerAutomate 흐름이 만들어지고 모델에서 식별된 필드를 추출한 다음 **흐름 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="4e695-177">작업이 완료되면 **흐름이 성공적으로 만들어졌습니다**라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="4e695-178">6 단계: 모델 사용</span><span class="sxs-lookup"><span data-stu-id="4e695-178">Step 6: Use your model</span></span>

<span data-ttu-id="4e695-179">모델을 게시하고 PowerAutomate 흐름을 만든 후, SharePoint 문서 라이브러리에서 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="4e695-180">모델을 게시한 후 **SharePoint로 이동**을 선택하여 문서 라이브러리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="4e695-181">문서 라이브러리 모델 보기에서 선택한 필드가 열로 표시된 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![적용된 문서 라이브러리 모델](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="4e695-183">**문서** 옆에 있는 정보 링크는 양식 처리 모델이 문서 라이브러리에 적용되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![정보 단추](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="4e695-185">문서 라이브러리에 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="4e695-185">Upload files to your document library.</span></span> <span data-ttu-id="4e695-186">모델이 콘텐츠 유형으로 식별하는 모든 파일은 보기에 있는 파일을 나열하고 추출한 데이터를 열에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e695-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![완료](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="4e695-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e695-188">See Also</span></span>
  
[<span data-ttu-id="4e695-189">파워 자동화 문서</span><span class="sxs-lookup"><span data-stu-id="4e695-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="4e695-190">교육: AI Builder를 사용하여 비즈니스 성과 개선</span><span class="sxs-lookup"><span data-stu-id="4e695-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)

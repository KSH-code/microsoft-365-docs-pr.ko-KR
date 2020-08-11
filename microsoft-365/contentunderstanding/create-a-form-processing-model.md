---
title: 양식 처리 모델 만들기 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex에서 양식 처리 모델을 만듭니다.
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612777"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="0ae33-103">양식 처리 모델 만들기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="0ae33-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="0ae33-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="0ae33-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="0ae33-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="0ae33-106">[AI Builder](https://docs.microsoft.com/ai-builder/overview) 사용-Microsoft PowerApps-Project Cortex 사용자의 기능은 SharePoint 문서 라이브러리에서 직접 [양식 처리 모델](form-processing-overview.md) 을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="0ae33-107">양식 처리 모델을 만들려면 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="0ae33-108">1 단계: 콘텐츠 형식을 만들기 위한 원본 프로세스 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="0ae33-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="0ae33-109">2 단계: 예제 파일 추가 및 분석</span><span class="sxs-lookup"><span data-stu-id="0ae33-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="0ae33-110">3 단계: 양식 필드 선택</span><span class="sxs-lookup"><span data-stu-id="0ae33-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="0ae33-111">4 단계: 모델 훈련 및 테스트</span><span class="sxs-lookup"><span data-stu-id="0ae33-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="0ae33-112">5 단계: 모델 게시</span><span class="sxs-lookup"><span data-stu-id="0ae33-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="0ae33-113">6 단계: 모델 사용</span><span class="sxs-lookup"><span data-stu-id="0ae33-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="0ae33-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ae33-114">Requirements</span></span>

<span data-ttu-id="0ae33-115">양식 처리 모델은 사용 하도록 설정 된 SharePoint 문서 라이브러리 에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="0ae33-116">양식 처리가 사용 하도록 설정 된 경우 문서 라이브러리의 **자동화** 메뉴 아래에 있는 **AI Builder** **"양식 처리 모델 만들기"** 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="0ae33-117">문서 라이브러리에서 사용 하도록 설정 해야 하는 경우 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ae33-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![AI 빌더 모델 만들기](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="0ae33-119">1 단계: 양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="0ae33-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="0ae33-120">양식 처리 모델을 만드는 첫 번째 단계는 새 콘텐츠 형식을 정의 하 고 해당 형식에 대 한 새 문서 라이브러리 보기를 만들기 위한 이름을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="0ae33-121">문서 라이브러리에서 **자동화** 메뉴를 선택 하 고 **AI 작성기**를 선택한 다음 **양식 처리 모델 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![AI 빌더 모델 만들기](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="0ae33-123">**새 양식 처리 모델** 창의 **이름** 필드에 모델의 이름 (예: *구매 주문*)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![새 양식 처리 모델](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="0ae33-125">양식 처리 모델을 만들 때 새 SharePoint 콘텐츠 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="0ae33-126">SharePoint 콘텐츠 형식은 공통 특성을 가지 며 특정 콘텐츠에 대 한 열 또는 메타 데이터 속성의 컬렉션을 공유 하는 문서 범주를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="0ae33-127">SharePoint 콘텐츠 형식은 [콘텐츠 형식 갤러리]()를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="0ae33-128">이 모델을 SharePoint 콘텐츠 형식 갤러리의 기존 콘텐츠 형식에 매핑하려면 해당 스키마를 사용 하려면 **고급 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="0ae33-129">모델은 문서 라이브러리에 추출 된 데이터에 대 한 새 보기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="0ae33-130">기본 보기로 설정 하지 않으려면 **보기를 기본값으로 설정을**선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="0ae33-131">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="0ae33-132">2 단계: 문서 추가 및 분석</span><span class="sxs-lookup"><span data-stu-id="0ae33-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="0ae33-133">새 양식 처리 모델을 만들면 브라우저에서 새 PowerApps AI Builder 폼 처리 모델 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="0ae33-134">이 페이지에서는 예제 문서를 추가 하 고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="0ae33-135">사용할 예제 파일을 찾는 경우 [양식 처리 모델 입력 문서 요구 사항 및 최적화 팁](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ae33-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![파워 앱 AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="0ae33-137">**문서 추가** 를 클릭 하 여 분석 된 예제 문서를 추가 하 여 추출할 수 있는 명명 된 값 쌍을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="0ae33-138">로컬 저장소, **SharePoint**또는 **Azure Blob 저장소** **에서 업로드**중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="0ae33-139">교육을 위해 적어도 5 개의 파일을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="0ae33-140">파일을 추가한 후에는 **분석** 을 선택 하 여 공통적으로 모든 파일에 해당 하는 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="0ae33-141">이 작업을 완료 하려면 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![파일 분석](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="0ae33-143">분석이 완료 되 면 **저장할 양식 필드 선택** 페이지에서 파일을 클릭 하 여 검색 된 필드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![양식 필드 선택](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="0ae33-145">3 단계: 양식 필드 선택</span><span class="sxs-lookup"><span data-stu-id="0ae33-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="0ae33-146">필드에 대 한 문서를 분석 한 후에는 검색 된 필드와 저장 하려는 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="0ae33-147">저장 된 필드는 모델의 문서 라이브러리 보기에 열로 표시 되 고 각 문서에서 추출 된 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="0ae33-148">다음 페이지에는 예제 파일 중 하나가 표시 되며, 시스템에서 자동으로 검색 된 모든 일반 필드를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![양식 필드 선택](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="0ae33-150">저장 하려는 필드를 선택 하 고 확인란을 선택 하 여 선택을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="0ae33-151">예를 들어 구매 주문 모델에서 *날짜*, *PO*및 *요약* 필드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="0ae33-152">선택한 경우 필드 이름을 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![PO 선택 #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="0ae33-154">필드가 분석을 통해 검색 되지 않은 경우에는 추가를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="0ae33-155">추출할 정보를 강조 표시 하 고 이름 상자에 지정할 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="0ae33-156">그런 다음 확인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-156">Then select the check.</span></span> <span data-ttu-id="0ae33-157">나머지 예제 파일에서 검색 되지 않은 필드를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="0ae33-158">저장할 필드를 선택한 후 **필드 확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![확인 필드](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="0ae33-160">**저장할 양식 필드 선택** 페이지에는 선택한 필드 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="0ae33-161">**완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="0ae33-162">4 단계: 모델 훈련 및 테스트</span><span class="sxs-lookup"><span data-stu-id="0ae33-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="0ae33-163">**모델 요약** 페이지에서는 저장 하려는 필드를 선택한 후 모델을 학습 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="0ae33-164">**모델 요약** 페이지의 **선택한** 필드 섹션에 저장 된 필드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="0ae33-165">예제 파일에 대 한 교육을 시작 하려면 **트레인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="0ae33-166">이 작업을 완료 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="0ae33-167">![확인 필드](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="0ae33-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="0ae33-168">교육이 완료 되었다는 알림이 표시 되 면 **세부 정보 페이지로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="0ae33-169">**모델 세부 정보** 페이지에서 **빠른 테스트**를 선택 하 여 모델이 작동 하는 방식을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="0ae33-170">이렇게 하면 파일을 페이지에 끌어서 놓고 해당 필드가 검색 되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="0ae33-171">5 단계: 모델 게시</span><span class="sxs-lookup"><span data-stu-id="0ae33-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="0ae33-172">모델의 결과가 만족 스 러 우면 **게시** 를 선택 하 여 사용 가능 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="0ae33-173">모델이 게시 된 후 **모델 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="0ae33-174">이렇게 하면 SharePoint 문서 라이브러리에서 실행 되 고 모델에서 식별 된 필드를 추출 하는 PowerAutomate 흐름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="0ae33-175">**흐름 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="0ae33-176">완료 되 면 **흐름을 성공적으로 만들었는지**확인 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="0ae33-177">6 단계: 모델 사용</span><span class="sxs-lookup"><span data-stu-id="0ae33-177">Step 6: Use your model</span></span>

<span data-ttu-id="0ae33-178">모델을 게시 하 고 PowerAutomate 흐름을 만든 후에는 SharePoint 문서 라이브러리에서 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="0ae33-179">모델을 게시 한 후 **SharePoint로 이동을** 선택 하 여 문서 라이브러리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="0ae33-180">문서 라이브러리 모델 보기에서 선택한 필드가 이제 열로 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![모델이 적용 된 문서 라이브러리](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="0ae33-182">또한 **문서** 옆의 정보 링크에는 양식 처리 모델이이 문서 라이브러리에 적용 된다는 내용이 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![풀린](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="0ae33-184">파일을 문서 라이브러리에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-184">Upload files to your document library.</span></span> <span data-ttu-id="0ae33-185">모델에서 콘텐츠 형식으로 식별 되는 모든 파일은 보기에 있는 파일을 나열 하 고 추출 된 데이터를 열에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae33-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![풀린](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="0ae33-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ae33-187">See Also</span></span>
  
[<span data-ttu-id="0ae33-188">파워 자동화 설명서</span><span class="sxs-lookup"><span data-stu-id="0ae33-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="0ae33-189">교육: AI Builder를 사용 하 여 비즈니스 성과 개선</span><span class="sxs-lookup"><span data-stu-id="0ae33-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>





---
title: 추출기 만들기
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
description: Microsoft SharePoint Syntex에서 추출기를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: e95df00c2601bccc5041f96c745048adc8dfc91f
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222794"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="370ff-103">Microsoft SharePoint Syntex에서 추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="370ff-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="370ff-104">특정 문서 유형의 식별 및 분류를 자동화하기 위해 분류자 모델을 만들기 전 또는 후에, 모델에 추출기를 추가하여 해당 문서에서 필요에 따라 특정 정보를 가져오도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="370ff-105">예를 들어, 문서 라이브러리에 추가된 모든 *계약 갱신* 문서를 식별할 뿐만 아니라 각 문서의 *서비스 시작 날짜* 를 문서 라이브러리의 열 값으로 표시하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="370ff-106">추출하려는 문서의 각 엔터티에 대해 추출기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="370ff-107">예를 들어 모델로 식별된 각각의  **계약 갱신**  문서에서  **서비스 시작 날짜** 를 추출하고자 한다고 칩시다.</span><span class="sxs-lookup"><span data-stu-id="370ff-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="370ff-108">모든  **계약 갱신**  문서의 문서 라이브러리 보기를 각 문서의 **서비스 시작** 날짜 값을 표시하는 열을 포함하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="370ff-109">추출기를 만들려면, 분류자를 학습시키기 위해 기존에 업로드했던 동일 파일을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="370ff-110">추출기 이름 짓기</span><span class="sxs-lookup"><span data-stu-id="370ff-110">Name your extractor</span></span>

1. <span data-ttu-id="370ff-111">모델 홈 페이지의 **추출기 만들기와 학습시키기** 타일에서 **추출기 학습시키기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="370ff-112">**새로운 엔터티 추출기** 화면에서 **새로운 추출기 이름** 필드에 추출기 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="370ff-113">예를 들어 각 계약 갱신 문서에서 서비스 시작 날짜를 추출하려는 경우 **서비스 시작 날짜** 를 이름으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="370ff-114">이전에 만든 열(예: 관리된 메타데이터 열)을 다시 사용하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="370ff-115">새 추출기를 만든 경우에는 **새 열 유형** 을 선택하고 **단일 텍스트 줄** 을 선택하세요. 최대 문자 제한은 255자 입니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="370ff-116">입력한 문자가 한도를 초과하는 경우 모두 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="370ff-117">모두 마쳤으면 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="370ff-118">레이블 추가</span><span class="sxs-lookup"><span data-stu-id="370ff-118">Add a label</span></span>

<span data-ttu-id="370ff-119">다음 단계는 학습 파일 예제에 추출하려는 엔터티에 레이블을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="370ff-120">추출기 만들기를 선택하면 추출기 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="370ff-121">여기 뷰어에 표시된 목록의 첫번째 파일과 함께 샘플 파일 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="370ff-122">뷰어에서 파일로부터 추출하려는 데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="370ff-123">예를 들어 *서비스 날짜 시작* 을 추출하려면 첫째 파일에서 날짜 값을 하이라이트 합니다.(*2019년 10월 14일 월요일*)</span><span class="sxs-lookup"><span data-stu-id="370ff-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="370ff-124">그 다음 **저장** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="370ff-124">and then click **Save**.</span></span>  <span data-ttu-id="370ff-125">해당 파일의 값은 레이블된 예제 목록에서 **레이블** 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="370ff-126">**다음 파일** 을 선택하여 자동 저장하고 뷰어의 목록에서 다음 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="370ff-127">또는 **저장** 을 선택한 다음 **레이블된 예제** 목록에서 다른 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="370ff-128">뷰어에서 1 단계와 2 단계를 반복하여 5개 파일 모두의 레이블을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![고급 설정](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="370ff-130">5개 파일의 레이블이 지정되면 학습으로 이동하라는 알림 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="370ff-131">더 많은 문서를 레이블 지정하거나, 다음 교육으로 넘어갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-131">You can choose to more label more documents or advance to training.</span></span> 

### <a name="use-find-to-search-your-file"></a><span data-ttu-id="370ff-132">찾기를 사용하여 파일 검색</span><span class="sxs-lookup"><span data-stu-id="370ff-132">Use Find to search your file</span></span>
<span data-ttu-id="370ff-133"><b>찾기</b> 기능을 사용하여 레이블을 지정하려는 엔터티를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-133">You can use the <b>Find</b> feature to search for an entity in your document that you want to label.</span></span>

   ![파일에서 찾기](../media/content-understanding/find-feature.png) 

<span data-ttu-id="370ff-135">찾기 기능은 큰 문서를 검색하거나 문서에 엔터티의 인스턴스가 여러 개 있는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-135">The Find feature is useful if you are searching a large document or if there are multiple instances of the entity in the document.</span></span> <span data-ttu-id="370ff-136">인스턴스가 여러 개 있는 경우, 검색 결과에 필요한 인스턴스를 선택하여 뷰어에서 해당 위치로 이동하여 레이블을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-136">If you find multiple instances, you can select the one you need in the search results to go to that location in the viewer to label it.</span></span>


## <a name="add-an-explanation"></a><span data-ttu-id="370ff-137">설명 추가하기</span><span class="sxs-lookup"><span data-stu-id="370ff-137">Add an explanation</span></span>

<span data-ttu-id="370ff-138">이 예제에서는 엔터티 서식 자체에 대한 힌트를 제공하는 설명과 샘플 문서에 포함될 수 있는 변형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-138">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="370ff-139">예를 들어 날짜 값은 다음과 같이 다양한 형식으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-139">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="370ff-140">2019/10/14</span><span class="sxs-lookup"><span data-stu-id="370ff-140">10/14/2019</span></span>
- <span data-ttu-id="370ff-141">2019년 10월 14일</span><span class="sxs-lookup"><span data-stu-id="370ff-141">October 14, 2019</span></span>
- <span data-ttu-id="370ff-142">2019년 10월 14일 월요일</span><span class="sxs-lookup"><span data-stu-id="370ff-142">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="370ff-143">*서비스 시작 날짜* 를 식별하는 데 도움이 되도록 패턴 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-143">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="370ff-144">설명 섹션에서 **신규** 를 선택한 다음 이름(예: *날짜*)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-144">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="370ff-145">입력에서 **패턴 목록** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-145">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="370ff-146">값으로 샘플 파일에 표시되는 날짜 변형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-146">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="370ff-147">예를 들어 0000/00/0으로 표시되는 날짜 형식이 있는 경우 문서에 표시되는 모든 변형을 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-147">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="370ff-148">0000/0/0</span><span class="sxs-lookup"><span data-stu-id="370ff-148">0/0/0000</span></span>
    - <span data-ttu-id="370ff-149">0000/0/00</span><span class="sxs-lookup"><span data-stu-id="370ff-149">0/00/0000</span></span>
    - <span data-ttu-id="370ff-150">0000/00/0</span><span class="sxs-lookup"><span data-stu-id="370ff-150">00/0/0000</span></span>
    - <span data-ttu-id="370ff-151">0000/00/00</span><span class="sxs-lookup"><span data-stu-id="370ff-151">00/00/0000</span></span>
4. <span data-ttu-id="370ff-152">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-152">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="370ff-153">설명 유형에 대한 자세한 내용은 [설명 유형](./explanation-types-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="370ff-153">For more learn more about explanation types, see [Explanation types](./explanation-types-overview.md).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="370ff-154">설명 라이브러리 사용하기</span><span class="sxs-lookup"><span data-stu-id="370ff-154">Use the Explanation library</span></span>

<span data-ttu-id="370ff-155">날짜와 같은 항목에 대한 설명을 만들려면 수동으로 모든 변형을 입력하기보다는 [설명 라이브러리 사용하기](./explanation-types-overview.md)가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-155">For creating explanations for items such as dates, it is easier to [use the explanation library](./explanation-types-overview.md) than to manually enter all variations.</span></span> <span data-ttu-id="370ff-156">설명 라이브러리는 미리 작성된 구 및 패턴 설명 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="370ff-157">라이브러리는 날짜, 전화 번호, 우편 번호 등과 같은 일반적인 구문 또는 패턴 목록의 모든 형식을 제공하고자 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-157">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="370ff-158">*서비스 시작 날짜* 샘플의 경우 설명 라이브러리에서 미리 작성된 *날짜* 설명을 이용하는 것이 훨씬 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="370ff-159">**설명 섹션** 에서 **신규** 를 선택한 다음 **설명 라이브러리 이용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="370ff-160">설명 라이브러리에서 **날짜** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="370ff-161">인식되는 모든 날짜 변형을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="370ff-162">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-162">Select **Add**.</span></span></br>

    ![설명 라이브러리](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="370ff-164">**설명 만들기** 페이지에서 설명 라이브러리의 *날짜* 정보가 필드에 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="370ff-165">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-165">Select **Save**.</span></span></br>

    ![날짜](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="370ff-167">모델 학습시키기</span><span class="sxs-lookup"><span data-stu-id="370ff-167">Train the model</span></span> 

<span data-ttu-id="370ff-168">설명을 저장하여 학습 시작하기</span><span class="sxs-lookup"><span data-stu-id="370ff-168">Saving your explanation start the training.</span></span> <span data-ttu-id="370ff-169">사용자의 모델에 레이블 지정된 예제 파일에서 데이터를 추출하기에 충분한 정보가 있을 경우 각 파일에 **일치** 라고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![일치](../media/content-understanding/match2.png) 

<span data-ttu-id="370ff-171">추출하려는 데이터를 찾기에 정보가 불충분할 경우 각 파일에 **불일치** 라고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="370ff-172">**불일치** 된 파일을 클릭하여 불일치된 이유에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="370ff-173">다른 설명 추가</span><span class="sxs-lookup"><span data-stu-id="370ff-173">Add another explanation</span></span>

<span data-ttu-id="370ff-174">일반적으로 불일치는 제공된 설명에 서비스 시작 날짜 값을 추출하여 레이블된 파일과 연결시키기에 충분한 정보가 없었다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="370ff-175">편집하거나 다른 설명을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="370ff-176">이 예제에서는 *서비스 날짜 시작* 텍스트 문자열이 항상 실제 값보다 우선한다는 것에 주목하세요.</span><span class="sxs-lookup"><span data-stu-id="370ff-176">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="370ff-177">서비스 시작 날짜를 식별하기 위해 구 설명을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-177">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="370ff-178">설명 섹션에서 **신규** 를 선택한 다음 이름(예: *접두사 문자열*)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="370ff-179">입력에서 **구 목록** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="370ff-180">*서비스 시작 날짜* 를 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="370ff-181">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-181">Select **Save**.</span></span>

    ![접두사 문자열](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="370ff-183">모델 다시 학습시키기</span><span class="sxs-lookup"><span data-stu-id="370ff-183">Train the model again</span></span>

<span data-ttu-id="370ff-184">설명을 저장 하면 이번에는 예제에서 두 가지 설명을 모두 사용하여 학습을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-184">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="370ff-185">사용자의 모델이 레이블된 예제 파일에서 데이터를 추출하는 데 필요한 정보를 충분히 가지고 있을 경우 각 파일에 **일치** 라고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-185">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="370ff-186">레이블이 지정된 파일에 **불일치** 가 다시 표시된 경우 문서 유형 식별을 위해 더 많은 정보를 모델에게 제공하도록 또 다른 설명을 만들거나 기존 설명을 수정하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="370ff-187">모델 테스트하기</span><span class="sxs-lookup"><span data-stu-id="370ff-187">Test your model</span></span>

<span data-ttu-id="370ff-188">레이블이 지정된 샘플 파일에 일치를 받은 경우 이제 레이블 지정되지 못한 남은 예제 파일에서 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="370ff-189">이는 선택 사항이지만, 모델을 전에 보지 못한 파일에서 테스트하여 모델 사용 전에 모델의 "적합성"이나 준비 상태를 평가하는 데 유용한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-189">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="370ff-190">모델 홈페이지에서 **테스트** 탭을 클릭합니다. 그러면 레이블이 지정되지 않은 샘플 파일에서 모델이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-190">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="370ff-191">**테스트 파일** 목록에서 해당 모델이 필요한 정보를 추출할 수 있는지 여부를 보여 주는 예제 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-191">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="370ff-192">이 정보를 사용하여 문서를 식별하는 데 필요한 분류자의 효율성을 알아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="370ff-192">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![파일에서 테스트하기](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="370ff-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="370ff-194">See Also</span></span>
[<span data-ttu-id="370ff-195">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="370ff-195">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="370ff-196">설명 유형</span><span class="sxs-lookup"><span data-stu-id="370ff-196">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="370ff-197">추출기를 만들 때 용어 저장소 분류 활용</span><span class="sxs-lookup"><span data-stu-id="370ff-197">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="370ff-198">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="370ff-198">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="370ff-199">모델 적용</span><span class="sxs-lookup"><span data-stu-id="370ff-199">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="370ff-200">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="370ff-200">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
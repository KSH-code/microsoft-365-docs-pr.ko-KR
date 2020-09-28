---
title: 추출기 만들기
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
description: Microsoft SharePoint Syntex에서 추출기를 만드는 방법을 알아봅니다.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295459"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="071f0-103">추출기 만들기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="071f0-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="071f0-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="071f0-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="071f0-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="071f0-106">특정 문서 형식의 식별 및 분류를 자동화 하기 위해 분류자 모델을 만들기 전이나 후에 추출기를 모델에 추가 하 여 이러한 문서에서 특정 정보를 가져올 수 있습니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="071f0-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="071f0-107">예를 들어 모델이 문서 라이브러리에 추가 된 모든 *계약 갱신* 문서를 식별 하는 것이 아니라 각 문서에 대 한 *서비스 시작 날짜* 를 문서 라이브러리의 열로 표시 하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="071f0-108">추출할 문서의 각 엔터티에 대해 추출기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="071f0-109">이 예제에서는 모델로 식별 된 각 *계약 갱신* 문서에 대 한 *서비스 시작 날짜* 를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="071f0-110">이 문제는 모든 *계약 갱신* 문서의 문서 라이브러리에서 각 문서에 대 한 서비스 시작 날짜 값을 표시 하는 열이 포함 된 보기를 보려는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="071f0-111">추출기를 만들기 전에 추출할 정보를 식별 하기 위해 모델을 교육 하는 데 도움이 되는 [예제 파일을 추가](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="071f0-112">분류자를 만드는 데 사용한 것과 동일한 샘플 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="071f0-113">추출기 이름</span><span class="sxs-lookup"><span data-stu-id="071f0-113">Name your extractor</span></span>

1. <span data-ttu-id="071f0-114">모델 홈 페이지의 **추출기 만들기 및 트레인** 타일에서 **추출기 양성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="071f0-115">**새 entity 추출기** 화면의 **새 추출기 이름** 필드에 추출기의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="071f0-116">예를 들어 각 계약 갱신 문서에서 서비스 시작 날짜를 추출 하려면 it **서비스 시작 날짜** 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="071f0-117">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="071f0-118">레이블 추가</span><span class="sxs-lookup"><span data-stu-id="071f0-118">Add a label</span></span>

<span data-ttu-id="071f0-119">다음 단계에서는 예제 학습 파일에서 추출할 정보에 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="071f0-120">추출기를 만들면 추출기 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="071f0-121">여기에는 보기의 첫 번째 파일을 보기에 표시 하는 예제 파일 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="071f0-122">뷰어에서 추출 하려는 데이터를 파일에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="071f0-123">예를 들어 *서비스 시작 날짜*를 추출 하려면 첫 번째 파일 (*월요일, 10 월 14 일, 2019*)의 날짜 값을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="071f0-124">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-124">and then click **Save**.</span></span>  <span data-ttu-id="071f0-125">파일의 **레이블** 열 아래 레이블이 지정 된 예제 목록에 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="071f0-126">자동으로 저장할 **다음 파일** 을 선택 하 고 보기의 목록에서 다음 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="071f0-127">또는 **저장** 을 선택한 다음 **레이블이 지정 된 예제** 목록에서 다른 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="071f0-128">뷰어에서 1 ~ 2 단계를 반복한 다음, 모든 5 개 파일에 레이블을 저장할 때까지 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![고급 설정](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="071f0-130">음수 예제 추가</span><span class="sxs-lookup"><span data-stu-id="071f0-130">Add a negative example</span></span>

<span data-ttu-id="071f0-131">분류자를 만들 때 네거티브 샘플 파일을 추가 하는 방법과 마찬가지로 추출기에 대 한 음수 샘플을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="071f0-132">"서비스 시작" 날짜 값이 포함 되지 않은 파일 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="071f0-133">**레이블이 지정 된 예제** 목록에서 음수 예제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="071f0-134">문서 맨 위의 뷰어에서 **레이블 없음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="071f0-135">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-135">Click **Save**.</span></span>
 
<span data-ttu-id="071f0-136">5 개의 파일에 레이블을 지정 하면 교육으로 이동 하 라는 알림 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="071f0-137">더 많은 문서를 선택 하거나 교육을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="071f0-138">설명 추가</span><span class="sxs-lookup"><span data-stu-id="071f0-138">Add an explanation</span></span>

<span data-ttu-id="071f0-139">이 예제에서는 엔터티 형식과 샘플 문서에 포함 될 수 있는 변형에 대 한 힌트를 제공 하는 설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="071f0-140">예를 들어 날짜 값의 형식은 다음과 같이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="071f0-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="071f0-141">10/14/2019</span></span>
- <span data-ttu-id="071f0-142">2019년 10월 14일</span><span class="sxs-lookup"><span data-stu-id="071f0-142">October 14, 2019</span></span>
- <span data-ttu-id="071f0-143">2019 년 10 월 14 일 월요일</span><span class="sxs-lookup"><span data-stu-id="071f0-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="071f0-144">*서비스 시작 날짜* 를 식별 하는 데 도움이 되도록 패턴 설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="071f0-145">설명 섹션에서 **새로 만들기** 를 선택 하 고 이름 (예: *날짜*)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="071f0-146">유형에 대해 **패턴 목록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="071f0-147">값의 경우 샘플 파일에 표시 되는 대로 날짜 변형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="071f0-148">예를 들어 날짜 형식이 0/00/0000로 나타나는 경우 문서에 표시 되는 모든 변형을 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="071f0-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="071f0-149">0/0/0000</span></span>
    - <span data-ttu-id="071f0-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="071f0-150">0/00/0000</span></span>
    - <span data-ttu-id="071f0-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="071f0-151">00/0/0000</span></span>
    - <span data-ttu-id="071f0-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="071f0-152">00/00/0000</span></span>
4. <span data-ttu-id="071f0-153">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="071f0-154">설명 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="071f0-154">Use the Explanation library</span></span>

<span data-ttu-id="071f0-155">날짜와 같은 항목에 대 한 설명을 만들려면 모든 변형을 수동으로 입력 하는 것 보다 설명 라이브러리를 사용 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="071f0-156">설명 라이브러리는 미리 작성 된 구 및 패턴 설명 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="071f0-157">라이브러리는 날짜, 전화 번호, 우편 번호 등의 일반 구 또는 패턴 목록에 대 한 모든 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="071f0-158">*서비스 시작 날짜* 샘플의 경우에는 설명 라이브러리에서 이전에 작성 한 *날짜* 에 대 한 설명을 사용 하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="071f0-159">**설명 섹션**에서 **새로 만들기**를 선택 하 고 **설명 라이브러리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="071f0-160">설명 라이브러리에서 **날짜**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="071f0-161">인식 되는 모든 날짜 변형을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="071f0-162">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-162">Select **Add**.</span></span></br>

    ![설명 라이브러리](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="071f0-164">**설명 만들기** 페이지에서 설명 라이브러리의 *날짜* 정보는 필드를 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="071f0-165">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-165">Select **Save**.</span></span></br>

    ![날짜](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="071f0-167">모델 훈련</span><span class="sxs-lookup"><span data-stu-id="071f0-167">Train the model</span></span> 

<span data-ttu-id="071f0-168">설명을 저장 하 여 교육을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-168">Saving your explanation start the training.</span></span> <span data-ttu-id="071f0-169">모델에 레이블이 지정 된 예제 파일에서 데이터를 추출 하는 데 필요한 정보가 충분 한 경우 각 파일에 **Match**라는 레이블이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="071f0-171">설명에 포함 된 정보가 부족 하 여 추출할 데이터를 찾을 수 없는 경우 각 파일의 레이블이 **일치**하지 않는 레이블로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="071f0-172">일치 하지 **않는** 파일을 클릭 하 여 일치 하지 않는 이유에 대 한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="071f0-173">다른 설명 추가</span><span class="sxs-lookup"><span data-stu-id="071f0-173">Add another explanation</span></span>

<span data-ttu-id="071f0-174">이 불일치는 제공 된 설명에서 레이블이 지정 된 파일에 맞게 서비스 시작 날짜 값을 추출 하는 데 충분 한 정보가 제공 되지 않았다는 것을 의미 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="071f0-175">이를 편집 하거나 다른 설명을 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="071f0-176">이 예제에서는 항상 실제 값 보다 우선 하는 텍스트 문자열 *의 서비스 시작 날짜* 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="071f0-177">서비스 시작 날짜를 식별 하는 데 도움이 되도록 create a 구 설명 만들기가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="071f0-178">설명 섹션에서 **새로 만들기**를 선택한 다음 이름 (예: *접두사 문자열*)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="071f0-179">유형에 대해 **구 목록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="071f0-180">*서비스 시작 날짜* 를 값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="071f0-181">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-181">Select **Save**.</span></span>

    ![접두사 문자열](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="071f0-183">모델을 다시 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-183">Train the model again</span></span>

<span data-ttu-id="071f0-184">설명을 저장 하면 이번에는 샘플의 두 가지 설명을 모두 사용 하 여 교육이 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="071f0-185">모델에 레이블이 지정 된 예제 파일에서 데이터를 추출 하는 데 필요한 정보가 충분 한 경우 각 파일에 **일치 항목이**표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="071f0-186">레이블이 지정 된 파일에서 다시 **일치 하지 않는** 경우에는 더 많은 정보를 제공 하 여 문서 유형을 식별 하거나 예제 모델을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="071f0-187">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="071f0-187">Test your model</span></span>

<span data-ttu-id="071f0-188">레이블이 지정 된 샘플 파일에서 일치 하는 항목을 확인 하는 경우에는 레이블이 설정 되지 않은 나머지 샘플 파일에서 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="071f0-189">모델 홈 페이지에서 **테스트** 탭을 클릭 합니다.  이렇게 하면 레이블이 지정 되지 않은 샘플 파일에서 모델이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="071f0-190">**테스트 파일** 목록에서 예제 파일은 모델에서 필요한 정보를 추출할 수 있는지 여부를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="071f0-191">이 정보를 사용 하 여 문서를 식별 하는 분류자의 유효성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f0-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![파일에 대해 테스트 합니다.](../media/content-understanding/test-filies-extractor.png) 

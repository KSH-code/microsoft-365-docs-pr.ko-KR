---
title: 추출기 만들기 (미리 보기)
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
description: 추출기를 만드는 방법 알아보기
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950087"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="83ed8-103">추출기 만들기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="83ed8-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="83ed8-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="83ed8-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="83ed8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="83ed8-106">특정 문서 형식의 식별 및 분류를 자동화 하기 위해 분류자 모델을 만들기 전이나 후에 추출기를 모델에 추가 하 여 이러한 문서에서 특정 정보를 가져오도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="83ed8-107">예를 들어 모델이 문서 라이브러리에 추가 된 모든 *계약 갱신* 문서를 식별 하는 것이 아니라, 각 문서에 대 한 *서비스 시작 날짜가* 문서 라이브러리의 열로 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="83ed8-108">추출할 문서의 각 엔터티에 대해 추출기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="83ed8-109">이 예제에서는 모델로 식별 된 각 *계약 갱신* 문서에 대 한 *서비스 시작 날짜* 를 추출 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="83ed8-110">각 문서에 대 한 서비스 시작 날짜 값을 표시 하는 열을 사용 하 여 모든 *계약 갱신* 문서의 문서 라이브러리에 있는 보기를 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="83ed8-111">추출기를 만들기 전에 추출할 정보를 식별 하기 위해 모델을 교육 하는 데 필요한 [예제 파일을 추가](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="83ed8-112">분류자를 만드는 데 사용한 것과 동일한 예제 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="83ed8-113">추출기 이름</span><span class="sxs-lookup"><span data-stu-id="83ed8-113">Name your extractor</span></span>

1. <span data-ttu-id="83ed8-114">모델 홈 페이지의 **추출기 만들기 및 트레인** 타일에서 **추출기 양성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="83ed8-115">**새 entity 추출기** 화면의 **새 추출기 이름** 필드에 추출기의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="83ed8-116">예를 들어 각 계약 갱신 문서에서 서비스 시작 날짜를 추출 하려는 경우 **서비스 시작 날짜** 의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="83ed8-117">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="83ed8-118">레이블 추가</span><span class="sxs-lookup"><span data-stu-id="83ed8-118">Add a label</span></span>

<span data-ttu-id="83ed8-119">다음 단계에서는 예제 트레이닝 파일에서 추출할 정보에 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="83ed8-120">추출기를 만들면 예제 파일 목록이 표시 되는 추출기 페이지가 열리고, 목록에 첫 번째 파일이 뷰어에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="83ed8-121">뷰어에서 파일에서 추출 하려는 데이터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="83ed8-122">예를 들어 *서비스 시작 날짜*를 추출 하려면 첫 번째 파일 (*월요일, 10 월 14 일, 2019*)에 해당 날짜 값을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="83ed8-123">그런 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-123">Then click **Save**.</span></span>  <span data-ttu-id="83ed8-124">**레이블** 열 아래의 레이블이 지정 된 예제 목록에 파일에 대 한 값 표시가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="83ed8-125">자동 **저장할** **다음 파일** 을 선택 하 고 viewer의 목록에서 다음 파일을 열거나, 저장을 선택 하 고 **레이블이 지정 된 예제** 목록에서 다른 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="83ed8-126">뷰어에서 1 ~ 2 단계를 반복 하 고 5 개의 파일에 레이블을 저장 하기 전까지이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![고급 설정](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="83ed8-128">음수 예제 추가</span><span class="sxs-lookup"><span data-stu-id="83ed8-128">Add a negative example</span></span>

<span data-ttu-id="83ed8-129">분류자를 만들 때 음수 예제 파일을 추가 하는 방법과 마찬가지로 추출기에 대 한 음수 예제를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="83ed8-130">이 예제에서는 서비스 시작 날짜 값이 포함 되지 않은 파일 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="83ed8-131">**레이블이 지정 된 예제** 목록에서 음수 예제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="83ed8-132">뷰어에서 문서 맨 위에 있는 **레이블 없음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="83ed8-133">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-133">Click **Save**.</span></span>
 
<span data-ttu-id="83ed8-134">5 개의 파일에 레이블을 지정 하면 교육으로 이동 하 라는 알림 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="83ed8-135">더 많은 문서를 선택 하거나 교육을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="83ed8-136">설명 추가</span><span class="sxs-lookup"><span data-stu-id="83ed8-136">Add an explanation</span></span>

<span data-ttu-id="83ed8-137">이 예제에서는 엔터티 형식과 예제 문서에 있는 변형에 대 한 힌트를 제공 하는 설명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="83ed8-138">예를 들어 날짜 값의 형식은 다음과 같이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="83ed8-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="83ed8-139">10/14/2019</span></span>
- <span data-ttu-id="83ed8-140">2019년 10월 14일</span><span class="sxs-lookup"><span data-stu-id="83ed8-140">October 14, 2019</span></span>
- <span data-ttu-id="83ed8-141">2019 년 10 월 14 일 월요일</span><span class="sxs-lookup"><span data-stu-id="83ed8-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="83ed8-142">*서비스 시작 날짜* 를 식별 하는 데 도움이 되도록 패턴 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="83ed8-143">설명 섹션에서 **새로 만들기**를 선택 하 고 이름 (예: *날짜*)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="83ed8-144">유형에 대해 **패턴 목록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="83ed8-145">값의 경우에는 샘플 파일에 표시 되는 대로 날짜 변형을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="83ed8-146">예를 들어 날짜 형식이 0/00/0000로 나타나는 경우 문서에 나타날 수 있는 모든 변형을 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="83ed8-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="83ed8-147">0/0/0000</span></span>
    - <span data-ttu-id="83ed8-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="83ed8-148">0/00/0000</span></span>
    - <span data-ttu-id="83ed8-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="83ed8-149">00/0/0000</span></span>
    - <span data-ttu-id="83ed8-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="83ed8-150">00/00/0000</span></span>
4. <span data-ttu-id="83ed8-151">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="83ed8-152">설명 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="83ed8-152">Use the Explanation library</span></span>

<span data-ttu-id="83ed8-153">날짜와 같은 작업에 대 한 설명을 만들려면 모든 변형을 수동으로 입력 하는 것 보다 설명 라이브러리를 사용 하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="83ed8-154">설명 라이브러리는 미리 작성 된 구 및 패턴 설명 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="83ed8-155">라이브러리는 날짜, 전화 번호, 우편 번호 등의 일반 구 또는 패턴 목록에 대 한 모든 형식을 제공 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="83ed8-156">*서비스 시작 날짜* 예제를 보려면 설명 라이브러리에서 이전에 작성 한 *날짜* 에 대 한 설명을 사용 하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="83ed8-157">**설명 섹션**에서 \* \* **새로 만들기**를 선택 하 고 **설명 라이브러리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="83ed8-158">설명 라이브러리에서 **날짜**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="83ed8-159">인식 되는 모든 날짜 변형을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="83ed8-160">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-160">Select **Add**.</span></span></br>

    ![설명 라이브러리](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="83ed8-162">**설명 만들기** 페이지에서 설명 라이브러리의 *날짜* 정보는 필드를 자동으로 다시 채움 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="83ed8-163">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-163">Select **Save**.</span></span></br>

    ![설명 라이브러리](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="83ed8-165">모델 훈련</span><span class="sxs-lookup"><span data-stu-id="83ed8-165">Train the model</span></span> 

<span data-ttu-id="83ed8-166">설명을 저장 하면 교육을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="83ed8-167">모델에 레이블이 지정 된 예제 파일에서 데이터를 추출 하는 데 필요한 정보가 충분 한 경우 각 파일에 **Match**라는 레이블이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![설명 라이브러리](../media/content-understanding/match2.png) 

<span data-ttu-id="83ed8-169">설명에 포함 된 정보가 부족 하 여 추출할 데이터를 찾을 수 없는 경우 각 파일의 레이블이 **일치**하지 않는 레이블로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="83ed8-170">일치 하지 않는 파일을 클릭 하 여 일치 하지 않는 이유에 대 한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="83ed8-171">다른 설명 추가</span><span class="sxs-lookup"><span data-stu-id="83ed8-171">Add another explanation</span></span>

<span data-ttu-id="83ed8-172">이 불일치는 제공 된 설명에서 레이블이 지정 된 파일에 맞게 서비스 시작 날짜 값을 추출 하는 데 충분 한 정보가 제공 되지 않았다는 것을 의미 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="83ed8-173">이를 편집 하거나 다른 설명을 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="83ed8-174">이 예에서 텍스트 문자열은 항상 실제 값 보다 우선 하 여 *서비스 날짜를 시작* 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="83ed8-175">서비스 시작 날짜를 식별 하는 데 도움이 되도록 구문 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="83ed8-176">설명 섹션에서 **새로 만들기**를 선택한 다음 이름 (예: *접두사 문자열*)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="83ed8-177">유형에 대해 **구 목록을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="83ed8-178">*서비스 시작 날짜* 를 값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="83ed8-179">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-179">Select **Save**.</span></span>

    ![설명 라이브러리](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="83ed8-181">모델 훈련</span><span class="sxs-lookup"><span data-stu-id="83ed8-181">Train the model</span></span>

<span data-ttu-id="83ed8-182">설명을 저장 하면이 예제에서 두 가지 설명을 모두 사용 하 여 교육이 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="83ed8-183">모델에 레이블이 지정 된 예제 파일에서 데이터를 추출 하는 데 필요한 정보가 충분 한 경우 각 파일에 **Match**라는 레이블이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="83ed8-184">레이블이 지정 된 파일에서 다시 **일치 하지 않는** 경우에는 더 많은 정보를 제공 하 여 문서 유형을 식별 하거나 기존 항목을 변경 하는 방법을 확인 하는 또 다른 설명을 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="83ed8-185">모델 테스트</span><span class="sxs-lookup"><span data-stu-id="83ed8-185">Test your model</span></span>

<span data-ttu-id="83ed8-186">레이블이 지정 된 예제 파일에서 일치 하는 항목을 받은 경우에는 레이블 없는 나머지 예제 파일에서 모델을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="83ed8-187">모델 홈 페이지에서 **테스트** 탭을 클릭 합니다.  이렇게 하면 레이블이 지정 되지 않은 예제 파일에서 모델이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="83ed8-188">**테스트 파일** 목록에 예제 파일이 표시 되 고 모델에서 필요한 정보를 추출할 수 있는지 여부를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="83ed8-189">이 정보를 사용 하 여 문서를 식별 하는 데 사용할 분류자의 효율성을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ed8-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![파일에 대해 테스트 합니다.](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="83ed8-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83ed8-191">See Also</span></span>
  





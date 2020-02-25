---
title: Trainable 분류자 만들기 (미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 기본 제공 분류자 중 하나가 사용자의 요구 사항을 충족 하지 않는 경우 trainable 분류자를 사용 합니다. Microsoft 365 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다. 이 항목에서는 사용자 지정 분류자를 만드는 방법을 보여 줍니다.
ms.openlocfilehash: 31fb4374290bcf92a5c68bc4e7531e9472622b0b
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266897"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="227fd-105">Trainable 분류자 만들기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="227fd-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="227fd-106">상자 분류자 중 하나가 사용자의 요구 사항을 충족 하지 않는 경우 trainable 분류자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="227fd-107">Microsoft 365 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="227fd-108">교육 분류자는 먼저 사용자가 선택한 것 이며 범주와 정확히 일치 하는 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="227fd-109">그런 다음 처리 된 것으로, 긍정적이 고 부정적 샘플을 함께 제공 하 여 예측을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="227fd-110">서로 다른 종류의 분류자에 대 한 자세한 내용은 [trainable 분류자 시작 (미리 보기)](classifier-getting-started-with.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="227fd-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="227fd-111">이 타임 라인은 예제 배포를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-111">This timeline reflects a sample deployment.</span></span>

![trainable-분류자-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="227fd-113">Trainable 분류자에 대해 처음으로 옵트인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-113">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="227fd-114">Microsoft 365에서 조직의 콘텐츠를 기준으로 평가 하는 데 12 일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-114">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="227fd-115">전역 관리자에 게 연락 하 여 옵트인 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-115">Contact your global administrator to kick off the opt-in process.</span></span>

## <a name="seed-content"></a><span data-ttu-id="227fd-116">콘텐츠 시드</span><span class="sxs-lookup"><span data-stu-id="227fd-116">Seed content</span></span>

<span data-ttu-id="227fd-117">Trainable 분류자가 특정 콘텐츠 범주에 있는 항목을 독립적으로 식별 하도록 하려면 먼저 범주에 포함 된 콘텐츠 형식의 여러 샘플을 사용 하 여이를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-117">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="227fd-118">이러한 trainable 분류자에 대 한 샘플 공급을 *시드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-118">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="227fd-119">시드 콘텐츠는 사용자가 선택 하 고 콘텐츠 범주를 나타내도록 판단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-119">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="227fd-120">최소 50의 양수 500 샘플을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-120">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="227fd-121">Trainable 분류자는 가장 최근에 생성 500 된 샘플 (파일을 만든 날짜/시간 스탬프)까지 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-121">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="227fd-122">제공 하는 샘플이 많을 수록 분류자가 더 정확 하 게 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-122">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="227fd-123">콘텐츠 테스트</span><span class="sxs-lookup"><span data-stu-id="227fd-123">Testing content</span></span>

<span data-ttu-id="227fd-124">Trainable 분류자가 예측 모델을 작성 하기에 충분 한 긍정적인 샘플을 처리 한 후에는 해당 분류자가 해당 범주 및 항목과 일치 하는 항목을 올바르게 구분할 수 있는지 여부를 확인 하는 예측을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-124">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="227fd-125">이 작업을 수행 하면 범주 및 샘플에 포함 되는 샘플로 구성 된 사용자가 선택한 콘텐츠 집합을 다른 사람에 게 공급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-125">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="227fd-126">이러한 프로세스를 처리 하면 수동으로 결과를 확인 하 여 각 예측이 올바른지, 부정확 한지 또는 확실 하지 않을 지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-126">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="227fd-127">Trainable 분류자는이 피드백을 사용 하 여 예측 모델을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-127">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="227fd-128">최상의 결과를 위해서는 테스트 샘플 집합에 1만 항목에 긍정 및 음의 일치를 고르게 분산 하 여 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-128">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="227fd-129">Trainable 분류자를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="227fd-129">How to create a trainable classifier</span></span>

1. <span data-ttu-id="227fd-130">50-500 seed 콘텐츠 항목을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-130">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="227fd-131">이러한 샘플은 trainable 분류자가 분류 범주에서 진행 되는 것 처럼 식별 하려는 콘텐츠 유형을 강력 하 게 나타내는 예제 일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-131">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="227fd-132">지원 되는 파일 형식에 대해서는 [기본 크롤링 파일 이름 확장명 및 구문 분석 된 파일 형식 SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="227fd-132">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="227fd-133">Seed 및 test 샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-133">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="227fd-134">시드 집합의 항목이 범주의 **강력한** 예 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-134">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="227fd-135">Trainable 분류자는 초기 시드를 기반으로 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-135">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="227fd-136">이 분류자는 모든 시드 샘플을 강력 하 게 가정 하며, 샘플이 해당 범주와 가장 약한 지 또는 음의 일치 인지를 알 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-136">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="227fd-137">Seed 콘텐츠만 보관 전용으로 설정 된 시드 콘텐츠를 SharePoint Online 폴더에 배치 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="227fd-137">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="227fd-138">사이트, 라이브러리 및 폴더 URL을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-138">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="227fd-139">시드 데이터에 대 한 새 사이트 및 폴더를 만드는 경우 해당 위치에 대해 최소 1 시간 이상 해당 시드 데이터를 사용 하는 trainable 분류자를 만들기 전에이를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-139">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="227fd-140">준수 관리자 또는 보안 관리자 역할 액세스를 사용 하 여 microsoft 365 준수 센터에 로그인 하 고 **microsoft 365 준수 센터** 또는 **microsoft 365 보안 센터** > **데이터 분류** 열기</span><span class="sxs-lookup"><span data-stu-id="227fd-140">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="227fd-141">**Trainable 분류자** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-141">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="227fd-142">**Trainable 분류자 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-142">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="227fd-143">이 trainable 분류자가 식별 하 `Name`는 데 `Description` 사용할 항목의 범주에 적절 한 값과 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-143">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="227fd-144">2 단계의 정확한 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 시드 콘텐츠 사이트에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-144">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="227fd-145">을 `Add`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-145">Choose `Add`.</span></span>

8. <span data-ttu-id="227fd-146">설정을 검토 하 고를 `Create trainable classifier`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-146">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="227fd-147">24 시간 이내에 trainable 분류자는 시드 데이터를 처리 하 고 예측 모델을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-147">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="227fd-148">분류자 상태는 시드 `In progress` 데이터를 처리 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-148">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="227fd-149">분류자가 시드 데이터 처리를 마치면 상태가로 `Need test items`변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-149">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="227fd-150">이제 분류자를 선택 하 여 세부 정보 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-150">You can now view the details page by choosing the classifier.</span></span>


![trainable 분류자에서 테스트할 준비가 되었습니다.](../media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="227fd-152">테스트 콘텐츠 항목을 200 개 이상 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-152">Collect at least 200 test content items.</span></span> <span data-ttu-id="227fd-153">최상의 결과를 위해 1만을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-153">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="227fd-154">이러한 항목은 강력한 포지티브, 강력한 네거티브 및 해당 특성을 약간 명확 하 게 나타내는 항목과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-154">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="227fd-155">지원 되는 파일 형식에 대해서는 [기본 크롤링 파일 이름 확장명 및 구문 분석 된 파일 형식 SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="227fd-155">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="227fd-156">샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-156">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="227fd-157">테스트 *콘텐츠만*보류 전용으로 설정 된 테스트 콘텐츠를 SharePoint Online 폴더에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-157">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="227fd-158">SharePoint Online 사이트, 라이브러리 및 폴더 URL을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-158">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="227fd-159">테스트 데이터에 대 한 새 사이트와 폴더를 만드는 경우 해당 위치에 대해 최소 1 시간 이상 해당 시드 데이터를 사용 하는 trainable 분류자를 만들기 전에이를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-159">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="227fd-160">을 `Add items to test`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-160">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="227fd-161">12 단계에서 테스트 콘텐츠 사이트에 대 한 정확한 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-161">Enter the exact SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="227fd-162">을 `Add`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-162">Choose `Add`.</span></span>

15. <span data-ttu-id="227fd-163">을 선택 `Done`하 여 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-163">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="227fd-164">Trainable 분류자는 테스트 파일을 처리 하는 데 최대 1 시간까지 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-164">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="227fd-165">Trainable 분류자가 테스트 파일의 처리를 마치면 세부 정보 페이지의 상태가로 `Ready to review`변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-165">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="227fd-166">테스트 샘플 크기 `Add items to test` 를 증가 시켜야 하는 경우에는 trainable 분류자가 추가 항목을 처리 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-166">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![스크린샷 검토 준비 완료](../media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="227fd-168">항목 `Tested items to review` 을 검토 하려면 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-168">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="227fd-169">Microsoft 365는 한 번에 30 개의 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-169">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="227fd-170">이러한 항목을 검토 하 `We predict this item is "Relevant". Do you agree?` 고 상자에서 `Yes` 또는 `No` 또는 `Not sure, skip to next item`를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-170">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="227fd-171">모델 정확도는 30 개 항목 마다 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-171">Model accuracy is automatically updated after every 30 items.</span></span>

![검토 항목 상자](../media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="227fd-173">*최소* 200 항목을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-173">Review *at least* 200 items.</span></span>

<!-- insert Analyze steps here-->

20. <span data-ttu-id="227fd-174">정확도가 최소 70%이 고 `Publish the classifier` 상태가 인지 `Ready to use`때까지 계속 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-174">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![정확성과 게시할 준비가 완료 되었습니다.](../media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="227fd-176">분류자를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-176">Publish the classifier.</span></span>

22. <span data-ttu-id="227fd-177">게시 된 분류자는 조건 및 [통신 준수](communication-compliance.md)를 [기반으로 하는 자동 적용 보존 레이블 정책의](labels.md#applying-a-retention-label-automatically-based-on-conditions) 조건으로 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-177">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="227fd-178">일단 분류자가 게시 되 면 추가 교육을 받을 수 없으므로 가능한 한 많은 항목을 테스트 하 고 검토 하 여 정확성을 최대한 높게 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227fd-178">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="227fd-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="227fd-179">See also</span></span>

- [<span data-ttu-id="227fd-180">학습 가능한 분류자 시작 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="227fd-180">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="227fd-181">SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식</span><span class="sxs-lookup"><span data-stu-id="227fd-181">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

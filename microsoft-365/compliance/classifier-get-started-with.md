---
title: 학습 가능한 분류자 시작
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 분류자 는 다양한 유형의 콘텐츠를 인식할 수 있는 도구로, 샘플을 제공하면 됩니다. 이 문서에서는 사용자 지정 분류기를 만들고 교육하는 방법과 정확도를 높이기 위해 분류기를 다시 학습하는 방법을 보여집니다.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918182"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="6b12b-104">학습 가능한 분류자 시작</span><span class="sxs-lookup"><span data-stu-id="6b12b-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="6b12b-105">교육 가능한 Microsoft 365 분류자 는 살펴보기 위한 샘플을 제공하여 다양한 유형의 콘텐츠를 인식할 수 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6b12b-106">교육이 이행된 후 이를 사용하여 Office 민감도 레이블, 커뮤니케이션 규정 준수 정책 및 보존 레이블 정책을 적용하기 위한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6b12b-107">학습 가능한 사용자 지정 분류자 만들기는 먼저 사람이 선택하고 해당 범주와 긍정적인 일치인 샘플을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="6b12b-108">그런 다음 분류자에 양수 및 음의 샘플을 혼합하여 예측할 수 있는 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="6b12b-109">이 문서에서는 사용자 지정 분류기를 만들고 교육하는 방법과 재 교육을 통해 수명 동안 사용자 지정 학습 가능한 분류자 및 사전 학습된 분류자 성능을 개선하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="6b12b-110">다양한 분류자 유형에 대한 자세한 내용은 학습 가능한 분류자에 대해 자세히 [알아보기를 참조합니다.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="6b12b-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="6b12b-111">학습 가능한 분류자 만들기에 대한 간단한 요약은 이 비디오를 시청해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="6b12b-112">자세한 내용을 확인하려면 이 전체 문서를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="6b12b-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6b12b-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="6b12b-114">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b12b-114">Licensing requirements</span></span>

<span data-ttu-id="6b12b-115">분류자 는 Microsoft 365 E5 또는 E5 규정 준수 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="6b12b-116">이러한 구독을 사용하려면 이러한 구독 중 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="6b12b-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6b12b-117">Permissions</span></span>

<span data-ttu-id="6b12b-118">UI에서 분류자에 액세스하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6b12b-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="6b12b-119">전역 관리자는 테넌트에 대해 옵트인(opt in)하여 사용자 지정 분류자 만들기를 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="6b12b-120">분류자 교육을 위해서는 준수 관리자 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="6b12b-121">이러한 시나리오에서 분류기를 사용하려면 다음 권한이 있는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6b12b-122">보존 레이블 정책 시나리오: 레코드 관리 및 보존 관리 역할</span><span class="sxs-lookup"><span data-stu-id="6b12b-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="6b12b-123">민감도 레이블 정책 시나리오: 보안 관리자, 준수 관리자, 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="6b12b-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="6b12b-124">커뮤니케이션 규정 준수 정책 시나리오: 내부자 위험 관리 관리자, 관리 검토 관리자</span><span class="sxs-lookup"><span data-stu-id="6b12b-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6b12b-125">기본적으로 사용자 지정 분류자를 만든 사용자만 해당 분류자에 의해 예측을 학습하고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="6b12b-126">학습 가능한 사용자 지정 분류자 준비</span><span class="sxs-lookup"><span data-stu-id="6b12b-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="6b12b-127">학습 가능한 사용자 지정 분류자 만들기와 관련된 것을 이해하면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="6b12b-128">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="6b12b-128">Timeline</span></span>

<span data-ttu-id="6b12b-129">이 타임라인은 학습 가능한 분류자 샘플 배포를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="6b12b-131">학습 가능한 분류자에 대해 옵트인(opt in)이 처음 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="6b12b-132">Microsoft 365에서 조직 콘텐츠에 대한 기준 평가를 완료하는 데 12일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="6b12b-133">전역 관리자에게 문의하여 옵트인 프로세스를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b12b-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="6b12b-134">전체 워크플로</span><span class="sxs-lookup"><span data-stu-id="6b12b-134">Overall workflow</span></span>

<span data-ttu-id="6b12b-135">사용자 지정 학습 가능한 분류자 만들기의 전체 워크플로에 대한 자세한 내용은 고객 교육 가능한 분류자 만들기를 위한 프로세스 흐름을 [참조하세요.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="6b12b-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="6b12b-136">시드 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6b12b-136">Seed content</span></span>

<span data-ttu-id="6b12b-137">학습 가능한 분류자를 통해 항목을 특정 콘텐츠 범주에 속하는 것으로 독립적으로 정확하게 식별하려는 경우 먼저 범주에 있는 콘텐츠 유형의 많은 샘플을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="6b12b-138">학습 가능한 분류자에 샘플을 공급하는 이를 시드라고 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="6b12b-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="6b12b-139">시드 콘텐츠는 사람이 선택하며 콘텐츠 범주를 나타내는 것으로 판단됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="6b12b-140">50개 이상의 양수 샘플과 500개가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="6b12b-141">학습 가능한 분류자는 가장 최근에 만든 500개의 샘플(파일에서 만든 날짜/타임스탬프)을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="6b12b-142">샘플을 더 많이 제공할수록 분류자는 예측의 정확도를 더 정확하게 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="6b12b-143">콘텐츠 테스트</span><span class="sxs-lookup"><span data-stu-id="6b12b-143">Testing content</span></span>

<span data-ttu-id="6b12b-144">학습 가능한 분류자에서 예측 모델을 빌드하기에 충분한 양의 샘플을 처리한 후 분류자에서 범주와 일치하지 않는 항목을 올바르게 구분할 수 있는지 테스트하는 예측을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="6b12b-145">범주에 속해야 하는 샘플과 해당되지 않는 샘플로 구성된 사람이 선택한 다른 콘텐츠 집합을 선택하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="6b12b-146">처음 제공한 초기 시드 데이터와 다른 데이터로 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="6b12b-147">이러한 결과를 처리하고 나면 수동으로 결과를 진행하여 각 예측이 올바르거나, 올바르지 않거나, 확실하지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="6b12b-148">학습 가능한 분류기는 이 피드백을 사용하여 예측 모델을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="6b12b-149">최상의 결과를 얻기 위해 테스트 샘플 집합에 200개 이상의 항목이 있으며 양수 및 음수 일치 항목이 고수로 분포되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="6b12b-150">학습 가능한 분류자 만들기 방법</span><span class="sxs-lookup"><span data-stu-id="6b12b-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="6b12b-151">50-500개 사이의 시드 콘텐츠 항목을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="6b12b-152">이러한 샘플은 학습 가능한 분류자에서 분류 범주에 속하는 것으로 긍정적으로 식별하려는 콘텐츠 유형을 강력하게 나타내는 샘플만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="6b12b-153">지원되는 파일 형식에 대한 자세한 내용은 [SharePoint Server의](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 크롤링되는 기본 파일 이름 확장명 및 구문 분석된 파일 형식을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6b12b-154">시드 및 테스트 샘플 항목은 암호화되지 말고 영어로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6b12b-155">시드 집합의 항목이 범주의  강력한 예가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="6b12b-156">학습 가능한 분류기는 처음에 시드한 모델을 기반으로 모델을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="6b12b-157">분류기는 모든 시드 샘플이 강력한 양수로 가정하며, 샘플이 범주에 약한지 또는 음수와 일치하는지 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="6b12b-158">시드 콘텐츠만 보유하는 전용 SharePoint Online 폴더에 시드 *콘텐츠를 배치합니다.*</span><span class="sxs-lookup"><span data-stu-id="6b12b-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="6b12b-159">사이트, 라이브러리 및 폴더 URL을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="6b12b-160">시드 데이터에 대한 새 사이트 및 폴더를 만드는 경우 해당 시드 데이터를 사용할 학습 가능한 분류기를 만들기 전에 해당 위치가 인덱싱될 수 있도록 적어도 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="6b12b-161">규정 준수 관리자 또는 보안 관리자 역할 액세스로 Microsoft 365 규정 준수 센터에 로그인하고 **Microsoft 365** 규정 준수 센터 또는 Microsoft **365** 보안 센터 데이터 분류를  >  하세요.</span><span class="sxs-lookup"><span data-stu-id="6b12b-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="6b12b-162">학습 가능한 **분류자 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="6b12b-163">학습 **가능한 분류자 만들기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6b12b-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="6b12b-164">학습 가능한 분류자를 식별할 항목 범주의 및 필드에 적절한 값을 `Name` `Description` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="6b12b-165">2단계에서 시드 콘텐츠 사이트의 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="6b12b-166">를 `Add` 선택.</span><span class="sxs-lookup"><span data-stu-id="6b12b-166">Choose `Add`.</span></span>

8. <span data-ttu-id="6b12b-167">설정을 검토하고 `Create trainable classifier` 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="6b12b-168">교육 가능한 분류자는 24시간 이내에 시드 데이터를 처리하고 예측 모델을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="6b12b-169">분류자 상태는 `In progress` 시드 데이터를 처리하는 동안입니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="6b12b-170">분류자에서 시드 데이터 처리를 마치면 상태가 로 `Need test items` 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="6b12b-171">이제 분류자 를 선택하여 세부 정보 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b12b-172">![교육 가능한 분류자 테스트 준비](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6b12b-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="6b12b-173">최상의 결과를 얻으 위해 테스트 콘텐츠 항목을 200개 이상(최대 10,000개) 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="6b12b-174">이러한 항목은 강한 양성, 강력한 부정 및 특성상 약간 명확하지 않다는 항목이 혼합된 것이 틀려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="6b12b-175">지원되는 파일 형식에 대한 자세한 내용은 [SharePoint Server의](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 크롤링되는 기본 파일 이름 확장명 및 구문 분석된 파일 형식을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6b12b-176">샘플 항목은 암호화되지 말고 영어로 번역해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="6b12b-177">테스트 콘텐츠만 보유하는 전용 SharePoint Online 폴더에 테스트 *콘텐츠를 배치합니다.*</span><span class="sxs-lookup"><span data-stu-id="6b12b-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="6b12b-178">SharePoint Online 사이트, 라이브러리 및 폴더 URL을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="6b12b-179">테스트 데이터에 대한 새 사이트 및 폴더를 만드는 경우 해당 시드 데이터를 사용할 학습 가능한 분류기를 만들기 전에 해당 위치가 인덱싱될 수 있도록 적어도 1시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="6b12b-180">를 `Add items to test` 선택.</span><span class="sxs-lookup"><span data-stu-id="6b12b-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="6b12b-181">12단계에서 테스트 콘텐츠 사이트의 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="6b12b-182">를 `Add` 선택.</span><span class="sxs-lookup"><span data-stu-id="6b12b-182">Choose `Add`.</span></span>

15. <span data-ttu-id="6b12b-183">를 선택하여 마법사를 `Done` 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="6b12b-184">학습 가능한 분류자는 테스트 파일을 처리하는 데 최대 1시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="6b12b-185">학습 가능한 분류자에서 테스트 파일 처리를 완료하면 세부 정보 페이지의 상태가 로 `Ready to review` 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="6b12b-186">테스트 샘플 크기를 늘리기 위해 학습 가능한 분류기를 선택하고 추가 항목을 `Add items to test` 처리하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b12b-187">![스크린샷을 검토할 준비가 완료되었습니다.](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6b12b-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="6b12b-188">항목을 `Tested items to review` 검토할 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="6b12b-189">Microsoft 365는 한에 30개 항목을 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="6b12b-190">검토하고 상자에서 또는 `We predict this item is "Relevant". Do you agree?` 를 `Yes` `No` `Not sure, skip to next item` 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="6b12b-191">모델 정확도는 30개 항목마다 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b12b-192">![검토 항목 상자](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6b12b-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="6b12b-193">200개 이상의 항목을 검토합니다. </span><span class="sxs-lookup"><span data-stu-id="6b12b-193">Review *at least* 200 items.</span></span> <span data-ttu-id="6b12b-194">정확도 점수가 안정화되면  게시 옵션을 사용할 수 있으며 분류자 상태가 으로 `Ready to use` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b12b-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b12b-195">![정확도 점수 및 게시 준비 완료](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="6b12b-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="6b12b-196">분류자 게시</span><span class="sxs-lookup"><span data-stu-id="6b12b-196">Publish the classifier.</span></span>

21. <span data-ttu-id="6b12b-197">분류자가 게시된 후 민감도 레이블이 있는 [Office](apply-sensitivity-label-automatically.md)자동 레이블 [지정,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 조건 및 통신 준수에 따라 보존 레이블 정책 자동 적용에서 조건으로 사용할 [수 있습니다.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="6b12b-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
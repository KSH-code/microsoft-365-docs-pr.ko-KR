---
title: 학습 가능한 분류자 시작(미리 보기)
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
description: Microsoft 365 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다. 이 문서에서는 사용자 지정 분류자를 만들고 학습 하는 방법과이를 재교육 하 여 정확성을 향상 시키는 방법을 설명 합니다.
ms.openlocfilehash: 30f3c45945b4879be17eadfe04e8ccb8526df16a
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379250"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="7f38b-104">학습 가능한 분류자 시작(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7f38b-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="7f38b-105">Microsoft 365 trainable 분류자는 다양 한 유형의 콘텐츠를 확인할 수 있도록 교육을 제공 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="7f38b-106">훈련을 받은 후에는이를 통해 Office 민감도 레이블, 통신 준수 정책 및 보존 레이블 정책의 응용 프로그램에 대 한 항목을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="7f38b-107">먼저 사용자 지정 trainable 분류자를 만들려면 해당 범주와 정확히 일치 하는 샘플을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="7f38b-108">그런 다음이를 처리 한 후에는 긍정적이 고 부정적 샘플을 함께 제공 하 여 분류자 기능을 예측 하도록 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="7f38b-109">이 문서에서는 사용자 지정 분류자를 만들고 학습 하는 방법과, 사용자 지정 trainable 분류자 및 해당 수명 보다 미리 훈련 된 분류자의 성능을 개선 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="7f38b-110">서로 다른 종류의 분류자에 대 한 자세한 내용은 [trainable 분류자 (preview)에 대 한](classifier-learn-about.md)자세한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f38b-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f38b-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7f38b-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="7f38b-112">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f38b-112">Licensing requirements</span></span>

<span data-ttu-id="7f38b-113">분류자는 Microsoft 365 E5 또는 E5 규정 준수 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="7f38b-114">이러한 구독 중 하나를 사용 하 여이를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="7f38b-115">권한</span><span class="sxs-lookup"><span data-stu-id="7f38b-115">Permissions</span></span>

<span data-ttu-id="7f38b-116">UI의 분류자에 액세스 하려면:</span><span class="sxs-lookup"><span data-stu-id="7f38b-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="7f38b-117">전역 관리자가 사용자 지정 분류자를 만들기 위해 테 넌 트를 옵트인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-117">the Global admin needs to opt in for the tenant to create custom classifiers</span></span>
- <span data-ttu-id="7f38b-118">분류자를 교육 하려면 준수 관리자 역할 또는 준수 데이터 관리자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-118">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="7f38b-119">이러한 시나리오에서 분류자를 사용 하려면 다음과 같은 권한이 있는 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="7f38b-120">보존 레이블 정책 시나리오: 레코드 관리 및 보존 관리 역할</span><span class="sxs-lookup"><span data-stu-id="7f38b-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="7f38b-121">민감도 레이블 정책 시나리오: 보안 관리자, 준수 관리자, 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="7f38b-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="7f38b-122">통신 준수 정책 시나리오: 참가자 위험 관리 관리자, 관리 검토 관리자</span><span class="sxs-lookup"><span data-stu-id="7f38b-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7f38b-123">기본적으로 사용자 지정 분류자를 만드는 사용자만이 해당 분류자에서 수행한 예측을 학습 하 고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="7f38b-124">다른 사용자가 분류자 예측을 학습 하 고 검토할 수 있도록 하려면 [다른 사용자에 게 교육 및 권한 검토](#give-others-train-and-review-rights)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f38b-124">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](#give-others-train-and-review-rights).</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="7f38b-125">사용자 지정 trainable 분류자 준비</span><span class="sxs-lookup"><span data-stu-id="7f38b-125">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="7f38b-126">시작 하기 전에 사용자 지정 trainable 분류자를 만드는 것과 관련 된 사항을 이해 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-126">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="7f38b-127">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="7f38b-127">Timeline</span></span>

<span data-ttu-id="7f38b-128">이 시간 표시줄에는 trainable 분류자의 배포 예가 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-128">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-분류자-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="7f38b-130">Trainable 분류자에 대해 처음으로 옵트인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-130">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="7f38b-131">Microsoft 365에서 조직의 콘텐츠를 기준으로 평가 하는 데 12 일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-131">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="7f38b-132">전역 관리자에 게 연락 하 여 옵트인 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-132">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="7f38b-133">전체 워크플로</span><span class="sxs-lookup"><span data-stu-id="7f38b-133">Overall workflow</span></span>

<span data-ttu-id="7f38b-134">사용자 지정 trainable 분류자를 만드는 전체 워크플로에 대 한 자세한 내용은 [customer trainable 분류자를 만들기 위한 프로세스 흐름](classifier-learn-about.md#process-flow-for-creating-custom-classifiers) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f38b-134">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span></span>

### <a name="seed-content"></a><span data-ttu-id="7f38b-135">콘텐츠 시드</span><span class="sxs-lookup"><span data-stu-id="7f38b-135">Seed content</span></span>

<span data-ttu-id="7f38b-136">Trainable 분류자가 특정 콘텐츠 범주에 있는 항목을 독립적으로 식별 하도록 하려면 먼저 범주에 포함 된 콘텐츠 형식의 여러 샘플을 사용 하 여이를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-136">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="7f38b-137">이러한 trainable 분류자에 대 한 샘플 공급을 *시드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-137">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="7f38b-138">시드 콘텐츠는 사용자가 선택 하 고 콘텐츠 범주를 나타내도록 판단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-138">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="7f38b-139">최소 50의 양수 500 샘플을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-139">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="7f38b-140">Trainable 분류자는 가장 최근에 생성 500 된 샘플 (파일을 만든 날짜/시간 스탬프)까지 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-140">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="7f38b-141">제공 하는 샘플이 많을 수록 분류자가 더 정확 하 게 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-141">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="7f38b-142">콘텐츠 테스트</span><span class="sxs-lookup"><span data-stu-id="7f38b-142">Testing content</span></span>

<span data-ttu-id="7f38b-143">Trainable 분류자가 예측 모델을 작성 하기에 충분 한 긍정적인 샘플을 처리 한 후에는 해당 분류자가 해당 범주 및 항목과 일치 하는 항목을 올바르게 구분할 수 있는지 여부를 확인 하는 예측을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-143">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="7f38b-144">이 작업을 수행 하면 범주 및 샘플에 포함 되는 샘플로 구성 된 사용자가 선택한 콘텐츠 집합을 다른 사람에 게 공급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-144">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="7f38b-145">이러한 프로세스를 처리 하면 수동으로 결과를 확인 하 여 각 예측이 올바른지, 부정확 한지 또는 확실 하지 않을 지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="7f38b-146">Trainable 분류자는이 피드백을 사용 하 여 예측 모델을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="7f38b-147">최상의 결과를 위해서는 테스트 샘플 집합에 긍정 및 음의 일치를 균등 하 게 배포 하 여 200 개 이상의 항목을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="7f38b-148">Trainable 분류자를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="7f38b-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="7f38b-149">50-500 seed 콘텐츠 항목을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="7f38b-150">이러한 샘플은 trainable 분류자가 분류 범주에서 진행 되는 것 처럼 식별 하려는 콘텐츠 유형을 강력 하 게 나타내는 예제 일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="7f38b-151">지원 되는 파일 형식에 대해서는 [기본 크롤링 파일 이름 확장명 및 구문 분석 된 파일 형식 SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f38b-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f38b-152">Seed 및 test 샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f38b-153">시드 집합의 항목이 범주의 **강력한** 예 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="7f38b-154">Trainable 분류자는 초기 시드를 기반으로 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="7f38b-155">이 분류자는 모든 시드 샘플을 강력 하 게 가정 하며, 샘플이 해당 범주와 가장 약한 지 또는 음의 일치 인지를 알 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="7f38b-156">Seed 콘텐츠만 보관 전용으로 설정 된 시드 콘텐츠를 SharePoint Online 폴더에 배치 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="7f38b-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="7f38b-157">사이트, 라이브러리 및 폴더 URL을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-157">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="7f38b-158">시드 데이터에 대 한 새 사이트 및 폴더를 만드는 경우 해당 위치에 대해 최소 1 시간 이상 해당 시드 데이터를 사용 하는 trainable 분류자를 만들기 전에이를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="7f38b-159">준수 관리자 또는 보안 관리자 역할 액세스를 사용 하 여 microsoft 365 준수 센터에 로그인 하 고 **microsoft 365 준수 센터** 또는 **microsoft 365 보안 센터**  >  **데이터 분류** 열기</span><span class="sxs-lookup"><span data-stu-id="7f38b-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="7f38b-160">**Trainable 분류자** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="7f38b-161">**Trainable 분류자 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="7f38b-162">`Name` `Description` 이 trainable 분류자가 식별 하는 데 사용할 항목의 범주에 적절 한 값과 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-162">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="7f38b-163">2 단계의 시드 콘텐츠 사이트에 대 한 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="7f38b-164">`Add`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-164">Choose `Add`.</span></span>

8. <span data-ttu-id="7f38b-165">설정을 검토 하 고 `Create trainable classifier` 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="7f38b-166">24 시간 이내에 trainable 분류자는 시드 데이터를 처리 하 고 예측 모델을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="7f38b-167">분류자 상태는 `In progress` 시드 데이터를 처리 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="7f38b-168">분류자가 시드 데이터 처리를 마치면 상태가로 변경 됩니다 `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="7f38b-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="7f38b-169">이제 분류자를 선택 하 여 세부 정보 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-169">You can now view the details page by choosing the classifier.</span></span>


![trainable 분류자에서 테스트할 준비가 되었습니다.](../media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="7f38b-171">최상의 결과를 위해 200 개 이상의 테스트 콘텐츠 항목 (1만 최대)을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="7f38b-172">이러한 항목은 강력한 포지티브, 강력한 네거티브 및 해당 특성을 약간 명확 하 게 나타내는 항목과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="7f38b-173">지원 되는 파일 형식에 대해서는 [기본 크롤링 파일 이름 확장명 및 구문 분석 된 파일 형식 SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f38b-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f38b-174">샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="7f38b-175">테스트 *콘텐츠만*보류 전용으로 설정 된 테스트 콘텐츠를 SharePoint Online 폴더에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="7f38b-176">SharePoint Online 사이트, 라이브러리 및 폴더 URL을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="7f38b-177">테스트 데이터에 대 한 새 사이트와 폴더를 만드는 경우 해당 위치에 대해 최소 1 시간 이상 해당 시드 데이터를 사용 하는 trainable 분류자를 만들기 전에이를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="7f38b-178">`Add items to test`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="7f38b-179">12 단계에서 테스트 콘텐츠 사이트에 대 한 SharePoint Online 사이트, 라이브러리 및 폴더 URL을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="7f38b-180">`Add`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-180">Choose `Add`.</span></span>

15. <span data-ttu-id="7f38b-181">을 선택 하 여 마법사를 완료 `Done` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="7f38b-182">Trainable 분류자는 테스트 파일을 처리 하는 데 최대 1 시간까지 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="7f38b-183">Trainable 분류자가 테스트 파일의 처리를 마치면 세부 정보 페이지의 상태가로 변경 됩니다 `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="7f38b-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="7f38b-184">테스트 샘플 크기를 증가 시켜야 하는 경우에 `Add items to test` 는 trainable 분류자가 추가 항목을 처리 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![스크린샷 검토 준비 완료](../media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="7f38b-186">`Tested items to review`항목을 검토 하려면 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="7f38b-187">Microsoft 365는 한 번에 30 개의 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="7f38b-188">이러한 항목을 검토 하 고 `We predict this item is "Relevant". Do you agree?` 상자에서 `Yes` 또는 `No` 또는 `Not sure, skip to next item` 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="7f38b-189">모델 정확도는 30 개 항목 마다 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-189">Model accuracy is automatically updated after every 30 items.</span></span>

![검토 항목 상자](../media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="7f38b-191">*최소* 200 항목을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-191">Review *at least* 200 items.</span></span> <span data-ttu-id="7f38b-192">정확도 점수가 안정화 되 면 **게시** 옵션을 사용할 수 있게 되 고 분류자 상태가 표시 됩니다 `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="7f38b-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

![정확성 성과를 게시할 준비가 되었습니다.](../media/classifier-trainable-review-ready-to-publish.png)

20. <span data-ttu-id="7f38b-194">분류자를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-194">Publish the classifier.</span></span>

21. <span data-ttu-id="7f38b-195">게시 한 분류자는 [민감도 레이블이 있는 Office 자동 레이블](apply-sensitivity-label-automatically.md)지정의 조건으로 사용할 수 있으며, 조건 및 [통신 준수](communication-compliance.md)에 [따라 보존 레이블 정책을 자동으로 적용](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

## <a name="give-others-train-and-review-rights"></a><span data-ttu-id="7f38b-196">다른 사용자에 게 교육 권한 제공 및 검토</span><span class="sxs-lookup"><span data-stu-id="7f38b-196">Give others train and review rights</span></span>

<span data-ttu-id="7f38b-197">다음 절차에 따라 다른 사람에 게 사용자 지정 trainable 분류자를 훈련, 검토 및 조정할 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-197">Use this procedure to give others permissions to train, review and tune your custom trainable classifier.</span></span>  
 
1. <span data-ttu-id="7f38b-198">분류자를 만든 사람은 전역 관리자 또는 eDiscovery 관리자가 PowerShell을 사용 하 여 준수 센터에 연결 하 여 [Security to & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true)의 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-198">As the creator of the classifier, a global admin or eDiscovery admin connect to the Compliance center using PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span></span>
2. <span data-ttu-id="7f38b-199">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-199">Run this command:</span></span>
```powershell
Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
```
<span data-ttu-id="7f38b-200">예: `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7f38b-200">For example: `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span></span>

<span data-ttu-id="7f38b-201">이 명령을 여러 번 실행 하 여 여러 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-201">You can run this command multiple times to add multiple users.</span></span> <span data-ttu-id="7f38b-202">Azure 역할 그룹은 EOP (Exchange Online Protection) 역할 그룹만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f38b-202">Note that you can only add Exchange Online Protection (EOP) Role Groups and not Azure Role Groups.</span></span>

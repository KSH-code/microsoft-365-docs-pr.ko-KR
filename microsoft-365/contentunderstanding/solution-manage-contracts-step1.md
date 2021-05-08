---
title: 1단계. Syntex를 SharePoint 사용하여 계약 파일을 식별하고 데이터 추출
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Syntex를 사용하여 SharePoint 솔루션을 사용하여 계약 파일을 식별하고 데이터를 추출하는 Microsoft 365 대해 알아보십시오.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281342"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="26b09-104">1단계.</span><span class="sxs-lookup"><span data-stu-id="26b09-104">Step 1.</span></span> <span data-ttu-id="26b09-105">Syntex를 SharePoint 사용하여 계약 파일을 식별하고 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="26b09-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="26b09-106">조직에서는 받은 많은 파일에서 모든 계약 문서를 식별하고 분류하는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="26b09-107">또한 식별된 각 계약 파일의 여러 주요 요소(예: *클라이언트,* 계약자 및 수수료 금액)를 빠르게 볼 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="26b09-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="26b09-108">이 작업을 위해 [Syntex를](index.md) SharePoint 문서 이해 모델을 만들어 문서 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

<span data-ttu-id="26b09-109">[문서 이해는](document-understanding-overview.md) 인공 지능(AI) 모델을 사용하여 파일 분류 및 정보 추출을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-109">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="26b09-110">문서 이해 모델은 필요한 정보가 테이블이나 양식(예: 계약)에 포함되어 있지 않은 구조화되지 않은 문서 및 반구조적 문서에서 정보를 추출할 때도 최적의 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-110">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="26b09-111">먼저 식별하려는 콘텐츠 형식(계약)에 특정한 특성을 검색하기 위해 모델을 "학습"하는 데 사용할 수 있는 5개 이상의 예제 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-111">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="26b09-112">Syntex를 SharePoint 새 문서 이해 모델을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-112">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="26b09-113">예제 파일을 사용하여 분류자 [를 만들어야 합니다.](create-a-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="26b09-113">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="26b09-114">분류자에 예제 파일을 교육하여 회사 계약에서 볼 수 있는 특징을 검색하도록 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-114">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="26b09-115">예를 들어 서비스 계약, 계약 조건 및 보상과 같이 계약에 있는 특정 문자열을 검색하는 ["설명"을](create-a-classifier.md#create-an-explanation) *만들 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="26b09-115">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="26b09-116">문서의 특정 섹션에서 또는 다른 문자열 옆에 있는 이러한 문자열을 검색하도록 설명을 교육할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-116">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="26b09-117">필요한 정보를 사용하여 분류자 교육을 했다고 생각되는 경우 예제 파일 예제 집합에서 모델을 테스트하여 효율성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-117">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="26b09-118">테스트 후 필요한 경우 설명을 보다 효율적으로 변경하기 위해 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-118">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="26b09-119">모델에서 각 계약에서 특정 데이터 조각을 끌어오는 추출기 만들기를 만들 수 있습니다. [](create-an-extractor.md)</span><span class="sxs-lookup"><span data-stu-id="26b09-119">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="26b09-120">예를 들어 각 계약에 대해 가장 우려되는 정보는 클라이언트의 사용자, 계약자 이름 및 총 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-120">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="26b09-121">모델을 성공적으로 만든 후 SharePoint [라이브러리에 적용합니다.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="26b09-121">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="26b09-122">문서 라이브러리에 문서를 업로드하면 문서 이해 모델이 실행되고 모델에서 정의한 계약 콘텐츠 형식과 일치하는 모든 파일을 식별하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-122">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="26b09-123">계약으로 분류된 모든 파일은 사용자 지정 라이브러리 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-123">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="26b09-124">파일에는 추출기에서 정의한 각 계약의 값도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-124">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![문서 라이브러리의 계약](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="26b09-126">또한 계약에 대한 보존 요구 사항이 있는 경우 모델을 사용하여 [](apply-a-retention-label-to-a-model.md) 지정된 기간 동안 계약이 삭제되지 않도록 하는 보존 레이블을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26b09-126">Additionally, if you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="next-step"></a><span data-ttu-id="26b09-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="26b09-127">Next step</span></span>

[<span data-ttu-id="26b09-128">2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="26b09-128">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
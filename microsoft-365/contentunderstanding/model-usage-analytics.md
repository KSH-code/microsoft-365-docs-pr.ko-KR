---
title: 문서 이해 모델 사용 분석
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
description: 문서 이해 모델에 보존 레이블을 적용하는 방법 알아보기
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080440"
---
# <a name="document-understanding-model-usage-analytics"></a><span data-ttu-id="183a3-103">문서 이해 모델 사용 분석</span><span class="sxs-lookup"><span data-stu-id="183a3-103">Document understanding model usage analytics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


<span data-ttu-id="183a3-104">Microsoft SharePoint Syntex 콘텐츠 센터는 콘텐츠 센터에서 게시 된 모델이 어떻게 사용 되는지에 대한 더 많은 정보를 제공 하기 위해 모델 사용 분석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-104">Your Microsoft SharePoint Syntex content center provides you model usage analytics to provide more information about how your models that have been published from the content center are being used.</span></span> <span data-ttu-id="183a3-105">콘텐츠 센터의 <b>최근 30일 동안 모델의 성능</b> 섹션에는 다음 챠트 및 목록에 제공되는 30일 간의 사용 현황 분석 테이터 롤업이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-105">The <b>How your models are performing in the last 30 days</b> section of the content center includes a 30 day roll-up of usage analytics data provided in the following charts and lists:</span></span>

- <span data-ttu-id="183a3-106">모델별 분류</span><span class="sxs-lookup"><span data-stu-id="183a3-106">Classification by model</span></span>
- <span data-ttu-id="183a3-107">라이브러리별 분류</span><span class="sxs-lookup"><span data-stu-id="183a3-107">Classification by library</span></span>
- <span data-ttu-id="183a3-108">모델 사용</span><span class="sxs-lookup"><span data-stu-id="183a3-108">Model usage</span></span> 

 ![모델 분석](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a><span data-ttu-id="183a3-110">기본 콘텐츠 센터에서 모델 사용 현황 데이터 롤업</span><span class="sxs-lookup"><span data-stu-id="183a3-110">Roll up of model usage data in the default content center</span></span>

<span data-ttu-id="183a3-111">SharePoint Syntex에서 기본 콘텐츠 센터는 설치 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-111">In SharePoint Syntex, the default content center is created during setup.</span></span> <span data-ttu-id="183a3-112">필요한 경우 추가 콘텐츠 센터를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-112">Additional content centers can also be created as needed.</span></span> <span data-ttu-id="183a3-113">예를 들어 부서에서 자체 콘텐츠 센터를 만들어 모델을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-113">For example, departments might create their own content centers to create and manage their models.</span></span> 

<span data-ttu-id="183a3-114">모델 사용 현황 분석과 관련하여 다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="183a3-114">In regards to model usage analytics, note that:</span></span>

- <span data-ttu-id="183a3-115">기본 콘텐츠 센터에는 추가 콘텐츠 센터에서 만든 모델을 포함하여 조직의 모든 콘텐츠 센터 및 모델에 대한 모델 사용 현황 분석을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-115">Your default content center will show model usage analytics for all content centers and models in your org, including ones created in additional content centers.</span></span> <span data-ttu-id="183a3-116">이를 통해 콘텐츠 관리자 및 기타 이해 관계자에게 회사 전체의 콘텐츠 센터 및 모델을 관리 감독할 수 있는 중앙 집중식 포털을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-116">This gives content managers and other stakeholders a centralized portal to manage and oversee the content centers and models across the company.</span></span>  
- <span data-ttu-id="183a3-117">다른 콘텐츠 센터에서는 해당 콘텐츠 센터에서 만든 모델에 대한 모델 사용 현황 분석만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-117">Other content centers will only show model usage analytics for the models that were created in them.</span></span> <span data-ttu-id="183a3-118">이로써 콘텐츠 관리자는 관심있어 하는 모델에 대해서만 사용 현황 데이터에 대한 통찰력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-118">This gives content managers insights into usage data for only the models they are concerned with.</span></span>


## <a name="classification-by-model"></a><span data-ttu-id="183a3-119">모델별 분류</span><span class="sxs-lookup"><span data-stu-id="183a3-119">Classification by model</span></span>

   ![총 모델 백분율](../media/content-understanding/total-model-percentage.png) </br>

<span data-ttu-id="183a3-121">**모델별 분류** 원형 차트에서는 가장 많은 파일을 분류한 모델이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-121">The **Classification by model** pie chart displays which models have classified the most files.</span></span> <span data-ttu-id="183a3-122">게시된 각 모델은 콘텐츠 센터에 게시된 모든 모델에서 처리한 총 파일의 백분율로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-122">It shows each published model as a percentage of the total files processed by all published models on the content center.</span></span>

<span data-ttu-id="183a3-123">각 모델은 모델에 의해 성공적으로 분석된 업로드 된 파일의 백분율인 **완성율** 을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-123">Each model also shows the **Completeness Rate**, the percentage of uploaded files that were successfully analyzed by the model.</span></span> <span data-ttu-id="183a3-124">낮은 완성율은 모델 혹은 분석된 파일에 문제가 있음을 의미 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-124">A low completeness rate may mean that there are issues with either the model or the files that are being analyzed.</span></span>

## <a name="classification-by-library"></a><span data-ttu-id="183a3-125">라이브러리별 분류</span><span class="sxs-lookup"><span data-stu-id="183a3-125">Classification by library</span></span>

   ![처리된 파일](../media/content-understanding/files-processed-over-time.png) </br>

<span data-ttu-id="183a3-127">**라이브러리별 분류** 막대 차트는 조직에서 콘텐츠 이해의 효율성을 결정하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-127">The **Classification by library** bar chart helps you determine the effectiveness of content understanding in your organization.</span></span>  <span data-ttu-id="183a3-128">각 모델에서 시간에 따라 처리된 파일 수를 보여줄 뿐만 아니라 챠트의 열을 선택하면 모델이 적용된 문서 라이브러리도 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-128">It shows you not only the number of files processed over time for each model, but by selecting a column in chart, it will also show you the document libraries to which the model was applied.</span></span>


## <a name="model-usage"></a><span data-ttu-id="183a3-129">모델 사용</span><span class="sxs-lookup"><span data-stu-id="183a3-129">Model usage</span></span>

<span data-ttu-id="183a3-130">모델 사용 목록에는 콘텐츠 센터를 통해 만들어진 모델에 대한 사용 현황 분석이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-130">The Model Usage list will show usage analytics for the models created through the content center.</span></span>  

> [!NOTE]
> <span data-ttu-id="183a3-131">기본 콘텐츠 센터에 있으며 조직에 추가 콘텐츠 센터가 있는 경우 모델 사용 목록은 콘텐츠 센터별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-131">If you are in the default content center and have additional content centers in your organization, the model usage list will be grouped by content center.</span></span>

<span data-ttu-id="183a3-132">모델 사용 목록에 있는 각 모델에는 사용 현황 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-132">Each model in the model usage list will show the usage data:</span></span>

- <span data-ttu-id="183a3-133">분류된 항목 수: 모델별로 처리되는 파일 수입니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-133">Classified item count: Number of files processed by the model.</span></span>
- <span data-ttu-id="183a3-134">평균 신뢰도 점수: 파일에 대해 실행할 때 모델의 평균 정확도 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-134">Average confidence score: Average accuracy score of the model when run against files.</span></span>
- <span data-ttu-id="183a3-135">대상 목록 URL: 모델이 적용되는 SharePoint 문서 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="183a3-135">Target list URL: The SharePoint document library to which the model is applied.</span></span>



## <a name="see-also"></a><span data-ttu-id="183a3-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="183a3-136">See Also</span></span>
[<span data-ttu-id="183a3-137">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="183a3-137">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="183a3-138">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="183a3-138">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="183a3-139">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="183a3-139">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="183a3-140">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="183a3-140">Create a form processing model</span></span>](create-a-form-processing-model.md)  

---
title: 다음의 검토 집합에서 데이터 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 사례를 분석할 때 문서 집합을 구성하는 데 사용할 수 있는 Advanced eDiscovery 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751373"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="d81f7-103">다음의 검토 집합에서 데이터 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d81f7-103">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="d81f7-104">수집된 문서의 수가 크면 모두 검토하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-104">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="d81f7-105">Advanced eDiscovery 정보를 손실하지 않고도 검토할 문서의 양을 줄이고 문서를 공동으로 구성하는 데 도움이 되는 다양한 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-105">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="d81f7-106">이러한 기능에 대한 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="d81f7-107">중복에 가까운 검색</span><span class="sxs-lookup"><span data-stu-id="d81f7-107">Near duplicate detection</span></span>](near-duplicate-detection-in-advanced-ediscovery.md)

- [<span data-ttu-id="d81f7-108">전자 메일 스레드</span><span class="sxs-lookup"><span data-stu-id="d81f7-108">Email threading</span></span>](email-threading-in-advanced-ediscovery.md)

- [<span data-ttu-id="d81f7-109">테마</span><span class="sxs-lookup"><span data-stu-id="d81f7-109">Themes</span></span>](themes-in-advanced-ediscovery.md)

<span data-ttu-id="d81f7-110">검토 집합의 데이터를 분석하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d81f7-110">To analyze data in a review set:</span></span>

1. <span data-ttu-id="d81f7-111">사례에 대한 분석 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-111">Configure analytics settings for your case.</span></span> <span data-ttu-id="d81f7-112">자세한 내용은 검색 및 분석 [설정 구성을 참조하세요.](configure-search-and-analytics-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d81f7-112">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).</span></span>

2. <span data-ttu-id="d81f7-113">분석할 리뷰 집합을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-113">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="d81f7-114">검토 **집합 관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d81f7-114">Click **Manage review set**.</span></span>

4. <span data-ttu-id="d81f7-115">검토 **집합에 대한 분석 실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d81f7-115">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="d81f7-116">사례의 작업 탭에서 분석  진행률을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-116">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="d81f7-117">분석이 완료되면 분석 보고서를 보고, 분석 출력에 대한 검토 집합 내에서 쿼리를 실행하고(검토 집합 내의 쿼리 [참조)](review-set-search.md)특정 문서의 관련 문서를 볼 수 있습니다(검토 집합의 데이터 검토 [참조).](reviewing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="d81f7-117">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="d81f7-118">분석 보고서</span><span class="sxs-lookup"><span data-stu-id="d81f7-118">Analytics report</span></span>

<span data-ttu-id="d81f7-119">검토 집합에 대한 분석 보고서를 보는 방법:</span><span class="sxs-lookup"><span data-stu-id="d81f7-119">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="d81f7-120">검토 집합을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-120">Open the review set.</span></span>

2. <span data-ttu-id="d81f7-121">검토 **집합 관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d81f7-121">Click **Manage review set**.</span></span>

3. <span data-ttu-id="d81f7-122">보고서 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d81f7-122">Click **View report**.</span></span>

<span data-ttu-id="d81f7-123">보고서에는 분석의 7개 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-123">The report has seven components from analysis:</span></span>

- <span data-ttu-id="d81f7-124">**대상 인구:** 검토 집합에 있는 전자 메일 메시지, 첨부 파일 및 느슨한 문서의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-124">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="d81f7-125">**문서(첨부** 파일 제외): 피벗인 느슨한 문서 수, 피벗의 거의 중복에 가까운 고유 문서 또는 다른 문서의 정확한 복제본 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-125">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="d81f7-126">**전자 메일:** 포괄 복사본, 포괄 복사본 또는 그 어느 것도 포함하지 않은 전자 메일 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-126">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="d81f7-127">**첨부 파일:** 검토 집합에 있는 다른 전자 메일 첨부 파일과 고유하거나 중복되는 전자 메일 첨부 파일 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-127">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="d81f7-128">**유형별로 파일 수:** 파일 확장명으로 식별되는 파일 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-128">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="d81f7-129">**원본을 통해 문서 수:** 원본 데이터 원본의 콘텐츠 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-129">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="d81f7-130">**프로세스별로 집계된 문서:** 검토 집합 프로세스의 콘텐츠 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="d81f7-130">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 

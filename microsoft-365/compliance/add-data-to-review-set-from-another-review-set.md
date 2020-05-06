---
title: 한 검토 집합의 데이터를 다른 검토 집합에 추가
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
description: 한 검토 집합에서 문서를 선택 하 고 고급 eDiscovery 사례의 다른 집합에서 개별적으로 사용 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 636e76b1740cfa07254e4c56165cfafa8f1fad5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034682"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="4d53a-103">다른 검토 집합의 검토 집합에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="4d53a-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="4d53a-104">어떤 경우에는 한 검토 집합에서 문서를 선택 하 여 다른 검토 집합에서 개별적으로 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="4d53a-105">이 기능은 검토 집합에 콘텐츠를 culled 데이터 하위 집합에 대 한 분석을 실행 하려는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="4d53a-106">이 문서에서 설명 하는 워크플로를 따라 검토 집합 간에 콘텐츠를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4d53a-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4d53a-107">Before you begin</span></span>

<span data-ttu-id="4d53a-108">시작 하기 전에 데이터를 추가할 새 검토 집합을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-108">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="4d53a-109">사례에 대 한 **검토 집합** 탭에 새 검토 집합을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="4d53a-110">자세한 내용은 [Create a review set](managing-review-sets.md#create-a-review-set)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d53a-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="4d53a-111">1 단계: 다른 검토 집합에 추가할 콘텐츠 식별</span><span class="sxs-lookup"><span data-stu-id="4d53a-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="4d53a-112">원본 검토 집합에서 특정 문서를 선택 하거나 검토 집합 쿼리에서 반환 된 모든 항목을 선택 하 여 한 검토 집합의 콘텐츠를 다른 검토용으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="4d53a-113">선택한 항목을 추가 하는 경우 항목을 선택 하 고 **동작**을 선택한 다음 **다른 검토 집합에 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![다른 검토 집합에 추가](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="4d53a-115">2 단계: 다른 검토 집합에 추가 하기 위한 옵션 지정</span><span class="sxs-lookup"><span data-stu-id="4d53a-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="4d53a-116">**다른 검토 설정 옵션** 의 플라이 아웃 추가 페이지에서 항목을 추가할 검토 집합을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="4d53a-117">**모든 검색 결과** 또는 **선택한 항목**을 추가할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="4d53a-118">**추가 정보** 는 문서를 새 검토 집합에 추가할 때 항목의 모든 메타 데이터와 태그를 포함 ( **레이블** 확인란 선택) 하 여 원본 검토 집합에서 해당 태그로 포함할 것인지 여부를 포함 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![다른 검토 집합에 추가](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="4d53a-120">**확인**을 클릭 하면 다른 검토 집합에 추가 된 새 작업 ( **다른 검토 집합에 데이터 추가**)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="4d53a-121">**작업** 탭으로 이동 하 여이 작업의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d53a-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="4d53a-122">자세한 내용은 [작업 관리](managing-jobs-ediscovery20.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d53a-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>

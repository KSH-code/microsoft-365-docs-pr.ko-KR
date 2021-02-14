---
title: Advanced eDiscovery에서 스마트 태그 설정
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
ROBOTS: NOINDEX, NOFOLLOW
description: 스마트 태그를 사용하면 Advanced eDiscovery 사례의 콘텐츠를 검토할 때 기계 학습 기능을 적용할 수 있습니다. 스마트 태그 그룹을 사용하여 변호인-클라이언트 권한 모델과 같은 기계 학습 검색 모델의 결과를 표시합니다.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081085"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="a020e-104">Advanced eDiscovery에서 스마트 태그 설정</span><span class="sxs-lookup"><span data-stu-id="a020e-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="a020e-105">Advanced eDiscovery의 ML(기계 학습) 기능을 사용하면 검토 집합에서 사례 문서를 검토할 때 의사 결정 프로세스를 보다 효율적으로 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="a020e-106">스마트 태그는 검토 중에 문서에 태그를 지정하는 경우와 같은 결정이 기록되는 위치로 ML 기능을 가져오는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="a020e-107">스마트 태그 그룹을 만들면 스마트 태그 그룹과 연결된 ML 모델의 결과로 결정된 결정이 태그 그룹의 태그와 함께 인라인으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="a020e-108">이렇게 하면 특정 문서를 검토할 때 ML 결과 정보를 인라인으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="a020e-109">스마트 태그 그룹을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="a020e-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="a020e-110">검토 집합에서 검토 집합 관리를 **클릭한** 다음 태그 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a020e-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="a020e-111">태그 **그룹 추가를 클릭한** 다음 스마트 태그 **그룹 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a020e-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="a020e-112">태그 그룹에 연결하려는 ML 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="a020e-113">이렇게 하면 태그 그룹과 *N* 자식 태그가 생성됩니다. 여기서 *N은* 모델의 가능한 출력 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="a020e-114">예를 들어, [변호사-클라이언트 권한](attorney-privilege-detection.md) 검색 모델에는 다음 두 가지 출력이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="a020e-115">**양수** - 변호사-클라이언트 권한이 부여된 콘텐츠를 포함하는 문서에 태그를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="a020e-116">**음수** – 변호사-클라이언트 권한이 부여된 콘텐츠를 포함하지 않는 문서에 태그를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="a020e-117">이 모델을 선택하면 검토 집합에 대해 두 개의 하위 태그가 있는 태그 **그룹(Positive라는** 자식 태그 하나와 **네거티브라는** 다른 이름의 태그)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="a020e-118">이 예에서 각 자식 태그는 변호사-클라이언트 권한 검색 모델에서 가능한 출력 중 하나에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="a020e-119">선택적으로 태그 그룹 및 하위 태그의 이름을 이름을 다시 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="a020e-120">예를 들어 양수 태그의  이름을 Privileged로, **음수** 태그를 Not **privileged로** **이름을 지정하면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a020e-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="a020e-121">스마트 태그를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="a020e-121">How to use smart tags</span></span>

<span data-ttu-id="a020e-122">문서를 검토할 때 모델의 결과가 해당 자식 태그 옆에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="a020e-123">예를 들어, 변호사-클라이언트 권한 검색을 위한 스마트 태그 그룹이 있으며 잠재적으로 권한이 부여된 문서를 검토하는 경우 해당 결론의 이유가 적절한 태그 옆에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="a020e-124">태그는 문서에 자동으로 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="a020e-125">검토는 문서에 태그를 지정하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a020e-125">The reviewer makes the decision about how to tag the document.</span></span>

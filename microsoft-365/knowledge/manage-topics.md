---
title: '항목 환경의 항목 센터에서 항목 관리(미리 보기) '
description: 항목 센터에서 항목을 관리하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 371ccc16e787b331f42026dec48e5e3113b2b172
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976194"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="d5cae-103">항목 센터에서 항목 관리(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d5cae-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d5cae-104">이 문서의 내용은 Project Cortex Private Preview용입니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d5cae-105">[Project Cortex](https://aka.ms/projectcortex)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d5cae-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="d5cae-106">항목 센터에서 기술 관리자는 항목  관리 페이지를 보고 지식 관리자가 지정한 SharePoint 원본 위치에서 식별된 항목을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![항목 센터](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="d5cae-108">지식 관리자는 다음 항목의 수명 주기를 통해 검색된 항목을 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="d5cae-109">제안: 항목을 AI로 식별하여 항목 임계값을 충족할 수 있는 충분한 지원 리소스, 연결 및 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="d5cae-110">확인: AI가 제안한 항목의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="d5cae-111">유효성 검사는 지식 관리자의 확인을 통해 수행됩니다. 또한 두 개 이상의 사용자가 항목 피드백을 통해 해당 항목의 유효하다는 긍정적인 피드백을 제공하면 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="d5cae-112">제거됨: 항목은 기술 관리자가 거부하며 더 이상 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="d5cae-113">이 항목은 제거될 때(제안되거나 확인됨) 모든 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="d5cae-114">게시: 수동으로 업데이트된 확인된 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![항목 수명 주기 차트](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="d5cae-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5cae-116">Requirements</span></span>

<span data-ttu-id="d5cae-117">항목 센터에서 항목을 관리하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="d5cae-118">항목 환경 라이선스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="d5cae-119">항목을 관리할 수 [**있는 사용자에 대한 권한이 있습니다.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="d5cae-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="d5cae-120">지식 관리자는 기술 네트워크 항목 사용 권한 설정에서 사용자에게 이 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="d5cae-121">항목 관리 권한이 있는 경우 항목 센터에서 항목 관리 페이지를 볼 **수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="d5cae-122">항목 센터에서 기술 관리자는 지정한 SharePoint 원본 위치에서 식별된 항목을 검토할 수 있으며 이를 확인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="d5cae-123">또한 지식 관리자는 항목 검색에서 새 항목 페이지를 만들고 게시하거나, 업데이트해야 할 경우 기존 항목 페이지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="d5cae-124">추천 항목 검토</span><span class="sxs-lookup"><span data-stu-id="d5cae-124">Review suggested topics</span></span>

<span data-ttu-id="d5cae-125">항목 센터 항목 관리 페이지에서 지정된 SharePoint 원본 위치에서 검색된 항목은 제안  탭에 나열됩니다. 기술 관리자는 확인되지 않은 항목을 검토하고 이를 확인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="d5cae-126">제안된 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="d5cae-127">항목 **관리 페이지에서** 추천 탭을 선택하고 항목 페이지를 열 항목을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="d5cae-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="d5cae-128">항목 페이지에서 항목 페이지를 검토하고 페이지를  변경해야 하는 경우 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="d5cae-129">항목을 검토한 후 항목 관리 페이지로 돌아 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="d5cae-130">선택한 항목의 경우 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="d5cae-131">항목을 확인하려면 확인 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="d5cae-132">항목을 거부하려면 **x를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="d5cae-133">확인된 항목은 제안 목록에서 제거되고 이제 확인 목록에 **표시됩니다.** </span><span class="sxs-lookup"><span data-stu-id="d5cae-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="d5cae-134">거부된 항목은 제안 목록에서 제거되고 제거된 탭에 **표시됩니다.** </span><span class="sxs-lookup"><span data-stu-id="d5cae-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="d5cae-135">확인된 항목</span><span class="sxs-lookup"><span data-stu-id="d5cae-135">Confirmed topics</span></span>

<span data-ttu-id="d5cae-136">항목 관리 페이지에서 지정된 SharePoint 원본 위치에서 검색되어 기술 관리자 또는 카드 피드백 메커니즘을 통해 두명 이상의 사람이 확인한 "크라우드 소스"에서  확인한 항목은 확인된 탭에 나열됩니다. 필요한 경우 항목을 관리할 권한이 있는 사용자는 확인된 항목을 검토하고 거부하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="d5cae-137">확인된 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="d5cae-138">확인된  탭에서 항목을 선택하여 항목 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="d5cae-139">항목 페이지에서 항목 페이지를 검토하고 페이지를  변경해야 하는 경우 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="d5cae-140">여전히 확인된 항목을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="d5cae-141">이렇게하려면 확인된 목록에서 선택한 항목으로 이동한 다음 항목을 거부하려면 **x를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="d5cae-142">게시된 항목</span><span class="sxs-lookup"><span data-stu-id="d5cae-142">Published topics</span></span>
<span data-ttu-id="d5cae-143">게시된 항목은 편집된 항목으로, 특정 정보가 페이지를 방문하는 모든 사용자에 대해 항상 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="d5cae-144">수동으로 만든 항목은 여기에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5cae-144">Manually created topics are listed here.</span></span>





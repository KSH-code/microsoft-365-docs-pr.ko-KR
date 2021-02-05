---
title: Microsoft Viva 항목의 항목 센터에서 항목 관리
description: 항목 센터에서 항목을 관리하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107197"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="b19b1-103">항목 센터에서 항목 관리</span><span class="sxs-lookup"><span data-stu-id="b19b1-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="b19b1-104">Viva 항목 항목 센터에서 기술 관리자는 항목  관리 페이지를 보고 지식 관리자가 지정한 SharePoint 원본 위치에서 식별된 항목을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![항목 센터](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="b19b1-106">지식 관리자는 다음 항목의 수명 주기를 통해 검색된 항목을 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="b19b1-107">제안: 항목을 AI로 식별하여 충분한 지원 리소스, 연결 및 속성을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="b19b1-108">확인: AI에서 제안한 항목의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="b19b1-109">유효성 검사는 지식 관리자의 확인을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="b19b1-110">또한 두 개 이상의 사용자가 항목 카드의 피드백 질문을 통해 긍정적인 피드백을 제공하면 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="b19b1-111">게시: 큐레이터가 확정된 항목: 품질을 개선하기 위해 수동 편집을 진행했습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="b19b1-112">제거됨: 항목은 기술 관리자가 거부하며 더 이상 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="b19b1-113">이 항목은 제거될 때(제안, 확인 또는 게시) 모든 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="b19b1-114">게시된 항목을 제거하면 항목 센터의 페이지 라이브러리를 통해 큐레이터 세부 정보가 있는 페이지를 수동으로 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![항목 수명 주기 차트](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="b19b1-116">항목 관리 페이지에서 각 기술 관리자는 해당 항목의 파일 및 페이지에 대한 액세스 권한이 있는 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="b19b1-117">이는 추천, 확인, 제거 및 게시된 탭에 나열된 항목에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="b19b1-118">그러나 이 항목에서는 조직의 총 수를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="b19b1-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b19b1-119">Requirements</span></span>

<span data-ttu-id="b19b1-120">항목 센터에서 항목을 관리하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="b19b1-121">Viva Topics 라이선스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="b19b1-122">항목을 [**관리할 수 있는 사용자 권한을 부여합니다.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="b19b1-122">Have the [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) permission.</span></span> <span data-ttu-id="b19b1-123">지식 관리자는 Viva 항목 항목의 사용 권한 설정에서 사용자에게 이 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="b19b1-124">항목 관리 권한이 있는 경우 항목 센터에서 항목 관리 페이지를 볼 **수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="b19b1-125">항목 센터에서 기술 관리자는 지정한 SharePoint 원본 위치에서 식별된 항목을 검토할 수 있으며 이를 확인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="b19b1-126">또한 지식 관리자는 항목 검색에서 새 항목 페이지를 만들고 게시하거나, 업데이트해야 할 경우 기존 항목 페이지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="b19b1-127">추천 항목 검토</span><span class="sxs-lookup"><span data-stu-id="b19b1-127">Review suggested topics</span></span>

<span data-ttu-id="b19b1-128">항목 센터 항목 관리 페이지에서 지정된 SharePoint 원본 위치에서 검색된 항목은 제안  탭에 나열됩니다. 필요한 경우 기술 관리자는 확인되지 않은 항목을 검토하고 확인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![추천 항목](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="b19b1-130">제안된 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="b19b1-131">항목 **관리 페이지에서** 추천 탭을 선택하고 항목 페이지를 열 항목을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="b19b1-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="b19b1-132">항목 페이지에서 항목 페이지를 검토하고 페이지를  변경해야 하는 경우 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="b19b1-133">편집한 항목을 게시하면 이 항목은 게시된 **탭으로 이동됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b19b1-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="b19b1-134">항목을 검토한 후 항목 관리 페이지로 돌아 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="b19b1-135">선택한 항목의 경우 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="b19b1-136">항목을 확인하려면 확인 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="b19b1-137">항목을 거부하려면 **x를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="b19b1-138">확인된 항목은 제안 목록에서 제거되고 이제 확인 목록에 **표시됩니다.** </span><span class="sxs-lookup"><span data-stu-id="b19b1-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="b19b1-139">거부된 항목은 제안 목록에서 제거되고 제거된 탭에 **표시됩니다.** </span><span class="sxs-lookup"><span data-stu-id="b19b1-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="b19b1-140">품질 점수</span><span class="sxs-lookup"><span data-stu-id="b19b1-140">Quality score</span></span>

<span data-ttu-id="b19b1-141">추천 항목 페이지에 나타나는 각 항목에는 품질 <b></b> 점수가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="b19b1-142">품질 점수는 항목의 정보에 대해 평균 사용자가 볼 수 있는 정보의 양을 반영하는 것으로, 각 사용자는 항목의 정보에 대해 사용할 수 있는 권한으로 더 많이 또는 더 적은 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="b19b1-143">품질 점수는 가장 많은 정보를 사용하여 항목에 대한 정보를 파악하는 데 도움이 될 수 있으며 수동으로 편집해야 할 수 있는 항목을 찾는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="b19b1-144">예를 들어 품질 점수가 낮은 항목은 일부 사용자가 항목에 포함된 관련 파일 또는 사이트에 대한 SharePoint 권한이 없는 경우일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="b19b1-145">그런 다음 참가자가 해당 정보를 포함하도록 항목을 편집할 수 있습니다(해당되는 경우). 그러면 해당 항목을 볼 수 있는 모든 사용자가 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="b19b1-146">품질 점수의 범위는 1에서 100까지입니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="b19b1-147">새로 검색된 항목의 품질 점수는 두 명 이상의 사용자가 볼 때까지 0입니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="b19b1-148">각 사용자 품질 점수는 특정 사용자에게 표시되는 콘텐츠의 양과 같은 다양한 요인에 의해 결정됩니다. 각 항목 페이지에 AI 생성 콘텐츠에 대한 보안 트리밍이 적용되어 사용자 권한이 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="b19b1-149">추천 항목 탭에 표시되는 품질 점수는 각 사용자 개별 점수의 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="b19b1-150">광고 노출</span><span class="sxs-lookup"><span data-stu-id="b19b1-150">Impressions</span></span>

<span data-ttu-id="b19b1-151">노출 <b>수</b> 열에는 최종 사용자에게 항목을 표시한 횟수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="b19b1-152">여기에는 검색할 항목 카드, 항목 강조 표시 및 항목 센터 보기를 통한 보기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="b19b1-153">이 항목은 이러한 항목에 대한 클릭을 반영하지 않지만 해당 항목은 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="b19b1-154">노출 열은 항목 관리 페이지의 추천, 확인됨, 게시 및 제거된 탭에 있는 항목에 대해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="b19b1-155">확인된 항목</span><span class="sxs-lookup"><span data-stu-id="b19b1-155">Confirmed topics</span></span>

<span data-ttu-id="b19b1-156">항목 관리 페이지에서 지정된 SharePoint 원본 위치에서 검색되어 기술 관리자 또는 카드 피드백 메커니즘을 통해 두명 이상의 사람이 확인한 "크라우드 소스"에서  확인한 항목은 확인된 탭에 나열됩니다. 필요한 경우 항목을 관리할 권한이 있는 사용자는 확인된 항목을 검토하고 거부하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="b19b1-157">확인된 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="b19b1-158">확인된  탭에서 항목을 선택하여 항목 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="b19b1-159">항목 페이지에서 항목 페이지를 검토하고 페이지를  변경해야 하는 경우 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="b19b1-160">여전히 확인된 항목을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="b19b1-161">이렇게하려면 확인된 목록에서 선택한 항목으로 이동한 다음 항목을 거부하려면 **x를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="b19b1-162">게시된 항목</span><span class="sxs-lookup"><span data-stu-id="b19b1-162">Published topics</span></span>
<span data-ttu-id="b19b1-163">게시된 항목은 편집된 항목으로, 특정 정보가 페이지를 방문하는 모든 사용자에 대해 항상 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="b19b1-164">수동으로 만든 항목도 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b19b1-164">Manually created topics are listed here as well.</span></span>

   ![항목 관리](../media/knowledge-management/manage-topics-new.png) </br> 





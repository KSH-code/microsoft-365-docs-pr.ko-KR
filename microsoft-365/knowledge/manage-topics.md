---
title: Microsoft Viva 항목의 항목 센터에서 항목 관리
description: 항목 센터에서 항목을 관리하는 방법
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2c29cdb6823e695cb9c96a4f51ef7b1c41642ac9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333629"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="054d7-103">Microsoft Viva 항목의 항목 센터에서 항목 관리</span><span class="sxs-lookup"><span data-stu-id="054d7-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="054d7-104">Viva Topics 항목 센터에서 기술 관리자는  항목 관리 페이지를 보고 지식 관리자가 지정한 원본 위치에서 식별된 항목을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![항목 센터](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="054d7-106">항목 단계</span><span class="sxs-lookup"><span data-stu-id="054d7-106">Topic stages</span></span>

<span data-ttu-id="054d7-107">지식 관리자는 제안됨, 확인됨, 게시됨 및 제거됨 등 다양한 항목 수명 주기 단계에 대해 검색된 항목을  **안내할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="054d7-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![항목 수명 주기 차트](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="054d7-109">**추천 항목**: AI에 의해 식별되어 있으며 충분한 지원 리소스, 연결 및 속성을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="054d7-110">이러한 항목은 UI에서 추천 **항목으로** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="054d7-111">**확인된 항목**: AI에 의해 제안한 항목의 유효성이 입증되었습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="054d7-112">항목 유효성 검사는 기술 관리자가 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="054d7-113">항목을 확인하려면 항목 카드의 피드백 메커니즘을 사용하여 투표한 사용자로부터 받은 두 개의 긍정적인 투표의 네트워크가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="054d7-114">예를 들어 한 사용자가 특정 항목에 대해 긍정적인 반응을 보인 경우 한 사용자가 특정 항목에 대해 부정적인 반응을 보인 경우 확인하려면 여전히 두 개의 긍정적인 투표가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="054d7-115">**게시:** 큐레이터가 확정된 항목: 품질을 개선하기 위해 수동 편집을 진행했습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="054d7-116">**제거됨**: 지식 관리자가 항목을 거부하며 더 이상 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="054d7-117">모든 상태(제안, 확인 또는 게시)에서 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="054d7-118">항목을 제거하려면 항목 카드의 피드백 메커니즘을 사용하여 투표한 사용자로부터 받은 두 개의 부정적인 투표의 네트워크가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="054d7-119">예를 들어 한 사용자가 음수로 투표하고 한 사용자가 특정 항목에 대해 긍정적인 반응을 보인 경우 제거할 항목에 대해 두 개의 부정적인 투표가 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="054d7-120">게시된 항목을 제거하면 항목 센터의 페이지 라이브러리를 통해 큐레이터 세부 정보가 있는 페이지를 수동으로 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="054d7-121">항목 **관리 페이지에서** 각 기술 관리자는 항목에 연결된 파일 및 페이지에 대한 액세스 권한이 있는 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-121">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="054d7-122">이 사용 권한 트리밍은 제안됨, 확인됨, 게시됨 및 제거된 탭에 나타나는 항목 목록에 **반영됩니다.** </span><span class="sxs-lookup"><span data-stu-id="054d7-122">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="054d7-123">그러나 이 항목의 개수는 사용 권한에 관계없이 조직의 총 수를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-123">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="054d7-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="054d7-124">Requirements</span></span>

<span data-ttu-id="054d7-125">항목 센터에서 항목을 관리하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-125">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="054d7-126">Viva 항목 라이선스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-126">Have a Viva Topics license.</span></span>

- <span data-ttu-id="054d7-127">항목을 [**Who 수 있도록**](./topic-experiences-user-permissions.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-127">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="054d7-128">지식 관리자는 Viva 항목의 사용 권한 설정에서 사용자에게 이 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-128">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="054d7-129">항목 관리 권한이 있는  경우 항목 센터에서 항목 관리 페이지를 **Who 수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-129">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="054d7-130">항목 센터에서 기술 관리자는 지정한 원본 위치에서 식별된 항목을 검토할 수 있으며, 항목을 확인하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-130">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="054d7-131">또한 지식 관리자는 항목 검색에서 발견되지 않은 새 항목 페이지를 만들어 게시하거나, 업데이트해야 하는 경우 기존 항목을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-131">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="054d7-132">제안된 항목 검토</span><span class="sxs-lookup"><span data-stu-id="054d7-132">Review suggested topics</span></span>

<span data-ttu-id="054d7-133">항목 **관리 페이지에서** 지정한 원본 위치에서 검색된 항목은 SharePoint 탭에 나열됩니다.  필요한 경우 기술 관리자는 확인되지 않은 항목을 검토하고 확인하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-133">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![추천 항목](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="054d7-135">제안된 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-135">To review a suggested topic:</span></span>

1. <span data-ttu-id="054d7-136">항목 **관리 페이지에서** 추천 탭을 선택한 다음 항목을 선택하여 항목 페이지를 열 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="054d7-136">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="054d7-137">항목 페이지에서 항목 페이지를 검토하고 페이지를  변경해야 하는 경우 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-137">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="054d7-138">편집을 게시하면 이 항목은 **게시된 탭으로 이동됩니다.**</span><span class="sxs-lookup"><span data-stu-id="054d7-138">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="054d7-139">항목을 검토한 후 항목 **관리 페이지로 돌아** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-139">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="054d7-140">선택한 항목에 대해 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-140">For the selected topic, you can:</span></span>

   - <span data-ttu-id="054d7-141">항목을 확인하려면 확인 표시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-141">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="054d7-142">항목을 **제거하려면 x를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-142">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="054d7-143">확인된 항목은 제안 목록에서 제거되고 이제 확인됨 목록에 **표시됩니다.** </span><span class="sxs-lookup"><span data-stu-id="054d7-143">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="054d7-144">제거된 항목은 제안  목록에서 제거되고 이제 제거된 **탭에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-144">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="054d7-145">품질 점수</span><span class="sxs-lookup"><span data-stu-id="054d7-145">Quality score</span></span>

<span data-ttu-id="054d7-146">추천 항목 페이지에 나타나는  각 항목에는 품질 점수가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-146">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="054d7-147">품질 점수는 항목의 정보에 대해 평균 사용자가 볼 수 있는 정보의 양을 반영하는 것입니다. 각 사용자는 항목의 정보에 대한 사용 권한 또는 사용 권한으로 인하여 정보가 더 많이 또는 적게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-147">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="054d7-148">품질 점수는 가장 많은 정보를 사용하여 항목에 대한 정보를 제공하는 데 도움이 될 수 있으며 수동으로 편집해야 할 수 있는 항목을 찾는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-148">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="054d7-149">예를 들어 품질 점수가 낮은 항목은 일부 사용자가 해당 항목에 SharePoint 관련 파일 또는 사이트에 대한 사용 권한을 부여하지 않은 결과일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-149">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="054d7-150">그러면 참가자가 항목을 편집하여 정보를 포함(적절한 경우)시킬 수 있고, 토픽을 볼 수 있는 모든 사용자가 이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-150">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="054d7-151">노출</span><span class="sxs-lookup"><span data-stu-id="054d7-151">Impressions</span></span>

<span data-ttu-id="054d7-152">광고 **노출 열에는** 최종 사용자에게 항목을 표시한 횟수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-152">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="054d7-153">여기에는 검색의 항목 응답 카드와 항목 강조를 통한 보기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-153">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="054d7-154">이 항목의 클릭 클릭은 반영되지 않지만 해당 항목은 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-154">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="054d7-155">노출  **열은** 항목 관리 페이지의 **제안됨,** 확인됨, 게시됨  및 제거된 탭의 항목에 **대해** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-155">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="054d7-156">확인된 항목</span><span class="sxs-lookup"><span data-stu-id="054d7-156">Confirmed topics</span></span>

<span data-ttu-id="054d7-157">항목  관리 페이지에서 지정된 SharePoint 원본 위치에서 검색되고 네트워크 2명 이상이 확인한 "크라우드소싱"에서 확인한 항목(부정적인 사용자 투표와 긍정적인 사용자 투표의 균형 조정)이 카드 피드백 메커니즘을 통해  확인된 탭에 나열됩니다. 필요한 경우 항목을 관리할 권한이 있는 사용자는 확인된 항목을 검토하고 거부하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-157">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="054d7-158">확인된 항목을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-158">To review a confirmed topic:</span></span>

1. <span data-ttu-id="054d7-159">**확인된 항목** 탭에서 항목을 선택하여 항목 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-159">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="054d7-160">항목 페이지에서 항목 페이지를 검토하고 페이지를  변경해야 하는 경우 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-160">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="054d7-161">여전히 확인된 항목을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-161">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="054d7-162">이렇게하려면 확인 탭에서 선택한 항목으로 이동한 다음 항목을 거부하려면 **x를** 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="054d7-162">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="054d7-163">게시된 항목</span><span class="sxs-lookup"><span data-stu-id="054d7-163">Published topics</span></span>

<span data-ttu-id="054d7-164">게시된 항목은 편집된 항목으로, 특정 정보가 페이지를 방문하는 모든 사용자에 대해 항상 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-164">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="054d7-165">수동적으로 생성된 항목 또한 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d7-165">Manually created topics are listed here as well.</span></span>

   ![항목 관리](../media/knowledge-management/manage-topics-new.png)

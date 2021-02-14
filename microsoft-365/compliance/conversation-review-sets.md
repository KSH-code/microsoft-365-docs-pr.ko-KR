---
title: Advanced eDiscovery에서 대화 검토
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 대화 재구성 기능을 사용하여 스레드된 대화를 재구성, 검토 및 내보내는 방법을 학습합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358346"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="b56c0-103">Advanced eDiscovery에서 대화 검토</span><span class="sxs-lookup"><span data-stu-id="b56c0-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="b56c0-104">인스턴트 메시징은 질문을 하고, 아이디어를 공유하거나, 많은 대상에게 신속하게 통신할 수 있는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="b56c0-105">Microsoft Teams와 같은 인스턴트 메시징 플랫폼은 엔터프라이즈 공동 작업의 핵심이 되기 때문에 조직은 eDiscovery 워크플로가 이러한 새로운 형태의 커뮤니케이션 및 공동 작업을 어떻게 해결하고 있는지 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="b56c0-106">Advanced eDiscovery의 대화 재구성 기능은 상황에 맞는 콘텐츠를 식별하고 고유한 대화 보기를 생성하는 데 도움이 하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="b56c0-107">이 기능을 사용하면 Microsoft Teams와 같은 플랫폼에서 생성되는 전체 인스턴트 메시지 대화(스레드 대화라고도 지음)를 효율적이고 빠르게 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="b56c0-108">대화 재구성 기능을 사용하면 기본 제공 기능을 사용하여 스레드된 대화를 재구성, 검토 및 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="b56c0-109">고급 eDiscovery 대화 재구성을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="b56c0-110">대화 내의 모든 메시지에서 고유한 메시지 수준 메타데이터를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="b56c0-111">검색 결과와 관련한 상황에 맞는 메시지를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="b56c0-112">스레드 대화를 검토, 주석 및 다시 시정합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="b56c0-113">개별 메시지 또는 스레드된 대화 내보내기</span><span class="sxs-lookup"><span data-stu-id="b56c0-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="b56c0-114">용어</span><span class="sxs-lookup"><span data-stu-id="b56c0-114">Terminology</span></span>

<span data-ttu-id="b56c0-115">다음은 대화 재구성 사용을 시작하는 데 도움이 되는 몇 가지 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="b56c0-116">**메시지:** 대화의 가장 작은 단위를 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="b56c0-117">메시지의 크기, 구조 및 메타데이터는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="b56c0-118">**대화:** 하나 이상의 메시지 그룹화</span><span class="sxs-lookup"><span data-stu-id="b56c0-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="b56c0-119">여러 응용 프로그램에서 대화는 서로 다른 방식으로 표현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="b56c0-120">일부 응용 프로그램에서는 기존 메시지에 회신하는 명시적 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="b56c0-121">대화는 이 사용자 작업의 결과로 명시적으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="b56c0-122">예를 들어 Microsoft Teams의 채널 대화 스크린샷은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams 채널 대화](../media/threadedchat.png)

   <span data-ttu-id="b56c0-124">다른 앱(예: Teams의 1xN 채팅 메시지)에는 공식적인 회신 체인이 없는 대신 메시지가 단일 스레드 내에서 "평평한 메시지 강"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="b56c0-125">이러한 유형의 앱에서는 특정 시간 내에 발생하는 메시지 그룹에서 대화가 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="b56c0-126">이 "소프트 그룹화" 메시지(회신 체인과 반대)는 특정 관심 주제에 대한 "전방" 대화를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="b56c0-127">1단계: 검색 실행</span><span class="sxs-lookup"><span data-stu-id="b56c0-127">Step 1: Run a search</span></span>

<span data-ttu-id="b56c0-128">관련 관리인 및 콘텐츠 위치를 확인한 후 검색을 만들어 관련성이 있는 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="b56c0-129">Advanced  eDiscovery 사례의 검색 탭에서 새 검색을 클릭하고  마법사를 따라 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="b56c0-130">검색을 만들고, 검색 쿼리를 작성하고, 검색 결과를 보는 방법에 대한 자세한 내용은 사례에 대한 데이터 [수집을 참조하세요.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="b56c0-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="b56c0-131">2단계: 대화 검토 집합 만들기</span><span class="sxs-lookup"><span data-stu-id="b56c0-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="b56c0-132">검토 집합에서는 문서, 전자 메일 메시지 및 채팅 대화를 검색, 태그 지정, 주석 처리 및 재배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="b56c0-133">Advanced eDiscovery에서 개별 메시지 또는 스레드된 대화에 따라 대화 검토를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="b56c0-134">이 설정은 1단계에서 만든 검색 결과를 추가하는 검토 집합 유형에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="b56c0-135">검토 집합에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="b56c0-136">**표준 검토 집합:** 대화의 메시지는 처리되고 개별 항목으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="b56c0-137">**대화 검토 집합:** 대화의 메시지는 개별적으로 처리되지만 대화 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="b56c0-138">대화 검토 집합에서는 스레드된 대화 보기에서 메시지에 주석을 추가하고 태그를 지정하고 메시지를 다시 고치면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="b56c0-139">검토 집합에서 콘텐츠를 검토하고 관리하는 방법에 대한 자세한 내용은 검토 집합 [관리를 참조하십시오.](managing-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="b56c0-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="b56c0-140">3단계: 대화 검색 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="b56c0-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="b56c0-141">검색 쿼리를 검토하고 마무리한 후 검색 결과를 검토 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="b56c0-142">검색 결과를 검토 집합에 추가하면 검토 및 분석 프로세스를 용이하게 하기 위해 원본 데이터가 Azure Storage 영역에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="b56c0-143">검색 결과를 검토 집합에 추가하는 데 대한 자세한 내용은 리뷰 집합에 검색 [결과 추가를 참조하세요.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="b56c0-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="b56c0-144">대화의 데이터를 검토 집합에 추가할 때 대화 검색 옵션을 사용하여 검색을 확장하고 상황에 맞는 메시지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="b56c0-145">대화 검색 옵션을 설정하면 다음과 같은 상황이 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![대화 검색](../media/messagesandconversations.png)
  
1. <span data-ttu-id="b56c0-147">키워드 및 날짜 범위 쿼리를 사용하여 메시지 3에서 검색이 *적중을 반환했습니다.*</span><span class="sxs-lookup"><span data-stu-id="b56c0-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="b56c0-148">이 메시지는 *CRC1에서* 설명하는 더 큰 대화의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="b56c0-149">검토 집합에 데이터를 추가하고 대화 검색 옵션을 사용하도록 설정하면 Advanced eDiscovery가 *돌아가서 CRC1에서* 다른 항목을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="b56c0-150">검토 집합에 항목이 추가된 후 *CRC1의* 모든 개별 메시지를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="b56c0-151">대화 검색을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="b56c0-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="b56c0-152">Advanced  eDiscovery 사례의 검색 탭에서 검색을 선택한 다음  플라이아웃 페이지에서 설정한 검토에 추가를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="b56c0-153">기존 검토 집합을 선택하거나 검토 집합을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="b56c0-154">표준 또는 대화 검토 집합에 검색 결과를 추가할 때 검색 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="b56c0-155">컬렉션 **옵션에서** 검색에서 확장할 콘텐츠 원본에 대한 대화 검색 옵션을 구성한 다음  추가를 클릭하여 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="b56c0-156">작업 **탭에서 검토에** 추가 설정 **작업이** 완료된 후 대화 검토를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="b56c0-157">4단계: 검토 집합에서 대화 검토 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="b56c0-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="b56c0-158">콘텐츠가 처리되고 검토 집합에 추가된 후 검토 집합의 데이터 검토를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="b56c0-159">검토 기능은 콘텐츠가 표준 검토 집합에 추가되어 있는지 또는 대화 검토 집합에 추가되어 있는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="b56c0-160">표준 검토 집합에서 대화 검토</span><span class="sxs-lookup"><span data-stu-id="b56c0-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="b56c0-161">표준 검토 집합에서 메시지는 사서함 폴더에 저장되는 방법과 유사하게 개별 항목으로 처리되고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="b56c0-162">이 워크플로에서는 각 메시지가 별도의 항목으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="b56c0-163">따라서 표준 검토 집합에서는 스레드 요약 및 내보내기 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![표준 검토 집합](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="b56c0-165">대화 검토 집합에서 대화 검토</span><span class="sxs-lookup"><span data-stu-id="b56c0-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="b56c0-166">대화 검토 집합에서 개별 메시지는 함께 스레드되어 대화로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="b56c0-167">이를 통해 상황에 맞는 대화를 검토하고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-167">This lets you review and export contextual conversations.</span></span> 

  ![대화 검토 집합](../media/ConversationRSOptions.PNG)

<span data-ttu-id="b56c0-169">다음 섹션에서는 대화 검토 집합에서 대화를 검토하고 내보내는 데 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="b56c0-170">대화 검토</span><span class="sxs-lookup"><span data-stu-id="b56c0-170">Reviewing conversations</span></span>

<span data-ttu-id="b56c0-171">대화 검토 집합에서 다음 옵션을 사용하여 검토 프로세스를 용이하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="b56c0-172">**대화로 그룹화:** 사용자가 검토 프로세스를 단순화하고 더 쉽게 진행할 수 있도록 동일한 대화 내의 메시지를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="b56c0-173">**요약 보기:** 스레드된 대화를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="b56c0-174">이 보기에서는 전체 대화를 볼 수 있으며 각 개별 메시지의 메타데이터에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="b56c0-175">개별 메시지에 대한 메타데이터 보기</span><span class="sxs-lookup"><span data-stu-id="b56c0-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="b56c0-176">개별 메시지 다운로드</span><span class="sxs-lookup"><span data-stu-id="b56c0-176">Download individual messages</span></span>

- <span data-ttu-id="b56c0-177">**텍스트 보기:** 전체 대화에 대해 추출된 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="b56c0-178">**주석 보기:** 스레드된 대화 보기를 마크업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="b56c0-179">대화의 모든 메시지는 동일한 주석이 있는 문서를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="b56c0-180">**태그 지정:** 검토 집합에서 대화를 볼 때 코딩 패널에서 태그  지정 패널을 클릭하여 태그를 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="b56c0-181">**대화 변환 다시 시작:** 메시지가 대화 검토 집합에 추가되는 경우 변환 작업이 자동으로 실행되어 스레드된 요약을 만들고 보기에 주석을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="b56c0-182">대화 재구성 작업이 실패하면 검토 집합에서 대화 > 만들기 작업을 클릭하여 이 작업을 **다시** 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="b56c0-183">대화 내보내기</span><span class="sxs-lookup"><span data-stu-id="b56c0-183">Exporting conversations</span></span>

<span data-ttu-id="b56c0-184">대화 검토 집합에서 다음 옵션을 설정하여 대화를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![대화에 대한 옵션 내보내기](../media/export.png)

<span data-ttu-id="b56c0-186">a.</span><span class="sxs-lookup"><span data-stu-id="b56c0-186">a.</span></span> <span data-ttu-id="b56c0-187">메타데이터 옵션</span><span class="sxs-lookup"><span data-stu-id="b56c0-187">Metadata options</span></span>

   - <span data-ttu-id="b56c0-188">**파일을 로드합니다.** 각 개별 메시지, 전자 메일 및 문서에 대한 메타데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="b56c0-189">대화의 각 메시지에 대해 하나의 행이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="b56c0-190">**태그:** 검토 프로세스의 태그는 메타데이터 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="b56c0-191">대화의 메시지는 동일한 태그를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="b56c0-192">b.</span><span class="sxs-lookup"><span data-stu-id="b56c0-192">b.</span></span> <span data-ttu-id="b56c0-193">대화 옵션</span><span class="sxs-lookup"><span data-stu-id="b56c0-193">Conversation options</span></span>
  
   - <span data-ttu-id="b56c0-194">**대화 파일:** 대화 파일을 내보내면 주석이 있는 보기가 PDF 파일로 변환된 후 내보내기 폴더로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="b56c0-195">한 대화 파일의 메시지는 동일한 대화 파일의 PDF 버전을 지점으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="b56c0-196">**개별 채팅 메시지:** 개별 메시지를 내보낼 때 대화의 각 고유 메시지는 독립 실행형 항목으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="b56c0-197">파일을 사서함에 저장한 형식과 같은 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="b56c0-198">특정 대화의 경우 여러 .msg 파일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="b56c0-199">대화 파일에 주석을 적용한 경우 이러한 주석은 개별 메시지로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="b56c0-200">c.</span><span class="sxs-lookup"><span data-stu-id="b56c0-200">c.</span></span> <span data-ttu-id="b56c0-201">기타 옵션</span><span class="sxs-lookup"><span data-stu-id="b56c0-201">Other options</span></span>

   - <span data-ttu-id="b56c0-202">**내보낼 모든 콘텐츠에 대한 텍스트 파일을 생성합니다.** 검토 집합에서 내보낼 각 대화에 대한 텍스트 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="b56c0-203">**내보낼 콘텐츠를 업데이트된 PDF로 바꾸기:** 검토 프로세스 중에 삭제된 대화 파일이 생성되는 경우 내보내기 중에 이러한 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="b56c0-204">기본 파일만 내보낼지(이 옵션을 선택하지 않은 경우) 아니면 기본 파일을 PDF 파일로 내보낼지(이 옵션을 선택하여) 편집된 버전의 네이티브 파일로 바꿀지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="b56c0-205">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b56c0-205">More information</span></span>

<span data-ttu-id="b56c0-206">Advanced eDiscovery에서 사례 데이터를 검토하는 방법에 대한 자세한 내용은 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b56c0-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="b56c0-207">사례 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="b56c0-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="b56c0-208">대/소문자 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="b56c0-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="b56c0-209">사례 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="b56c0-209">Export case data</span></span>](exporting-data-ediscover20.md)

---
title: Microsoft Viva 항목 보안 트리밍
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: 항목을 보는 데 보안이 사용되는 방식에 대한 개요입니다.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939626"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="6862a-103">Microsoft Viva 항목 보안 트리밍</span><span class="sxs-lookup"><span data-stu-id="6862a-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="6862a-104">Viva 항목 사용자는 기존 Office 365 사용 권한으로 인해 사용자가 볼 수 없는 항목의 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="6862a-105">사용자가 항목 페이지에 표시하는 모든 정보(예: SharePoint 사이트, 문서, 파일)는 이미 볼 수 있는 정보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="6862a-106">Viva 항목은 기존 사용 권한을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="6862a-107">두 사용자가 동일한 항목에 대해 서로 다른 보기를 가지는 이유</span><span class="sxs-lookup"><span data-stu-id="6862a-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="6862a-108">AI 또는 수동 큐레이터를 통해 항목을 만들 때 항목에 대한 설명, 대체 이름, 항목과 연결된 사용자, 항목과 관련된 사이트, 페이지 및 파일에 대한 설명을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="6862a-109">항목 페이지에서 이 정보를 볼 때 동일한 항목을 보는 두 사용자가 동일한 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="6862a-110">예를 들어 사용자 1이 Neptune 항목 페이지를 볼 때 항목 페이지의 이 보기가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![사용자 1에 대한 Neptune 항목](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="6862a-112">그러나 사용자 2가 동일한 Neptune 항목 페이지를 보는 경우 보기는 사용자 1과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="6862a-113">사용자 2는 항목 페이지의 고정된 파일 및 페이지 섹션에서  사용자 1에 대해 나타나지 않는 *DG-2000* 제품 개요 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![사용자 2에 대한 Neptune 항목](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="6862a-115">사용자가 관련 사이트 또는 파일을 볼 수 있는 Office 365 권한이 없는 경우도 있기 때문에 동일한 항목에 사용자에게 표시될 수 있는 항목의 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="6862a-116">Viva Topics는 항목의 항목에 대해 설정된 사용 권한을 사용하며 해당 항목에 대한 액세스를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="6862a-117">이 예제에서는 사용자 1에 파일을 볼 수 있는 Office 365 권한이 있기 때문에 사용자 1이 Neptune의 항목 페이지에서 *DG-2000* 제품 개요 파일을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="6862a-118">사용자가 항목에 충분한 정보를 볼 수 없는 경우 해당 항목을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="6862a-119">이 경우 강조 표시된 항목은 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="6862a-120">유용하게 사용할 수 있도록 항목의 추가 정보에 대한 사용 권한이 있는 다른 사용자는 해당 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="6862a-121">지식 관리자 및 주제 참가자에 대한 항목 사용 권한</span><span class="sxs-lookup"><span data-stu-id="6862a-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="6862a-122">항목을 관리할 수 있는 권한이 할당된 사용자(기술 관리자)는 항목 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="6862a-123">마찬가지로 항목 작성 및 편집 권한(항목 참가자)은 주제 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="6862a-124">AI와 수동 큐레이터 항목 정보</span><span class="sxs-lookup"><span data-stu-id="6862a-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="6862a-125">항목에는 AI에서 생성된 정보와 항목 참가자 또는 지식 관리자가 추가하거나 편집한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="6862a-126">AI가 추가한 항목의 정보는 원본 콘텐츠에 액세스할 수 있는 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="6862a-127">항목 참가자 또는 기술 관리자가 수동으로 추가하거나 편집한 항목 설명 및 사용자 정보는 해당 항목을 볼 수 있는 모든 사람이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="6862a-128">파일, 페이지 및 사이트는 AI에서 수동으로 추가하거나 추가하는지 여부에 관계 없이 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="6862a-129">다음 표에서는 사용자의 사용 권한에 따라 특정 항목에서 볼 수 있는 사용자( 주제 뷰어, 참가자 및 기술 관리자)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="6862a-130">항목 항목</span><span class="sxs-lookup"><span data-stu-id="6862a-130">Topic item</span></span>|<span data-ttu-id="6862a-131">사용자에게 표시될 수 있는 것</span><span class="sxs-lookup"><span data-stu-id="6862a-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="6862a-132">항목 이름</span><span class="sxs-lookup"><span data-stu-id="6862a-132">Topic name</span></span>|<span data-ttu-id="6862a-133">사용자는 항목 센터에서 항목 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="6862a-134">사용자가 원본 콘텐츠에 대한 사용 권한이 없는 경우 또는 사용자에게 관련성이 낮은 경우 일부 항목은 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="6862a-135">항목 설명</span><span class="sxs-lookup"><span data-stu-id="6862a-135">Topic description</span></span>|<span data-ttu-id="6862a-136">AI 생성 설명은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="6862a-137">수동으로 입력하거나 편집한 설명은 모든 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="6862a-138">사용자</span><span class="sxs-lookup"><span data-stu-id="6862a-138">People</span></span>|<span data-ttu-id="6862a-139">고정된 사용자는 모든 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="6862a-140">제안된 사용자는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="6862a-141">파일</span><span class="sxs-lookup"><span data-stu-id="6862a-141">Files</span></span>|<span data-ttu-id="6862a-142">파일은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="6862a-143">페이지</span><span class="sxs-lookup"><span data-stu-id="6862a-143">Pages</span></span>|<span data-ttu-id="6862a-144">페이지는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="6862a-145">사이트</span><span class="sxs-lookup"><span data-stu-id="6862a-145">Sites</span></span>|<span data-ttu-id="6862a-146">사이트는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6862a-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="6862a-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6862a-147">See also</span></span>


---
title: Microsoft Viva Topics 보안 트리밍
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
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107521"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="d2c6f-103">Microsoft Viva Topics 보안 트리밍</span><span class="sxs-lookup"><span data-stu-id="d2c6f-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="d2c6f-104">Viva Topics 사용자는 기존 Office 365 권한으로 인해 사용자가 볼 수 없는 항목의 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="d2c6f-105">사용자가 항목 페이지에 표시하는 모든 항목(예: SharePoint 사이트, 문서, 파일)은 이미 볼 수 있는 정보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="d2c6f-106">Viva Topics는 기존 사용 권한을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="d2c6f-107">두 사용자가 동일한 항목에 대해 서로 다른 보기를 사용할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="d2c6f-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="d2c6f-108">AI 또는 수동 큐레이터를 통해 항목을 만들 때 항목에 대한 설명, 대체 이름, 항목과 관련된 사용자, 해당 항목과 관련된 사이트, 페이지 및 파일에 대한 설명이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="d2c6f-109">이 정보를 항목 페이지에서 볼 때 동일한 항목을 보는 두 사용자가 동일한 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="d2c6f-110">예를 들어 사용자 1이 Neptune 항목 페이지를 볼 때 항목 페이지의 이 보기가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![사용자 1에 대한 Neptune 항목](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="d2c6f-112">그러나 사용자 2가 동일한 Neptune 항목 페이지를 보는 경우 해당 보기는 사용자 1과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="d2c6f-113">사용자 2는 항목 페이지의 고정된 파일 및 페이지 섹션에서  사용자 1에 대해 나타나지 않는 *DG-2000* 제품 개요 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![사용자 2에 대한 Neptune 항목](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="d2c6f-115">사용자가 관련 사이트 또는 파일을 볼 수 있는 Office 365 권한이 없는 경우도 있기 때문에 동일한 항목에 대해 사용자에게 표시될 수 있는 항목의 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="d2c6f-116">Viva Topics는 항목의 항목에 대해 설정된 사용 권한을 사용하며 해당 항목에 대한 액세스를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="d2c6f-117">이 예제에서는 사용자 1에 파일을 볼 수 있는 Office 365 권한이 있기 때문에 사용자 1은 Neptune의 항목 페이지에서 *DG-2000* 제품 개요 파일을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="d2c6f-118">사용자가 유용하게 사용할 수 있도록 항목에 충분한 정보를 볼 수 없는 경우 해당 항목을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="d2c6f-119">이 경우 사용자에게 강조 표시된 항목은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="d2c6f-120">유용하게 사용할 수 있도록 항목의 추가 정보에 대한 사용 권한이 있는 다른 사용자가 해당 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="d2c6f-121">지식 관리자 및 주제 참가자에 대한 항목 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d2c6f-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="d2c6f-122">항목을 관리할 수 있는 권한이 할당된 사용자(기술 관리자)는 항목 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="d2c6f-123">마찬가지로 항목 작성 및 편집 권한(항목 참가자)은 항목 내에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="d2c6f-124">AI와 수동 큐레이터 항목 정보</span><span class="sxs-lookup"><span data-stu-id="d2c6f-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="d2c6f-125">항목에는 AI에서 생성된 정보와 항목 참가자 또는 지식 관리자가 추가하거나 편집한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="d2c6f-126">AI에서 추가한 항목의 정보는 원본 콘텐츠에 액세스할 수 있는 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="d2c6f-127">항목 작성자 또는 지식 관리자가 수동으로 추가하거나 편집한 정보는 해당 항목을 볼 수 있는 모든 사람이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="d2c6f-128">다음 표에서는 사용자(주제 뷰어, 참가자 및 지식 관리자)가 사용 권한에 따라 특정 항목에서 볼 수 있는 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="d2c6f-129">항목 항목</span><span class="sxs-lookup"><span data-stu-id="d2c6f-129">Topic item</span></span>|<span data-ttu-id="d2c6f-130">사용자에게 표시될 수 있는 것</span><span class="sxs-lookup"><span data-stu-id="d2c6f-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="d2c6f-131">항목 이름</span><span class="sxs-lookup"><span data-stu-id="d2c6f-131">Topic name</span></span>|<span data-ttu-id="d2c6f-132">사용자는 항목 센터에서 모든 항목의 항목 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="d2c6f-133">사용자에게 관련성 수준이 낮은 경우 일부 항목은 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="d2c6f-134">항목 설명</span><span class="sxs-lookup"><span data-stu-id="d2c6f-134">Topic description</span></span>|<span data-ttu-id="d2c6f-135">AI 생성 설명은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="d2c6f-136">수동으로 입력하거나 편집한 설명은 모든 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="d2c6f-137">사용자</span><span class="sxs-lookup"><span data-stu-id="d2c6f-137">People</span></span>|<span data-ttu-id="d2c6f-138">고정된 사용자는 모든 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="d2c6f-139">제안된 사용자는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="d2c6f-140">파일</span><span class="sxs-lookup"><span data-stu-id="d2c6f-140">Files</span></span>|<span data-ttu-id="d2c6f-141">파일은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="d2c6f-142">페이지</span><span class="sxs-lookup"><span data-stu-id="d2c6f-142">Pages</span></span>|<span data-ttu-id="d2c6f-143">페이지는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="d2c6f-144">사이트</span><span class="sxs-lookup"><span data-stu-id="d2c6f-144">Sites</span></span>|<span data-ttu-id="d2c6f-145">사이트는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="d2c6f-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2c6f-146">See also</span></span>


---
title: '항목 센터의 항목에 대 한 작업 (미리 보기) '
description: 항목 센터의 항목을 사용 하 여 작업 하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: d2fd3df200ab350ca3e6595402bab17034d960a7
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906922"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a><span data-ttu-id="8f898-103">항목 센터의 항목에 대 한 작업 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="8f898-103">Work with topics in the topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="8f898-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="8f898-105">[Project Cortex](https://aka.ms/projectcortex)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8f898-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="8f898-106">기술 자료 관리자는 항목 센터에서 지정한 SharePoint 원본 위치에서 검색 하 고 찾은 항목을 검토 하 고이를 확인 하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-106">In the topic center, a knowledge manager can review topics that have been mined and discovered in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="8f898-107">또한 기술 관리자가 항목 검색에서 새 항목 페이지를 만들거나 업데이트 해야 하는 경우에는이를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-107">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f898-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f898-108">Requirements</span></span>

<span data-ttu-id="8f898-109">항목 센터에서 작업 하려면 필요한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-109">In order to work in the topic center, you need to have the required permissions.</span></span> <span data-ttu-id="8f898-110">관리자는 [지식 관리 설치](set-up-knowledge-network.md)중에 사용자를 추가 하거나 [나중](give-user-permissions-to-the-topic-center.md)에 새 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-110">Your admin can add you during [knowledge management setup](set-up-knowledge-network.md), or new users can be [added afterwards](give-user-permissions-to-the-topic-center.md).</span></span>

<span data-ttu-id="8f898-111">항목 센터 사용자에 게는 다음과 같은 두 가지 권한 집합이 제공 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-111">Topic center users can be given two sets of permissions:</span></span>

- <span data-ttu-id="8f898-112">항목 만들기 및 편집: 새 항목을 만들거나 설명, 문서 및 관련 사용자와 같은 항목 콘텐츠를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-112">Create and edit topics: Create new topics or update topic content such as the description, documents and associated persons.</span></span>

- <span data-ttu-id="8f898-113">항목 관리: 관리 대시보드를 사용 하 여 조직 전체의 항목을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-113">Manage topics: Use the Topic management dashboard to review topics across the organization.</span></span> <span data-ttu-id="8f898-114">사용자는 확인 및 거부 항목과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-114">Users can perform actions such as confirm and reject topics.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="8f898-115">제안 항목 검토</span><span class="sxs-lookup"><span data-stu-id="8f898-115">Review suggested topics</span></span>

<span data-ttu-id="8f898-116">항목 센터 홈 페이지에서 지정한 SharePoint 원본 위치에서 검색 된 항목이 **제안** 된 탭에 나열 됩니다. 항목 관리 권한이 있는 사용자는 확인 되지 않은 항목을 검토 하 고이를 선택 하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-116">On the topic center home page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A user with permissions to manage topics can review unconfirmed topics and choose to confirm or reject them.</span></span>


<span data-ttu-id="8f898-117">추천 항목을 검토 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-117">To review a suggested topic:</span></span>

1. <span data-ttu-id="8f898-118">**제안** 된 탭에서 항목 페이지를 여는 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-118">On the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="8f898-119">항목 페이지에서 항목 페이지를 검토 하 고 페이지를 변경 해야 하는 경우 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-119">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="8f898-120">정보 센터 홈 페이지에서 선택한 항목에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-120">On the Knowledge Center home page, for the selected topic, you can:</span></span>

    1. <span data-ttu-id="8f898-121">항목을 유지할지 여부를 확인 하는 확인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-121">Select the check to confirm that you want to keep the topic.</span></span>
    
    1. <span data-ttu-id="8f898-122">**X** 를 선택 하 여 항목을 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-122">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="8f898-123">**확정 된 항목이** 확인 되지 않은 목록에서 제거 되며 이제 **확인** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-123">Confirmed topics will be removed from the **Unconfirmed** list and will now display in the **Confirmed** tab.</span></span>

    <span data-ttu-id="8f898-124">거부 됨 항목이 **확정** 되지 않은 목록에서 제거 되며 이제 **거부 또는 제외** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-124">Rejected topics will be removed from the **Unconfirmed** list and will now display in the **Rejected or Excluded** tab.</span></span>

## <a name="review-confirmed-topics"></a><span data-ttu-id="8f898-125">확인 된 항목 검토</span><span class="sxs-lookup"><span data-stu-id="8f898-125">Review confirmed topics</span></span>

<span data-ttu-id="8f898-126">항목 센터 홈 페이지에서 지정 된 SharePoint 원본 위치에서 검색 되 고, 고객에 게 카드 피드백 메커니즘을 통해 2 명 이상의 사용자가 확인 한 crowdsourced에 따라 확인 된 항목이 **확인** 탭에 나열 됩니다. 항목 관리 권한이 있는 사용자는 확인 된 항목을 검토 하 고 거부 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-126">On the topic center home page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowlege manager or crowdsourced confirmed by 2 or more people through the card feedback mechanism will be listed in the **Confirmed** tab. A user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>


<span data-ttu-id="8f898-127">확인 된 항목을 검토 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-127">To review a confirmed topic:</span></span>

1. <span data-ttu-id="8f898-128">**확정** 탭에서 항목 페이지를 여는 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-128">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="8f898-129">항목 페이지에서 항목 페이지를 검토 하 고 페이지를 변경 해야 하는 경우 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-129">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="8f898-130">이를 거부 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-130">You can reject it too</span></span>

## <a name="review-published-topics"></a><span data-ttu-id="8f898-131">게시 된 항목 검토</span><span class="sxs-lookup"><span data-stu-id="8f898-131">Review published topics</span></span>
<span data-ttu-id="8f898-132">게시 된 항목은 페이지를 encountrs 하는 사람에 게 항상 표시 되는 speific 정보를 편집 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-132">Published topics have been edited so that speific information will always appear to whoever encountrs the page.</span></span> <span data-ttu-id="8f898-133">수동으로 만든 항목은 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-133">Manually created topics show here.</span></span>

   
## <a name="create-a-new-topic"></a><span data-ttu-id="8f898-134">새 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="8f898-134">Create a new topic</span></span>

<span data-ttu-id="8f898-135">항목 만들기 또는 편집 권한이 있는 사용자는 필요한 경우 새 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-135">A user with create or edit topic permissions can create a new topic if needed.</span></span> <span data-ttu-id="8f898-136">항목이 검색을 통해 검색 되지 않거나 인공 지능 기술에서이를 항목으로 설정 하기에 충분 한 증거를 찾지 못한 경우이 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-136">You might need to do this if the topic was not discovered through discovery or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

<span data-ttu-id="8f898-137">새 항목을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-137">To create a new topic:</span></span>

1. <span data-ttu-id="8f898-138">항목 센터 페이지에서 **새로 만들기** 를 선택한 다음 **항목 페이지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-138">On the topic center page, select **New** , then select **Topic Page**.</span></span>

    ![새 항목](../media/content-understanding/k-new-topic.png)

2. <span data-ttu-id="8f898-140">새 항목 페이지에서 새 항목 서식 파일에 대 한 정보를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-140">On the new topic page, you can fill in the information on the new topic template:</span></span>

    1. <span data-ttu-id="8f898-141">**이 항목의 이름** 섹션에서 새 항목의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-141">In the **Name this topic** section, type the name of the new topic.</span></span>
    
    1. <span data-ttu-id="8f898-142">**대체 이름** 섹션에서 항목을 참조 하는 데 사용 되는 이름 또는 머리글자어를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-142">In the **Alternate names** section, type names or acronyms that are also used to refer to the topic.</span></span>
    
    1. <span data-ttu-id="8f898-143">**간단한 설명** 섹션에서 항목에 대 한 한 가지 또는 두 개의 문장의 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-143">In the **Short description** section, type a one or two sentence description of the topic.</span></span> <span data-ttu-id="8f898-144">이 텍스트는 연결 된 항목 카드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-144">This text will be used for the associated topic card.</span></span>
    
    1. <span data-ttu-id="8f898-145">**사용자** 섹션에서 해당 항목에 대 한 주제별 전문가의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-145">In the **People** section, type the names of subject matter experts for the topic.</span></span>
    
    1. <span data-ttu-id="8f898-146">**파일 및 페이지** 섹션에서 **추가** 를 선택 하 고 다음 페이지에서 연결 된 OneDrive 파일 또는 SharePoint Online 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-146">In the **Files and pages** section, select **Add** and then on the next page you can select associated OneDrive files or SharePoint Online pages.</span></span>
    
    1. <span data-ttu-id="8f898-147">**사이트** 섹션에서 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-147">In the **Sites** section, select **Add**.</span></span> <span data-ttu-id="8f898-148">표시 되는  **사이트** 창에서 항목에 연결 된 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-148">In the  **Sites** pane that displays, select the sites that are associated to the topic.</span></span>

    ![새 항목 페이지](../media/content-understanding/k-new-topic-page.png)
    
3. <span data-ttu-id="8f898-150">페이지에 텍스트, 이미지, 웹 파트, 링크 등의 다른 구성 요소를 추가 해야 하는 경우 페이지 가운데에서 캔버스 아이콘을 선택 하 여 셰이프를 찾아서 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-150">If you need to add other components to the page, such as text, images, webparts, links, etc., select the canvas icon in the middle of the page to locate and add them.</span></span>

    ![페이지에 항목 추가](../media/content-understanding/static-icon.png)

4. <span data-ttu-id="8f898-152">작업을 마치면 **게시** 를 선택 하 여 항목 페이지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-152">When you are done, select **Publish** to publish the topic page.</span></span> <span data-ttu-id="8f898-153">게시 된 항목 페이지는 **페이지** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-153">Published topic pages will display in the **Pages** tab.</span></span>

> [!Note] 
> <span data-ttu-id="8f898-154">새 항목 페이지는 *기술 네트워크를 인식* 하는 웹 파트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-154">The new topic page is made up of web parts that are *knowledge network aware*.</span></span> <span data-ttu-id="8f898-155">즉, AI에서 항목에 대 한 추가 정보를 수집 하는 경우 이러한 웹 파트의 정보가 사용자에 게 더 유용한 페이지를 만들기 위한 제안으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-155">This means that as AI gathers more information on the topic, the information in these web parts will be updated with suggestions to make the page more useful to users.</span></span>


## <a name="edit-an-existing-topic-page"></a><span data-ttu-id="8f898-156">기존 항목 페이지 편집</span><span class="sxs-lookup"><span data-stu-id="8f898-156">Edit an existing topic page</span></span>

<span data-ttu-id="8f898-157">기존 항목 페이지는 **페이지** 페이지에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-157">Existing topic pages can be found in the **Pages** page.</span></span> 

1. <span data-ttu-id="8f898-158">항목 센터 페이지에서 **페이지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-158">On the Topic Center page, select **Pages**.</span></span>

2. <span data-ttu-id="8f898-159">**페이지** 페이지에 항목 페이지 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-159">On the **Pages** page, you will see a list of topic pages.</span></span> <span data-ttu-id="8f898-160">검색 상자를 사용 하 여 업데이트할 항목 페이지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-160">Use the Search box to find the topic page you want to update.</span></span> <span data-ttu-id="8f898-161">편집 하려는 항목 페이지의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-161">Click on the name of the topic page that you want to edit.</span></span>

3. <span data-ttu-id="8f898-162">항목 페이지에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-162">On the topic page, select **Edit**.</span></span>

4. <span data-ttu-id="8f898-163">페이지에 필요한 사항을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-163">Make the changes you need to the page.</span></span> <span data-ttu-id="8f898-164">여기에는 다음 필드에 대 한 업데이트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-164">This includes updates to the following fields:</span></span>

    1. <span data-ttu-id="8f898-165">대체 이름</span><span class="sxs-lookup"><span data-stu-id="8f898-165">Alternate names</span></span>
    1. <span data-ttu-id="8f898-166">설명</span><span class="sxs-lookup"><span data-stu-id="8f898-166">Description</span></span>
    1. <span data-ttu-id="8f898-167">사람</span><span class="sxs-lookup"><span data-stu-id="8f898-167">People</span></span>
    1. <span data-ttu-id="8f898-168">파일 및 페이지</span><span class="sxs-lookup"><span data-stu-id="8f898-168">Files and pages</span></span>
    1. <span data-ttu-id="8f898-169">사이트</span><span class="sxs-lookup"><span data-stu-id="8f898-169">Sites</span></span>
    1. <span data-ttu-id="8f898-170">캔버스 아이콘을 선택 하 여 텍스트, 이미지 또는 링크와 같은 정적 항목을 페이지에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-170">You can also add static items to the page—such as text, images, or link—by selecting the canvas icon.</span></span>

5. <span data-ttu-id="8f898-171">다시 **게시** 를 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f898-171">Select **Republish** to save your changes.</span></span>

<!--## See also-->



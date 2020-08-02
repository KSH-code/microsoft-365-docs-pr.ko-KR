---
title: '지식 관리 네트워크 관리 (미리 보기) '
description: 지식 관리를 설정 하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540121"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="c71bf-103">지식 관리 네트워크 관리 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="c71bf-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c71bf-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c71bf-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="c71bf-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="c71bf-106">[지식 관리를 설정한](set-up-knowledge-network.md)후에는 언제 든 지 관리자가 Microsoft 365 관리 센터를 통해 구성 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="c71bf-107">예를 들어 다음 중 하나에 대 한 설정을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="c71bf-108">항목을 광산에 새 SharePoint 원본을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="c71bf-109">항목에 액세스할 사용자를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="c71bf-110">항목 센터에서 작업을 수행할 수 있는 권한이 있는 사용자를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="c71bf-111">주제 센터 이름 변경</span><span class="sxs-lookup"><span data-stu-id="c71bf-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="c71bf-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c71bf-112">Requirements</span></span> 
<span data-ttu-id="c71bf-113">Microsoft 365 관리 센터에 액세스 하 고 조직의 기술 자료 작업을 관리 하려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="c71bf-114">기술 항목 관리 설정에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="c71bf-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="c71bf-115">Microsoft 365 관리 센터에서 **설치**를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="c71bf-116">**조직의 기술 자료** 섹션에서 **사용자에 게 자세한 정보 연결을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![전문 지식을 사용자에 게 연결](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="c71bf-118">**사용자에 게 정보 연결** 페이지에서 **관리** 를 선택 하 여 **정보 네트워크 설정** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![지식-네트워크-설정](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="c71bf-120">지식 네트워크에서 항목을 찾을 수 있는 방식 변경</span><span class="sxs-lookup"><span data-stu-id="c71bf-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="c71bf-121">SharePoint 항목 원본에 대 한 선택 사항을 업데이트 하려면 **항목 검색** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="c71bf-122">이 설정을 사용 하 여 테 넌 트에서 크롤링할 SharePoint 사이트를 선택 하 고 항목에 대 한 의견을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="c71bf-123">**항목 검색** 탭의 **SharePoint 항목 소스 선택**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="c71bf-124">**Sharepoint 항목 원본 선택** 페이지에서 검색 중에 항목의 소스로 크롤링할 SharePoint 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="c71bf-125">해당 활동은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-125">This includes:</span></span></br>
    <span data-ttu-id="c71bf-126">a.</span><span class="sxs-lookup"><span data-stu-id="c71bf-126">a.</span></span> <span data-ttu-id="c71bf-127">**모든 사이트**: 테 넌 트의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="c71bf-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="c71bf-128">현재 및 미래의 사이트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="c71bf-129">b.</span><span class="sxs-lookup"><span data-stu-id="c71bf-129">b.</span></span> <span data-ttu-id="c71bf-130">**선택한 사이트를 제외한 모두 (모두**): 제외 하려는 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="c71bf-131">검색에서 옵트아웃 할 사이트의 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="c71bf-132">앞으로 만들어진 사이트는 항목 검색의 원본으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="c71bf-133">c.</span><span class="sxs-lookup"><span data-stu-id="c71bf-133">c.</span></span> <span data-ttu-id="c71bf-134">**선택한 사이트만**: 포함 하려는 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="c71bf-135">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-135">You can also upload a list of sites.</span></span> <span data-ttu-id="c71bf-136">앞에서 만든 사이트는 항목 검색의 원본으로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![항목 검색 방법 선택](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="c71bf-138">제외할 사이트가 여러 개 있는 경우 ( **모두, 선택한 사이트를 제외 하 고 모두**선택) 또는 포함 ( **선택한 사이트만**선택한 경우)을 선택 하 고 사이트 이름과 url을 사용 하 여 CSV 파일을 업로드 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="c71bf-139">CSV 서식 파일을 사용 하려는 경우에는 **사이트 서식 파일인 .Csv 다운로드** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="c71bf-140">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="c71bf-141">조직의 항목을 볼 수 있는 사람 변경</span><span class="sxs-lookup"><span data-stu-id="c71bf-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="c71bf-142">조직에서 검색 결과의 검색 된 항목을 볼 수 있는 사용자를 업데이트 하 고 SharePoint 페이지와 같은 콘텐츠에서 항목을 강조 표시 하려면 **항목 검색** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="c71bf-143">**항목 검색** 탭의 **사용자가 정보 네트워크의 항목을 볼 수 있는 사람**아래에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="c71bf-144">**정보 네트워크 페이지의 항목을 볼 수 있는 사용자** 는 강조 표시 된 항목, 항목 카드, 검색의 항목 대답 및 주제 페이지와 같은 항목 세부 정보에 액세스할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="c71bf-145">다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-145">You can select:</span></span></br>
    <span data-ttu-id="c71bf-146">a.</span><span class="sxs-lookup"><span data-stu-id="c71bf-146">a.</span></span> <span data-ttu-id="c71bf-147">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="c71bf-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c71bf-148">b.</span><span class="sxs-lookup"><span data-stu-id="c71bf-148">b.</span></span> <span data-ttu-id="c71bf-149">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="c71bf-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="c71bf-150">c.</span><span class="sxs-lookup"><span data-stu-id="c71bf-150">c.</span></span> <span data-ttu-id="c71bf-151">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="c71bf-151">**No one**</span></span></br>

    ![항목을 볼 수 있는 사람](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="c71bf-153">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="c71bf-154">이 설정을 사용 하면 조직의 모든 사용자를 선택할 수 있지만, 기술 관리 라이선스가 할당 된 사용자만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="c71bf-155">항목 센터에서 작업을 수행할 수 있는 권한이 있는 사용자 변경</span><span class="sxs-lookup"><span data-stu-id="c71bf-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="c71bf-156">항목 센터 페이지에서 다음 작업을 수행할 수 있는 권한이 있는 사용자를 업데이트 하려면 **항목 사용 권한** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="c71bf-157">항목을 만들고 편집할 수 있는 사용자: 검색 하는 동안 발견 되지 않은 새 항목을 만들거나 기존 항목 페이지 세부 정보를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="c71bf-158">항목을 관리할 수 있는 사용자: 검색 된 항목 확인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="c71bf-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="c71bf-159">항목을 만들고 편집할 수 있는 권한이 있는 사용자를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="c71bf-160">**항목 권한** 탭의 **항목을 만들고 편집할 수 있는 사용자는 누구 입니까**?에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="c71bf-161">주제를 **만들고 편집할 수 있는 사람** 페이지에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="c71bf-162">a.</span><span class="sxs-lookup"><span data-stu-id="c71bf-162">a.</span></span> <span data-ttu-id="c71bf-163">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="c71bf-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c71bf-164">b.</span><span class="sxs-lookup"><span data-stu-id="c71bf-164">b.</span></span> <span data-ttu-id="c71bf-165">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="c71bf-165">**Only selected people or security groups**</span></span></br>

    ![항목 만들기 및 편집](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="c71bf-167">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-167">Select **Save**.</span></span></br>

<span data-ttu-id="c71bf-168">항목을 관리할 수 있는 권한이 있는 사용자를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="c71bf-169">**항목 권한** 탭의 **항목을 관리할 수 있는 사용자**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="c71bf-170">주제를 **관리할 수 있는 사람** 페이지에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="c71bf-171">a.</span><span class="sxs-lookup"><span data-stu-id="c71bf-171">a.</span></span> <span data-ttu-id="c71bf-172">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="c71bf-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c71bf-173">b.</span><span class="sxs-lookup"><span data-stu-id="c71bf-173">b.</span></span> <span data-ttu-id="c71bf-174">**선택한 사용자 또는 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="c71bf-174">**Selected people or security groups**</span></span></br>

    ![항목 관리](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="c71bf-176">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="c71bf-177">항목 센터 이름 업데이트</span><span class="sxs-lookup"><span data-stu-id="c71bf-177">Update your topic center name</span></span>

<span data-ttu-id="c71bf-178">항목 센터의 이름을 업데이트 하려면 **항목 가운데** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="c71bf-179">**항목 가운데** 탭의 **항목 센터 이름**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="c71bf-180">**항목 센터 이름 편집** 페이지의 **항목 센터 이름** 상자에 항목 센터의 새 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="c71bf-181">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c71bf-181">Select **Save**</span></span>

    ![항목 센터 이름 편집](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="c71bf-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c71bf-183">See also</span></span>



  







---
title: '지식 관리 설정 (미리 보기) '
description: 지식 관리를 설정 하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540133"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="c51d5-103">지식 관리 설정 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="c51d5-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c51d5-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c51d5-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="c51d5-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c51d5-106">Microsoft 365 관리 센터를 사용 하 여 [기술 자료 관리](knowledge-management-overview.md)를 설정 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="c51d5-107">환경에서 기술 관리를 설정 하 고 구성 하는 최상의 방법을 계획 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="c51d5-108">예를 들어 다음과 같은 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="c51d5-109">항목에 대해 분석할 SharePoint 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="c51d5-110">항목을 볼 수 있도록 할 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="c51d5-111">항목 센터에서 항목을 관리 하기 위한 권한을 부여할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="c51d5-112">항목 센터에서 항목을 만들거나 편집할 수 있는 권한을 부여할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="c51d5-113">주제 센터에 제공 하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="c51d5-114">항목을 보고, 항목을 관리 하 고, 항목을 만들고 편집 하는 데 필요한 사용 권한을 사용자에 게 할당 하는 보안 그룹을 만드는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="c51d5-115">관리자는 설치 후 Microsoft 365 관리 센터에서 기술 관리 설정을 통해 [언제 든 지 선택한 설정을 변경할](manage-knowledge-network.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="c51d5-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c51d5-116">Requirements</span></span> 
<span data-ttu-id="c51d5-117">Microsoft 365 관리 센터에 액세스 하 고 조직의 기술 자료 작업을 설정 하려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="c51d5-118">지식 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="c51d5-118">Set up your knowledge network</span></span>

<span data-ttu-id="c51d5-119">기술 자료 네트워크를 설정 하면 다음과 같은 과정을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="c51d5-120">검색 항목: 검색에서 제외할 항목 원본 및 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="c51d5-121">항목 표시 유형: 검색 및 항목 페이지에서 항목을 강조 표시로 볼 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="c51d5-122">항목 사용 권한: 항목을 작성, 편집 및 관리할 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="c51d5-123">항목 센터: 주제 센터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="c51d5-124">검토: 설정을 확인 하 고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="c51d5-125">지식 네트워크를 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="c51d5-126">Microsoft 365 관리 센터 (admin.microsoft.com)에서 **설치**를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="c51d5-127">**조직의 기술 자료** 섹션에서 **사용자에 게 자세한 정보 연결을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![전문 지식을 사용자에 게 연결](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="c51d5-129">**사용자에 게 정보 연결** 페이지에서 **시작** 을 클릭 하 여 설치 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![시작하기](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="c51d5-131">**기술 네트워크에서 항목을 찾을 수 있는 방법 선택** 페이지에서 항목 검색을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="c51d5-132">**Sharepoint 항목 원본 선택** 섹션에서 검색 중에 항목의 소스로 크롤링할 SharePoint 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="c51d5-133">해당 활동은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-133">This includes:</span></span></br>
    <span data-ttu-id="c51d5-134">a.</span><span class="sxs-lookup"><span data-stu-id="c51d5-134">a.</span></span> <span data-ttu-id="c51d5-135">**모든 사이트**: 테 넌 트의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="c51d5-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="c51d5-136">현재 및 미래의 사이트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="c51d5-137">b.</span><span class="sxs-lookup"><span data-stu-id="c51d5-137">b.</span></span> <span data-ttu-id="c51d5-138">**선택한 사이트를 제외한 모두 (모두**): 제외 하려는 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="c51d5-139">검색에서 옵트아웃 하려는 사이트의 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="c51d5-140">이후에 만들어진 사이트는 항목 검색의 원본으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="c51d5-141">c.</span><span class="sxs-lookup"><span data-stu-id="c51d5-141">c.</span></span> <span data-ttu-id="c51d5-142">**선택한 사이트만**: 포함 하려는 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="c51d5-143">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-143">You can also upload a list of sites.</span></span> <span data-ttu-id="c51d5-144">앞에서 만든 사이트는 항목 검색의 원본으로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![항목 검색 방법 선택](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="c51d5-146">**이름으로 항목 제외** 섹션에서 검색 된 결과에 포함 하지 않을 항목의 이름을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="c51d5-147">이 설정을 사용 하 여 중요 한 항목이 지식 네트워크의 일부로 포함 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="c51d5-148">다음과 같은 옵션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-148">Your options include:</span></span></br>
    <span data-ttu-id="c51d5-149">a.</span><span class="sxs-lookup"><span data-stu-id="c51d5-149">a.</span></span> <span data-ttu-id="c51d5-150">**항목을 제외 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="c51d5-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="c51d5-151">b.</span><span class="sxs-lookup"><span data-stu-id="c51d5-151">b.</span></span> <span data-ttu-id="c51d5-152">다음 **단어가 포함 된 제외 항목**: 사용자에 게 정보를 표시 하지 않으려는 항목이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c51d5-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="c51d5-153">-제공 된 서식 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-153">- Download the provided template.</span></span>
   <span data-ttu-id="c51d5-154">-제외 하려는 항목 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="c51d5-155">일치 유형을 정확히 또는 부분으로 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="c51d5-156">정확 하 게 일치는 용어에 적합 한 항목을 제외 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="c51d5-157">부분 일치는 보다 엄격 하며 용어를 포함 하는 항목이 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="c51d5-158">예를 들어 항목 이름으로 *doc* 를 입력 하면 *Docker* 가 아닌 동안 *doc 어셈블리가* 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="c51d5-159">항목 이름은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="c51d5-160">-  **+**   완성 된 CSV 파일을 가져오려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="c51d5-161">그런 다음 **업로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-161">Then select **Upload**.</span></span> <span data-ttu-id="c51d5-162">파일을 성공적으로 처리 한 경우 녹색 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="c51d5-163">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="c51d5-164">**주제 및 항목을 볼 수 있는 위치를 볼 수 있는 사용자** 는 항목 표시 여부를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="c51d5-165">**정보 네트워크 설정의 항목을 볼 수 있는 사용자** 는 강조 표시 된 항목, 항목 카드, 검색의 항목 대답 및 주제 페이지와 같은 항목 세부 정보에 대 한 액세스 권한을 부여할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="c51d5-166">다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-166">You can select:</span></span></br>
    <span data-ttu-id="c51d5-167">a.</span><span class="sxs-lookup"><span data-stu-id="c51d5-167">a.</span></span> <span data-ttu-id="c51d5-168">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="c51d5-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c51d5-169">b.</span><span class="sxs-lookup"><span data-stu-id="c51d5-169">b.</span></span> <span data-ttu-id="c51d5-170">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="c51d5-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="c51d5-171">c.</span><span class="sxs-lookup"><span data-stu-id="c51d5-171">c.</span></span> <span data-ttu-id="c51d5-172">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="c51d5-172">**No one**</span></span></br>

    ![항목을 볼 수 있는 사람](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="c51d5-174">이 설정을 사용 하면 조직의 모든 사용자를 선택할 수 있지만, 기술 관리 라이선스가 할당 된 사용자만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="c51d5-175">**항목 관리에 대 한 사용 권한** 페이지에서 항목을 만들거나 편집 하거나 관리할 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="c51d5-176">항목을 **만들고 편집할 수 있는 사용자** 섹션에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="c51d5-177">a.</span><span class="sxs-lookup"><span data-stu-id="c51d5-177">a.</span></span> <span data-ttu-id="c51d5-178">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="c51d5-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c51d5-179">b.</span><span class="sxs-lookup"><span data-stu-id="c51d5-179">b.</span></span> <span data-ttu-id="c51d5-180">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="c51d5-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="c51d5-181">항목을 **관리할 수 있는 사용자** 섹션에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="c51d5-182">a.</span><span class="sxs-lookup"><span data-stu-id="c51d5-182">a.</span></span> <span data-ttu-id="c51d5-183">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="c51d5-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c51d5-184">b.</span><span class="sxs-lookup"><span data-stu-id="c51d5-184">b.</span></span> <span data-ttu-id="c51d5-185">**선택한 사용자 또는 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="c51d5-185">**Selected people or security groups**</span></span></br>

    ![항목 관리에 대 한 사용 권한](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="c51d5-187">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="c51d5-188">**주제 센터 만들기** 페이지에서 항목 페이지를 볼 수 있고 항목을 관리할 수 있는 주제 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="c51d5-189">**항목 센터 이름** 상자에 주제 센터의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="c51d5-190">원하는 경우 **사이트 설명** 상자에 간단한 설명을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="c51d5-191">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-191">Select **Next**.</span></span></br>

   ![정보 센터 만들기](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="c51d5-193">**검토 및 마침** 페이지에서 선택한 설정을 확인 하 고 변경 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="c51d5-194">선택에 만족 하면 **활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![완료 및 검토](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="c51d5-196">이제 시스템에서 항목에 대 한 선택 된 사이트의 분석을 시작 하 고 정보 센터 사이트를 만들기 시작할 것인지 묻는 **기술 네트워크 활성화** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="c51d5-197">**완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-197">Select **Done**.</span></span></br>

    ![활성화](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="c51d5-199">**사용자에 게 정보를 연결** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="c51d5-200">이 페이지에서 **관리** 를 선택 하 여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![적용 되는 설정](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="c51d5-202">설치가 완료 되 면 관리자는이 페이지로 돌아와 언제 든 지 [선택한 기술 관리 설정을 변경할](manage-knowledge-network.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51d5-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="c51d5-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c51d5-203">See also</span></span>



  







---
title: '지식 관리 설정 (미리 보기) '
description: 지식 관리를 설정 하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989002"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="a0a3b-103">지식 관리 설정 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a0a3b-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="a0a3b-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="a0a3b-105">[Project Cortex](https://aka.ms/projectcortex)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="a0a3b-106">Microsoft 365 관리 센터를 사용 하 여 [기술 자료 관리](knowledge-management-overview.md)를 설정 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="a0a3b-107">환경에서 기술 관리를 설정 하 고 구성 하는 최상의 방법을 계획 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="a0a3b-108">예를 들어 다음과 같은 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="a0a3b-109">항목에 대해 분석할 SharePoint 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="a0a3b-110">항목을 볼 수 있도록 할 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="a0a3b-111">항목 센터에서 항목을 관리 하기 위한 권한을 부여할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="a0a3b-112">항목 센터에서 항목을 만들거나 편집할 수 있는 권한을 부여할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="a0a3b-113">주제 센터에 제공 하려는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="a0a3b-114">항목을 보고, 항목을 관리 하 고, 항목을 만들고 편집 하는 데 필요한 사용 권한을 사용자에 게 할당 하는 보안 그룹을 만드는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="a0a3b-115">관리자는 설치 후 Microsoft 365 관리 센터에서 기술 관리 설정을 통해 [언제 든 지 선택한 설정을 변경할](topic-experiences-discovery.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0a3b-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0a3b-116">Requirements</span></span> 
<span data-ttu-id="a0a3b-117">Microsoft 365 관리 센터에 액세스 하 고 조직의 기술 자료 작업을 설정 하려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="a0a3b-118">지식 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="a0a3b-118">Set up your knowledge network</span></span>

<span data-ttu-id="a0a3b-119">기술 자료 네트워크를 설정 하면 다음과 같은 과정을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="a0a3b-120">검색 항목: 검색에서 제외할 항목 원본 및 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="a0a3b-121">항목 표시 유형: 검색 및 항목 페이지에서 항목을 강조 표시로 볼 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="a0a3b-122">항목 사용 권한: 항목을 작성, 편집 및 관리할 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="a0a3b-123">항목 센터: 주제 센터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="a0a3b-124">검토: 설정을 확인 하 고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="a0a3b-125">지식 네트워크를 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="a0a3b-126">Microsoft 365 관리 센터 (admin.microsoft.com)에서 **설치** 를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="a0a3b-127">**조직의 기술 자료** 섹션에서 **사용자에 게 자세한 정보 연결을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![전문 지식을 사용자에 게 연결](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="a0a3b-129">**사용자에 게 정보 연결** 페이지에서 **시작** 을 클릭 하 여 설치 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![시작](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="a0a3b-131">**기술 네트워크에서 항목을 찾을 수 있는 방법 선택** 페이지에서 항목 검색을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="a0a3b-132">**Sharepoint 항목 원본 선택** 섹션에서 검색 중에 항목의 소스로 크롤링할 SharePoint 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="a0a3b-133">해당 활동은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-133">This includes:</span></span></br>
    <span data-ttu-id="a0a3b-134">a.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-134">a.</span></span> <span data-ttu-id="a0a3b-135">**모든 사이트** : 테 넌 트의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="a0a3b-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="a0a3b-136">현재 및 미래의 사이트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="a0a3b-137">b.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-137">b.</span></span> <span data-ttu-id="a0a3b-138">**선택한 사이트를 제외한 모두 (모두** ): 제외 하려는 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="a0a3b-139">검색에서 옵트아웃 하려는 사이트의 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="a0a3b-140">이후에 만들어진 사이트는 항목 검색의 원본으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="a0a3b-141">c.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-141">c.</span></span> <span data-ttu-id="a0a3b-142">**선택한 사이트만** : 포함 하려는 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="a0a3b-143">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-143">You can also upload a list of sites.</span></span> <span data-ttu-id="a0a3b-144">앞에서 만든 사이트는 항목 검색의 원본으로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![항목 검색 방법 선택](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="a0a3b-146">**이름으로 항목 제외** 섹션에서 검색 된 결과에 포함 하지 않을 항목의 이름을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="a0a3b-147">이 설정을 사용 하 여 중요 한 항목이 지식 네트워크의 일부로 포함 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="a0a3b-148">다음과 같은 옵션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-148">Your options include:</span></span></br>
    <span data-ttu-id="a0a3b-149">a.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-149">a.</span></span> <span data-ttu-id="a0a3b-150">**항목을 제외 하지 않음**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="a0a3b-151">b.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-151">b.</span></span> <span data-ttu-id="a0a3b-152">**이름으로 항목 제외** : 사용자에 게 지식 네트워크의 일부로 표시 하지 않을 항목을 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![제외 항목](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="a0a3b-154">항목을 이름으로 제외 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a0a3b-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="a0a3b-155">항목을 제외 해야 하는 경우에는 **이름으로 제외 항목** 을 선택한 후 **.Csv 서식 파일 다운로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="a0a3b-156">Excel을 사용 합니다. CSV 템플릿-검색 결과에서 제외 하려는 항목 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV 템플릿의 항목 제외](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="a0a3b-158">CSV 서식 파일에 제외 하려는 항목에 대 한 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="a0a3b-159">**이름** : 제외 하려는 항목의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="a0a3b-160">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="a0a3b-161">정확 하 게 일치: 정확한 이름 또는 머리글자어 (예를 들어 *Contoso* 또는 *ATL* )를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="a0a3b-162">부분 일치: 특정 단어를 포함 하는 모든 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="a0a3b-163">예를 들어 *원호* 는 *호 원* , *플라즈마 호 용접* 또는 *트레이닝 호* 같은 단어 *호가* 있는 모든 항목을 제외 합니다. 텍스트를 *아키텍처* 같은 단어의 일부로 포함 하는 항목은 제외 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="a0a3b-164">**확장 (선택 사항)** : 머리글자어를 제외 하려면 머리글자어에서 표시할 단어를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="a0a3b-165">**MatchType-exact/Partial** : 입력 한 이름이 *정확히* 일치 하는 유형 인지, *부분적인* match type이 었는 지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="a0a3b-166">CSV 서식 파일을 완료 하 고 저장 한 후 **찾아보기를** 선택 하 여 찾아서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="a0a3b-167">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="a0a3b-168">**주제 및 항목을 볼 수 있는 위치를 볼 수 있는 사용자** 는 항목 표시 여부를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="a0a3b-169">**정보 네트워크 설정의 항목을 볼 수 있는 사용자** 는 강조 표시 된 항목, 항목 카드, 검색의 항목 대답 및 주제 페이지와 같은 항목 세부 정보에 대 한 액세스 권한을 부여할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="a0a3b-170">다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-170">You can select:</span></span></br>
    <span data-ttu-id="a0a3b-171">a.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-171">a.</span></span> <span data-ttu-id="a0a3b-172">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a0a3b-173">b.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-173">b.</span></span> <span data-ttu-id="a0a3b-174">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="a0a3b-175">c.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-175">c.</span></span> <span data-ttu-id="a0a3b-176">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-176">**No one**</span></span></br>

    ![항목을 볼 수 있는 사람](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="a0a3b-178">이 설정을 사용 하면 조직의 모든 사용자를 선택할 수 있지만, 기술 관리 라이선스가 할당 된 사용자만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="a0a3b-179">**항목 관리에 대 한 사용 권한** 페이지에서 항목을 만들거나 편집 하거나 관리할 수 있는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="a0a3b-180">항목을 **만들고 편집할 수 있는 사용자** 섹션에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="a0a3b-181">a.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-181">a.</span></span> <span data-ttu-id="a0a3b-182">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a0a3b-183">b.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-183">b.</span></span> <span data-ttu-id="a0a3b-184">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="a0a3b-185">항목을 **관리할 수 있는 사용자** 섹션에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="a0a3b-186">a.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-186">a.</span></span> <span data-ttu-id="a0a3b-187">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a0a3b-188">b.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-188">b.</span></span> <span data-ttu-id="a0a3b-189">**선택한 사용자 또는 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="a0a3b-189">**Selected people or security groups**</span></span></br>

    ![항목 관리에 대 한 사용 권한](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="a0a3b-191">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="a0a3b-192">**주제 센터 만들기** 페이지에서 항목 페이지를 볼 수 있고 항목을 관리할 수 있는 주제 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="a0a3b-193">**항목 센터 이름** 상자에 주제 센터의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="a0a3b-194">원하는 경우 **사이트 설명** 상자에 간단한 설명을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="a0a3b-195">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-195">Select **Next**.</span></span></br>

   ![정보 센터 만들기](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="a0a3b-197">**검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="a0a3b-198">원하는 항목을 선택한 경우 **활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![완료 및 검토](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="a0a3b-200">이제 시스템에서 항목에 대 한 선택 된 사이트의 분석을 시작 하 고 정보 센터 사이트를 만들기 시작할 것인지 묻는 **기술 네트워크 활성화** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="a0a3b-201">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-201">Select **Done**.</span></span></br>

    ![활성화](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="a0a3b-203">**사용자에 게 정보를 연결** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="a0a3b-204">이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![적용 되는 설정](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="a0a3b-206">설치가 완료 되 면 관리자는이 페이지로 돌아와 언제 든 지 [선택한 기술 관리 설정을 변경할](topic-experiences-discovery.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3b-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="a0a3b-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0a3b-207">See also</span></span>



  







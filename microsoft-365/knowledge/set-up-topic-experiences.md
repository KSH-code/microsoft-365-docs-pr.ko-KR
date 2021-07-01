---
title: Microsoft Viva 항목 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva 항목을 설정하는 방법 학습
ms.openlocfilehash: 42f84b9b792907d7fe118e0b15c3767674ddf19b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229590"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="4539c-103">Microsoft Viva 항목 설정</span><span class="sxs-lookup"><span data-stu-id="4539c-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="4539c-104">를 사용하여 Microsoft 365 관리 센터 및 [구성할 수 있습니다.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4539c-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="4539c-105">환경에서 항목을 설정하고 구성하는 가장 좋은 방법을 계획하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="4539c-106">이 문서의 절차를 시작하기 전에 [Plan for Microsoft Viva Topics을](plan-topic-experiences.md) 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="4539c-107">Viva 항목에 액세스하고 항목을 설정하려면 [Viva](https://www.microsoft.com/microsoft-viva/topics) SharePoint 관리자 또는 Microsoft 365 관리 센터 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="4539c-108">관리되는 SharePoint 구성한 경우 [](/sharepoint/control-access-from-unmanaged-devices)관리되는 장치에서 항목을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="4539c-109">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="4539c-109">Video demonstration</span></span>

<span data-ttu-id="4539c-110">이 비디오에서는 2016에서 항목을 설정하는 프로세스를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4539c-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="4539c-111">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4539c-111">Assign licenses</span></span>

<span data-ttu-id="4539c-112">항목을 사용할 사용자에 대한 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="4539c-113">라이선스가 있는 사용자만 하이라이트, 주제 카드, 주제 페이지 및 주제 센터를 비롯한 주제에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="4539c-114">라이선스를 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-114">To assign licenses:</span></span>

1. <span data-ttu-id="4539c-115">Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="4539c-116">라이선스를 부여할 사용자를 선택하고 라이선스 및 **앱을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4539c-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="4539c-117">**라이선스에서** **Viva 항목을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4539c-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="4539c-118">앱 **아래에서** **Graph(Viva 항목)** 및 **Viva** 항목을 사용하여 커넥터 검색을 모두 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4539c-119">![Microsoft Viva 항목의 Microsoft 365 관리 센터](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="4539c-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="4539c-120">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-120">Click **Save changes**.</span></span>

<span data-ttu-id="4539c-121">라이선스가 할당된 후 사용자가 항목에 액세스하는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="4539c-122">주제 설정</span><span class="sxs-lookup"><span data-stu-id="4539c-122">Set up Topics</span></span>

> [!Note]
> <span data-ttu-id="4539c-123">항목을 처음 검색할 수 있도록 설정한 경우 제안된 모든 항목을 항목 관리 보기에 표시하는 데 최대 2주가 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-123">The first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="4539c-124">콘텐츠에 대한 새 콘텐츠 또는 업데이트가 진행될 때 항목 검색이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-124">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="4539c-125">Viva Topics는 새 정보를 평가하므로 조직에서 제안된 주제 수가 변동되는 것은 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-125">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

<span data-ttu-id="4539c-126">항목을 설정하기 위해</span><span class="sxs-lookup"><span data-stu-id="4539c-126">To set up Topics</span></span>
1. <span data-ttu-id="4539c-127">에서 [Microsoft 365 관리 센터](https://admin.microsoft.com) **를 선택한** 다음 파일 및 콘텐츠 **섹션을** 를 니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-127">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="4539c-128">파일 **및 콘텐츠 섹션에서** 정보를 **커넥트 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4539c-128">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![커넥트 정보를 알 수 있습니다.](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="4539c-130">사용자 **커넥트** 페이지에서 시작을 클릭하여 설정  프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-130">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![시작](../media/k-get-started.png) 

4. <span data-ttu-id="4539c-132">**Viva 항목을 찾는 방법** 선택 페이지에서 항목 검색을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-132">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="4539c-133">검색 **SharePoint** 원본 선택 섹션에서 SharePoint 항목의 원본으로 크롤링할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-133">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="4539c-134">다음 중 선택:</span><span class="sxs-lookup"><span data-stu-id="4539c-134">Choose from:</span></span>
    - <span data-ttu-id="4539c-135">**모든 사이트**: 조직의 모든 SharePoint 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-135">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="4539c-136">여기에는 현재 사이트와 향후 사이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-136">This includes current and future sites.</span></span>
    - <span data-ttu-id="4539c-137">**선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-137">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="4539c-138">검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-138">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="4539c-139">향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-139">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="4539c-140">**선택한 사이트만:** 포함할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-140">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="4539c-141">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-141">You can also upload a list of sites.</span></span> <span data-ttu-id="4539c-142">이후에 생성된 사이트는 토픽 검색의 원본으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-142">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="4539c-143">**사이트 없음**: SharePoint 사이트는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-143">**No sites**: Do not include any SharePoint sites.</span></span>

    ![항목을 찾는 방법 선택](../media/ksetup1.png) 
   
5. <span data-ttu-id="4539c-145">이름 **항목 제외 섹션에서** 항목 검색에서 제외하려는 항목의 이름을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-145">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="4539c-146">이 설정을 사용하여 중요한 정보가 항목으로 포함되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-146">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="4539c-147">다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-147">The options are:</span></span>
    - <span data-ttu-id="4539c-148">**항목을 제외하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="4539c-148">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="4539c-149">**이름으로 토픽 제외**</span><span class="sxs-lookup"><span data-stu-id="4539c-149">**Exclude topics by name**</span></span>

    ![제외 항목](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="4539c-151">(기술 관리자는 검색 후 항목 센터의 항목을 제외할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="4539c-151">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="4539c-152">이름으로 항목을 제외하는 방법</span><span class="sxs-lookup"><span data-stu-id="4539c-152">How to exclude topics by name</span></span>    

    <span data-ttu-id="4539c-153">항목을 제외해야 하는 경우 이름으로 항목 제외를 선택한 후 .csv 템플릿을 다운로드하고 검색 결과에서 제외하려는 항목 목록으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-153">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV 템플릿에서 항목 제외](../media/exclude-topics-csv.png) 

    <span data-ttu-id="4539c-155">CSV 템플릿에서 제외할 토픽에 대한 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-155">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="4539c-156">**이름**: 제외할 토픽의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-156">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="4539c-157">이 작업을 수행하는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-157">There are two ways to do this:</span></span>
        - <span data-ttu-id="4539c-158">정확한 일치: 정확한 이름 또는 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="4539c-158">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="4539c-159">부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-159">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="4539c-160">예를 들어 *호는* 호 원, 4도분의 호, 교육 호 등 호 단어가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외되지 *않습니다.*</span><span class="sxs-lookup"><span data-stu-id="4539c-160">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="4539c-161">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span><span class="sxs-lookup"><span data-stu-id="4539c-161">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="4539c-162">**MatchType-Exact/Partial**: 입력한 이름이 정확히  일치 유형인지 또는 부분 일치 *유형인지 여부를* 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-162">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="4539c-163">파일 파일을 완료하고 .csv 찾아보기를 선택하여  찾아보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-163">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="4539c-164">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-164">Select **Next**.</span></span>

6. <span data-ttu-id="4539c-165">항목 **Who** 볼 수 있는 위치 페이지에서 항목 표시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-165">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="4539c-166">항목 **Who** 수 있습니다. 설정에서 강조 표시된 항목, 항목 카드, 검색의 항목 답변 및 항목 페이지와 같은 항목 세부 정보에 액세스할 수 있는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="4539c-166">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="4539c-167">다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-167">You can select:</span></span>
    - <span data-ttu-id="4539c-168">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="4539c-168">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4539c-169">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="4539c-169">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="4539c-170">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="4539c-170">**No one**</span></span>

    ![Who 항목을 볼 수 있습니다.](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="4539c-172">이 설정을 사용하면 조직의 사용자를 선택할 수 있는 반면, 항목에 할당된 항목 환경 라이선스가 있는 사용자만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-172">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="4539c-173">항목 **관리에 대한** 사용 권한 페이지에서 항목을 만들거나 편집하거나 관리할 수 있는 인원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-173">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="4539c-174">항목 Who 수 있습니다. **섹션에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-174">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="4539c-175">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="4539c-175">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4539c-176">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="4539c-176">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="4539c-177">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="4539c-177">**No one**</span></span>

    ![항목을 만들고 편집할 수 있는 항목 관리에 대한 사용 권한](../media/ksetup3.png) 

8. <span data-ttu-id="4539c-179">항목 **Who 수 있습니다. 섹션에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-179">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="4539c-180">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="4539c-180">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4539c-181">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="4539c-181">**Only selected people or security groups**</span></span>

    ![항목 관리에 대한 사용 권한](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="4539c-183">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-183">Select **Next**.</span></span>

9. <span data-ttu-id="4539c-184">항목 **센터 만들기 페이지에서** 항목 페이지를 보고 항목을 관리할 수 있는 항목 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-184">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="4539c-185">사이트 **이름 상자에** 항목 센터의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-185">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="4539c-186">URL을 변경하려면 연필 아이콘을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-186">You can click the pencil icon if you want to change the URL.</span></span> <span data-ttu-id="4539c-187">선택적으로 설명 상자에 간단한 설명을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="4539c-187">Optionally, type a short description in the **Description** box.</span></span> 

   > [!Important]
   > <span data-ttu-id="4539c-188">나중에 사이트 이름을 변경할 수 있지만 마법사를 완료한 후 URL을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-188">You can change the site name later, but you can't change the URL after you complete the wizard.</span></span>

   <span data-ttu-id="4539c-189">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-189">Select **Next**.</span></span>

   ![기술 센터 만들기](../media/ksetup4.png)  

10. <span data-ttu-id="4539c-191">**검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-191">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="4539c-192">원하는 항목을 선택한 경우 **활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-192">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="4539c-193">**Viva 항목** 활성화 페이지가 표시되어 시스템에서 선택한 사이트에서 항목을 분석하고 항목 센터 사이트를 만들기 시작할 것 것 을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-193">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="4539c-194">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-194">Select **Done**.</span></span>

12. <span data-ttu-id="4539c-195">You'll be returned to your **커넥트 people to knowledge** page.</span><span class="sxs-lookup"><span data-stu-id="4539c-195">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="4539c-196">이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4539c-196">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![설정 적용](../media/ksetup7.png)    

## <a name="manage-topic-experiences"></a><span data-ttu-id="4539c-198">항목 환경 관리</span><span class="sxs-lookup"><span data-stu-id="4539c-198">Manage topic experiences</span></span>

<span data-ttu-id="4539c-199">항목을 설정한 후 의 설치 중에 선택한 설정을 변경할 [Microsoft 365 관리 센터.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="4539c-199">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="4539c-200">다음 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4539c-200">See the following references:</span></span>

- [<span data-ttu-id="4539c-201">Microsoft Viva 항목에서 항목 검색 관리</span><span class="sxs-lookup"><span data-stu-id="4539c-201">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="4539c-202">Microsoft Viva 항목에서 항목 표시 관리</span><span class="sxs-lookup"><span data-stu-id="4539c-202">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="4539c-203">Microsoft Viva 항목에서 항목 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="4539c-203">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="4539c-204">Microsoft Viva 항목의 항목 센터 이름 변경</span><span class="sxs-lookup"><span data-stu-id="4539c-204">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="4539c-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4539c-205">See also</span></span>

[<span data-ttu-id="4539c-206">항목 환경 개요</span><span class="sxs-lookup"><span data-stu-id="4539c-206">Topic Experiences Overview</span></span>](topic-experiences-overview.md)

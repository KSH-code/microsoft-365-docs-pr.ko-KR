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
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150503"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="cb3ca-103">Microsoft Viva 항목 설정</span><span class="sxs-lookup"><span data-stu-id="cb3ca-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="cb3ca-104">Microsoft 365 관리 센터를 사용하여 항목을 설정하고 [구성할 수 있습니다.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cb3ca-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="cb3ca-105">환경에서 항목을 설정하고 구성하는 가장 좋은 방법을 계획하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="cb3ca-106">이 문서의 절차를 시작하기 전에 [Microsoft Viva 항목](plan-topic-experiences.md) 계획을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="cb3ca-107">[Viva Topics를](https://www.microsoft.com/microsoft-viva/topics) 구독하고 Microsoft 365 관리 센터에 액세스하고 항목을 설정하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="cb3ca-108">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="cb3ca-108">Video demonstration</span></span>

<span data-ttu-id="cb3ca-109">이 비디오에서는 Microsoft 365에서 항목을 설정하는 프로세스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="cb3ca-110">주제 설정</span><span class="sxs-lookup"><span data-stu-id="cb3ca-110">Set up Topics</span></span>

<span data-ttu-id="cb3ca-111">항목을 설정하기 위해</span><span class="sxs-lookup"><span data-stu-id="cb3ca-111">To set up Topics</span></span>

1. <span data-ttu-id="cb3ca-112">Microsoft [365](https://admin.microsoft.com)관리 센터에서 설치를 **선택한** 다음 파일 및 콘텐츠 **섹션을** 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="cb3ca-113">파일 및 **콘텐츠 섹션에서** 사용자 **지식에 연결을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![지식에 사람 연결](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="cb3ca-115">기술에 사용자 연결 **페이지에서**  시작을 클릭하여 설정 프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![시작](../media/k-get-started.png) 

4. <span data-ttu-id="cb3ca-117">**Viva 항목에서 항목을** 찾는 방법 선택 페이지에서 항목 검색을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="cb3ca-118">**SharePoint** 항목 원본 선택 섹션에서 검색 중에 항목에 대한 원본으로 크롤링할 SharePoint 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="cb3ca-119">다음 중 선택:</span><span class="sxs-lookup"><span data-stu-id="cb3ca-119">Choose from:</span></span>
    - <span data-ttu-id="cb3ca-120">**모든 사이트:** 조직의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="cb3ca-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="cb3ca-121">여기에는 현재 및 향후 사이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="cb3ca-122">**선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="cb3ca-123">검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="cb3ca-124">앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="cb3ca-125">**선택한 사이트만 :** 포함할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="cb3ca-126">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-126">You can also upload a list of sites.</span></span> <span data-ttu-id="cb3ca-127">앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="cb3ca-128">**사이트 없음**: SharePoint 사이트를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![항목을 찾는 방법 선택](../media/ksetup1.png) 
   
5. <span data-ttu-id="cb3ca-130">이름 항목 **제외** 섹션에서 항목 검색에서 제외하려는 항목의 이름을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="cb3ca-131">이 설정을 사용하여 중요한 정보가 항목으로 포함되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="cb3ca-132">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-132">The options are:</span></span>
    - <span data-ttu-id="cb3ca-133">**항목을 제외하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="cb3ca-134">**이름으로 항목 제외**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-134">**Exclude topics by name**</span></span>

    ![항목 제외](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="cb3ca-136">(기술 관리자는 검색 후 항목 센터의 항목을 제외할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="cb3ca-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="cb3ca-137">이름으로 항목을 제외하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb3ca-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="cb3ca-138">항목을 제외해야 하는 경우 이름으로 제외 항목을 선택한 후 .csv 템플릿을 다운로드하여 검색 결과에서 제외하려는 항목 목록으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV 템플릿의 항목 제외](../media/exclude-topics-csv.png) 

    <span data-ttu-id="cb3ca-140">CSV 템플릿에서 제외할 항목에 대한 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="cb3ca-141">**이름:** 제외할 항목의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="cb3ca-142">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="cb3ca-143">정확한 일치: 정확한 이름이나 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="cb3ca-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="cb3ca-144">부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="cb3ca-145">예를 들어 *호는* 호 원, 마주치기 또는 교육 호와 같이 단어 호가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외하지 *않습니다.*</span><span class="sxs-lookup"><span data-stu-id="cb3ca-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="cb3ca-146">**약어(선택 사항)**: 약어를 제외하려는 경우 약어가 대명하는 단어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="cb3ca-147">**MatchType-Exact/Partial**: 입력한 이름이 정확한지 부분 일치 *유형인지* *여부를* 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="cb3ca-148">.csv 파일을 완료하고 저장한 후 찾아보기를 선택하여 찾습니다. </span><span class="sxs-lookup"><span data-stu-id="cb3ca-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="cb3ca-149">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-149">Select **Next**.</span></span>

6. <span data-ttu-id="cb3ca-150">항목을 **볼 수 있는 사람** 및 해당 항목을 볼 수 있는 위치 페이지에서 항목 표시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="cb3ca-151">항목 **설정을** 볼 수 있는 사용자 설정에서 강조 표시된 항목, 항목 카드, 검색의 항목 답변, 항목 페이지와 같은 항목 세부 정보에 액세스할 수 있는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="cb3ca-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="cb3ca-152">다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-152">You can select:</span></span>
    - <span data-ttu-id="cb3ca-153">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="cb3ca-154">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="cb3ca-155">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-155">**No one**</span></span>

    ![항목을 볼 수 있는 사람](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="cb3ca-157">이 설정을 사용하면 조직의 모든 사용자를 선택할 수 있습니다. 그러나 항목에 항목 환경 라이선스가 할당된 사용자만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="cb3ca-158">항목 관리에 **대한** 사용 권한 페이지에서 항목을 만들거나 편집하거나 관리할 수 있는 사용자들을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="cb3ca-159">항목을 **만들고 편집할 수** 있는 사용자 섹션에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="cb3ca-160">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="cb3ca-161">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="cb3ca-162">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-162">**No one**</span></span>

    ![항목을 만들고 편집할 수 있는 항목 관리에 대한 사용 권한](../media/ksetup3.png) 

8. <span data-ttu-id="cb3ca-164">항목을 **관리할 수 있는 사용자 섹션에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="cb3ca-165">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="cb3ca-166">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-166">**Only selected people or security groups**</span></span>

    ![항목 관리에 대한 사용 권한](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="cb3ca-168">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-168">Select **Next**.</span></span>

9. <span data-ttu-id="cb3ca-169">항목 센터 **만들기 페이지에서** 항목 페이지를 보고 항목을 관리할 수 있는 항목 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="cb3ca-170">사이트 이름 **상자에** 항목 센터의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="cb3ca-171">필요한 경우 설명 상자에 간단한 설명을 입력할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="cb3ca-172">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-172">Select **Next**.</span></span>

   ![기술 센터 만들기](../media/ksetup4.png)  

10. <span data-ttu-id="cb3ca-174">**검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="cb3ca-175">원하는 항목을 선택한 경우 **활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="cb3ca-176">**Viva Topics 활성화** 페이지가 표시되어 시스템에서 선택한 사이트가 항목에 대한 분석 및 항목 센터 사이트 만들기를 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="cb3ca-177">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-177">Select **Done**.</span></span>

12. <span data-ttu-id="cb3ca-178">기술에 대한 사용자 연결 **페이지로 돌아오게** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="cb3ca-179">이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![적용된 설정](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="cb3ca-181">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="cb3ca-181">Assign licenses</span></span>

<span data-ttu-id="cb3ca-182">항목 환경을 구성한 후 항목을 사용할 사용자에 대한 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="cb3ca-183">라이선스가 있는 사용자만 주요 항목, 항목 카드, 항목 페이지, 항목 센터 등의 항목에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="cb3ca-184">라이선스를 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-184">To assign licenses:</span></span>

1. <span data-ttu-id="cb3ca-185">Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="cb3ca-186">라이선스를 부여할 사용자를 선택하고 라이선스 및 **앱을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cb3ca-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="cb3ca-187">앱에서 **인덱스** 및 항목 환경이 포함된 **Graph Connectors** **검색이** 모두 선택되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="cb3ca-188">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="cb3ca-189">항목 환경 관리</span><span class="sxs-lookup"><span data-stu-id="cb3ca-189">Manage topic experiences</span></span>

<span data-ttu-id="cb3ca-190">항목을 설정한 후 [Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)관리 센터에서 설치 중에 선택한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="cb3ca-191">다음 참조를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-191">See the following references:</span></span>

- [<span data-ttu-id="cb3ca-192">Microsoft Viva 항목에서 항목 검색 관리</span><span class="sxs-lookup"><span data-stu-id="cb3ca-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="cb3ca-193">Microsoft Viva 항목의 항목 표시 관리</span><span class="sxs-lookup"><span data-stu-id="cb3ca-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="cb3ca-194">Microsoft Viva 항목의 항목 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="cb3ca-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="cb3ca-195">Microsoft Viva 항목에서 항목 센터의 이름 변경</span><span class="sxs-lookup"><span data-stu-id="cb3ca-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="cb3ca-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb3ca-196">See also</span></span>

[<span data-ttu-id="cb3ca-197">항목 환경 개요</span><span class="sxs-lookup"><span data-stu-id="cb3ca-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)

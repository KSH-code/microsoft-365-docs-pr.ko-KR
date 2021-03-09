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
ms.openlocfilehash: cc420a0631f5b861341116abcd50cfe90e15450e
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551894"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="b3268-103">Microsoft Viva 항목 설정</span><span class="sxs-lookup"><span data-stu-id="b3268-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="b3268-104">Microsoft 365 관리 센터를 사용하여 항목을 설정하고 [구성할 수 있습니다.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b3268-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="b3268-105">환경에서 항목을 설정하고 구성하는 가장 좋은 방법을 계획하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="b3268-106">이 문서의 절차를 시작하기 전에 [Plan for Microsoft Viva Topics을](plan-topic-experiences.md) 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="b3268-107">Microsoft 365 관리 센터에 액세스하고 항목을 설정하려면 [Viva](https://www.microsoft.com/microsoft-viva/topics) 항목을 구독하고 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="b3268-108">관리되는 장치가 필요하도록 [](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)SharePoint를 구성한 경우 관리되는 장치에서 항목을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-108">If you have configured SharePoint to [require managed devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b3268-109">동영상 데모</span><span class="sxs-lookup"><span data-stu-id="b3268-109">Video demonstration</span></span>

<span data-ttu-id="b3268-110">이 비디오에서는 Microsoft 365에서 항목을 설정하는 프로세스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="b3268-111">주제 설정</span><span class="sxs-lookup"><span data-stu-id="b3268-111">Set up Topics</span></span>

<span data-ttu-id="b3268-112">항목을 설정하기 위해</span><span class="sxs-lookup"><span data-stu-id="b3268-112">To set up Topics</span></span>

1. <span data-ttu-id="b3268-113">Microsoft [365 관리 센터에서](https://admin.microsoft.com)설치 를 선택한 다음 파일 및 **콘텐츠 섹션을** 니다. </span><span class="sxs-lookup"><span data-stu-id="b3268-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="b3268-114">파일 **및 콘텐츠 섹션에서** 기술에 **사용자 연결 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3268-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![지식에 사람 연결](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="b3268-116">기술에 사용자 연결 **페이지에서**  시작을 클릭하여 설정 프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![시작](../media/k-get-started.png) 

4. <span data-ttu-id="b3268-118">**Viva 항목을 찾는 방법** 선택 페이지에서 항목 검색을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="b3268-119">**SharePoint** 항목 원본 선택 섹션에서 검색 중에 항목에 대한 원본으로 크롤링할 SharePoint 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="b3268-120">다음 중 선택:</span><span class="sxs-lookup"><span data-stu-id="b3268-120">Choose from:</span></span>
    - <span data-ttu-id="b3268-121">**모든 사이트:** 조직의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="b3268-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="b3268-122">여기에는 현재 및 향후 사이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="b3268-123">**선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="b3268-124">검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="b3268-125">향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="b3268-126">**선택한 사이트만:** 포함할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="b3268-127">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-127">You can also upload a list of sites.</span></span> <span data-ttu-id="b3268-128">향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="b3268-129">**사이트 없음:** SharePoint 사이트를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![항목을 찾는 방법 선택](../media/ksetup1.png) 
   
5. <span data-ttu-id="b3268-131">이름 **항목 제외 섹션에서** 항목 검색에서 제외하려는 항목의 이름을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="b3268-132">이 설정을 사용하여 중요한 정보가 항목으로 포함되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="b3268-133">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-133">The options are:</span></span>
    - <span data-ttu-id="b3268-134">**항목을 제외하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="b3268-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="b3268-135">**이름으로 항목 제외**</span><span class="sxs-lookup"><span data-stu-id="b3268-135">**Exclude topics by name**</span></span>

    ![제외 항목](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="b3268-137">(기술 관리자는 검색 후 항목 센터의 항목을 제외할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b3268-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="b3268-138">이름으로 항목을 제외하는 방법</span><span class="sxs-lookup"><span data-stu-id="b3268-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="b3268-139">항목을 제외해야 하는 경우 이름으로 항목 제외를 선택한 후 .csv 템플릿을 다운로드하여 검색 결과에서 제외하려는 항목 목록으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV 템플릿에서 항목 제외](../media/exclude-topics-csv.png) 

    <span data-ttu-id="b3268-141">CSV 서식 파일에서 제외하려는 항목에 대한 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="b3268-142">**이름:** 제외할 항목의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="b3268-143">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="b3268-144">정확한 일치: 정확한 이름 또는 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="b3268-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="b3268-145">부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="b3268-146">예를 들어 *호는* 호 원, 4도분의 호, 교육 호 등 호 단어가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외되지 *않습니다.*</span><span class="sxs-lookup"><span data-stu-id="b3268-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="b3268-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span><span class="sxs-lookup"><span data-stu-id="b3268-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="b3268-148">**MatchType-Exact/Partial**: 입력한 이름이 정확히  일치 유형인지 또는 부분 일치 *유형인지 여부를* 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="b3268-149">.csv 파일을 완료하고 저장한 후 찾아보기를 선택하여 찾아서 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="b3268-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="b3268-150">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-150">Select **Next**.</span></span>

6. <span data-ttu-id="b3268-151">항목을 **볼 수 있는** 사용자 및 항목을 볼 수 있는 위치 페이지에서 항목 표시를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="b3268-152">항목을 **볼** 수 있는 사용자 설정에서 강조 표시된 항목, 항목 카드, 검색의 항목 응답 및 항목 페이지와 같은 항목 세부 정보에 액세스할 수 있는 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="b3268-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="b3268-153">다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-153">You can select:</span></span>
    - <span data-ttu-id="b3268-154">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="b3268-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="b3268-155">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="b3268-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="b3268-156">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="b3268-156">**No one**</span></span>

    ![항목을 볼 수 있는 사용자](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="b3268-158">이 설정을 사용하면 조직의 사용자를 선택할 수 있는 반면, 항목에 할당된 항목 환경 라이선스가 있는 사용자만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="b3268-159">항목 **관리에 대한** 사용 권한 페이지에서 항목을 만들거나 편집하거나 관리할 수 있는 인원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="b3268-160">항목을 **만들고 편집할 수 있는 사용자 섹션에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="b3268-161">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="b3268-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="b3268-162">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="b3268-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="b3268-163">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="b3268-163">**No one**</span></span>

    ![항목을 만들고 편집할 수 있는 항목 관리에 대한 사용 권한](../media/ksetup3.png) 

8. <span data-ttu-id="b3268-165">항목을 **관리할 수 있는 사용자 섹션에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="b3268-166">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="b3268-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="b3268-167">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="b3268-167">**Only selected people or security groups**</span></span>

    ![항목 관리에 대한 사용 권한](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="b3268-169">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-169">Select **Next**.</span></span>

9. <span data-ttu-id="b3268-170">항목 **센터 만들기 페이지에서** 항목 페이지를 보고 항목을 관리할 수 있는 항목 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="b3268-171">사이트 **이름 상자에** 항목 센터의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="b3268-172">필요한 경우 설명 상자에 간단한 설명을 입력할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="b3268-173">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-173">Select **Next**.</span></span>

   ![기술 센터 만들기](../media/ksetup4.png)  

10. <span data-ttu-id="b3268-175">**검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b3268-176">원하는 항목을 선택한 경우 **활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="b3268-177">**Viva 항목** 활성화 페이지가 표시되어 시스템에서 선택한 사이트에서 항목을 분석하고 항목 센터 사이트를 만들기 시작할 것 것 을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="b3268-178">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-178">Select **Done**.</span></span>

12. <span data-ttu-id="b3268-179">기술에 사용자 연결 **페이지로 돌아오게** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="b3268-180">이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![적용된 설정](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="b3268-182">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="b3268-182">Assign licenses</span></span>

<span data-ttu-id="b3268-183">항목 환경을 구성한 후 항목을 사용할 사용자에 대한 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-183">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="b3268-184">라이선스가 있는 사용자만 주요 항목, 항목 카드, 항목 페이지 및 항목 센터를 비롯한 항목에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-184">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="b3268-185">라이선스를 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-185">To assign licenses:</span></span>

1. <span data-ttu-id="b3268-186">Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-186">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="b3268-187">라이선스를 부여할 사용자를 선택하고 라이선스 및 **앱을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3268-187">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="b3268-188">**라이선스에서** **Viva 항목을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3268-188">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="b3268-189">앱에서 **그래프** 커넥터 **검색(Viva 항목)** 및 **Viva 항목을** 둘 다 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-189">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

    ![Microsoft 365 관리 센터의 Microsoft Viva 항목 라이선스](../media/topic-experiences-licenses.png)

5. <span data-ttu-id="b3268-191">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="b3268-192">항목 환경 관리</span><span class="sxs-lookup"><span data-stu-id="b3268-192">Manage topic experiences</span></span>

<span data-ttu-id="b3268-193">항목을 설정한 후 [Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)관리 센터에서 설정하는 동안 선택한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3268-193">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="b3268-194">다음 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3268-194">See the following references:</span></span>

- [<span data-ttu-id="b3268-195">Microsoft Viva 항목에서 항목 검색 관리</span><span class="sxs-lookup"><span data-stu-id="b3268-195">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="b3268-196">Microsoft Viva 항목에서 항목 표시 관리</span><span class="sxs-lookup"><span data-stu-id="b3268-196">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="b3268-197">Microsoft Viva 항목에서 항목 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="b3268-197">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="b3268-198">Microsoft Viva 항목의 항목 센터 이름 변경</span><span class="sxs-lookup"><span data-stu-id="b3268-198">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="b3268-199">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3268-199">See also</span></span>

[<span data-ttu-id="b3268-200">항목 환경 개요</span><span class="sxs-lookup"><span data-stu-id="b3268-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)

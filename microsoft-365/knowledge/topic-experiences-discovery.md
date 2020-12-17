---
title: Microsoft 365에서 항목 검색 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365에서 항목 검색을 관리하는 방법을 학습합니다.
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698546"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a><span data-ttu-id="669f3-103">Microsoft 365에서 항목 검색 관리</span><span class="sxs-lookup"><span data-stu-id="669f3-103">Manage topic discovery in Microsoft 365</span></span>

<span data-ttu-id="669f3-104">[Microsoft 365](https://admin.microsoft.com)관리 센터에서 항목 검색 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="669f3-105">이러한 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="669f3-106">항목 관리 설정에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="669f3-106">To access topics management settings:</span></span>

1. <span data-ttu-id="669f3-107">Microsoft 365 관리 센터에서 설정을 클릭한 **다음, Org 설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="669f3-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="669f3-108">서비스 **탭에서** **기술 네트워크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="669f3-108">On the **Services** tab, click **Knowledge network**.</span></span>

    ![지식에 사람 연결](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="669f3-110">항목 검색 **탭을** 선택합니다. 각 설정에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="669f3-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="669f3-112">SharePoint 항목 원본 선택</span><span class="sxs-lookup"><span data-stu-id="669f3-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="669f3-113">항목에 대해 크롤링할 조직의 SharePoint 사이트를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="669f3-114">특정 사이트 목록을 포함하거나 제외하려는 경우 다음 .csv 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="669f3-115">사이트 선택을 사용하여 사이트를 추가하는 경우 포함하거나 제외할 기존 사이트 목록에 사이트가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="669f3-116">.csv 파일을 업로드하면 기존 목록을 덮어니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="669f3-117">이전에 특정 사이트를 포함하거나 제외한 경우 목록을 .csv 파일로 다운로드하고, 변경하고, 새 목록을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="669f3-118">항목 검색을 위한 사이트를 선택</span><span class="sxs-lookup"><span data-stu-id="669f3-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="669f3-119">항목 검색 **탭의** **SharePoint** 항목 원본 선택 아래에서 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="669f3-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="669f3-120">**SharePoint** 항목 원본 선택 페이지에서 검색 중에 항목에 대한 원본으로 크롤링할 SharePoint 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="669f3-121">해당 활동은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-121">This includes:</span></span>
    - <span data-ttu-id="669f3-122">**모든 사이트**: 테넌트의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="669f3-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="669f3-123">이렇게 하여 현재 및 향후 사이트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="669f3-124">**선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="669f3-125">검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="669f3-126">앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="669f3-127">**선택한 사이트만 :** 포함할 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="669f3-128">사이트 목록을 업로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-128">You can also upload a list of sites.</span></span> <span data-ttu-id="669f3-129">앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="669f3-130">**사이트 없음**: 항목은 SharePoint 콘텐츠로 자동으로 생성되거나 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="669f3-131">기존 항목은 항목 센터에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-131">Existing topics remain in the topic center.</span></span>

    ![SharePoint 항목 원본 사용자 인터페이스 스크린샷](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="669f3-133">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="669f3-134">이름으로 항목 제외</span><span class="sxs-lookup"><span data-stu-id="669f3-134">Exclude topics by name</span></span>

<span data-ttu-id="669f3-135">.csv 파일을 사용하여 목록을 업로드하여 검색에서 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="669f3-136">이전에 항목을 제외한 경우 .csv를 다운로드하고 변경한 후 다시 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="669f3-137">항목 검색 **탭의** **제외 항목 아래에서** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="669f3-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="669f3-138">이름으로 **항목 제외를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="669f3-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="669f3-139">목록을 만들어야 하는 경우 .csv 템플릿을 다운로드하고 제외할 항목을 추가합니다(아래 *.csv* 템플릿 작업 참조).</span><span class="sxs-lookup"><span data-stu-id="669f3-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="669f3-140">파일이 준비되면 찾아보기를 **클릭하고** 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="669f3-141">기존 목록이 있는 경우 목록이 포함된 .csv를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="669f3-142">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-142">Click **Save**.</span></span>

    ![제외 항목 사용자 인터페이스 스크린샷](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="669f3-144">.csv 템플릿 작업</span><span class="sxs-lookup"><span data-stu-id="669f3-144">Working with the .csv template</span></span>

<span data-ttu-id="669f3-145">아래 csv 템플릿을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="669f3-146">CSV 템플릿에서 제외할 항목에 대한 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="669f3-147">**이름:** 제외할 항목의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="669f3-148">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="669f3-149">정확한 일치: 정확한 이름이나 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="669f3-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="669f3-150">부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="669f3-151">예를 들어 *호는* 호 원, 마주치기 또는 교육 호와 같이 단어 호가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외하지 *않습니다.*</span><span class="sxs-lookup"><span data-stu-id="669f3-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="669f3-152">**약어(선택 사항)**: 약어를 제외하려는 경우 약어가 대명하는 단어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="669f3-153">**MatchType-Exact/Partial**: 입력한 이름이 정확히 일치하는 형식인지 부분 일치 *형식인지* *여부를* 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="669f3-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![CSV 템플릿의 항목 제외](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="669f3-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="669f3-155">See also</span></span>

[<span data-ttu-id="669f3-156">Microsoft 365에서 항목 표시 관리</span><span class="sxs-lookup"><span data-stu-id="669f3-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="669f3-157">Microsoft 365에서 항목 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="669f3-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="669f3-158">Microsoft 365에서 항목 센터의 이름 변경</span><span class="sxs-lookup"><span data-stu-id="669f3-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

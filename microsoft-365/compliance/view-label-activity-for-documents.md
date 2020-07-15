---
title: 문서에 대한 레이블 활동 보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Microsoft 365 보안 및 준수 센터에서 레이블 활동 탐색기를 사용하여 레이블 활동을 검색하고 확인하는 방법을 알아봅니다.
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127275"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="0111d-103">문서에 대한 레이블 활동 보기</span><span class="sxs-lookup"><span data-stu-id="0111d-103">View label activity for documents</span></span>

<span data-ttu-id="0111d-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span><span class="sxs-lookup"><span data-stu-id="0111d-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="0111d-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span><span class="sxs-lookup"><span data-stu-id="0111d-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span></span> <span data-ttu-id="0111d-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span><span class="sxs-lookup"><span data-stu-id="0111d-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="0111d-107">예를 들어 레이블 활동 탐색기로 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0111d-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="0111d-108">각 레이블이 각 날에 적용된 횟수를 확인합니다(최대 30일).</span><span class="sxs-lookup"><span data-stu-id="0111d-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="0111d-109">누가 어떤 파일에 언제 레이블을 지정했는지와 해당 파일이 있는 사이트에 대한 링크를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0111d-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="0111d-110">레이블이 변경 또는 제거된 파일, 어느 것이 이전 및 새 레이블인지 및 변경한 사람을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0111d-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="0111d-111">Filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="0111d-111">Filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="0111d-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="0111d-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="0111d-113">View label activity for folders as well as individual documents.</span><span class="sxs-lookup"><span data-stu-id="0111d-113">View label activity for folders as well as individual documents.</span></span> <span data-ttu-id="0111d-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span><span class="sxs-lookup"><span data-stu-id="0111d-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="0111d-115">보안 &amp; 준수 센터 > **정보 거버넌스** > **레이블 활동 탐색기**에서 레이블 활동 탐색기를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0111d-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="0111d-116">레이블 활동 탐색기를 사용하려면 Office 365 Enterprise E5 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0111d-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![레이블 활동 탐색기](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="0111d-118">파일 또는 폴더에 대한 레이블 활동 보기</span><span class="sxs-lookup"><span data-stu-id="0111d-118">View label activities for files or folders</span></span>

<span data-ttu-id="0111d-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span><span class="sxs-lookup"><span data-stu-id="0111d-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span></span> <span data-ttu-id="0111d-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span><span class="sxs-lookup"><span data-stu-id="0111d-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="0111d-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span><span class="sxs-lookup"><span data-stu-id="0111d-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span></span> <span data-ttu-id="0111d-122">Therefore, labeling folders might affect a significant number of files.</span><span class="sxs-lookup"><span data-stu-id="0111d-122">Therefore, labeling folders might affect a significant number of files.</span></span> <span data-ttu-id="0111d-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="0111d-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![파일 및 폴더에 대한 레이블 활동을 보여 주는 드롭다운 메뉴](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="0111d-125">레이블 활동</span><span class="sxs-lookup"><span data-stu-id="0111d-125">Label activities</span></span>

 <span data-ttu-id="0111d-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="0111d-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span></span> <span data-ttu-id="0111d-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span><span class="sxs-lookup"><span data-stu-id="0111d-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="0111d-128">레이블 변경</span><span class="sxs-lookup"><span data-stu-id="0111d-128">Label changes</span></span>

 <span data-ttu-id="0111d-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="0111d-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span></span> <span data-ttu-id="0111d-130">You can use this view to quickly see such risky actions and the user who performed them.</span><span class="sxs-lookup"><span data-stu-id="0111d-130">You can use this view to quickly see such risky actions and the user who performed them.</span></span> <span data-ttu-id="0111d-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span><span class="sxs-lookup"><span data-stu-id="0111d-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![레이블 활동에 대한 세부 정보 창](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="0111d-133">레이블 활동 필터링</span><span class="sxs-lookup"><span data-stu-id="0111d-133">Filter label activity</span></span>

<span data-ttu-id="0111d-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="0111d-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="0111d-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="0111d-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![레이블 활동에 대한 필터](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  


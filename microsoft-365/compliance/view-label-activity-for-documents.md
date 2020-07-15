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
# <a name="view-label-activity-for-documents"></a>문서에 대한 레이블 활동 보기

After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.
  
예를 들어 레이블 활동 탐색기로 다음을 수행할 수 있습니다.
  
- 각 레이블이 각 날에 적용된 횟수를 확인합니다(최대 30일).
    
- 누가 어떤 파일에 언제 레이블을 지정했는지와 해당 파일이 있는 사이트에 대한 링크를 확인합니다.
    
- 레이블이 변경 또는 제거된 파일, 어느 것이 이전 및 새 레이블인지 및 변경한 사람을 확인합니다.
    
- Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.
    
- View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.
    
보안 &amp; 준수 센터 > **정보 거버넌스** > **레이블 활동 탐색기**에서 레이블 활동 탐색기를 찾을 수 있습니다.
  
레이블 활동 탐색기를 사용하려면 Office 365 Enterprise E5 구독이 있어야 합니다.
  
![레이블 활동 탐색기](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a>파일 또는 폴더에 대한 레이블 활동 보기

At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.
  
You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![파일 및 폴더에 대한 레이블 활동을 보여 주는 드롭다운 메뉴](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a>레이블 활동

 **Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day. 
  
### <a name="label-changes"></a>레이블 변경

 **Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right. 
  
![레이블 활동에 대한 세부 정보 창](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a>레이블 활동 필터링

You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.
  
![레이블 활동에 대한 필터](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  


---
title: 삭제 된 Office 365 그룹 복원
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 삭제 된 Office 365 그룹을 복원 하는 방법을 알아봅니다.
ms.openlocfilehash: 2efd8c35286d224c6a3ed185043c82ab4b8e954e
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547535"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="3bf29-103">삭제된 Office 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="3bf29-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="3bf29-104">그룹을 삭제 한 경우에는 기본적으로 30 일간 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="3bf29-105">이 30 일의 기간은 여전히 그룹을 복원할 수 있기 때문에 "일시 삭제"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="3bf29-106">30 일이 지나면 그룹 및 관련 내용이 영구적으로 삭제 되며 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="3bf29-107">그룹이 복원되면 다음 콘텐츠가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="3bf29-108">Azure AD (Active Directory) Office 365 그룹 개체, 속성 및 구성원</span><span class="sxs-lookup"><span data-stu-id="3bf29-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="3bf29-109">그룹의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="3bf29-110">Exchange Online 공유 받은 편지함 및 일정</span><span class="sxs-lookup"><span data-stu-id="3bf29-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="3bf29-111">SharePoint Online 팀 사이트 및 파일</span><span class="sxs-lookup"><span data-stu-id="3bf29-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="3bf29-112">OneNote 전자 필기장</span><span class="sxs-lookup"><span data-stu-id="3bf29-112">OneNote notebook</span></span>
    
- <span data-ttu-id="3bf29-113">Planner</span><span class="sxs-lookup"><span data-stu-id="3bf29-113">Planner</span></span>
    
- <span data-ttu-id="3bf29-114">Teams</span><span class="sxs-lookup"><span data-stu-id="3bf29-114">Teams</span></span>

- <span data-ttu-id="3bf29-115">Yammer 그룹 및 그룹 콘텐츠 (Yammer에서 Office 365 그룹을 만든 경우)</span><span class="sxs-lookup"><span data-stu-id="3bf29-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="3bf29-116">Outlook을 사용 하 여 소유한 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="3bf29-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="3bf29-117">Office 365 그룹의 소유자 인 경우 다음 단계를 수행 하 여 Outlook에서 그룹을 직접 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="3bf29-118">삭제 된 [그룹 페이지](https://outlook.office.com/people/group/deleted)에서 **그룹** 노드 아래의 **그룹 관리** 옵션을 선택한 다음 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="3bf29-119">복원 하려는 그룹 옆에 있는 **복원** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="3bf29-120">삭제 된 그룹이 여기에 표시 되지 않으면 관리자에 게 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3bf29-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3bf29-121">Microsoft 365 관리 센터에서 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="3bf29-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3bf29-122">전역 관리자 또는 그룹 관리자 인 경우 Microsoft 365 관리 센터에서 삭제 된 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="3bf29-123">[관리 센터로](https://admin.microsoft.com)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="3bf29-124">**그룹**을 확장 한 다음 **삭제 된 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="3bf29-125">복원할 그룹을 선택한 다음 **그룹 복원을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="3bf29-126">Office 365그룹 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="3bf29-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="3bf29-127">경우에 따라 30 일 일시 삭제 기간이 만료 될 때까지 기다리지 않고 그룹을 영구적으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="3bf29-128">이렇게 하려면 PowerShell을 시작하고 이 명령을 실행하여 그룹의 개체 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="3bf29-129">영구적으로 삭제 하려는 그룹 (또는 그룹)의 개체 ID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3bf29-130">그룹을 제거하면 그룹 및 해당 데이터가 영구적으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="3bf29-131">그룹을 제거하려면 PowerShell에서 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="3bf29-p103">그룹이 제거되었는지 확인하려면  *Get-AzureADMSDeletedGroup*  cmdlet을 다시 실행하여 그룹이 소프트 삭제된 그룹 목록에 더 이상 나타나지 않는지 확인합니다. 일부 경우 그룹 및 모든 해당 데이터가 영구적으로 삭제되는 데 24시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf29-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="3bf29-134">Office 365 그룹에 대한 질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="3bf29-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="3bf29-135">[Microsoft 기술 커뮤니티](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 를 방문 하 여 질문을 게시 하 고 Office 365 그룹에 대 한 대화에 참여 하세요.</span><span class="sxs-lookup"><span data-stu-id="3bf29-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="3bf29-136">관련 문서</span><span class="sxs-lookup"><span data-stu-id="3bf29-136">Related articles</span></span>

[<span data-ttu-id="3bf29-137">PowerShell을 사용하여 Office 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="3bf29-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="3bf29-138">Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="3bf29-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="3bf29-139">그룹에 연결된 팀 사이트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="3bf29-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="3bf29-140">Outlook에서 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="3bf29-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)

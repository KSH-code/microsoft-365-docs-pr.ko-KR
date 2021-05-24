---
title: 삭제된 그룹 Microsoft 365 복원
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 삭제된 그룹은 30일 동안 보존되고 그룹을 복원할 수 있습니다. 30일이 지난 후 그룹 및 해당 콘텐츠는 영구적으로 삭제됩니다.
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635741"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="d640f-104">삭제된 그룹 Microsoft 365 복원</span><span class="sxs-lookup"><span data-stu-id="d640f-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="d640f-105">그룹을 삭제한 경우 기본적으로 30일 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="d640f-106">이 30일 기간은 그룹을 복원할 수 있기 때문에 "소프트 삭제"로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d640f-107">30일이 지난 후 그룹 및 관련 콘텐츠는 영구적으로 삭제되고 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d640f-108">그룹이 복원되면 다음 콘텐츠가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="d640f-109">Azure Active Directory(AD) Microsoft 365, 속성 및 구성원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="d640f-110">그룹의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="d640f-111">Exchange Online 받은 편지함 및 일정을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="d640f-112">SharePoint 온라인 팀 사이트 및 파일.</span><span class="sxs-lookup"><span data-stu-id="d640f-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="d640f-113">OneNote 전자 필기장</span><span class="sxs-lookup"><span data-stu-id="d640f-113">OneNote notebook</span></span>
    
- <span data-ttu-id="d640f-114">Planner</span><span class="sxs-lookup"><span data-stu-id="d640f-114">Planner</span></span>
    
- <span data-ttu-id="d640f-115">Teams</span><span class="sxs-lookup"><span data-stu-id="d640f-115">Teams</span></span>

- <span data-ttu-id="d640f-116">Yammer 및 그룹 콘텐츠(Microsoft 365 그룹이 Yammer)</span><span class="sxs-lookup"><span data-stu-id="d640f-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="d640f-117">이 문서에서는 그룹만 복원하는 Microsoft 365 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="d640f-118">다른 모든 그룹은 한 번 삭제하면 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="d640f-119">그룹 복원</span><span class="sxs-lookup"><span data-stu-id="d640f-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="d640f-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="d640f-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="d640f-121">Microsoft 365 그룹의 소유자인 경우 다음 단계를 수행하여 웹 Outlook 그룹에서 직접 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="d640f-122">삭제된 [그룹 페이지에서](https://outlook.office.com/people/group/deleted)그룹  노드 아래에서 그룹 관리 옵션을 **선택한** 다음 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d640f-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="d640f-123">복원할 **그룹** 옆의 복원 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="d640f-124">삭제된 그룹이 여기에 나타나지 않는 경우 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d640f-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="d640f-125">관리 센터</span><span class="sxs-lookup"><span data-stu-id="d640f-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="d640f-126">전역 관리자 또는 그룹 관리자인 경우 Microsoft 365 관리 센터에서 삭제된 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="d640f-127">[관리 센터](https://admin.microsoft.com)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d640f-128">그룹을 **확장한** 다음 삭제된 **그룹을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d640f-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="d640f-129">복원할 그룹을 선택한 다음 그룹 **복원 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d640f-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="d640f-130">경우에 따라 그룹 및 모든 데이터를 복원하는 데 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d640f-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="d640f-131">그룹에 대한 Microsoft 365 있나요?</span><span class="sxs-lookup"><span data-stu-id="d640f-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="d640f-132">Microsoft [Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 방문하여 질문을 게시하고 Microsoft 365 그룹에 대한 대화에 참여하세요.</span><span class="sxs-lookup"><span data-stu-id="d640f-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="d640f-133">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d640f-133">Related content</span></span>

<span data-ttu-id="d640f-134">[PowerShell을 Microsoft 365 그룹](../../enterprise/manage-microsoft-365-groups-with-powershell.md) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="d640f-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="d640f-135">[Remove-UnifiedGroup cmdlet을](/powershell/module/exchange/remove-unifiedgroup) 사용하여 그룹 삭제(문서)</span><span class="sxs-lookup"><span data-stu-id="d640f-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="d640f-136">[그룹에 연결된 팀 사이트 설정](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="d640f-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="d640f-137">[사용자 계정에서 Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) 삭제(문서)</span><span class="sxs-lookup"><span data-stu-id="d640f-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>
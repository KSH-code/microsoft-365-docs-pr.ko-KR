---
title: 삭제된 Microsoft 365 그룹 복원
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
description: 삭제된 Microsoft 365 그룹을 복원하는 방법을 배워야 합니다.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753246"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="cfb3a-103">삭제된 Microsoft 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="cfb3a-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="cfb3a-104">그룹을 삭제한 경우 기본적으로 30일 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="cfb3a-105">이 30일의 기간은 그룹을 복원할 수 있기 때문에 "소프트 삭제"로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="cfb3a-106">30일이 지난 후 그룹 및 해당 관련 콘텐츠는 영구적으로 삭제되고 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="cfb3a-107">그룹이 복원되면 다음 콘텐츠가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="cfb3a-108">Azure AD(Active Directory) Microsoft 365 그룹 개체, 속성 및 구성원</span><span class="sxs-lookup"><span data-stu-id="cfb3a-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="cfb3a-109">그룹의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="cfb3a-110">Exchange Online 공유 받은 편지함 및 일정</span><span class="sxs-lookup"><span data-stu-id="cfb3a-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="cfb3a-111">SharePoint Online 팀 사이트 및 파일.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="cfb3a-112">OneNote 전자 필기장</span><span class="sxs-lookup"><span data-stu-id="cfb3a-112">OneNote notebook</span></span>
    
- <span data-ttu-id="cfb3a-113">Planner</span><span class="sxs-lookup"><span data-stu-id="cfb3a-113">Planner</span></span>
    
- <span data-ttu-id="cfb3a-114">Teams</span><span class="sxs-lookup"><span data-stu-id="cfb3a-114">Teams</span></span>

- <span data-ttu-id="cfb3a-115">Yammer 및 그룹 콘텐츠(Microsoft 365 그룹이 그룹에서 만들어진 Yammer)</span><span class="sxs-lookup"><span data-stu-id="cfb3a-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="cfb3a-116">이 문서에서는 Microsoft 365 그룹만 복원하는 데 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="cfb3a-117">다른 모든 그룹은 한 번 삭제하면 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="cfb3a-118">그룹 복원</span><span class="sxs-lookup"><span data-stu-id="cfb3a-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="cfb3a-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="cfb3a-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="cfb3a-120">Microsoft 365 그룹의 소유자인 경우 다음 단계에 따라 웹에서 Outlook에서 그룹을 직접 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="cfb3a-121">삭제된 [그룹 페이지에서](https://outlook.office.com/people/group/deleted)그룹  노드에서 그룹  관리 옵션을 선택한 다음 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfb3a-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="cfb3a-122">복원할 **그룹** 옆의 복원 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="cfb3a-123">삭제된 그룹이 여기에 나타나지 않는 경우 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="cfb3a-124">관리 센터</span><span class="sxs-lookup"><span data-stu-id="cfb3a-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="cfb3a-125">전역 관리자 또는 그룹 관리자인 경우 Microsoft 365 관리 센터에서 삭제된 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="cfb3a-126">[관리 센터](https://admin.microsoft.com)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="cfb3a-127">그룹을 **확장한** 다음 **삭제된 그룹을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfb3a-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="cfb3a-128">복원할 그룹을 선택한 다음 **그룹 복원을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfb3a-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="cfb3a-129">경우에 따라 그룹 및 모든 데이터를 복원하는 데 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="cfb3a-130">Microsoft 365 그룹에 대한 질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="cfb3a-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="cfb3a-131">Microsoft [기술 커뮤니티를 방문하여 질문을](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 게시하고 Microsoft 365 그룹에 대한 대화에 참여하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb3a-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="cfb3a-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="cfb3a-132">Related articles</span></span>

[<span data-ttu-id="cfb3a-133">PowerShell을 사용하여 Microsoft 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="cfb3a-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="cfb3a-134">Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="cfb3a-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="cfb3a-135">그룹에 연결된 팀 사이트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="cfb3a-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="cfb3a-136">Outlook에서 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="cfb3a-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)

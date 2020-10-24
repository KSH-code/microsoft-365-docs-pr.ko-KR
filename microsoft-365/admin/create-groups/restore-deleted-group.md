---
title: 삭제 된 Microsoft 365 그룹 복원
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
description: 삭제 된 Microsoft 365 그룹을 복원 하는 방법을 알아봅니다.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753246"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="a5c51-103">삭제 된 Microsoft 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="a5c51-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="a5c51-104">그룹을 삭제 한 경우에는 기본적으로 30 일간 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="a5c51-105">이 30 일의 기간은 여전히 그룹을 복원할 수 있기 때문에 "일시 삭제"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="a5c51-106">30 일이 지나면 그룹 및 관련 내용이 영구적으로 삭제 되며 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="a5c51-107">그룹이 복원되면 다음 콘텐츠가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="a5c51-108">Azure AD (Active Directory) Microsoft 365 Groups 개체, 속성 및 구성원</span><span class="sxs-lookup"><span data-stu-id="a5c51-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="a5c51-109">그룹의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="a5c51-110">Exchange Online 공유 받은 편지함 및 일정</span><span class="sxs-lookup"><span data-stu-id="a5c51-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="a5c51-111">SharePoint Online 팀 사이트 및 파일</span><span class="sxs-lookup"><span data-stu-id="a5c51-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="a5c51-112">OneNote 전자 필기장</span><span class="sxs-lookup"><span data-stu-id="a5c51-112">OneNote notebook</span></span>
    
- <span data-ttu-id="a5c51-113">Planner</span><span class="sxs-lookup"><span data-stu-id="a5c51-113">Planner</span></span>
    
- <span data-ttu-id="a5c51-114">Teams</span><span class="sxs-lookup"><span data-stu-id="a5c51-114">Teams</span></span>

- <span data-ttu-id="a5c51-115">Yammer 그룹 및 그룹 콘텐츠 (Yammer에서 Microsoft 365 그룹이 만들어진 경우)</span><span class="sxs-lookup"><span data-stu-id="a5c51-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="a5c51-116">이 문서에서는 Microsoft 365 그룹만 복원에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="a5c51-117">다른 모든 그룹은 삭제 한 후에 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="a5c51-118">그룹 복원</span><span class="sxs-lookup"><span data-stu-id="a5c51-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="a5c51-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="a5c51-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="a5c51-120">Microsoft 365 그룹의 소유자 인 경우 다음 단계를 수행 하 여 웹용 Outlook에서 그룹을 직접 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="a5c51-121">삭제 된 [그룹 페이지](https://outlook.office.com/people/group/deleted)에서 **그룹** 노드 아래의 **그룹 관리** 옵션을 선택한 다음 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="a5c51-122">복원 하려는 그룹 옆에 있는 **복원** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="a5c51-123">삭제 된 그룹이 여기에 표시 되지 않으면 관리자에 게 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5c51-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="a5c51-124">관리 센터</span><span class="sxs-lookup"><span data-stu-id="a5c51-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="a5c51-125">전역 관리자 또는 그룹 관리자 인 경우 Microsoft 365 관리 센터에서 삭제 된 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="a5c51-126">[관리 센터](https://admin.microsoft.com)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="a5c51-127">**그룹**을 확장 한 다음 **삭제 된 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="a5c51-128">복원할 그룹을 선택한 다음 **그룹 복원을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="a5c51-129">경우에 따라 그룹 및 해당 모든 데이터를 복원 하는 데 24 시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c51-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="a5c51-130">Microsoft 365 그룹에 대 한 질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="a5c51-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="a5c51-131">[Microsoft 기술 커뮤니티](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 를 방문 하 여 질문을 게시 하 고 microsoft 365 그룹에 대 한 대화에 참여 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5c51-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a5c51-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a5c51-132">Related articles</span></span>

[<span data-ttu-id="a5c51-133">PowerShell을 사용 하 여 Microsoft 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="a5c51-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="a5c51-134">Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="a5c51-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="a5c51-135">그룹에 연결된 팀 사이트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a5c51-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="a5c51-136">Outlook에서 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="a5c51-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)

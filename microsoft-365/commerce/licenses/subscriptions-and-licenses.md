---
title: 비즈니스용 Office 365의 구독 및 라이선스 이해
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: '비즈니스용 Office 365의 구독 및 라이선스에 대해 알아보고 라이선스를 할당할 수 있는 사람 및 사용자에 게 라이선스를 할당할 때 수행 되는 작업을 파악 합니다. '
ms.custom: okr_SMB
ms.openlocfilehash: 1a90e4b80322ad075f2149801aebd02ac07a2aef
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246349"
---
# <a name="understand-subscriptions-and-licenses-in-office-365-for-business"></a><span data-ttu-id="45235-103">비즈니스용 Office 365의 구독 및 라이선스 이해</span><span class="sxs-lookup"><span data-stu-id="45235-103">Understand subscriptions and licenses in Office 365 for business</span></span>

<span data-ttu-id="45235-104">이 문서에서는 구독 및 라이선스 간의 관계에 대해 설명 하 고, 라이선스를 [할당할 수 있는 사람](#find-out-who-can-assign-licenses), 사용자 [에 게 라이선스를 할당할 때 수행 되는 작업](#understand-what-happens-when-you-assign-a-license-to-someone)및 [사용자가 Office를 설치할 수 있는 장치 개수](#how-many-devices-can-people-install-office-on)에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45235-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="45235-105">또한 [비 사용자 사서함의 라이선스 이해](#understand-licenses-for-non-user-mailboxes)에 대 한 링크와 [라이선스 관리에 대 한 문서](#articles-about-managing-licenses)도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="45235-106">비즈니스용 Office 365에 대 한 구독을 구입할 때 매월 또는 연간 기준으로 지불 하는 응용 프로그램 및 서비스 집합에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="45235-106">When you buy a subscription to Office 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="45235-107">구독의 일부로 수신 하는 응용 프로그램 및 서비스는 구입한 제품 (예: Office 365 Business 또는 Office 365 Business Premium)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="45235-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Office 365 Business or Office 365 Business Premium.</span></span> <span data-ttu-id="45235-108">[Office 구입 365 페이지](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)에서 각 제품과 함께 제공 되는 내용을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-108">You can review what comes with each product on the [Buy Office 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="45235-109">구독을 구입할 때 조직의 사용자 수를 기준으로 필요한 라이선스 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45235-109">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="45235-110">구입을 완료한 후 사용자 계정을 만들고 각 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="45235-110">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="45235-111">조직의 요구 사항이 변경 되 면 새 사용자를 수용할 수 있는 라이선스를 추가로 구입 하거나 다른 사용자에 게 라이선스를 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="45235-111">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="45235-112">구독이 두 개 이상 있는 경우 각 구독에 대해 다른 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-112">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="45235-113">예를 들어 모든 사용자가 Office 365 Business Premium 구독의 일부로 모든 Office 365 응용 프로그램 및 서비스에 할당 될 수 있지만, 사용자의 하위 집합은 별도의 Visio 구독을 통해 Visio Online에 할당 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-113">For example, all of your users could be assigned to all Office 365 applications and services as part of an Office 365 Business Premium subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="45235-114">라이선스를 할당할 수 있는 사용자 찾기</span><span class="sxs-lookup"><span data-stu-id="45235-114">Find out who can assign licenses</span></span>

<span data-ttu-id="45235-p105">여러 유형의 관리자가 해당 역할에 따라 서로 다른 방법으로 라이선스를 사용할 수 있습니다. 다음 표에는 가장 일반적인 옵션이 나열되어 있습니다. 관리자 역할 및 권한의 전체 목록은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45235-p105">Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="45235-118">**관리자 역할**</span><span class="sxs-lookup"><span data-stu-id="45235-118">**Admin role**</span></span>|<span data-ttu-id="45235-119">**라이선스 할당**</span><span class="sxs-lookup"><span data-stu-id="45235-119">**Assign a license**</span></span>|<span data-ttu-id="45235-120">**라이선스 제거**</span><span class="sxs-lookup"><span data-stu-id="45235-120">**Remove a license**</span></span>|<span data-ttu-id="45235-121">**추가 라이선스 구입**</span><span class="sxs-lookup"><span data-stu-id="45235-121">**Purchase more licenses**</span></span>|<span data-ttu-id="45235-122">**계정 삭제**</span><span class="sxs-lookup"><span data-stu-id="45235-122">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45235-123">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="45235-123">Global admin</span></span>  <br/> |<span data-ttu-id="45235-124">예</span><span class="sxs-lookup"><span data-stu-id="45235-124">Yes</span></span>  <br/> |<span data-ttu-id="45235-125">예</span><span class="sxs-lookup"><span data-stu-id="45235-125">Yes</span></span>  <br/> |<span data-ttu-id="45235-126">예</span><span class="sxs-lookup"><span data-stu-id="45235-126">Yes</span></span>  <br/> |<span data-ttu-id="45235-127">예</span><span class="sxs-lookup"><span data-stu-id="45235-127">Yes</span></span>  <br/> |
|<span data-ttu-id="45235-128">대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="45235-128">Billing admin</span></span>  <br/> |<span data-ttu-id="45235-129">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-129">No</span></span>  <br/> |<span data-ttu-id="45235-130">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-130">No</span></span>  <br/> |<span data-ttu-id="45235-131">예</span><span class="sxs-lookup"><span data-stu-id="45235-131">Yes</span></span>  <br/> |<span data-ttu-id="45235-132">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-132">No</span></span>  <br/> |
|<span data-ttu-id="45235-133">사용자 관리 관리자</span><span class="sxs-lookup"><span data-stu-id="45235-133">User management admin</span></span>  <br/> |<span data-ttu-id="45235-134">예</span><span class="sxs-lookup"><span data-stu-id="45235-134">Yes</span></span>  <br/> |<span data-ttu-id="45235-135">예</span><span class="sxs-lookup"><span data-stu-id="45235-135">Yes</span></span>  <br/> |<span data-ttu-id="45235-136">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-136">No</span></span>  <br/> |<span data-ttu-id="45235-137">예</span><span class="sxs-lookup"><span data-stu-id="45235-137">Yes</span></span>  <br/> |
|<span data-ttu-id="45235-138">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="45235-138">Service admin</span></span>  <br/> |<span data-ttu-id="45235-139">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-139">No</span></span>  <br/> |<span data-ttu-id="45235-140">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-140">No</span></span>  <br/> |<span data-ttu-id="45235-141">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-141">No</span></span>  <br/> |<span data-ttu-id="45235-142">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-142">No</span></span>  <br/> |
|<span data-ttu-id="45235-143">암호 관리자</span><span class="sxs-lookup"><span data-stu-id="45235-143">Password admin</span></span>  <br/> |<span data-ttu-id="45235-144">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-144">No</span></span>  <br/> |<span data-ttu-id="45235-145">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-145">No</span></span>  <br/> |<span data-ttu-id="45235-146">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-146">No</span></span>  <br/> |<span data-ttu-id="45235-147">아니요</span><span class="sxs-lookup"><span data-stu-id="45235-147">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="45235-148">사용자에게 라이선스를 할당할 때 발생하는 사항 이해</span><span class="sxs-lookup"><span data-stu-id="45235-148">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="45235-149">다음 표에는 사용자에게 라이선스를 할당할 때 자동으로 발생하는 일이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-149">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="45235-150">**구독에 이 서비스가 있는 경우**</span><span class="sxs-lookup"><span data-stu-id="45235-150">**If the subscription has this service**</span></span>|<span data-ttu-id="45235-151">**자동으로 일어나는 일**</span><span class="sxs-lookup"><span data-stu-id="45235-151">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="45235-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="45235-152">Exchange Online</span></span>  <br/> |<span data-ttu-id="45235-153">해당 사용자의 사서함이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="45235-153">A mailbox is created for that person.</span></span>  <br/> |
|<span data-ttu-id="45235-154">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="45235-154">SharePoint Online</span></span>  <br/> |<span data-ttu-id="45235-155">기본 SharePoint Online 팀 사이트에 대한 편집 권한이 해당 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="45235-155">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="45235-156">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="45235-156">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="45235-157">사용자가 라이선스 관련 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-157">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="45235-158">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="45235-158">Office 365 ProPlus</span></span>  <br/> |<span data-ttu-id="45235-159">사용자는 조직의 최대 5대의 Mac 또는 PC, 최대 5대의 태블릿, 최대 5대의 스마트폰에 Microsoft Office를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-159">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="45235-160">사용자가 Office를 설치할 수 있는 장치는 몇 개인가요?</span><span class="sxs-lookup"><span data-stu-id="45235-160">How many devices can people install Office on?</span></span>

<span data-ttu-id="45235-161">구독에 다음 제품이 포함되는 경우 각 사용자는 최대 5대의 PC 또는 Mac, 최대 5대의 태블릿, 최대 5대의 전화기에 Office를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45235-161">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="45235-162">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="45235-162">Office 365 Business</span></span>
    
- <span data-ttu-id="45235-163">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="45235-163">Office 365 Business Premium</span></span>
    
- <span data-ttu-id="45235-164">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="45235-164">Office 365 ProPlus</span></span>
    
- <span data-ttu-id="45235-165">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="45235-165">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="45235-166">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="45235-166">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="45235-167">비사용자 사서함의 라이선스 이해</span><span class="sxs-lookup"><span data-stu-id="45235-167">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="45235-p106">리소스 사서함, 대화방 사서함, 공유 사서함이 50GB(기가바이트)의 저장소 할당량을 초과할 경우를 제외하고, 해당 사서함에 라이선스를 할당할 필요가 없습니다. 비사용자 사서함에 대해서는 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45235-p106">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="45235-170">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="45235-170">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="45235-171">[Exchange Online의 공유 사서함](https://go.microsoft.com/fwlink/p/?linkid=847433)(다른 모든 Office 365 요금제용)</span><span class="sxs-lookup"><span data-stu-id="45235-171">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Office 365 plans.</span></span> 
    
- [<span data-ttu-id="45235-172">대화방 사서함 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="45235-172">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [<span data-ttu-id="45235-173">장비 사서함 관리</span><span class="sxs-lookup"><span data-stu-id="45235-173">Manage Equipment Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="45235-174">라이선스 관리에 대 한 문서</span><span class="sxs-lookup"><span data-stu-id="45235-174">Articles about managing licenses</span></span>

- [<span data-ttu-id="45235-175">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="45235-175">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="45235-176">사용자의 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="45235-176">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="45235-177">구독용 라이선스 구매</span><span class="sxs-lookup"><span data-stu-id="45235-177">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="45235-178">다른 구독 구입</span><span class="sxs-lookup"><span data-stu-id="45235-178">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="45235-179">추가 기능 구입 또는 편집</span><span class="sxs-lookup"><span data-stu-id="45235-179">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="45235-180">구독에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="45235-180">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- [<span data-ttu-id="45235-181">라이선스 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="45235-181">Resolve license conflicts</span></span>](../../admin/manage/resolve-license-conflicts.md)
    
- [<span data-ttu-id="45235-182">Yammer 사용자 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="45235-182">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

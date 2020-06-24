---
title: 비즈니스에 대 한 Microsoft 365의 구독 및 라이선스 이해
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
description: '비즈니스에 대 한 Microsoft 365의 구독 및 라이선스에 대해 알아보고, 사용자에 게 라이선스를 할당할 때 라이선스를 할당할 수 있는 사람 및 상황을 파악 합니다. '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844683"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a><span data-ttu-id="901d7-103">비즈니스에 대 한 Microsoft 365의 구독 및 라이선스 이해</span><span class="sxs-lookup"><span data-stu-id="901d7-103">Understand subscriptions and licenses in Microsoft 365 for business</span></span>

<span data-ttu-id="901d7-104">이 문서에서는 구독 및 라이선스 간의 관계에 대해 설명 하 고, 라이선스를 [할당할 수 있는 사람](#find-out-who-can-assign-licenses), 사용자 [에 게 라이선스를 할당할 때 수행 되는 작업](#understand-what-happens-when-you-assign-a-license-to-someone)및 [사용자가 Office를 설치할 수 있는 장치 개수](#how-many-devices-can-people-install-office-on)에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="901d7-105">또한 [비 사용자 사서함의 라이선스 이해](#understand-licenses-for-non-user-mailboxes)에 대 한 링크와 [라이선스 관리에 대 한 문서](#articles-about-managing-licenses)도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="901d7-106">비즈니스를 위해 Microsoft 365 구독을 구입 하는 경우 매달 또는 연간 기준으로 지불 하는 응용 프로그램 및 서비스 집합에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-106">When you buy a subscription to Microsoft 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="901d7-107">구독의 일부로 수신 하는 응용 프로그램 및 서비스는 구입한 제품 (예: 비즈니스용 Microsoft 365 Apps 또는 Microsoft 365 Business Standard)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Microsoft 365 Apps for business or Microsoft 365 Business Standard.</span></span> <span data-ttu-id="901d7-108">[Microsoft 365 구입 페이지](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)에서 각 제품과 함께 제공 되는 내용을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-108">You can review what comes with each product on the [Buy Microsoft 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="901d7-109">[중소 규모 기업을 위해 Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb) 에서 제공 되는 다양 한 라이선스 옵션을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-109">You can review different Licensing options available in [Microsoft 365 for small and medium-sized businesses](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)</span></span>

<span data-ttu-id="901d7-110">구독을 구입할 때 조직의 사용자 수를 기준으로 필요한 라이선스 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-110">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="901d7-111">구입을 완료한 후 사용자 계정을 만들고 각 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-111">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="901d7-112">조직의 요구 사항이 변경 되 면 새 사용자를 수용할 수 있는 라이선스를 추가로 구입 하거나 다른 사용자에 게 라이선스를 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-112">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="901d7-113">구독이 두 개 이상 있는 경우 각 구독에 대해 다른 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-113">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="901d7-114">예를 들어 모든 사용자가 Microsoft 365 Business Standard 구독의 일부로 모든 Microsoft 365 응용 프로그램 및 서비스에 할당 될 수 있지만, 사용자의 하위 집합은 별도의 Visio 구독을 통해 Visio Online에 할당 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-114">For example, all of your users could be assigned to all Microsoft 365 applications and services as part of an Microsoft 365 Business Standard subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="901d7-115">라이선스를 할당할 수 있는 사용자 찾기</span><span class="sxs-lookup"><span data-stu-id="901d7-115">Find out who can assign licenses</span></span>

<span data-ttu-id="901d7-116">Different types of admins can work with licenses in different ways, depending on their roles.</span><span class="sxs-lookup"><span data-stu-id="901d7-116">Different types of admins can work with licenses in different ways, depending on their roles.</span></span> <span data-ttu-id="901d7-117">The following table lists the most common options.</span><span class="sxs-lookup"><span data-stu-id="901d7-117">The following table lists the most common options.</span></span> <span data-ttu-id="901d7-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="901d7-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="901d7-119">**관리자 역할**</span><span class="sxs-lookup"><span data-stu-id="901d7-119">**Admin role**</span></span>|<span data-ttu-id="901d7-120">**라이선스 할당**</span><span class="sxs-lookup"><span data-stu-id="901d7-120">**Assign a license**</span></span>|<span data-ttu-id="901d7-121">**라이선스 제거**</span><span class="sxs-lookup"><span data-stu-id="901d7-121">**Remove a license**</span></span>|<span data-ttu-id="901d7-122">**추가 라이선스 구입**</span><span class="sxs-lookup"><span data-stu-id="901d7-122">**Purchase more licenses**</span></span>|<span data-ttu-id="901d7-123">**계정 삭제**</span><span class="sxs-lookup"><span data-stu-id="901d7-123">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="901d7-124">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="901d7-124">Global admin</span></span>  <br/> |<span data-ttu-id="901d7-125">예</span><span class="sxs-lookup"><span data-stu-id="901d7-125">Yes</span></span>  <br/> |<span data-ttu-id="901d7-126">예</span><span class="sxs-lookup"><span data-stu-id="901d7-126">Yes</span></span>  <br/> |<span data-ttu-id="901d7-127">예</span><span class="sxs-lookup"><span data-stu-id="901d7-127">Yes</span></span>  <br/> |<span data-ttu-id="901d7-128">예</span><span class="sxs-lookup"><span data-stu-id="901d7-128">Yes</span></span>  <br/> |
|<span data-ttu-id="901d7-129">대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="901d7-129">Billing admin</span></span>  <br/> |<span data-ttu-id="901d7-130">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-130">No</span></span>  <br/> |<span data-ttu-id="901d7-131">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-131">No</span></span>  <br/> |<span data-ttu-id="901d7-132">예</span><span class="sxs-lookup"><span data-stu-id="901d7-132">Yes</span></span>  <br/> |<span data-ttu-id="901d7-133">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-133">No</span></span>  <br/> |
|<span data-ttu-id="901d7-134">사용자 관리 관리자</span><span class="sxs-lookup"><span data-stu-id="901d7-134">User management admin</span></span>  <br/> |<span data-ttu-id="901d7-135">예</span><span class="sxs-lookup"><span data-stu-id="901d7-135">Yes</span></span>  <br/> |<span data-ttu-id="901d7-136">예</span><span class="sxs-lookup"><span data-stu-id="901d7-136">Yes</span></span>  <br/> |<span data-ttu-id="901d7-137">아니오</span><span class="sxs-lookup"><span data-stu-id="901d7-137">No</span></span>  <br/> |<span data-ttu-id="901d7-138">예</span><span class="sxs-lookup"><span data-stu-id="901d7-138">Yes</span></span>  <br/> |
|<span data-ttu-id="901d7-139">서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="901d7-139">Service admin</span></span>  <br/> |<span data-ttu-id="901d7-140">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-140">No</span></span>  <br/> |<span data-ttu-id="901d7-141">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-141">No</span></span>  <br/> |<span data-ttu-id="901d7-142">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-142">No</span></span>  <br/> |<span data-ttu-id="901d7-143">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-143">No</span></span>  <br/> |
|<span data-ttu-id="901d7-144">암호 관리자</span><span class="sxs-lookup"><span data-stu-id="901d7-144">Password admin</span></span>  <br/> |<span data-ttu-id="901d7-145">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-145">No</span></span>  <br/> |<span data-ttu-id="901d7-146">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-146">No</span></span>  <br/> |<span data-ttu-id="901d7-147">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-147">No</span></span>  <br/> |<span data-ttu-id="901d7-148">아니요</span><span class="sxs-lookup"><span data-stu-id="901d7-148">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="901d7-149">사용자에게 라이선스를 할당할 때 발생하는 사항 이해</span><span class="sxs-lookup"><span data-stu-id="901d7-149">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="901d7-150">다음 표에는 사용자에게 라이선스를 할당할 때 자동으로 발생하는 일이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-150">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="901d7-151">**구독에 이 서비스가 있는 경우**</span><span class="sxs-lookup"><span data-stu-id="901d7-151">**If the subscription has this service**</span></span>|<span data-ttu-id="901d7-152">**자동으로 일어나는 일**</span><span class="sxs-lookup"><span data-stu-id="901d7-152">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="901d7-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="901d7-153">Exchange Online</span></span>  <br/> |<span data-ttu-id="901d7-154">해당 사용자의 사서함이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-154">A mailbox is created for that person.</span></span>  <br/> <span data-ttu-id="901d7-155">이 작업을 완료 하는 데 필요한 SLA에 대 한 자세한 내용은 "설정 ..."을 참조 하십시오 [. Microsoft 365 관리 센터의 메시지](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)</span><span class="sxs-lookup"><span data-stu-id="901d7-155">To learn about the SLA for this task to be completed, see ["Setting up..." messages in the Microsoft 365 admin center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).</span></span> |
|<span data-ttu-id="901d7-156">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="901d7-156">SharePoint Online</span></span>  <br/> |<span data-ttu-id="901d7-157">기본 SharePoint Online 팀 사이트에 대한 편집 권한이 해당 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-157">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="901d7-158">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="901d7-158">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="901d7-159">사용자가 라이선스 관련 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-159">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="901d7-160">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="901d7-160">Microsoft 365 Apps for enterprise</span></span>  <br/> |<span data-ttu-id="901d7-161">사용자는 조직의 최대 5대의 Mac 또는 PC, 최대 5대의 태블릿, 최대 5대의 스마트폰에 Microsoft Office를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-161">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="901d7-162">사용자가 Office를 설치할 수 있는 장치는 몇 개인가요?</span><span class="sxs-lookup"><span data-stu-id="901d7-162">How many devices can people install Office on?</span></span>

<span data-ttu-id="901d7-163">구독에 다음 제품이 포함되는 경우 각 사용자는 최대 5대의 PC 또는 Mac, 최대 5대의 태블릿, 최대 5대의 전화기에 Office를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d7-163">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="901d7-164">비즈니스용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="901d7-164">Microsoft 365 Apps for business</span></span>
    
- <span data-ttu-id="901d7-165">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="901d7-165">Microsoft 365 Business Standard</span></span>
    
- <span data-ttu-id="901d7-166">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="901d7-166">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="901d7-167">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="901d7-167">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="901d7-168">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="901d7-168">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="901d7-169">비사용자 사서함의 라이선스 이해</span><span class="sxs-lookup"><span data-stu-id="901d7-169">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="901d7-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="901d7-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span></span> <span data-ttu-id="901d7-171">For more about non-user mailboxes, see the following articles:</span><span class="sxs-lookup"><span data-stu-id="901d7-171">For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="901d7-172">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="901d7-172">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="901d7-173">다른 모든 Microsoft 365 계획에 대 한 [Exchange Online의 공유 사서함](https://go.microsoft.com/fwlink/p/?linkid=847433)</span><span class="sxs-lookup"><span data-stu-id="901d7-173">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Microsoft 365 plans.</span></span> 
    
- [<span data-ttu-id="901d7-174">대화방 사서함 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="901d7-174">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [<span data-ttu-id="901d7-175">장비 사서함 관리</span><span class="sxs-lookup"><span data-stu-id="901d7-175">Manage Equipment Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="901d7-176">라이선스 관리에 대 한 문서</span><span class="sxs-lookup"><span data-stu-id="901d7-176">Articles about managing licenses</span></span>

- [<span data-ttu-id="901d7-177">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="901d7-177">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="901d7-178">사용자의 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="901d7-178">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="901d7-179">구독용 라이선스 구매</span><span class="sxs-lookup"><span data-stu-id="901d7-179">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="901d7-180">다른 구독 구입</span><span class="sxs-lookup"><span data-stu-id="901d7-180">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="901d7-181">추가 기능 구입 또는 편집</span><span class="sxs-lookup"><span data-stu-id="901d7-181">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="901d7-182">구독에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="901d7-182">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- [<span data-ttu-id="901d7-183">라이선스 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="901d7-183">Resolve license conflicts</span></span>](../../admin/manage/resolve-license-conflicts.md)
    
- [<span data-ttu-id="901d7-184">Yammer 사용자 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="901d7-184">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

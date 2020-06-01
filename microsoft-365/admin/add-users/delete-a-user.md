---
title: 조직에서 사용자 삭제
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 사용자 계정을 삭제 하는 방법에 대해 알아봅니다. 사용자의 전자 메일, OneDrive 콘텐츠, 제품 라이선스를 유지할지 아니면 지불할 지를 결정 합니다.
ms.openlocfilehash: 81243286b70985082f8b671d7e021735a76cffc4
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431680"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="4c49c-104">조직에서 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="4c49c-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="4c49c-105">**회사 또는 학교에서 사용 하는 Microsoft 365 사용자 계정을 *직접* 삭제 하는 방법을 찾으십니까? 회사 또는 대학에서 기술 지원 서비스에 문의 하 여 다음 단계를 수행 하세요.**</span><span class="sxs-lookup"><span data-stu-id="4c49c-105">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="4c49c-106">사용자 삭제에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="4c49c-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="4c49c-107">비즈니스 또는 학교에 대 한 [Microsoft 365 전역 관리자](about-admin-roles.md) 또는 사용자 관리 권한이 있는 사용자만 사용자 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-107">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="4c49c-108">30일 내에 계정을 [복원](restore-user.md)하지 않으면 사용자 데이터가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="4c49c-p102">사용자의 OneDrive 데이터를 유지하려는 경우 다른 위치로 이동합니다. 계정을 삭제한 후 최대 30일까지 이 작업을 수행할 수 있습니다. [이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요. 해당 SharePoint 파일을 이동할 필요는 없으며 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="4c49c-p103">사용자의 전자 메일을 유지하려는 경우 계정을 삭제하기 **전에** 전자 메일을 다른 위치로 이동합니다. 계정을 이미 삭제한 경우 아직 30일이 경과하지 않았으면 계정을 복원한 뒤 전자 메일 데이터를 이동한 다음에 계정을 삭제합니다. [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md)(이전 사용자의 데이터 액세스 및 백업)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="4c49c-116">Office 365 Enterprise e 3과 같은 엔터프라이즈 구독을 사용 하는 경우 삭제 된 사용자 계정의 사서함 데이터를 *비활성 사서함*으로 설정 하 여 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="4c49c-117">자세한 내용은 [Office 365에서 비활성 사서함 관리](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="4c49c-118">전역 관리자: 사용자 삭제, 해당 라이선스에 대 한 지불 중지 및 전자 메일 및 OneDrive 콘텐츠로 수행할 작업 선택</span><span class="sxs-lookup"><span data-stu-id="4c49c-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="4c49c-119">전역 관리자 인 경우 사용자를 삭제 하는 경우 다른 사용자에 게 전자 메일에 대 한 액세스 권한을 부여 하 고 OneDrive 콘텐츠로 수행할 작업을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="4c49c-120">고려할 사항...</span><span class="sxs-lookup"><span data-stu-id="4c49c-120">Things to consider...</span></span>

<span data-ttu-id="4c49c-121">시작 하기 전에 사용자의 전자 메일 및 OneDrive 콘텐츠를 사용 하 여 수행할 작업과 라이선스를 유지할지, 아니면 비용을 지불할 지를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4c49c-122">제품 라이선스</span><span class="sxs-lookup"><span data-stu-id="4c49c-122">Product licenses</span></span>  <br/> |<span data-ttu-id="4c49c-123">사용자 로부터 라이선스를 제거 하 고 해당 라이선스에 대 한 비용 지불을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="4c49c-124">이 옵션을 선택 하면 구독이 구독에서 자동으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="4c49c-125">파트너 또는 볼륨 라이선스를 통해 **라이선스를 구입한 경우에는 제거할 수 없습니다** .</span><span class="sxs-lookup"><span data-stu-id="4c49c-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="4c49c-126">연간 요금제에 대 한 비용을 지불 하거나 대금 청구 주기의 중간에 있는 경우에는 약정을 완료할 때까지 구독에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="4c49c-127">OneDrive 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="4c49c-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="4c49c-128">사용자가 파일을 OneDrive에 저장 한 경우에는 다른 사용자에 게 이러한 파일에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="4c49c-129">보관 하려는 파일을 OneDrive 파일에 대해 설정 된 보존 기간 내에 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="4c49c-130">**기본적으로 보존 기간은 30 일입니다.**</span><span class="sxs-lookup"><span data-stu-id="4c49c-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="4c49c-131">사용자를 삭제 한 후 보존 기간 내에 파일을 이동 하지 않으면 OneDrive 콘텐츠가 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="4c49c-132">삭제 된 계정에 대해 OneDrive 파일을 보존 하는 기간 (일)을 높이려면 [삭제 한 사용자에 대 한 onedrive 보존 설정을](https://docs.microsoft.com/onedrive/set-retention)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://docs.microsoft.com/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="4c49c-133">**중요 한!**</span><span class="sxs-lookup"><span data-stu-id="4c49c-133">**Important!**</span></span> <span data-ttu-id="4c49c-134">삭제 된 사용자가 개인 컴퓨터를 사용 하 여 SharePoint 및 OneDrive에서 파일을 다운로드 한 경우에는 컴퓨터에 저장 된 파일을 지울 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="4c49c-135">OneDrive에서 동기화 된 모든 파일에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="4c49c-136">전자 메일</span><span class="sxs-lookup"><span data-stu-id="4c49c-136">Email</span></span>  <br/> | <span data-ttu-id="4c49c-137">삭제 된 사용자의 전자 메일에 대해 다른 사용자에 게 액세스 권한을 부여 하면 삭제 된 사용자의 사서함이 공유 사서함으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="4c49c-138">그런 다음 새 사서함 소유자가 사서함에 액세스 하 고 새 전자 메일을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="4c49c-139">또한 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="4c49c-140">표시 이름 변경-활성 사용자 목록에서 공유 사서함을 쉽게 식별할 수 있도록 표시 이름을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="4c49c-141">자동 회신 설정-이미 예의 지키고 자동 회신을 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="4c49c-142">조직과 외부의 사용자에 게 서로 다른 자동 회신을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="4c49c-143">별칭 정리-사용자의 추가 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="4c49c-144">일부 조직에서는이를 사용 하지 않으므로 여기에서 다른 작업을 수행 하지 않아도 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="4c49c-145">사용자에 게 별칭이 있는 경우 해당 전자 메일 주소를 다시 사용할 수 있도록이를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="4c49c-146">그렇지 않으면 삭제 된 사서함의 보존 기간이 지날 때까지 해당 전자 메일 주소를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-146">Otherwise, you can't re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="4c49c-147">기본적으로 삭제 된 사서함은 30 일간 복구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="4c49c-148">자세한 내용은 [Exchange Online에서 사용자 사서함 삭제 또는 복원을](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="4c49c-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c49c-149">Active Directory</span></span>  <br/> |<span data-ttu-id="4c49c-150">회사에서 Azure AD와 동기화 되는 **Active directory** 를 사용 하는 경우 active directory에서 사용자 계정을 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="4c49c-151">Office 365를 통해서는 이렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-151">You can't do it through Office 365.</span></span> <span data-ttu-id="4c49c-152">자세한 내용은 [사용자 계정 삭제](https://go.microsoft.com/fwlink/p/?linkid=841808)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4c49c-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="4c49c-153">시작하기</span><span class="sxs-lookup"><span data-stu-id="4c49c-153">Get started</span></span>

<span data-ttu-id="4c49c-154">안내가 제공 되는 환경에서는 사용자를 삭제 하는 단계를 안내 하므로 시작 하려면 다음을 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-154">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4c49c-155">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4c49c-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4c49c-156">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4c49c-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4c49c-157">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4c49c-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="4c49c-158">삭제 하려는 사용자를 선택 하 고 **사용자 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-158">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="4c49c-159">사용자 관리 관리자: Office 365에서 하나 이상의 사용자를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-159">User management admin: Delete one or more users from Office 365</span></span>


> [!IMPORTANT]
> <span data-ttu-id="4c49c-160">사용자 계정이 [공유 사서함으로 변환](../email/convert-user-mailbox-to-shared-mailbox.md) 되었거나 계정에 전자 메일 전달을 설정한 경우에는 해당 계정을 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-160">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="4c49c-161">이러한 기능은 여전히 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-161">Those functions still need the account.</span></span> <span data-ttu-id="4c49c-162">공유 사서함에는 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-162">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="4c49c-163">계정을 공유 사서함으로 변환한 경우 [에는 라이선스에 대 한 비용 지불을 중지할](#stop-paying-for-the-license)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-163">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="4c49c-164">계정에 전자 메일 전달을 설정한 경우에는 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-164">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="4c49c-165">이렇게 하면 전자 메일 전달이 중지 되 고 사서함이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-165">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4c49c-166">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4c49c-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="4c49c-167">삭제할 사용자의 이름을 선택 하 고 **기타 옵션** (**...**)을 선택한 다음 **사용자 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-167">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="4c49c-168">사용자 계정을 삭제 했지만 **여전히 라이선스에 대 한**비용을 지불 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-168">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="4c49c-169">라이선스에 대 한 비용 지불을 중지 하려면 다음 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-169">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="4c49c-170">또는 다른 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-170">Or, you can assign the license to another user.</span></span> <span data-ttu-id="4c49c-171">자동으로 사용자에 게 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-171">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4c49c-172">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4c49c-172">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4c49c-173">삭제 하려는 사용자의 이름을 선택 하 고 **대량 작업** 창에서 **사용자 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-173">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="4c49c-174">사용자 계정을 삭제 했지만 **여전히 라이선스에 대 한**비용을 지불 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-174">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="4c49c-175">라이선스에 대 한 비용 지불을 중지 하려면 다음 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-175">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="4c49c-176">또는 다른 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-176">Or, you can assign the license to another user.</span></span> <span data-ttu-id="4c49c-177">자동으로 사용자에 게 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-177">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4c49c-178">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="4c49c-178">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4c49c-179">삭제 하려는 사용자의 이름을 선택 하 고 **대량 작업** 창에서 **사용자 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-179">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="4c49c-180">사용자 계정을 삭제 했지만 **여전히 라이선스에 대 한**비용을 지불 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-180">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="4c49c-181">라이선스에 대 한 비용 지불을 중지 하려면 다음 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-181">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="4c49c-182">또는 다른 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-182">Or, you can assign the license to another user.</span></span> <span data-ttu-id="4c49c-183">자동으로 사용자에 게 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-183">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="4c49c-184">라이선스 비용 지불 중지</span><span class="sxs-lookup"><span data-stu-id="4c49c-184">Stop paying for the license</span></span>

<span data-ttu-id="4c49c-185">라이선스 수를 줄이는 것은 전역 관리자 또는 대금 청구 관리자만 수행할 수 있는 별도의 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-185">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4c49c-186">관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-186">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span> <span data-ttu-id="4c49c-187">이 옵션이 표시 되지 않으면 전역 관리자 또는 대금 청구 관리자가 아니므로이 단계를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-187">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="4c49c-188">구독을 하나 이상 선택한 다음 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이선스에 대해 비용을 지불 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-188">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="4c49c-189">나중에 비즈니스에 다른 사람을 추가 하는 단계를 진행할 때 동시에 라이선스를 구입 하 라는 메시지가 표시 되며,이는 한 단계만 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-189">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4c49c-190">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-190">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="4c49c-191">이 옵션이 표시 되지 않으면 전역 관리자 또는 대금 청구 관리자가 아니므로이 단계를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-191">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="4c49c-192">구독을 하나 이상 선택한 다음 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이선스에 대해 비용을 지불 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-192">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="4c49c-193">나중에 비즈니스에 다른 사람을 추가 하는 단계를 진행할 때 동시에 라이선스를 구입 하 라는 메시지가 표시 되며,이는 한 단계만 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-193">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4c49c-194">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-194">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="4c49c-195">이 옵션이 표시 되지 않으면 전역 관리자 또는 대금 청구 관리자가 아니므로이 단계를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-195">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="4c49c-196">구독을 하나 이상 선택한 다음 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이선스에 대해 비용을 지불 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-196">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="4c49c-197">나중에 비즈니스에 다른 사람을 추가 하는 단계를 진행할 때 동시에 라이선스를 구입 하 라는 메시지가 표시 되며,이는 한 단계만 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-197">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="4c49c-198">여러 사용자를 동시에 삭제</span><span class="sxs-lookup"><span data-stu-id="4c49c-198">Delete many users at the same time</span></span>

<span data-ttu-id="4c49c-199">[Get-msoluser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-199">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="4c49c-200">사용자 삭제와 관련된 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4c49c-200">Fix issues with deleting a user</span></span>

<span data-ttu-id="4c49c-201">사용자를 삭제할 때 발생할 수 있는 가장 일반적인 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-201">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="4c49c-202">**"사용자를 삭제할 수 없습니다. 라는 줄에 오류 메시지가 표시 됩니다. 나중에 다시 시도 하세요. "**</span><span class="sxs-lookup"><span data-stu-id="4c49c-202">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="4c49c-203">계정에 전자 메일 전달이 설정 되어 있는지, 아니면 공유 사서함으로 변환 붙여넣으세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-203">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="4c49c-204">두 경우 모두 해당 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-204">Both of these will cause that error.</span></span> <span data-ttu-id="4c49c-205">전자 메일 전달이 있거나 공유 사서함으로 변환 된 경우에는 계정을 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4c49c-205">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="4c49c-206">**사용자를 삭제하기 위한 적절한 권한이 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="4c49c-206">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="4c49c-207">[Microsoft 365 전역 관리자 또는 사용자 관리 관리자](about-admin-roles.md) 만 사용자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-207">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="4c49c-208">일반적으로 학교 또는 회사의 기술 지원 담당자입니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-208">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="4c49c-p122">**사용자를 삭제했지만 해당 이름이 전체 주소록에 계속 나타납니다**. 회사에서 Active Directory를 사용하는 경우 이 문제가 발생합니다. Active Directory에서 사용자 계정을 삭제해야 합니다. 지침은 다음 TechNet 문서를 참조하세요. [사용자 계정 삭제.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="4c49c-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="4c49c-213">**컴퓨터에서 Microsoft 365을 (를) 삭제 하 시겠습니까? [구독 취소](../../commerce/subscriptions/cancel-your-subscription.md)로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c49c-213">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="4c49c-214">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4c49c-214">Related articles</span></span>

[<span data-ttu-id="4c49c-215">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="4c49c-215">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="4c49c-216">사서함을 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="4c49c-216">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="4c49c-217">Office 365에서 이전 직원 제거</span><span class="sxs-lookup"><span data-stu-id="4c49c-217">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="4c49c-218">Office 365에 새 직원 추가</span><span class="sxs-lookup"><span data-stu-id="4c49c-218">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="4c49c-219">[사용자 계정 삭제](https://go.microsoft.com/fwlink/p/?linkid=841808): 회사에서 Azure AD와 동기화 되는 **Active Directory** 를 사용 하는 경우 이러한 지침을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-219">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="4c49c-220">Office 365를 통해서는 이렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c49c-220">You can't do it through Office 365.</span></span>
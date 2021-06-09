---
title: 조직에서 사용자 삭제
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 사용자 계정을 삭제하는 방법과 사용자의 전자 메일 및 전자 메일로 할 OneDrive 콘텐츠 및 제품 라이선스를 유지할지 여부에 대해 자세히 알아보겠습니다.
ms.openlocfilehash: 43a57a69ce0d810af2b029f49c15d32d75a4dc33
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683142"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="30356-103">조직에서 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="30356-103">Delete a user from your organization</span></span>
  
<span data-ttu-id="30356-104">**직장이나 학교에서  사용하는 Microsoft 365 계정을 삭제하는 방법을 찾고 있나요? 이 단계를 수행하기 위해 직장이나 대학의 기술 지원에 문의하세요.**</span><span class="sxs-lookup"><span data-stu-id="30356-104">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="30356-105">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="30356-105">Before you begin</span></span>

- <span data-ttu-id="30356-106">전역 관리자 [](about-admin-roles.md) 또는 Microsoft 365 사용자 관리 권한이 있는 사용자만 사용자 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-106">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span>
- <span data-ttu-id="30356-107">30일 내에 계정을 [복원](restore-user.md)하지 않으면 사용자 데이터가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="30356-107">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span>
- <span data-ttu-id="30356-108">사용자의 OneDrive 데이터를 유지하려는 경우 다른 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-108">If you want to keep the user's OneDrive data, move it to a different location.</span></span> <span data-ttu-id="30356-109">계정을 삭제한 후 최대 30일까지 데이터를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-109">You can even move the data up to 30 days after deleting the account.</span></span> <span data-ttu-id="30356-110">[이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-110">See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span> <span data-ttu-id="30356-111">해당 SharePoint 파일을 이동할 필요는 없으며 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-111">You don't need to move their SharePoint files; you'll still have access to them.</span></span>
- <span data-ttu-id="30356-p102">사용자의 전자 메일을 유지하려는 경우 계정을 삭제하기 **전에** 전자 메일을 다른 위치로 이동합니다. 계정을 이미 삭제한 경우 아직 30일이 경과하지 않았으면 계정을 복원한 뒤 전자 메일 데이터를 이동한 다음에 계정을 삭제합니다. [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md)(이전 사용자의 데이터 액세스 및 백업)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-p102">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
- <span data-ttu-id="30356-115">Enterprise E3와 같은 Office 365 Enterprise 구독이 있는 경우 삭제된 사용자 계정의 사서함 데이터를 비활성 사서함으로 전환하여 보존할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="30356-115">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="30356-116">자세한 내용은 [Office 365에서 비활성 사서함 관리](../../compliance/inactive-mailboxes-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-116">To learn more, see [Manage inactive mailboxes in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).</span></span>

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="30356-117">전역 관리자: 사용자 삭제, 라이선스 비용 지불 중지, 전자 메일 및 콘텐츠로 할 OneDrive 선택</span><span class="sxs-lookup"><span data-stu-id="30356-117">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="30356-118">전역 관리자인 경우 사용자를 삭제할 때 다른 사용자에게 전자 메일에 대한 액세스 권한을 부여하고 해당 전자 메일 콘텐츠로 할 작업을 OneDrive 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-118">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span>

### <a name="things-to-consider"></a><span data-ttu-id="30356-119">고려할 사항</span><span class="sxs-lookup"><span data-stu-id="30356-119">Things to consider</span></span>

<span data-ttu-id="30356-120">시작하기 전에 사용자의 전자 메일 및 전자 메일 콘텐츠로 OneDrive, 라이선스를 유지하거나 라이선스 비용 지불을 중지할지 여부를 생각해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-120">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|<span data-ttu-id="30356-121">항목</span><span class="sxs-lookup"><span data-stu-id="30356-121">Item</span></span> | <span data-ttu-id="30356-122">설명</span><span class="sxs-lookup"><span data-stu-id="30356-122">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="30356-123">제품 라이선스</span><span class="sxs-lookup"><span data-stu-id="30356-123">Product licenses</span></span>  <br/> |<span data-ttu-id="30356-124">사용자에서 라이선스를 제거하고 구독에서 라이선스를 제거하여 해당 라이선스 비용 지불을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-124">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="30356-125">이 옵션을 선택하면 라이선스가 구독에서 자동으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="30356-125">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="30356-126">**파트너 또는 볼륨** 라이선스를 통해 라이선스를 구입한 경우 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-126">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="30356-127">연간 요금제 비용을 지불하거나 청구 주기가 진행 중이면 약정이 완료될 때까지 구독에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-127">If you're paying for an annual plan or if you're in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="30356-128">OneDrive 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="30356-128">OneDrive content</span></span>  <br/> |<span data-ttu-id="30356-129">사용자가 파일을 저장하여 파일을 OneDrive 다른 사용자에게 이러한 파일에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-129">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="30356-130">보존 기간 내에 보관할 파일을 이동해야 합니다. 이 기간에는 해당 파일에 대해 OneDrive 합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-130">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="30356-131">**기본적으로 보존 기간은 30일입니다.**</span><span class="sxs-lookup"><span data-stu-id="30356-131">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="30356-132">사용자를 삭제한 후 보존 기간 내에 파일을 이동하지 않는 경우 OneDrive 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="30356-132">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="30356-133">삭제된 계정에 대한 OneDrive 보존하는 기간을 늘리기 위해 삭제된 사용자에 대한 OneDrive 보존 설정 [을 참조합니다.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="30356-133">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="30356-134">**중요!**</span><span class="sxs-lookup"><span data-stu-id="30356-134">**Important!**</span></span> <span data-ttu-id="30356-135">삭제된 사용자가 개인 컴퓨터를 사용하여 SharePoint 및 OneDrive 파일을 다운로드하는 경우 컴퓨터에 저장된 파일을 지우는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-135">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="30356-136">이러한 파일은 해당 파일에서 동기화된 모든 파일에 계속 액세스할 수 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="30356-136">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="30356-137">전자 메일</span><span class="sxs-lookup"><span data-stu-id="30356-137">Email</span></span>  <br/> | <span data-ttu-id="30356-138">삭제된 사용자의 전자 메일에 다른 사용자에게 액세스 권한을 부여하면 삭제된 사용자의 사서함이 공유 사서함으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="30356-138">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="30356-139">그러면 새 사서함 소유자가 사서함에 액세스하여 새 전자 메일을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-139">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="30356-140">다음 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-140">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="30356-141">표시 이름 변경 - 활성 사용자 목록에서 공유 사서함을 쉽게 식별할 수 있도록 표시 이름을 변경하는 **것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-141">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the **Active users** list.</span></span>  <br/>  <span data-ttu-id="30356-142">자동 회신 설정 - 이미 정중한 자동 회신을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-142">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="30356-143">조직 내 사용자와 조직 외부의 사용자에 대해 다른 자동 응답을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-143">You can send different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="30356-144">별칭 정리 - 별칭은 사용자를 위한 추가 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="30356-144">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="30356-145">일부 조직에서는 사용하지 않습니다. 따라서 사용하지 않는 조직이 없는 경우 여기에서 다른 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-145">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="30356-146">사용자에게 별칭이 있는 경우 해당 전자 메일 주소를 다시 사용할 수 있도록 별칭을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-146">If the user does have aliases, we recommend removing them so that you can reuse those email addresses.</span></span> <span data-ttu-id="30356-147">그렇지 않으면 삭제된 사서함의 보존 기간이 지나야 해당 전자 메일 주소를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-147">Otherwise, you can't reuse those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="30356-148">기본적으로 삭제된 사서함은 30일 동안 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-148">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="30356-149">자세한 내용은 [Delete or restore user mailboxes in Exchange Online.](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)</span><span class="sxs-lookup"><span data-stu-id="30356-149">For more information, see  [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="30356-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="30356-150">Active Directory</span></span>  <br/> |<span data-ttu-id="30356-151">비즈니스에서 Azure AD와 동기화되는 **Active Directory를** 사용하는 경우 Active Directory에서 사용자 계정을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-151">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="30356-152">Office 365를 통해서는 이렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-152">You can't do it through Office 365.</span></span> <span data-ttu-id="30356-153">자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="30356-153">For instructions, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>  <br/> |

### <a name="get-started"></a><span data-ttu-id="30356-154">시작하기</span><span class="sxs-lookup"><span data-stu-id="30356-154">Get started</span></span>

<span data-ttu-id="30356-155">안내된 환경은 사용자를 삭제하는 단계를 안내하기 때문에 시작하는 방법에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="30356-156">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="30356-157">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="30356-158">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="30356-159">삭제할 사용자를 선택한 다음 사용자 삭제 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="30356-159">Select the user that you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="30356-160">사용자 관리 관리자: 사용자 계정에서 하나 이상의 Office 365</span><span class="sxs-lookup"><span data-stu-id="30356-160">User management admin: Delete one or more users from Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30356-161">공유 사서함으로 변환하거나 계정에 전자 메일 [](../email/convert-user-mailbox-to-shared-mailbox.md) 전달을 설정한 경우 사용자 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-161">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="30356-162">이러한 함수에는 여전히 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-162">Those functions still need the account.</span></span> <span data-ttu-id="30356-163">공유 사서함에는 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-163">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="30356-164">계정을 공유 사서함으로 변환한 경우 라이선스 비용 지불을 [중지할 수 있습니다.](#stop-paying-for-the-license)</span><span class="sxs-lookup"><span data-stu-id="30356-164">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="30356-165">계정에 전자 메일 전달을 설정한 경우 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-165">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="30356-166">이렇게 하면 전자 메일 전달이 중지된 다음 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="30356-166">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="30356-167">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="30356-168">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="30356-169">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="30356-170">삭제할 사용자의 이름을 선택하고 세 개의 점(추가 작업)을 선택한 다음 사용자 삭제 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="30356-170">Select the names of the users that you want to delete, select the three dots (more actions), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="30356-171">사용자의 계정을 삭제한 경우 라이선스 비용은 계속 **지불하고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="30356-171">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="30356-172">라이선스 비용 지불을 중지하는 다음 절차를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-172">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="30356-173">또는 다른 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-173">Or, you can assign the license to another user.</span></span> <span data-ttu-id="30356-174">자동으로 누군가에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-174">It won't be assigned to someone automatically.</span></span>

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="30356-175">라이선스 비용 지불 중지</span><span class="sxs-lookup"><span data-stu-id="30356-175">Stop paying for the license</span></span>

<span data-ttu-id="30356-176">라이선스 수를 줄이는 것은 전역 관리자 또는 대금 청구 관리자만 수행할 수 있는 별도의 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="30356-176">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="30356-177">관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-177">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="30356-178">관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="30356-179">관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">내 상품</a>페이지로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-179">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="30356-180">제품 **탭에서** 라이선스를 제거할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-180">On the **Products** tab, select the subscription that you want to remove licenses for.</span></span>

3. <span data-ttu-id="30356-181">구독 세부 정보 페이지에서 **라이선스 제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-181">On the subscription details page, select **Remove licenses**.</span></span>

4. <span data-ttu-id="30356-182">라이선스 **제거 창의** **새** 수량 에서  총 라이선스 상자에 이 구독에 대해 원하는 총 라이선스 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-182">In the **Remove licenses** pane, under **New quantity**, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="30356-183">예를 들어 라이선스가 100개인 경우 5개의 라이선스를 제거하려면 95를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-183">For example, if you have 100 licenses and you want to remove five of them, enter 95.</span></span>

5. <span data-ttu-id="30356-184">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-184">Select **Save**.</span></span>

<span data-ttu-id="30356-185">나중에 다른 사람을 비즈니스에 추가하는 단계를 진행할 때 한 단계만 수행하면 라이선스를 동시에 구입하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30356-185">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="30356-186">동시에 여러 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="30356-186">Delete many users at the same time</span></span>

<span data-ttu-id="30356-187">[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-187">See the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="30356-188">사용자 삭제와 관련된 문제 해결</span><span class="sxs-lookup"><span data-stu-id="30356-188">Fix issues with deleting a user</span></span>

<span data-ttu-id="30356-189">다음은 사용자를 삭제하는 경우 발생하는 가장 일반적인 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="30356-189">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="30356-190">**"사용자를 삭제할 수 없습니다. 나중에 다시 시도하세요."**</span><span class="sxs-lookup"><span data-stu-id="30356-190">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="30356-191">계정에 전자 메일 전달이 설정되어 있는지 또는 공유 사서함으로 변환되어 있는지 다시 한 번 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-191">Double-check whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="30356-192">이 두 가지 모두 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-192">Both of these will cause that error.</span></span> <span data-ttu-id="30356-193">전자 메일 전달이 있는 계정이나 공유 사서함으로 변환된 경우 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-193">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="30356-194">**사용자를 삭제하기 위한 적절한 권한이 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="30356-194">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="30356-195">전역 관리자 또는 [Microsoft 365 관리자인](about-admin-roles.md) 사용자만 사용자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-195">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="30356-196">일반적으로 학교 또는 회사의 기술 지원 담당자입니다.</span><span class="sxs-lookup"><span data-stu-id="30356-196">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="30356-197">사용자를 삭제하지만 해당 이름은 전체 주소 책 **에 계속 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="30356-197">**You delete the user but their name continues appear in your global address book**.</span></span> <span data-ttu-id="30356-198">이 문제는 기업에서 Active Directory를 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-198">This happens when a business is using Active Directory.</span></span> <span data-ttu-id="30356-199">Active Directory에서 사용자 계정을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30356-199">You must delete the users account from Active Directory.</span></span> <span data-ttu-id="30356-200">자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="30356-200">For instructions, see [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span></span>

<span data-ttu-id="30356-201">**컴퓨터에서 Microsoft 365 삭제하고 싶나요? 구독 [취소로 이동하세요.](../../commerce/subscriptions/cancel-your-subscription.md)**</span><span class="sxs-lookup"><span data-stu-id="30356-201">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>

## <a name="related-content"></a><span data-ttu-id="30356-202">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="30356-202">Related content</span></span>

<span data-ttu-id="30356-203">[사용자](restore-user.md) 복원(문서)</span><span class="sxs-lookup"><span data-stu-id="30356-203">[Restore a user](restore-user.md) (article)</span></span>\
<span data-ttu-id="30356-204">[사서함 영구](/exchange/permanently-delete-a-mailbox-exchange-2013-help) 삭제(문서)</span><span class="sxs-lookup"><span data-stu-id="30356-204">[Permanently delete a mailbox](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (article)</span></span>\
<span data-ttu-id="30356-205">[이전 직원을 제거합니다Office 365(문서)\](remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="30356-205">[Remove a former employee from Office 365](remove-former-employee.md) (article)\</span></span>
<span data-ttu-id="30356-206">[새 직원을 추가하여](add-new-employee.md) Office 365(문서)</span><span class="sxs-lookup"><span data-stu-id="30356-206">[Add a new employee to Office 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="30356-207">[사용자 계정 삭제:](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))비즈니스에서 Azure AD와 동기화되는 **Active Directory를** 사용하는 경우 다음 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="30356-207">[Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="30356-208">Office 365를 통해서는 이렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30356-208">You can't do it through Office 365.</span></span> <span data-ttu-id="30356-209">(문서)</span><span class="sxs-lookup"><span data-stu-id="30356-209">(article)</span></span>
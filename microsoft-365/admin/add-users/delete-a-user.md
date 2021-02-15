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
description: 사용자 계정을 삭제하는 방법을 학습합니다. 사용자의 전자 메일 및 OneDrive 콘텐츠로 할 작업을 결정하십시오. 또한 제품 라이선스를 유지할지 아니면 그에 대한 지불을 중지할지 여부를 결정하십시오.
ms.openlocfilehash: 45cf8b9173a3a4260fe664b809f47ab14b57d9fe
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551379"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="40437-105">조직에서 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="40437-105">Delete a user from your organization</span></span>
  
<span data-ttu-id="40437-106">**직장이나 학교에서 사용하는 *Microsoft* 365 사용자 계정을 삭제하는 방법을 찾고 있나요? 이러한 단계를 수행하기 위해 직장이나 대학의 기술 지원에 문의하세요.**</span><span class="sxs-lookup"><span data-stu-id="40437-106">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>

## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="40437-107">사용자 삭제에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="40437-107">What you need to know about deleting users</span></span>

- <span data-ttu-id="40437-108">비즈니스 또는 학교에 [대한 Microsoft 365](about-admin-roles.md) 전역 관리자 또는 사용자 관리 권한이 있는 사용자만 사용자 계정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-108">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span>
- <span data-ttu-id="40437-109">30일 내에 계정을 [복원](restore-user.md)하지 않으면 사용자 데이터가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="40437-109">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span>
- <span data-ttu-id="40437-110">사용자의 OneDrive 데이터를 유지하려는 경우 다른 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-110">If you want to keep the user's OneDrive data, move it to a different location.</span></span> <span data-ttu-id="40437-111">계정을 삭제한 후 최대 30일까지 데이터를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-111">You can even move the data up to 30 days after deleting the account.</span></span> <span data-ttu-id="40437-112">[이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40437-112">See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span> <span data-ttu-id="40437-113">해당 SharePoint 파일을 이동할 필요는 없으며 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-113">You don't need to move their SharePoint files; you'll still have access to them.</span></span>
- <span data-ttu-id="40437-p103">사용자의 전자 메일을 유지하려는 경우 계정을 삭제하기 **전에** 전자 메일을 다른 위치로 이동합니다. 계정을 이미 삭제한 경우 아직 30일이 경과하지 않았으면 계정을 복원한 뒤 전자 메일 데이터를 이동한 다음에 계정을 삭제합니다. [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md)(이전 사용자의 데이터 액세스 및 백업)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40437-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
- <span data-ttu-id="40437-117">Office 365 Enterprise E3와 같은 엔터프라이즈 구독이 있는 경우 삭제된 사용자 계정의 사서함 데이터를 비활성 사서함으로 전환하여 보존할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="40437-117">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="40437-118">자세한 내용은 [Office 365에서 비활성 사서함 관리](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40437-118">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="40437-119">전역 관리자: 사용자 삭제, 라이선스 비용 지불 중지, 전자 메일 및 OneDrive 콘텐츠로 할 일 선택</span><span class="sxs-lookup"><span data-stu-id="40437-119">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="40437-120">전역 관리자인 경우 사용자를 삭제할 때 다른 사용자에게 전자 메일에 대한 액세스 권한을 부여하고 OneDrive 콘텐츠로 할 작업을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-120">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span>

### <a name="things-to-consider"></a><span data-ttu-id="40437-121">고려할 사항...</span><span class="sxs-lookup"><span data-stu-id="40437-121">Things to consider...</span></span>

<span data-ttu-id="40437-122">시작하기 전에 사용자의 전자 메일 및 OneDrive 콘텐츠로 무엇을 할 것인지, 라이선스를 유지하거나 라이선스 비용을 지불하지 못하게 할지 여부를 생각해 본 후 생각해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-122">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|<span data-ttu-id="40437-123">항목</span><span class="sxs-lookup"><span data-stu-id="40437-123">Item</span></span> | <span data-ttu-id="40437-124">설명</span><span class="sxs-lookup"><span data-stu-id="40437-124">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="40437-125">제품 라이선스</span><span class="sxs-lookup"><span data-stu-id="40437-125">Product licenses</span></span>  <br/> |<span data-ttu-id="40437-126">사용자에서 라이선스를 제거하고 구독에서 라이선스를 제거하여 해당 라이선스 결제를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-126">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="40437-127">이 옵션을 선택하면 라이선스가 구독에서 자동으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="40437-127">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="40437-128">**파트너 또는 볼륨** 라이선스를 통해 라이선스를 구입한 경우 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-128">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="40437-129">연간 요금제에 대한 비용을 지불하거나 청구 주기를 진행하는 경우 약정이 완료될 때까지 구독에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-129">If you're paying for an annual plan or if you're in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="40437-130">OneDrive 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="40437-130">OneDrive content</span></span>  <br/> |<span data-ttu-id="40437-131">사용자가 파일을 OneDrive에 저장한 경우 다른 사용자에게 이러한 파일에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-131">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="40437-132">OneDrive 파일에 대해 설정된 보존 기간 내에 보관할 파일을 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-132">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="40437-133">**기본적으로 보존 기간은 30일입니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-133">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="40437-134">사용자를 삭제한 후 보존 기간 내에 파일을 이동하지 않는 경우 OneDrive 콘텐츠가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="40437-134">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="40437-135">삭제된 계정에 대한 OneDrive 파일을 보존하는 기간을 늘리기 위해 삭제된 사용자에 대한 [OneDrive 보존](https://docs.microsoft.com/onedrive/set-retention)설정을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-135">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://docs.microsoft.com/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="40437-136">**중요!**</span><span class="sxs-lookup"><span data-stu-id="40437-136">**Important!**</span></span> <span data-ttu-id="40437-137">삭제된 사용자가 개인 컴퓨터를 사용하여 SharePoint 및 OneDrive에서 파일을 다운로드한 경우 컴퓨터에 저장된 파일을 지우는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-137">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="40437-138">OneDrive에서 동기화된 모든 파일에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-138">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="40437-139">전자 메일</span><span class="sxs-lookup"><span data-stu-id="40437-139">Email</span></span>  <br/> | <span data-ttu-id="40437-140">삭제된 사용자의 전자 메일에 다른 사용자에게 액세스 권한을 부여하면 삭제된 사용자의 사서함이 공유 사서함으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="40437-140">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="40437-141">그러면 새 사서함 소유자가 사서함에 액세스하여 새 전자 메일을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-141">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="40437-142">다음 옵션도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-142">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="40437-143">표시 이름 변경 - 활성 사용자 목록에서 공유 사서함을 쉽게 식별할 수 있도록 표시 이름을 변경하는 **것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-143">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the **Active users** list.</span></span>  <br/>  <span data-ttu-id="40437-144">자동 회신 켜기 - 이미 정중한 자동 회신을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-144">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="40437-145">조직 내부 사용자와 조직 외부의 사용자에 대해 서로 다른 자동 응답을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-145">You can send different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="40437-146">별칭 정리 - 별칭은 사용자의 추가 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-146">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="40437-147">일부 조직에서는 사용하지 않습니다. 따라서 이러한 조직이 없는 경우 여기에서 다른 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-147">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="40437-148">사용자에게 별칭이 있는 경우 해당 전자 메일 주소를 다시 사용할 수 있도록 별칭을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-148">If the user does have aliases, we recommend removing them so that you can reuse those email addresses.</span></span> <span data-ttu-id="40437-149">그렇지 않으면 삭제된 사서함의 보존 기간이 지나야 해당 전자 메일 주소를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-149">Otherwise, you can't reuse those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="40437-150">기본적으로 삭제된 사서함은 30일 동안 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-150">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="40437-151">자세한 내용은 Exchange Online에서 사용자 사서함 삭제 또는 [복원을 참조하십시오.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)</span><span class="sxs-lookup"><span data-stu-id="40437-151">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="40437-152">Active Directory</span><span class="sxs-lookup"><span data-stu-id="40437-152">Active Directory</span></span>  <br/> |<span data-ttu-id="40437-153">비즈니스에서 Azure AD와 동기화되는 **Active Directory를** 사용하는 경우 Active Directory에서 사용자 계정을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-153">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="40437-154">Office 365를 통해서는 이렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-154">You can't do it through Office 365.</span></span> <span data-ttu-id="40437-155">자세한 내용은 [사용자 계정 삭제를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="40437-155">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |

### <a name="get-started"></a><span data-ttu-id="40437-156">시작</span><span class="sxs-lookup"><span data-stu-id="40437-156">Get started</span></span>

<span data-ttu-id="40437-157">안내된 환경은 사용자를 삭제하는 단계를 안내하기 때문에 시작하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-157">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="40437-158">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="40437-159">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="40437-160">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="40437-161">삭제할 사용자를 선택한 다음 사용자 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-161">Select the user that you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="40437-162">사용자 관리 관리자: Office 365에서 하나 이상의 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="40437-162">User management admin: Delete one or more users from Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40437-163">공유 사서함으로 변환하거나 계정에 전자 메일 [](../email/convert-user-mailbox-to-shared-mailbox.md) 전달을 설정한 경우 사용자의 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-163">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="40437-164">이러한 함수에는 여전히 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-164">Those functions still need the account.</span></span> <span data-ttu-id="40437-165">공유 사서함에는 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-165">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="40437-166">계정을 공유 사서함으로 변환한 경우 라이선스 비용 지불을 [중지할 수 있습니다.](#stop-paying-for-the-license)</span><span class="sxs-lookup"><span data-stu-id="40437-166">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="40437-167">계정에 전자 메일 전달을 설정한 경우 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-167">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="40437-168">이렇게 하면 전자 메일 전달이 중지된 다음 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="40437-168">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="40437-169">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="40437-170">삭제할 사용자의 이름을 선택하고 다른 옵션(...  **)을** 선택한 다음 사용자 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-170">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="40437-171">사용자 계정을 삭제한 경우 라이선스 비용은 계속 **지불하고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-171">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="40437-172">라이선스 비용 지불을 중지하는 다음 절차를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-172">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="40437-173">또는 다른 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-173">Or, you can assign the license to another user.</span></span> <span data-ttu-id="40437-174">자동으로 누군가에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-174">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="40437-175">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="40437-176">삭제할 사용자의 이름을 선택하고 대량 작업 창에서  사용자 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-176">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="40437-177">사용자 계정을 삭제한 경우 라이선스 비용은 계속 **지불하고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-177">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="40437-178">라이선스 비용 지불을 중지하는 다음 절차를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-178">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="40437-179">또는 다른 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-179">Or, you can assign the license to another user.</span></span> <span data-ttu-id="40437-180">자동으로 누군가에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-180">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="40437-181">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-181">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="40437-182">삭제할 사용자의 이름을 선택하고 대량 작업 창에서  사용자 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-182">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="40437-183">사용자 계정을 삭제한 경우 라이선스 비용은 계속 **지불하고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-183">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="40437-184">라이선스 비용 지불을 중지하는 다음 절차를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-184">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="40437-185">또는 다른 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-185">Or, you can assign the license to another user.</span></span> <span data-ttu-id="40437-186">자동으로 누군가에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-186">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="40437-187">라이선스 비용 지불 중지</span><span class="sxs-lookup"><span data-stu-id="40437-187">Stop paying for the license</span></span>

<span data-ttu-id="40437-188">라이선스 수를 줄이는 것은 전역 관리자 또는 청구 관리자만 수행할 수 있는 별도의 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-188">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="40437-189">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-189">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span> <span data-ttu-id="40437-190">이 옵션이 표시되지 않는 경우 전역 관리자 또는 대금 청구 관리자가 아니며 이 단계를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-190">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="40437-191">제품 **탭에서** 라이선스를 제거할 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-191">On the **Products** tab, select the subscription that you want to remove licenses for.</span></span>

3. <span data-ttu-id="40437-192">구독 세부 정보 페이지에서 라이선스 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-192">On the subscription details page, select **Remove licenses**.</span></span>

4. <span data-ttu-id="40437-193">라이선스 **제거** 창의 **새** 수량 아래에 있는  총 라이선스 상자에 이 구독에 대해 원하는 총 라이선스 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-193">In the **Remove licenses** pane, under **New quantity**, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="40437-194">예를 들어 라이선스가 100개인 경우 이 중 5개 라이선스를 제거하려면 95를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-194">For example, if you have 100 licenses and you want to remove five of them, enter 95.</span></span>

5. <span data-ttu-id="40437-195">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-195">Select **Save**.</span></span>

<span data-ttu-id="40437-196">나중에 다른 사람을 비즈니스에 추가하는 단계를 진행할 때 한 단계만 수행하면 동시에 라이선스를 구입하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-196">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="40437-197">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-197">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="40437-198">이 옵션이 표시되지 않는 경우 전역 관리자 또는 대금 청구 관리자가 아니며 이 단계를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-198">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="40437-199">구독(두 개 이상인 경우)을 선택한 다음 라이선스 **추가/제거를** 선택하여 라이선스를 삭제하여 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-199">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="40437-200">나중에 다른 사람을 비즈니스에 추가하는 단계를 진행할 때 한 단계만 수행하면 동시에 라이선스를 구입하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-200">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="40437-201">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-201">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="40437-202">이 옵션이 표시되지 않는 경우 전역 관리자 또는 대금 청구 관리자가 아니며 이 단계를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-202">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="40437-203">구독(두 개 이상인 경우)을 선택한 다음 라이선스 **추가/제거를** 선택하여 라이선스를 삭제하여 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-203">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="40437-204">나중에 다른 사람을 비즈니스에 추가하는 단계를 진행할 때 한 단계만 수행하면 동시에 라이선스를 구입하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-204">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="40437-205">동시에 많은 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="40437-205">Delete many users at the same time</span></span>

<span data-ttu-id="40437-206">[Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-206">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="40437-207">사용자 삭제와 관련된 문제 해결</span><span class="sxs-lookup"><span data-stu-id="40437-207">Fix issues with deleting a user</span></span>

<span data-ttu-id="40437-208">다음은 사용자를 삭제하는 경우 사용자에게 발생하는 가장 일반적인 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-208">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="40437-209">**"사용자를 삭제할 수 없습니다. 나중에 다시 시도하세요."**</span><span class="sxs-lookup"><span data-stu-id="40437-209">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="40437-210">계정에 전자 메일 전달이 설정되어 있는지 또는 공유 사서함으로 변환되어 있는지 다시 한 번 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-210">Double-check whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="40437-211">이 두 가지를 모두 통해 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-211">Both of these will cause that error.</span></span> <span data-ttu-id="40437-212">전자 메일 전달이 있는 계정이나 공유 사서함으로 변환된 계정은 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-212">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="40437-213">**사용자를 삭제하기 위한 적절한 권한이 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="40437-213">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="40437-214">[Microsoft 365](about-admin-roles.md) 전역 관리자 또는 사용자 관리 관리자인 사용자만 사용자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-214">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="40437-215">일반적으로 학교 또는 회사의 기술 지원 담당자입니다.</span><span class="sxs-lookup"><span data-stu-id="40437-215">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="40437-216">사용자를 삭제하지만 해당 이름은 전체 주소 **책에 계속 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="40437-216">**You delete the user but their name continues appear in your global address book**.</span></span> <span data-ttu-id="40437-217">이 문제는 기업에서 Active Directory를 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-217">This happens when a business is using Active Directory.</span></span> <span data-ttu-id="40437-218">Active Directory에서 사용자 계정을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40437-218">You must delete the users account from Active Directory.</span></span> <span data-ttu-id="40437-219">자세한 내용은 [사용자 계정 삭제를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="40437-219">For instructions, see [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

<span data-ttu-id="40437-220">**컴퓨터에서 Microsoft 365를 삭제하고 싶나요? 구독 [취소로 이동하세요.](../../commerce/subscriptions/cancel-your-subscription.md)**</span><span class="sxs-lookup"><span data-stu-id="40437-220">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>

## <a name="related-articles"></a><span data-ttu-id="40437-221">관련 문서</span><span class="sxs-lookup"><span data-stu-id="40437-221">Related articles</span></span>

[<span data-ttu-id="40437-222">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="40437-222">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="40437-223">사서함을 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="40437-223">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="40437-224">Office 365에서 이전 직원 제거</span><span class="sxs-lookup"><span data-stu-id="40437-224">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="40437-225">Office 365에 새 직원 추가</span><span class="sxs-lookup"><span data-stu-id="40437-225">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="40437-226">[사용자 계정 삭제:](https://go.microsoft.com/fwlink/p/?linkid=841808)비즈니스에서 Azure AD와 동기화되는 **Active Directory를** 사용하는 경우 다음 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="40437-226">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="40437-227">Office 365를 통해서는 이렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40437-227">You can't do it through Office 365.</span></span>
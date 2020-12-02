---
title: 사용자 복원
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 삭제 된 사용자 계정 및 모든 관련 데이터를 복원 하는 방법을 알아봅니다.
ms.openlocfilehash: 7d7269ec338aafb9be317c2ee10a57d23c775c0a
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551847"
---
# <a name="restore-a-user"></a><span data-ttu-id="4bc23-103">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="4bc23-103">Restore a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4bc23-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-104">The admin center is changing.</span></span> <span data-ttu-id="4bc23-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc23-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
   
<span data-ttu-id="4bc23-p102">사용자 계정을 삭제한 후 30일 이내에 복원할 경우 계정 및 모든 관련 데이터가 복원됩니다. 사용자는 같은 회사 또는 학교 계정으로 로그인할 수 있습니다. 해당 사서함이 완전히 복원됩니다. 특정 사용자 계정을 복원할 수 있는 기간이 얼마나 남았는지 확인해야 하는 경우 [Microsoft에 문의](../contact-support-for-business-products.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc23-p102">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="4bc23-110">다음은 몇 가지 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-110">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="4bc23-111">계정에 할당할 수 있는 라이선스가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-111">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="4bc23-112">회사에서 Active Directory를 사용할 경우, 사용자 계정 복원에 대한 자세한 내용은 [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308)(Office 365에서 삭제된 사용자 계정 문제를 해결하는 방법)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc23-112">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="4bc23-113">하나 이상의 사용자 계정 복원</span><span class="sxs-lookup"><span data-stu-id="4bc23-113">Restore one or more user accounts</span></span>

<span data-ttu-id="4bc23-114">이러한 단계를 수행 하려면 Microsoft 365 전역 관리자 또는 사용자 관리 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-114">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4bc23-115">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">삭제 된 사용자</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-115">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4bc23-116">[관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=848041)이동한 후 **사용자** \> **삭제 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-116">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4bc23-117">[관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=850627)이동한 후 **사용자** \> **삭제 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-117">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="4bc23-118">삭제 된 **사용자** 페이지에서 복원 하려는 사용자의 이름을 선택 하 고 **복원을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-118">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="4bc23-119">프롬프트에 따라 암호를 설정 하 고 **복원을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-119">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="4bc23-120">사용자가 성공적으로 복원 되 면 **전자 메일 보내기 및 닫기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-120">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="4bc23-121">이름 충돌이나 프록시 주소 충돌이 발생할 경우 해당 계정을 복원하는 방법에 대한 아래 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc23-121">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="4bc23-122">사용자를 복원한 후에는 암호를 변경 하 고 팔 로우 하는 작업을 수행 했는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-122">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="4bc23-123">사용자 이름 충돌이 있는 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="4bc23-123">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="4bc23-124"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="4bc23-124"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="4bc23-125">사용자 이름 충돌은 사용자 계정을 삭제하고 같은 사용자 또는 비슷한 이름의 다른 사용자에 대해 동일한 사용자 이름으로 새 사용자 계정을 만든 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-125">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="4bc23-p104">이 문제를 해결하려면 활성 사용자 계정을 복원하려는 계정으로 바꾸거나 동일한 사용자 이름을 갖는 2개의 계정이 존재하지 않도록 다른 사용자 이름을 복원하려는 계정에 할당합니다. 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-p104">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4bc23-129">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">삭제 된 사용자</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4bc23-130">[관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=848041)이동한 후 **사용자** \> **삭제 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-130">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4bc23-131">[관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=850627)이동한 후 **사용자** \> **삭제 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-131">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="4bc23-132">삭제 된 **사용자** 페이지에서 복원 하려는 사용자의 이름을 선택 하 고 **복원을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-132">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4bc23-p105">두 명 이상의 사용자를 복원하지 못한 경우 일부 사용자의 복원 작업이 실패했음을 알리는 오류 메시지가 나타납니다. 로그를 보고 복원되지 않은 사용자를 확인한 다음 실패한 계정을 한 번에 하나씩 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-p105">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="4bc23-135">프롬프트에 따라 암호를 설정 하 고 **복원을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-135">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="4bc23-p106">메시지에서 계정을 복원하는 동안 문제가 발생했음을 알려 줍니다. 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-p106">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="4bc23-p107">복원을 취소하고 현재 활성 사용자의 이름을 바꿉니다. 그런 다음 복원을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-p107">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="4bc23-140">또는 사용자의 새로운 기본 전자 메일 주소를 입력 하 고 **복원을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-140">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="4bc23-141">결과를 검토한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-141">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="4bc23-142">프록시 주소 충돌이 있는 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="4bc23-142">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="4bc23-p108">프록시 주소 충돌은 프록시 주소가 포함된 사용자 계정을 삭제하고 동일한 프록시 주소를 다른 계정에 할당한 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다. 이 문제를 해결하려면 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4bc23-p108">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="4bc23-145">이 작업을 수행 하려면 Microsoft 365에 [관리자 권한이](about-admin-roles.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-145">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4bc23-146">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">삭제 된 사용자</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="4bc23-147">[관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=848041)이동한 후 **사용자** \> **삭제 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-147">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4bc23-148">[관리 센터로](https://go.microsoft.com/fwlink/p/?linkid=850627)이동한 후 **사용자** \> **삭제 된 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-148">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="4bc23-149">**삭제된 사용자** 페이지에서 복원할 사용자를 선택하고 **복원** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-149">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="4bc23-150">**복원** 페이지에서 지침에 따라 암호를 설정 하 고 **복원을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-150">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="4bc23-151">충돌하는 프록시 주소가 복원할 사용자에서 자동으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-151">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="4bc23-152">결과를 검토한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc23-152">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4bc23-153">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4bc23-153">Related articles</span></span>

[<span data-ttu-id="4bc23-154">사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="4bc23-154">Delete a user</span></span>](delete-a-user.md)
  

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
description: 삭제된 사용자 계정 및 모든 관련 데이터를 복원하는 방법을 학습합니다.
ms.openlocfilehash: b7d98c1f49f8252ea9fdda2d863b5b77ac5bea9d
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291070"
---
# <a name="restore-a-user"></a><span data-ttu-id="ac179-103">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="ac179-103">Restore a user</span></span>
   
<span data-ttu-id="ac179-p101">사용자 계정을 삭제한 후 30일 이내에 복원할 경우 계정 및 모든 관련 데이터가 복원됩니다. 사용자는 같은 회사 또는 학교 계정으로 로그인할 수 있습니다. 해당 사서함이 완전히 복원됩니다. 특정 사용자 계정을 복원할 수 있는 기간이 얼마나 남았는지 확인해야 하는 경우 [Microsoft에 문의](../../business-video/get-help-support.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="ac179-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="ac179-108">다음은 몇 가지 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="ac179-109">계정에 할당할 수 있는 라이선스가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ac179-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="ac179-110">회사에서 Active Directory를 사용할 경우, 사용자 계정 복원에 대한 자세한 내용은 [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md)(Office 365에서 삭제된 사용자 계정 문제를 해결하는 방법)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac179-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="ac179-111">하나 이상의 사용자 계정 복원</span><span class="sxs-lookup"><span data-stu-id="ac179-111">Restore one or more user accounts</span></span>

<span data-ttu-id="ac179-112">이러한 단계를 수행하려면 Microsoft 365 관리자 또는 사용자 관리 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="ac179-113">관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="ac179-114">삭제된 **사용자 페이지에서** 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="ac179-115">프롬프트에 따라 암호를 설정한 다음 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="ac179-116">사용자가 복원되면 전자 메일 **보내기 및 닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="ac179-117">이름 충돌이나 프록시 주소 충돌이 발생할 경우 해당 계정을 복원하는 방법에 대한 아래 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac179-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="ac179-118">사용자를 복원한 후 암호가 변경되었다는 사실을 사용자에게 알리고 추가 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="ac179-119">사용자 이름 충돌이 있는 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="ac179-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="ac179-120">사용자 이름 충돌은 사용자 계정을 삭제하고 같은 사용자 또는 비슷한 이름의 다른 사용자에 대해 동일한 사용자 이름으로 새 사용자 계정을 만든 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="ac179-p103">이 문제를 해결하려면 활성 사용자 계정을 복원하려는 계정으로 바꾸거나 동일한 사용자 이름을 갖는 2개의 계정이 존재하지 않도록 다른 사용자 이름을 복원하려는 계정에 할당합니다. 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="ac179-124">관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="ac179-125">삭제된 **사용자 페이지에서** 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac179-p104">두 명 이상의 사용자를 복원하지 못한 경우 일부 사용자의 복원 작업이 실패했음을 알리는 오류 메시지가 나타납니다. 로그를 보고 복원되지 않은 사용자를 확인한 다음 실패한 계정을 한 번에 하나씩 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="ac179-128">프롬프트에 따라 암호를 설정하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="ac179-p105">메시지에서 계정을 복원하는 동안 문제가 발생했음을 알려 줍니다. 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="ac179-p106">복원을 취소하고 현재 활성 사용자의 이름을 바꿉니다. 그런 다음 복원을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="ac179-133">또는 사용자의 새 기본 전자 메일 주소를 입력하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="ac179-134">결과를 검토한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="ac179-135">프록시 주소 충돌이 있는 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="ac179-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="ac179-p107">프록시 주소 충돌은 프록시 주소가 포함된 사용자 계정을 삭제하고 동일한 프록시 주소를 다른 계정에 할당한 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다. 이 문제를 해결하려면 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ac179-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="ac179-138">이렇게하려면 [](about-admin-roles.md) 관리자 권한이 Microsoft 365 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="ac179-139">관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="ac179-140">**삭제된 사용자** 페이지에서 복원할 사용자를 선택하고 **복원** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="ac179-141">복원 **페이지에서** 지침에 따라 암호를 설정하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac179-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="ac179-142">충돌하는 프록시 주소가 복원할 사용자에서 자동으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="ac179-143">결과를 검토한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac179-143">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ac179-144">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ac179-144">Related articles</span></span>

[<span data-ttu-id="ac179-145">사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="ac179-145">Delete a user</span></span>](delete-a-user.md)

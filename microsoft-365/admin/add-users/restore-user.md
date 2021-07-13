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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 사용자 계정을 삭제한 후 30일 이내에 계정 및 모든 데이터를 복원할 수 있으며 사용자는 동일한 계정으로 로그인할 수 있습니다.
ms.openlocfilehash: e37f913bcc6a54bdcc1e0f52168fe1aab0c8afdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394270"
---
# <a name="restore-a-user"></a><span data-ttu-id="827ad-103">사용자 복원</span><span class="sxs-lookup"><span data-stu-id="827ad-103">Restore a user</span></span>
   
<span data-ttu-id="827ad-p101">사용자 계정을 삭제한 후 30일 이내에 복원할 경우 계정 및 모든 관련 데이터가 복원됩니다. 사용자는 같은 회사 또는 학교 계정으로 로그인할 수 있습니다. 해당 사서함이 완전히 복원됩니다. 특정 사용자 계정을 복원할 수 있는 기간이 얼마나 남았는지 확인해야 하는 경우 [Microsoft에 문의](../../business-video/get-help-support.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="827ad-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="827ad-108">다음은 몇 가지 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="827ad-109">계정에 할당할 수 있는 라이선스가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="827ad-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="827ad-110">비즈니스에서 Active Directory를 사용하는 경우 사용자 계정 복원에 대한 자세한 내용은 에서 삭제된 사용자 계정 문제를 해결하는 [Office 365.](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)</span><span class="sxs-lookup"><span data-stu-id="827ad-110">If your business uses Active Directory, for instrutcions on restoring a user account, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="827ad-111">하나 이상의 사용자 계정 복원</span><span class="sxs-lookup"><span data-stu-id="827ad-111">Restore one or more user accounts</span></span>

<span data-ttu-id="827ad-112">이러한 단계를 수행하려면 Microsoft 365 관리자 또는 사용자 관리 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="827ad-113">관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="827ad-114">삭제된 **사용자 페이지에서** 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="827ad-115">프롬프트에 따라 암호를 설정한 다음 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="827ad-116">사용자가 복원되면 전자 메일 **보내기 및 닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="827ad-117">이름 충돌이나 프록시 주소 충돌이 발생할 경우 해당 계정을 복원하는 방법에 대한 아래 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="827ad-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="827ad-118">사용자를 복원한 후 암호가 변경되었다는 사실을 사용자에게 알리고 추가 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="827ad-119">사용자 이름 충돌이 있는 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="827ad-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="827ad-120">사용자 이름 충돌은 사용자 계정을 삭제하고 같은 사용자 또는 비슷한 이름의 다른 사용자에 대해 동일한 사용자 이름으로 새 사용자 계정을 만든 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="827ad-p103">이 문제를 해결하려면 활성 사용자 계정을 복원하려는 계정으로 바꾸거나 동일한 사용자 이름을 갖는 2개의 계정이 존재하지 않도록 다른 사용자 이름을 복원하려는 계정에 할당합니다. 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="827ad-124">관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="827ad-125">삭제된 **사용자 페이지에서** 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="827ad-p104">두 명 이상의 사용자를 복원하지 못한 경우 일부 사용자의 복원 작업이 실패했음을 알리는 오류 메시지가 나타납니다. 로그를 보고 복원되지 않은 사용자를 확인한 다음 실패한 계정을 한 번에 하나씩 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="827ad-128">프롬프트에 따라 암호를 설정하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="827ad-p105">메시지에서 계정을 복원하는 동안 문제가 발생했음을 알려 줍니다. 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="827ad-p106">복원을 취소하고 현재 활성 사용자의 이름을 바꿉니다. 그런 다음 복원을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="827ad-133">또는 사용자의 새 기본 전자 메일 주소를 입력하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="827ad-134">결과를 검토한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="827ad-135">프록시 주소 충돌이 있는 사용자 복원</span><span class="sxs-lookup"><span data-stu-id="827ad-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="827ad-p107">프록시 주소 충돌은 프록시 주소가 포함된 사용자 계정을 삭제하고 동일한 프록시 주소를 다른 계정에 할당한 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다. 이 문제를 해결하려면 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="827ad-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="827ad-138">이렇게하려면 [](about-admin-roles.md) 관리자 권한이 Microsoft 365 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="827ad-139">관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="827ad-140">**삭제된 사용자** 페이지에서 복원할 사용자를 선택하고 **복원** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="827ad-141">복원 **페이지에서** 지침에 따라 암호를 설정하고 복원을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="827ad-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="827ad-142">충돌하는 프록시 주소가 복원할 사용자에서 자동으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="827ad-143">결과를 검토한 다음 **닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="827ad-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="827ad-144">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="827ad-144">Related content</span></span>

<span data-ttu-id="827ad-145">[사용자](delete-a-user.md) 삭제(문서)</span><span class="sxs-lookup"><span data-stu-id="827ad-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="827ad-146">[관리자 역할](assign-admin-roles.md) 할당(비디오)</span><span class="sxs-lookup"><span data-stu-id="827ad-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="827ad-147">[사용자에게 라이선스](../manage/assign-licenses-to-users.md) 할당(문서)</span><span class="sxs-lookup"><span data-stu-id="827ad-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>

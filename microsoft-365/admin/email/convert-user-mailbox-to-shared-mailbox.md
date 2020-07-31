---
title: 사용자 사서함을 공유 사서함으로 변환
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '개인 사서함을 여러 사용자가 액세스할 수 있는 공유 사서함으로 변환 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521032"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="a28ee-103">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="a28ee-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="a28ee-104">사용자의 사서함을 공유 사서함으로 변환 하면 기존 전자 메일 및 일정이 모두 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="a28ee-105">이제는 여러 사용자가 한 사람을 대신 하 여 액세스할 수 있는 공유 사서함에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="a28ee-106">나중에 공유 사서함을 다시 사용자 (개인) 사서함으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="a28ee-107">**다음은 알아야 할 몇 가지 중요 한 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="a28ee-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="a28ee-108">변환 중인 사용자 사서함에는 라이선스를 공유 사서함으로 변환 하기 전에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="a28ee-109">그렇지 않으면 사서함을 변환 하는 옵션이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="a28ee-110">라이선스를 제거한 경우 사서함을 변환할 수 있도록 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="a28ee-111">공유 사서함으로 변환한 후 사용자의 계정에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="a28ee-112">공유 사서함에는 라이선스가 할당 되지 않은 데이터를 최대 50 GB까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="a28ee-113">그 보다 더 많은 데이터를 포함 하려면 라이선스가 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="a28ee-114">라이선스를 제거할 수 있도록 공유 사서함에서 첨부 파일을 포함 하는 대용량 전자 메일을 삭제 하 여 축소 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="a28ee-115">이전 사용자의 계정을 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-115">Don't delete the old user's account.</span></span> <span data-ttu-id="a28ee-116">공유 사서함을 고정 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="a28ee-117">사용자 계정을 이미 삭제 한 경우에는 삭제 된 [사용자의 사서함 변환을](#convert-the-mailbox-of-a-deleted-user)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a28ee-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="a28ee-118">사서함이 공유 사서함으로 변환 된 후에는 규칙이 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="a28ee-119">Exchange 관리 센터를 사용 하 여 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="a28ee-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="a28ee-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="a28ee-121">**받는 사람** \> **사서함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="a28ee-122">사용자 사서함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-122">Select the user mailbox.</span></span> <span data-ttu-id="a28ee-123">**공유 사서함으로 변환**에서 **변환을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="a28ee-124">사서함이 50 보다 작으면 [사용자의 라이선스](../manage/remove-licenses-from-users.md)를 제거 하 고이에 대 한 비용 지불을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="a28ee-125">사용자의 계정을 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-125">Don't delete the user's account.</span></span> <span data-ttu-id="a28ee-126">공유 사서함에는 기준 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="a28ee-127">조직에서 나가는 직원의 사서함을 변환 하는 경우에는 추가 단계를 수행 하 여 더 이상 로그인 할 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="a28ee-128">[Microsoft 365에서 이전 직원 제거를](../add-users/remove-former-employee.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="a28ee-129">공유 사서함에 대해 알아야 할 다른 모든 작업은 [공유](about-shared-mailboxes.md) 사서함 및 [공유 사서함 만들기](create-a-shared-mailbox.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="a28ee-130">Microsoft 365 관리 센터를 사용 하 여 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="a28ee-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a28ee-131">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="a28ee-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a28ee-132">해당 사서함을 변환 하려는 사용자의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="a28ee-133">사용자 암호를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-133">Reset the user's password.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a28ee-134">사서함 변환 중에 사용자 암호를 다시 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="a28ee-135">그러나 암호를 다시 설정 하지 않으면 사서함 변환이 끝난 후 **에도 원래 사용자 이름 및 암호가 계속 작동** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="a28ee-136">**메일** 탭의 **기타 작업**에서 **공유 사서함으로 변환을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a28ee-137">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="a28ee-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a28ee-138">해당 사서함을 변환 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="a28ee-139">오른쪽 창에서 **메일 설정을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="a28ee-140">**기타 설정**옆에 있는 **공유 사서함으로 변환을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a28ee-141">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="a28ee-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a28ee-142">해당 사서함을 변환 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="a28ee-143">오른쪽 창에서 **메일 설정을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="a28ee-144">**기타 설정**옆에 있는 **공유 사서함으로 변환을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="a28ee-145">사서함이 50 보다 작으면 [사용자의 라이선스를 제거](../manage/remove-licenses-from-users.md)하 고이에 대 한 비용 지불을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-145">If the mailbox is smaller than 50 GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="a28ee-146">사용자의 이전 사서함은 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="a28ee-147">공유 사서함에는 기준 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="a28ee-148">조직에서 나가는 직원의 사서함을 변환 하는 경우에는 추가 단계를 수행 하 여 더 이상 로그인 할 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="a28ee-149">[Microsoft 365에서 이전 직원 제거를](../add-users/remove-former-employee.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="a28ee-150">공유 사서함에 대해 알아야 할 다른 모든 작업은 [공유](about-shared-mailboxes.md) 사서함 및 [공유 사서함 만들기](create-a-shared-mailbox.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a28ee-151">공유 사서함에는 별도의 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="a28ee-152">그러나 원본 위치 보관을 사용하도록 설정하거나 공유 사서함에 원본 위치 유지 또는 소송 보존을 적용하려는 경우 Exchange Online Archiving이 있는 Exchange Online 계획 1 또는 Exchange Online 계획 2 라이선스를 사서함에 할당해야 입니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="a28ee-153">삭제 된 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="a28ee-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="a28ee-154">사용자 계정을 삭제 했 고 이제 이전 사서함을 공유 사서함으로 변환 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-154">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="a28ee-155">수행 해야 하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-155">Here's what you need to do:</span></span>

1. <span data-ttu-id="a28ee-156">[사용자의 계정을 복원](../add-users/restore-user.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="a28ee-157">Microsoft 365 라이선스가 할당 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="a28ee-158">사용자 암호를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="a28ee-159">사서함을 다시 만들 때까지 20-30 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="a28ee-160">이제이 페이지의 지침에 따라 사서함을 공유 사서함으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="a28ee-161">이 작업을 완료 한 후에는 사용자의 사서함에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="a28ee-162">사용자의 이전 사서함은 삭제 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="a28ee-163">공유 사서함에는 기준 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="a28ee-164">공유 사서함에 구성원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="a28ee-165">공유 사서함을 사용자의 (개인) 사서함으로 다시 변환</span><span class="sxs-lookup"><span data-stu-id="a28ee-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="a28ee-166"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="a28ee-167">공유 되는 **받는 사람** \> **Shared**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="a28ee-168">공유 사서함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-168">Select the shared mailbox.</span></span> <span data-ttu-id="a28ee-169">**일반 사서함으로 변환**에서 **변환을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="a28ee-170">관리 센터로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-170">Go back to the admin center.</span></span> <span data-ttu-id="a28ee-171">**사용자**에서 이전 공유 사서함과 연결 된 사용자 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="a28ee-172">계정에 라이선스를 할당 하 고 암호를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="a28ee-173">사서함이 설정 되는 데 몇 분 정도 소요 되지만 그 이후에는 해당 계정을 사용 하려는 사용자가 준비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-173">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="a28ee-174">로그인 할 때 공유 사서함에 있는 것으로 사용 된 전자 메일 및 일정 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-174">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="a28ee-175">하이브리드 환경에서 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="a28ee-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="a28ee-176">이 공유 사서함을 하이브리드 환경에서 사용 하는 경우에는 사용자 사서함을 다시 온-프레미스로 변환 하 고 사용자 사서함을 공유 사서함으로 변환한 다음 공유 사서함을 다시 클라우드로 이동 하는 것이 **좋습니다** (거의 필요 합니다).</span><span class="sxs-lookup"><span data-stu-id="a28ee-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="a28ee-177">그 이유는 다음과 같습니다. 클라우드에서 사서함을 변환 하는 경우 새 현실을 다시 온-프레미스로 동기화 하지 않으므로 온-프레미스에서 사서함이 사용자 사서함 인 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="a28ee-178">일반적으로이 문제는 문제가 되지 않지만, 사서함이 사용자 사서함 인 것으로 생각 하는 온-프레미스 특성이 해당 특성의 새 클라우드 버전을 덮어쓸 수 있으며, 결과적으로 사서함이 다시 변환 될 수 있는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="a28ee-179">사용자 사서함에 라이선스가 필요 **하거나 30 일 후에 일시 삭제**되기 때문에이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="a28ee-180">이 문제가 발생 하는 대부분의 이유는 아니지만 여전히 가끔씩 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="a28ee-181">안전 하 고 사서함을 다시 온-프레미스로 이동 하 고 변환한 후 공유 사서함을 다시 클라우드로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-181">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="a28ee-182">이 권장 솔루션은 온-프레미스의 사용자 사서함이 일시적 으로만 존재 하기 때문에 하이브리드 환경에 대 한 사용권 계약을 위반 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-182">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="a28ee-183">온-프레미스 조직에서 사용자 사서함 또는 공유 사서함을 유지 관리 하 고이를 클라우드로 다시 이동 하지 않은 경우 라이선스를 위반 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-183">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="a28ee-184">조직 관리 또는 받는 사람 관리 역할 그룹의 구성원 인 경우 Exchange 관리 셸을 사용 하 여 온-프레미스의 공유 사서함으로 사용자 사서함을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-184">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="a28ee-185">예를 들면 `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a28ee-185">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="a28ee-186">[공유 사서함이 예기치 않게 사용자 사서함으로 변환 되는](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)경우이 지원 솔루션의 해결 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a28ee-186">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="a28ee-187">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a28ee-187">Related articles</span></span>

[<span data-ttu-id="a28ee-188">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="a28ee-188">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="a28ee-189">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="a28ee-189">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="a28ee-190">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="a28ee-190">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="a28ee-191">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="a28ee-191">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="a28ee-192">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a28ee-192">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

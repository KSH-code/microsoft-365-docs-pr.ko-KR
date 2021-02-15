---
title: 사용자 사서함을 공유 사서함으로 변환
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: '개인 사서함을 여러 사용자가 액세스할 수 있는 공유 사서함으로 변환하는 방법을 학습합니다. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737968"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="0540f-103">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="0540f-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="0540f-104">사용자의 사서함을 공유 사서함으로 변환하면 모든 기존 전자 메일 및 일정이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="0540f-105">이제 한 사람이 아닌 여러 사람이 공유 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="0540f-106">나중에 공유 사서함을 사용자(개인) 사서함으로 다시 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="0540f-107">**다음은 알아야 할 몇 가지 중요한 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="0540f-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="0540f-108">변환할 사용자 사서함에는 공유 사서함으로 변환하기 전에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="0540f-109">그렇지 않으면 사서함을 변환하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="0540f-110">라이선스를 제거한 경우 사서함을 변환할 수 있도록 라이선스를 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="0540f-111">사서함을 공유 사서함으로 변환한 후 사용자 계정에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="0540f-112">공유 사서함에는 라이선스가 할당되지 않은 경우 최대 50GB의 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="0540f-113">이보다 많은 데이터를 저장하려면 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="0540f-114">라이선스를 제거할 수 있도록 공유 사서함에서 대용량 전자 메일(예: 첨부 파일이 있는 전자 메일)을 삭제하여 축소해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="0540f-115">이전 사용자의 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-115">Don't delete the old user's account.</span></span> <span data-ttu-id="0540f-116">공유 사서함의 기준이 앵커되는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="0540f-117">사용자 계정을 이미 삭제한 경우 삭제된 사용자의 사서함 [변환을 참조하세요.](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="0540f-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="0540f-118">사서함이 공유 사서함으로 변환된 후 규칙은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="0540f-119">Exchange 관리 센터를 사용하여 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="0540f-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="0540f-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="0540f-121">받는 **사람** \> **사서함을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0540f-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="0540f-122">사용자 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-122">Select the user mailbox.</span></span> <span data-ttu-id="0540f-123">공유 **사서함으로 변환에서** 변환을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0540f-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="0540f-124">사서함이 50GB보다 작은 경우 사용자에서 라이선스를 제거하고 해당 라이선스에 대한 비용을 지불하지 못하게 할 수 있습니다. [](../manage/remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="0540f-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="0540f-125">사용자 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-125">Don't delete the user's account.</span></span> <span data-ttu-id="0540f-126">공유 사서함은 앵커로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="0540f-127">조직을 떠나는 직원의 사서함을 변환하는 경우 추가 단계를 수행하여 더 이상 로그인할 수 없는지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="0540f-128">Microsoft [365에서 이전 직원 제거를 참조 하시기 바랍니다.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="0540f-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0540f-129">사서함 변환 중에 사용자 암호를 다시 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="0540f-130">그러나 암호를 다시 설정하지 않은 경우 **사서함** 변환이 완료된 후에도 원래 사용자 이름과 암호가 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="0540f-131">공유 사서함에 대해 알아야 할 모든 [](about-shared-mailboxes.md) 내용은 공유 사서함 및 공유 사서함 [만들기를 참조합니다.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="0540f-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0540f-132">공유 사서함에는 별도의 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="0540f-133">그러나 원본 위치 보관을 사용하도록 설정하거나 공유 사서함에 원본 위치 유지 또는 소송 보존을 적용하려는 경우 Exchange Online Archiving이 있는 Exchange Online 계획 1 또는 Exchange Online 계획 2 라이선스를 사서함에 할당해야 입니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="0540f-134">삭제된 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="0540f-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="0540f-135">사용자 계정을 삭제했다가 이제 이전 사서함을 공유 사서함으로 변환하고자 했다고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="0540f-136">다음과 같은 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="0540f-137">[사용자 계정을 복원합니다.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="0540f-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="0540f-138">Microsoft 365 라이선스가 할당되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0540f-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="0540f-139">사용자의 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="0540f-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="0540f-140">사서함을 다시 만들 때까지 20-30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="0540f-141">이제 이 페이지의 지침에 따라 사서함을 공유 사서함으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="0540f-142">그런 다음 사용자 사서함에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="0540f-143">사용자의 이전 사서함을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="0540f-144">공유 사서함은 앵커로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="0540f-145">공유 사서함에 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="0540f-146">공유 사서함을 사용자의 (개인) 사서함으로 다시 변환</span><span class="sxs-lookup"><span data-stu-id="0540f-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="0540f-147"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="0540f-148">받는 **사람** \> **공유를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0540f-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="0540f-149">공유 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-149">Select the shared mailbox.</span></span> <span data-ttu-id="0540f-150">일반 **사서함으로 변환에서** 변환을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0540f-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="0540f-151">관리 센터로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-151">Go back to the admin center.</span></span> <span data-ttu-id="0540f-152">사용자 **아래에서** 이전 공유 사서함과 연결된 사용자 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="0540f-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="0540f-153">계정에 라이선스를 할당하고 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="0540f-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="0540f-154">사서함을 설정하는 데 몇 분 정도 걸릴 수 있지만 그 후에 해당 계정을 사용하게 될 사람이 준비됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="0540f-155">로그인하면 공유 사서함에 있는 전자 메일 및 일정 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="0540f-156">하이브리드 환경에서 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="0540f-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="0540f-157">Exchange 하이브리드 환경에서 사용자 사서함을 공유 사서함으로 변환하는 데 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0540f-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="0540f-158">원격 공유 사서함을 만들거나 수정하기 위한 cmdlet</span><span class="sxs-lookup"><span data-stu-id="0540f-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="0540f-159">Exchange 하이브리드 배포에서 디렉터리 동기화가 실행된 후 공유 사서함이 예기치 않게 사용자 사서함으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="0540f-160">조직 관리 또는 받는 사람 관리 역할 그룹의 구성원인 경우 Exchange 관리 셸을 사용하여 사용자 사서함을 공유 사서함으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="0540f-161">예를 들면 `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0540f-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0540f-162">관련 문서</span><span class="sxs-lookup"><span data-stu-id="0540f-162">Related articles</span></span>

[<span data-ttu-id="0540f-163">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="0540f-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0540f-164">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="0540f-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="0540f-165">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="0540f-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="0540f-166">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="0540f-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="0540f-167">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0540f-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

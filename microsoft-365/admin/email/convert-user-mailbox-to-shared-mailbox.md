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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '개인 사서함을 한 사람이 아닌 여러 사람이 액세스할 수 있는 공유 사서함으로 변환하는 방법을 학습합니다. '
ms.openlocfilehash: caf3935b1ffb36989b2884c6811111531a061098
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393970"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="790c4-103">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="790c4-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="790c4-104">사용자의 사서함을 공유 사서함으로 변환하면 모든 기존 전자 메일 및 일정이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="790c4-105">이제 한 사람이 아닌 여러 사람이 액세스할 수 있는 공유 사서함에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="790c4-106">나중에 공유 사서함을 사용자(개인) 사서함으로 다시 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="790c4-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="790c4-107">Before you begin</span></span>

<span data-ttu-id="790c4-108">**다음은 알아야 할 몇 가지 중요한 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="790c4-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="790c4-109">변환할 사용자 사서함에는 공유 사서함으로 변환하기 전에 라이선스가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="790c4-110">그렇지 않으면 사서함을 변환하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="790c4-111">라이선스를 제거한 경우 사서함을 변환할 수 있도록 라이선스를 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="790c4-112">사서함을 공유 사서함으로 변환한 후 사용자 계정에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="790c4-113">공유 사서함에는 라이선스가 할당되지 않은 경우 최대 50GB의 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="790c4-114">이보다 많은 데이터를 저장하려면 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="790c4-115">라이선스를 제거할 수 있도록 공유 사서함에서 대용량 전자 메일(예: 첨부 파일이 있는 전자 메일)을 삭제하여 축소해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="790c4-116">이전 사용자의 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-116">Don't delete the old user's account.</span></span> <span data-ttu-id="790c4-117">공유 사서함의 기준이 앵커되는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-117">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="790c4-118">사용자 계정을 이미 삭제한 경우 삭제된 사용자의 [사서함 변환을 참조하세요.](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="790c4-118">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="790c4-119">이 규칙은 사서함이 공유 사서함으로 변환된 후 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="790c4-120">Exchange 관리 센터를 사용하여 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="790c4-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="790c4-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="790c4-122">받는 **사람 사서함** \> **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="790c4-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="790c4-123">사용자 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-123">Select the user mailbox.</span></span> <span data-ttu-id="790c4-124">공유 **사서함으로 변환에서** 변환을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="790c4-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="790c4-125">사서함이 50GB보다 작은 경우 사용자 에서 [](../manage/remove-licenses-from-users.md)라이선스를 제거하고 비용 지불을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="790c4-126">사용자 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-126">Don't delete the user's account.</span></span> <span data-ttu-id="790c4-127">공유 사서함은 앵커로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="790c4-128">조직을 떠나는 직원의 사서함을 변환하는 경우 추가 단계를 수행하여 더 이상 로그인할 수 없는지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="790c4-129">에서 [이전 직원 제거를 Microsoft 365.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="790c4-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="790c4-130">사서함 변환 중에 사용자 암호를 다시 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="790c4-131">그러나 암호를 다시 설정하지  않은 경우 사서함 변환이 완료된 후에도 원래 사용자 이름과 암호가 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="790c4-132">공유 사서함에 대해 알아야 할 다른 모든 내용은 [공유](about-shared-mailboxes.md) 사서함 및 공유 사서함 만들기를 [참조합니다.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="790c4-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="790c4-133">공유 사서함에는 별도의 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="790c4-134">그러나 원본 위치 보관을 사용하도록 설정하거나 공유 사서함에 원본 위치 유지 또는 소송 보존을 적용하려는 경우 Exchange Online Archiving이 있는 Exchange Online 계획 1 또는 Exchange Online 계획 2 라이선스를 사서함에 할당해야 입니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="790c4-135">삭제된 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="790c4-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="790c4-136">사용자 계정을 삭제하고 이제 이전 사서함을 공유 사서함으로 변환하려는 경우를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-136">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="790c4-137">다음 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-137">Here's what you need to do:</span></span>

1. <span data-ttu-id="790c4-138">[사용자 계정을 복원합니다.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="790c4-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="790c4-139">라이선스가 Microsoft 365 할당되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="790c4-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="790c4-140">사용자의 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="790c4-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="790c4-141">사서함을 다시 만들 때까지 20-30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="790c4-142">이제 이 페이지의 지침에 따라 사서함을 공유 사서함으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="790c4-143">그런 다음 사용자 사서함에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="790c4-144">사용자의 이전 사서함을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="790c4-145">공유 사서함은 앵커로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="790c4-146">공유 사서함에 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="790c4-147">공유 사서함을 사용자의 (개인) 사서함으로 다시 변환</span><span class="sxs-lookup"><span data-stu-id="790c4-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="790c4-148"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="790c4-149">받는 **사람 공유** \> **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="790c4-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="790c4-150">공유 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-150">Select the shared mailbox.</span></span> <span data-ttu-id="790c4-151">일반 **사서함으로 변환에서** 변환을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="790c4-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="790c4-152">관리 센터로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-152">Go back to the admin center.</span></span> <span data-ttu-id="790c4-153">사용자 **아래에서** 이전 공유 사서함과 연결된 사용자 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="790c4-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="790c4-154">계정에 라이선스를 할당하고 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="790c4-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="790c4-155">사서함을 설정하는 데 몇 분 정도 걸릴 수 있지만 그 후에 해당 계정을 사용하게 될 사람이 준비됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-155">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="790c4-156">로그인하면 공유 사서함에 있는 데 사용된 전자 메일 및 일정 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-156">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="790c4-157">하이브리드 환경에서 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="790c4-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="790c4-158">하이브리드 환경에서 사용자 사서함을 공유 사서함으로 변환하는 Exchange 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="790c4-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="790c4-159">Cmdlet - 프레미스 환경의 원격 공유 사서함을 만들거나 수정하는 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="790c4-160">공유 사서함은 하이브리드 배포에서 디렉터리 동기화가 실행된 후 예기치 않게 Exchange 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="790c4-161">조직 관리 또는 받는 사람 관리 역할 그룹의 구성원인 경우 Exchange 관리 셸을 사용하여 사용자 사서함을 공유 사서함을 사내 공유 사서함으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="790c4-162">예를 들면 `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="790c4-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="790c4-163">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="790c4-163">Related content</span></span>

<span data-ttu-id="790c4-164">[공유 사서함 정보](about-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="790c4-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="790c4-165">[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="790c4-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="790c4-166">[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="790c4-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="790c4-167">[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="790c4-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="790c4-168">[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="790c4-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
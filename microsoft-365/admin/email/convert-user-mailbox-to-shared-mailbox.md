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
ms.openlocfilehash: fa8e37b5e924f1b38755a953f40d8b70011213d0
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698282"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="46b07-103">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="46b07-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="46b07-104">사용자의 사서함을 공유 사서함으로 변환하면 모든 기존 전자 메일 및 일정이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="46b07-105">이제 한 사람이 아닌 여러 사람이 공유 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="46b07-106">나중에 공유 사서함을 사용자(개인) 사서함으로 다시 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="46b07-107">**다음은 알아야 할 몇 가지 중요한 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="46b07-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="46b07-108">변환할 사용자 사서함에는 공유 사서함으로 변환하기 전에 라이선스가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="46b07-109">그렇지 않으면 사서함을 변환하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="46b07-110">라이선스를 제거한 경우 사서함을 변환할 수 있도록 라이선스를 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="46b07-111">사서함을 공유 사서함으로 변환한 후 사용자 계정에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="46b07-112">공유 사서함에는 라이선스가 할당되지 않은 경우 최대 50GB의 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="46b07-113">이보다 많은 데이터를 저장하려면 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="46b07-114">라이선스를 제거할 수 있도록 공유 사서함에서 대용량 전자 메일(예: 첨부 파일이 있는 전자 메일)을 삭제하여 축소해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="46b07-115">이전 사용자의 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-115">Don't delete the old user's account.</span></span> <span data-ttu-id="46b07-116">공유 사서함의 기준이 앵커되는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="46b07-117">사용자 계정을 이미 삭제한 경우 삭제된 사용자의 사서함 [변환을 참조하세요.](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="46b07-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="46b07-118">사서함이 공유 사서함으로 변환된 후 규칙은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="46b07-119">Exchange 관리 센터를 사용하여 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="46b07-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="46b07-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="46b07-121">받는 **사람** \> **사서함을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b07-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="46b07-122">사용자 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-122">Select the user mailbox.</span></span> <span data-ttu-id="46b07-123">공유 **사서함으로 변환에서** 변환을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b07-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="46b07-124">사서함이 50GB보다 작은 경우 사용자에서 라이선스를 제거하고 해당 라이선스에 대한 비용을 지불하지 못하게 할 수 있습니다. [](../manage/remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="46b07-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="46b07-125">사용자 계정을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-125">Don't delete the user's account.</span></span> <span data-ttu-id="46b07-126">공유 사서함은 앵커로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="46b07-127">조직을 떠나는 직원의 사서함을 변환하는 경우 추가 단계를 수행하여 더 이상 로그인할 수 없는지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="46b07-128">Microsoft [365에서 이전 직원 제거를 참조 하시기 바랍니다.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="46b07-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="46b07-129">사서함 변환 중에 사용자 암호를 다시 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="46b07-130">그러나 암호를 다시 설정하지 않은 경우 **사서함** 변환이 완료된 후에도 원래 사용자 이름과 암호가 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="46b07-131">공유 사서함에 대해 알아야 할 모든 [](about-shared-mailboxes.md) 내용은 공유 사서함 및 공유 사서함 [만들기를 참조합니다.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="46b07-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="46b07-132">공유 사서함에는 별도의 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="46b07-133">그러나 원본 위치 보관을 사용하도록 설정하거나 공유 사서함에 원본 위치 유지 또는 소송 보존을 적용하려는 경우 Exchange Online Archiving이 있는 Exchange Online 계획 1 또는 Exchange Online 계획 2 라이선스를 사서함에 할당해야 입니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="46b07-134">삭제된 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="46b07-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="46b07-135">사용자 계정을 삭제했다가 이제 이전 사서함을 공유 사서함으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="46b07-136">다음과 같은 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="46b07-137">[사용자 계정을 복원합니다.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="46b07-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="46b07-138">Microsoft 365 라이선스가 할당되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="46b07-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="46b07-139">사용자의 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="46b07-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="46b07-140">사서함을 다시 만들 때까지 20-30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="46b07-141">이제 이 페이지의 지침에 따라 사서함을 공유 사서함으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="46b07-142">그런 다음 사용자 사서함에서 라이선스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="46b07-143">사용자의 이전 사서함을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="46b07-144">공유 사서함은 앵커로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="46b07-145">공유 사서함에 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="46b07-146">공유 사서함을 사용자의 (개인) 사서함으로 다시 변환</span><span class="sxs-lookup"><span data-stu-id="46b07-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="46b07-147"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="46b07-148">받는 **사람** \> **공유를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b07-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="46b07-149">공유 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-149">Select the shared mailbox.</span></span> <span data-ttu-id="46b07-150">일반 **사서함으로 변환에서** 변환을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b07-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="46b07-151">관리 센터로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-151">Go back to the admin center.</span></span> <span data-ttu-id="46b07-152">사용자 **아래에서** 이전 공유 사서함과 연결된 사용자 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="46b07-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="46b07-153">계정에 라이선스를 할당하고 암호를 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="46b07-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="46b07-154">사서함을 설정하는 데 몇 분 정도 걸릴 수 있지만, 그 후에 해당 계정을 사용하게 될 사람이 준비됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="46b07-155">로그인하면 공유 사서함에 있는 전자 메일 및 일정 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="46b07-156">하이브리드 환경에서 사용자의 사서함 변환</span><span class="sxs-lookup"><span data-stu-id="46b07-156">Convert a user's mailbox in a hybrid environment</span></span>

> [!NOTE] 
> <span data-ttu-id="46b07-157">2018년 10월 11일부터 Exchange 하이브리드 배포는 Exchange Server 2013용 누적 업데이트 21부터 원격 공유 사서함을 만들 수 있도록 지원하며, Exchange Server 2016의 경우 Exchange Server 환경에서 원격 공유 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-157">Starting October 11th, 2018, Exchange hybrid deployment supports the creation of remote shared mailboxes starting in Cumulative Update 21 for Exchange Server 2013 and Cumulative Update 10 for Exchange Server 2016 in an on-premises Exchange Server environment.</span></span> <span data-ttu-id="46b07-158">새 _-shared_ 매개 변수를 사용하여 원격 공유 사서함을 직접 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-158">You can directly create or modify a remote shared mailbox by using the new _-shared_ parameter.</span></span> <span data-ttu-id="46b07-159">자세한 내용은 [Cmdlet을](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange)방문하여 Exchange 환경의 원격 공유 사서함을 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-159">For more information, visit [Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange).</span></span>

<span data-ttu-id="46b07-160">이 공유 사서함이 하이브리드 환경에 있으며 위 시나리오에 속하지 않는 경우 사용자 사서함을 다시온-프레미스로 이동하고, 사용자 사서함을 공유 사서함으로 변환한 다음 공유 사서함을 다시 클라우드로 이동하는 것이 좋습니다(거의 필요함). </span><span class="sxs-lookup"><span data-stu-id="46b07-160">If this shared mailbox is in a hybrid environment and not falling under the above scenario, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="46b07-161">그 이유는 다음과 같습니다. 클라우드에서 사서함을 변환할 경우 변환할 수 있지만, 새 현실이 다시온-프레미스와 동기화되지 않는 것이기 때문에 여전히 사서함이 사용자 사서함으로 생각됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-161">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="46b07-162">일반적으로 이 문제는 문제가 되지 않지만 사서함이 사용자 사서함으로 생각되는 일부 시나리오에서는 해당 특성의 새 클라우드 버전을 덮어 사용할 수 있으며 그로 인해 사서함이 다시 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-162">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="46b07-163">사용자 사서함에 라이선스가 필요하거나 **30일이** 지난 후 소프트 삭제되는 경우 이는 문제입니다!</span><span class="sxs-lookup"><span data-stu-id="46b07-163">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="46b07-164">이 문제는 발생하는 대부분의 원인에 대해 해결했지만, 이 문제는 발생하기는 하지만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-164">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="46b07-165">안전한 사서함으로 사서함을 다시 이동하고, 사서함을 변환한 다음 공유 사서함을 클라우드로 다시 이동하는 것이 가장 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-165">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="46b07-166">이 권장 솔루션은 하이브리드 환경에 대한 라이선스 계약을 위반하지 않습니다. 사용자 사서함은 일시적으로만 존재하기 때문에</span><span class="sxs-lookup"><span data-stu-id="46b07-166">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="46b07-167">사용자 사서함 또는 공유 사서함을온-프레미스 조직에서 유지 관리하고 클라우드로 다시 이동하지 않은 경우 라이선스가 위반됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-167">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>


> [!NOTE]
> <span data-ttu-id="46b07-168">조직 관리 또는 받는 사람 관리 역할 그룹의 구성원인 경우 Exchange 관리 셸을 사용하여 사용자 사서함을 공유 사서함으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-168">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="46b07-169">예를 들면 `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46b07-169">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="46b07-170">공유 사서함이 예기치 않게 사용자 사서함으로 변환되는 경우 이 지원 솔루션의 해결 [방법(예:](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span><span class="sxs-lookup"><span data-stu-id="46b07-170">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="46b07-171">관련 문서</span><span class="sxs-lookup"><span data-stu-id="46b07-171">Related articles</span></span>

[<span data-ttu-id="46b07-172">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="46b07-172">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="46b07-173">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="46b07-173">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="46b07-174">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="46b07-174">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="46b07-175">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="46b07-175">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="46b07-176">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="46b07-176">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

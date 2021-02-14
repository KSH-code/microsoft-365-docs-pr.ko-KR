---
title: Exchange online에서 In-Place 사서함을 보류
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: 비활성으로 만들고 콘텐츠를 보존하기 위해 In-Place 사서함에 대한 보류를 만드는 방법을 알아보겠습니다.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818867"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="e2248-103">Exchange online에서 In-Place 사서함을 보류</span><span class="sxs-lookup"><span data-stu-id="e2248-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="e2248-104">비활성으로 만들고 콘텐츠를 보존하기 위해 In-Place 사서함에 대한 보류를 만드는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="e2248-105">그런 다음 Microsoft eDiscovery 도구를 사용하여 비활성 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2248-106">사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 EAC(Exchange 관리 센터)에서 In-Place 보류의 사용 중지를 발표하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="e2248-107">2020년 7월 1일부터는 Exchange Online에서 새 보류 In-Place 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="e2248-108">그러나 EAC에서 또는 Exchange Online PowerShell에서 **Set-MailboxSearch** cmdlet을 사용하여 In-Place 보류를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="e2248-109">그러나 2020년 10월 1일부터는 보류를 관리할 In-Place 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="e2248-110">EAC에서 또는 **Remove-MailboxSearch** cmdlet을 사용하여 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="e2248-111">보류의 사용 중지에 대한 In-Place 내용은 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2248-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="e2248-112">사용자가 조직을 떠났고 해당 사용자 계정 및 사서함이 삭제된 상황이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="e2248-113">그런 다음 사서함에 보존해야 하는 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="e2248-114">어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e2248-114">What can you do?</span></span> <span data-ttu-id="e2248-115">삭제된 사서함 보존 기간이 만료되지 않은 경우 In-Place 보류를 삭제된 사서함(소프트 삭제된 사서함)에 저장하고 비활성 사서함으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="e2248-116">*비활성 사서함은* 퇴사한 후 이전 직원의 전자 메일을 보존하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="e2248-117">비활성 사서함의 콘텐츠는 비활성 상태일 때 In-Place 사서함에 배치된 보존 기간 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="e2248-118">사서함이 비활성으로 설정된 후 Exchange Online의 In-Place eDiscovery &, 보안 및 준수 센터의 콘텐츠 검색 또는 SharePoint Online의 eDiscovery 센터를 사용하여 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e2248-119">Exchange Online에서 소프트 삭제된 사서함은 삭제되지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="e2248-120">Exchange Online의 사서함 보존 기간은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="e2248-121">즉, 삭제 후 30일 이내에 사서함을 복구하거나 비활성 사서함으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="e2248-122">30일이 지난 후 소프트 삭제된 사서함은 영구 삭제로 표시되고 복구되거나 비활성 상태일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="e2248-123">보류 In-Place 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2248-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="e2248-124">사서함을 소프트 삭제된 사서함에 Windows PowerShell In-Place **New-MailboxSearch** cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="e2248-125">SharePoint Online에서는 EAC(Exchange 관리 센터) 또는 eDiscovery 센터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="e2248-126">Windows PowerShell을 사용하여 Exchange Online에 연결하는 방법에 대한 자세한 내용은 [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2248-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="e2248-127">다음 명령을 실행하여 조직에서 소프트 삭제된 사서함에 대한 ID 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="e2248-128">비활성 사서함에 대한 자세한 내용은 [Office 365의 비활성 사서함 개요를 참조하세요.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="e2248-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="e2248-129">사서함을 In-Place 사서함을 비활성 사서함으로 만들기 위해 보류</span><span class="sxs-lookup"><span data-stu-id="e2248-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="e2248-130">**New-MailboxSearch** cmdlet을 사용하여 소프트 삭제된 사서함을 비활성 사서함으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="e2248-131">자세한 내용은 [New-MailboxSearch를 참조하십시오.](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2248-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="e2248-132">소프트 삭제된 사서함의 속성을 포함하는 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="e2248-133">이전 명령에서 **DistinguishedName** 또는 **ExchangeGuid** 속성 값을 사용하여 소프트 삭제된 사서함을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="e2248-134">이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 소프트 삭제된 사서함의 기본 SMTP 주소가 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="e2248-135">사서함을 In-Place 사서함에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="e2248-136">이 예에서는 보류 기간을 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="e2248-137">즉, 항목이 무기한으로 또는 비활성 사서함에서 보류가 제거될 때까지 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="e2248-138">보류를 만들 때 보류 기간을 In-Place 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="e2248-139">이 예에서는 비활성 사서함의 항목을 약 7년 동안 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="e2248-140">잠시 후 다음 명령 중 하나를 실행하여 소프트 삭제된 사서함이 비활성 사서함인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="e2248-141">또는</span><span class="sxs-lookup"><span data-stu-id="e2248-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="e2248-142">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e2248-142">More information</span></span>

<span data-ttu-id="e2248-143">소프트 삭제된 사서함을 비활성 사서함으로 만들면 여러 가지 방법으로 사서함을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2248-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="e2248-144">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2248-144">For more information, see:</span></span>
  
- [<span data-ttu-id="e2248-145">비활성 사서함의 유지 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="e2248-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="e2248-146">비활성 사서함 복구</span><span class="sxs-lookup"><span data-stu-id="e2248-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="e2248-147">비활성 사서함 복원</span><span class="sxs-lookup"><span data-stu-id="e2248-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="e2248-148">[비활성 사서함](delete-an-inactive-mailbox.md) 삭제(보류 제거)</span><span class="sxs-lookup"><span data-stu-id="e2248-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>

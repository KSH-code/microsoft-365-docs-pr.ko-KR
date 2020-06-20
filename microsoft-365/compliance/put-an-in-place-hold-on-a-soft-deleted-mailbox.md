---
title: Exchange Online에서 일시 삭제 된 사서함에 원본 위치 유지
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
description: 일시 삭제 된 사서함의 원본 위치 유지를 사용 하 여 비활성 상태로 만들고 해당 콘텐츠를 보존 하는 방법을 알아봅니다.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818867"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="85f15-103">Exchange Online에서 일시 삭제 된 사서함에 원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="85f15-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="85f15-104">일시 삭제 된 사서함의 원본 위치 유지를 사용 하 여 비활성 상태로 만들고 해당 콘텐츠를 보존 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="85f15-105">그런 다음 Microsoft eDiscovery 도구를 사용 하 여 비활성 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85f15-106">계속 해 서 사서함 콘텐츠를 보존 하는 다양 한 방법을 사용할 때 EAC (Exchange 관리 센터)에서 원본 위치 유지의 만료를 알리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="85f15-107">2020 년 7 월 1 일부 터 시작 Exchange Online에 새로운 현재 위치 유지를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="85f15-108">그러나 여전히 EAC에서 원본 위치 유지를 관리할 수 있으며 Exchange Online PowerShell에서 **new-mailboxsearch** cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="85f15-109">그러나 2020 년 10 월 1 일부 터 시작 하는 경우 원본 위치 유지를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="85f15-110">EAC에서 또는 **new-mailboxsearch** cmdlet을 사용 하 여 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="85f15-111">원본 위치 유지의 만료에 대 한 자세한 내용은 [레거시 eDiscovery 도구의 만료](legacy-ediscovery-retirement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85f15-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="85f15-112">사용자가 조직을 떠난 경우와 해당 사용자 계정 및 사서함이 삭제 된 상황이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="85f15-113">나중에 사서함에 보존 해야 하는 정보가 있음을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="85f15-114">어떤 작업을 수행 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="85f15-114">What can you do?</span></span> <span data-ttu-id="85f15-115">삭제 된 사서함 보존 기간이 만료 되지 않은 경우에는 삭제 된 사서함 (일시 삭제 된 사서함 이라고 함)에 원본 위치 유지를 설정 하 고 비활성 사서함으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="85f15-116">*비활성 사서함* 은 조직에서 이전 직원의 전자 메일을 보존 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="85f15-117">비활성 사서함의 콘텐츠는 비활성 상태로 설정 되었을 때 일시 삭제 된 사서함에 있던 원본 위치 유지 기간 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="85f15-118">사서함을 비활성화 한 후에는 Exchange Online의 원본 위치 eDiscovery, 보안 & 준수 센터의 콘텐츠 검색 또는 SharePoint Online의 eDiscovery Center를 사용 하 여 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85f15-119">Exchange Online에서 일시 삭제 된 사서함은 삭제 되었지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="85f15-120">Exchange Online의 일시 삭제 된 사서함 보존 기간은 30 일입니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="85f15-121">즉, 삭제 된 30 일 이내에 사서함을 복구 하거나 비활성 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="85f15-122">30 일이 지나면 일시 삭제 된 사서함은 영구적으로 삭제 되도록 표시 되며 복구 하거나 비활성 상태로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="85f15-123">원본 위치 유지에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85f15-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="85f15-124">Windows PowerShell에서 **new-mailboxsearch** cmdlet을 사용 하 여 일시 삭제 된 사서함을 원본 위치 유지 상태로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="85f15-125">SharePoint Online의 EAC (Exchange 관리 센터) 또는 eDiscovery 센터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="85f15-126">Windows PowerShell을 사용하여 Exchange Online에 연결하는 방법에 대한 자세한 내용은 [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85f15-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="85f15-127">다음 명령을 실행 하 여 조직의 일시 삭제 된 사서함에 대 한 id 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="85f15-128">비활성 사서함에 대 한 자세한 내용은 [Overview In Office 365의 비활성 사서함 개요](inactive-mailboxes-in-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85f15-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="85f15-129">일시 삭제 된 사서함에 원본 위치 유지를 적용 하 여 비활성 사서함으로 설정</span><span class="sxs-lookup"><span data-stu-id="85f15-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="85f15-130">**New-mailboxsearch** cmdlet을 사용 하 여 일시 삭제 된 사서함을 비활성 사서함으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="85f15-131">자세한 내용은 [new-mailboxsearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85f15-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="85f15-132">일시 삭제 된 사서함의 속성이 포함 된 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="85f15-133">이전 명령에서 **DistinguishedName** 또는 **ExchangeGuid** 속성 값을 사용 하 여 일시 삭제 된 사서함을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="85f15-134">이러한 속성은 조직의 각 사서함에 대해 고유 하지만 활성 사서함과 일시 삭제 된 사서함의 기본 SMTP 주소가 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="85f15-135">원본 위치 유지를 만들고 일시 삭제 된 사서함에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="85f15-136">이 예에서는 보존 기간을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="85f15-137">즉, 항목이 무기한으로 또는 비활성 사서함에서 제거 될 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="85f15-138">원본 위치 유지를 만들 때 보존 기간을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="85f15-139">이 예에서는 약 7 년 동안 비활성 사서함의 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="85f15-140">잠시 후에 다음 명령 중 하나를 실행 하 여 일시 삭제 된 사서함이 비활성 사서함 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="85f15-141">또는</span><span class="sxs-lookup"><span data-stu-id="85f15-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="85f15-142">추가 정보</span><span class="sxs-lookup"><span data-stu-id="85f15-142">More information</span></span>

<span data-ttu-id="85f15-143">일시 삭제 된 사서함을 비활성 사서함으로 설정한 후 사서함을 관리 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f15-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="85f15-144">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85f15-144">For more information, see:</span></span>
  
- [<span data-ttu-id="85f15-145">비활성 사서함의 유지 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="85f15-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="85f15-146">비활성 사서함 복구</span><span class="sxs-lookup"><span data-stu-id="85f15-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="85f15-147">비활성 사서함 복원</span><span class="sxs-lookup"><span data-stu-id="85f15-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="85f15-148">[비활성 사서함 삭제](delete-an-inactive-mailbox.md) (보존 제거)</span><span class="sxs-lookup"><span data-stu-id="85f15-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>

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
description: 일시 삭제 된 사서함의 원본 위치 유지를 사용 하 여 비활성 상태로 만들고 해당 콘텐츠를 보존 하는 방법을 알아봅니다. 그런 다음 Microsoft eDiscovery 도구를 사용 하 여 비활성 사서함을 검색할 수 있습니다.
ms.openlocfilehash: 1986a4bfca72c192b268984b7d2f49eb2e88134a
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978158"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="35125-104">Exchange Online에서 일시 삭제 된 사서함에 원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="35125-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="35125-105">일시 삭제 된 사서함의 원본 위치 유지를 사용 하 여 비활성 상태로 만들고 해당 콘텐츠를 보존 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="35125-105">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="35125-106">그런 다음 Microsoft eDiscovery 도구를 사용 하 여 비활성 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-106">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35125-107">계속 해 서 사서함 콘텐츠를 보존 하는 다양 한 방법을 사용할 때 EAC (Exchange 관리 센터)에서 원본 위치 유지의 만료를 알리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="35125-107">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="35125-108">2020 년 7 월 1 일부 터 시작 Exchange Online에 새로운 현재 위치 유지를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-108">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="35125-109">그러나 여전히 EAC에서 원본 위치 유지를 관리할 수 있으며 Exchange Online PowerShell에서 **new-mailboxsearch** cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-109">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="35125-110">그러나 2020 년 10 월 1 일부 터 시작 하는 경우 원본 위치 유지를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35125-110">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="35125-111">EAC에서 또는 **new-mailboxsearch** cmdlet을 사용 하 여 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35125-111">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="35125-112">원본 위치 유지의 만료에 대 한 자세한 내용은 [레거시 eDiscovery 도구의 만료](legacy-ediscovery-retirement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35125-112">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="35125-113">사용자가 조직을 떠난 경우와 해당 사용자 계정 및 사서함이 삭제 된 상황이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="35125-114">나중에 사서함에 보존 해야 하는 정보가 있음을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35125-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="35125-115">어떤 작업을 수행 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="35125-115">What can you do?</span></span> <span data-ttu-id="35125-116">삭제 된 사서함 보존 기간이 만료 되지 않은 경우에는 삭제 된 사서함 (일시 삭제 된 사서함 이라고 함)에 원본 위치 유지를 설정 하 고 비활성 사서함으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="35125-117">*비활성 사서함* 은 조직에서 이전 직원의 전자 메일을 보존 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35125-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="35125-118">비활성 사서함의 콘텐츠는 비활성 상태로 설정 되었을 때 일시 삭제 된 사서함에 있던 원본 위치 유지 기간 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35125-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="35125-119">사서함을 비활성화 한 후에는 Exchange Online의 원본 위치 eDiscovery, 보안 & 준수 센터의 콘텐츠 검색 또는 SharePoint Online의 eDiscovery Center를 사용 하 여 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-119">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="35125-120">Exchange Online에서 일시 삭제 된 사서함은 삭제 되었지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="35125-120">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="35125-121">Exchange Online의 일시 삭제 된 사서함 보존 기간은 30 일입니다.</span><span class="sxs-lookup"><span data-stu-id="35125-121">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="35125-122">즉, 삭제 된 30 일 이내에 사서함을 복구 하거나 비활성 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-122">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="35125-123">30 일이 지나면 일시 삭제 된 사서함은 영구적으로 삭제 되도록 표시 되며 복구 하거나 비활성 상태로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-123">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="35125-124">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="35125-124">Before you begin</span></span>

- <span data-ttu-id="35125-125">Windows PowerShell에서 **new-mailboxsearch** cmdlet을 사용 하 여 일시 삭제 된 사서함을 원본 위치 유지 상태로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35125-125">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="35125-126">SharePoint Online의 EAC (Exchange 관리 센터) 또는 eDiscovery 센터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-126">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="35125-127">Windows PowerShell을 사용하여 Exchange Online에 연결하는 방법에 대한 자세한 내용은 [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35125-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="35125-128">다음 명령을 실행 하 여 조직의 일시 삭제 된 사서함에 대 한 id 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35125-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="35125-129">비활성 사서함에 대 한 자세한 내용은 [Overview In Office 365의 비활성 사서함 개요](inactive-mailboxes-in-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35125-129">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="35125-130">일시 삭제 된 사서함에 원본 위치 유지를 적용 하 여 비활성 사서함으로 설정</span><span class="sxs-lookup"><span data-stu-id="35125-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="35125-131">**New-mailboxsearch** cmdlet을 사용 하 여 일시 삭제 된 사서함을 비활성 사서함으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-131">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="35125-132">자세한 내용은 [new-mailboxsearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35125-132">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="35125-133">일시 삭제 된 사서함의 속성이 포함 된 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35125-133">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="35125-134">이전 명령에서 **DistinguishedName** 또는 **ExchangeGuid** 속성 값을 사용 하 여 일시 삭제 된 사서함을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="35125-134">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="35125-135">이러한 속성은 조직의 각 사서함에 대해 고유 하지만 활성 사서함과 일시 삭제 된 사서함의 기본 SMTP 주소가 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-135">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="35125-136">원본 위치 유지를 만들고 일시 삭제 된 사서함에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="35125-136">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="35125-137">이 예에서는 보존 기간을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-137">In this example, no hold duration is specified.</span></span> <span data-ttu-id="35125-138">즉, 항목이 무기한으로 또는 비활성 사서함에서 제거 될 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35125-138">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="35125-139">원본 위치 유지를 만들 때 보존 기간을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-139">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="35125-140">이 예에서는 약 7 년 동안 비활성 사서함의 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="35125-140">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="35125-141">잠시 후에 다음 명령 중 하나를 실행 하 여 일시 삭제 된 사서함이 비활성 사서함 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35125-141">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="35125-142">또는</span><span class="sxs-lookup"><span data-stu-id="35125-142">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="35125-143">추가 정보</span><span class="sxs-lookup"><span data-stu-id="35125-143">More information</span></span>

<span data-ttu-id="35125-144">일시 삭제 된 사서함을 비활성 사서함으로 설정한 후 사서함을 관리 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35125-144">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="35125-145">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35125-145">For more information, see:</span></span>
  
- [<span data-ttu-id="35125-146">비활성 사서함의 유지 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="35125-146">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="35125-147">비활성 사서함 복구</span><span class="sxs-lookup"><span data-stu-id="35125-147">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="35125-148">비활성 사서함 복원</span><span class="sxs-lookup"><span data-stu-id="35125-148">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="35125-149">[비활성 사서함 삭제](delete-an-inactive-mailbox.md) (보존 제거)</span><span class="sxs-lookup"><span data-stu-id="35125-149">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>

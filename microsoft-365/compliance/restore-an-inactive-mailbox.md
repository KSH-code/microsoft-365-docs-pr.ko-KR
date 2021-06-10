---
title: 비활성 사서함 복원
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 비활성 사서함의 내용을 기존 사서함에 복원(또는 병합)하는 방법을 Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917302"
---
# <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="a7506-103">비활성 사서함 복원</span><span class="sxs-lookup"><span data-stu-id="a7506-103">Restore an inactive mailbox</span></span>

<span data-ttu-id="a7506-104">비활성 사서함(소프트 삭제된 사서함의 한 유형)은 퇴사한 후 이전 직원의 전자 메일을 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="a7506-105">다른 직원이 퇴사한 직원의 직무를 대신하거나 해당 직원이 조직으로 돌아오면 다음 두 가지 방법으로 사용자가 비활성 사서함의 콘텐츠를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span>

- <span data-ttu-id="a7506-106">**비활성 사서함 복원** 다른 직원이 퇴사한 직원의 직무를 대신하거나 다른 사용자가 비활성 사서함의 콘텐츠에 액세스해야 하는 경우 비활성 사서함의 내용을 기존 사서함으로 복원하거나 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-106">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="a7506-107">비활성 사서함에서 보관 파일을 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-107">You can also restore the archive from an inactive mailbox.</span></span> <span data-ttu-id="a7506-108">사서함이 복원된 후 비활성 사서함은 보존되고 비활성 사서함으로 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-108">After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox.</span></span> <span data-ttu-id="a7506-109">이 항목에서는 비활성 사서함을 복원하는 절차에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-109">This topic describes the procedures for restoring an inactive mailbox.</span></span>

- <span data-ttu-id="a7506-110">**비활성 사서함 복구** 퇴사한 직원이 조직으로 돌아오거나 퇴사한 직원의 직무를 위해 신입 사원이 고용된 경우 비활성 사서함의 내용을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="a7506-111">이 메서드는 비활성 사서함을 비활성 사서함의 내용이 포함된 새 사서함으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="a7506-112">복구한 후 비활성 사서함 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="a7506-113">단계별 절차는 [에서 비활성 사서함 복구를 Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="a7506-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

<span data-ttu-id="a7506-114">[비활성](#more-information) 사서함 복원 및 복구 간의 차이점에 대한 자세한 내용은 이 문서의 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7506-114">See the [More information](#more-information) section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="a7506-115">자동 확장 보관함으로 구성된 비활성 사서함은 복구하거나 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-115">You can't recover or restore an inactive mailbox that's configured with an auto-expanding archive.</span></span> <span data-ttu-id="a7506-116">자동 확장 보관함이 있는 비활성 사서함에서 데이터를 복구해야 하는 경우 콘텐츠 검색을 사용하여 사서함에서 데이터를 내보낼 수 있으며 다른 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-116">If you need to recover data from an inactive mailbox with an auto-expanding archive, use content search to export the data from the mailbox and then import to another mailbox.</span></span> <span data-ttu-id="a7506-117">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7506-117">For instructions, see following topics:</span></span>
>
> - [<span data-ttu-id="a7506-118">콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="a7506-118">Content search</span></span>](content-search.md)
> - [<span data-ttu-id="a7506-119">콘텐츠 검색 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="a7506-119">Export content search results</span></span>](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a><span data-ttu-id="a7506-120">비활성 사서함 복원 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7506-120">Requirements to restore an inactive mailbox</span></span>

- <span data-ttu-id="a7506-121">비활성 사서함을 복원 Exchange Online PowerShell을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-121">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="a7506-122">EAC(Exchange 관리 센터)는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="a7506-123">단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7506-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a7506-124">PowerShell에서 Exchange Online 명령을 실행하여 조직의 비활성 사서함에 대한 ID 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-124">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  <span data-ttu-id="a7506-125">이 명령에서 반환된 정보를 사용하여 특정 비활성 사서함을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-125">Use the information returned by this command to restore a specific inactive mailbox.</span></span>

- <span data-ttu-id="a7506-126">비활성 사서함에 대한 자세한 내용은 에서 [비활성 사서함을 Office 365.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a7506-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="restore-inactive-mailboxes"></a><span data-ttu-id="a7506-127">비활성 사서함 복원</span><span class="sxs-lookup"><span data-stu-id="a7506-127">Restore inactive mailboxes</span></span>

<span data-ttu-id="a7506-128">SourceMailbox 및 _TargetMailbox_ 매개 변수와  함께 **New-MailboxRestoreRequest** cmdlet을 사용하여 비활성 사서함의 콘텐츠를 기존 사서함으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-128">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="a7506-129">이 cmdlet 사용에 대한 자세한 내용은 [New-MailboxRestoreRequest 를 참조하세요.](/powershell/module/exchange/new-mailboxrestorerequest)</span><span class="sxs-lookup"><span data-stu-id="a7506-129">For more information about using this cmdlet, see [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).</span></span>

1. <span data-ttu-id="a7506-130">비활성 사서함의 속성을 포함하는 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-130">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="a7506-131">이전 명령에서 **DistinguishedName** 또는 **ExchangeGUID** 속성 값을 사용하여 비활성 사서함을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-131">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="a7506-132">이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 비활성 사서함의 기본 SMTP 주소가 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-132">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="a7506-133">비활성 사서함의 내용을 기존 사서함으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-133">Restore the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="a7506-134">비활성 사서함(원본 사서함)의 콘텐츠는 기존 사서함(대상 사서함)의 해당 폴더에 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-134">The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   <span data-ttu-id="a7506-135">또는 대상 사서함에서 비활성 사서함의 콘텐츠를 복원할 최상위 폴더를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-135">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox.</span></span> <span data-ttu-id="a7506-136">지정한 대상 폴더 또는 대상 폴더 구조가 대상 사서함에 아직 없는 경우 복원 프로세스 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-136">If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span>

   <span data-ttu-id="a7506-137">이 예에서는 비활성 사서함의 사서함 항목 및 하위 폴더를 대상 사서함의 최상위 폴더 구조에 있는 "비활성 사서함"이라는 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-137">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="a7506-138">비활성 사서함에서 보관함 복원</span><span class="sxs-lookup"><span data-stu-id="a7506-138">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="a7506-139">비활성 사서함에 보관 사서함이 있는 경우 기존 사서함의 보관 사서함으로 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-139">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="a7506-140">비활성 사서함에서 보관 파일을 복원하기 위해 비활성 사서함을 복원하는 데 사용되는 명령에 _SourceIsArchive_ 및 _TargetIsArchive_ 스위치를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-140">To restore the archive from an inactive mailbox, you have to add the _SourceIsArchive_ and _TargetIsArchive_ switches to the command used to restore an inactive mailbox.</span></span>

1. <span data-ttu-id="a7506-141">비활성 사서함의 속성을 포함하는 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-141">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > <span data-ttu-id="a7506-142">이전 명령에서 **DistinguishedName** 또는 **ExchangeGUID** 속성 값을 사용하여 비활성 사서함을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-142">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="a7506-143">이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 비활성 사서함의 기본 SMTP 주소가 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-143">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="a7506-144">비활성 사서함(원본 보관함)에서 기존 사서함의 보관함(대상 보관함)으로 보관함의 콘텐츠를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-144">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive).</span></span> <span data-ttu-id="a7506-145">이 예에서는 원본 보관함의 내용이 대상 사서함의 보관함에 있는 "비활성 사서함 보관함"이라는 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-145">In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a><span data-ttu-id="a7506-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a7506-146">More information</span></span>

- <span data-ttu-id="a7506-147">**비활성 사서함 복구 및 복원의 주요 차이점은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="a7506-147">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="a7506-148">비활성 사서함을 복구하면 기본적으로 사서함이 새 사서함으로 변환되고, 비활성 사서함의 콘텐츠와 폴더 구조가 보존되고, 사서함이 새 사용자 계정에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-148">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="a7506-149">복구된 비활성 사서함은 더 이상 존재하지 않습니다. 새 사서함의 콘텐츠에 대한 변경 내용은 원래 비활성 사서함에 보류된 콘텐츠에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-149">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="a7506-150">반대로 비활성 사서함을 복원할 때 콘텐츠는 다른 사서함으로만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-150">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="a7506-151">비활성 사서함은 보존되고 비활성 사서함으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-151">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="a7506-152">대상 사서함의 콘텐츠에 대한 변경 내용은 비활성 사서함에 있는 원래 콘텐츠에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-152">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="a7506-153">비활성 사서함은 콘텐츠 검색 도구를 [](content-search.md)사용하여 계속 검색할 수 있습니다. 해당 콘텐츠를 다른 사서함으로 복원하거나 나중에 복구하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-153">The inactive mailbox can still be searched by using the [Content Search tool](content-search.md), its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span>

- <span data-ttu-id="a7506-154">**비활성 사서함은 어떻게 찾을 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="a7506-154">**How do you find inactive mailboxes?**</span></span> <span data-ttu-id="a7506-155">조직의 비활성 사서함 목록을 표시하고 비활성 사서함을 복원하는 데 유용한 정보를 표시하기 위해 이 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-155">To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="a7506-156">**소송 보존 또는 Microsoft 365 정책을 사용하여 비활성 사서함 콘텐츠를 보존합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7506-156">**Use a Litigation Hold or Microsoft 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="a7506-157">비활성 사서함이 복원된 후 상태를 유지하려는 경우 대상 사서함을 소송 [](create-a-litigation-hold.md) 보존 상태로 설정하거나 비활성 사서함을 복원하기 전에 Microsoft 365 보존 정책을 적용할 수 있습니다. [](retention.md)</span><span class="sxs-lookup"><span data-stu-id="a7506-157">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](create-a-litigation-hold.md) or apply an [Microsoft 365 retention policy](retention.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="a7506-158">이렇게 하면 비활성 사서함의 항목이 대상 사서함으로 복원된 후 항목이 영구적으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-158">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span>

- <span data-ttu-id="a7506-159">**비활성 사서함을 복원하기 전에 대상 사서함에 대한 보존을 사용하도록 설정**</span><span class="sxs-lookup"><span data-stu-id="a7506-159">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="a7506-160">비활성 사서함의 사서함 항목은 오래 될 수 있으므로 비활성 사서함을 복원 하기 전에 대상 사서함에 대 한 보존을 사용 하도록 설정 하는 것이 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-160">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="a7506-161">사서함을 보존으로 설정하면 사서함에 할당된 보존 정책은 보존 보존이 제거되거나 보존 기간이 만료될 때까지 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-161">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="a7506-162">이렇게 하면 대상 사서함의 소유자가 비활성 사서함의 이전 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-162">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="a7506-163">그렇지 않은 경우 보존 정책은 대상 사서함에 대해 구성된 보존 설정에 따라 만료된 오래된 항목을 삭제하거나 보관 사서함으로 항목을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-163">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="a7506-164">자세한 내용은 [Place a mailbox on retention hold in Exchange Online.](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)</span><span class="sxs-lookup"><span data-stu-id="a7506-164">For more information, see [Place a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).</span></span>

- <span data-ttu-id="a7506-165">**AllowLegacyDNMismatch 스위치는 어떤 작업을 하나요?**</span><span class="sxs-lookup"><span data-stu-id="a7506-165">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="a7506-166">비활성 사서함을 복원하기 위한 이전 예에서는 **AllowLegacyDNMismatch** 스위치를 사용하여 비활성 사서함을 다른 대상 사서함으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-166">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="a7506-167">일반적인 복원 시나리오에서 목표는 원본 사서함과 대상 사서함이 동일한 사서함인 콘텐츠를 복원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-167">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="a7506-168">따라서 **기본적으로 New-MailboxRestoreRequest** cmdlet은 원본 및 대상 사서함의 **LegacyExchangeDN** 속성 값이 동일한지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-168">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="a7506-169">이렇게 하면 원본 사서함을 잘못된 대상 사서함으로 실수로 복원하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-169">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="a7506-170">**AllowLegacyDNMismatch** 스위치를 사용하지 않고 비활성 사서함을 복원하려고 하면 원본 사서함과 대상 사서함의 **LegacyExchangeDN** 속성 값이 다른 경우 명령이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-170">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span>

- <span data-ttu-id="a7506-171">**cmdlet과 함께 다른 매개 변수를 New-MailboxRestoreRequest 비활성 사서함에 대해 다른 복원 시나리오를 구현할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7506-171">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.**</span></span> <span data-ttu-id="a7506-172">예를 들어 이 명령을 실행하여 비활성 사서함의 보관 파일을 대상 사서함의 기본 사서함으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-172">For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="a7506-173">이 명령을 실행하여 비활성 기본 사서함을 대상 사서함의 보관함으로 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-173">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="a7506-174">**TargetRootFolder 매개 변수는 어떤 작업을 하나요?**</span><span class="sxs-lookup"><span data-stu-id="a7506-174">**What does the TargetRootFolder parameter do?**</span></span> <span data-ttu-id="a7506-175">앞서 설명한 것 처럼 **TargetRootFolder** 매개 변수를 사용하여 비활성 사서함의 콘텐츠를 복원할 대상 사서함의 폴더 구조 맨 위에 폴더(루트라고도함)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-175">As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox.</span></span> <span data-ttu-id="a7506-176">이 매개 변수를 사용하지 않는 경우 비활성 사서함의 사서함 항목이 대상 사서함의 해당 기본 폴더에 병합되어 사용자 지정 폴더가 대상 사서함의 루트에 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-176">If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox.</span></span> <span data-ttu-id="a7506-177">다음 그림에서는 **TargetRootFolder** 매개 변수를 사용하지 않는 경우와 사용하지 않는 것 간의 이러한 차이점을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="a7506-177">The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span>

  <span data-ttu-id="a7506-178">**TargetRootFolder 매개 변수가 사용되지 않는 경우 대상 사서함의 폴더 계층 구조**</span><span class="sxs-lookup"><span data-stu-id="a7506-178">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>

  ![TargetRootFolder 매개 변수가 사용되지 않는 경우의 스크린샷](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  <span data-ttu-id="a7506-180">**TargetRootFolder 매개 변수를 사용하는 경우 대상 사서함의 폴더 계층 구조**</span><span class="sxs-lookup"><span data-stu-id="a7506-180">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>

  ![TargetRootFolder 매개 변수가 사용된 경우의 스크린샷](../media/300da592-7323-48db-b8a4-07012259d113.png)
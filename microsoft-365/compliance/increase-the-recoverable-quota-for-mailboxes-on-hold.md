---
title: 보류된 사물함의 복구 가능한 항목 할당량 증가
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
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 보관 사서함을 사용하도록 설정하고 자동 확장 보관을 설정하여 Microsoft 365에서 사서함의 복구 가능한 항목 폴더 크기를 늘입니다.
ms.openlocfilehash: c674d3df4ad14dabce13effd0dd6729edaeab715
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804647"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="4ca0e-103">보류된 사물함의 복구 가능한 항목 할당량 증가</span><span class="sxs-lookup"><span data-stu-id="4ca0e-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="4ca0e-104">Exchange Online의 새 사서함에 자동으로 적용되는 기본 Exchange 보존 정책(기본 *MRM* 정책)에는 보관으로 14일 후의 복구 가능한 항목이라는 보존 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="4ca0e-105">이 보존 태그는 특정 항목의 보존 기간 14일이 만료되면 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 항목이 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="4ca0e-106">이렇게 항목이 이동하려면 사용자의 보관 사서함을 반드시 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="4ca0e-107">보관 사서함을 사용하도록 설정하지 않은 경우, 어떠한 조치도 취하지 않으면 보류된 사서함의 복구 가능한 항목 폴더에 있는 항목이 보존 기간 14일이 만료된 후에도 보관 사서함으로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="4ca0e-108">보류된 사서함에서 어떤 항목도 삭제되지 않기 때문에 복구 가능한 항목 폴더의 저장소 할당량이 초과될 수 있으며 사용자의 보관 사서함을 사용하도록 설정하지 않으면 특히 이러한 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="4ca0e-109">이 제한을 초과할 가능성이 줄어듭니다. Exchange Online의 사서함에 보류가 설정될 때 복구 가능한 항목 폴더의 저장소 할당량은 자동으로 30GB에서 100GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="4ca0e-110">보관 사서함을 사용하도록 설정하는 경우에도 보관 사서함에 있는 복구 가능한 항목 폴더의 저장소 할당량이 30GB에서 100GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="4ca0e-111">Exchange Online의 자동 확장 보관 기능을 사용하도록 설정하면 사용자의 보관함에서 복구 가능한 항목 폴더의 저장소 할당량에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="4ca0e-112"> 다음 표는 복구 가능한 항목 폴더의 저장소 할당량을 간략하게 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="4ca0e-113">**복구 가능한 항목 폴더 위치**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="4ca0e-114">**보류되지 않은 사서함**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="4ca0e-115">**보류된 사서함**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ca0e-116">기본 사서함</span><span class="sxs-lookup"><span data-stu-id="4ca0e-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="4ca0e-117">30GB</span><span class="sxs-lookup"><span data-stu-id="4ca0e-117">30 GB</span></span>  <br/> |<span data-ttu-id="4ca0e-118">100GB</span><span class="sxs-lookup"><span data-stu-id="4ca0e-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="4ca0e-119">보관 사서함<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ca0e-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="4ca0e-120">무제한</span><span class="sxs-lookup"><span data-stu-id="4ca0e-120">Unlimited</span></span>  <br/> |<span data-ttu-id="4ca0e-121">무제한</span><span class="sxs-lookup"><span data-stu-id="4ca0e-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="4ca0e-122">**복구 가능한 항목 폴더 할당량**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="4ca0e-123">무제한</span><span class="sxs-lookup"><span data-stu-id="4ca0e-123">Unlimited</span></span>  <br/> |<span data-ttu-id="4ca0e-124">무제한</span><span class="sxs-lookup"><span data-stu-id="4ca0e-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="4ca0e-125"><sup>\*</sup> Exchange Online(계획 2) 라이선스가 있는 사용자의 경우 보관 사서함의 초기 저장소 할당량은 100GB입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="4ca0e-126">그러나 보류된 사서함에 대해 자동 확장 보관이 설정되어 있는 경우 보관 사서함과 복구할 수 있는 항목 폴더의 저장소 할당량은 모두 110GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="4ca0e-127">필요한 경우 추가 보관 저장소 공간이 프로비전됩니다. 이 경우 무제한의 보관 저장소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="4ca0e-128">자동 확장 보관에 대한 자세한 내용은 [Office 365의](unlimited-archiving.md)무제한 보관 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="4ca0e-129">보류된 사서함의 기본 사서함에 있는 복구 가능한 항목 폴더의 저장소 할당량이 한도에 도달하려는 경우 다음 항목을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="4ca0e-130">**보관 사서함을 사용하도록 설정하고 자동 확장 보관을 하게 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="4ca0e-131">보관 사서함을 사용하도록 설정한 다음 Exchange Online에서 자동 확장 보관 기능을 켜기만 하면 복구 가능한 항목 폴더에 대해 무제한 저장소 용량을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="4ca0e-132">그러면 기본 사서함의 복구 가능한 항목 폴더에 대해 110GB가 필요하고 사용자의 보관함에 있는 복구 가능한 항목 폴더의 저장 용량이 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="4ca0e-133">방법 참조: 보안 및 준수 [센터에서](enable-archive-mailboxes.md) 보관 & 사용 하 고 [무제한 보관을 사용 하도록 설정 Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="4ca0e-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ca0e-134">복구 가능한 항목 폴더의 저장소 할당량 초과에 가까운 사서함에 대해 보관을 사용하도록 설정한 후 관리되는 폴더 도우미를 실행하여 도우미가 사서함을 수동으로 트리거하여 만료된 항목이 보관 사서함의 복구 가능한 항목 폴더로 이동하도록 사서함을 처리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="4ca0e-135">[4단계](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)에서 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="4ca0e-136">사용자의 사서함에 있는 다른 항목이 새로운 보관 사서함으로 이동되었을 수 있다는 점에 유의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="4ca0e-137">보관 사서함을 사용하도록 설정한 후에 이러한 일이 발생하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="4ca0e-138">**보류된 사서함에 대한 사용자 지정 Exchange 보존 정책을 만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="4ca0e-139">보관 사서함을 사용하도록 설정하고 소송 보존 또는 In-Place 사서함에 대해 보관을 자동으로 확장하는 것 외에도 보류된 사서함에 대한 사용자 지정 Exchange 보존 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="4ca0e-140">이렇게 하면 보류 중이 아닌 사서함에 적용되는 기본 MRM 정책과는 다른 보존 정책을 보류된 사서함에 적용할 수 있으며 보류된 사서함용으로 설계된 보존 태그를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="4ca0e-141">여기에는 복구 가능한 항목 폴더에 대한 새 보존 태그 만들기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="4ca0e-142">이 항목의 나머지에서는 보류된 사서함에 대한 사용자 지정 Exchange 보존 정책을 만드는 단계별 절차에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="4ca0e-143">1단계: 복구 가능한 항목 폴더에 대한 사용자 지정 보존 태그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-143">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[<span data-ttu-id="4ca0e-144">2단계: 보류된 사서함에 대한 새 Exchange 보존 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4ca0e-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="4ca0e-145">3단계: 보류된 사서함에 새 Exchange 보존 정책 적용</span><span class="sxs-lookup"><span data-stu-id="4ca0e-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="4ca0e-146">(옵션)4단계: 관리되는 폴더 도우미를 실행하여 새로운 보존 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="4ca0e-147">1단계: 복구 가능한 항목 폴더에 대한 사용자 지정 보존 태그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="4ca0e-148">첫 번째 단계는 복구 가능한 항목 폴더에 대하여 사용자 지정 보존 태그(보존 정책 태그 또는 RPT라고 함)를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="4ca0e-149">앞서 설명된 바와 같이 이 RPT는 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 항목을 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="4ca0e-150">PowerShell을 사용하여 복구 가능한 항목 폴더에 대한 RPT를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="4ca0e-151">EAC(Exchange 관리 센터)는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-151">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="4ca0e-152">원격 PowerShell을 사용하여 Exchange Online에 연결</span><span class="sxs-lookup"><span data-stu-id="4ca0e-152">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="4ca0e-153">복구할 수 있는 항목 폴더에 대한 새로운 RPT를 만들려면 다음 명령을 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="4ca0e-154">예를 들어 다음 명령은 보존 기간이 30일인 "보류된 사서함의 복구 가능한 항목 30일"이라는 복구 가능한 항목 폴더에 대한 RPT를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="4ca0e-155">이는 어떤 항목이 복구 가능한 항목 폴더에서 30일 동안 있은 후 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더로 이동함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="4ca0e-156">복구할 수 있는 항목 RPT의 보존  _기간(AgeLimitForRetention_ 매개 변수로 정의)은 RPT가 적용되는 사서함의 삭제된 항목 보존 기간과 동일하게 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="4ca0e-157">이렇게 하면 사용자가 삭제된 항목 보존 기간을 전부 활용하여 삭제된 항목이 보관 사서함으로 이동하기 전에 삭제된 항목을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="4ca0e-158">이전 예에서는 사서함의 삭제된 항목 보존 기간도 30일이라는 가정 하에 보존 기간이 30일로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="4ca0e-159">기본적으로 Exchange Online 사서함은 14일 동안 삭제된 항목을 보존하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="4ca0e-160">하지만 이 설정을 최대 30일로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="4ca0e-161">자세한 내용은 Exchange Online의 사서함에 대한 삭제된 항목 보존 [기간 변경을 참조하세요.](https://www.microsoft.com/?ref=go)</span><span class="sxs-lookup"><span data-stu-id="4ca0e-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="4ca0e-162">2단계: 보류된 사서함에 대한 새 Exchange 보존 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4ca0e-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="4ca0e-p110">다음 단계는 새로운 보존 정책을 만들고 1단계에서 만든 복구 가능한 항목 RPT 등 이 새로운 보존 정책에 보존 태그를 추가하는 것입니다. 새로운 보존 정책은 다음 단계에서 보류된 사서함에 적용됩니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="4ca0e-p111">새로운 보존 정책을 만들기 전에 추가할 추가적인 보존 태그를 결정합니다. 기본 MRM 정책에 추가되는 보존 태그의 목록 및 새로운 보존 태그에 대한 정보를 확인하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="4ca0e-167">Exchange Online의 기본 보존 정책</span><span class="sxs-lookup"><span data-stu-id="4ca0e-167">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="4ca0e-168">보존 정책 태그를 지원하는 기본 폴더</span><span class="sxs-lookup"><span data-stu-id="4ca0e-168">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="4ca0e-169">보존 정책 만들기 항목의 "보존 태그 [만들기" 섹션](https://go.microsoft.com/fwlink/p/?LinkId=404422)</span><span class="sxs-lookup"><span data-stu-id="4ca0e-169">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="4ca0e-170">EAC 또는 Exchange Online PowerShell을 사용하여 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="4ca0e-171">EAC를 사용하여 보존 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4ca0e-171">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="4ca0e-172">EAC에서 준수 **관리** 보존 정책으로 이동한 다음 아이콘 추가를 \>   ![ ](../media/ITPro-EAC-AddIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="4ca0e-173">**새 보존 정책** 페이지의 **이름** 에서 **MRM Policy for Mailboxes on Hold** 등 보존 정책의 목적을 설명하는 이름을 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="4ca0e-174">보존 **태그 아래에서** 아이콘 **추가를** ![ ](../media/ITPro-EAC-AddIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="4ca0e-175">보존 태그 목록에서 1단계에서 만든 복구 가능한 항목 RPT를 선택한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![사용자 지정 복구 가능한 항목 보존 태그 선택](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="4ca0e-p112">보존 정책에 추가할 추가적인 보존 태그를 선택합니다. 예를 들어 기존 MRM 정책에 포함되어 있는 것과 동일한 태그를 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="4ca0e-179">보존 태그 추가가 완료되면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-179">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="4ca0e-180">**저장** 을 클릭하여 새 보존 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-180">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="4ca0e-181">보존 정책에 연결된 보존 태그가 세부 정보 창에 표시된다는 점에 유의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![보존 정책에 연결된 보존 태그가 세부 정보 창에 표시됩니다.](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="4ca0e-183">Exchange Online PowerShell을 사용하여 보존 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4ca0e-183">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="4ca0e-184">보류된 사서함에 대한 새 보존 정책을 만들려면 다음 명령을 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-184">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="4ca0e-185">예를 들어 다음 명령은 이전 그림에 표시된 보존 정책 및 연결된 보존 태그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="4ca0e-186">3단계: 보류된 사서함에 새 Exchange 보존 정책 적용</span><span class="sxs-lookup"><span data-stu-id="4ca0e-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="4ca0e-187">마지막 단계는 조직의 보류된 사서함에 2단계에서 만든 새로운 보존 정책을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="4ca0e-188">EAC 또는 Exchange Online PowerShell을 사용하여 단일 사서함 또는 여러 사서함에 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="4ca0e-189">EAC를 사용하여 새 보존 정책 적용하기</span><span class="sxs-lookup"><span data-stu-id="4ca0e-189">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="4ca0e-190">받는 사람  >  **사서함으로 이동**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-190">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="4ca0e-191">목록 보기에서 보존 정책을 적용할 사서함을 선택하고 편집  ![ 아이콘을 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="4ca0e-192">**사용자 사서함** 페이지에서 **사서함 기능** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="4ca0e-193">**보존 정책** 에서 2단계에서 만든 보존 정책을 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="4ca0e-194">EAC를 사용하여 여러 사서함에 보존 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="4ca0e-195">받는 사람  >  **사서함으로 이동**</span><span class="sxs-lookup"><span data-stu-id="4ca0e-195">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="4ca0e-196">목록 보기에서 Shift 또는 Ctrl 키를 사용하여 여러 개의 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="4ca0e-197">세부 정보 창에서 **기타 옵션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-197">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="4ca0e-198">**보존 정책** 에서 **업데이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-198">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="4ca0e-199">**대량 할당 보존 정책** 페이지에서 2단계에서 만든 보존 정책을 선택하고  **저장** 을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="4ca0e-200">Exchange Online PowerShell을 사용하여 새 보존 정책 적용</span><span class="sxs-lookup"><span data-stu-id="4ca0e-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="4ca0e-201">Exchange Online PowerShell을 사용하여 단일 사서함에 새 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="4ca0e-202">그러나 PowerShell의 실질적인 강점은 이를 사용하여 조직의 소송 보존 또는 In-Place 보류 중인 모든 사서함을 빠르게 식별한 다음 단일 명령으로 보류된 모든 사서함에 새 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="4ca0e-203">다음은 Exchange PowerShell을 사용하여 하나 이상의 사서함에 보존 정책을 적용하는 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="4ca0e-204">모든 예에서는 2단계에서 만든 보존 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-204">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="4ca0e-205">이 예에서는 Pilar Pinilla의 사서함에 새로운 보존 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="4ca0e-206">이 예에서는 조직의 모든 소송 보존 사서함에 새로운 보존 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="4ca0e-207">이 예에서는 조직의 모든 원본 위치 유지 사서함에 새로운 보존 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="4ca0e-208">**Get-Mailbox** cmdlet를 사용하여 새로운 보존 정책이 적용되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="4ca0e-209">다음은 이전 예에서 소송 보존 사서함 및 원본 위치 유지 사서함에 "보류된 사서함에 대한 MRM 정책" 보존 정책이 적용되었는지 확인하기 위한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="4ca0e-210">(옵션) 4단계: 관리되는 폴더 도우미를 실행하여 새로운 보존 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="4ca0e-211">보류된 사서함에 새 Exchange 보존 정책을 적용한 후 관리되는 폴더 도우미가 새 보존 정책의 설정을 사용하여 이러한 사서함을 처리하려면 Exchange Online에서 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="4ca0e-212">관리되는 폴더 도우미가 실행되기를 기다리는 대신 **Start-ManagedFolderAssistant** cmdlet를 사용하여 새로운 보존 정책이 적용된 사서함을 처리하도록 도우미를 수동으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="4ca0e-213">다음 명령을 실행하여 Pilar Pinilla의 사서함에 관리되는 폴더 도우미를 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="4ca0e-214">다음 명령을 실행하여 보류된 모든 사서함에 관리되는 폴더 도우미를 실행합니다. </span><span class="sxs-lookup"><span data-stu-id="4ca0e-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="4ca0e-215">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4ca0e-215">More information</span></span>

- <span data-ttu-id="4ca0e-216">사용자의 보관 사서함을 사용하도록 설정한 후 사용자에게 사서함에 있는 다른 항목(복구 가능한 항목 폴더에 있는 항목 외)이 보관 사서함으로 이동될 수 있다는 점을 안내하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="4ca0e-217">Exchange Online 사서함에 할당된 기본 MRM 정책에는 항목이 사서함으로 배달되거나 사용자가 만든 날짜 후 2년 후에 항목을 보관 사서함으로 이동하는 보존 태그(기본값 2년 후 보관함으로 이동)가 포함되어 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="4ca0e-218">자세한 내용은 Exchange Online의 기본 [보존 정책을 참조하세요. ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="4ca0e-218">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="4ca0e-219">사용자의 보관 사서함을 사용하도록 설정한 후 사용자에게 보관 사서함의 복구 가능한 항목 폴더에서 삭제된 항목을 복구할 수 있다고 안내하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="4ca0e-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="4ca0e-220">보관 사서함에서 지우기 항목  폴더를 선택한 다음 홈 탭에서  서버에서 삭제된 항목 복구를 클릭하여 Outlook에서 이 작업을 할 **수** 있습니다. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="4ca0e-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 

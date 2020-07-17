---
title: 비활성 사서함 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없으면 비활성 사서함을 영구적으로 삭제할 수 있습니다.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817897"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="38a4d-103">비활성 사서함 삭제</span><span class="sxs-lookup"><span data-stu-id="38a4d-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="38a4d-104">비활성 사서함은 직원이 퇴사한 후에 해당 전자 메일을 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="38a4d-105">비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우에는 보류를 제거 하 여 비활성 사서함을 영구적으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="38a4d-106">또한 비활성 사서함에 여러 보류가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="38a4d-107">예를 들어 비활성 사서함은 소송 보존 및 하나 이상의 원본 위치 유지에 배치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="38a4d-108">또한 Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 만든 보존 정책이 비활성 사서함에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="38a4d-109">삭제 하려면 모든 보류 및 보존 정책을 비활성 사서함에서 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="38a4d-110">보류 및 보존 정책을 제거한 후 비활성 사서함은 삭제 되도록 표시 되며 처리 된 후 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="38a4d-111">계속 해 서 사서함 콘텐츠를 보존 하는 다양 한 방법을 사용할 때 Exchange 관리 센터에서 원본 위치 유지의 만료를 알리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="38a4d-112">즉, 소송 보유 및 보존 정책을 사용 하 여 비활성 사서함을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="38a4d-113">2020 년 7 월 1 일부 터 시작 Exchange Online에 새로운 현재 위치 유지를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="38a4d-114">그러나 비활성 사서함에 저장 된 원본 위치 유지의 보존 기간은 여전히 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="38a4d-115">그러나 2020 년 10 월 1 일부 터 시작 하는 경우에는 보존 기간을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="38a4d-116">원본 위치 유지를 제거 해야만 비활성 사서함을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="38a4d-117">원본 위치 유지 상태인 기존 비활성 사서함은 보존을 제거할 때까지 계속 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="38a4d-118">원본 위치 유지의 만료에 대 한 자세한 내용은 [레거시 eDiscovery 도구의 만료](legacy-ediscovery-retirement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a4d-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="38a4d-119">비활성 사서함에서 보류가 제거 된 후 발생 하는 작업에 대 한 설명을 보려면 [추가 정보](#more-information) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a4d-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="38a4d-120">비활성 사서함을 삭제 하기 전에</span><span class="sxs-lookup"><span data-stu-id="38a4d-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="38a4d-121">Exchange Online PowerShell을 사용 하 여 비활성 사서함에서 소송 보존을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="38a4d-122">EAC(Exchange 관리 센터)는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="38a4d-123">단계별 지침은 [Exchange Online PowerShell에 연결을](https://go.microsoft.com/fwlink/?linkid=396554)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="38a4d-124">Exchange Online PowerShell 또는 EAC를 사용 하 여 비활성 사서함에서 원본 위치 유지를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="38a4d-125">보류를 제거 하 고 비활성 사서함을 삭제 하기 전에 비활성 사서함의 내용을 다른 사서함에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="38a4d-126">자세한 내용은 [Office 365에서 비활성 사서함 복원을](restore-an-inactive-mailbox.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="38a4d-127">비활성 사서함에서 보류 또는 보존 정책을 제거 하는 경우 사서함의 일시 삭제 된 사서함 보존 기간이 만료 되 면 사서함이 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="38a4d-128">삭제 된 후에는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="38a4d-129">보류를 제거 하기 전에 사서함의 내용이 더 이상 필요 하지 않은지 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="38a4d-130">비활성 사서함을 다시 활성화 하려면 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="38a4d-131">자세한 내용은 [Office 365에서 비활성 사서함 복구](recover-an-inactive-mailbox.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="38a4d-132">비활성 사서함에 대 한 자세한 내용은 [Office 365의 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="38a4d-133">1 단계: 비활성 사서함의 보류 확인</span><span class="sxs-lookup"><span data-stu-id="38a4d-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="38a4d-134">앞에서 설명한 것 처럼 소송 보존, 원본 위치 유지 또는 보존 정책이 비활성 사서함에 배치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="38a4d-135">첫 번째 단계는 비활성 사서함에 대 한 보류를 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="38a4d-136">다음 명령을 실행 하 여 조직의 모든 비활성 사서함에 대 한 보류 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="38a4d-137">**LitigationHoldEnabled** 속성의 **True** 값은 비활성 사서함이 소송 보존 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="38a4d-138">비활성 사서함에 원본 위치 유지를 적용 하면 보류에 대 한 GUID가 **InPlaceHolds** 속성의 값으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="38a4d-139">예를 들어 두 비활성 사서함에 대 한 다음 결과는 소송 보존을 Ann Beebe에 배치 하 고 두 개의 원본 위치 유지가 Pilar Pinilla에 배치 된다는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="38a4d-140">전체 원본 위치 유지가 비활성 사서함에 배치 되는 경우에는 원본 위치 유지 Guid 중 일부가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="38a4d-141">다음 명령을 실행 하 여 모든 원본 위치 유지 Guid를 표시할 수 있습니다.`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="38a4d-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="38a4d-142">2 단계: 비활성 사서함에서 보류 제거</span><span class="sxs-lookup"><span data-stu-id="38a4d-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="38a4d-143">비활성 사서함에 적용 되는 보존 유형 및 여러 보류가 있는지 확인 한 후에는 사서함에서 보류를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="38a4d-144">앞에서 설명한 것 처럼 비활성 사서함을 영구적으로 삭제 하려면 모든 보류를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="38a4d-145">소송 보존 제거</span><span class="sxs-lookup"><span data-stu-id="38a4d-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="38a4d-146">앞에서 설명한 것 처럼, Windows PowerShell을 사용 하 여 비활성 사서함에서 소송 보존을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="38a4d-147">EAC는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-147">You can't use the EAC.</span></span> <span data-ttu-id="38a4d-148">다음 명령을 실행 하 여 소송 보존을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="38a4d-149">비활성 사서함을 식별 하는 가장 좋은 방법은 해당 고유 이름이 나 Exchange GUID 값을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="38a4d-150">이러한 값 중 하나를 사용 하면 실수로 잘못 된 사서함을 지정 하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="38a4d-151">원본 위치 유지 제거</span><span class="sxs-lookup"><span data-stu-id="38a4d-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="38a4d-152">비활성 사서함에서 원본 위치 유지를 제거 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="38a4d-153">원본 **위치 유지 개체 삭제** 영구적으로 삭제 하려는 비활성 사서함이 원본 위치 유지를 위한 유일한 사서함 인 경우 현재 위치 유지 개체만 삭제 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="38a4d-154">원본 위치 유지 개체를 삭제 하려면 먼저 보류를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-154">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="38a4d-155">보류가 사용 되도록 설정 된 원본 위치 유지 개체를 삭제 하려고 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="38a4d-156">**비활성 사서함을 원본 위치 유지의 소스 사서함으로 제거** 원본 위치 유지를 위해 다른 원본 사서함을 유지 하려는 경우 소스 사서함 목록에서 비활성 사서함을 제거 하 고 현재 위치 유지 개체를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="38a4d-157">EAC를 사용 하 여 원본 위치 유지 삭제</span><span class="sxs-lookup"><span data-stu-id="38a4d-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="38a4d-158">삭제할 원본 위치 유지의 이름을 알고 있는 경우 다음 단계를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="38a4d-159">그렇지 않으면 다음 명령을 실행 하 여 영구적으로 삭제 하려는 비활성 사서함에 저장 된 원본 위치 유지의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="38a4d-160">[1 단계: 비활성 사서함에서 보류 확인](#step-1-identify-the-holds-on-an-inactive-mailbox)에서 얻은 원본 위치 유지 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="38a4d-161">EAC에서 **규정 준수 관리** 원본 \> **위치 eDiscovery &amp; 유지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="38a4d-162">삭제할 원본 위치 유지를 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="38a4d-163">원본 **위치 eDiscovery &amp; 보류** 속성 페이지에서 원본 **위치 유지**를 클릭 하 고 **선택한 사서함에 있는 검색 쿼리와 일치 하는 콘텐츠를 보류에** 저장 상자를 선택 취소 한 후에 **Save**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="38a4d-164">원본 **위치 eDiscovery &amp; 유지** 페이지에서 원본 위치 유지를 다시 선택한 다음 삭제 아이콘 **삭제**를 클릭 ![ ](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="38a4d-165">경고에서 **예** 를 클릭 하 여 원본 위치 유지를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="38a4d-166">Exchange Online PowerShell을 사용 하 여 원본 위치 유지 삭제</span><span class="sxs-lookup"><span data-stu-id="38a4d-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="38a4d-167">삭제할 원본 위치 유지의 속성을 포함 하는 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="38a4d-168">[1 단계: 비활성 사서함에서 보류 확인](#step-1-identify-the-holds-on-an-inactive-mailbox)에서 얻은 원본 위치 유지 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="38a4d-169">원본 위치 유지에 대 한 보류를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="38a4d-170">원본 위치 유지를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="38a4d-171">EAC를 사용 하 여 원본 위치 유지에서 비활성 사서함 제거</span><span class="sxs-lookup"><span data-stu-id="38a4d-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="38a4d-172">비활성 사서함에 배치 된 원본 위치 유지의 이름을 알고 있는 경우 다음 단계를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="38a4d-173">그렇지 않으면 다음 명령을 실행 하 여 사서함에 배치 된 원본 위치 유지의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="38a4d-174">[1 단계: 비활성 사서함에서 보류 확인](#step-1-identify-the-holds-on-an-inactive-mailbox)에서 얻은 원본 위치 유지 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="38a4d-175">EAC에서 **규정 준수 관리** 원본 \> **위치 eDiscovery &amp; 유지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="38a4d-176">비활성 사서함에 저장 된 원본 위치 유지를 선택 하 고 편집 아이콘 편집을 클릭 **Edit** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="38a4d-177">원본 **위치 eDiscovery &amp; 보류** 속성 페이지에서 **원본을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="38a4d-178">원본 사서함 목록에서 제거 하려는 비활성 사서함의 이름을 클릭 하 고 제거 아이콘 **제거**를 클릭 ![ ](../media/adf01106-cc79-475c-8673-065371c1897b.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="38a4d-179">**저장**을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-179">Click **Save** to save the change.</span></span> <span data-ttu-id="38a4d-180">작업이 성공적으로 완료 되었음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-180">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="38a4d-181">비활성 사서함에 저장 된 다른 원본 위치 유지를 제거 하려면 1 ~ 6 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="38a4d-182">Exchange Online PowerShell을 사용 하 여 원본 위치 유지에서 비활성 사서함 제거</span><span class="sxs-lookup"><span data-stu-id="38a4d-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="38a4d-183">원본 사서함의 수가 많은 경우에는 비활성 사서함이 EAC의 **원본** 페이지에 나열 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="38a4d-184">원본 위치 유지를 편집 하면 **소스** 페이지에 최대 3000의 사서함이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="38a4d-185">비활성 사서함이 **원본** 페이지에 나열 되지 않은 경우 Exchange Online PowerShell을 사용 하 여 현재 위치 유지에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="38a4d-186">비활성 사서함에 배치 된 원본 위치 유지의 속성을 포함 하는 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="38a4d-187">[1 단계: 비활성 사서함에서 보류 확인](#step-1-identify-the-holds-on-an-inactive-mailbox)에서 얻은 원본 위치 유지 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="38a4d-188">비활성 사서함이 현재 위치 유지에 대 한 원본 사서함으로 나열 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="38a4d-189">**참고:** 원본 위치 유지의 *Sources* 속성은 소스 사서함을 해당 *LegacyExchangeDN* 속성으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="38a4d-190">이 속성은 비활성 사서함을 고유 하 게 식별 하므로 원본 위치 유지의 *Sources* 속성을 사용 하면 잘못 된 사서함을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="38a4d-191">이는 두 사서함의 별칭이 나 SMTP 주소가 같을 때 발생 하는 문제를 방지 하는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="38a4d-192">변수의 원본 사서함 목록에서 비활성 사서함을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="38a4d-193">이전 단계에서 명령에 의해 반환 되는 비활성 사서함의 **LegacyExchangeDN** 을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="38a4d-194">예를 들어 다음 명령은 Pilar Pinilla의 비활성 사서함을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="38a4d-195">비활성 사서함이 변수의 원본 사서함 목록에서 제거 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="38a4d-196">비활성 사서함이 포함 되지 않은 업데이트 된 원본 사서함 목록을 사용 하 여 현재 위치 유지를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="38a4d-197">현재 위치 유지를 위해 비활성 사서함이 원본 사서함 목록에서 제거 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="38a4d-198">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38a4d-198">More information</span></span>

- <span data-ttu-id="38a4d-199">**비활성 사서함은 일시 삭제 된 사서함의 유형입니다.**</span><span class="sxs-lookup"><span data-stu-id="38a4d-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="38a4d-200">Exchange Online에서 일시 삭제 된 사서함은 삭제 되었지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="38a4d-201">Exchange Online의 일시 삭제 된 사서함 보존 기간은 30 일입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="38a4d-202">즉, 사서함이 일시 삭제 된 30 일 이내에 복구 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="38a4d-203">30 일이 지나면 일시 삭제 된 사서함이 영구적으로 삭제 되도록 표시 되며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="38a4d-204">**비활성 사서함에서 보류를 제거한 후에 수행 되는 작업**</span><span class="sxs-lookup"><span data-stu-id="38a4d-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="38a4d-205">사서함은 일시적으로 삭제 된 다른 사서함 처럼 취급 되며 30 일 일시 삭제 된 사서함 보존 기간이 만료 되 면 영구 삭제로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="38a4d-206">이 보존 기간은 사서함을 처음으로 비활성화 한 날짜에 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="38a4d-207">이 날짜는 일시 삭제 된 날짜, 즉 해당 사용자 계정이 삭제 되거나 **사서함 제거** cmdlet을 사용 하 여 Exchange Online 사서함이 삭제 된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="38a4d-208">일시 삭제 된 날짜는 보류를 제거한 날짜가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="38a4d-209">**비활성 사서함이 보존을 제거한 즉시 영구적으로 삭제 됩니까?**</span><span class="sxs-lookup"><span data-stu-id="38a4d-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="38a4d-210">비활성 사서함의 일시 삭제 된 날짜가 30 일 보다 오래 된 경우 보존을 제거 하는 즉시 사서함이 영구적으로 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="38a4d-211">사서함은 영구적으로 삭제 되도록 표시 되며 다음에 처리 될 때 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="38a4d-212">**일시 삭제 된 사서함 보존 기간은 비활성 사서함에 어떤 영향을 줍니까?**</span><span class="sxs-lookup"><span data-stu-id="38a4d-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="38a4d-213">비활성 사서함의 일시 삭제 된 날짜가 보존을 제거한 날짜 보다 30 일 보다 많은 경우에는 사서함이 영구적으로 삭제 되도록 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="38a4d-214">그러나 비활성 사서함의 지난 30 일 이내에 일시 삭제 된 날짜가 있고 보존을 제거 하면 일시 삭제 된 사서함 보존 기간이 만료 될 때까지 사서함을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="38a4d-215">자세한 내용은 [Exchange Online에서 사용자 사서함 삭제 또는 복원을](https://go.microsoft.com/fwlink/?linkid=856835)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="38a4d-216">일시 삭제 된 사서함 보존 기간이 만료 되 면 비활성 사서함을 복구 하기 위한 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="38a4d-217">자세한 내용은 [Office 365에서 비활성 사서함 복구](recover-an-inactive-mailbox.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a4d-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="38a4d-218">**보류를 제거한 후 비활성 사서함에 대 한 정보를 표시 하는 방법은 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="38a4d-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="38a4d-219">보류를 제거 하 고 비활성 사서함이 일시 삭제 된 사서함으로 다시 되돌아간 후에는 **사서함** cmdlet과 함께 *Inactivemailboxonly* 매개 변수를 사용 하 여 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="38a4d-220">그러나 **undo-softdeletedmailbox** 명령을 사용 하 여 사서함에 대 한 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="38a4d-221">예시:</span><span class="sxs-lookup"><span data-stu-id="38a4d-221">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="38a4d-222">위의 예제에서, 다음 예제에서는 *일시 삭제 된* 날짜를 식별 하며이 예에서는 10 월 30 일을 2014 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="38a4d-223">이 일시 삭제 된 사서함이 보존을 제거한 이전에 비활성화 된 사서함 인 경우에는 소송 *소프트 deleted* 속성 값 다음에 30 일이 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="38a4d-224">이 경우 사서함은 11 월 30 2014 일 이후에 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4d-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>


---
title: 비활성 사서함 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: Microsoft 365 비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우 비활성 사서함을 영구적으로 삭제할 수 있습니다.
ms.openlocfilehash: d5acccbf37ee5b6958d282de14edafc0b9b00182
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717583"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="389ac-103">비활성 사서함 삭제</span><span class="sxs-lookup"><span data-stu-id="389ac-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="389ac-104">비활성 사서함은 조직에서 나서 이전 직원의 전자 메일을 보존하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="389ac-105">비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우 비활성 사서함을 영구적으로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="389ac-106">또한 비활성 사서함에 여러 보류가 배치될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="389ac-107">예를 들어 비활성 사서함은 소송 보류에 배치될 수 있으며 하나 이상의 소송 In-Place 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="389ac-108">또한 Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 만든 보존 정책이 비활성 사서함에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="389ac-109">비활성 사서함에서 모든 보류 및 보존 정책을 제거하여 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="389ac-110">보존 및 보존 정책을 제거한 후 비활성 사서함은 삭제로 표시되고 처리된 후 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="389ac-111">사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 Exchange 관리 센터에서 In-Place 보존의 사용 중지를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="389ac-112">즉, 소송 보존 및 보존 정책을 사용하여 비활성 사서함을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="389ac-113">2020년 7월 1일부터는 Exchange Online에서 보류를 In-Place 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="389ac-114">그러나 비활성 사서함에 배치된 보류 In-Place 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="389ac-115">그러나 2020년 10월 1일부터는 보류 기간을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="389ac-116">비활성 사서함은 비활성 사서함을 제거하여 비활성 사서함만 삭제할 In-Place 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="389ac-117">보류에 있는 In-Place 비활성 사서함은 보존이 제거될 때까지 계속 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="389ac-118">보류의 사용 중지에 대한 In-Place 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="389ac-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="389ac-119">[비활성 사서함에서](#more-information) 보류를 제거한 후 발생하는 일에 대한 설명은 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="389ac-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="389ac-120">비활성 사서함을 삭제하기 전에</span><span class="sxs-lookup"><span data-stu-id="389ac-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="389ac-121">Exchange Online PowerShell을 사용하여 비활성 사서함에서 소송 보류를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="389ac-122">EAC(Exchange 관리 센터)는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="389ac-123">단계별 지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="389ac-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="389ac-124">비활성 사서함의 내용을 다른 사서함에 복사한 후 보류를 제거하고 비활성 사서함을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="389ac-125">자세한 내용은 [Office 365에서 비활성 사서함 복원을 참조합니다.](restore-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="389ac-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="389ac-126">비활성 사서함에서 보존 또는 보존 정책을 제거하고 사서함에 대한 소프트 삭제된 사서함 보존 기간이 만료된 경우 사서함은 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="389ac-127">삭제된 후 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="389ac-128">보류를 제거하기 전에 사서함의 내용이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="389ac-129">비활성 사서함을 다시 활성화 하려는 경우 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="389ac-130">자세한 내용은 [Office 365에서 비활성 사서함 복구를 참조합니다.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="389ac-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="389ac-131">비활성 사서함에 대한 자세한 내용은 [Office 365의 비활성 사서함을 참조하세요.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="389ac-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="389ac-132">1단계: 비활성 사서함에 대한 보류 식별</span><span class="sxs-lookup"><span data-stu-id="389ac-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="389ac-133">앞서 설명한 것 처럼 소송 보존, In-Place 또는 보존 정책이 비활성 사서함에 배치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="389ac-134">첫 번째 단계는 비활성 사서함에 대한 보류를 식별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="389ac-135">다음 명령을 실행하여 조직의 모든 비활성 사서함에 대한 보류 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="389ac-136">**LitigationHoldEnabled** 속성의 **True** 값은 비활성 사서함이 소송 보류 상태임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="389ac-137">비활성 In-Place 사서함에 대해 보류의 GUID가 **InPlaceHolds** 속성 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="389ac-138">예를 들어 두 개의 비활성 사서함에 대한 다음 결과는 Ann Beebe에 소송 보존이 적용되어 있으며 pilar Pinilla에 In-Place 보존 정책이 적용되어 있는 것으로 나타 내보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="389ac-139">많은 In-Place 보류 또는 보존 정책이 비활성 사서함에 배치되는 경우 모든 In-Place 보류 GUID가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="389ac-140">다음 명령을 실행하여 InPlaceHolds 속성에 모든 GUID를 표시할 수 있습니다.  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="389ac-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="389ac-141">보류를 식별하는 방법에 대한 자세한 내용은 사서함에 배치된 보류 유형을 [식별하는 방법을 참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="389ac-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="389ac-142">2단계: 비활성 사서함에서 보류 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="389ac-143">비활성 사서함에 배치되는 보류 유형과 여러 보류가 있는지 여부를 확인한 후 다음 단계는 사서함의 보류를 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="389ac-144">앞서 설명한 것 처럼 비활성 사서함을 영구적으로 삭제하려면 모든 보류를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="389ac-145">소송 보류 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="389ac-146">앞서 설명한 것 처럼 비활성 사서함에서 Windows PowerShell 소송 보류를 제거 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="389ac-147">EAC는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-147">You can't use the EAC.</span></span> <span data-ttu-id="389ac-148">다음 명령을 실행하여 소송 보류를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="389ac-149">비활성 사서함을 식별하는 가장 좋은 방법은 고유 이름 또는 Exchange GUID 값을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="389ac-150">이러한 값 중 하나를 사용하면 잘못된 사서함을 실수로 지정하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="389ac-151">보존 정책에서 비활성 사서함 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="389ac-152">Microsoft 365 보존 정책에서 비활성 사서함을 제거하는 절차는 비활성 사서함에 할당된 보존 정책이 조직 전체 또는 명시적 보존 정책인지에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="389ac-153">은 비활성 사서함에 할당된 보존 정책 유형에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="389ac-154">조직의 모든 사서함에 할당된 조직 전체 보존 정책</span><span class="sxs-lookup"><span data-stu-id="389ac-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="389ac-155">Exchange Online PowerShell의 **Get-OrganizationConfig** cmdlet을 사용하여 조직 전체 보존 정책에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="389ac-156">특정 사서함에 할당된 특정 위치 보존 정책</span><span class="sxs-lookup"><span data-stu-id="389ac-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="389ac-157">특정 사용자의 콘텐츠 위치에 할당되는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="389ac-158">Exchange Online PowerShell에서 **Get-Mailbox -IncludeInactiveMailbox** cmdlet을 사용하여 특정 비활성 사서함에 할당된 보존 정책에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="389ac-159">조직 전체 보존 정책에서 비활성 사서함 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="389ac-160">Exchange Online PowerShell에서 다음 명령을 실행하여 조직 전체 보존 정책에서 비활성 사서함을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="389ac-161">비활성 사서함에 적용된 조직 전체 보존 정책을 식별하고 보존 정책의 GUID를 얻는 방법에 대한 자세한 내용은 사서함에 배치된 보류 유형을 식별하는 방법의 "Get-OrganizationConfig" 섹션을 [참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="389ac-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="389ac-162">또는 다음 명령을 실행하여 모든 조직 전체 정책에서 비활성 사서함을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="389ac-163">특정 위치 보존 정책에서 비활성 사서함 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="389ac-164">Security & Compliance [Center PowerShell에서](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 다음 명령을 실행하여 명시적 보존 정책에서 비활성 사서함을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-164">Run the following command in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="389ac-165">비활성 사서함에 적용된 특정 위치 보존 정책을 식별하고 보존 정책의 GUID를 얻는 방법에 대한 자세한 내용은 사서함에 배치된 보류 유형을 식별하는 방법의 "Get-Mailbox" 섹션을 [참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)</span><span class="sxs-lookup"><span data-stu-id="389ac-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="389ac-166">원본 위치 보존 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="389ac-167">비활성 사서함에서 보류를 In-Place 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="389ac-168">**Hold In-Place 삭제합니다.**</span><span class="sxs-lookup"><span data-stu-id="389ac-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="389ac-169">영구적으로 삭제할 비활성 사서함이 비활성 보류에 대한 유일한 원본 In-Place 보류 개체를 In-Place 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="389ac-170">Hold 개체를 삭제하려면 먼저 보류를 In-Place 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-170">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="389ac-171">보류를 사용하도록 In-Place Hold 개체를 삭제하려고 시도하면 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-171">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="389ac-172">비활성 사서함을 보류의 원본 **사서함으로 In-Place 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="389ac-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="389ac-173">보류에 대해 다른 원본 사서함을 In-Place 경우 원본 사서함 목록에서 비활성 사서함을 제거하고 비활성 사서함을 In-Place 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="389ac-174">보류 In-Place 삭제</span><span class="sxs-lookup"><span data-stu-id="389ac-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="389ac-175">삭제할 보류 In-Place 속성이 포함된 변수를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-175">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="389ac-176">1단계: In-Place 사서함에 대한 보류 확인에서 획득한 보류 GUID를 [사용할 수 있습니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="389ac-176">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="389ac-177">보류를 사용하지 In-Place.</span><span class="sxs-lookup"><span data-stu-id="389ac-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="389ac-178">보류 In-Place 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="389ac-179">비활성 사서함에서 비활성 In-Place 제거</span><span class="sxs-lookup"><span data-stu-id="389ac-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="389ac-180">원본 In-Place 사서함 수가 많은 경우 비활성 사서함이 EAC의 원본 페이지에 나열되지 않는  것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-180">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="389ac-181">보류를 편집하면 원본 페이지에 최대 3,000개 In-Place 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="389ac-181">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="389ac-182">비활성 사서함이 원본 페이지에 나열되지 않은 경우 Exchange Online PowerShell을 사용하여 비활성 사서함에서 제거할 In-Place 있습니다. </span><span class="sxs-lookup"><span data-stu-id="389ac-182">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="389ac-183">비활성 사서함에 배치된 In-Place 속성이 포함된 변수를 만드시오.</span><span class="sxs-lookup"><span data-stu-id="389ac-183">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="389ac-184">1단계: In-Place 사서함에 대한 보류 확인에서 획득한 보류 GUID를 [사용할 수 있습니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="389ac-184">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="389ac-185">비활성 사서함이 보류의 원본 사서함으로 In-Place 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="389ac-186">In-Place Hold의 *Sources* 속성은 *LegacyExchangeDN* 속성으로 원본 사서함을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-186">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="389ac-187">이 속성은 비활성 사서함을 고유하게 식별하기 때문에 In-Place 보류에서 *Sources* 속성을 사용하면 잘못된 사서함을 제거하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-187">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="389ac-188">또한 두 사서함의 별칭 또는 SMTP 주소가 같은 경우 문제를 방지하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-188">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="389ac-189">변수의 원본 사서함 목록에서 비활성 사서함을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-189">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="389ac-190">이전 단계의 명령에 의해 반환된 비활성 사서함의 **LegacyExchangeDN을** 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-190">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="389ac-191">예를 들어 다음 명령은 Pilar Pinilla의 비활성 사서함을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="389ac-192">비활성 사서함이 변수의 원본 사서함 목록에서 제거되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="389ac-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="389ac-193">비활성 In-Place 없는 업데이트된 원본 사서함 목록으로 보류를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="389ac-194">비활성 사서함이 비활성 사서함의 원본 사서함 목록에서 In-Place 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="389ac-195">추가 정보</span><span class="sxs-lookup"><span data-stu-id="389ac-195">More information</span></span>

- <span data-ttu-id="389ac-196">**비활성 사서함은 소프트 삭제된 사서함의 유형입니다.**</span><span class="sxs-lookup"><span data-stu-id="389ac-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="389ac-197">Exchange Online에서 소프트 삭제된 사서함은 삭제된 사서함이지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="389ac-198">Exchange Online에서 소프트 삭제된 사서함 보존 기간은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-198">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="389ac-199">즉, 사서함이 소프트 삭제된 후 30일 이내에 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-199">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="389ac-200">30일이 지난 후 소프트 삭제된 사서함은 영구적으로 삭제된 것으로 표시되고 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-200">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="389ac-201">**비활성 사서함에 대한 보류를 제거하면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="389ac-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="389ac-202">사서함은 다른 소프트 삭제된 사서함처럼 처리되고 30일의 소프트 삭제된 사서함 보존 기간이 만료되면 영구적으로 삭제된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="389ac-203">이 보존 기간은 사서함이 처음 비활성화된 날짜에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="389ac-204">이 날짜를 일시 삭제 날짜(해당 사용자 계정이 삭제된 날짜 또는 **Remove-Mailbox** cmdlet을 사용하여 Exchange Online 사서함이 삭제된 날짜)라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="389ac-205">일시 삭제된 날짜는 보류를 제거하는 날짜가 아니며,</span><span class="sxs-lookup"><span data-stu-id="389ac-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="389ac-206">**비활성 사서함은 보류가 제거된 직후 영구적으로 삭제하나요?**</span><span class="sxs-lookup"><span data-stu-id="389ac-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="389ac-207">비활성 사서함에 대한 일시 삭제 날짜가 30일보다 오래된 경우 보류를 제거하는 즉시 사서함이 영구적으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-207">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="389ac-208">사서함은 영구 삭제로 표시되고 다음에 처리될 때 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-208">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="389ac-209">**소프트 삭제된 사서함 보존 기간은 비활성 사서함에 어떤 영향을 미치나요?**</span><span class="sxs-lookup"><span data-stu-id="389ac-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="389ac-210">비활성 사서함에 대한 일시 삭제 날짜가 보류가 제거된 날짜보다 30일이 지난 경우 사서함은 영구 삭제로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="389ac-211">그러나 비활성 사서함이 지난 30일 이내에 일시 삭제된 날짜가 있는 경우 보류를 제거하면 일시 삭제된 사서함 보존 기간이 만료될 때까지 사서함을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="389ac-212">자세한 내용은 Exchange Online에서 사용자 사서함 삭제 또는 [복원을 참조하세요.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="389ac-212">For details, see [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="389ac-213">소프트 삭제된 사서함 보존 기간이 만료되면 비활성 사서함을 복구하기 위한 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-213">After the soft-deleted mailbox retention period expires, you have to follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="389ac-214">자세한 내용은 [Office 365에서 비활성 사서함 복구를 참조합니다.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="389ac-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="389ac-215">**보류가 제거된 후 비활성 사서함에 대한 정보를 표시하는 방법**</span><span class="sxs-lookup"><span data-stu-id="389ac-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="389ac-216">보류가 제거되고 비활성 사서함이 소프트 삭제된 사서함으로 되돌아가면 **Get-Mailbox** cmdlet과 *함께 InactiveMailboxOnly* 매개 변수를 사용하여 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="389ac-217">그러나 **Get-Mailbox -SoftDeletedMailbox** 명령을 사용하여 사서함에 대한 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="389ac-218">예제:</span><span class="sxs-lookup"><span data-stu-id="389ac-218">For example:</span></span>

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

  <span data-ttu-id="389ac-219">위의 예제에서 *WhenSoftDeleted* 속성은 일시 삭제된 날짜(이 예제에서는 2014년 10월 30일)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="389ac-220">이 소프트 삭제된 사서함이 이전에 보류가 제거된 비활성 사서함이면 *WhenSoftDeleted* 속성 값 이후 30일 후에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="389ac-221">이 경우 사서함은 2014년 11월 30일 이후에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="389ac-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

---
title: 비활성 사서함의 보존 기간 변경
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 사서함이 비활성 상태가 되 면 비활성 사서함에 할당 된 보류 또는 Office 365 보존 정책의 기간을 변경 합니다.
ms.openlocfilehash: 675e6eb36f762a50c3caafce07d09fda9ba9d98e
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126379"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="9e9bc-103">비활성 사서함의 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="9e9bc-103">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="9e9bc-104">비활성 사서함은 조직에서 이전 직원의 전자 메일을 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-104">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="9e9bc-105">소송 보존, 원본 위치 유지, Microsoft 365 보존 정책 또는 eDiscovery 사례와 관련 된 보류가 사서함에 배치 되 고 해당 사용자 계정이 삭제 되 면 사서함이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-105">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, a Microsoft 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding user account is deleted.</span></span> <span data-ttu-id="9e9bc-106">비활성 사서함의 콘텐츠는 비활성 상태로 설정 되기 전에 사서함에 적용 된 보류 기간 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-106">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="9e9bc-107">보류 기간은 복구 가능한 항목 폴더에서 항목이 보관 되는 기간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-107">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="9e9bc-108">복구 가능한 항목 폴더의 항목에 대 한 보존 기간이 만료 되 면 해당 항목이 비활성 사서함에서 영구적으로 삭제 (제거) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-108">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-109">사서함을 비활성화 한 후에는 비활성 사서함에 할당 된 보류 또는 Microsoft 365 보존 정책의 기간을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-109">After a mailbox is made inactive, you can change the duration of the hold or Microsoft 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9e9bc-110">계속 해 서 사서함 콘텐츠를 보존 하는 다양 한 방법을 사용할 때 Exchange 관리 센터에서 원본 위치 유지의 만료를 알리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-110">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="9e9bc-111">즉, 소송 보유 및 Microsoft 365 보존 정책을 사용 하 여 비활성 사서함을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-111">That means you should use Litigation Holds and Microsoft 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="9e9bc-112">2020 년 4 월 1 일부 터 Exchange Online에 새로운 현재 위치 유지를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-112">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="9e9bc-113">그러나 비활성 사서함에 저장 된 원본 위치 유지의 보존 기간은 여전히 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-113">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="9e9bc-114">그러나 2020 년 7 월 1 일부 터 시작 하는 경우에는 보류 시간을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-114">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="9e9bc-115">원본 위치 유지를 제거 해야만 비활성 사서함을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-115">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="9e9bc-116">원본 위치 유지 상태인 기존 비활성 사서함은 보존을 제거할 때까지 계속 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-116">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="9e9bc-117">원본 위치 유지의 만료에 대 한 자세한 내용은 [레거시 eDiscovery 도구의 만료](legacy-ediscovery-retirement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-117">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
## <a name="connect-to-powershell"></a><span data-ttu-id="9e9bc-118">PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="9e9bc-118">Connect to PowerShell</span></span>

- <span data-ttu-id="9e9bc-119">비활성 사서함의 소송 보존에 대 한 보존 기간을 변경 하려면 Exchange Online PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="9e9bc-120">EAC(Exchange 관리 센터)는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="9e9bc-121">그러나 Exchange Online PowerShell 또는 EAC를 사용 하 여 원본 위치 유지에 대 한 보존 기간을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="9e9bc-122">보안 및 준수 센터 또는 Security & 준수 센터 PowerShell을 사용 하 여 Microsoft 365 보존 정책에 대 한 유지 기간을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-122">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for a Microsoft 365 retention policy.</span></span>
    
- <span data-ttu-id="9e9bc-123">Exchange Online PowerShell 또는 보안 & 준수 센터 PowerShell에 연결 하려면 다음 항목 중 하나를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-123">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="9e9bc-124">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="9e9bc-124">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="9e9bc-125">보안 및 준수 센터 PowerShell에 연결하기</span><span class="sxs-lookup"><span data-stu-id="9e9bc-125">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="9e9bc-126">EDiscovery 사례와 관련 된 보류는 무제한 보존으로, 변경할 수 있는 보존 기간이 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-126">Holds associated with eDiscovery cases are infinite holds, which means there's no hold duration that can be changed.</span></span> <span data-ttu-id="9e9bc-127">항목이 영구적으로 또는 보류를 제거 하 고 비활성 사서함이 삭제 될 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-127">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="9e9bc-128">비활성 사서함에 대 한 자세한 내용은 [Microsoft 365의 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-128">For more information about inactive mailboxes, see [Inactive mailboxes in Microsoft 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="9e9bc-129">1 단계: 비활성 사서함의 보류 확인</span><span class="sxs-lookup"><span data-stu-id="9e9bc-129">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="9e9bc-130">비활성 사서함에는 여러 가지 유형의 보류 또는 하나 이상의 Microsoft 365 보존 정책이 적용 될 수 있으므로 첫 번째 단계는 비활성 사서함에 대 한 보류를 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-130">Because different types of holds or one or more Microsoft 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="9e9bc-131">Exchange Online PowerShell에서 다음 명령을 실행 하 여 조직의 모든 비활성 사서함에 대 한 보류 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-131">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

<span data-ttu-id="9e9bc-132">**LitigationHoldEnabled** 속성의 **True** 값은 비활성 사서함이 소송 보존 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-132">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="9e9bc-133">원본 위치 유지, eDiscovery 보류 또는 Microsoft 365 보존 정책이 비활성 사서함에 배치 되 면 보류 또는 보존 정책에 대 한 GUID가 **InPlaceHolds** 속성의 값으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-133">If an In-Place Hold, eDiscovery hold, or Microsoft 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="9e9bc-134">예를 들어 다음은 5 개의 비활성 사서함에 대 한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-134">For example, the following shows results for five inactive mailboxes.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

<span data-ttu-id="9e9bc-135">다음 표에는 각 사서함을 비활성화 하는 데 사용 되는 5 가지 서로 다른 보존 유형이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-135">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="9e9bc-136">**비활성 사서함**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-136">**Inactive mailbox**</span></span>|<span data-ttu-id="9e9bc-137">**보류 유형**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-137">**Hold type**</span></span>|<span data-ttu-id="9e9bc-138">**비활성 사서함에서 보류를 확인 하는 방법**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-138">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e9bc-139">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="9e9bc-139">Ann Beebe</span></span>  <br/> |<span data-ttu-id="9e9bc-140">소송 대기</span><span class="sxs-lookup"><span data-stu-id="9e9bc-140">Litigation Hold</span></span>  <br/> |<span data-ttu-id="9e9bc-141">*LitigationHoldEnabled* 속성은로 설정 됩니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="9e9bc-141">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="9e9bc-142">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="9e9bc-142">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="9e9bc-143">원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="9e9bc-143">In-Place Hold</span></span>  <br/> |<span data-ttu-id="9e9bc-144">*InPlaceHolds* 속성은 비활성 사서함에 배치 된 원본 위치 유지의 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-144">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-145">ID가 접두사로 시작 되지 않으므로 현재 위치 유지로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-145">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="9e9bc-146">`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`Exchange Online PowerShell의 명령을 사용 하 여 비활성 사서함의 원본 위치 유지에 대 한 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-146">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="9e9bc-147">고 대 Necaise</span><span class="sxs-lookup"><span data-stu-id="9e9bc-147">Mario Necaise</span></span>  <br/> |<span data-ttu-id="9e9bc-148">보안 & 준수 센터의 조직 전체 Microsoft 365 보존 정책</span><span class="sxs-lookup"><span data-stu-id="9e9bc-148">Organization-wide Microsoft 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="9e9bc-149">*InPlaceHolds* 속성은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-149">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="9e9bc-150">이는 하나 이상의 조직 전체 또는 (Exchange 전체) Microsoft 365 보존 정책이 비활성 사서함에 적용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-150">This indicates that one or more organization-wide or (Exchange-wide) Microsoft 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-151">이 경우 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Exchange Online PowerShell에서 명령을 실행 하 여 조직 전체의 Microsoft 365 보존 정책에 대 한 guid 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-151">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Microsoft 365 retention policies.</span></span> <span data-ttu-id="9e9bc-152">Exchange 사서함에 적용 되는 조직 전체 보존 정책의 GUID는 접두사로 시작 합니다 `mbx` (예:) `mbxa3056bb15562480fadb46ce523ff7b02` .</span><span class="sxs-lookup"><span data-stu-id="9e9bc-152">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="9e9bc-153">비활성 사서함에 적용 되는 Microsoft 365 보존 정책을 식별 하려면 Security & 준수 센터 PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-153">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="9e9bc-154">에이 옛 아들</span><span class="sxs-lookup"><span data-stu-id="9e9bc-154">Carol Olson</span></span>  <br/> |<span data-ttu-id="9e9bc-155">특정 사서함에 적용 되는 보안 & 준수 센터의 Microsoft 365 보존 정책</span><span class="sxs-lookup"><span data-stu-id="9e9bc-155">Microsoft 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="9e9bc-156">*InPlaceHolds* 속성은 비활성 사서함에 적용 되는 Microsoft 365 보존 정책의 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-156">The  *InPlaceHolds*  property contains the GUID of the Microsoft 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-157">GUID는 접두사로 시작 되므로 특정 사서함에 적용 되는 보존 정책 임을 확인할 수 있습니다 `mbx` .</span><span class="sxs-lookup"><span data-stu-id="9e9bc-157">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="9e9bc-158">비활성 사서함에 적용 된 보존 정책의 GUID가 `skp` 접두사로 시작 되 면 보존 정책이 비즈니스용 Skype 대화에 적용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-158">If the GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, it would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="9e9bc-159">비활성 사서함에 적용 되는 Microsoft 365 보존 정책을 식별 하려면 Security & 준수 센터 PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-159">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="9e9bc-160">`mbx` `skp` 이 명령을 실행할 때 or 접두사를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-160">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="9e9bc-161">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="9e9bc-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="9e9bc-162">보안 & 준수 센터의 eDiscovery 사례 보류</span><span class="sxs-lookup"><span data-stu-id="9e9bc-162">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="9e9bc-163">*InPlaceHolds* 속성은 비활성 사서함에 저장 된 eDiscovery 사례 보류의 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-163">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-164">GUID는 접두사로 시작 되므로 eDiscovery 사례 보류 임을 확인할 수 있습니다 `UniH` .</span><span class="sxs-lookup"><span data-stu-id="9e9bc-164">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="9e9bc-165">`Get-CaseHoldPolicy`보안 & 준수 센터 PowerShell에서 cmdlet을 사용 하 여 비활성 사서함의 보류가 연결 된 eDiscovery 사례에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-165">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="9e9bc-166">예를 들어 명령을 실행 `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 하 여 비활성 사서함에 대 한 사례 보류의 이름을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-167">`UniH`이 명령을 실행할 때 접두사를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-167">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="9e9bc-168">비활성 사서함의 보류가 연결 된 eDiscovery 사례를 식별 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-168">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="9e9bc-169">**참고:** 비활성 사서함에 대해서는 eDiscovery 보류를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-169">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="9e9bc-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="9e9bc-171">특정 시점에 법적 사례가 종료 되 고 사례와 관련 된 보류가 제거 되 고 eDiscovery 사례가 닫히거나 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-171">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="9e9bc-172">실제로 비활성 사서함에 있는 보류가 eDiscovery 사례와 연결 되 고 보류가 해제 되거나 eDiscovery 사례가 종료 되거나 삭제 되 면 비활성 사서함이 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-172">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="9e9bc-173">Microsoft 365 보존 정책에 대 한 자세한 내용은 [보존 정책 및 보존 레이블에 대 한](retention.md)자세한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-173">For more information about Microsoft 365 retention policies, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="9e9bc-174">2 단계: 비활성 사서함에 대 한 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="9e9bc-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="9e9bc-175">비활성 사서함에 적용 되는 보존 유형 및 여러 보류가 있는지 확인 한 후에는 보존 기간을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="9e9bc-176">소송 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="9e9bc-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="9e9bc-177">Exchange Online PowerShell을 사용 하 여 비활성 사서함에 있는 소송 보존의 보존 기간을 변경 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-177">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="9e9bc-178">EAC는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-178">You can't use the EAC.</span></span> <span data-ttu-id="9e9bc-179">다음 명령을 실행 하 여 보존 기간을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-179">Run the following command to change the hold duration.</span></span> <span data-ttu-id="9e9bc-180">이 예에서는 보존 기간이 무제한으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-180">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="9e9bc-181">따라서 비활성 사서함의 항목은 무기한 보존 되거나 보존 기간이 다른 값으로 변경 될 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="9e9bc-182">비활성 사서함을 식별 하는 가장 좋은 방법은 해당 **고유 이름이** 나 **Exchange GUID** 값을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-182">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value.</span></span> <span data-ttu-id="9e9bc-183">이러한 값 중 하나를 사용 하면 실수로 잘못 된 사서함을 지정 하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-183">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="9e9bc-184">원본 위치 유지 기간 변경</span><span class="sxs-lookup"><span data-stu-id="9e9bc-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="9e9bc-185">EAC 또는 Exchange Online PowerShell을 사용 하 여 원본 위치 유지에 대 한 보존 기간을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-185">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="9e9bc-186">EAC를 사용 하 여 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="9e9bc-186">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="9e9bc-187">변경할 원본 위치 유지의 이름을 알고 있는 경우 다음 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-187">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="9e9bc-188">그렇지 않으면 다음 명령을 실행 하 여 비활성 사서함에 배치 된 원본 위치 유지의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-188">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-189">[1 단계](#step-1-identify-the-holds-on-an-inactive-mailbox)에서 구한 원본 위치 유지 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-189">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="9e9bc-190">EAC에서 **규정 준수 관리** 원본 \> **위치 eDiscovery &amp; 유지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-190">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="9e9bc-191">변경 하려는 원본 위치 유지를 선택 하 고 편집 아이콘 편집을 선택 **Edit** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-191">Select the In-Place Hold you want to change, and then select **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="9e9bc-192">원본 **위치 eDiscovery &amp; 보류** 속성 페이지에서 원본 **위치 유지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-192">On the **In-Place eDiscovery &amp; Hold** properties page, select **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="9e9bc-193">현재 보존 기간에 따라 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-193">Do one of the following based on the current hold duration:</span></span>
    
    1. <span data-ttu-id="9e9bc-194">무제한 **보존** 을 선택 하 여 일정 기간 동안 항목을 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-194">Select **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
    2. <span data-ttu-id="9e9bc-195">특정 기간에 대 한 항목을 포함 하도록 **받은 날짜를 기준으로 항목을 보관할 일 수를 지정** 합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-195">Select **Specify number of days to hold items relative to their received date** to hold items for a specific period.</span></span> <span data-ttu-id="9e9bc-196">항목을 보유할 일 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-196">Type the number of days that you want to hold items for.</span></span> 
    
    ![원본 위치 유지 기간을 변경하는 작업의 스크린샷입니다.](../media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="9e9bc-198">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-198">Select **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="9e9bc-199">Exchange Online PowerShell을 사용 하 여 보존 기간 변경</span><span class="sxs-lookup"><span data-stu-id="9e9bc-199">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="9e9bc-200">변경할 원본 위치 유지의 이름을 알고 있는 경우 다음 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-200">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="9e9bc-201">그렇지 않으면 다음 명령을 실행 하 여 비활성 사서함에 배치 된 원본 위치 유지의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-201">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-202">[1 단계](#step-1-identify-the-holds-on-an-inactive-mailbox)에서 구한 원본 위치 유지 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-202">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="9e9bc-203">다음 명령을 실행 하 여 보존 기간을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-203">Run the following command to change the hold duration.</span></span> <span data-ttu-id="9e9bc-204">이 예에서는 보존 기간이 2555 일 (약 7 년)으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-204">In this example, the hold duration is changed to 2,555 days (approximately seven years).</span></span> 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="9e9bc-205">보류 시간을 무제한으로 변경 하려면 _-ItemHoldPeriod 무제한적_을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-205">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="9e9bc-206">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9e9bc-206">More information</span></span>

- <span data-ttu-id="9e9bc-207">**비활성 사서함의 항목에 대해 보존 기간을 계산 하는 방법**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-207">**How is the hold duration calculated for an item in an inactive mailbox?**</span></span> <span data-ttu-id="9e9bc-208">기간은 사서함 항목을 받거나 만든 원래 날짜부터 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-208">The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="9e9bc-209">**보존 기간이 만료 되 면 어떻게 됩니까?**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-209">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="9e9bc-210">복구 가능한 항목 폴더의 사서함 항목에 대해 보존 기간이 만료 되 면 해당 항목이 비활성 사서함에서 영구적으로 삭제 (제거) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-210">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-211">비활성 사서함에 대 한 보존 기간을 지정 하지 않은 경우에는 복구 가능한 항목 폴더의 항목은 제거 되지 않습니다 (비활성 사서함의 보존 기간이 변경 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="9e9bc-211">If there's no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="9e9bc-212">**비활성 사서함에서 Exchange 보존 정책이 여전히 처리 되 고 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-212">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="9e9bc-213">사용 하지 않을 경우 Exchange 보존 정책 (메시징 레코드 관리 또는 MRM, Exchange Online 기능)이 사서함에 적용 된 경우 **삭제** 보존 작업을 사용 하 여 구성 된 보존 태그는 비활성 사서함에서 계속 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-213">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-214">즉, 삭제 정책을 사용 하 여 태그가 지정 된 항목은 보존 기간이 만료 될 때 복구 가능한 항목 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-214">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="9e9bc-215">그런 다음 항목의 보존 기간이 만료 되 면 해당 항목이 비활성 사서함에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-215">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="9e9bc-216">이와 반대로 비활성 사서함에 할당 된 보존 정책에 포함 된 모든 보관 정책 (인, **보관 폴더로 이동** 보존 작업을 사용 하 여 구성 하는 보존 태그)은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-216">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored.</span></span> <span data-ttu-id="9e9bc-217">즉, 보존 기간이 만료 되 면 보관 정책으로 태그가 지정 된 비활성 사서함의 항목이 기본 사서함에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-217">That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires.</span></span> <span data-ttu-id="9e9bc-218">보관 사서함으로 또는 보관 사서함의 복구 가능한 항목 폴더를 이동 하지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-218">They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="9e9bc-219">사용자가 비활성 사서함에 로그인 할 수 없기 때문에 보관 정책을 처리 하기 위해 데이터 센터 리소스를 사용 해야 하는 이유는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-219">Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="9e9bc-220">**새로 보존 기간을 확인 하려면 다음 명령 중 하나를 실행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-220">**To check the new hold duration, run one of the following commands.**</span></span> <span data-ttu-id="9e9bc-221">첫 번째 명령은 소송 보존에 대 한 것입니다. 두 번째는 원본 위치 유지를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-221">The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="9e9bc-222">**일반 사서함 처럼 MFA (관리 되는 폴더 도우미)도 비활성 사서함을 처리 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-222">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="9e9bc-223">Exchange Online에서 MFA는 사서함을 약 7 일 마다 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-223">In Exchange Online, the MFA processes mailboxes approximately once every seven days.</span></span> <span data-ttu-id="9e9bc-224">비활성 사서함에 대 한 보존 기간을 변경한 후에는 **시작 ManagedFolderAssistant** cmdlet을 사용 하 여 비활성 사서함에 대 한 새 보존 기간을 즉시 처리 하도록 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-224">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="9e9bc-225">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-225">Run the following command.</span></span> 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="9e9bc-226">**비활성 사서함에 많은 보류를 적용 하는 경우에는 보류 Guid 중 일부가 표시 되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9e9bc-226">**If many holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="9e9bc-227">다음 명령을 실행 하 여 비활성 사서함에 저장 된 모든 보류 (소송 보존 제외)의 Guid를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e9bc-227">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```

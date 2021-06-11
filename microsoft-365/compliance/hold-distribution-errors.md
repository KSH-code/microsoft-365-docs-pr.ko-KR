---
title: eDiscovery 보류 오류 문제 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Core eDiscovery에서 보유자 및 비관리 데이터 원본에 적용된 법적 보유와 관련된 오류를 해결합니다.
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538474"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="2cb61-103">eDiscovery 보류 오류 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2cb61-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="2cb61-104">이 문서에서는 eDiscovery 보류에서 발생할 수 있는 일반적인 문제와 이러한 문제를 해결하는 방법에 대해 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="2cb61-105">이 문서에는 이러한 문제를 완화하거나 방지하는 데 도움이 되는 권장 사례도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="2cb61-106">권장 사례</span><span class="sxs-lookup"><span data-stu-id="2cb61-106">Recommended practices</span></span>

<span data-ttu-id="2cb61-107">eDiscovery 보류와 관련된 오류 수를 줄이면 다음과 같은 모범 사례가 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="2cb61-108">보류 배포가 계속 보류 중인 경우 상태 또는 는 보류 배포가 완료될 때까지 기다렸다가 추가 업데이트를 `On (Pending)` `Off (Pending)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="2cb61-109">보류 정책을 추가로 업데이트하기 전에 보류 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="2cb61-110">다음 명령을 실행하거나 PowerShell 스크립트에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="2cb61-111">각 트랜잭션에 대해 보류 정책을 반복적으로 업데이트하는 대신 단일 대량 요청으로 업데이트를 eDiscovery 보류에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="2cb61-112">예를 들어 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet을 사용하여 기존 보류 정책에 여러 사용자 사서함을 추가하기 위해 여러 사용자를 추가하기 위해 한 번만 실행하도록 명령을 실행(또는 스크립트에 코드 블록으로 추가)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="2cb61-113">**올바른 예**</span><span class="sxs-lookup"><span data-stu-id="2cb61-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="2cb61-114">**잘못된 예**</span><span class="sxs-lookup"><span data-stu-id="2cb61-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="2cb61-115">이전의 잘못된 예에서 cmdlet은 작업을 완료하기 위해 5번 별도로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="2cb61-116">보류 정책에 사용자를 추가하는 권장 사례에 대한 자세한 내용은 추가 정보 [섹션을 참조하세요.](#more-information)</span><span class="sxs-lookup"><span data-stu-id="2cb61-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="2cb61-117">eDiscovery 보류 문제에 대해 Microsoft 지원에 문의하기 전에 [오류/문제:](#errorissue-holds-dont-sync) 보류가 동기화되지 않습니다 섹션의 단계를 수행하여 보류 배포를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="2cb61-118">이 프로세스에서는 내부 서버 오류를 비롯한 일시적인 문제를 해결하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="2cb61-119">오류/문제: 보류가 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="2cb61-120">보유자 및 데이터 원본을 보류할 때 다음 오류 메시지가 표시되어 있는 경우 해결 단계를 사용하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="2cb61-121">리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="2cb61-122">최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="2cb61-123">일시적인 데이터 센터 문제로 인해 콘텐츠 원본에 정책을 Office 365 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="2cb61-124">현재 정책은 원본의 콘텐츠에 적용되지 않습니다. 따라서 차단된 배포에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="2cb61-125">이 문제를 해결하려는 경우 정책을 다시 재배포해 하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="2cb61-126">죄송합니다. 일시적인 내부 서버 오류로 인해 요청된 정책 변경을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="2cb61-127">30분 후 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="2cb61-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="2cb61-128">해결 방법</span><span class="sxs-lookup"><span data-stu-id="2cb61-128">Resolution</span></span>

1. <span data-ttu-id="2cb61-129">커넥트 보안 & [센터 PowerShell에](/powershell/exchange/connect-to-scc-powershell) 대한 정보를 보고 eDiscovery 보류에 대해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="2cb61-130">*DistributionDetail* 매개 변수의 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="2cb61-131">다음과 같은 오류를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="2cb61-132">오류: 리소스: 정책을 배포하는 데 예상보다 시간이 오래 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="2cb61-133">최종 배포 상태를 업데이트하는 데 추가 2시간이 걸릴 수 있으므로 몇 시간 후 다시 확인해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="2cb61-134">문제의 보류 정책에서 **Set-CaseHoldPolicy -RetryDistribution** 명령을 실행합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2cb61-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="2cb61-135">오류: SharePoint 사이트가 읽기 전용 또는 액세스 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="2cb61-136">보유자 및 데이터 원본을 보류할 때 다음 오류 [메시지가](/sharepoint/sharepoint-admin-role) 표시될 경우 조직의 전역 관리자 또는 SharePoint 사이트가 잠겨 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="2cb61-137">잠긴 사이트는 eDiscovery가 사이트에 보류를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="2cb61-138">사이트 SharePoint 읽기 전용 또는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="2cb61-139">사이트 관리자에게 문의하여 사이트를 필기할 수 있도록 설정한 다음 이 정책을 다시 재배포하세요.</span><span class="sxs-lookup"><span data-stu-id="2cb61-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="2cb61-140">해결 방법</span><span class="sxs-lookup"><span data-stu-id="2cb61-140">Resolution</span></span>

<span data-ttu-id="2cb61-141">이 문제를 해결하려면 사이트의 잠금을 해제합니다(또는 관리자에게 잠금 해제 요청).</span><span class="sxs-lookup"><span data-stu-id="2cb61-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="2cb61-142">사이트의 잠금 상태를 변경하는 방법에 대한 자세한 내용은 사이트 잠금 및 잠금 [해제를 참조하세요.](/sharepoint/manage-lock-status)</span><span class="sxs-lookup"><span data-stu-id="2cb61-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="2cb61-143">오류: 사서함 또는 SharePoint 사이트가 존재하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="2cb61-144">보유자 및 데이터 원본을 보류할 때 다음 오류 메시지가 표시되어 있는 경우 해결 단계를 사용하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="2cb61-145">사서함 또는 SharePoint 사이트가 존재하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="2cb61-146">이 문제가 올바르지 않은 경우 Microsoft 지원에 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="2cb61-147">그렇지 않은 경우 해당 정책에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="2cb61-148">해결 방법</span><span class="sxs-lookup"><span data-stu-id="2cb61-148">Resolution</span></span>

- <span data-ttu-id="2cb61-149">조직에 사용자 사서함이 Exchange Online PowerShell에서 [Get-Mailbox를](/powershell/module/exchange/get-mailbox) 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="2cb61-150">조직에 사이트가 SharePoint PowerShell에서 [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet을 실행하여 사이트가 조직에 존재하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="2cb61-151">사이트 URL이 변경된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="2cb61-152">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2cb61-152">More information</span></span>

<span data-ttu-id="2cb61-153">"권장 사례" 섹션에서 여러 사용자에 대한 보류 정책을 업데이트하는 지침은 시스템이 보류 정책에 대한 동시 업데이트를 차단하는 사실에서 비로소 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="2cb61-154">즉, 업데이트된 보류 정책이 새 콘텐츠 위치에 적용되고 보류 정책이 보류 중인 상태이면 보류 정책에 추가 콘텐츠 위치를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="2cb61-155">다음은 이 문제를 완화하는 데 도움이 있도록 유의해야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="2cb61-156">보류가 업데이트될 때마다 즉시 보류 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="2cb61-157">보류 상태는 보류가 콘텐츠 위치에 적용되고 있는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="2cb61-158">루프를 실행하고 정책을 하나씩 추가하는 스크립트가 있는 경우("권장 사례" 섹션에 표시된 잘못된 예와 유사함) 첫 번째 콘텐츠 위치(예: 사용자 사서함)는 보류 중인 상태를 트리거하는 동기화 프로세스를 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="2cb61-159">즉, 후속 루프에서 정책에 추가된 다른 사용자는 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="2cb61-160">조직에서 루프를 실행하여 보류 정책의 콘텐츠 위치를 업데이트하는 스크립트를 사용하는 경우 "권장 사례" 섹션의 올바른 예와 같이 단일 대량 작업에서 위치를 업데이트할 수 있도록 스크립트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb61-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>

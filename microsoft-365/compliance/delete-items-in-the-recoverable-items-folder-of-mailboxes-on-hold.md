---
title: 보류 가능한 항목 폴더의 클라우드 사서함에서 항목 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 사서함이 법적 보존 상태로 설정 된 경우에도 사용자의 복구 가능한 항목 폴더에서 Exchange Online 사서함의 항목을 삭제 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b4338784602826694b4683f3d000391592547a8
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127025"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="76703-103">보류에서 클라우드 기반 사서함의 복구 가능한 항목 폴더에 있는 항목 삭제-관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="76703-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="76703-104">Exchange Online 사서함에 대 한 복구 가능한 항목 폴더는 실수로 또는 악의적으로 삭제 되는 것을 방지 하기 위해 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="76703-105">또한 보류 및 eDiscovery 검색과 같은 규정 준수 기능에 의해 보존 되 고 액세스 되는 항목을 저장 하는 데도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="76703-106">그러나 조직에서 삭제 해야 하는 복구 가능한 항목 폴더에 실수로 보존 된 데이터가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="76703-107">예를 들어 사용자가 중요 한 정보를 포함 하는 전자 메일 메시지를 실수로 보내거나 전달할 수 있으며 비즈니스에 심각한 영향을 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="76703-108">메시지가 영구적으로 삭제 된 경우에도 사서함에 법적 보존이 설정 되어 있기 때문에 무기한 유지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="76703-109">이 시나리오는 데이터가 실수로 Office 365에 분산 되어 있기 때문에 데이터 유출 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-109">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="76703-110">이러한 상황에서는 사용자의 복구 가능한 항목 폴더에서 Exchange Online 사서함에 대 한 항목을 삭제할 수 있으며 해당 사서함이 Office 365의 다른 보존 기능 중 하 나와 함께 유지 되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="76703-111">이러한 유형의 보류에는 소송 보존, 원본 위치 유지, eDiscovery 보존 및 Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 만든 보존 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="76703-112">이 문서에서는 보류 중인 클라우드 기반 사서함에 대 한 복구 가능한 항목 폴더에서 항목을 삭제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-112">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="76703-113">이 절차에서는 사서함에 대 한 액세스를 사용 하지 않도록 설정 하 고, 단일 항목 복구를 사용 하지 않도록 설정 하 고, 관리 되는 폴더 도우미가 사서함을 처리 하 고, 일시적으로 보류를 제거 하 고, 복구 가능한 항목 폴더에서 항목을 삭제 한 다음 이전 구성으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="76703-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="76703-114">프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-114">Here's the process:</span></span> 
  
[<span data-ttu-id="76703-115">1 단계: 사서함에 대 한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="76703-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="76703-116">2 단계: 사서함 준비</span><span class="sxs-lookup"><span data-stu-id="76703-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="76703-117">3 단계: 사서함에서 모든 보류 제거</span><span class="sxs-lookup"><span data-stu-id="76703-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="76703-118">4 단계: 사서함에서 지연 된 보류 제거</span><span class="sxs-lookup"><span data-stu-id="76703-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="76703-119">5 단계: 복구 가능한 항목 폴더에서 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="76703-119">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="76703-120">6 단계: 사서함을 이전 상태로 되돌리기</span><span class="sxs-lookup"><span data-stu-id="76703-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="76703-121">이 문서에서 설명 하는 절차에 따라 Exchange Online 사서함에서 데이터가 영구적으로 삭제 (제거) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="76703-122">즉, 복구 가능한 항목 폴더에서 삭제 한 메시지는 복구할 수 없으며, 법적 검색 이나 다른 규정 준수 용도로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="76703-123">보안 및 준수 센터에서 만든 소송 보존, 원본 위치 유지, eDiscovery 보존 또는 보관 정책의 일부로 보류 중인 사서함에서 메시지를 삭제 하려면 보류를 제거 하기 전에 레코드 관리 또는 법률 부서에 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="76703-124">조직에 보류 중인 사서함 또는 데이터 유출 인시던트가 우선적으로 적용 되는지 여부를 정의 하는 정책이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-delete-items"></a><span data-ttu-id="76703-125">항목을 삭제 하기 전에</span><span class="sxs-lookup"><span data-stu-id="76703-125">Before you delete items</span></span>

- <span data-ttu-id="76703-126">콘텐츠 검색을 만들고 실행하려면 eDiscovery 관리자 역할 그룹의 구성원이거나 준수 검색 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="76703-127">메시지를 삭제하려면 조직 관리 역할 그룹의 구성원이거나 검색 및 제거 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="76703-128">역할 그룹에 사용자를 추가하는 방법에 대한 자세한 내용은 [보안 및 준수 센터의 eDiscovery 권한 부여](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).</span></span>

- <span data-ttu-id="76703-129">이 문서에서 설명 하는 절차는 비활성 사서함에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="76703-130">보류 (또는 보존 정책)를 제거한 후에 비활성 사서함에 다시 적용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="76703-131">비활성 사서함에서 보류를 제거 하면 일시 삭제 된 일반 사서함으로 변경 되 고 관리 되는 폴더 도우미에 의해 처리 된 후 조직에서 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="76703-132">보존 잠금으로 잠긴 보호 정책에 할당 된 사서함에 대해서는이 절차를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-132">You can't perform this procedure for a mailbox that has been assigned to a retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="76703-133">이는 보존 잠금 때문에 사서함에 대 한 관리 되는 폴더 도우미를 사용 하지 않도록 설정 하는 것을 방지 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-133">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="76703-134">보존 정책 잠금에 대 한 자세한 내용은 [Use 보존이 Lock을 사용 하 여 규정 요구 사항 준수](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-134">For more information about locking retention policies,see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

- <span data-ttu-id="76703-135">사서함이 보류 되지 않거나 단일 항목 복구를 사용 하도록 설정 되지 않은 경우 복구 가능한 항목 폴더에서 항목을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="76703-136">이 작업을 수행 하는 방법에 대 한 자세한 내용은 [조직에서 전자 메일 메시지 검색 및 삭제](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-136">For more information about how to do this, see [Search for and delete email messages in your organization](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="76703-137">1 단계: 사서함에 대 한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="76703-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="76703-138">첫 번째 단계는이 절차에 영향을 주는 대상 사서함에서 선택한 속성을 수집 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="76703-139">복구 가능한 항목 폴더에서 항목을 삭제 한 후 이러한 속성 중 일부를 변경 하 고 6 단계에서 원래 값으로 되돌리는 것 이므로 이러한 설정을 기록 하거나 텍스트 파일에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="76703-140">여기에는 수집 해야 하는 사서함 속성의 목록이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="76703-141">*Singleitemrecoveryenabled* 및 *RetainDeletedItemsFor*.</span><span class="sxs-lookup"><span data-stu-id="76703-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="76703-142">필요한 경우 한 번 복구를 사용 하지 않도록 설정 하 고 3 단계에서 삭제 된 항목 보존 기간을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="76703-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 

- <span data-ttu-id="76703-143">*LitigationHoldEnabled* 및 *InPlaceHolds*</span><span class="sxs-lookup"><span data-stu-id="76703-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="76703-144">3 단계에서 일시적으로 제거할 수 있도록 사서함에 설정 된 모든 보류를 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="76703-145">사서함에 저장 될 수 있는 유형 보존을 식별 하는 방법에 대 한 팁을 보려면 [추가 정보](#more-information) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 

<span data-ttu-id="76703-146">또한 사서함 클라이언트 액세스 설정을 일시적으로 사용 하지 않도록 설정 하 여 소유자 (또는 다른 사용자)가이 절차 중에 사서함에 액세스할 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="76703-147">마지막으로 복구 가능한 항목 폴더의 현재 크기 및 항목 수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="76703-148">5 단계에서 복구 가능한 항목 폴더의 항목을 삭제 한 후에는이 정보를 사용 하 여 항목이 제거 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="76703-149">[Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="76703-149">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="76703-150">Exchange Online에서 적절 한 관리 역할이 할당 된 관리자 계정에 대해 사용자 이름과 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="76703-151">다음 명령을 실행 하 여 단일 항목 복구 및 삭제 된 항목 보존 기간에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="76703-152">단일 항목 복구를 사용 하도록 설정 하면 2 단계에서이를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="76703-153">삭제 된 항목 보존 기간이 30 일 (Exchange Online의 최대값)으로 설정 되지 않은 경우 2 단계에서이를 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="76703-154">다음 명령을 실행 하 여 사서함에 대 한 사서함 액세스 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-154">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="76703-155">2 단계에서 이러한 모든 access 메서드를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-155">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="76703-156">다음 명령을 실행 하 여 사서함에 적용 된 보류 및 보존 정책에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="76703-157">*InPlaceHolds* 속성에 값이 너무 많고 이러한 속성이 모두 표시 되지 않는 경우에는 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 명령을 실행 하 여 각 값을 별도의 줄에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="76703-158">다음 명령을 실행 하 여 조직 차원의 보존 정책에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   <span data-ttu-id="76703-159">조직에서 조직 차원의 보존 정책을 사용 하는 경우에는 3 단계에서 이러한 정책 으로부터 사서함을 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="76703-160">*InPlaceHolds* 속성에 값이 너무 많고 이러한 속성이 모두 표시 되지 않는 경우에는 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 명령을 실행 하 여 각 값을 별도의 줄에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="76703-161">다음 명령을 실행 하 여 사용자의 기본 사서함에 있는 복구할 수 있는 항목 폴더에서 폴더 및 하위 폴더의 현재 크기와 총 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-161">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="76703-162">사용자의 보관 사서함을 사용할 수 있는 경우 다음 명령을 실행 하 여 보관 사서함에서 복구 가능한 항목 폴더의 폴더 및 하위 폴더에 있는 항목의 크기 및 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-162">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="76703-163">5 단계에서 항목을 삭제 하는 경우 사용자의 기본 보관 사서함에서 복구 가능한 항목 폴더의 항목을 삭제 하거나 삭제 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-163">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="76703-164">사서함에 대해 자동 확장 보관을 사용 하도록 설정 된 경우 보조 보관 사서함의 항목은 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-164">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="76703-165">2 단계: 사서함 준비</span><span class="sxs-lookup"><span data-stu-id="76703-165">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="76703-166">사서함에 대 한 정보를 수집 하 고 저장 한 다음에는 다음 작업을 수행 하 여 사서함을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-166">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="76703-167">사서함 소유자가 사서함에 액세스할 수 없도록 사서함에 대 한 **클라이언트 액세스를 사용 하지 않도록 설정** 하 고이 절차 중에 사서함 데이터를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-167">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="76703-168">**삭제 된 항목 보존 기간** 을 5 단계에서 삭제 하기 전에 복구 가능한 항목 폴더에서 항목을 제거 하지 않도록 최대 30 일 (Exchange Online의 최대값)으로 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="76703-168">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="76703-169">5 단계에서 복구 가능한 항목 폴더에서 항목을 삭제 한 후 항목이 보존 되지 않도록 하려면 **단일 항목 복구를 사용 하지 않도록 설정** 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-169">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="76703-170">사서함을 처리 하지 않고 5 단계에서 삭제 한 항목을 유지 하도록 **관리 되는 폴더 도우미를 사용 하지 않도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="76703-170">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="76703-171">Exchange Online PowerShell에서 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-171">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="76703-172">다음 명령을 실행 하 여 사서함에 대 한 모든 클라이언트 액세스를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-172">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="76703-173">명령 구문에서는 사서함에서 모든 클라이언트 액세스 방법을 사용 하도록 설정 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-173">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="76703-174">사서함에 대 한 모든 클라이언트 액세스 방법을 사용 하지 않도록 설정 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-174">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="76703-175">이러한 access 메서드를 사용 하지 않도록 설정 해도 현재 로그인 되어 있는 사서함 소유자와의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="76703-175">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="76703-176">소유자가 로그인 되어 있지 않으면 이러한 액세스 방법을 사용 하지 않도록 설정한 후에 사서함에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-176">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="76703-177">다음 명령을 실행 하 여 삭제 된 항목 보존 기간을 최대 30 일로 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="76703-177">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="76703-178">이 경우 현재 설정이 30 일 미만인 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-178">This assumes that the current setting is less than 30 days.</span></span> 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="76703-179">다음 명령을 실행 하 여 단일 항목 복구를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-179">Run the following command to disable single item recovery.</span></span>
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="76703-180">단일 항목 복구를 사용 하지 않도록 설정 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-180">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="76703-181">이 기간이 경과할 때까지 복구 가능한 항목 폴더의 항목을 삭제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-181">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="76703-182">다음 명령을 실행 하 여 관리 되는 폴더 도우미가 사서함을 처리 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-182">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="76703-183">앞에서 설명한 것 처럼 보존 잠금이 있는 보존 정책이 사서함에 적용 되지 않는 경우에만 관리 되는 폴더 도우미를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-183">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="76703-184">3 단계: 사서함에서 모든 보류 제거</span><span class="sxs-lookup"><span data-stu-id="76703-184">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="76703-185">복구 가능한 항목 폴더에서 항목을 삭제 하는 마지막 단계는 사서함에 대해 1 단계에서 확인 한 모든 보류를 제거 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-185">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="76703-186">복구 가능한 항목 폴더에서 항목을 삭제 한 후에 항목이 보존 되지 않도록 하려면 모든 보존을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-186">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="76703-187">다음 섹션에는 사서함에서 서로 다른 유형의 보류를 제거 하는 방법에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-187">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="76703-188">사서함에 저장 될 수 있는 유형 보존을 식별 하는 방법에 대 한 팁을 보려면 [추가 정보](#more-information) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-188">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="76703-189">자세한 내용은 [Exchange Online 사서함에 대해 설정 된 보류 유형을 식별](identify-a-hold-on-an-exchange-online-mailbox.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-189">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="76703-190">앞에서 설명한 것 처럼 사서함에서 보류를 제거 하기 전에 레코드 관리 또는 법률 부서에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-190">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="76703-191">소송 대기</span><span class="sxs-lookup"><span data-stu-id="76703-191">Litigation Hold</span></span>
  
<span data-ttu-id="76703-192">Exchange Online PowerShell에서 다음 명령을 실행 하 여 사서함에서 소송 보존을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-192">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="76703-193">클라이언트 액세스 방법 및 단일 항목 복구를 사용 하지 않도록 설정 하는 것과 마찬가지로 소송 보존을 제거 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-193">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="76703-194">이 기간이 경과할 때까지 복구 가능한 항목 폴더에서 항목을 삭제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-194">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="76703-195">원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="76703-195">In-Place Hold</span></span>
  
<span data-ttu-id="76703-196">Exchange Online PowerShell에서 다음 명령을 실행 하 여 사서함에 배치 된 원본 위치 유지를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-196">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="76703-197">1 단계에서 확인 한 원본 위치 유지에 대해 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-197">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="76703-198">원본 위치 유지를 확인 한 후 EAC (Exchange 관리 센터) 또는 Exchange Online PowerShell을 사용 하 여 보류에서 사서함을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-198">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="76703-199">자세한 내용은 [만들기 또는 In-place Hold 제거](https://go.microsoft.com/fwlink/?linkid=852668) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-199">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="76703-200">특정 사서함에 적용 되는 보존 정책</span><span class="sxs-lookup"><span data-stu-id="76703-200">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="76703-201">[보안 & 준수 센터 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) 에서 다음 명령을 실행 하 여 사서함에 적용 되는 보존 정책을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-201">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="76703-202">`mbx` `skp` 1 단계에서 확인 한 보존 정책에 대해 또는 접두사를 제외 하 고 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-202">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="76703-203">보존 정책을 식별 한 후에는 보안 & 준수 센터의 **정보 거 버 넌 스** 로 이동한 후 \> **Retention** , 이전 단계에서 식별 한 보존 정책을 편집 하 고, 보존 정책에 포함 된 받는 사람 목록에서 해당 사서함을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-203">After you identify the retention policy, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-retention-policies"></a><span data-ttu-id="76703-204">조직 전체 보존 정책</span><span class="sxs-lookup"><span data-stu-id="76703-204">Organization-wide retention policies</span></span>
  
<span data-ttu-id="76703-205">조직 전체 및 Exchange 전체 보존 정책은 조직의 모든 사서함에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-205">Organization-wide and Exchange-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="76703-206">이러한 사용자는 조직 수준 (사서함 수준이 아님)에서 적용 되며 1 단계에서 **set-organizationconfig** cmdlet을 실행 하면 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-206">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="76703-207">[보안 & 준수 센터 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) 에서 다음 명령을 실행 하 여 조직 차원의 보존 정책을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-207">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="76703-208">`mbx`1 단계에서 확인 한 조직 차원의 보존 정책에 대해 접두사를 제외한 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-208">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="76703-209">조직 전체 보존 정책을 파악 한 후에는 보안 & 준수 센터의 **정보 거 버 넌 스** 로 이동한 후 \> **Retention** , 이전 단계에서 식별 한 각 조직 차원의 보존 정책을 편집 하 고, 제외 된 받는 사람 목록에 사서함을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-209">After you identify the organization-wide retention policies, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="76703-210">이렇게 하면 보존 정책에서 사용자의 사서함이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-210">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="retention-labels"></a><span data-ttu-id="76703-211">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="76703-211">Retention labels</span></span>

<span data-ttu-id="76703-212">사용자가 콘텐츠를 보존 하도록 구성 된 레이블을 적용할 때마다 해당 사서함의 폴더 또는 항목에 대 한 콘텐츠를 보존 하 고 삭제 하려면 *ComplianceTagHoldApplied* mailbox 속성을 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-212">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="76703-213">이 문제가 발생 하면 사서함은 소송 보존에 적용 된 것으로 간주 되는 그대로 유지 되는 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-213">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="76703-214">*ComplianceTagHoldApplied* 속성의 값을 확인 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-214">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="76703-215">폴더 또는 항목에 보존 레이블이 적용 되므로 사서함이 보류 중인 것을 확인 한 후에는 보안 및 준수 센터의 콘텐츠 검색 도구를 사용 하 여 New-compliancetag 검색 조건을 사용 하 여 레이블이 지정 된 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-215">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="76703-216">자세한 내용은 [키워드 쿼리 및 검색 조건에서 콘텐츠 검색에 대 한](keyword-queries-and-search-conditions.md#conditions-for-common-properties)"검색 조건" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-216">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="76703-217">레이블에 대 한 자세한 내용은 [보존 정책 및 보존 레이블에 대 한](retention.md)자세한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-217">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

 ### <a name="ediscovery-holds"></a><span data-ttu-id="76703-218">eDiscovery 보류</span><span class="sxs-lookup"><span data-stu-id="76703-218">eDiscovery holds</span></span>
  
<span data-ttu-id="76703-219">[Security & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) 에서 다음 명령을 실행 하 여 사서함에 적용 된 ediscovery 사례 ( *ediscovery 보류*)와 관련 된 보류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-219">Run the following commands in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="76703-220">`UniH`1 단계에서 확인 한 eDiscovery 보존에 대 한 GUID (접두사를 포함 하지 않음)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-220">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="76703-221">두 번째 명령은 보류가 연결 된 eDiscovery 사례의 이름을 표시 합니다. 세 번째 명령은 보류의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-221">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="76703-222">Ediscovery 사례 및 보류의 이름을 식별 한 후에는 **eDiscovery** \> 준수 센터의 ediscovery **ediscovery** 페이지로 이동 하 고 케이스를 연 다음 보류에서 사서함을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-222">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="76703-223">EDiscovery 보류를 식별 하는 방법에 대 한 자세한 내용은 [Exchange Online 사서함에 대해 설정 된 보류 유형을 식별](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)하는 방법의 "eDiscovery 보류" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-223">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="76703-224">4 단계: 사서함에서 지연 된 보류 제거</span><span class="sxs-lookup"><span data-stu-id="76703-224">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="76703-225">사서함에서 모든 보류 유형을 제거한 후에는 *DelayHoldApplied* 또는 *DelayReleaseHoldApplied* mailbox 속성의 값이 **True**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-225">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="76703-226">다음 번에 관리 되는 폴더 도우미가 사서함을 처리 하 고 보류가 제거 되었음을 감지할 때 이러한 상황이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-226">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="76703-227">이를 *지연 보존* 이라고 하며, 데이터가 사서함에서 영구적으로 삭제 되는 것을 방지 하기 위해 보류의 실제 제거가 30 일 동안 지연 되는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-227">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="76703-228">지연 보존의 목적은 관리자가 보류를 제거한 후 삭제 될 사서함 항목을 검색 하거나 복구할 수 있도록 하는 것입니다.  사서함에 연기 대기를 설정 하면 사서함이 소송 보존 상태에 있는 것 처럼 여전히 무제한 기간 동안 유지 되는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-228">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="76703-229">30 일 후에 지연 보류가 만료 되 고 Microsoft 365에서 자동으로 지연 보존 ( *DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성을 **False**로 설정)을 제거 하 여 보류가 제거 되도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-229">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="76703-230">지연 보존에 대 한 자세한 내용은 [Exchange Online 사서함에 대해 설정 된 보류 유형을 식별 하는 방법](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)의 "지연 보류 시 사서함 관리" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76703-230">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="76703-231">5 단계에서 항목을 삭제 하려면 먼저 사서함에서 지연 된 보류를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-231">Before you can delete items in Step 5, you have to remove a delay hold from the mailbox.</span></span> <span data-ttu-id="76703-232">먼저 Exchange Online PowerShell에서 다음 명령을 실행 하 여 지연 보류가 사서함에 적용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-232">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

<span data-ttu-id="76703-233">*DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성 값을 **False**로 설정 하면 대기 시간이 사서함에 저장 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-233">If the value of either the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="76703-234">5 단계까지 이동 하 여 복구 가능한 항목 폴더의 항목을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-234">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="76703-235">*DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성 값이 **True**로 설정 된 경우 다음 명령 중 하나를 실행 하 여 지연 보존을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-235">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="76703-236">또는</span><span class="sxs-lookup"><span data-stu-id="76703-236">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="76703-237">*RemoveDelayHoldApplied* 또는 *RemoveDelayReleaseHoldApplied* 매개 변수를 사용 하려면 Exchange Online에서 법적 보존 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-237">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="76703-238">5 단계: 복구 가능한 항목 폴더에서 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="76703-238">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="76703-239">이제 보안 & 준수 센터의 [ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) 및 [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlet을 사용 하 여 복구 가능한 항목 폴더의 항목을 실제로 삭제할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-239">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlets in the Security & Compliance Center.</span></span> 

<span data-ttu-id="76703-240">이 작업을 수행 하려면 [전자 메일 메시지 검색 및 삭제](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-240">To do this, see [Search for and delete email messages](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="76703-241">항목이 삭제 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="76703-241">Verify that items were deleted</span></span>

<span data-ttu-id="76703-242">사서함의 복구할 수 있는 항목 폴더에서 항목이 삭제 되었는지 확인 하려면 Exchange Online PowerShell에서 **get-mailboxfolderstatistics** cmdlet을 사용 하 여 복구 가능한 항목 폴더의 항목 크기 및 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-242">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="76703-243">이러한 통계를 1 단계에서 수집한 것과 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-243">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="76703-244">에서 다음 명령을 실행 하 여 사용자의 기본 사서함에 있는 복구할 수 있는 항목 폴더에서 폴더 및 하위 폴더의 현재 크기와 총 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-244">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="76703-245">다음 명령을 실행 하 여 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더의 폴더 및 하위 폴더에 있는 항목의 크기 및 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76703-245">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="76703-246">6 단계: 사서함을 이전 상태로 되돌리기</span><span class="sxs-lookup"><span data-stu-id="76703-246">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="76703-247">마지막 단계는 사서함을 다시 이전 구성으로 되돌리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-247">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="76703-248">즉, 2 단계에서 변경한 속성을 다시 설정 하 고 3 단계에서 제거한 보존을 재적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-248">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="76703-249">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-249">This includes:</span></span>
  
- <span data-ttu-id="76703-250">삭제 된 항목 보존 기간을 이전 값으로 변경</span><span class="sxs-lookup"><span data-stu-id="76703-250">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="76703-251">또는 Exchange Online에서이 설정을 최대 30 일로 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-251">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="76703-252">단일 항목 복구를 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-252">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="76703-253">소유자가 자신의 사서함에 액세스할 수 있도록 클라이언트 액세스 방법을 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-253">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="76703-254">제거한 보류 및 보존 정책을 다시 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-254">Reapplying the holds and retention policies that you removed.</span></span>
    
- <span data-ttu-id="76703-255">관리 되는 폴더 도우미가 사서함을 처리할 수 있도록 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-255">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="76703-256">관리 되는 폴더 도우미가 사서함을 처리 하도록 다시 설정 하기 전에 보류 또는 보존 정책을 다시 적용 하 고 현재 위치에 있는지 확인 한 후 24 시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-256">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="76703-257">Exchange Online PowerShell에서 지정 된 순서 대로 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-257">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="76703-258">다음 명령을 실행 하 여 삭제 된 항목 보존 기간을 원래 값으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-258">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="76703-259">이는 이전 설정이 30 일 보다 작은 것으로 가정 합니다. 예: 14 일</span><span class="sxs-lookup"><span data-stu-id="76703-259">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span> 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="76703-260">다음 명령을 실행 하 여 단일 항목 복구를 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-260">Run the following command to re-enable single item recovery.</span></span>
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="76703-261">다음 명령을 실행 하 여 사서함에 대 한 모든 클라이언트 액세스 방법을 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-261">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="76703-262">3 단계에서 제거한 보존을 다시 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-262">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="76703-263">보존 유형에 따라 다음 절차 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-263">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="76703-264">**소송 대기**</span><span class="sxs-lookup"><span data-stu-id="76703-264">**Litigation Hold**</span></span>
    
    <span data-ttu-id="76703-265">다음 명령을 실행 하 여 사서함에 대 한 소송 보존을 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-265">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="76703-266">**원본 위치 유지**</span><span class="sxs-lookup"><span data-stu-id="76703-266">**In-Place Hold**</span></span>
    
    <span data-ttu-id="76703-267">EAC (또는 Exchange Online PowerShell)를 사용 하 여 사서함을 원본 위치 유지 상태로 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-267">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="76703-268">**특정 사서함에 적용 되는 보존 정책**</span><span class="sxs-lookup"><span data-stu-id="76703-268">**Retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="76703-269">보안 & 준수 센터를 사용 하 여 사서함을 보존 정책에 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-269">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="76703-270">보안 & 준수 센터의 **정보 거 버 넌 스** \> **Retention** 페이지로 이동 하 여 보존 정책을 편집한 다음 보존 정책이 적용 되는 받는 사람 목록에 사서함을 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-270">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="76703-271">**조직 전체 보존 정책**</span><span class="sxs-lookup"><span data-stu-id="76703-271">**Organization-wide Retention policies**</span></span>
    
    <span data-ttu-id="76703-272">정책에서 조직 전체 또는 Exchange 전체 보존 정책을 제거한 경우에는 보안 & 준수 센터를 사용 하 여 제외 된 사용자 목록에서 사서함을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-272">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="76703-273">보안 & 준수 센터의 **정보 거 버 넌 스** \> **Retention** 페이지로 이동 하 여 조직 차원의 보존 정책을 편집 하 고 제외 된 받는 사람 목록에서 사서함을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-273">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="76703-274">이렇게 하면 보존 정책이 사용자 사서함에 다시 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-274">Doing this will reapply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="76703-275">**eDiscovery 사례 보류**</span><span class="sxs-lookup"><span data-stu-id="76703-275">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="76703-276">보안 & 준수 센터를 사용 하 여 사서함을 eDiscovery 사례와 연결 된 보류에 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-276">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="76703-277">**Ediscovery** \> **ediscovery** 페이지로 이동 하 여 사례를 열고 사서함을 다시 보류에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-277">Go to the **eDiscovery** \> **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="76703-278">다음 명령을 실행 하 여 관리 되는 폴더 도우미가 사서함을 다시 처리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-278">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="76703-279">앞에서 설명한 것 처럼 관리 되는 폴더 도우미를 다시 사용 하도록 설정 하기 전에 보류 또는 보존 정책을 재적용 한 후 24 시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-279">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="76703-280">사서함이 이전 구성으로 되돌아간 것을 확인 하려면 다음 명령을 실행 하 여 1 단계에서 수집한 설정과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-280">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="76703-281">추가 정보</span><span class="sxs-lookup"><span data-stu-id="76703-281">More information</span></span>

<span data-ttu-id="76703-282">다음은 *InPlaceHolds* 속성의 값에 따라 **get-Mailbox** 또는 **set-organizationconfig** cmdlet을 실행할 때 서로 다른 유형의 보류를 식별 하는 방법을 설명 하는 표입니다.</span><span class="sxs-lookup"><span data-stu-id="76703-282">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="76703-283">자세한 내용은 [Exchange Online 사서함에 대해 설정 된 보류 유형을 식별](identify-a-hold-on-an-exchange-online-mailbox.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76703-283">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="76703-284">앞에서 설명한 것 처럼 복구 가능한 항목 폴더의 항목을 성공적으로 삭제 하려면 먼저 사서함에서 모든 보류 및 보존 정책을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-284">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="76703-285">**보류 유형**</span><span class="sxs-lookup"><span data-stu-id="76703-285">**Hold type**</span></span>|<span data-ttu-id="76703-286">**예제 값**</span><span class="sxs-lookup"><span data-stu-id="76703-286">**Example value**</span></span>|<span data-ttu-id="76703-287">**보류를 확인 하는 방법**</span><span class="sxs-lookup"><span data-stu-id="76703-287">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76703-288">소송 대기</span><span class="sxs-lookup"><span data-stu-id="76703-288">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="76703-289">*LitigationHoldEnabled* 속성은로 설정 됩니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="76703-289">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="76703-290">원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="76703-290">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="76703-291">*InPlaceHolds* 속성은 사서함에 배치 된 원본 위치 유지의 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-291">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="76703-292">GUID가 접두사로 시작 되지 않으므로 현재 위치 유지로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-292">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="76703-293">`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`Exchange Online PowerShell의 명령을 사용 하 여 사서함의 원본 위치 유지에 대 한 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-293">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="76703-294">특정 사서함에 적용 되는 보안 & 준수 센터의 보존 정책</span><span class="sxs-lookup"><span data-stu-id="76703-294">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="76703-295">또는</span><span class="sxs-lookup"><span data-stu-id="76703-295">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="76703-296">**사서함** cmdlet을 실행 하는 경우 *InPlaceHolds* 속성에는 사서함에 적용 된 보존 정책의 guid도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-296">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="76703-297">GUID는 접두사로 시작 되므로 보존 정책을 식별할 수 있습니다 `mbx` .</span><span class="sxs-lookup"><span data-stu-id="76703-297">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="76703-298">보존 정책의 GUID가 접두사로 시작 되 면 `skp` 보존 정책이 비즈니스용 Skype 대화에 적용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76703-298">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="76703-299">사서함에 적용 된 보존 정책을 식별 하려면 Security & 준수 센터 PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-299">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="76703-300">`mbx` `skp` 이 명령을 실행할 때 or 접두사를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-300">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="76703-301">보안 & 준수 센터의 조직 전체 보존 정책</span><span class="sxs-lookup"><span data-stu-id="76703-301">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="76703-302">No 값</span><span class="sxs-lookup"><span data-stu-id="76703-302">No value</span></span>  <br/> <span data-ttu-id="76703-303">또는</span><span class="sxs-lookup"><span data-stu-id="76703-303">or</span></span>  <br/>  <span data-ttu-id="76703-304">`-mbxe9b52bf7ab3b46a286308ecb29624696`(사서함이 조직 차원 정책에서 제외 됨을 나타냄)</span><span class="sxs-lookup"><span data-stu-id="76703-304">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="76703-305">*InPlaceHolds* 속성이 비어 있는 **경우에도 사서함 cmdlet을** 실행할 때 하나 이상의 조직 범위 보존 정책이 사서함에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-305">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="76703-306">이를 확인 하려면 `Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell에서 명령을 실행 하 여 조직 전체 보존 정책의 guid 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-306">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="76703-307">Exchange 사서함에 적용 되는 조직 차원의 보존 정책의 GUID는 접두사로 시작 합니다 `mbx` (예:) `mbxa3056bb15562480fadb46ce523ff7b02` .</span><span class="sxs-lookup"><span data-stu-id="76703-307">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="76703-308">사서함에 적용 되는 조직 차원의 보존 정책을 식별 하려면 Security & 준수 센터 PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-308">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="76703-309">사서함이 조직 전체 보존 정책에서 제외 되는 경우 **사서함** cmdlet을 실행할 때 보존 정책의 GUID가 사용자 사서함의 *InPlaceHolds* 속성에 표시 됩니다. 예를 들어이 접두사는 접두사로 식별 `-mbx` 됩니다.`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="76703-309">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="76703-310">보안 & 준수 센터의 eDiscovery 사례 보류</span><span class="sxs-lookup"><span data-stu-id="76703-310">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="76703-311">*InPlaceHolds* 속성에는 또한 사서함에 저장 될 수 있는 보안 & 준수 센터에서 eDiscovery 사례와 관련 된 모든 보류의 GUID가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76703-311">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="76703-312">GUID는 접두사로 시작 되므로 eDiscovery 사례 보류 임을 확인할 수 있습니다 `UniH` .</span><span class="sxs-lookup"><span data-stu-id="76703-312">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="76703-313">`Get-CaseHoldPolicy`보안 & 준수 센터 PowerShell에서 cmdlet을 사용 하 여 사서함의 보류가 연결 된 eDiscovery 사례에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-313">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="76703-314">예를 들어 명령을 실행 `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 하 여 사서함에 대 한 케이스 보류의 이름을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76703-314">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="76703-315">`UniH`이 명령을 실행할 때 접두사를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-315">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="76703-316">사서함의 보류가 연결 된 eDiscovery 사례를 식별 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76703-316">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`



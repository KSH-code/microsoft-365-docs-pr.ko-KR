---
title: 클라우드 사서함 보류의 복구 가능한 항목 폴더에서 항목 삭제
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
description: 관리자가 Exchange Online 사서함에 대한 사용자의 복구 가능한 항목 폴더에서 해당 사서함이 법적 보유 상태인 경우에도 항목을 삭제할 수 있는 방법을 확인합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326645"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a><span data-ttu-id="d2035-103">보류 중인 클라우드 기반 사서함의 복구 가능한 항목 폴더에서 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="d2035-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>

<span data-ttu-id="d2035-104">Exchange Online 사서함의 복구 가능한 항목 폴더는 실수로 또는 악의적인 삭제로부터 보호하기 위해 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="d2035-105">또한 보존 및 eDiscovery 검색과 같은 준수 기능에서 보존 및 액세스하는 항목을 저장하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="d2035-106">그러나 경우에 따라 조직에서 삭제해야 하는 복구 가능한 항목 폴더에 의도치 않은 보존된 데이터가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="d2035-107">예를 들어 사용자는 업무상 심각한 결과를 초래할 수 있는 중요한 정보나 정보가 포함된 전자 메일 메시지를 무의미하게 보내거나 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="d2035-108">메시지가 영구적으로 삭제된 경우에도 사서함에 법적 보존이 설정되면 영구적으로 보존될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="d2035-109">이 시나리오는  데이터가 Office 365로 의도치게  유출된 것이기 때문에 데이터 유출로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-109">This scenario is known as *data spillage* because data has been unintentionally *spilled* into Office 365.</span></span> <span data-ttu-id="d2035-110">이러한 상황에서는 해당 사서함이 Office 365의 다른 보류 기능 중 하나를 사용하여 보류된 경우에도 Exchange Online 사서함에 대한 사용자의 복구 가능한 항목 폴더에 있는 항목을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="d2035-111">이러한 유형의 보류에는 Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 만든 소송 보존, In-Place 보류, eDiscovery 보류 및 보존 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>

<span data-ttu-id="d2035-112">이 문서에서는 관리자가 보류된 클라우드 기반 사서함의 복구 가능한 항목 폴더에서 항목을 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-112">This article explains how admins can delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="d2035-113">이 절차에는 사서함에 대한 액세스를 사용 중지하고, 단일 항목 복구를 사용할 수 있도록 설정하고, 관리되는 폴더 도우미가 사서함을 처리하지 못하게 설정하고, 보류를 일시적으로 제거하고, 복구 가능한 항목 폴더에서 항목을 삭제한 다음 사서함을 이전 구성으로 되돌리면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="d2035-114">프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-114">Here's the process:</span></span>
  
[<span data-ttu-id="d2035-115">1단계: 사서함에 대한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="d2035-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="d2035-116">2단계: 사서함 준비</span><span class="sxs-lookup"><span data-stu-id="d2035-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="d2035-117">3단계: 사서함에서 모든 보류 제거</span><span class="sxs-lookup"><span data-stu-id="d2035-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="d2035-118">4단계: 사서함에서 지연 보류 제거</span><span class="sxs-lookup"><span data-stu-id="d2035-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="d2035-119">5단계: 복구 가능한 항목 폴더의 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="d2035-119">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="d2035-120">6단계: 사서함을 이전 상태로 되전</span><span class="sxs-lookup"><span data-stu-id="d2035-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="d2035-121">이 문서에 설명된 절차에 따라 데이터가 Exchange Online 사서함에서 영구적으로 삭제(제거)됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="d2035-122">즉, 복구 가능한 항목 폴더에서 삭제한 메시지는 복구할 수 없습니다. 법적 검색 또는 기타 규정 준수 목적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="d2035-123">보안 및 준수 센터에서 만든 소송 보존, In-Place 보류, eDiscovery 보류 또는 보존 정책의 일부로 보류된 사서함에서 메시지를 삭제하려면 보류를 제거하기 전에 레코드 관리 또는 법률 부서에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2035-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="d2035-124">조직에 보류된 사서함 또는 데이터 유출 인시던트가 우선적으로 적용될지 여부를 정의하는 정책이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span>
  
## <a name="before-you-delete-items"></a><span data-ttu-id="d2035-125">항목을 삭제하기 전에</span><span class="sxs-lookup"><span data-stu-id="d2035-125">Before you delete items</span></span>

- <span data-ttu-id="d2035-126">콘텐츠 검색을 만들고 실행하려면 eDiscovery 관리자 역할 그룹의 구성원이거나 준수 검색 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="d2035-127">메시지를 삭제하려면 조직 관리 역할 그룹의 구성원이거나 검색 및 제거 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="d2035-128">역할 그룹에 사용자를 추가하는 방법에 대한 자세한 내용은 [보안 및 준수 센터의 eDiscovery 권한 부여](./assign-ediscovery-permissions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2035-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](./assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="d2035-129">이 문서에 설명된 절차는 비활성 사서함에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="d2035-130">제거한 후 비활성 사서함에 보류(또는 보존 정책)를 다시 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="d2035-131">비활성 사서함에서 보류를 제거하면 해당 사서함이 소프트 삭제된 일반 사서함으로 변경되고 관리되는 폴더 도우미가 처리한 후 조직에서 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="d2035-132">보존 잠금을 사용하여 잠긴 정책을 사용하여 보존 설정이 할당된 사서함에는 이 절차를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-132">You can't perform this procedure for a mailbox that has been assigned retention settings with a policy that's locked by using Preservation Lock.</span></span> <span data-ttu-id="d2035-133">이 잠금으로 인해 정책에서 사서함을 제거하거나 제외할 수 있으며 사서함의 관리되는 폴더 도우미를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-133">That's because this lock prevents you from removing or excluding the mailbox from the policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="d2035-134">보존 정책 잠금에 대한 자세한 내용은 [Use Preservation Lock to restrict changes to retention policies and retention label policies 을 참조하십시오.](retention-preservation-lock.md)</span><span class="sxs-lookup"><span data-stu-id="d2035-134">For more information about locking policies for retention,see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

- <span data-ttu-id="d2035-135">사서함이 보류되지 않은 경우(또는 단일 항목 복구를 사용하도록 설정하지 않은 경우) 복구할 수 있는 항목 폴더에서 항목을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-136">이 작업을 하는 방법에 대한 자세한 내용은 조직에서 전자 메일 메시지 검색 및 [삭제를 참조하세요.](./search-for-and-delete-messages-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="d2035-136">For more information about how to do this, see [Search for and delete email messages in your organization](./search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="d2035-137">1단계: 사서함에 대한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="d2035-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="d2035-138">이 첫 번째 단계는 이 절차에 영향을 줄 대상 사서함에서 선택한 속성을 수집하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="d2035-139">이러한 설정 중 일부를 변경한 다음 복구 가능한 항목 폴더에서 항목을 삭제한 후 6단계에서 원래 값으로 되돌리게 예정이기 때문에 이러한 설정을 적어 두거나 텍스트 파일에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-140">다음은 수집해야 하는 사서함 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="d2035-141">*SingleItemRecoveryEnabled*  및  *RetainDeletedItemsFor*.</span><span class="sxs-lookup"><span data-stu-id="d2035-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="d2035-142">필요한 경우 단일 복구를 사용하지 않도록 설정하고 3단계에서 삭제된 항목 보존 기간을 늘리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span>

- <span data-ttu-id="d2035-143">*LitigationHoldEnabled*  및  *InPlaceHolds*.</span><span class="sxs-lookup"><span data-stu-id="d2035-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="d2035-144">3단계에서 일시적으로 제거할 수 있도록 사서함에 배치된 모든 보류를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="d2035-145">사서함에 [배치될](#more-information) 수 있는 형식 보류를 식별하는 방법에 대한 팁은 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2035-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span>

<span data-ttu-id="d2035-146">또한 이 절차 중에 소유자(또는 다른 사용자)가 사서함에 액세스할 수 있도록 사서함 클라이언트 액세스 설정을 일시적으로 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="d2035-147">마지막으로 복구 가능한 항목 폴더의 현재 크기와 항목 수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-148">5단계에서 복구할 수 있는 항목 폴더의 항목을 삭제한 후 이 정보를 사용하여 항목이 제거된 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="d2035-149">[Exchange Online PowerShell에 연결합니다](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d2035-149">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d2035-150">Exchange Online에서 적절한 관리 역할이 할당된 관리자 계정의 사용자 이름과 암호를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d2035-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span>

2. <span data-ttu-id="d2035-151">다음 명령을 실행하여 단일 항목 복구 및 삭제된 항목 보존 기간에 대한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="d2035-152">단일 항목 복구를 사용하도록 설정한 경우 2단계에서 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="d2035-153">삭제된 항목 보존 기간이 30일(Exchange Online의 최대값)으로 설정되지 않은 경우 2단계에서 늘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span>

3. <span data-ttu-id="d2035-154">다음 명령을 실행하여 사서함에 대한 사서함 액세스 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-154">Run the following command to get the mailbox access settings for the mailbox.</span></span>

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="d2035-155">2단계에서 이러한 모든 액세스 방법을 사용하지 않도록 설정하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-155">You'll disable all of these access methods in Step 2.</span></span>

4. <span data-ttu-id="d2035-156">다음 명령을 실행하여 사서함에 적용된 보류 및 보존 정책에 대한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > <span data-ttu-id="d2035-157">*InPlaceHolds* 속성에 값이 너무 많고 모든 값이 표시되지 않는 경우 명령을 실행하여 각 값을 별도의 줄에 표시할 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span>
  
5. <span data-ttu-id="d2035-158">다음 명령을 실행하여 조직 전체 보존 정책에 대한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   <span data-ttu-id="d2035-159">조직에 조직 전체 보존 정책이 있는 경우 3단계에서 이러한 정책에서 사서함을 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span> <span data-ttu-id="d2035-160">변경을 복제하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-160">It may take up to 24 hours to replicate the change.</span></span>

    > [!TIP]
    > <span data-ttu-id="d2035-161">*InPlaceHolds* 속성에 값이 너무 많고 모든 값이 표시되지 않는 경우 명령을 실행하여 각 값을 별도의 줄에 표시할 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-161">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="d2035-162">다음 명령을 실행하여 사서함에 지연 보류가 적용되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-162">Run the following command to determine if a delay hold is applied to the mailbox.</span></span>

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   <span data-ttu-id="d2035-163">*DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성 값을 **True로** 설정하면 사서함에 지연 보류가 적용되어 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-163">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, a delay hold is applied to the mailbox and must be removed.</span></span> <span data-ttu-id="d2035-164">지연 보류에 대한 자세한 내용은 [4단계: 사서함에서 지연 보류 제거를 참조하세요.](#step-4-remove-the-delay-hold-from-the-mailbox)</span><span class="sxs-lookup"><span data-stu-id="d2035-164">For more information about delay holds, see [Step 4: Remove the delay hold from the mailbox](#step-4-remove-the-delay-hold-from-the-mailbox).</span></span>

   <span data-ttu-id="d2035-165">두 속성의 값을 **False로** 설정하면 사서함에 지연 보류가 적용되지 않고 4단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-165">If the value of either properties is set to **False**, a delay hold is not applied to the mailbox, and you can skip Step 4.</span></span>

7. <span data-ttu-id="d2035-166">다음 명령을 실행하여 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더에 있는 폴더 및 하위 폴더의 현재 크기와 총 항목 수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-166">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="d2035-167">사용자의 보관 사서함을 사용하도록 설정한 경우 다음 명령을 실행하여 보관 사서함의 복구 가능한 항목 폴더에 있는 폴더 및 하위 폴더의 총 항목 수와 크기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-167">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="d2035-168">5단계에서 항목을 삭제할 때 사용자의 기본 보관 사서함에 있는 복구 가능한 항목 폴더의 항목을 삭제하거나 삭제하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-168">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="d2035-169">사서함에 대해 자동 확장 보관을 사용하도록 설정하면 보조 보관 사서함의 항목이 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-169">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="d2035-170">2단계: 사서함 준비</span><span class="sxs-lookup"><span data-stu-id="d2035-170">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="d2035-171">사서함에 대한 정보를 수집하고 저장한 후 다음 단계는 다음 작업을 수행하여 사서함을 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-171">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span>
  
- <span data-ttu-id="d2035-172">**이 절차 중에** 사서함 소유자가 사서함에 액세스할 수 없는 경우 사서함 데이터를 변경할 수 있도록 사서함에 대한 클라이언트 액세스를 사용하지 않도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2035-172">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span>

- <span data-ttu-id="d2035-173">**삭제된** 항목 보존 기간을 30일(Exchange Online의 최대값)으로 늘리면 5단계에서 항목을 삭제하기 전에 복구 가능한 항목 폴더에서 항목이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-173">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span>

- <span data-ttu-id="d2035-174">**단일 항목** 복구를 사용하지 않도록 설정하여 5단계의 복구 가능한 항목 폴더에서 항목을 삭제한 후 삭제된 항목 보존 기간 동안 항목이 보존되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-174">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span>

- <span data-ttu-id="d2035-175">**관리되는 폴더 도우미가** 사서함을 처리하지 않도록 설정하고 5단계에서 삭제한 항목을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-175">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span>

<span data-ttu-id="d2035-176">Exchange Online PowerShell에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-176">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="d2035-177">다음 명령을 실행하여 사서함에 대한 모든 클라이언트 액세스를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-177">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="d2035-178">명령 구문에서는 모든 클라이언트 액세스 방법이 사서함에서 사용하도록 설정되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-178">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > <span data-ttu-id="d2035-179">사서함에 대한 모든 클라이언트 액세스 방법을 사용하지 않도록 설정하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-179">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="d2035-180">이러한 액세스 방법을 해제하면 사서함 소유자가 현재 로그인한 경우 연결이 끊어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-180">Note that disabling these access methods won't disconnect the mailbox owner if they are currently signed in.</span></span> <span data-ttu-id="d2035-181">소유자가 로그인하지 않은 경우 이러한 액세스 방법을 사용하지 않도록 설정한 후에도 사서함에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-181">If the owner isn't signed in, they won't be able to access their mailbox after these access methods are disabled.</span></span>
  
2. <span data-ttu-id="d2035-182">삭제된 항목 보존 기간을 최대 30일로 늘리기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-182">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="d2035-183">이 경우 현재 설정이 30일 미만인 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-183">This assumes that the current setting is less than 30 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="d2035-184">다음 명령을 실행하여 단일 항목 복구를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-184">Run the following command to disable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > <span data-ttu-id="d2035-185">단일 항목 복구를 사용하지 않도록 설정하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-185">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="d2035-186">이 기간이 경과할 때까지 복구 가능한 항목 폴더의 항목을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-186">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="d2035-187">다음 명령을 실행하여 관리되는 폴더 도우미가 사서함을 처리하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-187">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="d2035-188">앞서 설명한 것 처럼 보존 잠금이 있는 보존 정책이 사서함에 적용되지 않은 경우만 관리되는 폴더 도우미를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-188">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="d2035-189">3단계: 사서함에서 모든 보류 제거</span><span class="sxs-lookup"><span data-stu-id="d2035-189">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="d2035-190">복구 가능한 항목 폴더에서 항목을 삭제할 수 있는 마지막 단계는 사서함에 있는 모든 보류(1단계에서 식별)를 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-190">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="d2035-191">복구 가능한 항목 폴더에서 항목을 삭제한 후에도 항목이 보존되지 못하게 모든 보류를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-191">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-192">다음 섹션에는 사서함에서 여러 유형의 보류를 제거하는 데 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-192">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="d2035-193">사서함에 [배치될](#more-information) 수 있는 형식 보류를 식별하는 방법에 대한 팁은 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2035-193">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="d2035-194">자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 식별하는 [방법을 참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="d2035-194">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d2035-195">앞서 설명한 것 처럼 사서함에서 보류를 제거 하기 전에 레코드 관리 또는 법률 부서에 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-195">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
### <a name="litigation-hold"></a><span data-ttu-id="d2035-196">소송 대기</span><span class="sxs-lookup"><span data-stu-id="d2035-196">Litigation Hold</span></span>
  
<span data-ttu-id="d2035-197">Exchange Online PowerShell에서 다음 명령을 실행하여 사서함에서 소송 보류를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-197">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> <span data-ttu-id="d2035-198">클라이언트 액세스 방법 및 단일 항목 복구를 사용할 수 있도록 설정하는 경우와 마찬가지로 소송 보류를 제거하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-198">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="d2035-199">이 기간이 경과할 때까지 복구 가능한 항목 폴더에서 항목을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-199">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
### <a name="in-place-hold"></a><span data-ttu-id="d2035-200">원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="d2035-200">In-Place Hold</span></span>
  
<span data-ttu-id="d2035-201">Exchange Online PowerShell에서 다음 명령을 실행하여 사서함에 In-Place 보류를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-201">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="d2035-202">1단계에서 In-Place 보류에 대한 GUID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-202">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="d2035-203">보류를 In-Place EAC(Exchange 관리 센터) 또는 Exchange Online PowerShell을 사용하여 보류에서 사서함을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-203">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="d2035-204">자세한 내용은 [만들기 또는 In-place Hold 제거](/exchange/security-and-compliance/create-or-remove-in-place-holds) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2035-204">For more information, see [Create or remove an In-Place Hold](/exchange/security-and-compliance/create-or-remove-in-place-holds).</span></span>
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="d2035-205">특정 사서함에 적용된 보존 정책</span><span class="sxs-lookup"><span data-stu-id="d2035-205">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="d2035-206">Security & Compliance [Center PowerShell에서](/powershell/exchange/exchange-online-powershell) 다음 명령을 실행하여 사서함에 적용되는 보존 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-206">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="d2035-207">이 명령은 사서함에 적용된 Teams 대화 보존 정책도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-207">This command will also return any Teams conversation retention policies applied to a mailbox.</span></span> <span data-ttu-id="d2035-208">1단계에서 식별한 보존 정책에 대한 GUID(또는 prefix 포함 안 `mbx` `skp` )를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-208">Use the GUID (not including the `mbx` or `skp` prefix) for the retention policy that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="d2035-209">보존 정책을 식별한 후 보안 & 준수 센터의 정보 거버넌스 보존 페이지로 이동하여 이전 단계에서 식별한 보존 정책을 편집하고 보존 정책에 포함된 받는 사람 목록에서 사서함을  >   제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-209">After you identify the retention policy, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span>
  
### <a name="organization-wide-retention-policies"></a><span data-ttu-id="d2035-210">조직 전체 보존 정책</span><span class="sxs-lookup"><span data-stu-id="d2035-210">Organization-wide retention policies</span></span>
  
<span data-ttu-id="d2035-211">조직 전체, Exchange 전체 및 Teams 전체 보존 정책은 조직의 모든 사서함에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-211">Organization-wide, Exchange-wide, and Teams-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="d2035-212">이러한 CMD는 사서함 수준이 아닌 조직 수준에서 적용되고 1단계에서 **Get-OrganizationConfig** cmdlet을 실행할 때 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-212">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="d2035-213">보안 및 준수 센터 [powerShell에서 &](/powershell/exchange/exchange-online-powershell) 명령을 실행하여 조직 전체 보존 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-213">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="d2035-214">1단계에서 식별한 조직 전체 보존 정책에 대해 GUID(prefix 포함 안  `mbx` )를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-214">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="d2035-215">조직 전체 보존 정책을 식별한 후 보안 & 준수 센터의 정보 거버넌스 보존 페이지로 이동하여 이전 단계에서 식별한 각 조직 전체 보존 정책을 편집하고 제외된 받는 사람 목록에 사서함을  >   추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-215">After you identify the organization-wide retention policies, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="d2035-216">이렇게 하면 보존 정책에서 사용자의 사서함이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-216">Doing this will remove the user's mailbox from the retention policy.</span></span> <span data-ttu-id="d2035-217">변경을 복제하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-217">It may take up to 24 hours to replicate the change.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="d2035-218">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="d2035-218">Retention labels</span></span>

<span data-ttu-id="d2035-219">사용자가 콘텐츠를 보존하거나 보존한 다음 사서함의 폴더나 항목에 콘텐츠를 삭제하도록 구성된 레이블을 적용하면 *ComplianceTagHoldApplied* 사서함 속성이 **True로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d2035-219">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="d2035-220">이 경우 사서함은 소송 보존에 배치되거나 보존 정책에 할당된 경우처럼 보류된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-220">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="d2035-221">*ComplianceTagHoldApplied* 속성 값을 보기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-221">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="d2035-222">보존 레이블이 폴더 또는 항목에 적용되어 사서함이 보류 중으로 확인되면 보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 ComplianceTag 검색 조건을 사용하여 레이블이 지정된 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-222">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="d2035-223">자세한 내용은 콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건의 "검색 조건" [섹션을 참조하세요.](keyword-queries-and-search-conditions.md#conditions-for-common-properties)</span><span class="sxs-lookup"><span data-stu-id="d2035-223">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="d2035-224">레이블에 대한 자세한 내용은 보존 정책 및 보존 레이블에 대해 [자세히를 참조하세요.](retention.md)</span><span class="sxs-lookup"><span data-stu-id="d2035-224">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="d2035-225">eDiscovery 보존</span><span class="sxs-lookup"><span data-stu-id="d2035-225">eDiscovery holds</span></span>
  
<span data-ttu-id="d2035-226">Security & Compliance [Center PowerShell에서](/powershell/exchange/connect-to-scc-powershell) 다음 명령을 실행하여 사서함에 적용된 *eDiscovery 사례(eDiscovery* 보류)와 연결된 보류를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-226">Run the following commands in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="d2035-227">1단계에서 식별한 eDiscovery 보류에 대한 GUID(prefix를 포함하지  `UniH` 않습니다.)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-227">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="d2035-228">두 번째 명령은 보류가 연결된 eDiscovery 사례의 이름을 표시합니다. 세 번째 명령은 보류의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-228">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span>
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="d2035-229">eDiscovery 사례 및 보류의 이름을 확인한 후 준수 센터의 **eDiscovery eDiscovery** 페이지로 이동하여 사례를 열고 보류에서 사서함을 \>  제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-229">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="d2035-230">eDiscovery 보류를 식별하는 방법에 대한 자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 식별하는 방법의 "eDiscovery 보류" 섹션을 [참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)</span><span class="sxs-lookup"><span data-stu-id="d2035-230">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="d2035-231">4단계: 사서함에서 지연 보류 제거</span><span class="sxs-lookup"><span data-stu-id="d2035-231">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="d2035-232">사서함에서 모든 유형의 보류를 제거하고 나면 *DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 사서함 속성의 값이 **True로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d2035-232">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="d2035-233">이 문제는 다음에 관리되는 폴더 도우미가 사서함을 처리하고 보류가 제거된 것으로 감지될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-233">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="d2035-234">이를 지연  보류라고 합니다. 즉, 데이터가 사서함에서 영구적으로 삭제되지 않도록 보류의 실제 제거가 30일 동안 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-234">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="d2035-235">지연 보류의 목적은 관리자가 보류를 제거한 후 제거될 사서함 항목을 검색하거나 복구할 수 있는 기회를 주는 것입니다.  사서함에 지연 보류가 배치된 경우 사서함은 사서함이 소송 보류에 있는 경우처럼 무제한 기간 동안 보류된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-235">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="d2035-236">30일이 지난 후 지연 보류가 만료되고 Microsoft 365는 지연 보류를 제거하기 위해 *DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성을 **False로** 설정하여 지연 보류를 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-236">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="d2035-237">지연 보류에 대한 자세한 내용은 [How to identify the type of hold on an Exchange Online mailbox의](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)"지연된 사서함 관리" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2035-237">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="d2035-238">*DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성 값이 **True로** 설정된 경우 다음 명령 중 하나를 실행하여 지연 보류를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-238">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="d2035-239">또는</span><span class="sxs-lookup"><span data-stu-id="d2035-239">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="d2035-240">*RemoveDelayHoldApplied* 또는 *RemoveDelayReleaseHoldApplied* 매개 변수를 사용하려면 Exchange Online에서 Legal Hold 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-240">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="d2035-241">5단계: 복구 가능한 항목 폴더의 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="d2035-241">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="d2035-242">이제 보안 및 준수 센터 PowerShell에서 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) 및 [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlet을 사용하여 복구 가능한 항목 폴더의 항목을 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-242">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlets in Security & Compliance Center PowerShell.</span></span>

<span data-ttu-id="d2035-243">복구 가능한 항목 폴더에 있는 항목을 검색하기 위해 대상 컬렉션을 수행하는 *것이 좋습니다.*</span><span class="sxs-lookup"><span data-stu-id="d2035-243">To search for items that are located in the Recoverable Items folder, we recommend that you perform a *targeted collection*.</span></span> <span data-ttu-id="d2035-244">즉, 검색 범위를 복구 가능한 항목 폴더에 있는 항목으로만 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-244">This means you narrow the scope of your search only to items located in the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-245">대상 컬렉션에 대한 콘텐츠 검색 사용 문서에서 스크립트를 실행하여 이 [작업을 할 수](use-content-search-for-targeted-collections.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-245">You can do this by running the script in the [Use Content Search for targeted collections](use-content-search-for-targeted-collections.md) article.</span></span> <span data-ttu-id="d2035-246">이 스크립트는 대상 복구 가능한 항목 폴더에 있는 모든 하위 폴더의 폴더 ID 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-246">This script returns the value of the folder ID property for all the subfolders in the target Recoverable Items folder.</span></span> <span data-ttu-id="d2035-247">그런 다음 검색 쿼리의 폴더 ID를 사용하여 해당 폴더에 있는 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-247">Then you use the folder ID in a search query to return items located in that folder.</span></span>

<span data-ttu-id="d2035-248">다음은 사용자의 복구 가능한 항목 폴더에서 항목을 검색하고 삭제하는 프로세스의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-248">Here's an overview of the process to search for and delete items in a user's Recoverable Items folder:</span></span>

1. <span data-ttu-id="d2035-249">대상 사용자의 사서함에 있는 모든 폴더의 폴더 ID를 반환하는 대상 컬렉션 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-249">Run the targeted collection script that returns the folder IDs for all folders in the target user's mailbox.</span></span> <span data-ttu-id="d2035-250">스크립트는 동일한 PowerShell 세션에서 Exchange Online PowerShell 및 & 준수 PowerShell에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-250">The script connects to Exchange Online PowerShell and Security & Compliance PowerShell in the same PowerShell session.</span></span> <span data-ttu-id="d2035-251">자세한 내용은 [스크립트 실행을 참조하여](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)사서함의 폴더 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-251">For more information, see [Run the script to get a list of folders for a mailbox](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).</span></span>

2. <span data-ttu-id="d2035-252">복구 가능한 항목 폴더에 있는 모든 하위 폴더의 폴더 ID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-252">Copy the folder IDs for all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-253">또는 스크립트의 출력을 텍스트 파일로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-253">Alternatively, you can redirect the output of the script to a text file.</span></span>

   <span data-ttu-id="d2035-254">다음은 항목을 검색하고 삭제할 수 있는 복구 가능한 항목 폴더의 하위 폴더 목록 및 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-254">Here's a list and description of the subfolders in the Recoverable Items folder that you can search and delete items from:</span></span>

   - <span data-ttu-id="d2035-255">**삭제:** 삭제된 항목 보존 기간이 만료되지 않은 소프트 삭제된 항목이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-255">**Deletions**: Contains soft-deleted items whose deleted item retention period has not expired.</span></span> <span data-ttu-id="d2035-256">사용자는 Outlook에서 지워진 항목 복구 도구를 사용하여 이 하위폴더에서 소프트 삭제된 항목을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-256">Users can recover soft-deleted items from this subfolder using the Recover Deleted Items tool in Outlook.</span></span>

   - <span data-ttu-id="d2035-257">**제거:** 삭제된 항목 보존 기간이 만료된 영구 삭제된 항목이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-257">**Purges**: Contains hard-deleted items whose deleted item retention period has expired.</span></span> <span data-ttu-id="d2035-258">사용자는 복구 가능한 항목 폴더에서 항목을 제거하여 항목을 영구 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-258">Users can also hard-delete items by purging items from their Recoverable Items folder.</span></span> <span data-ttu-id="d2035-259">사서함이 보류 중이면 영구 삭제된 항목이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-259">If the mailbox is on hold, hard-deleted items are preserved.</span></span> <span data-ttu-id="d2035-260">이 하위폴더는 최종 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-260">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="d2035-261">**DiscoveryHolds**: eDiscovery 보류 또는 보존 정책에 의해 보존된 영구 삭제된 항목을 포함</span><span class="sxs-lookup"><span data-stu-id="d2035-261">**DiscoveryHolds**: Contains hard-deleted items that have been preserved by an eDiscovery hold or a retention policy.</span></span> <span data-ttu-id="d2035-262">이 하위폴더는 최종 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-262">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="d2035-263">**SubstrateHolds**: 보존 정책 또는 다른 유형의 보류에 의해 보존된 Teams 및 기타 클라우드 기반 앱에서 영구 삭제된 항목을 포함</span><span class="sxs-lookup"><span data-stu-id="d2035-263">**SubstrateHolds**: Contains hard-deleted items from Teams and other cloud-based apps that have been preserved by a retention policy or other type of hold.</span></span> <span data-ttu-id="d2035-264">이 하위폴더는 최종 사용자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-264">This subfolder isn't visible to end users.</span></span>

3. <span data-ttu-id="d2035-265">**New-ComplianceSearch** cmdlet(보안 & 준수 센터 PowerShell에서) 또는 준수 센터의 콘텐츠 검색 도구를 사용하여 대상 사용자의 복구 가능한 항목 폴더에서 항목을 반환하는 콘텐츠 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-265">Use the **New-ComplianceSearch** cmdlet (in Security & Compliance Center PowerShell) or use the Content search tool in the compliance center to create a content search that returns items from the target user's Recoverable Items folder.</span></span> <span data-ttu-id="d2035-266">검색할 모든 하위 폴더에 대한 검색 쿼리에 FolderId를 포함하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-266">You can do this by including the FolderId in the search query for all subfolders that you want to search.</span></span> <span data-ttu-id="d2035-267">예를 들어 다음 쿼리는 제거 및 eDiscoveryHolds 하위폴더의 모든 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-267">For example, the following query returns all messages in the Purges and eDiscoveryHolds subfolders:</span></span>

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   <span data-ttu-id="d2035-268">폴더 ID 속성을 사용하는 콘텐츠 검색을 실행하는 데 대한 자세한 내용 및 예제는 폴더 ID 사용 또는 대상 컬렉션 [수행을 참조하세요.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)</span><span class="sxs-lookup"><span data-stu-id="d2035-268">For more information and examples about running content searches that use the folder ID property, see [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d2035-269">**New-ComplianceSearch** cmdlet을 사용하여 복구 가능한 항목 폴더를 검색하는 경우 **Start-ComplianceSearch** cmdlet을 사용하여 검색을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-269">If you use the **New-ComplianceSearch** cmdlet to search the Recoverable Items folder, be sure to use **Start-ComplianceSearch** cmdlet to run the search.</span></span>

4. <span data-ttu-id="d2035-270">콘텐츠 검색을 만든 후 삭제할 항목을 반환하는지 확인한 후 명령(보안 & 준수 센터 PowerShell)을 사용하여 이전 단계에서 만든 콘텐츠 검색에서 반환된 항목을 영구적으로 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-270">After you've created a content search and validated that it returns the items that you wan to delete, use the `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command (in Security & Compliance Center PowerShell) to permanently delete the items returned by the content search that you created in the previous step.</span></span> <span data-ttu-id="d2035-271">예를 들어 다음 명령과 유사한 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-271">For example, you can run a command similar to the following command:</span></span>

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. <span data-ttu-id="d2035-272">이전 명령을 실행하면 사서함당 최대 10개 항목이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-272">A maximum of 10 items per mailbox are deleted when you run the previous command.</span></span> <span data-ttu-id="d2035-273">즉, 복구 가능한 항목 폴더에서 삭제할 모든 항목을 삭제하려면 명령을 여러 번 `New-ComplianceSearchAction -Purge` 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-273">That means you may have to run the `New-ComplianceSearchAction -Purge` command multiple times to delete all the items that you want to delete in the Recoverable Items folder.</span></span> <span data-ttu-id="d2035-274">추가 항목을 삭제하려면 먼저 이전 준수 검색 삭제 작업을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-274">To delete additional items, you first have to remove the previous compliance search purge action.</span></span> <span data-ttu-id="d2035-275">이 작업을 위해 `Remove-ComplianceSearchAction` cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-275">You do this by running the `Remove-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="d2035-276">예를 들어 이전 단계에서 실행된 제거 작업을 삭제하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-276">For example, to delete the purge action that was run in the previous step, run the following command:</span></span>

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   <span data-ttu-id="d2035-277">이 작업을 수행한 후 새 준수 검색 삭제 작업을 만들어 더 많은 항목을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-277">After you do this, you can create a new compliance search purge action to delete more items.</span></span> <span data-ttu-id="d2035-278">새 제거 작업을 만들기 전에 각 제거 작업을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-278">You'll have to delete each purge action before creating a new one.</span></span>

   <span data-ttu-id="d2035-279">준수 검색 작업 목록을 얻습니다. `Get-ComplianceSearchAction` cmdlet을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-279">To get a list of the compliance search actions, you can run the `Get-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="d2035-280">제거 작업은 검색 `_Purge` 이름에 추가하여 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-280">Purge actions are identified by `_Purge` appended to the search name.</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="d2035-281">항목이 삭제된지 확인</span><span class="sxs-lookup"><span data-stu-id="d2035-281">Verify that items were deleted</span></span>

<span data-ttu-id="d2035-282">사서함의 복구 가능한 항목 폴더에서 항목이 성공적으로 삭제 지어 있는지 확인하려면 Exchange Online PowerShell에서 **Get-MailboxFolderStatistics** cmdlet을 사용하여 복구 가능한 항목 폴더에 있는 항목의 크기와 수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-282">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="d2035-283">이러한 통계를 1단계에서 수집한 통계와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-283">You can compare these statistics with the ones you collected in Step 1.</span></span>
  
<span data-ttu-id="d2035-284">다음 명령을 실행하여 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더에 있는 폴더 및 하위 폴더의 현재 크기와 총 항목 수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-284">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="d2035-285">다음 명령을 실행하여 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더의 폴더 및 하위 폴더에 있는 항목의 크기와 총 수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-285">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span>

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="d2035-286">6단계: 사서함을 이전 상태로 되전</span><span class="sxs-lookup"><span data-stu-id="d2035-286">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="d2035-287">마지막 단계는 사서함을 이전 구성으로 되돌리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-287">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="d2035-288">즉, 2단계에서 변경한 속성을 다시 설정하고 3단계에서 제거한 보류를 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-288">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="d2035-289">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-289">This includes:</span></span>
  
- <span data-ttu-id="d2035-290">삭제된 항목 보존 기간을 이전 값으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-290">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="d2035-291">또는 이 집합을 Exchange Online의 최대값인 30일로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-291">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>

- <span data-ttu-id="d2035-292">단일 항목 복구를 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d2035-292">Re-enabling single Item recovery.</span></span>

- <span data-ttu-id="d2035-293">소유자가 자신의 사서함에 액세스할 수 있도록 클라이언트 액세스 방법을 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d2035-293">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>

- <span data-ttu-id="d2035-294">제거한 보존 및 보존 정책을 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-294">Reapplying the holds and retention policies that you removed.</span></span>

- <span data-ttu-id="d2035-295">관리되는 폴더 도우미를 다시 사용하도록 설정하여 사서함을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-295">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2035-296">관리되는 폴더 도우미가 사서함을 처리하도록 다시 사용하도록 설정하기 전에 보류 또는 보존 정책을 다시 적용하고 현재 보존 정책을 적용한 후 24시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-296">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span>
  
<span data-ttu-id="d2035-297">Exchange Online PowerShell에서 다음 단계를 지정한 순서대로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-297">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="d2035-298">삭제된 항목 보존 기간을 다시 원래 값으로 변경하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-298">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="d2035-299">이 경우 이전 설정이 30일 미만인 것으로 가정합니다. 예: 14일</span><span class="sxs-lookup"><span data-stu-id="d2035-299">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="d2035-300">다음 명령을 실행하여 단일 항목 복구를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-300">Run the following command to re-enable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="d2035-301">다음 명령을 실행하여 모든 클라이언트 액세스 방법을 사서함에 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-301">Run the following command to re-enable all client access methods to the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="d2035-302">3단계에서 제거한 보류를 다시합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-302">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="d2035-303">보류 유형에 따라 다음 절차 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-303">Depending on the type of hold, use one of the following procedures.</span></span>

    <span data-ttu-id="d2035-304">**소송 대기**</span><span class="sxs-lookup"><span data-stu-id="d2035-304">**Litigation Hold**</span></span>

    <span data-ttu-id="d2035-305">사서함에 대해 소송 보류를 다시 사용하도록 설정하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-305">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="d2035-306">**원본 위치 유지**</span><span class="sxs-lookup"><span data-stu-id="d2035-306">**In-Place Hold**</span></span>

    <span data-ttu-id="d2035-307">EAC(또는 Exchange Online PowerShell)를 사용하여 사서함을 In-Place 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-307">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span>

    <span data-ttu-id="d2035-308">**특정 사서함에 적용된 보존 정책**</span><span class="sxs-lookup"><span data-stu-id="d2035-308">**Retention policies applied to specific mailboxes**</span></span>

    <span data-ttu-id="d2035-309">보안 및 & 센터를 사용하여 사서함을 보존 정책에 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-309">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="d2035-310">Security & Compliance Center의 정보 거버넌스 보존 페이지로 이동하여 보존 정책을 편집한 다음 보존 정책이 적용되는 받는 사람 목록에 사서함을 다시  >   추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-310">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span>

    <span data-ttu-id="d2035-311">**조직 전체 보존 정책**</span><span class="sxs-lookup"><span data-stu-id="d2035-311">**Organization-wide Retention policies**</span></span>

    <span data-ttu-id="d2035-312">정책에서 정책을 제외하여 조직 전체 또는 Exchange 전체 보존 정책을 제거한 경우 보안 & 준수 센터를 사용하여 제외된 사용자 목록에서 사서함을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-312">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="d2035-313">보안 **및** 준수 센터의 정보 거버넌스 보존 & 조직 전체 보존 정책을 편집하고 제외된 받는 사람 목록에서 사서함을  >   제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-313">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="d2035-314">이렇게 하면 보존 정책이 사용자 사서함에 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-314">Doing this will reapply the retention policy to the user's mailbox.</span></span>

    <span data-ttu-id="d2035-315">**eDiscovery 사례 보류**</span><span class="sxs-lookup"><span data-stu-id="d2035-315">**eDiscovery case holds**</span></span>

    <span data-ttu-id="d2035-316">보안 & 준수 센터를 사용하여 eDiscovery 사례와 연결된 사서함을 다시 보류합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-316">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="d2035-317">**eDiscovery**  >  **eDiscovery** 페이지로 이동하여 사례를 열고 사서함을 보류에 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-317">Go to the **eDiscovery** > **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 

5. <span data-ttu-id="d2035-318">다음 명령을 실행하여 관리되는 폴더 도우미가 사서함을 다시 처리하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-318">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="d2035-319">앞서 언급했듯이 관리되는 폴더 도우미를 다시 사용하도록 설정하기 전에 보류 또는 보존 정책을 다시 적용하고 현재 상태가 확인된 후 24시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-319">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span>

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="d2035-320">사서함이 이전 구성으로 되돌아가고 있는지 확인하려면 다음 명령을 실행한 다음 설정을 1단계에서 수집한 설정과 비교하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-320">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="d2035-321">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d2035-321">More information</span></span>

<span data-ttu-id="d2035-322">**다음은 Get-Mailbox** 또는 **Get-OrganizationConfig** cmdlet을 실행할 때 *InPlaceHolds* 속성의 값에 따라 다양한 유형의 보류를 식별하는 방법을 설명하는 표입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-322">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="d2035-323">자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 식별하는 [방법을 참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="d2035-323">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="d2035-324">앞서 설명한처럼 복구 가능한 항목 폴더의 항목을 성공적으로 삭제하려면 먼저 사서함에서 모든 보류 및 보존 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-324">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span>
  
| <span data-ttu-id="d2035-325">보류 유형</span><span class="sxs-lookup"><span data-stu-id="d2035-325">Hold type</span></span> | <span data-ttu-id="d2035-326">예제 값</span><span class="sxs-lookup"><span data-stu-id="d2035-326">Example value</span></span> | <span data-ttu-id="d2035-327">보류를 식별하는 방법</span><span class="sxs-lookup"><span data-stu-id="d2035-327">How to identify the hold</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="d2035-328">소송 대기</span><span class="sxs-lookup"><span data-stu-id="d2035-328">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="d2035-329">*LitigationHoldEnabled* 속성이 로 `True` 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-329">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="d2035-330">원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="d2035-330">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="d2035-331">*InPlaceHolds* 속성에는 사서함에 In-Place Hold의 GUID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-331">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="d2035-332">GUID가 In-Place 시작하지 않는 경우 이 보류를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-332">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="d2035-333">Exchange Online PowerShell의 명령을 사용하여 사서함의 보류 In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-333">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="d2035-334">특정 사서함에 & 보안 및 준수 센터의 보존 정책</span><span class="sxs-lookup"><span data-stu-id="d2035-334">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="d2035-335">또는</span><span class="sxs-lookup"><span data-stu-id="d2035-335">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="d2035-336">**Get-Mailbox** cmdlet을 실행할 때 *InPlaceHolds* 속성에는 사서함에 적용된 보존 정책의 GUID도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-336">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="d2035-337">GUID는 prefix로 시작하기 때문에 보존 정책을  `mbx` 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-337">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="d2035-338">보존 정책의 GUID가 prefix로 시작하는 경우 보존 정책이 비즈니스용 Skype 대화에  `skp` 적용된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-338">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="d2035-339">사서함에 적용되는 보존 정책을 ID로 설정하기 위해 보안 및 준수 센터 PowerShell에서 & 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-339">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="d2035-340">이 명령을 실행할 때 또는  `mbx`  `skp` prefix를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-340">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="d2035-341">보안 및 준수 센터의 조직 & 정책</span><span class="sxs-lookup"><span data-stu-id="d2035-341">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="d2035-342">값 없음</span><span class="sxs-lookup"><span data-stu-id="d2035-342">No value</span></span>  <br/> <span data-ttu-id="d2035-343">또는</span><span class="sxs-lookup"><span data-stu-id="d2035-343">or</span></span>  <br/>  <span data-ttu-id="d2035-344">`-mbxe9b52bf7ab3b46a286308ecb29624696` (사서함이 조직 전체 정책에서 제외된 것)</span><span class="sxs-lookup"><span data-stu-id="d2035-344">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="d2035-345">**Get-Mailbox** cmdlet을 실행할 때 *InPlaceHolds* 속성이 비어 있는 경우에도 사서함에 하나 이상의 조직 전체 보존 정책이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-345">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="d2035-346">이를 확인하기 위해 Exchange Online PowerShell에서 명령을 실행하여 조직 전체 보존 정책에 대한 GUID 목록을  `Get-OrganizationConfig | FL InPlaceHolds` 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-346">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="d2035-347">Exchange 사서함에 적용된 조직 전체 보존 정책의 GUID는 다음과 같은  `mbx` prefix로  `mbxa3056bb15562480fadb46ce523ff7b02` 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-347">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="d2035-348">사서함에 적용되는 조직 전체 보존 정책을 ID로 설정하기 위해 보안 및 준수 센터 PowerShell에서 & 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-348">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="d2035-349">사서함이 조직 전체 보존 정책에서 제외된 경우 **Get-Mailbox** cmdlet을 실행할 때 보존 정책의 GUID가 사용자 사서함의 *InPlaceHolds* 속성에 표시됩니다. 예를 들면 다음과 같습니다. `-mbx``-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="d2035-349">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="d2035-350">보안 및 준수 센터의 eDiscovery 사례 & 보류</span><span class="sxs-lookup"><span data-stu-id="d2035-350">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="d2035-351">*InPlaceHolds* 속성에는 사서함에 배치될 수 있는 보안 및 준수 센터의 eDiscovery 사례와 & 보류의 GUID도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-351">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="d2035-352">GUID가 prefix로 시작하기 때문에 eDiscovery 케이스 보류라고 알  `UniH` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-352">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="d2035-353">Security &  `Get-CaseHoldPolicy` Compliance Center PowerShell의 cmdlet을 사용하여 사서함의 보류가 연결된 eDiscovery 사례에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-353">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="d2035-354">예를 들어 명령을 실행하여 사서함에 있는 케이스 보류의  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 이름을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-354">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="d2035-355">이 명령을 실행할 때 반드시  `UniH` prefix를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-355">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="d2035-356">사서함의 보류가 연결된 eDiscovery 사례를 ID로 설정하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2035-356">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`

---
title: Exchange의 보존에 대해 자세히 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Exchange 전자 메일과 Exchange 공용 폴더에만 적용되는 보존 동작에 대해 알아봅니다.
ms.openlocfilehash: 57f0bf7737522b0435b076fee46edd1736efd856
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080095"
---
# <a name="learn-about-retention-policies-for-exchange"></a><span data-ttu-id="7b54f-103">Exchange의 보존 정책에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="7b54f-103">Learn about retention policies for Exchange</span></span>

<span data-ttu-id="7b54f-104">이 문서의 정보는 Exchange와 관련된 정보를 포함하므로 [보존 정책에 대해 자세히 알아보기](retention-policies.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-104">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-a-retention-policy-works-with-exchange"></a><span data-ttu-id="7b54f-105">Exchange에서 보존 정책 작동 원리</span><span class="sxs-lookup"><span data-stu-id="7b54f-105">How a retention policy works with Exchange</span></span>

<span data-ttu-id="7b54f-106">사용자의 메일, 일정 및 기타 사서함 항목의 경우 보존 정책은 사서함 수준에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-106">For a user's mail, calendar, and other mailbox items, a retention policy is applied at the level of a mailbox.</span></span>

<span data-ttu-id="7b54f-107">공용 폴더의 경우 보존 정책은 폴더 또는 사서함 수준이 아닌 모든 공용 폴더에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-107">For public folders, a retention policy is applied to all public folders and not at the folder or mailbox level.</span></span>

<span data-ttu-id="7b54f-108">해당 위치에 대한 보존 정책을 구성하면 전자 메일 메시지(임시 보관함 포함)와 첨부 파일, 작업 및 일정 항목이 끝나는 날짜, 메모가 포함된 메일 메시지에 다음 메일 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-108">When you configure a retention policy for these locations, the following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="7b54f-109">종료 날짜가 없는 모든 작업 및 일정 항목은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-109">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="7b54f-110">Skype 및 Teams에 저장된 메시지와 같이 사서함에 저장된 다른 항목은 별도의 보존 정책에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-110">Other items stored in a mailbox, such as Skype and Teams saved messages, are included with their separate retention policy.</span></span>

<span data-ttu-id="7b54f-111">사서함 및 공용 폴더 모두 항목을 보존하기 위해 [복구 가능한 항목 폴더](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-111">Both a mailbox and a public folder use the [Recoverable Items folder](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="7b54f-112">eDiscovery 권한을 할당 받은 사용자만 다른 사용자의 복구 가능한 항목 폴더에서 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-112">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="7b54f-113">사용자가 지운 편지함 폴더 이외의 폴더에서 메시지를 삭제하면 기본적으로 해당 메시지는 지운 편지함 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-113">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="7b54f-114">사용자가 지운 편지함 폴더에서 항목을 삭제하면 해당 메시지는 복구할 수 있는 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-114">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="7b54f-115">그러나 사용자는 모든 폴더에서 Shift+Delete로 항목을 일시적으로 삭제할 수 있습니다. 이 경우 항목이 지운 편지함 폴더를 무시하고 복구할 수 있는 항목 폴더로 바로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-115">However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="7b54f-116">보존 정책을 Exchange 위치에 적용하면 타이머 작업이 복구 가능한 항목 폴더에서 주기적으로 항목을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-116">When you apply a retention policy to an Exchange location, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="7b54f-117">항목이 최소한 하나의 보존 정책의 규칙과 일치하지 않는 경우, 항목은 복구 가능한 항목 폴더에서 영구적으로 삭제됩니다(영구 삭제).</span><span class="sxs-lookup"><span data-stu-id="7b54f-117">If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="7b54f-118">타이머 작업은 최대 7일이 걸릴 수 있으며 Exchange 위치에는 적어도 10MB가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-118">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="7b54f-119">사용자가 메시지의 제목, 본문, 첨부 파일, 보내는 사람 및 받는 사람, 보낸 날짜 또는 받은 날짜와 같은 사서함 항목의 속성을 변경하려고 하면 변경이 적용되기 전에 원본 항목의 복사본이 복구 가능한 항목 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-119">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="7b54f-120">이 작업은 후속 변경이 있을 때마다 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-120">This action happens for each subsequent change.</span></span> <span data-ttu-id="7b54f-121">보존 기간이 끝나면 복구 가능한 항목 폴더의 복사본이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-121">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="7b54f-122">보존 정책을 사서함이나 공용 폴더에 할당한 후 콘텐츠가 사용하는 경로는 보존 설정이 보존 및 삭제, 보존 또는 삭제만 가능한지 여부에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-122">After a retention policy is assigned to a mailbox or public folder, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="7b54f-123">보존 설정이 보존 및 삭제인 경우:</span><span class="sxs-lookup"><span data-stu-id="7b54f-123">When the retention settings are to retain and delete:</span></span>

![전자 메일과 공용 폴더의 보존 흐름 다이어그램](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="7b54f-125">사용자가 보존 기간 내에 **항목을 수정하거나 영구적으로 삭제하면**(SHIFT+DELETE를 사용하거나 삭제된 항목에서 삭제하는 경우) 항목이 복구 가능한 항목 폴더로 이동(또는 편집한 경우 복사)됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-125">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="7b54f-126">여기에서 타이머 작업이 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-126">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="7b54f-127">14일은 기본값이며, 최대 30일로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-127">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="7b54f-128">보존 기간 내에 **항목이 수정되거나 삭제되지 않으면** 사서함의 모든 폴더에서 동일한 프로세스가 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-128">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="7b54f-129">14일은 기본값이며, 최대 30일로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-129">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="7b54f-130">보존 설정이 보존 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보존 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-130">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="7b54f-131">보존 전용 보존 설정의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="7b54f-131">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="7b54f-132">보존 기간 동안 **항목이 수정되거나 삭제된 경우**: 복구 가능한 항목 폴더의 사본이 항목이 만료된 후 14일 이내에 영구적으로 삭제되면 원래 항목의 사본이 복구 가능한 항목 폴더에 작성되고 보존 기간이 끝날 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-132">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="7b54f-133">보존 기간 동안 **항목이 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 항목은 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-133">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="7b54f-134">삭제 전용 보존 설정의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="7b54f-134">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="7b54f-135">구성된 기간에 **항목이 삭제되지 않은 경우**: 보존 정책에서 구성된 기간이 끝나면 항목은 복구 가능한 항목 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-135">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="7b54f-136">구성된 기간에 **항목이 삭제된 경우**: 항목은 즉시 복구 가능한 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-136">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="7b54f-137">사용자가 해당 항목을 삭제하거나 복구 가능한 항목 폴더를 비우면 항목이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-137">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="7b54f-138">그렇지 않으면 14일 동안 복구 가능한 항목 폴더에있는 항목이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-138">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="7b54f-139">보존 정책에서 특정 유형의 Exchange 항목 제외</span><span class="sxs-lookup"><span data-stu-id="7b54f-139">Excluding specific types of Exchange items from a retention policy</span></span>

<span data-ttu-id="7b54f-140">보존 설정이 보존 전용인 경우 PowerShell을 사용하여 보존 정책에서 특정 유형의 Exchange 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-140">By using PowerShell, you can exclude specific types of Exchange items from a retention policy when the retention settings are for retain-only.</span></span> <span data-ttu-id="7b54f-141">예를 들어 사서함에서 음성 사서함 메시지, IM 대화 및 기타 비즈니스용 Skype Online 콘텐츠를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-141">For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes.</span></span> <span data-ttu-id="7b54f-142">일정, 메모 및 작업 항목도 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-142">You can also exclude calendar, note, and task items.</span></span> <span data-ttu-id="7b54f-143">이 기능은 PowerShell을 통해서만 사용할 수 있으며, Microsoft 365 규정 준수 센터에서 마법사를 사용하여 보존 정책을 만들 때는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-143">This capability is available only by using PowerShell; it's not available when you create a retention policy by using the wizard in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="7b54f-144">보존 정책에서 Exchange 항목에 대해 선택한 유형을 제외하려면 [RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) 및 [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) cmdlet로 `ExcludedItemClasses` 매개 변수를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7b54f-144">To exclude your selected types for Exchange items in a retention policy, use the  `ExcludedItemClasses` parameter with the [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) and  [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) cmdlets.</span></span>

<span data-ttu-id="7b54f-145">보존 정책 cmdlet을 사용하려면 먼저 [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-145">To use the retention policies cmdlets, you must first [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="7b54f-146">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="7b54f-146">When a user leaves the organization</span></span> 

<span data-ttu-id="7b54f-147">조직에서 나간 사용자의 사서함이 보존 정책에 포함되어 있는 경우, 사용자의 Microsoft 365 계정이 삭제되면 해당 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-147">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="7b54f-148">비활성화된 사서함의 콘텐츠 또한 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-148">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="7b54f-149">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b54f-149">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a><span data-ttu-id="7b54f-150">Exchange에 보존 정책을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="7b54f-150">How to configure a retention policy for Exchange</span></span>

<span data-ttu-id="7b54f-151">[보존 정책 만들기](create-retention-policies.md) 및 구성 지침에 따라 마법사의 **위치 선택** 페이지에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-151">Follow the instructions for [Create and configure retention policies](create-retention-policies.md) and for the **Choose locations**  page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="7b54f-152">**Exchange 전자 메일, 공용 폴더, Office 365 그룹, OneDrive 및 SharePoint 문서에 있는 콘텐츠에만 정책 적용하기**</span><span class="sxs-lookup"><span data-stu-id="7b54f-152">**Apply policy only to content in Exchange email, public folders, Office 365 groups, OneDrive and SharePoint documents**</span></span>

- <span data-ttu-id="7b54f-153">**특정 위치 선택 허용** > **Exchange 전자 메일**, **Exchange 공용 폴더** 및 **Office 365 그룹**. </span><span class="sxs-lookup"><span data-stu-id="7b54f-153">**Let me choose specific locations** > **Exchange email**, **Exchange public folders**, and **Office 365 groups**.</span></span>

<span data-ttu-id="7b54f-154">Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b54f-154">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="7b54f-155">이러한 사서함의 콘텐츠를 보존하려면 **Office 365 그룹** 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="7b54f-155">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

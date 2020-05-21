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
ms.openlocfilehash: db39ab0f1eca1cc03dd0bbb5ffb500658695247a
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292536"
---
# <a name="learn-about-retention-policies-for-exchange"></a><span data-ttu-id="bab88-103">Exchange의 보존 정책에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="bab88-103">Learn about retention policies for Exchange</span></span>

<span data-ttu-id="bab88-104">이 문서의 정보는 Exchange와 관련된 정보를 포함하므로 [보존 정책에 대해 자세히 알아보기](retention-policies.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-104">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-a-retention-policy-works-with-exchange-locations"></a><span data-ttu-id="bab88-105">보존 정책이 Exchange 위치와 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="bab88-105">How a retention policy works with Exchange locations</span></span>

<span data-ttu-id="bab88-106">사용자의 메일, 일정 및 기타 항목의 경우 보존 정책은 사서함 수준에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-106">For a user's mail, calendar, and other items, a retention policy is applied at the level of a mailbox.</span></span>

<span data-ttu-id="bab88-107">공용 폴더의 경우 사서함 수준이 아닌 폴더 수준에서 보존 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-107">For a public folder, a retention policy is applied at the folder level, not the mailbox level.</span></span> 

<span data-ttu-id="bab88-108">사서함 및 공용 폴더 모두 항목을 보존하기 위해 복구 가능한 항목 폴더를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-108">Both a mailbox and a public folder use the Recoverable Items folder to retain items.</span></span> <span data-ttu-id="bab88-109">eDiscovery 권한을 할당 받은 사용자만 다른 사용자의 복구 가능한 항목 폴더에서 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-109">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="bab88-110">사용자가 지운 편지함 폴더 이외의 폴더에서 메시지를 삭제하면 기본적으로 해당 메시지는 지운 편지함 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-110">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="bab88-111">사용자가 지운 편지함 폴더에서 항목을 삭제하면 해당 메시지는 복구할 수 있는 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-111">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="bab88-112">그러나 사용자는 모든 폴더에서 Shift+Delete로 항목을 일시적으로 삭제할 수 있습니다. 이 경우 항목이 지운 편지함 폴더를 무시하고 복구할 수 있는 항목 폴더로 바로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-112">However, a user can soft-delete an item (SHIFT+DELETE) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="bab88-113">보존 정책을 Exchange 위치에 적용하면 타이머 작업이 복구 가능한 항목 폴더에서 주기적으로 항목을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-113">When you apply a retention policy to an Exchange location, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="bab88-114">항목이 최소한 하나의 보존 정책의 규칙과 일치하지 않는 경우, 항목은 복구 가능한 항목 폴더에서 영구적으로 삭제됩니다(영구 삭제).</span><span class="sxs-lookup"><span data-stu-id="bab88-114">If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="bab88-115">타이머 작업은 최대 7일이 걸릴 수 있으며 Exchange 위치에는 적어도 10MB가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-115">The timer job can take up to 7 days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="bab88-116">사용자가 메시지의 제목, 본문, 첨부 파일, 보내는 사람 및 받는 사람, 보낸 날짜 또는 받은 날짜와 같은 사서함 항목의 속성을 변경하려고 하면 변경이 적용되기 전에 원본 항목의 복사본이 복구 가능한 항목 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-116">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="bab88-117">이 작업은 후속 변경이 있을 때마다 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-117">This action happens for each subsequent change.</span></span> <span data-ttu-id="bab88-118">보존 기간이 끝나면 복구 가능한 항목 폴더의 복사본이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-118">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="bab88-119">보존 정책을 사서함이나 공용 폴더에 할당한 후 콘텐츠가 사용하는 경로는 보존 설정이 보존 및 삭제, 보존 또는 삭제만 가능한지 여부에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-119">After a retention policy is assigned to a mailbox or public folder, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="bab88-120">보존 설정이 보존 및 삭제인 경우:</span><span class="sxs-lookup"><span data-stu-id="bab88-120">When the retention settings are to retain and delete:</span></span>

![전자 메일과 공용 폴더의 보존 흐름 다이어그램](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="bab88-122">사용자가 보존 기간 내에 **항목을 수정하거나 영구적으로 삭제하면**(SHIFT+DELETE를 사용하거나 삭제된 항목에서 삭제하는 경우) 항목이 복구 가능한 항목 폴더로 이동(또는 편집한 경우 복사)됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-122">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="bab88-123">여기에서 타이머 작업이 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-123">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="bab88-124">14일은 기본값이며, 최대 30일로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-124">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>
    
2. <span data-ttu-id="bab88-125">보존 기간 내에 **항목이 수정되거나 삭제되지 않으면** 사서함의 모든 폴더에서 동일한 프로세스가 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-125">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="bab88-126">14일은 기본값이며, 최대 30일로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-126">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="bab88-127">보존 설정이 보존 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보존 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-127">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="bab88-128">보존 전용 보존 설정의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="bab88-128">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="bab88-129">보존 기간 동안 **항목이 수정되거나 삭제된 경우**: 복구 가능한 항목 폴더의 사본이 항목이 만료된 후 14일 이내에 영구적으로 삭제되면 원래 항목의 사본이 복구 가능한 항목 폴더에 작성되고 보존 기간이 끝날 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-129">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="bab88-130">보존 기간 동안 **항목이 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 항목은 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-130">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="bab88-131">삭제 전용 보존 설정의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="bab88-131">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="bab88-132">구성된 기간에 **항목이 삭제되지 않은 경우**: 보존 정책에서 구성된 기간이 끝나면 항목은 복구 가능한 항목 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-132">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable items folder.</span></span> 

2. <span data-ttu-id="bab88-133">구성된 기간에 **항목이 삭제된 경우**: 항목은 즉시 복구 가능한 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-133">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable items folder.</span></span> <span data-ttu-id="bab88-134">사용자가 해당 항목을 삭제하거나 복구 가능한 항목 폴더를 비우면 항목이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-134">If a user deletes the item from there or empties the Recoverable items folder, the item is permanently deleted.</span></span> <span data-ttu-id="bab88-135">그렇지 않으면 14일 동안 복구 가능한 항목 폴더에있는 항목이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-135">Otherwise, the item is permanently deleted after being in the Recoverable items folder for 14 days.</span></span> 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="bab88-136">보존 정책에서 특정 유형의 Exchange 항목 제외</span><span class="sxs-lookup"><span data-stu-id="bab88-136">Excluding specific types of Exchange items from a retention policy</span></span>

<span data-ttu-id="bab88-137">PowerShell을 사용하여 보존 정책에서 특정 유형의 Exchange 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-137">By using PowerShell, you can exclude specific types of Exchange items from a retention policy.</span></span> <span data-ttu-id="bab88-138">예를 들어 사서함에서 음성 사서함 메시지, IM 대화 및 기타 비즈니스용 Skype Online 콘텐츠를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-138">For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes.</span></span> <span data-ttu-id="bab88-139">일정, 메모 및 작업 항목도 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-139">You can also exclude calendar, note, and task items.</span></span> <span data-ttu-id="bab88-140">이 기능은 PowerShell을 통해서만 사용할 수 있으며, Microsoft 365 규정 준수 센터에서 마법사를 사용하여 보존 정책을 만들 때는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-140">This capability is available only by using PowerShell; it's not available when you create a retention policy by using the wizard in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="bab88-141">보존 정책에서 Exchange 항목에서 선택한 유형을 제외하려면 `New-RetentionComplianceRule` 및 `Set-RetentionComplianceRule` cmdlet과 `ExcludedItemClasses` 매개 변수를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="bab88-141">To exclude your selected types for Exchange items in a retention policy, use the  `ExcludedItemClasses` parameter with the  `New-RetentionComplianceRule` and  `Set-RetentionComplianceRule` cmdlets.</span></span>


### <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="bab88-142">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="bab88-142">When a user leaves the organization</span></span> 

<span data-ttu-id="bab88-143">조직에서 나간 사용자의 사서함이 보존 정책에 포함되어 있는 경우, 사용자의 Office 365 계정이 삭제되면 해당 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-143">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Office 365 account is deleted.</span></span> <span data-ttu-id="bab88-144">비활성화된 사서함의 콘텐츠 또한 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab88-144">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="bab88-145">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bab88-145">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a><span data-ttu-id="bab88-146">Exchange에 보존 정책을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="bab88-146">How to configure a retention policy for Exchange</span></span>

<span data-ttu-id="bab88-147">[보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bab88-147">See [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="bab88-148">마법사의 **위치 선택** 페이지에서 다음 옵션 중 하나를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="bab88-148">For the **Choose locations** page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="bab88-149">**Exchange 전자 메일, 공용 폴더, Office 365 그룹, OneDrive와 SharePoint 문서에 있는 콘텐츠에만 정책 적용하기**</span><span class="sxs-lookup"><span data-stu-id="bab88-149">**Apply policy only to content in Exchange email, public folders, Office 365 groups, OneDrive and SharePoint documents**</span></span>

- <span data-ttu-id="bab88-150">**특정 위치 선택 허용** > **Exchange 전자 메일** 및 **Exchange 공용 폴더**</span><span class="sxs-lookup"><span data-stu-id="bab88-150">**Let me choose specific locations** > **Exchange email** and **Exchange public folders**</span></span>


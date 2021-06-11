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
description: Exchange에서 보존의 작동 방식을 알아봅니다.
ms.openlocfilehash: efb95b22355bff292ef63c77fb77fb5a15d66722
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861134"
---
# <a name="learn-about-retention-for-exchange"></a><span data-ttu-id="3dab1-103">Exchange의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="3dab1-103">Learn about retention for Exchange</span></span>

<span data-ttu-id="3dab1-104">Exchange에 관한 정보를 담고 있으므로 이 문서의 정보는 [보존 정책에 대해 자세히 알아보기](retention.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-104">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Exchange.</span></span>  <span data-ttu-id="3dab1-105">다른 워크로드는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dab1-105">For other workloads, see:</span></span>

- [<span data-ttu-id="3dab1-106">SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="3dab1-106">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="3dab1-107">Microsoft Teams의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="3dab1-107">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="3dab1-108">Yammer의 보존에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="3dab1-108">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="3dab1-109">보존 및 삭제에 포함된 항목</span><span class="sxs-lookup"><span data-stu-id="3dab1-109">What's included for retention and deletion</span></span>

<span data-ttu-id="3dab1-110">보존 정책 및 보존 레이블을 사용하여 다음 Exchange 항목을 보존 및 삭제할 수 있습니다.: 첨부 파일이 있는 메일 메시지(초안 포함), 종료 날짜와 노트가 있는 작업</span><span class="sxs-lookup"><span data-stu-id="3dab1-110">The following Exchange items can be retained and deleted by using retention policies and retention labels: Mail messages (includes drafts) with any attachments, tasks when they have an end date, and notes.</span></span> 

<span data-ttu-id="3dab1-111">종료 날짜가 있는 일정 항목은 보존 정책에서 지원되지만 보존 레이블에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-111">Calendar items that have an end date are supported for retention policies but aren't supported for retention labels.</span></span>

<span data-ttu-id="3dab1-112">종료 날짜가 없는 모든 작업 및 일정 항목은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-112">Contacts, and any tasks and calendar items that don't have an end date are not supported.</span></span>

<span data-ttu-id="3dab1-p102">사서함에 저장된 다른 항목(예: Skype 및 팀 메시지)은 Exchange의 보존 정책 또는 레이블에 포함되지 않습니다. 이러한 항목에는 자체 보존 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-p102">Other items stored in a mailbox, such as Skype and Teams messages, aren't included in retention policies or labels for Exchange. These items have their own retention policies.</span></span>

## <a name="how-retention-works-for-exchange"></a><span data-ttu-id="3dab1-115">Exchange에서 보존의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="3dab1-115">How retention works for Exchange</span></span>

<span data-ttu-id="3dab1-116">사서함 및 공용 폴더 모두 항목을 보존하기 위해 [복구 가능한 항목 폴더](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-116">Both a mailbox and a public folder use the [Recoverable Items folder](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="3dab1-117">eDiscovery 권한을 할당 받은 사용자만 다른 사용자의 복구 가능한 항목 폴더에서 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-117">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="3dab1-p104">사용자가 지운 편지함 폴더 이외의 폴더에서 메시지를 삭제하면 해당 메시지는 기본적으로 지운 편지함 폴더로 이동합니다. 사용자가 지운 편지함 폴더에서 항목을 삭제하면 메시지가 복구할 수 있는 항목 폴더로 이동합니다. 그러나 사용자는 Shift+Delete를 눌러 항목을 일시적으로 삭제할 수 있으며, 이 경우 항목이 지운 편지함 폴더를 거치지 않고 복구할 수 있는 항목 폴더로 바로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-p104">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder. When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder. However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="3dab1-121">보존 설정을 Exchange 데이터에 적용하면 타이머 작업이 복구 가능한 항목 폴더의 항목을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-121">When you apply retention settings to Exchange data, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="3dab1-122">항목이 하나 이상의 보존 정책이나 보존 레이블의 규칙과 일치하지 않는 경우, 항목은 복구 가능한 항목 폴더에서 영구적으로 삭제됩니다(영구 삭제).</span><span class="sxs-lookup"><span data-stu-id="3dab1-122">If an item doesn't match the rules of at least one retention policy or retention label to retain the item, it is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

> [!NOTE]
> <span data-ttu-id="3dab1-123">[첫 번째 보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence) 때문에 다른 보존 정책 또는 보존 레이블로 인해 동일한 항목을 유지해야 하거나 법적 또는 조사상의 이유로 eDiscovery 보류 상태에 있는 경우 영구 삭제는 항상 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-123">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy or retention label, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="3dab1-124">타이머 작업은 최대 7일이 걸릴 수 있으며 Exchange 위치에는 적어도 10MB가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-124">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="3dab1-p106">사용자가 메시지의 제목, 본문, 첨부 파일, 보낸 사람 및 받는 사람, 보낸 날짜 또는 받은 날짜와 같은 사서함 항목의 특정 속성을 변경하려고 하면 변경을 제출하기 전에 원본 항목의 복사본이 복구 가능한 항목 폴더에 저장됩니다. 이 작업은 후속 변경이 있을 때마다 진행됩니다. 보존 기간이 끝나면 복구 가능한 항목 폴더의 사본이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-p106">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed. This action happens for each subsequent change. At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="3dab1-128">보존 설정을 Exchange 콘텐츠에 적용한 후에 콘텐츠가 사용하는 경로는 보존 설정이 보존 후 삭제하는지, 아니면 보존 또는 삭제 한 가지만 실행하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-128">After retention settings are applied to Exchange content, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="3dab1-129">보존 설정이 보존 및 삭제인 경우:</span><span class="sxs-lookup"><span data-stu-id="3dab1-129">When the retention settings are to retain and delete:</span></span>

![전자 메일과 공용 폴더의 보존 흐름 다이어그램](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="3dab1-131">사용자가 보존 기간 내에 **항목을 수정하거나 영구적으로 삭제하면**(SHIFT+DELETE를 사용하거나 삭제된 항목에서 삭제하는 경우) 항목이 복구 가능한 항목 폴더로 이동(또는 편집한 경우 복사)됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-131">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="3dab1-132">여기에서 타이머 작업이 주기적으로 실행되며 보존 기간이 만료된 항목을 식별합니다. 식별된 항목은 보존 기간 종료일로부터 14일 이내에 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-132">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="3dab1-133">14일은 기본값이며, 최대 30일로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-133">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="3dab1-p108">**보존 기간 동안 항목이 수정되거나 삭제되지 않는 경우** 동일한 프로세스가 사서함의 모든 폴더에 대해 주기적으로 실행되고 보존 기간이 만료된 항목이 식별되며, 이러한 항목은 보존 기간이 끝나고 14일 이내에 영구적으로 삭제됩니다. 14일은 기본 설정이지만 최대 30일로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-p108">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="3dab1-136">보존 설정이 보존 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보존 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-136">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="3dab1-137">보존 전용 보존 설정의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="3dab1-137">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="3dab1-138">보존 기간 동안 **항목이 수정되거나 삭제된 경우**: 복구 가능한 항목 폴더의 사본이 항목이 만료된 후 14일 이내에 영구적으로 삭제되면 원래 항목의 사본이 복구 가능한 항목 폴더에 작성되고 보존 기간이 끝날 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-138">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="3dab1-139">보존 기간 동안 **항목이 수정되거나 삭제되지 않은 경우**: 보존 기간 전후에는 아무 것도 발생하지 않습니다. 항목은 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-139">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="3dab1-140">삭제 전용 보존 설정의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="3dab1-140">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="3dab1-141">구성된 기간에 **항목이 삭제되지 않은 경우**: 보존 정책에서 구성된 기간이 끝나면 항목은 복구 가능한 항목 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-141">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="3dab1-142">구성된 기간에 **항목이 삭제된 경우**: 항목은 즉시 복구 가능한 항목 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-142">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="3dab1-143">사용자가 해당 항목을 삭제하거나 복구 가능한 항목 폴더를 비우면 항목이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-143">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="3dab1-144">그렇지 않으면 14일 동안 복구 가능한 항목 폴더에있는 항목이 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-144">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="3dab1-145">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="3dab1-145">When a user leaves the organization</span></span> 

<span data-ttu-id="3dab1-146">조직에서 나간 사용자의 사서함이 보존 정책에 포함되어 있는 경우, 사용자의 Microsoft 365 계정이 삭제되면 해당 사서함이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-146">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="3dab1-147">비활성화된 사서함의 콘텐츠 또한 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dab1-147">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="3dab1-148">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dab1-148">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="3dab1-149">구성 지침</span><span class="sxs-lookup"><span data-stu-id="3dab1-149">Configuration guidance</span></span>

<span data-ttu-id="3dab1-150">Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dab1-150">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="3dab1-151">Exchange의 보존 정책 또는 보존 레이블을 구성할 준비가 되면 다음 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dab1-151">If you're ready to configure a retention policy or retention label for Exchange, see the following instructions:</span></span>
- [<span data-ttu-id="3dab1-152">보존 정책 만들기 및 구성하기</span><span class="sxs-lookup"><span data-stu-id="3dab1-152">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="3dab1-153">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="3dab1-153">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="3dab1-154">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="3dab1-154">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)
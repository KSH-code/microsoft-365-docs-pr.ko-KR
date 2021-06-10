---
title: Yammer의 보존에 대한 자세한 정보
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
description: Yammer에 적용되는 보존 정책에 대해 자세히 알아보기
ms.openlocfilehash: a8d047845b986029d393816982e6bede3db71485
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861566"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="9ee9e-103">Yammer의 보존에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9ee9e-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="9ee9e-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="9ee9e-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="9ee9e-105">이 기능은 미리 보기 상태이기 때문에 일부 고객은 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="9ee9e-106">Yammer에 관한 정보를 담고 있으므로 이 문서의 정보는 [보존 정책에 대해 자세히 알아보기](retention.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="9ee9e-107">다른 워크로드는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-107">For other workloads, see:</span></span>

- [<span data-ttu-id="9ee9e-108">SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="9ee9e-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="9ee9e-109">Microsoft Teams의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="9ee9e-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="9ee9e-110">Exchange의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="9ee9e-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="9ee9e-111">보존 및 삭제에 포함된 항목</span><span class="sxs-lookup"><span data-stu-id="9ee9e-111">What's included for retention and deletion</span></span>

<span data-ttu-id="9ee9e-112">Yammer에 대한 보존 정책을 사용하여 커뮤니티 메시지 및 개인 메시지 Yammer 항목을 보존 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="9ee9e-113">이모티콘 형태의 다른 사람의 반응은 이 메시지에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="9ee9e-114">Yammer를 사용하는 경우의 보존 방식</span><span class="sxs-lookup"><span data-stu-id="9ee9e-114">How retention works with Yammer</span></span>

<span data-ttu-id="9ee9e-115">보존 정책을 사용하여 Yammer에서 커뮤니티 메시지와 비공개 메시지를 보존 하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="9ee9e-116">비공개 메시지는 메시지에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, 커뮤니티 메시지는 커뮤니티의 그룹 사서함에 있는 유사한 숨겨진 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="9ee9e-117">Yammer 메시지는 사용자 또는 그룹 사서함에 대해 구성된 보존 정책의 영향을받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="9ee9e-118">Yammer 메시지가 Exchange에 저장되어 있어도 이 Yammer 데이터는 **Yammer 커뮤니티 메시지** 및 **Yammer 사용자 메시지** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="9ee9e-119">Yammer 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Yammer 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="9ee9e-120">사용자에 대한 이 Yammer 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="9ee9e-121">Yammer 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Yammer 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="9ee9e-122">타이머 작업의 실행은 7일까지 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="9ee9e-123">이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 하나의 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="9ee9e-124">[첫 번째 보존 원칙](retention.md#the-principles-of-retention-or-what-takes-precedence) 때문에 다른 보존 정책으로 인해 동일한 항목을 유지해야 하거나 법적 또는 조사상의 이유로 eDiscovery 보류 상태에 있는 경우 영구 삭제는 항상 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-124">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="9ee9e-125">Yammer 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-125">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="9ee9e-126">보존 정책을 유지한 후 삭제하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-126">When the retention policy is to retain and then delete:</span></span>

![Yammer 메시지의 보존 흐름 다이어그램](../media/yammerretentionlifecycle.png)

<span data-ttu-id="9ee9e-128">다이어그램의 두 경로:</span><span class="sxs-lookup"><span data-stu-id="9ee9e-128">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="9ee9e-129">보존 기간 동안 사용자가 **Yammer 메시지를 편집하거나 삭제** 하는 경우에는 원본 메시지가 즉시 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-129">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="9ee9e-130">이 메시지는 보존 기간이 만료될 때까지 저장된 다음 즉시 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-130">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="9ee9e-131">**Yammer 메시지가 삭제되지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-131">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="9ee9e-132">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-132">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="9ee9e-133">메시지가 SubstrateHolds 폴더에 있으면 즉시 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-133">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="9ee9e-134">SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-134">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="9ee9e-135">메시지가 영구적으로 삭제 될 때까지 (SubstrateHolds 폴더에서)는 eDiscovery 도구에 의해 검색가능한 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-135">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="9ee9e-136">보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-136">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="9ee9e-137">보유 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="9ee9e-137">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="9ee9e-138">**Yammer 메시지를 편집하거나 삭제하는 경우**: 원본 메시지의 복사본은 SubstrateHolds 폴더에 즉시 만들어지고 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-138">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="9ee9e-139">그런 다음 즉시 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-139">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="9ee9e-140">**Yammer 메시지가 수정되거나 삭제되지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-140">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="9ee9e-141">삭제 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="9ee9e-141">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="9ee9e-142">보존 기간 동안 **Yammer 메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-142">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="9ee9e-143">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-143">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="9ee9e-144">그런 다음 즉시 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-144">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="9ee9e-145">해당 기간 동안 **사용자가 Yammer 메시지를 삭제하는 경우** 그 항목은 즉시 영구적으로 삭제되는 SubstrateHolds 폴더로 즉시 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-145">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="9ee9e-146">메시지 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="9ee9e-146">Messages and external users</span></span>

<span data-ttu-id="9ee9e-147">기본적으로 Yammer 사용자 메시지에 대한 보존 정책은 조직의 모든 사용자에게 적용되지만 외부 사용자에게는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-147">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="9ee9e-148">**사용자 선택** 을 사용하고 해당 계정을 지정하는 경우 외부 사용자에게 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-148">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="9ee9e-149">지금은 Azure B2B 게스트 사용자가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-149">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="9ee9e-150">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="9ee9e-150">When a user leaves the organization</span></span> 

<span data-ttu-id="9ee9e-151">사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 Yammer 사용자 메시지는 비활성 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-151">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="9ee9e-152">이들 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-152">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="9ee9e-153">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-153">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="9ee9e-154">사용자가 Yammer에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-154">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="9ee9e-155">제한 사항</span><span class="sxs-lookup"><span data-stu-id="9ee9e-155">Limitations</span></span>

<span data-ttu-id="9ee9e-156">Yammer 보존 정책은 현재 미리 보기 상태이며 당사는 보존 기능 최적화를 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-156">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="9ee9e-157">그동안 Yammer 커뮤니티 메시지 및 개인 메시지에 대해 보존을 사용할 때 다음 제한 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-157">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="9ee9e-158">**Yammer 사용자 메시지** 위치에 대해 **사용자 선택** 을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-158">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="9ee9e-159">보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-159">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="9ee9e-160">구성 지침</span><span class="sxs-lookup"><span data-stu-id="9ee9e-160">Configuration guidance</span></span>

<span data-ttu-id="9ee9e-161">Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-161">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="9ee9e-162">Yammer에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-162">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>
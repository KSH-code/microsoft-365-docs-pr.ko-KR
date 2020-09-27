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
ms.openlocfilehash: 2918efe63947ee17cd7f55f19876ae4b98de7a8a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204389"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="14d3b-103">Yammer의 보존에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="14d3b-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="14d3b-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="14d3b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="14d3b-105">Yammer에 관한 정보를 담고 있으므로 이 문서의 정보는 [보존 정책에 대해 자세히 알아보기](retention.md)를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="14d3b-106">Yammer를 사용하는 경우의 보존 방식</span><span class="sxs-lookup"><span data-stu-id="14d3b-106">How retention works with Yammer</span></span>

<span data-ttu-id="14d3b-107">보존 정책을 사용하여 Yammer에서 커뮤니티 메시지와 비공개 메시지를 보존 하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-107">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="14d3b-108">비공개 메시지는 메시지에 포함된 각 사용자의 사서함에 있는 숨겨진 폴더에 저장되고, 커뮤니티 메시지는 커뮤니티의 그룹 사서함에 있는 유사한 숨겨진 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-108">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="14d3b-109">Yammer 메시지는 사용자 또는 그룹 사서함에 대해 구성된 보존 정책의 영향을받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-109">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="14d3b-110">Yammer 메시지가 Exchange에 저장되어 있어도 이 Yammer 데이터는 **Yammer 커뮤니티 메시지** 및 **Yammer 비공개 메시지** 위치에 대해 구성된 보존 정책에 의해서만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-110">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="14d3b-111">Yammer 데이터를 보존하는 활성 보존 정책에 사용자가 포함되어 있고 Yammer 데이터를 보존하기 위해 이 정책에 포함된 사용자의 사서함을 삭제하면 사서함이 [비활성 사서함](inactive-mailboxes-in-office-365.md)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-111">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="14d3b-112">사용자에 대한 이 Yammer 데이터를 유지할 필요가 없는 경우 사서함을 삭제하기 전에 사용자 계정을 보존 정책에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-112">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="14d3b-113">Yammer 메시지에 대한 보존 정책을 구성한 후에는, Exchange 서비스의 타이머 작업이 해당 Yammer 메시지가 저장된 숨겨진 폴더의 항목을 주기적으로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-113">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="14d3b-114">타이머 작업의 실행은 7일까지 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-114">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="14d3b-115">이러한 항목의 보존 기간이 만료되면, 해당 항목은 영구적으로 삭제되기 전에 모든 사용자 또는 그룹 사서함에서 "일시 삭제됨" 항목을 저장하는 하나의 숨겨진 폴더인 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-115">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="14d3b-116">Yammer 메시지에 대해 보존 정책을 구성한 후 콘텐츠가 취하는 경로는 보존 정책이 보존 및 삭제, 보존만 또는 삭제만 가능한지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-116">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="14d3b-117">보존 정책을 유지한 후 삭제하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-117">When the retention policy is to retain and then delete:</span></span>

![Yammer 메시지의 보존 흐름 다이어그램](../media/yammerretentionlifecycle.png)

<span data-ttu-id="14d3b-119">다이어그램의 두 경로:</span><span class="sxs-lookup"><span data-stu-id="14d3b-119">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="14d3b-120">보존 기간 동안 사용자가 **Yammer 메시지를 편집하거나 삭제**하는 경우에는 원본 메시지가 즉시 복사되거나(편집된 경우) 또는 (삭제된 경우) SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-120">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="14d3b-121">이 메시지는 보존 기간이 만료될 때까지 저장된 다음 즉시 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-121">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="14d3b-122">**Yammer 메시지가 삭제되지 않는 경우**, 편집 후 현재 메시지에 대한 메시지는 보존 기간이 만료 된 후 SubstrateHolds 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-122">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="14d3b-123">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-123">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="14d3b-124">메시지가 SubstrateHolds 폴더에 있으면 즉시 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-124">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="14d3b-125">SubstrateHolds 폴더의 메시지는 eDiscovery 도구에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-125">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="14d3b-126">메시지가 영구적으로 삭제 될 때까지 (SubstrateHolds 폴더에서)는 eDiscovery 도구에 의해 검색가능한 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-126">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="14d3b-127">보유 정책이 보유 전용 또는 삭제 전용인 경우 컨텐츠 경로는 보유 및 삭제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-127">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="14d3b-128">보유 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="14d3b-128">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="14d3b-129">**Yammer 메시지를 편집하거나 삭제하는 경우**: 원본 메시지의 복사본은 SubstrateHolds 폴더에 즉시 만들어지고 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-129">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="14d3b-130">그런 다음 즉시 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-130">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="14d3b-131">**Yammer 메시지가 수정되거나 삭제되지 않거나** 보존 기간 중에 편집 후 현재 메시지에 대한 경우: 보존 기간 전후에 아무런 변화가 없습니다. 메시지는 원래 위치에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-131">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="14d3b-132">삭제 전용 보존 정책의 컨텐츠 경로</span><span class="sxs-lookup"><span data-stu-id="14d3b-132">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="14d3b-133">보존 기간 동안 **Yammer 메시지가 삭제되지 않은 경우**: 보존 기간이 끝나면 메시지가 SubstrateHolds 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-133">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="14d3b-134">이 작업은 만료 날짜로부터 최대 7일이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-134">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="14d3b-135">그런 다음 즉시 SubstrateHolds 폴더에서 메시지가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-135">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="14d3b-136">해당 기간 동안 **사용자가 Yammer 메시지를 삭제하는 경우** 그 항목은 즉시 영구적으로 삭제되는 SubstrateHolds 폴더로 즉시 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-136">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="14d3b-137">메시지 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="14d3b-137">Messages and external users</span></span>

<span data-ttu-id="14d3b-138">기본적으로 Yammer 비공개 메시지에 대한 보존 정책은 조직의 모든 사용자에게 적용되지만 외부 사용자에게는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-138">By default, a retention policy for Yammer private messages apply to all users in your organization, but not external users.</span></span> <span data-ttu-id="14d3b-139">**사용자 선택**을 사용하고 해당 계정을 지정하는 경우 외부 사용자에게 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-139">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="14d3b-140">지금은 Azure B2B 게스트 사용자가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-140">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="14d3b-141">사용자가 조직을 떠나는 경우</span><span class="sxs-lookup"><span data-stu-id="14d3b-141">When a user leaves the organization</span></span> 

<span data-ttu-id="14d3b-142">사용자가 조직을 떠나 Microsoft 365 계정이 삭제된 경우 보존이 적용되는 해당 사용자의 Yammer 비공개 메시지는 비활성 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-142">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="14d3b-143">이들 메시지는 비활성화 상태로 변경되기 전에 사서함에 적용된 보존 정책의 적용을 받으며, 콘텐츠 또한 eDiscovery 검색에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-143">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="14d3b-144">자세한 내용은 [Exchange Online에서 비활성 사서함](inactive-mailboxes-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14d3b-144">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="14d3b-145">사용자가 Yammer에 저장한 파일이 있다면 SharePoint 및 OneDrive의 경우 [해당 섹션](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14d3b-145">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="14d3b-146">제한 사항</span><span class="sxs-lookup"><span data-stu-id="14d3b-146">Limitations</span></span>

<span data-ttu-id="14d3b-147">Yammer 보존 정책은 현재 미리 보기 상태이며 당사는 보존 기능 최적화를 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-147">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="14d3b-148">그 동안 Yammer 커뮤니티 메시지와 비공개 메시지에 대한 보존을 사용할 때는 다음 몇 가지 제한 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-148">In the meantime, here are a few limitations to be aware of when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="14d3b-149">**Yammer 메시지에 대해 좋아요 및 기타 응답이 보존되지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="14d3b-149">**Likes and other reactions are not retained for Yammer messages**.</span></span> <span data-ttu-id="14d3b-150">이모티콘 형태의 다른 사람들의 반응은 보존 정책에 의해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-150">Reactions from others in the form of emoticons aren't supported by retention policies.</span></span>

- <span data-ttu-id="14d3b-151">**Yammer 비공개 메시지** 위치에 대해 **사용자 선택**을 선택하면 게스트 및 사서함이 아닌 사용자가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d3b-151">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="14d3b-152">보존 정책은 이러한 사용자를 위해 설계되지 않았으므로 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="14d3b-152">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="14d3b-153">구성 지침</span><span class="sxs-lookup"><span data-stu-id="14d3b-153">Configuration guidance</span></span>

<span data-ttu-id="14d3b-154">Microsoft 365에서 보존을 처음 구성하는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14d3b-154">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="14d3b-155">Yammer에 대한 보존 정책을 구성할 준비가 되면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14d3b-155">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>

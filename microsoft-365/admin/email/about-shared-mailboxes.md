---
title: 공유 사서함 정보
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함은 여러 사용자가 동일한 사서함에 액세스해야 하는 경우 사용됩니다. 공유 사서함을 만들기 전에 알아야 할 내용을 자세히 알아보세요.
ms.openlocfilehash: 744c4fece24cf1fa5ee7259a0d722ff123ff2664
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926513"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="9fb5b-104">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="9fb5b-104">About shared mailboxes</span></span>

<span data-ttu-id="9fb5b-105">공유 사서함은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소, 리셉션 데스크 또는 여러 사용자에 의해 공유될 수도 있는 기타 기능)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="9fb5b-106">그룹 사서함에 대한 권한이 있는 사용자는 관리자가 해당 사용자에게 권한을 부여한 경우 사서함 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="9fb5b-107">이 기능은 사용자가 "Contoso 지원" 또는 “A 빌딩 리셉션 데스크"에서 전자 메일을 보낼 수 있기 때문에 도움말 및 지원 사서함에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="9fb5b-108">공유 [사서함을](create-a-shared-mailbox.md)만들기 전에 다음을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know:</span></span>

- <span data-ttu-id="9fb5b-109">**라이선스:** 공유 사서함은 라이선스를 할당하지 않고도 최대 50GB의 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="9fb5b-110">그 후에는 추가 데이터를 저장하도록 사서함에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="9fb5b-111">공유 사서함 라이선스에 대한 자세한 내용은 [Exchange Online 제한을 참조하세요.](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)</span><span class="sxs-lookup"><span data-stu-id="9fb5b-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="9fb5b-112">공유 사서함이 저장소 한도에 도달하면 한동안 전자 메일을 받을 수 있지만, 새 전자 메일은 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="9fb5b-113">그런 다음 전자 메일 수신이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="9fb5b-114">사서함에 보낸 사람에게 배달 못 함 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="9fb5b-115">**사용자 권한:** 공유 사서함을 사용하려면 사용자에게 사용 권한(구성원 자격)을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="9fb5b-116">공유 사서함은 조직 내부 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="9fb5b-117">**외부 사용자:** 비즈니스 외부 사용자(예: Gmail 계정이 있는 사용자)에게 공유 사서함에 대한 액세스 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="9fb5b-118">이렇게 하려면 대신 Outlook용 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="9fb5b-119">자세한 내용은 관리 센터에서 [Microsoft 365 그룹 만들기를 참조하세요.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9fb5b-119">To learn more, see [Create a Microsoft 365 group in the admin center](../create-groups/create-groups.md).</span></span>

- <span data-ttu-id="9fb5b-120">**Outlook에서 사용:** 브라우저에서 웹용 Outlook을 사용하여 공유 사서함에 액세스하는 것 외에도 iOS용 Outlook 앱 또는 Android용 Outlook 앱을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="9fb5b-121">자세한 내용은 Outlook 모바일에 공유 [사서함 추가를 참조합니다.](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f)</span><span class="sxs-lookup"><span data-stu-id="9fb5b-121">To learn more, see [Add a shared mailbox to Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f).</span></span> <span data-ttu-id="9fb5b-122">또 다른 옵션은 공유 사서함에 대한 그룹을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="9fb5b-123">자세한 내용은 그룹 [비교를 참조합니다.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9fb5b-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>

- <span data-ttu-id="9fb5b-124">**암호화:** 공유 사서함에서 보낸 전자 메일은 암호화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="9fb5b-125">공유 사서함에는 자체 보안 컨텍스트(사용자 이름/암호)가 있으므로 키를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="9fb5b-126">둘 이상의 사용자가 구성원인 경우 자신의 키로 암호화된 전자 메일을 보내고 받는 경우 다른 구성원은 전자 메일이 암호화된 공개 키에 따라 전자 메일을 읽을 수 있을 수도 있으며 다른 구성원은 전자 메일을 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="9fb5b-127">**사서함 변환:** 사용자 사서함을 공유 사서함으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="9fb5b-128">[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="9fb5b-129">**관리자 역할:** 전역 관리자 또는 Exchange 관리자 역할이 있는 사용자는 공유 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="9fb5b-130">**구독 요구 사항:** 공유 사서함을 만들하려면 전자 메일(Exchange Online 서비스)이 포함된 비즈니스용 Microsoft 365 요금제에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to a Microsoft 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="9fb5b-131">비즈니스용 Microsoft 365 앱 구독에는 전자 메일이 포함되어 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-131">The Microsoft 365 Apps for business subscription doesn't include email.</span></span> <span data-ttu-id="9fb5b-132">Microsoft 365 Business Standard에는 전자 메일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-132">Microsoft 365 Business Standard does include email.</span></span>

- <span data-ttu-id="9fb5b-133">**로그인:** 공유 사서함은 연결된 사용자 계정으로 직접 로그인하기 위한 것이 아니며,</span><span class="sxs-lookup"><span data-stu-id="9fb5b-133">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="9fb5b-134">공유 사서함 계정에 대한 로그인을 항상 차단하고 차단된 것으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-134">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="9fb5b-135">**사용자가 너무 많습니다.** 지정된 사용자가 공유 사서함에 동시 액세스하는 사용자가 너무 많을 경우 간헐적으로 이 사서함에 연결하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-135">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="9fb5b-136">이 경우 사용자 수를 줄이거나 Microsoft 365 그룹 또는 공용 폴더와 같은 다른 워크로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-136">In this case, you can consider reducing the number of the users or using a different workload, such a Microsoft 365 group or Public folder.</span></span>

- <span data-ttu-id="9fb5b-137">**메시지 지우기:** 안타깝게도 사용자가 공유 사서함의 메시지를 삭제하는 것을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-137">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="9fb5b-138">이 경우 공유 사서함 대신 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-138">The only way around this is to create a Microsoft 365 group instead of a shared mailbox.</span></span> <span data-ttu-id="9fb5b-139">Outlook의 그룹은 공유 사서함과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-139">A group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="9fb5b-140">두 가지 비교는 비교 그룹을 [참조합니다.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9fb5b-140">For a comparison of the two, see [Compare groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="9fb5b-141">그룹에 대한 자세한 내용은 [그룹에 대한 자세한 내용을 참조합니다.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)</span><span class="sxs-lookup"><span data-stu-id="9fb5b-141">To learn more about groups, see [Learn more about groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9fb5b-142">관련 문서</span><span class="sxs-lookup"><span data-stu-id="9fb5b-142">Related articles</span></span>

[<span data-ttu-id="9fb5b-143">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="9fb5b-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="9fb5b-144">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="9fb5b-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="9fb5b-145">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="9fb5b-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="9fb5b-146">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="9fb5b-146">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="9fb5b-147">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9fb5b-147">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

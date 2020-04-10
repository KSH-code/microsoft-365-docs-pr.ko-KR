---
title: 공유 사서함 정보
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함은 여러 사용자가 같은 사서함에 액세스 해야 하는 경우에 사용 됩니다. 공유 사서함을 만들기 전에 알아야 할 사항에 대해 알아봅니다.
ms.openlocfilehash: 8e9e4b1ae0235886a9dbb5b39ad4c0f78c27b53f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210543"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="708ca-104">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="708ca-104">About shared mailboxes</span></span>

<span data-ttu-id="708ca-105">공유 사서함은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소, 리셉션 데스크 또는 여러 사용자에 의해 공유될 수도 있는 기타 기능)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="708ca-106">그룹 사서함에 대한 권한이 있는 사용자는 관리자가 해당 사용자에게 권한을 부여한 경우 사서함 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="708ca-107">이 기능은 사용자가 "Contoso Support" 또는 "수신 센터 구축"에서 전자 메일을 보낼 수 있으므로 도움말 및 지원 사서함에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk.</span></span>

<span data-ttu-id="708ca-108">[공유 사서함을 만들기](create-a-shared-mailbox.md)전에 알아야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know.</span></span>

- <span data-ttu-id="708ca-109">**라이선스:** 공유 사서함에는 라이선스를 할당 하지 않고 최대 50GB의 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="708ca-110">그 후에는 추가 데이터를 저장하도록 사서함에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="708ca-111">공유 사서함 라이선스에 대 한 자세한 내용은 [Exchange Online 제한을](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="708ca-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="708ca-112">공유 사서함이 저장소 한도에 도달하면 한동안 전자 메일을 받을 수 있지만, 새 전자 메일은 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="708ca-113">그런 다음 전자 메일 수신이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="708ca-114">사서함에 보낸 사람에게 배달 못 함 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="708ca-115">**사용자 권한:** 공유 사서함을 사용 하려면 사용자에 게 사용 권한 (구성원)을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="708ca-116">공유 사서함은 조직 내부 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="708ca-117">**외부 사용자:** 회사 외부의 사용자 (예: Gmail 계정을 가진 사용자)에 게 공유 사서함에 대 한 액세스 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="708ca-118">이렇게 하려면 대신 Outlook용 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="708ca-119">자세한 내용은 [관리 센터에서 Office 365 그룹 만들기](../create-groups/create-groups.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="708ca-119">To learn more, see [Create an Office 365 group in the admin center](../create-groups/create-groups.md).</span></span>

-  <span data-ttu-id="708ca-120">**Outlook에서 사용:** 브라우저에서 웹에 있는 Outlook을 사용 하 여 공유 사서함에 액세스 하는 것 외에도 iOS 용 Outlook 앱 또는 Android 용 Outlook 사용 앱을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="708ca-121">자세한 내용은 <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook mobile에 공유 사서함을 추가</a>합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="708ca-121">To learn more, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span> <span data-ttu-id="708ca-122">또 다른 옵션으로는 공유 사서함에 대 한 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="708ca-123">자세한 내용은 [그룹 비교](../create-groups/compare-groups.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="708ca-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>  

- <span data-ttu-id="708ca-124">**암호화:** 공유 사서함에서 보낸 전자 메일은 암호화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="708ca-125">공유 사서함에는 키를 할당할 수 없도록 하는 자체 보안 컨텍스트 (사용자 이름/암호)가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="708ca-126">두 명 이상이 구성원 인 경우 해당 사용자가 자신의 키를 사용 하 여 암호화 된 전자 메일을 전송/수신 하는 경우에는 다른 구성원이 메일을 암호화 한 공개 키에 따라 전자 메일이 읽기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="708ca-127">**사서함 변환:** 사용자 사서함을 공유 사서함으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="708ca-128">[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="708ca-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="708ca-129">**관리자 역할:** 전역 관리자 또는 Exchange 관리 역할이 있는 사용자는 공유 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="708ca-130">**구독 요구 사항:** 공유 사서함을 만들려면 전자 메일 (Exchange Online 서비스)을 포함 하는 비즈니스 계획에 대 한 Office 365을 구독 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to an Office 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="708ca-131">Office 365 비즈니스 구독에는 전자 메일이 포함 되지 않습니다. Office 365 Business Premium이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-131">The Office 365 Business subscription doesn't include email; Office 365 Business Premium does.</span></span>

- <span data-ttu-id="708ca-132">**로그인:** 공유 사서함은 연결 된 사용자 계정에의 한 직접 로그인이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-132">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="708ca-133">공유 사서함 계정의 로그인은 항상 차단 하 고 차단 된 상태로 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-133">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="708ca-134">**사용자가 너무 많음:** 공유 사서함에 동시에 액세스 하는 지정 된 사용자가 너무 많으면 일시적으로이 사서함에 연결 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-134">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="708ca-135">이 경우 사용자의 수를 줄이거나 Office 365 그룹 또는 공용 폴더와 같은 다른 작업을 사용 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-135">In this case, you can consider reducing the number of the users or using a different workload, such as Office 365 group or Public folder.</span></span>

- <span data-ttu-id="708ca-136">**메시지 삭제:** 아쉽게도 공유 사서함에서 메시지를 삭제 하는 것을 방지할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-136">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="708ca-137">이 문제를 해결하는 유일한 방법은 공유 사서함 대신 Office 365 그룹을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-137">The only way around this is to create an Office 365 Group instead of a shared mailbox.</span></span> <span data-ttu-id="708ca-138">Outlook의 그룹은 공유 사서함과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="708ca-138">A Group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="708ca-139">이 둘을 비교하려면 [그룹 비교](../create-groups/compare-groups.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="708ca-139">For a comparison of the two, see [Compare Groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="708ca-140">그룹에 대 한 자세한 내용은 [그룹에 대 한 자세한](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx) 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="708ca-140">To learn more about Groups, see [Learn more about Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)</span></span>

## <a name="related-articles"></a><span data-ttu-id="708ca-141">관련 문서</span><span class="sxs-lookup"><span data-stu-id="708ca-141">Related articles</span></span>

[<span data-ttu-id="708ca-142">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="708ca-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="708ca-143">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="708ca-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="708ca-144">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="708ca-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="708ca-145">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="708ca-145">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="708ca-146">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="708ca-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

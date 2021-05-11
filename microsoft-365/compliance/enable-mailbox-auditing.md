---
title: 사서함 감사 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: 사서함 감사 로깅은 기본적으로 Microsoft 365 사서함 감사 또는 사서함 감사라고도 합니다. 즉, 사서함 소유자, 대리인 및 관리자가 수행한 특정 작업이 사서함 감사 로그에 자동으로 기록되며, 사서함에서 수행되는 작업을 검색할 수 있습니다.
ms.openlocfilehash: 859bd0dc633ece887fe11d57068fab4eb1395cdd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311175"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="bbf1e-104">사서함 감사 관리</span><span class="sxs-lookup"><span data-stu-id="bbf1e-104">Manage mailbox auditing</span></span>

<span data-ttu-id="bbf1e-105">2019년 1월부터 Microsoft는 기본적으로 모든 조직에 대해 사서함 감사 로깅을 켜고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all organizations.</span></span> <span data-ttu-id="bbf1e-106">즉, 사서함 소유자, 대리인 및 관리자가 수행한 특정 작업이 자동으로 기록되며 사서함 감사 로그에서 해당 사서함 감사 레코드를 검색할 때 해당 사서함 감사 레코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="bbf1e-107">사서함 감사를 기본적으로 설정하기 전에 조직의 모든 사용자 사서함에 대해 수동으로 사용하도록 설정해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="bbf1e-108">기본적으로 사서함 감사의 몇 가지 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="bbf1e-109">감사는 새 사서함을 만들 때 자동으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="bbf1e-110">새 사용자에 대해 수동으로 사용하도록 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="bbf1e-111">감사되는 사서함 작업은 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="bbf1e-112">미리 정의한 사서함 작업 집합은 각 로그온 유형(관리자, 대리인 및 소유자)에 대해 기본적으로 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="bbf1e-113">Microsoft에서 새 사서함 작업을 릴리스하면 해당 작업이 기본적으로 감사되는 사서함 작업 목록에 자동으로 추가될 수 있습니다(해당 라이선스가 있는 사용자에 따라).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-113">When Microsoft releases a new mailbox action, the action might be automatically added to the list of mailbox actions that are audited by default (subject to the user having the appropriate license).</span></span> <span data-ttu-id="bbf1e-114">즉, 사서함에 대한 새 작업 추가를 모니터링할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="bbf1e-115">조직 전체에서 일관된 사서함 감사 정책이 있습니다(모든 사서함에 대해 동일한 작업을 감사하기 때문에).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
>* <span data-ttu-id="bbf1e-116">기본적으로 사서함 감사 릴리스에 대해 기억해야 할 중요한 점은 사서함 감사를 관리하기 위해 아무 작업도 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="bbf1e-117">그러나 자세한 내용을 알아보고 기본 설정에서 사서함 감사를 사용자 지정하거나 모두 해제하려면 이 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>
>- <span data-ttu-id="bbf1e-118">기본적으로 E5 사용자에 대한 사서함 감사 이벤트만 보안 및 준수 센터의 감사 로그 & 또는 Office 365 관리 활동 API를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-118">By default, only mailbox audit events for E5 users are available in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="bbf1e-119">자세한 내용은 이 항목의 [추가 정보](#more-information) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-119">For more information, see the [More information](#more-information) section in this topic.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="bbf1e-120">사서함 감사 기본 사용이 켜져 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="bbf1e-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="bbf1e-121">조직에 대해 사서함 감사가 기본적으로 설정되어 있는지 확인하기 위해 [PowerShell에서 Exchange Online 실행합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="bbf1e-122">False **값은** 기본적으로 사서함 감사가 조직에 대해 사용하도록 설정되어 있는 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="bbf1e-123">이 설정은 기본적으로 조직 값이 특정 사서함에 대한 사서함 감사 설정을 에 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="bbf1e-124">예를 들어 사서함에 대해 사서함 감사를 사용하지 않도록 설정한 *경우(AuditEnabled* 속성이 **사서함의 경우 False임)** 기본적으로 사서함 감사가 조직에 대해 사용하도록 설정되어 있기 때문에 사서함에 대한 기본 사서함 작업이 계속 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="bbf1e-125">특정 사서함에 대해 사서함 감사를 사용하지 않도록 설정하기 위해 사서함 소유자 및 사서함에 대한 액세스 권한을 위임된 다른 사용자에 대해 사서함 감사 우회를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="bbf1e-126">자세한 내용은 이 항목의 [사서함](#bypass-mailbox-audit-logging) 감사 로깅 무시 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="bbf1e-127">조직에 대해 기본적으로 사서함 감사가 설정되어 있는 경우 영향을 받는 사서함의 *AuditEnabled* 속성은 **False에서 True로** 변경되지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="bbf1e-128">즉, 기본적으로 설정되는 사서함 감사는 사서함의 *AuditEnabled* 속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="bbf1e-129">지원되는 사서함 유형</span><span class="sxs-lookup"><span data-stu-id="bbf1e-129">Supported mailbox types</span></span>

<span data-ttu-id="bbf1e-130">다음 표에는 기본적으로 사서함 감사에서 현재 지원되는 사서함 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="bbf1e-131">**사서함 유형**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-131">**Mailbox type**</span></span>|<span data-ttu-id="bbf1e-132">**지원**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-132">**Supported**</span></span>|<span data-ttu-id="bbf1e-133">**지원되지 않음**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-133">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="bbf1e-134">사용자 사서함</span><span class="sxs-lookup"><span data-stu-id="bbf1e-134">User mailboxes</span></span>|![확인 표시](../media/checkmark.png)||
|<span data-ttu-id="bbf1e-136">공유 사서함</span><span class="sxs-lookup"><span data-stu-id="bbf1e-136">Shared mailboxes</span></span>|![확인 표시](../media/checkmark.png)||
|<span data-ttu-id="bbf1e-138">Microsoft 365 그룹 사서함</span><span class="sxs-lookup"><span data-stu-id="bbf1e-138">Microsoft 365 Group mailboxes</span></span>|![확인 표시](../media/checkmark.png)||
|<span data-ttu-id="bbf1e-140">리소스 사서함</span><span class="sxs-lookup"><span data-stu-id="bbf1e-140">Resource mailboxes</span></span>||![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-142">공용 폴더 사서함</span><span class="sxs-lookup"><span data-stu-id="bbf1e-142">Public folder mailboxes</span></span>||![확인 표시](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="bbf1e-144">로그온 유형 및 사서함 작업</span><span class="sxs-lookup"><span data-stu-id="bbf1e-144">Logon types and mailbox actions</span></span>

<span data-ttu-id="bbf1e-145">로그온 유형 사서함에 대해 감사된 작업을 수행한 사용자를 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-145">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="bbf1e-146">다음 목록에는 사서함 감사 로깅에 사용되는 로그온 유형이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-146">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="bbf1e-147">**소유자:** 사서함 소유자(사서함과 연결된 계정)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-147">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="bbf1e-148">**대리자**:</span><span class="sxs-lookup"><span data-stu-id="bbf1e-148">**Delegate**:</span></span>

  - <span data-ttu-id="bbf1e-149">다른 사서함에 대한 SendAs, SendOnBehalf 또는 FullAccess 권한이 할당된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-149">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="bbf1e-150">사용자의 사서함에 대한 FullAccess 권한이 할당된 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-150">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="bbf1e-151">**관리자**:</span><span class="sxs-lookup"><span data-stu-id="bbf1e-151">**Admin**:</span></span>

  - <span data-ttu-id="bbf1e-152">사서함은 다음 Microsoft eDiscovery 도구 중 하나를 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-152">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="bbf1e-153">준수 센터의 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="bbf1e-153">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="bbf1e-154">eDiscovery 또는 Advanced eDiscovery 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-154">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="bbf1e-155">In-Place eDiscovery를 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-155">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="bbf1e-156">MAPI 편집기에서 사서함에 Microsoft Exchange Server 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-156">The mailbox is accessed by using the Microsoft Exchange Server MAPI Editor.</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="bbf1e-157">사용자 사서함 및 공유 사서함에 대한 사서함 작업</span><span class="sxs-lookup"><span data-stu-id="bbf1e-157">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="bbf1e-158">다음 표에서는 사용자 사서함 및 공유 사서함에 대한 사서함 감사 로깅에서 사용할 수 있는 사서함 작업에 대해 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-158">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="bbf1e-159">확인 표시(</span><span class="sxs-lookup"><span data-stu-id="bbf1e-159">A check mark (</span></span> ![확인 표시](../media/checkmark.png)<span data-ttu-id="bbf1e-161">)는 로그온 유형에 대해 사서함 작업을 기록할 수 있습니다(모든 로그온 유형에 대해 일부 작업을 사용할 수 있는 것은 아 아함).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-161">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="bbf1e-162">확인 표시 다음에 추가()는 사서함 작업이 로그온 유형에 대해 기본적으로 기록되어 있는 <sup>\*</sup> 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="bbf1e-163">사서함에 대한 모든 액세스 권한이 있는 관리자는 대리인으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-163">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="bbf1e-164">**사서함 작업**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-164">**Mailbox action**</span></span>|<span data-ttu-id="bbf1e-165">**설명**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-165">**Description**</span></span>|<span data-ttu-id="bbf1e-166">**Admin**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-166">**Admin**</span></span>|<span data-ttu-id="bbf1e-167">**대리인**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-167">**Delegate**</span></span>|<span data-ttu-id="bbf1e-168">**소유자**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-168">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="bbf1e-169">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-169">**AddFolderPermissions**</span></span>|<span data-ttu-id="bbf1e-170">**참고:** 이 값은 사서함 작업으로 수락되어도 이미 **UpdateFolderPermissions** 동작에 포함되어 있으며 별도로 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-170">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="bbf1e-171">즉, 이 값을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-171">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="bbf1e-172">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-172">**ApplyRecord**</span></span>|<span data-ttu-id="bbf1e-173">항목에 레코드로 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-173">An item is labeled as a record.</span></span>|<span data-ttu-id="bbf1e-174">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-174">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-175">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-175">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-176">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-176">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-177">**복사**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-177">**Copy**</span></span>|<span data-ttu-id="bbf1e-178">메시지가 다른 폴더에 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-178">A message was copied to another folder.</span></span>|![확인 표시](../media/checkmark.png)|||
|<span data-ttu-id="bbf1e-180">**만들기**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-180">**Create**</span></span>|<span data-ttu-id="bbf1e-181">항목이 사서함의 일정, 연락처, 메모 또는 작업 폴더에 만들어졌습니다(예: 새 모임 요청이 만들어지기).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-181">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="bbf1e-182">메시지 작성, 보내기 또는 받기는 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-182">Creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="bbf1e-183">사서함 폴더 만들기도 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-183">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="bbf1e-184">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-184">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-185">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-185">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-187">**기본값**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-187">**Default**</span></span>||![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-191">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-191">**FolderBind**</span></span>|<span data-ttu-id="bbf1e-p114">사서함 폴더에 액세스했습니다. 관리자 또는 대리인이 사서함을 열 때에도 작업이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-p114">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox. </span></span><br/><br/> <span data-ttu-id="bbf1e-194">**참고:** 대리인이 수행한 폴더 바인딩 작업에 대한 감사 레코드가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-194">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="bbf1e-195">24시간 내에 개별 폴더 액세스에 대해 하나의 감사 레코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-195">One audit record is generated for individual folder access within a 24-hour period.</span></span>|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|<span data-ttu-id="bbf1e-198">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-198">**HardDelete**</span></span>|<span data-ttu-id="bbf1e-199">메시지가 복구 가능한 항목 폴더에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-199">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="bbf1e-200">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-200">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-201">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-201">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-202">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-202">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-203">**MailItemsAccessed**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-203">**MailItemsAccessed**</span></span>|<span data-ttu-id="bbf1e-204">메일 데이터는 메일 프로토콜 및 클라이언트에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-204">Mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="bbf1e-205">이 값은 E5 또는 E5 준수 추가 기능 구독 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-205">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="bbf1e-206">자세한 내용은 고급 감사 [설정 을 참조하세요. ](set-up-advanced-audit.md)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-206">For more information, see [Set up Advanced Audit ](set-up-advanced-audit.md).</span></span>|<span data-ttu-id="bbf1e-207">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-207">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-208">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-208">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-209">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-209">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-210">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-210">**MailboxLogin**</span></span>|<span data-ttu-id="bbf1e-211">사용자가 사서함에 로그인한 경우</span><span class="sxs-lookup"><span data-stu-id="bbf1e-211">The user signed into their mailbox.</span></span> |||![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-213">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-213">**MessageBind**</span></span>|<span data-ttu-id="bbf1e-214">미리 보기 창에서 메시지를 보거나 관리자가 연 경우. **참고:** 이 값은 사서함 작업으로 수락되어도 이러한 작업은 더 이상 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-214">A message was viewed in the preview pane or opened by an admin. **Note**: Although this value is accepted as a mailbox action, these actions are no longer logged.</span></span>|![확인 표시](../media/checkmark.png)|||
|<span data-ttu-id="bbf1e-216">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-216">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="bbf1e-217">**참고:** 이 값은 사서함 작업으로 수락되어도 이미 **UpdateFolderPermissions** 동작에 포함되어 있으며 별도로 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-217">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="bbf1e-218">즉, 이 값을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-218">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="bbf1e-219">**이동**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-219">**Move**</span></span>|<span data-ttu-id="bbf1e-220">메시지가 다른 폴더로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-220">A message was moved to another folder.</span></span>|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-224">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-224">**MoveToDeletedItems**</span></span>|<span data-ttu-id="bbf1e-225">메시지가 삭제되어 지운 편지함 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-225">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="bbf1e-226">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-226">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-227">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-227">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-228">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-228">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-229">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-229">**RecordDelete**</span></span>|<span data-ttu-id="bbf1e-230">레코드로 레이블이 지정되는 항목이 소프트 삭제되었습니다(복구 가능한 항목 폴더로 이동).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-230">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="bbf1e-231">레코드로 레이블이 붙은 항목은 영구적으로 삭제할 수 없습니다(복구 가능한 항목 폴더에서 제거).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-231">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-235">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-235">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="bbf1e-236">**참고:** 이 값은 사서함 작업으로 수락되어도 이미 **UpdateFolderPermissions** 동작에 포함되어 있으며 별도로 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-236">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="bbf1e-237">즉, 이 값을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-237">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="bbf1e-238">**보내기**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-238">**Send**</span></span>|<span data-ttu-id="bbf1e-239">사용자는 전자 메일 메시지를 보내거나 전자 메일 메시지에 답장하거나 전자 메일 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-239">The user sends an email message, replies to an email message, or forwards an email message.</span></span> <span data-ttu-id="bbf1e-240">이 값은 E5 또는 E5 준수 추가 기능 구독 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-240">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="bbf1e-241">자세한 내용은 [사용자에 대한 고급 감사 설정 을 참조하세요.](set-up-advanced-audit.md)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-241">For more information, see [Set up Advanced Audit for users](set-up-advanced-audit.md).</span></span>|<span data-ttu-id="bbf1e-242">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-242">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-243">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-243">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-244">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-244">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-245">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-245">**SendAs**</span></span>|<span data-ttu-id="bbf1e-p121">메시지가 SendAs 권한을 사용하여 전송되었습니다. 즉 사서함 소유자가 보낸 것처럼 보이도록 하여 다른 사용자가 메시지를 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-p121">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="bbf1e-248">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-248">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-249">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-249">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="bbf1e-250">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-250">**SendOnBehalf**</span></span>|<span data-ttu-id="bbf1e-p122">메시지가 SendOnBehalf 권한을 사용하여 전송되었습니다. 즉 다른 사용자가 사서함 소유자 대신에 메시지를 보냈습니다. 받는 사람은 메시지를 대신 보낸 사용자와 해당 메시지를 실제로 보낸 사용자를 메시지에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-p122">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="bbf1e-254">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-254">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-255">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-255">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="bbf1e-256">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-256">**SoftDelete**</span></span>|<span data-ttu-id="bbf1e-p123">메시지가 지운 편지함 폴더에서 삭제되어가 영구적으로 삭제되었습니다. 소프트 삭제된 항목이 복구 가능한 항목 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-p123">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="bbf1e-259">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-259">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-260">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-260">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-261">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-261">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-262">**업데이트**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-262">**Update**</span></span>|<span data-ttu-id="bbf1e-263">메시지 또는 해당 속성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-263">A message or its properties was changed.</span></span>|<span data-ttu-id="bbf1e-264">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-264">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-265">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-265">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-266">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-266">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-267">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-267">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="bbf1e-268">일정 위임이 사서함에 할당된 경우</span><span class="sxs-lookup"><span data-stu-id="bbf1e-268">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="bbf1e-269">일정 위임 기능을 사용하여 같은 조직의 다른 사용자가 사서함 소유자의 일정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-269">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="bbf1e-270">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-270">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||<span data-ttu-id="bbf1e-271">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-271">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-272">**UpdateComplianceTag**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-272">**UpdateComplianceTag**</span></span>|<span data-ttu-id="bbf1e-273">다른 보존 레이블이 메일 항목에 적용됩니다(항목에 보존 레이블을 하나만 할당할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-273">A different retention label is applied to a mail item (an item can only have one retention label assigned to it).</span></span>|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|
|<span data-ttu-id="bbf1e-277">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-277">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="bbf1e-278">폴더 권한이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-278">A folder permission was changed.</span></span> <span data-ttu-id="bbf1e-279">폴더 사용 권한은 사서함의 폴더와 해당 폴더에 있는 메시지에 액세스할 수 있는 조직의 사용자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-279">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="bbf1e-280">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-280">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-281">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-281">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-282">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-282">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-283">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-283">**UpdateInboxRules**</span></span>|<span data-ttu-id="bbf1e-284">받은 편지함 규칙이 추가, 제거 또는 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-284">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="bbf1e-285">받은 편지함 규칙은 지정된 조건에 따라 사용자의 받은 편지함에서 메시지를 처리하고 규칙 조건이 충족될 때 지정된 폴더로 메시지를 이동하거나 메시지를 삭제하는 등의 작업을 수행하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-285">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="bbf1e-286">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-286">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-287">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-287">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-288">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-288">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="bbf1e-289">조직에서 기본적으로 사서함 감사를 사용하도록 설정하기 전에 로그온 유형에 대해 감사하도록 사서함 작업을 사용자 지정한 경우 사용자 지정된 설정은 사서함에 보존되고 이 섹션에 설명된 기본 사서함 작업으로 덮어 사용되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="bbf1e-289">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="bbf1e-290">감사 사서함 작업을 기본값으로 되버리면(어떤 경우든 수행할 수 [](#restore-the-default-mailbox-actions) 있습니다) 이 항목의 뒤에서 기본 사서함 작업 복원 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-290">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a><span data-ttu-id="bbf1e-291">그룹 사서함에 Microsoft 365 사서함 작업</span><span class="sxs-lookup"><span data-stu-id="bbf1e-291">Mailbox actions for Microsoft 365 Group mailboxes</span></span>

<span data-ttu-id="bbf1e-292">기본적으로 사서함 감사를 수행하면 사서함 감사 로깅이 Microsoft 365 그룹 사서함으로 이동되지만 로깅되는 항목은 사용자 지정할 수 없습니다(로그온 유형에 대해 기록되는 사서함 작업은 추가하거나 제거할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-292">Mailbox auditing on by default brings mailbox audit logging to Microsoft 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="bbf1e-293">다음 표에서는 각 로그온 유형에 대해 Microsoft 365 사서함에 기본적으로 기록되는 사서함 작업에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-293">The following table describes the mailbox actions that are logged by default on Microsoft 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="bbf1e-294">그룹 사서함에 대한 모든 액세스 권한이 Microsoft 365 관리자는 대리인으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-294">Remember, an admin with Full Access permission to a Microsoft 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="bbf1e-295">**사서함 작업**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-295">**Mailbox action**</span></span>|<span data-ttu-id="bbf1e-296">**설명**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-296">**Description**</span></span>|<span data-ttu-id="bbf1e-297">**Admin**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-297">**Admin**</span></span>|<span data-ttu-id="bbf1e-298">**대리인**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-298">**Delegate**</span></span>|<span data-ttu-id="bbf1e-299">**소유자**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-299">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="bbf1e-300">**만들기**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-300">**Create**</span></span>|<span data-ttu-id="bbf1e-301">일정 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="bbf1e-301">Creation of a calendar Item.</span></span> <span data-ttu-id="bbf1e-302">메시지 작성, 보내기 또는 받기는 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-302">Creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="bbf1e-303">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-303">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-304">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-304">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="bbf1e-305">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-305">**HardDelete**</span></span>|<span data-ttu-id="bbf1e-306">메시지가 복구 가능한 항목 폴더에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-306">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="bbf1e-307">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-307">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-308">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-308">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-309">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-309">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-310">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-310">**MoveToDeletedItems**</span></span>|<span data-ttu-id="bbf1e-311">메시지가 삭제되어 지운 편지함 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-311">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="bbf1e-312">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-312">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-313">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-313">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-314">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-314">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-315">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-315">**SendAs**</span></span>|<span data-ttu-id="bbf1e-316">SendAs 권한을 사용하여 메시지가 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-316">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="bbf1e-317">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-317">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-318">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-318">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="bbf1e-319">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-319">**SendOnBehalf**</span></span>|<span data-ttu-id="bbf1e-320">SendOnBehalf 권한을 사용하여 메시지가 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-320">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="bbf1e-321">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-321">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-322">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-322">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="bbf1e-323">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-323">**SoftDelete**</span></span>|<span data-ttu-id="bbf1e-p129">메시지가 지운 편지함 폴더에서 삭제되어가 영구적으로 삭제되었습니다. 소프트 삭제된 항목이 복구 가능한 항목 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-p129">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="bbf1e-326">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-326">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-327">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-327">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-328">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-328">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="bbf1e-329">**업데이트**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-329">**Update**</span></span>|<span data-ttu-id="bbf1e-330">메시지 또는 해당 속성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-330">A message or its properties was changed.</span></span>|<span data-ttu-id="bbf1e-331">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-331">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-332">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-332">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="bbf1e-333">![확인 표시](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bbf1e-333">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="bbf1e-334">각 로그온 유형에 대해 기본 사서함 작업이 기록되고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="bbf1e-334">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="bbf1e-335">기본적으로 사서함 감사는 모든 사서함에 새 *DefaultAuditSet* 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-335">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="bbf1e-336">이 속성의 값은 기본 사서함 작업(Microsoft에서 관리)이 사서함에 대해 감사되고 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-336">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="bbf1e-337">사용자 사서함 또는 공유 사서함의 값을 표시하기 위해 사서함의 이름, 별칭, 전자 메일 주소 또는 사용자 계정 \<MailboxIdentity\> 이름(사용자 이름)으로 바꾸고 PowerShell에서 Exchange Online 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-337">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="bbf1e-338">그룹 사서함에 값을 Microsoft 365 공유 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 \<MailboxIdentity\> PowerShell에서 Exchange Online 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-338">To display the value on Microsoft 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="bbf1e-339">값은 `Admin, Delegate, Owner` 다음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-339">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="bbf1e-340">세 가지 로그온 유형 모두에 대한 기본 사서함 작업이 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-340">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="bbf1e-341">이 값은 그룹 사서함에 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-341">This is the only value you'll see on Microsoft 365 Group mailboxes.</span></span>

- <span data-ttu-id="bbf1e-342">관리자가 *사용자 사서함* 또는 공유 사서함의 로그온 유형에 대해 감사된 사서함 작업을 변경하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-342">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="bbf1e-343">이 상태는 조직에서 사서함 감사를 기본적으로 처음 설정한 후의 기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-343">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="bbf1e-344">**관리자가 Set-Mailbox** cmdlet에서 *AuditAdmin,* *AuditDelegate* 또는 *AuditOwner* 매개 변수를 사용하여 로그온 유형에 대해 감사되는 사서함 작업을 변경한 경우 속성 값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-344">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="bbf1e-345">예를 들어 사용자 사서함 또는 공유 사서함의 `Owner` *DefaultAuditSet* 속성 값은 다음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-345">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="bbf1e-346">사서함 소유자에 대한 기본 사서함 작업이 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-346">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="bbf1e-347">및 로그온 유형에 대해 감사된 사서함 작업이 기본 `Delegate` `Admin` 작업에서 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-347">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="bbf1e-348">*DefaultAuditSet* 속성의 값을 비워 두면 사용자 사서함이나 공유 사서함에서 세 가지 로그온 유형에 대한 사서함 작업이 모두 변경된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-348">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="bbf1e-349">자세한 내용은 이 항목의 [기본적으로](#change-or-restore-mailbox-actions-logged-by-default) 기록되는 사서함 작업 변경 또는 복원 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-349">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="bbf1e-350">사서함에 로그온하는 사서함 작업 표시</span><span class="sxs-lookup"><span data-stu-id="bbf1e-350">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="bbf1e-351">현재 사용자 사서함 또는 공유 사서함에 로그온 중인 사서함 작업을 확인한 후 사서함의 이름, 별칭, 전자 메일 주소 또는 사용자 계정 이름(사용자 이름)으로 바꾸고 Exchange Online PowerShell에서 다음 명령 중 \<MailboxIdentity\> 하나 이상을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-351">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="bbf1e-352">그룹 사서함에 대한 다음 `-GroupMailbox` **Get-Mailbox** 명령에 Microsoft 365 수 있는 경우 반환되는 값을 믿지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-352">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Microsoft 365 Group mailboxes, don't believe the values that are returned.</span></span> <span data-ttu-id="bbf1e-353">Microsoft 365 그룹 사서함에 대해 감사되는 기본 및 정적 사서함 작업은 이 항목의 앞부분에 있는 Microsoft 365 [그룹](#mailbox-actions-for-microsoft-365-group-mailboxes) 사서함에 대한 사서함 작업 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-353">The default and static mailbox actions that are audited for Microsoft 365 Group mailboxes are described in the [Mailbox actions for Microsoft 365 Group mailboxes](#mailbox-actions-for-microsoft-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="bbf1e-354">소유자 작업</span><span class="sxs-lookup"><span data-stu-id="bbf1e-354">Owner actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="bbf1e-355">위임 작업</span><span class="sxs-lookup"><span data-stu-id="bbf1e-355">Delegate actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="bbf1e-356">관리자 작업</span><span class="sxs-lookup"><span data-stu-id="bbf1e-356">Admin actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="bbf1e-357">기본적으로 로깅되는 사서함 작업 변경 또는 복원</span><span class="sxs-lookup"><span data-stu-id="bbf1e-357">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="bbf1e-358">앞서 설명한 것 처럼 기본적으로 사서함 감사를 사용할 수 있는 주요 이점 중 하나는 감사되는 사서함 작업을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-358">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="bbf1e-359">Microsoft는 이 작업을 자동으로 수행하며, 기본적으로 감사할 새 사서함 작업이 릴리스될 때 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-359">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="bbf1e-360">그러나 조직에서 사용자 사서함 및 공유 사서함에 대해 다른 사서함 작업 집합을 감사해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-360">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="bbf1e-361">이 섹션의 절차에서는 각 로그온 유형에 대해 감사되는 사서함 작업을 변경하는 방법과 Microsoft에서 관리하는 기본 작업으로 되돌아가는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-361">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbf1e-362">다음 절차에 따라 사용자 사서함 또는 공유 사서함에 기록되는 사서함 작업을 사용자 지정하는 경우 Microsoft에서 릴리스한 새 기본 사서함 작업은 해당 사서함에 대해 자동으로 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-362">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="bbf1e-363">사용자 지정된 작업 목록에 새 사서함 작업을 수동으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-363">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="bbf1e-364">사서함 작업을 감사로 변경</span><span class="sxs-lookup"><span data-stu-id="bbf1e-364">Change the mailbox actions to audit</span></span>

<span data-ttu-id="bbf1e-365">**Set-Mailbox** cmdlet에서 *AuditAdmin,* *AuditDelegate* 또는 *AuditOwner* 매개 변수를 사용하여 사용자 사서함 및 공유 사서함에 대해 감사되는 사서함 작업을 변경할 수 있습니다(Microsoft 365 그룹 사서함에 대해 감사된 작업은 사용자 지정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="bbf1e-365">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Microsoft 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="bbf1e-366">다음 두 가지 방법을 사용하여 사서함 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-366">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="bbf1e-367">*다음* 구문을 사용하여 기존 사서함 작업을 대체(덮어 덮어) `action1,action2,...actionN` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-367">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="bbf1e-368">*또는 구문을* 사용하여 다른 기존 값에 영향을 주지 않고 사서함 작업을 추가하거나 `@{Add="action1","action2",..."actionN"}` `@{Remove="action1","action2",..."actionN"}` 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-368">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="bbf1e-369">이 예에서는 SoftDelete 및 HardDelete로 기본 작업을 덮어어 "Gabriela Laureano"라는 사서함에 대한 관리자 사서함 작업을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-369">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="bbf1e-370">이 예에서는 사서함 서버의 사서함에 MailboxLogin 소유자 작업을 laura@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-370">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="bbf1e-371">이 예에서는 팀 토론 사서함에 대한 MoveToDeletedItems 대리인 작업을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-371">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="bbf1e-372">사용하는 방법에 관계없이 사용자 사서함 또는 공유 사서함에 대해 감사되는 사서함 작업을 사용자 지정하면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-372">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="bbf1e-373">사용자 지정한 로그온 유형의 경우 감사된 사서함 작업은 Microsoft에서 더 이상 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-373">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="bbf1e-374">사용자 지정한 로그온 유형은 앞서 설명한 사서함의 *DefaultAuditSet* 속성 값에 더 이상 [표시되지 않습니다.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-374">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="bbf1e-375">기본 사서함 작업 복원</span><span class="sxs-lookup"><span data-stu-id="bbf1e-375">Restore the default mailbox actions</span></span>

<span data-ttu-id="bbf1e-376">사용자 사서함 또는 공유 사서함에서 감사되는 사서함 작업을 사용자 지정한 경우 다음 구문을 사용하여 하나 또는 모든 로그온 유형에 대한 기본 사서함 작업을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-376">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="bbf1e-377">*여러 DefaultAuditSet* 값을 각기 콤보로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-377">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="bbf1e-378">**참고:** 다음 절차는 Microsoft 365 그룹 사서함에 적용되지 않습니다(여기에 설명된 기본 작업으로 [제한).](#mailbox-actions-for-microsoft-365-group-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-378">**Note**: The following procedures don't apply to Microsoft 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-microsoft-365-group-mailboxes)).</span></span>

<span data-ttu-id="bbf1e-379">이 예에서는 사서함 서버의 모든 로그온 유형에 대해 감사되는 기본 사서함 작업을 mark@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-379">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="bbf1e-380">이 예에서는 사서함 서버의 관리자 로그온 유형에 대한 기본 감사된 사서함 작업을 chris@contoso.onmicrosoft.com 대리인 및 소유자 로그온 유형에 대해 사용자 지정된 감사된 사서함 작업을 그대로 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-380">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="bbf1e-381">로그온 유형에 대해 기본 감사 사서함 작업을 복원하면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-381">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="bbf1e-382">현재 사서함 작업 목록은 로그온 유형에 대한 기본 사서함 작업으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-382">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="bbf1e-383">Microsoft에서 릴리스한 모든 새 사서함 작업은 로그온 유형에 대한 감사된 작업 목록에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-383">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="bbf1e-384">사서함의 *DefaultAuditSet* 속성 값은 복원된 로그온 유형을 포함하기 위해 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-384">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="bbf1e-385">조직에 대해 사서함 감사를 기본적으로 끄기</span><span class="sxs-lookup"><span data-stu-id="bbf1e-385">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="bbf1e-386">PowerShell에서 다음 명령을 실행하여 전체 조직에 대해 기본적으로 사서함 감사를 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-386">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="bbf1e-387">기본적으로 사서함 감사를 끄면 다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-387">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="bbf1e-388">조직에서 사서함 감사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-388">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="bbf1e-389">기본적으로 사서함 감사를 사용하지 않도록 설정한 시간부터 사서함에서 감사를 사용하도록 설정한 경우에도 사서함 작업이 감사되지 않습니다(사서함의 *AuditEnabled* 속성이 **True임).**</span><span class="sxs-lookup"><span data-stu-id="bbf1e-389">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="bbf1e-390">새 사서함에 대해 사서함 감사를 사용하도록 설정하지 않은 경우 새 사서함이나 기존 사서함의 *AuditEnabled* 속성을 **True로** 설정하면 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-390">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="bbf1e-391">**Set-MailboxAuditBypassAssociation cmdlet을** 사용하여 구성한 사서함 감사 우회 연결 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-391">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="bbf1e-392">기존 사서함 감사 레코드는 레코드에 대한 감사 로그 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-392">Existing mailbox audit records are retained until the audit log age limit for the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="bbf1e-393">기본적으로 사서함 감사 켜기</span><span class="sxs-lookup"><span data-stu-id="bbf1e-393">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="bbf1e-394">조직에 대한 사서함 감사를 다시 설정하기 위해 PowerShell에서 Exchange Online 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-394">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="bbf1e-395">사서함 감사 로깅 우회</span><span class="sxs-lookup"><span data-stu-id="bbf1e-395">Bypass mailbox audit logging</span></span>

<span data-ttu-id="bbf1e-396">현재 조직의 사서함 감사 기본 사용이 켜져 있으면 특정 사서함에 대한 사서함 감사를 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-396">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="bbf1e-397">예를 들어 *AuditEnabled* 사서함 속성을 **False로** 설정하면 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-397">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="bbf1e-398">그러나 Exchange Online PowerShell에서 **Set-MailboxAuditBypassAssociation** cmdlet을 사용하여 작업이 수행되는 위치와 관계없이 지정된 사용자의 모든 사서함 작업이 기록되지 않도록 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="bbf1e-398">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="bbf1e-399">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-399">For example:</span></span>

- <span data-ttu-id="bbf1e-400">무시된 사용자가 수행한 사서함 소유자 작업은 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-400">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="bbf1e-401">다른 사용자의 사서함(공유 사서함 포함)에서 무시된 사용자가 수행한 위임 작업은 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-401">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="bbf1e-402">무시된 사용자가 수행한 관리 작업은 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-402">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="bbf1e-403">특정 사용자에 대한 사서함 감사 로깅을 무시하기 위해 사용자의 이름, 전자 메일 주소, 별칭 또는 사용자 계정 이름(사용자 이름)으로 바꾸고 다음 명령을 \<MailboxIdentity\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-403">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="bbf1e-404">지정된 사용자에 대해 감사가 우회되었는지 확인하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-404">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="bbf1e-405">True **값으로** 설정하면 사용자에 대해 사서함 감사 로깅이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-405">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="bbf1e-406">추가 정보</span><span class="sxs-lookup"><span data-stu-id="bbf1e-406">More information</span></span>

- <span data-ttu-id="bbf1e-407">기본적으로 사서함 감사 로그온은 모든 조직에 대해 사용하도록 설정되어 있습니다. 그러나 E5 라이선스가 있는 사용자만 보안 & 준수 센터 또는 Office 365 관리 활동 [API를](/office/office-365-management-api/office-365-management-activity-api-reference) 통해 감사 로그 검색의 사서함 감사 로그 이벤트를 **반환합니다.** [](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-407">Although mailbox audit logging on by default is enabled for all organizations, only users with E5 licenses will return mailbox audit log events in [audit log searches in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) or via the [Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference) **by default**.</span></span>

  <span data-ttu-id="bbf1e-408">E5 라이선스가 없는 사용자의 사서함 감사 로그 항목을 검색하려면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-408">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="bbf1e-409">개별 사서함에 대해 사서함 감사를 수동으로 사용하도록 설정(명령을 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` 실행합니다.)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-409">Manually enable mailbox auditing on individual mailboxes (run the command, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`).</span></span> <span data-ttu-id="bbf1e-410">이렇게 한 후 보안 및 준수 센터에서 감사 로그 검색을 & 관리 활동 API를 통해 Office 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-410">After you do this, you can use audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="bbf1e-411">사서함 감사가 이미 사서함에서 사용하도록 설정된 것으로 보이지만 검색에서 결과가 반환되지 않았다면 _AuditEnabled_ 매개 변수의 값을 로 변경한 다음 로 `$false` 다시 `$true` 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-411">If mailbox auditing already appears to be enabled on the mailbox, but your searches return no results, change the value of the _AuditEnabled_ parameter to `$false` and then back to `$true`.</span></span>
  
  - <span data-ttu-id="bbf1e-412">PowerShell에서 다음 cmdlet을 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-412">Use the following cmdlets in Exchange Online PowerShell:</span></span>

    - <span data-ttu-id="bbf1e-413">[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) - 특정 사용자에 대한 사서함 감사 로그를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-413">[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>

    - <span data-ttu-id="bbf1e-414">[New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) - 특정 사용자에 대한 사서함 감사 로그를 검색하고 지정된 받는 사람에게 전자 메일을 통해 결과를 전송하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-414">[New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="bbf1e-415">EAC(Exchange 관리 센터)를 사용하여 Exchange Online 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-415">Use the Exchange admin center (EAC) in Exchange Online to do the following actions:</span></span>

    - [<span data-ttu-id="bbf1e-416">사서함 감사 로그 내보내기</span><span class="sxs-lookup"><span data-stu-id="bbf1e-416">Export mailbox audit logs</span></span>](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [<span data-ttu-id="bbf1e-417">비소유자 사서함 액세스 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="bbf1e-417">Run a non-owner mailbox access report</span></span>](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="bbf1e-418">기본적으로 사서함 감사 로그 레코드는 삭제되기 90일 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-418">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="bbf1e-419">PowerShell의 **Set-Mailbox** cmdlet에서 *AuditLogAgeLimit* 매개 변수를 사용하여 감사 로그 레코드의 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-419">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="bbf1e-420">그러나 이 값을 늘리면 감사 로그에서 90일보다 오래된 이벤트를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-420">However, increasing this value doesn't allow you to search for events that are older than 90 days in the audit log.</span></span>

  <span data-ttu-id="bbf1e-421">사용 시간 제한을 늘리는 경우 Exchange Online PowerShell에서 [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet을 사용하여 사용자의 사서함 감사 로그에서 90일이 지난 레코드를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-421">If you increase the age limit, you need to use the [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="bbf1e-422">기본적으로 조직에 대해 사서함 감사를 설정하기 전에 사서함의 *AuditLogAgeLimit* 속성을 변경한 경우 사서함의 기존 감사 로그 사용 시간 제한은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-422">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="bbf1e-423">즉, 기본적으로 설정되는 사서함 감사는 사서함 감사 레코드의 현재 사용 시간 제한에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-423">In other words, mailbox auditing on by default doesn't affect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="bbf1e-424">그룹 사서함의 *AuditLogAgeLimit* Microsoft 365 Set-Mailbox 명령에 스위치를 `-GroupMailbox` **포함해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-424">To change the *AuditLogAgeLimit* value on a Microsoft 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="bbf1e-425">사서함 감사 로그 레코드는 각 사용자 사서함의 복구 가능한 항목 폴더에 있는 하위 *폴더(Audits)에* 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-425">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="bbf1e-426">사서함 감사 레코드 및 복구 가능한 항목 폴더에 대해 다음에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-426">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="bbf1e-427">사서함 감사 레코드는 기본적으로 30GB(경고 할당량은 20GB)인 복구 가능한 항목 폴더의 저장소 할당량에 대해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-427">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30 GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="bbf1e-428">저장소 할당량은 다음 경우 자동으로 100GB(90GB 경고 할당량 사용)로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-428">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="bbf1e-429">사서함에 보류가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-429">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="bbf1e-430">사서함은 준수 센터의 보존 정책에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-430">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="bbf1e-431">사서함 감사 레코드는 복구 가능한 항목 폴더의 폴더 [제한에 계산됩니다.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)</span><span class="sxs-lookup"><span data-stu-id="bbf1e-431">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="bbf1e-432">감사 하위폴더에 최대 300만 개 항목(감사 레코드)을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-432">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bbf1e-433">기본적으로 사서함 감사가 저장소 할당량 또는 복구 가능한 항목 폴더의 폴더 제한에 영향을 줄 가능성은 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-433">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="bbf1e-434">PowerShell에서 Exchange Online 명령을 실행하여 복구 가능한 항목 폴더의 감사 하위 폴더에 있는 항목의 크기와 수를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-434">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="bbf1e-435">복구 가능한 항목 폴더의 감사 로그 레코드에 직접 액세스할 수 없습니다. 대신 **Search-MailboxAuditLog** cmdlet을 사용하거나 감사 로그를 검색하여 사서함 감사 레코드를 찾아 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-435">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="bbf1e-436">사서함이 보류 중이거나 준수 센터의 보존 정책에 할당된 경우 감사 로그 레코드는 사서함의 *AuditLogAgeLimit* 속성(기본적으로 90일)으로 정의된 기간 동안 계속 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-436">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="bbf1e-437">보류된 사서함에 대해 감사 로그 레코드를 더 오래 유지하려면 *사서함의 AuditLogAgeLimit* 값을 증가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-437">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>

- <span data-ttu-id="bbf1e-438">다중 지리적 환경에서는 지역 횡단 사서함 감사가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-438">In a multi-geo environment, cross-geo mailbox auditing is not supported.</span></span> <span data-ttu-id="bbf1e-439">예를 들어 사용자가 다른 지리적 위치에서 공유 사서함에 액세스할 수 있는 권한을 할당받더라도 그 사용자가 수행한 사서함 작업이 공유 사서함의 사서함 감사 로그에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf1e-439">For example, if a user is assigned permissions to access a shared mailbox in a different geo location, mailbox actions performed by that user are not logged in the mailbox audit log of the shared mailbox.</span></span>
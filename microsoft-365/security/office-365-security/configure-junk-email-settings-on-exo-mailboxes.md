---
title: Exchange Online 사서함에 대한 정크 메일 설정 구성
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 사서함에서 정크 메일 설정을 구성하는 Exchange Online 있습니다. 이러한 설정 중 상당수는 웹에서 Outlook Outlook 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a401321645530d3d66ebcccd6b8aea27ce21d6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624804"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="674b5-104">Exchange Online 사서함에 대한 정크 메일 설정 구성</span><span class="sxs-lookup"><span data-stu-id="674b5-104">Configure junk email settings on Exchange Online mailboxes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="674b5-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="674b5-105">**Applies to**</span></span>
- [<span data-ttu-id="674b5-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="674b5-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="674b5-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="674b5-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="674b5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="674b5-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="674b5-109">조직의 Microsoft 365 사서함이 있는 Exchange Online 조직에서는 EOP(스팸 방지 Exchange Online Protection 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-109">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="674b5-110">자세한 내용은 [EOP의 스팸 방지 보호를 참조하세요.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="674b5-110">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="674b5-111">그러나 관리자가 다음의 개별 사서함에 대해 구성할 수 있는 특정 스팸 방지 설정도 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="674b5-111">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="674b5-112">정크 메일 규칙 사용 또는 사용 **안함:** 정크 메일 규칙은 모든 사서함에서 기본적으로 사용하도록 설정된 정크 메일 규칙이라는 숨겨진 받은 편지함 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-112">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="674b5-113">정크 메일 규칙은 다음 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-113">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="674b5-114">**스팸** 방지 정책에 따라 정크 메일 폴더로 메시지 이동: 스팸 필터링 판정에 대해 정크 메일 폴더로 메시지 이동 작업을 사용하여 스팸 방지 정책을 구성하면 정크 메일 필터 규칙은 메시지가 사서함으로 배달된 후 메시지를 정크 메일 폴더로 이동합니다. </span><span class="sxs-lookup"><span data-stu-id="674b5-114">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="674b5-115">스팸 방지 정책의 스팸 필터링 판정에 대한 자세한 내용은 EOP에서 스팸 방지 정책 [구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="674b5-115">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="674b5-116">마찬가지로 ZAP(제로 아워 자동 제거)에서 배달된 메시지가 스팸 또는 피싱으로 확인되는 경우 정크 메일 필터  규칙은 메시지를 정크 메일 폴더 스팸 필터링 판정 작업으로 이동하기 위해 메시지를 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-116">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="674b5-117">ZAP에 대한 자세한 내용은 에서 [제로 아워 ZAP(자동 제거)를 Exchange Online.](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="674b5-117">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>

  - <span data-ttu-id="674b5-118">**사용자가** 웹용 Outlook 또는 Outlook 사용자에 대해 구성하는 정크 메일  설정: 수신 수신 목록 컬렉션은 각 사서함의 수신이 가능한 보낸 사람 목록, 수신 수신이 가능한 받는 사람 목록 및 수신이 차단된 보낸 사람 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-118">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Blocked Senders list on each mailbox.</span></span> <span data-ttu-id="674b5-119">이러한 목록의 항목은 정크 메일 규칙이 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-119">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="674b5-120">사용자는 웹용 사서함(이전의 웹 Outlook 또는 Outlook 사서함에 대해 safelist 컬렉션을 구성할 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="674b5-120">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="674b5-121">관리자는 모든 사용자의 사서함에 대해 Safelist 컬렉션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-121">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="674b5-122">사서함에서 정크 메일 규칙을 사용하도록 설정하면 EOP는 스팸 필터링 판정 동작에 따라 메시지를 정크  메일 폴더로 이동하거나 사서함의 수신 차단된 보낸 사람 목록으로 메시지를 이동하고, 메시지가 사서함의 수신 가능 보낸 사람 목록에 따라 정크 메일 폴더로 배달되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-122">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="674b5-123">사서함에서 정크 메일 규칙을 사용하지 않도록 설정하면 EOP에서 스팸 필터링 판정 동작에 따라 메시지를 정크 메일 폴더로 이동하거나 사서함의 수신할 수 있는 목록 모음으로 메시지를 이동할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="674b5-123">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="674b5-124">관리자는 PowerShell을 사용하여 Exchange Online 정크 메일 규칙의 상태를 사용하지 않도록 설정하고, 사용하도록 설정하고, 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-124">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="674b5-125">관리자는 PowerShell을 사용하여 사서함의 수신 Exchange Online 컬렉션(수신- 보낸 사람 목록, 수신 금지된 받는 사람 목록 및 수신 금지된 보낸 사람 목록)을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-125">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Blocked Senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="674b5-126">사용자가 자신의 수신 - 보낸 사람 목록에 추가한 보낸 사람이 보낸 메시지는 EOP의 일부로 연결 필터링을 건너뜁습니다(SCL은 -1).</span><span class="sxs-lookup"><span data-stu-id="674b5-126">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="674b5-127">사용자가 보낸 사람 목록에 항목을 추가하지 못하게 Outlook 이 문서 의 2부에서 정크 메일 정보 설정에 설명된 Outlook 그룹 정책을 사용합니다. [](#about-junk-email-settings-in-outlook)</span><span class="sxs-lookup"><span data-stu-id="674b5-127">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this article.</span></span> <span data-ttu-id="674b5-128">정책 필터링, 콘텐츠 필터링 및 Office 365 검사에 대한 Defender는 메시지에 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-128">Policy filtering, Content filtering and Defender for Office 365 checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="674b5-129">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="674b5-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="674b5-130">PowerShell을 사용하여 Exchange Online 절차를 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-130">You can only use Exchange Online PowerShell to do the procedures in this article.</span></span> <span data-ttu-id="674b5-131">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="674b5-132">이 문서의 절차를 수행하려면 Exchange Online 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-132">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="674b5-133">특히 조직 관리, 받는 사람 관리 및 사용자 지정 메일 받는 사람 역할 그룹에 기본적으로 할당되는  Mail  **Recipients** 역할 또는 조직 관리 및 **지원** 센터 역할 그룹에 기본적으로 할당되는 사용자 옵션 역할이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="674b5-133">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="674b5-134">에서 역할 그룹에 사용자를 추가하려면 Exchange Online 에서 역할 [그룹 수정을 Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="674b5-134">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="674b5-135">기본 권한이 있는 사용자는 [PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)에 액세스할 수 있는 한 자신의 사서함에서 동일한 절차를 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-135">Note that users with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="674b5-136">EOP로 온-프레미스 Exchange 사서함을 보호하는 하이브리드 환경에서는 EOP 스팸 필터링 평가 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-136">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="674b5-137">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 EOP 구성하기](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-137">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span>

- <span data-ttu-id="674b5-138">공유 사서함의 수신 안전한 보낸 사람이 Azure AD 및 EOP에 기본적으로 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-138">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="674b5-139">PowerShell Exchange Online 사용하여 사서함에서 정크 메일 규칙을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="674b5-139">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="674b5-140">**Set-MailboxJunkEmailConfiguration** cmdlet을 사용하여 웹에서 Outlook(캐시된 Exchange 모드로) 또는 Outlook 사서함에서 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-140">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="674b5-141">사서함을 열지 않은 경우 다음 오류가 발생합니다. 대량 작업에 대해 이 오류를 표시하지 않는 경우 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 명령에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-141">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="674b5-142">사서함에서 정크 메일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-142">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="674b5-143">이 예에서는 Ori Epstein의 사서함에서 정크 메일 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-143">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="674b5-144">이 예에서는 조직의 모든 사용자 사서함에 대해 정크 메일 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-144">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="674b5-145">구문과 매개 변수에 대한 자세한 내용은 [Set-MailboxJunkEmailConfiguration을 참조하십시오.](/powershell/module/exchange/set-mailboxjunkemailconfiguration)</span><span class="sxs-lookup"><span data-stu-id="674b5-145">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="674b5-146">사용자가 사서함을 연 적이 없는 경우 이전 명령을 실행할 때 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-146">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="674b5-147">대량 작업에 대해 이 오류를 표시하지 않습니다. `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 명령에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-147">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="674b5-148">정크 메일 규칙을 사용하지 않도록 설정한 경우에도 Outlook 정크 메일 필터(구성 방법에 따라)는 메시지가 스팸인지 여부를 확인할 수 있으며, 자체 스팸 판정 및 사서함의 수신 금지 목록 모음에 따라 받은 편지함 또는 정크 메일 폴더로 메시지를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-148">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="674b5-149">자세한 내용은 이 문서의 정크 메일 Outlook [섹션을](#about-junk-email-settings-in-outlook) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-149">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this article.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="674b5-150">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="674b5-150">How do you know this worked?</span></span>

<span data-ttu-id="674b5-151">사서함에서 정크 메일 규칙을 성공적으로 사용하도록 설정하거나 사용하지 않도록 설정한 경우 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="674b5-151">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="674b5-152">사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행하여 _\<MailboxIdentity\>_ **Enabled** 속성 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-152">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="674b5-153">PowerShell Exchange Online 사용하여 사서함에 대해 Safelist 컬렉션 구성</span><span class="sxs-lookup"><span data-stu-id="674b5-153">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="674b5-154">사서함의 수신 금지 목록 컬렉션에는 수신 금지된 보낸 사람 목록, 수신 금지된 받는 사람 목록 및 수신이 차단된 보낸 사람 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-154">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="674b5-155">기본적으로 사용자는 웹용 사서함 또는 웹의 사서함에 Outlook Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-155">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="674b5-156">관리자는 **Set-MailboxJunkEmailConfiguration** cmdlet에서 해당 매개 변수를 사용하여 사용자 사서함에 대해 safelist 컬렉션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-156">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="674b5-157">이러한 매개 변수에 대한 설명은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-157">These parameters are described in the following table.</span></span>

****

|<span data-ttu-id="674b5-158">매개 변수의 Set-MailboxJunkEmailConfiguration</span><span class="sxs-lookup"><span data-stu-id="674b5-158">Parameter on Set-MailboxJunkEmailConfiguration</span></span>|<span data-ttu-id="674b5-159">Outlook 설정</span><span class="sxs-lookup"><span data-stu-id="674b5-159">Outlook on the web setting</span></span>|
|---|---|
|<span data-ttu-id="674b5-160">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="674b5-160">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="674b5-161">**이러한 보낸 사람 또는 도메인에서 정크 메일 폴더로 전자 메일 이동**</span><span class="sxs-lookup"><span data-stu-id="674b5-161">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="674b5-162">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="674b5-162">_ContactsTrusted_</span></span>|<span data-ttu-id="674b5-163">**연락처의 전자 메일 신뢰**</span><span class="sxs-lookup"><span data-stu-id="674b5-163">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="674b5-164">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="674b5-164">_TrustedListsOnly_</span></span>|<span data-ttu-id="674b5-165">**수신 허용 - 보낸 사람 및 도메인 목록의 주소와 안전한 메일링 목록의 전자 메일만 신뢰**</span><span class="sxs-lookup"><span data-stu-id="674b5-165">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="674b5-166">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="674b5-166">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="674b5-167">**이러한 보낸 사람이 내 정크 메일 폴더로 전자 메일을 이동하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="674b5-167">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="674b5-168"><sup>\*</sup>**참고**:</span><span class="sxs-lookup"><span data-stu-id="674b5-168"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="674b5-169">이 Exchange Online 수신  허용 - 보낸 사람 목록 또는 _TrustedSendersAndDomains_ 매개 변수의 도메인 항목은 인식되지 않습니다. 따라서 전자 메일 주소만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-169">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="674b5-170">디렉터리 동기화가 있는 독립 실행형 EOP에서는 도메인 항목이 기본적으로 동기화되지 않지만 도메인에 대해 동기화를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-170">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="674b5-171">자세한 내용은 [KB3019657을 참조하세요.](https://support.microsoft.com/help/3019657)</span><span class="sxs-lookup"><span data-stu-id="674b5-171">For more information, see [KB3019657](https://support.microsoft.com/help/3019657).</span></span>

- <span data-ttu-id="674b5-172">**Set-MailboxJunkEmailConfiguration** cmdlet을 사용하여 수신 가능한 받는 사람 목록을 직접 수정할 수 _없습니다(TrustedRecipientsAndDomains_ 매개 변수가 작동하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="674b5-172">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="674b5-173">수신-보낸 사람 목록을 수정하면 해당 변경 내용이 수신 가능한 받는 사람 목록에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-173">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="674b5-174">사서함에 대해 safelist 컬렉션을 구성하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-174">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="674b5-175">여러 값을 입력하고 _BlockedSendersAndDomains_ 및 _TrustedSendersAndDomains_ 매개 변수에 대한 기존 항목을 덮어치기 위해 다음 구문을 `"<Value1>","<Value2>"...` 사용합니다. .</span><span class="sxs-lookup"><span data-stu-id="674b5-175">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="674b5-176">다른 기존 항목에 영향을 주지 않고 하나 이상의 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="674b5-176">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="674b5-177">이 예에서는 Ori Epstein의 사서함에 있는 safelist 컬렉션에 대해 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-177">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="674b5-178">수신 shopping@fabrikam.com 목록에 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-178">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="674b5-179">수신- chris@fourthcoffee.com 목록 및 수신이 가능한 받는 사람 목록에서 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-179">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="674b5-180">연락처 폴더의 연락처를 신뢰할 수 있는 보낸 사람으로 처리하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-180">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="674b5-181">이 예에서는 조직의 contoso.com 사서함의 수신 차단된 보낸 사람 목록에서 도메인 도메인을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-181">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="674b5-182">구문과 매개 변수에 대한 자세한 내용은 [Set-MailboxJunkEmailConfiguration을 참조하십시오.](/powershell/module/exchange/set-mailboxjunkemailconfiguration)</span><span class="sxs-lookup"><span data-stu-id="674b5-182">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="674b5-183">사용자가 사서함을 연 적이 없는 경우 이전 명령을 실행할 때 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-183">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="674b5-184">대량 작업에 대해 이 오류를 표시하지 않습니다. `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 명령에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-184">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="674b5-185">사서함에서 정크 메일 규칙을 사용하지 않도록 설정한 경우에도 수신 수신 목록 컬렉션을 구성할 수 있으며 Outlook 정크 메일 필터는 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-185">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="674b5-186">자세한 내용은 이 문서의 정크 메일 Outlook [섹션을](#about-junk-email-settings-in-outlook) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-186">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this article.</span></span>
>
> - <span data-ttu-id="674b5-187">정크 Outlook 필터에 추가 수신 목록 모음 설정이 있습니다(예: 수신- 보낸 사람 목록에 전자 메일 **자동** 추가).</span><span class="sxs-lookup"><span data-stu-id="674b5-187">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="674b5-188">자세한 내용은 정크 메일 필터를 사용하여 보게되는 메시지 [제어를 참조하세요.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)</span><span class="sxs-lookup"><span data-stu-id="674b5-188">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="674b5-189">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="674b5-189">How do you know this worked?</span></span>

<span data-ttu-id="674b5-190">사서함에 대해 safelist 컬렉션을 성공적으로 구성한 경우 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="674b5-190">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="674b5-191">사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행하여 속성 _\<MailboxIdentity\>_ 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-191">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="674b5-192">값 목록이 너무 길면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-192">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="674b5-193">2016의 정크 메일 설정 Outlook</span><span class="sxs-lookup"><span data-stu-id="674b5-193">About junk email settings in Outlook</span></span>

<span data-ttu-id="674b5-194">사용자 계정에서 사용할 수 있는 클라이언트 쪽 정크 메일 필터 설정을 사용하도록 설정, 비활성화 및 구성하려면 Outlook 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-194">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="674b5-195">자세한 내용은 그룹 정책을 사용하여 [엔터프라이즈용 Microsoft 365 앱, Office 2019 및 Office 2016에 대한 관리 템플릿 파일(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) 및 Office [](https://support.microsoft.com/help/2252421)사용자 지정 도구 및 수신-보낸 사람 목록과 같은 정크 메일 설정을 배포하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-195">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).</span></span>

<span data-ttu-id="674b5-196">Outlook 정크 메일 필터가 기본값으로 설정되어  있는 경우 홈  정크 정크 메일 옵션에서 자동 필터링 안 하세요. Outlook 스팸으로 분류하지는 않지만 수신 금지 목록 컬렉션(수신이 가능한 보낸 사람 목록, 수신자 목록 및 수신 차단된 보낸 사람 목록)을 사용하여 메시지를 배달 후 정크 메일 폴더로 \>  \>  \> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-196">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="674b5-197">이러한 설정에 대한 자세한 내용은 정크 메일 필터 [개요를 참조하세요.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)</span><span class="sxs-lookup"><span data-stu-id="674b5-197">For more information about these settings, see [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="674b5-198">정크 Outlook 필터를 낮음 또는  높음으로 설정하면 Outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용하여 스팸을 식별하고 정크 메일 폴더로 이동합니다. </span><span class="sxs-lookup"><span data-stu-id="674b5-198">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="674b5-199">이 스팸 분류는 EOP에 의해 결정된 SCL(스팸 지수)과는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-199">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="674b5-200">실제로 Outlook EOP에서 SCL을 무시하고(EOP가 스팸 필터링을 건너뛰기 위해 메시지를 표시하지 않은 경우) 자체 조건을 사용하여 메시지가 스팸인지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-200">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="674b5-201">물론 EOP와 EOP의 스팸 판정이 같을 Outlook 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-201">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="674b5-202">이러한 설정에 대한 자세한 내용은 정크 메일 필터에서 보호 수준 [변경을 참조하세요.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)</span><span class="sxs-lookup"><span data-stu-id="674b5-202">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="674b5-203">2016년 11월, Microsoft는 2016년 11월에 Microsoft와 팜에서 SmartScreen 필터에 대한 스팸 정의 Exchange Outlook.</span><span class="sxs-lookup"><span data-stu-id="674b5-203">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="674b5-204">기존 SmartScreen 스팸 정의는 적용된 것이지만 시간이 지날 때 효율성이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-204">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="674b5-205">자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="674b5-205">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="674b5-206">따라서 Outlook 정크 메일 필터는 사서함에서 정크 메일 규칙을 사용하지 않도록 설정한 경우에도 사서함의 수신 수신 목록 모음 및 자체 스팸 분류를 사용하여 메시지를 정크 메일 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-206">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="674b5-207">Outlook Outlook 목록 모음을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-207">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="674b5-208">safelist 컬렉션은 Exchange Online 사서함에 저장됩니다. 따라서 Outlook 목록 모음의 변경 내용은 Outlook 웹에 표시되고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-208">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="674b5-209">정크 메일 설정에 대한 제한</span><span class="sxs-lookup"><span data-stu-id="674b5-209">Limits for junk email settings</span></span>

<span data-ttu-id="674b5-210">또한 사용자의 사서함에 저장된 수신 가능 목록 모음(수신 가능 보낸 사람 목록, 수신 가능 받는 사람 목록 및 수신이 차단된 보낸 사람 목록)도 EOP에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-210">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="674b5-211">디렉터리 동기화를 통해 Safelist 컬렉션이 Azure AD에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-211">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="674b5-212">사용자 사서함의 수신할 수 있는 목록 모음의 제한은 510 KB(모든 목록과 추가 정크 메일 필터 설정 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-212">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="674b5-213">사용자가 이 제한을 초과하면 다음과 같은 Outlook 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-213">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="674b5-214">서버에 정크 메일 목록을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-214">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="674b5-215">서버에서 허용되는 크기를 넘습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-215">You are over the size allowed on the server.</span></span> <span data-ttu-id="674b5-216">정크 메일 목록이 서버에서 허용되는 크기로 줄어들 때까지 서버의 정크 메일 필터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-216">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="674b5-217">이 제한 및 변경 방법에 대한 자세한 내용은 [KB2669081을 참조하세요.](https://support.microsoft.com/help/2669081)</span><span class="sxs-lookup"><span data-stu-id="674b5-217">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081).</span></span>

- <span data-ttu-id="674b5-218">EOP의 동기화된 Safelist 컬렉션에는 다음과 같은 동기화 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-218">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="674b5-219">내 연락처의 전자 메일을 신뢰하는 경우 수신 가능 보낸 사람 목록,  수신 가능 받는 사람 목록 및 외부 연락처의 총 항목 1024개</span><span class="sxs-lookup"><span data-stu-id="674b5-219">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="674b5-220">수신 차단된 보낸 사람 목록 및 차단된 도메인 목록의 총 항목 500개</span><span class="sxs-lookup"><span data-stu-id="674b5-220">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="674b5-221">1024 항목 제한에 도달하면 다음과 같은 상황이 발생하게됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-221">When the 1024 entry limit is reached, the following things happen:</span></span>

  - <span data-ttu-id="674b5-222">PowerShell 및 웹에서 Outlook 수락이 중지되지만 오류는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-222">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="674b5-223">Outlook 510 KB의 제한에 도달할 때까지 1024개가 넘는 항목을 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-223">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="674b5-224">Outlook 사서함으로 배달하기 전에 EOP 필터가 메시지를 차단하지 않는 한 이러한 추가 항목을 사용할 수 있습니다(메일 흐름 규칙, 스푸핑 방지 등).</span><span class="sxs-lookup"><span data-stu-id="674b5-224">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="674b5-225">디렉터리 동기화를 통해 항목은 다음 순서대로 Azure AD에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-225">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="674b5-226">내 연락처의 전자 메일을 신뢰하는 경우 메일 **연락처를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-226">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="674b5-227">처음 1024개 항목에 대해 변경이 이행될 때마다 수신이 가능한 보낸 사람 목록과 수신 수신자 목록이 사전순으로 결합, 중복 제거 및 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-227">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="674b5-228">처음 1024개 항목이 사용하며 관련 정보는 메시지 헤더에 스탬프 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-228">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>

  <span data-ttu-id="674b5-229">Azure AD에 동기화되지 않은 1024개가 넘는 항목은 웹에서 Outlook(웹에서 Outlook 아미라)에서 처리하며 메시지 헤더에 정보가 스탬프 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-229">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="674b5-230">아래에서 볼 수 있겠지만, 내 연락처에서 전자 메일 신뢰 설정을 사용하도록 설정하면 동기화할 수 있는 수신-보낸 사람 및 안전한 받는 사람 수가 줄어듭됩니다. </span><span class="sxs-lookup"><span data-stu-id="674b5-230">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="674b5-231">이 문제가 우려되는 경우 그룹 정책을 사용하여 이 기능을 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="674b5-231">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="674b5-232">파일 이름: outlk16.opax</span><span class="sxs-lookup"><span data-stu-id="674b5-232">File name: outlk16.opax</span></span>
- <span data-ttu-id="674b5-233">정책 설정: **연락처의 전자 메일 신뢰**</span><span class="sxs-lookup"><span data-stu-id="674b5-233">Policy setting: **Trust e-mail from contacts**</span></span>
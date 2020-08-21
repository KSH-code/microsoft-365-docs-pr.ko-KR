---
title: Exchange Online 사서함에 대한 정크 메일 설정 구성
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online 사서함에서 정크 메일 설정을 구성하는 방법을 알수 있습니다. Outlook 또는 웹용 Outlook에서 이러한 설정을 사용할 수 있습니다.
ms.openlocfilehash: 171eca8535958f01a7f749ad678e6ea9dd83d80c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825716"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="b01a7-104">Exchange Online 사서함에 대한 정크 메일 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b01a7-104">Configure junk email settings on Exchange Online mailboxes</span></span>

<span data-ttu-id="b01a7-105">Exchange Online 사서함이 있는 Microsoft 365 조직에서 조직의 스팸 방지 설정은 EOP(Exchange Online Protection)에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-105">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b01a7-106">자세한 내용은 [EOP의 스팸 방지 보호 기능을 참조하세요.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b01a7-106">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="b01a7-107">그렇지만 관리자가 Exchange Online에서 개별 사서함을 구성할 수 있는 특정 스팸 방지 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-107">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="b01a7-108">**정크 메일 규칙 사용 또는 사용 안**함: 정크 메일 규칙은 모든 사서함에서 기본적으로 사용하도록 설정되어 있는 정크 메일 규칙이라는 숨겨진 받은 편지함 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-108">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="b01a7-109">정크 메일 규칙은 다음 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-109">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="b01a7-110">**스팸 방지 정책을 사용하여 정크 메일**폴더로 메시지 이동: 스팸 필터링 결과에 대한 메시지 이동 동작으로 **스팸** 방지 정책이 구성되어 있는 경우 정크 메일 필터 규칙은 메시지가 사서함으로 전달된 후 메시지를 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-110">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="b01a7-111">스팸 방지 정책의 스팸 필터링 조건에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b01a7-111">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="b01a7-112">마찬가지로 ZAP(제로 아오스트 자동 비우기)가 배달된 메시지가 스팸 또는 피싱인 경우 정크 메일 필터 규칙은 **메시지를** 정크 메일 폴더 스팸 필터링 결과로 이동하기 위해 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-112">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="b01a7-113">ZAP에 대한 자세한 내용은 [Exchange Online의 ZAP(제로 아크로 자동 제거)를 참조하세요.](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="b01a7-113">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>

  - <span data-ttu-id="b01a7-114">**사용자가 웹에서 Outlook 또는 Outlook에서 자체하게**구성하는 정크 메일 설정 : 수신 _허용_ 목록 모음은 수신 허용 - 보낸 사람 목록, 수신 허용 - 받는 사람 목록 및 각 사서함의 수신 거부 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-114">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Block senders list on each mailbox.</span></span> <span data-ttu-id="b01a7-115">이러한 목록에 있는 항목은 정크 메일 규칙에 따라 메시지를 받은 편지함으로 이동할지 또는 정크 메일 폴더로 이동할지결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-115">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="b01a7-116">사용자는 Outlook 또는 웹용 Outlook(이전의 이전 의라고 함)에서 자신의 사서함에 대한 수신 허용 목록 모음을 구성할 Outlook Web App 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-116">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="b01a7-117">관리자는 모든 사용자 사서함에서 수신 허용 목록 모음을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-117">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="b01a7-118">사서함에 정크 메일 규칙이 사용되도록 설정되어 있을 때 EOP가 스팸 필터링 결과 작업을 통해 사서함의 **Move message to Junk Email folder** 정크 메일 폴더나 수신 거부 목록을 기반으로 메시지를 정크 메일 폴더로 이동하고, 사서함의 수신 허용 - 보낸 사람 목록을 기반으로 메시지가 정크 메일 폴더로 배달되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-118">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="b01a7-119">사서함에서 정크 메일 규칙을 사용하지 않도록 설정하면 EOP는 스팸 필터링 결과 작업에 따라 메시지를 정크 메일 폴더로 이동하거나 **사서함의** 수신 허용 목록 모음에 이어서 정크 메일 폴더로 메시지를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-119">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="b01a7-120">관리자는 Exchange Online PowerShell을 사용하여 사서함에서 정크 메일 규칙을 사용하지 않도록 설정하고 사용하도록 설정하고 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-120">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="b01a7-121">관리자는 Exchange Online PowerShell을 사용하여 사서함의 수신 허용 목록 모음(수신 허용 - 보낸 사람 목록, 수신 허용 - 받는 사람 목록 및 차단할 보낸 사람 목록)의 항목을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-121">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Block senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="b01a7-122">사용자가 자신의 수신 허용 - 보낸 사람 목록에 추가한 보낸 사람이 보낸 메시지는 EOP의 일부로 연결 필터링을 건너뜁니다(SCL은 -1임).</span><span class="sxs-lookup"><span data-stu-id="b01a7-122">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="b01a7-123">사용자가 Outlook의 수신 허용 - 보낸 사람 목록에 항목을 추가하지 못하도록 하려면 이 항목 뒷부분에 나오는 Outlook의 정크 메일 정보  [설정에 설명된 것과](#about-junk-email-settings-in-outlook) 같이 그룹 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-123">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this topic.</span></span> <span data-ttu-id="b01a7-124">정책 필터링, 콘텐츠 필터링 및 ATP(Advanced Threat Protection) 확인이 메시지에 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-124">Policy filtering, Content filtering and Advanced Threat Protection (ATP) checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b01a7-125">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="b01a7-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b01a7-126">Exchange Online PowerShell을 사용하며 이 절차는 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-126">You can only use Exchange Online PowerShell to perform these procedures.</span></span> <span data-ttu-id="b01a7-127">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b01a7-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b01a7-128">이러한 절차를 수행하려면 먼저 사용 권한을 할당만 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-128">You need to be assigned permissions before you can do these procedures.</span></span> <span data-ttu-id="b01a7-129">특히, 메일 받는 사람 **역할(기본적으로 조직** **관리,** 받는 사람 **관리**및 사용자 지정 **메일 받는** 사람 역할 그룹에 할당)이나 사용자 **옵션** 역할(기본적으로 조직 관리 **및 지원** **센터** 역할 그룹에 할당되는)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-129">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="b01a7-130">Exchange Online의 역할 그룹에 사용자를 추가하려면 Exchange [Online의 역할 그룹 수정을 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="b01a7-130">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="b01a7-131">기본 권한이 있는 사용자는 Exchange Online PowerShell에 액세스할 수 있는 한 자체 사서함에 대해 [이러한 절차를 동일할 수 있습니다.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b01a7-131">Note that a user with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b01a7-132">EOP로 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 EOP 스팸 필터링 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-132">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="b01a7-133">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b01a7-133">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="b01a7-134">공유 사서함에 대한 수신 허용 보낸 사람은 Azure AD 및 EOP의 의도에 의해 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-134">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="b01a7-135">Exchange Online PowerShell을 사용하여 사서함에 정크 메일 규칙을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b01a7-135">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="b01a7-136">**Set-MailboxJunkEmailConfiguration** cmdlet을 사용하 여 Outlook에서 캐시된 Exchange 모드로 열려 있거나 웹에서 Outlook에서 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-136">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="b01a7-137">사서함이 열려 있다면 다음 오류메시지가 표시됩니다. 대량 작업에 대해 이 오류가 표시되지 않도록 하려면 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration 명령에 추가하면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b01a7-137">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="b01a7-138">사서함에 정크 메일 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-138">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="b01a7-139">이 예에서는 Ori Epstein의 사서함에서 정크 메일 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-139">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="b01a7-140">이 예에서는 조직의 모든 사용자 사서함에 대해 정크 메일 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-140">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="b01a7-141">구문과 매개 변수에 대한 자세한 내용은 [Set-MailboxJunkEmailConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)</span><span class="sxs-lookup"><span data-stu-id="b01a7-141">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b01a7-142">사용자가 사서함을 열지 않은 경우 이전 명령을 실행할 때 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-142">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="b01a7-143">대량 작업에 대해 이 오류를 표시하지 않은 경우 `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration 명령을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="b01a7-143">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="b01a7-144">정크 메일 규칙을 사용하도록 설정하더라도 Outlook 정크 메일 그룹 구성 방법에 따라 Outlook 정크 메일 필터가 메시지가 스팸인지 결정할 수 있습니다. 또한 메시지를 스팸 결과와 사서함의 수신 허용 목록 모음을 기반으로 받은 편지함 또는 정크 메일 폴더로 메시지를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-144">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="b01a7-145">자세한 내용은 이 항목의 [Outlook의 정크 메일 설정에 대한 정보를](#about-junk-email-settings-in-outlook) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b01a7-145">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b01a7-146">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="b01a7-146">How do you know this worked?</span></span>

<span data-ttu-id="b01a7-147">사서함에 정크 메일 규칙을 사용하거나 사용하지 않도록 설정되었는지 확인하려면 다음 절차를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-147">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="b01a7-148">사서함의 _\<MailboxIdentity\>_ 이름, 별칭 또는 이메일 주소로 교체하고 다음 명령을 실행하여 Enabled 속성 **값을** 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-148">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="b01a7-149">Exchange Online PowerShell을 사용 하 고 에 대 한 사서함의 수신 허용 목록 모음 구성</span><span class="sxs-lookup"><span data-stu-id="b01a7-149">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="b01a7-150">사서함의 수신 허용 목록 컬렉션에는 수신 허용 - 보낸 사람 목록, 수신 허용 - 받는 사람 목록 및 수신 거부 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-150">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="b01a7-151">기본적으로 사용자는 Outlook 또는 웹에서 Outlook에서 자체 사서함에서 수신 허용 목록 모음을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-151">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="b01a7-152">관리자는 **Set-MailboxJunkEmailConfiguration** cmdlet에서 해당 매개 변수를 사용하여 사용자 사서함의 수신 허용 목록 모음을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-152">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="b01a7-153">다음 표에 는 이러한 매개 변수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-153">These parameters are described in the following table.</span></span>

****

|<span data-ttu-id="b01a7-154">Set-MailboxJunkEmailConfiguration의 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b01a7-154">Parameter on Set-MailboxJunkEmailConfiguration</span></span>|<span data-ttu-id="b01a7-155">웹용 Outlook 설정</span><span class="sxs-lookup"><span data-stu-id="b01a7-155">Outlook on the web setting</span></span>|
|---|---|
|<span data-ttu-id="b01a7-156">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="b01a7-156">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="b01a7-157">**이러한 보낸 사람 또는 도메인의 전자 메일을 내 정크 메일 폴더로 이동**</span><span class="sxs-lookup"><span data-stu-id="b01a7-157">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="b01a7-158">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="b01a7-158">_ContactsTrusted_</span></span>|<span data-ttu-id="b01a7-159">**내 연락처에서 가는 전자 메일 신뢰**</span><span class="sxs-lookup"><span data-stu-id="b01a7-159">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="b01a7-160">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="b01a7-160">_TrustedListsOnly_</span></span>|<span data-ttu-id="b01a7-161">**수신 허용 - 보낸 사람 및 도메인 목록과 안전한 메일 목록의 주소에서 전자 메일만 신뢰**</span><span class="sxs-lookup"><span data-stu-id="b01a7-161">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="b01a7-162">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b01a7-162">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="b01a7-163">**이 보낸 사람의 전자 메일을 내 정크 메일 폴더로 이동하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="b01a7-163">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="b01a7-164"><sup>\*</sup>**참고:**</span><span class="sxs-lookup"><span data-stu-id="b01a7-164"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="b01a7-165">Exchange Online에서 수신 **허용 -** 보낸 사람 목록 또는 _TrustedSendersAndDomains_ 매개 변수의 도메인 항목은 인식되지 않기 어려운 따라서 전자 메일 주소만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-165">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="b01a7-166">디렉터리 동기화를 사용한 독립 실행형 EOP에서는 도메인 항목이 기본적으로 동기화되지 않지만 도메인에 대해 동기화를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-166">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="b01a7-167">자세한 내용은 [KB3019657을 참조하세요.](https://support.microsoft.com/help/3019657)</span><span class="sxs-lookup"><span data-stu-id="b01a7-167">For more information, see [KB3019657](https://support.microsoft.com/help/3019657).</span></span>

- <span data-ttu-id="b01a7-168">**Set-MailboxJunkEmailConfiguration** cmdlet을 사용하여 수신 허용 - 받는 사람 목록을 직접 수정할 수는 _없습니다(TrustedRecipientsAndDomains_ 매개 변수가 작동하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="b01a7-168">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="b01a7-169">수신 허용 - 보낸 사람 목록을 수정하면 이러한 변경 내용이 수신 허용 - 받는 사람 목록과 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-169">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="b01a7-170">사서함에서 수신 허용 목록 모음을 구성하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-170">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="b01a7-171">다중 값을 입력하고 _BlockedSendersAndDomains_ 및 _TrustedSendersAndDomains_ 매개 변수의 기존 항목을 덮어쓰려면 다음 구문을 `"<Value1>","<Value2>"...` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-171">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="b01a7-172">기존 항목을 변경하지 않고 하나 이상의 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="b01a7-172">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="b01a7-173">이 예에서는 Ori Epstein 사서함의 수신 허용 목록 컬렉션에 대해 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-173">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="b01a7-174">사서함 shopping@fabrikam.com 목록에 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-174">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="b01a7-175">수신 허용 - chris@fourthcoffee.com 수신 허용 - 받는 사람 목록에서 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-175">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="b01a7-176">연락처 폴더의 연락처를 신뢰할 수 있는 보낸 사람으로 간주하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-176">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="b01a7-177">이 예에서는 조직의 contoso.com 사서함의 수신 거부 목록에서 도메인 도메인을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-177">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="b01a7-178">구문과 매개 변수에 대한 자세한 내용은 [Set-MailboxJunkEmailConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)</span><span class="sxs-lookup"><span data-stu-id="b01a7-178">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b01a7-179">사용자가 사서함을 열지 않은 경우 이전 명령을 실행할 때 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-179">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="b01a7-180">대량 작업에 대해 이 오류를 표시하지 않은 경우 `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration 명령을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="b01a7-180">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="b01a7-181">사서함에서 정크 메일 규칙이 사용되지 않는 경우에도 수신 허용 목록 모음을 구성할 수는 있고 Outlook 정크 메일 필터는 받은 편지함 또는 정크 메일 폴더로 메시지를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-181">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="b01a7-182">자세한 내용은 이 항목의 [Outlook의 정크 메일 설정에 대한 정보를](#about-junk-email-settings-in-outlook) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b01a7-182">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>
>
> - <span data-ttu-id="b01a7-183">Outlook 정크 메일 필터에 추가 수신 허용 목록 모음 설정(예: 수신 허용 - 보낸 사람 목록에 **사용자 I 전자 메일을 자동으로 추가)합니다.**</span><span class="sxs-lookup"><span data-stu-id="b01a7-183">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="b01a7-184">자세한 내용은 [정크 메일 필터를 사용하여 확인되는 메시지를 제어하는 방법을 참조하세요.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)</span><span class="sxs-lookup"><span data-stu-id="b01a7-184">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b01a7-185">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="b01a7-185">How do you know this worked?</span></span>

<span data-ttu-id="b01a7-186">사서함에 수신 허용 목록 컬렉션이 구성되었는지 확인하려면 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="b01a7-186">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="b01a7-187">사서함의 _\<MailboxIdentity\>_ 이름, 별칭 또는 이메일 주소로 교체하고 다음 명령을 실행하여 속성 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-187">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="b01a7-188">값 목록이 너무 길면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-188">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="b01a7-189">Outlook의 정크 메일 설정 정보</span><span class="sxs-lookup"><span data-stu-id="b01a7-189">About junk email settings in Outlook</span></span>

<span data-ttu-id="b01a7-190">Outlook에서 사용할 수 있는 클라이언트 쪽 정크 메일 필터 설정을 활성화, 해제 및 구성하려면 그룹 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-190">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="b01a7-191">자세한 내용은 그룹 정책을 [사용하여 엔터프라이즈용 Microsoft 365 앱, Office 2019 및 Office 2016용 Office 사용자](https://www.microsoft.com/download/details.aspx?id=49030) 지정 도구와 수신 허용 - 보낸 사람 목록 같은 정크 메일 설정을 배포하는 방법(예: ADMX/ADML) 및 관리 [도구를 참조하세요.](https://support.microsoft.com/help/2252421)</span><span class="sxs-lookup"><span data-stu-id="b01a7-191">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).</span></span>

<span data-ttu-id="b01a7-192">Outlook 정크 메일 필터가 홈 정크 메일 옵션에서 **기본값인 No automatic filtering** in **Home** \> **Junk** \> **E-Mail Options,** Outlook은 스팸으로 분류를 시도하지 않지만 여전히 수신 허용 목록 모음(수신 허용 - 보낸 사람 목록, 수신 허용 - 받는 사람 목록 및 수신 거부 목록)을 사용하여 배달 후 메시지를 정크 메일 \> **Options**폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-192">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="b01a7-193">이 설정에 대한 자세한 내용은 [정크 메일 필터의 개요를 참조하세요.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)</span><span class="sxs-lookup"><span data-stu-id="b01a7-193">For more information about these settings, see [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="b01a7-194">Outlook 정크 메일 필터가 Low 또는 **High로 설정된** **경우**Outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용하여 스팸을 식별하고 정크 메일 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-194">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="b01a7-195">이 스팸 분류는 EOP에서 결정한 SCL(스팸 지수)과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-195">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="b01a7-196">사실, 후 EOP에서 SCL은 스팸 필터링을 건너뛰라고 표시하지 않은 경우 해당 SCL을 무시하고 고유한 기준을 사용하여 메시지가 스팸인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-196">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="b01a7-197">물론 EOP와 Outlook의 스팸 결과는 동일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-197">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="b01a7-198">이 설정에 대한 자세한 내용은 [정크 메일 필터의 보호 수준 변경을 참조하세요.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)</span><span class="sxs-lookup"><span data-stu-id="b01a7-198">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="b01a7-199">2016년 11월 Microsoft는 Exchange 및 Outlook에서 SmartScreen 필터에 대한 스팸 정의 업데이트 생성을 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-199">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="b01a7-200">기존 SmartScreen 스팸 정의는 제자리에 있었지만 시간 경과에 따라 효율성이 저하될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-200">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="b01a7-201">자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b01a7-201">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="b01a7-202">따라서 Outlook 정크 메일 필터는 사서함에서 정크 메일 규칙이 비활성화된 경우에도 사서함의 수신 허용 목록 모음과 자체 스팸 분류를 사용하여 메시지를 정크 메일 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-202">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="b01a7-203">Outlook 및 웹용 Outlook은 모두 수신 허용 목록 모음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-203">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="b01a7-204">수신 허용 목록 모음은 Exchange Online 사서함에 저장되므로 Outlook의 수신 허용 목록 모음에 대한 변경 사항이 웹용 Outlook에 도시될 수 있고 그 와도 같은 그 도로도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-204">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="b01a7-205">정크 메일 설정 제한</span><span class="sxs-lookup"><span data-stu-id="b01a7-205">Limits for junk email settings</span></span>

<span data-ttu-id="b01a7-206">사용자 사서함에 저장된 수신 허용 목록 모음(수신 허용 - 보낸 사람 목록, 수신 허용 - 받는 사람 목록 및 수신 허용 - 보낸 사람 목록)도 EOP와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-206">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="b01a7-207">디렉터리 동기화를 사용하는 경우 수신 허용 목록 모음은 Azure AD와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-207">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="b01a7-208">사용자 사서함의 수신 허용 목록 모음에서는 모든 목록과 추가 정크 메일 필터 설정을 포함하는 510KB로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-208">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="b01a7-209">사용자가 이 제한을 초과하면 다음과 같은 Outlook 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-209">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="b01a7-210">정크 메일 목록에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-210">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="b01a7-211">서버에서 허용되는 크기보다 제한이 초과되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-211">You are over the size allowed on the server.</span></span> <span data-ttu-id="b01a7-212">정크 메일 목록을 서버에서 허용하는 크기로 줄일 때까지 서버의 정크 메일 필터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-212">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="b01a7-213">이 제한 및 이 제한을 변경하는 방법에 대한 자세한 내용은 [KB2669081을 참조하십시오.](https://support.microsoft.com/help/2669081)</span><span class="sxs-lookup"><span data-stu-id="b01a7-213">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081).</span></span>

- <span data-ttu-id="b01a7-214">EOP의 동기화된 수신 허용 목록 모음에는 다음과 같은 동기화 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-214">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="b01a7-215">수신 허용 - 보낸 사람 목록에 1024개의 전체 항목(내 연락처에서 수신하는 전자 메일을 **사용하도록** 설정한 경우)</span><span class="sxs-lookup"><span data-stu-id="b01a7-215">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="b01a7-216">수신 거부 목록과 수신 거부 도메인 목록에 총 500개의 항목</span><span class="sxs-lookup"><span data-stu-id="b01a7-216">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="b01a7-217">1024 입력 한도에 도달하면 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-217">When the 1024 entry limit is reached, the following things happen:</span></span>

  - <span data-ttu-id="b01a7-218">이 목록은 PowerShell 및 웹용 Outlook의 항목 수락을 중지하지만 오류는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-218">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="b01a7-219">Outlook 사용자는 Outlook 수가 510KB를 초과할 때까지 1024개가 넘는 항목을 계속 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-219">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="b01a7-220">Outlook에서는 EOP 필터가 사서함으로 배달되기 전에 메시지를 차단하지 않는 한 이러한 추가 항목을 사용할 수 있습니다(메일 흐름 규칙, 스푸핑 방지 등).</span><span class="sxs-lookup"><span data-stu-id="b01a7-220">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="b01a7-221">디렉터리 동기화를 사용하는 경우 항목은 다음 순서로 Azure AD에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-221">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="b01a7-222">내 연락처에서 **신뢰하는 전자 메일을 사용할 수 있는 경우 메일 연락처를** 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-222">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="b01a7-223">처음 1024개 항목에 대한 변경이 있을 때는 수신 허용 - 보낸 사람 목록과 수신 허용 - 허용 - 중복 제거 및 정렬된 항목이 결합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-223">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="b01a7-224">처음 1024개 항목이 사용되며 관련 정보는 메시지 머리글에 스탬프 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-224">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>

  <span data-ttu-id="b01a7-225">Azure AD와 동기화되지 않은 1024개가 초과된 항목은 Outlook(웹용 Outlook 아됨)에서 처리되며 메시지 머리글에 스탬프 처리된 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-225">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="b01a7-226">확인할 수 있는 바와 같이 내 **연락처에서 신뢰 전자 메일 을 사용하도록** 설정하면 동기화할 수 있는 수신 허용 - 보낸 사람 및 수신 허용 - 보낸 사람 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-226">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="b01a7-227">이 문제의 발생이 우리적이면 그룹 정책을 사용하여 이 기능을 끄는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b01a7-227">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="b01a7-228">파일 이름: outlk16.opax</span><span class="sxs-lookup"><span data-stu-id="b01a7-228">File name: outlk16.opax</span></span>
- <span data-ttu-id="b01a7-229">정책 설정: **연락처에서 보내는 전자 메일 신뢰**</span><span class="sxs-lookup"><span data-stu-id="b01a7-229">Policy setting: **Trust e-mail from contacts**</span></span>

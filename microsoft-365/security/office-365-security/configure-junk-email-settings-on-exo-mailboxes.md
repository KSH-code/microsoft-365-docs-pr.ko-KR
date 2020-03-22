---
title: Office 365에서 Exchange Online 사서함의 정크 메일 설정 구성
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online 사서함에서 정크 메일 설정을 구성 하는 방법을 알 수 있습니다. 이러한 설정 중 상당수는 Outlook 또는 웹용 Outlook에서 사용자에 게 제공 됩니다.
ms.openlocfilehash: 2b138830cff7337d7949606cc110ea8f7ae1c0ff
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42897066"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes-in-office-365"></a><span data-ttu-id="57e03-104">Office 365에서 Exchange Online 사서함의 정크 메일 설정 구성</span><span class="sxs-lookup"><span data-stu-id="57e03-104">Configure junk email settings on Exchange Online mailboxes in Office 365</span></span>

<span data-ttu-id="57e03-105">Exchange Online의 조직 스팸 방지 설정은 EOP (Exchange Online Protection)에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-105">Organizational anti-spam settings in Exchange Online are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="57e03-106">자세한 내용은 [Office 365의 스팸 방지 보호](anti-spam-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-106">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="57e03-107">그러나 관리자가 Exchange Online의 개별 사서함에 대해 구성할 수 있는 특정 스팸 방지 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-107">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="57e03-108">**정크 메일 규칙을 사용 하거나 사용 하지 않도록**설정: 정크 메일 규칙은 모든 사서함에서 기본적으로 사용 하도록 설정 된 정크 메일 규칙 이라는 숨겨진 받은 편지함 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-108">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="57e03-109">정크 메일 규칙은 다음과 같은 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-109">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="57e03-110">**스팸 방지 정책을 기반으로 정크 메일 폴더로 메시지 이동**: 스팸 방지 정책에 대 한 **메시지 이동** 작업을 정크 메일 필터링 결과으로 구성한 경우 정크 메일 필터 규칙은 메시지가 사서함으로 배달 된 후 해당 메시지를 정크 메일 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-110">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="57e03-111">스팸 방지 정책에서의 스팸 필터링 verdicts에 대 한 자세한 내용은 [Configure 안티스팸 information In Office 365](configure-your-spam-filter-policies.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-111">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="57e03-112">마찬가지로 자동 삭제 (ZAP)에서 이미 배달 된 메시지의 스팸 또는 피싱를 검색 하는 경우 정크 메일 필터 규칙은 메시지를 **정크 메일 폴더** 스팸 필터링 결과 작업으로 이동 하기 위해 정크 메일 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-112">Similarly, if auto purge (ZAP) detects spam or phish in an already delivered message, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="57e03-113">ZAP에 대 한 자세한 내용은 [0 시간 자동 삭제 (ZAP)-Office 365의 스팸 및 맬웨어에 대 한 보호](zero-hour-auto-purge.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-113">For more information about ZAP, see [Zero-hour auto purge (ZAP) - protection against spam and malware in Office 365](zero-hour-auto-purge.md).</span></span>
  
  - <span data-ttu-id="57e03-114">**사용자가 Outlook 또는 웹용 outlook에서 자신을 위해 구성 하는 정크 메일 설정**: _수신 허용 목록 컬렉션_ 은 수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 각 사서함의 보낸 사람 차단 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-114">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Block senders list on each mailbox.</span></span> <span data-ttu-id="57e03-115">이러한 목록의 항목에 따라 정크 메일 규칙에서 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할 것인지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-115">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="57e03-116">사용자는 Outlook 또는 웹용 Outlook (이전의 Outlook Web App)에서 자신의 사서함에 대 한 수신 허용 목록 컬렉션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-116">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="57e03-117">관리자는 모든 사용자 사서함에서 수신 허용 목록 컬렉션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-117">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="57e03-118">사서함에서 정크 메일 규칙을 사용 하도록 설정 하면 EOP에서 사서함에 대 한 스팸 필터링 결과 작업 **이동 메시지를 정크** 메일 폴더 또는 수신 거부 목록에 기반 하 여 정크 메일 폴더로 이동 하 고 메시지를 정크 메일 폴더 (사서함의 수신 허용-보낸 사람 목록에 기반)로 배달 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-118">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="57e03-119">사서함에서 정크 메일 규칙을 사용 하지 않도록 설정 된 경우 EOP에서 스팸 필터링 결과 동작 **메시지를 정크 메일** 폴더로 이동 하거나 사서함에서 수신 허용 목록 모음으로 메시지를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-119">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="57e03-120">관리자는 Exchange Online PowerShell을 사용 하 여 사서함에 대 한 정크 메일 규칙의 상태를 사용 하지 않도록 설정 하 고 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-120">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="57e03-121">또한 관리자는 Exchange Online PowerShell을 사용 하 여 사서함의 수신 허용 목록 컬렉션, 즉 수신 허용-보낸 사람 목록 및 수신 거부 목록에 있는 항목을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-121">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Block senders list).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="57e03-122">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="57e03-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="57e03-123">다음 절차를 수행 하는 경우에만 Exchange Online PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-123">You can only use Exchange Online PowerShell to perform these procedures.</span></span> <span data-ttu-id="57e03-124">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="57e03-125">이러한 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-125">You need to be assigned permissions before you can do these procedures.</span></span> <span data-ttu-id="57e03-126">특히 **조직 관리**, **받는 사람 관리**및 **사용자 지정 메일 받는 사람** 역할 그룹에 기본적으로 할당 되는 **메일 받는 사람** 역할 (기본적으로 **조직 관리** 및 **Help Desk** 역할 그룹에 할당 되는 **사용자 옵션** 역할)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-126">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="57e03-127">Exchange Online에서 역할 그룹에 사용자를 추가 하려면 [Exchange online에서 역할 그룹 수정을](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-127">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="57e03-128">기본 사용 권한이 있는 사용자는 [Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)대 한 액세스 권한이 있는 경우 자체 사서함에서 동일한 절차를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-128">Note that a user with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="57e03-129">EOP가 온-프레미스 Exchange 사서함을 보호 하는 독립 실행형 EOP 환경에서는 정크 메일 규칙이 메시지를 이동할 수 있도록 온-프레미스 Exchange의 메일 흐름 규칙 (전송 규칙이 라고도 함)을 구성 하 여 EOP 스팸 필터링 결과을 번역 해야 합니다. 정크 메일 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-129">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="57e03-130">자세한 내용은 [하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP 구성을](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-130">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="57e03-131">Exchange Online PowerShell을 사용 하 여 사서함에서 정크 메일 규칙을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="57e03-131">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="57e03-132">**Set-mailboxjunkemailconfiguration** cmdlet을 사용 하 여 Outlook (캐시 된 Exchange 모드) 또는 웹용 outlook에서 열린 사서함에 대해 정크 메일 규칙을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-132">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="57e03-133">사서함이 열려 있지 않으면 다음 오류가 표시 됩니다. 대량 작업에 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 대해이 오류를 표시 하지 않으려면 `-ErrorAction SlientlyContinue` **set-mailboxjunkemailconfiguration** 명령에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-133">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command</span></span>

<span data-ttu-id="57e03-134">사서함에 대해 정크 메일 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-134">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="57e03-135">이 예에서는 Ori Epstein의 사서함에 대 한 정크 메일 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-135">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="57e03-136">이 예에서는 조직의 모든 사용자 사서함에 대해 정크 메일 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-136">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="57e03-137">구문 및 매개 변수에 대 한 자세한 내용은 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-137">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).</span></span>

 <span data-ttu-id="57e03-138">**참고:**</span><span class="sxs-lookup"><span data-stu-id="57e03-138">**Notes**:</span></span>

- <span data-ttu-id="57e03-139">사용자가 자신의 사서함을 연 적이 없는 경우 이전 명령을 실행 하면 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-139">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="57e03-140">대량 작업에서이 오류가 발생 하지 않도록 설정 `-ErrorAction SlientlyContinue` 하려면 **set-mailboxjunkemailconfiguration** 명령에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-140">To suppress this error for bulk operations, add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

- <span data-ttu-id="57e03-141">정크 메일 규칙을 사용 하지 않도록 설정 하는 경우에도 Outlook 정크 메일 필터 (구성 된 방법에 따라)는 메시지의 스팸 여부를 확인 하 고 자체 스팸 결과 및 수신 허용 목록 컬렉션을 기반으로 받은 편지함 또는 정크 메일 폴더로 메시지를 이동할 수 있습니다. 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-141">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="57e03-142">자세한 내용은이 항목의 [Outlook의 정크 메일 설정](#about-junk-email-settings-in-outlook) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-142">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="57e03-143">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="57e03-143">How do you know this worked?</span></span>

<span data-ttu-id="57e03-144">사서함에서 정크 메일 규칙을 사용 하거나 사용 하지 않도록 성공적으로 설정 했는지 확인 하려면 다음 절차 중 하나를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-144">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="57e03-145">_ \<MailboxIdentity\> _ 를 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 하 여 **Enabled** 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-145">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

- <span data-ttu-id="57e03-146">_ \<MailboxIdentity\> _ 를 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 하 여 정크 메일 규칙의 **Enabled** 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-146">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value of the junk email rule.</span></span>

  ```PowerShell
  Get-InboxRule "Junk E-mail Rule" -Mailbox "<MailboxIdentity>" -IncludeHidden
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="57e03-147">Exchange Online PowerShell을 사용 하 여 사서함에 대 한 수신 허용 목록 컬렉션 구성</span><span class="sxs-lookup"><span data-stu-id="57e03-147">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="57e03-148">사서함의 수신 허용 목록 컬렉션에는 수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 수신 거부 목록이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-148">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="57e03-149">기본적으로 사용자는 Outlook 또는 웹용 Outlook에서 자체 사서함에 수신 허용 목록 모음을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-149">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="57e03-150">관리자는 **set-mailboxjunkemailconfiguration** cmdlet에 해당 하는 매개 변수를 사용 하 여 사용자의 사서함에서 수신 허용 목록 컬렉션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-150">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="57e03-151">이러한 매개 변수에 대 한 설명은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-151">These parameters are described in the following table.</span></span>

|||
|---|---|
|<span data-ttu-id="57e03-152">**Set-mailboxjunkemailconfiguration의 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="57e03-152">**Parameter on Set-MailboxJunkEmailConfiguration**</span></span>|<span data-ttu-id="57e03-153">**웹용 Outlook 설정**</span><span class="sxs-lookup"><span data-stu-id="57e03-153">**Outlook on the web setting**</span></span>|
|<span data-ttu-id="57e03-154">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="57e03-154">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="57e03-155">**다음 보낸 사람이 나 도메인에서 정크 메일 폴더로 전자 메일 이동**</span><span class="sxs-lookup"><span data-stu-id="57e03-155">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="57e03-156">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="57e03-156">_ContactsTrusted_</span></span>|<span data-ttu-id="57e03-157">**내 연락처에서 전자 메일 신뢰**</span><span class="sxs-lookup"><span data-stu-id="57e03-157">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="57e03-158">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="57e03-158">_TrustedListsOnly_</span></span>|<span data-ttu-id="57e03-159">**수신 허용-보낸 사람 및 도메인 목록 및 수신 허용-메일 그룹의 주소에서 보낸 전자 메일만 신뢰**</span><span class="sxs-lookup"><span data-stu-id="57e03-159">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="57e03-160">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="57e03-160">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="57e03-161">**이 보낸 사람 으로부터 정크 메일 폴더로 전자 메일 이동 안 함**</span><span class="sxs-lookup"><span data-stu-id="57e03-161">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="57e03-162"><sup>\*</sup>**참고**사항:</span><span class="sxs-lookup"><span data-stu-id="57e03-162"><sup>\*</sup>**Notes**:</span></span>

- <span data-ttu-id="57e03-163">Exchange Online에서 수신 허용-보낸 사람 목록 또는 _TrustedSendersAndDomains_ 매개 변수의 **도메인 항목** 은 인식 되지 않으므로 전자 메일 주소만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-163">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="57e03-164">독립 실행형 EOP에서 디렉터리 동기화를 사용 하는 경우 도메인 항목은 기본적으로 동기화 되지 않지만 도메인에 대 한 동기화를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-164">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="57e03-165">자세한 내용은 [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-165">For more information, see [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).</span></span>

- <span data-ttu-id="57e03-166">Set-mailboxjunkemailconfiguration cmdlet ( _TrustedRecipientsAndDomains_ 매개 변수는 작동 하지 않음)을 사용 하 여 수신 허용 **-** 받는 사람 목록을 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-166">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="57e03-167">수신 허용-보낸 사람 목록을 수정 하면 해당 변경 내용이 수신 허용-받는 사람 목록에 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-167">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="57e03-168">사서함에 대해 수신 허용 목록 컬렉션을 구성 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-168">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="57e03-169">여러 값을 입력 하 고 _BlockedSendersAndDomains_ 및 _TrustedSendersAndDomains_ 매개 변수에 대 한 기존 항목을 덮어쓰려면 다음 구문을 `"<Value1>","<Value2>"...`사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-169">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="57e03-170">기존의 다른 항목에 영향을 주지 않고 하나 이상의 값을 추가 하거나 제거 하려면 다음 구문을 사용 합니다.`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="57e03-170">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="57e03-171">이 예에서는 Ori Epstein의 사서함에서 수신 허용 목록 컬렉션에 대 한 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-171">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="57e03-172">Shopping@fabrikam.com 값을 수신 거부 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-172">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="57e03-173">수신 허용-보낸 사람 목록 및 안전한 받는 사람 목록에서 chris@fourthcoffee.com 값을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-173">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="57e03-174">연락처 폴더의 연락처를 신뢰할 수 있는 보낸 사람으로 처리 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-174">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="57e03-175">이 예에서는 조직의 모든 사용자 사서함에 있는 수신 거부 목록에서 contoso.com 도메인을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-175">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="57e03-176">구문 및 매개 변수에 대 한 자세한 내용은 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-176">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).</span></span>

 <span data-ttu-id="57e03-177">**참고:**</span><span class="sxs-lookup"><span data-stu-id="57e03-177">**Notes**:</span></span>

- <span data-ttu-id="57e03-178">사용자가 자신의 사서함을 연 적이 없는 경우에는 이전 명령을 실행할 때 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-178">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="57e03-179">대량 작업에서이 오류가 발생 하지 않도록 설정 `-ErrorAction SlientlyContinue` 하려면 **set-mailboxjunkemailconfiguration** 명령에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-179">To suppress this error for bulk operations, add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

- <span data-ttu-id="57e03-180">사서함에서 정크 메일 규칙이 사용 하지 않도록 설정 된 경우에도 수신 허용 목록 컬렉션을 구성할 수 있으며 Outlook 정크 메일 필터는 메시지를 받은 편지함 또는 정크 메일 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-180">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="57e03-181">자세한 내용은이 항목의 [Outlook의 정크 메일 설정](#about-junk-email-settings-in-outlook) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-181">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

- <span data-ttu-id="57e03-182">Outlook 정크 메일 필터에는 추가 수신 허용 목록 모음 설정 (예: **수신 허용-보낸 사람 목록에 전자 메일을 자동으로 추가**)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-182">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="57e03-183">자세한 내용은 [정크 메일 필터를 사용 하 여 표시 되는 메시지 제어](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-183">For more information, see [Use Junk Email Filters to control which messages you see](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="57e03-184">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="57e03-184">How do you know this worked?</span></span>

<span data-ttu-id="57e03-185">사서함에 수신 허용 목록 컬렉션을 성공적으로 구성 했는지 확인 하려면 다음 절차 중 하나를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-185">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="57e03-186">_ \<MailboxIdentity\> _ 를 사서함의 이름, 별칭 또는 전자 메일 주소로 바꾸고 다음 명령을 실행 하 여 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-186">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="57e03-187">값 목록이 너무 길면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-187">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="57e03-188">Outlook의 정크 메일 설정 정보</span><span class="sxs-lookup"><span data-stu-id="57e03-188">About junk email settings in Outlook</span></span>

<span data-ttu-id="57e03-189">Outlook에서 사용할 수 있는 클라이언트 쪽 정크 메일 필터 설정을 사용 하거나 사용 하지 않도록 설정 하 고 구성 하려면 그룹 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-189">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="57e03-190">자세한 내용은 [office 365 ProPlus, office 2019 및 office 2016 용 관리 템플릿 파일 (ADMX/ADML) 및 Office 사용자 지정 도구](https://www.microsoft.com/download/details.aspx?id=49030)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-190">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Office 365 ProPlus, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).</span></span>

<span data-ttu-id="57e03-191">Outlook 정크 메일 필터를 기본값으로 설정 하 고 **홈** \> **정크** \> **메일 옵션** \> **옵션**에서 **자동 필터링** 을 사용 하지 않으면 outlook이 massages로 분류를 시도 하지 않지만 수신 허용-보낸 사람 목록, 수신 허용-받는 사람 목록 및 수신 거부 목록에 있는 수신 허용 목록 컬렉션을 통해 메시지를 배달 후 정크 메일 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-191">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="57e03-192">이러한 설정에 대 한 자세한 내용은 [정크 메일 필터 개요](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-192">For more information about these settings, see [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="57e03-193">Outlook 정크 메일 필터를 **낮음** 또는 **높음으로**설정 하면 outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용 하 여 스팸 메일을 식별 하 고 정크 메일로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-193">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="57e03-194">이 스팸 분류는 EOP에 의해 결정 되는 SCL (스팸 지 수)과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-194">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="57e03-195">실제로 Outlook은 EOP에서 SCL을 무시 합니다 (EOP가 스팸 필터링을 건너뛰도록 메시지를 표시 하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="57e03-195">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="57e03-196">물론 EOP의 스팸 결과와 Outlook이 같을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-196">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="57e03-197">이러한 설정에 대 한 자세한 내용은 [정크 메일 필터에서 보호 수준 변경을](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57e03-197">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="57e03-198">11 월 2016 일에 Microsoft는 Exchange 및 Outlook의 SmartScreen 필터에 대 한 스팸 정의 업데이트 생성을 중지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-198">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="57e03-199">기존 SmartScreen 스팸 정의는 그대로 남아 있지만 해당 효율성은 시간이 지남에 따라 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-199">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="57e03-200">자세한 내용은 [Outlook 및 Exchange에서 SmartScreen 지원 삭제](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57e03-200">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="57e03-201">따라서 Outlook 정크 메일 필터는 사서함에서 정크 메일 규칙을 사용할 수 없는 경우에도 사서함의 수신 허용 목록 모음과 자체 스팸 분류를 사용 하 여 메시지를 정크 메일 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-201">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="57e03-202">Outlook 및 웹용 Outlook은 모두 수신 허용 목록 컬렉션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-202">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="57e03-203">수신 허용 목록 컬렉션은 Exchange Online 사서함에 저장 되므로 Outlook에서 수신 허용 목록 컬렉션에 대 한 변경 내용은 웹용 Outlook에 표시 되며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="57e03-203">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

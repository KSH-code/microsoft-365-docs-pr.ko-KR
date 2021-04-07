---
title: 웹에서 Outlook에서 정크 및 피싱 전자 메일 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online의 웹용 Outlook(Outlook Web App)에서 정크 메일이 아닌 기본 제공 정크 및 피싱 전자 메일 보고 옵션에 대해 알아보고 사용자에 대해 이러한 보고 옵션을 사용하지 않도록 설정하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615215"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="6a8db-103">Exchange Online에서 웹에서 Outlook에서 정크 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="6a8db-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6a8db-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="6a8db-104">**Applies to**</span></span>
- [<span data-ttu-id="6a8db-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6a8db-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6a8db-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="6a8db-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6a8db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a8db-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6a8db-108">Exchange Online 또는 하이브리드 최신 인증을 사용하는 사서함이 있는 Microsoft [](../../enterprise/hybrid-modern-auth-overview.md)365 조직에서는 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 EOP(Exchange Online Protection)에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a8db-109">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6a8db-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6a8db-110">최상의 사용자 제출 환경을 위해 보고서 메시지 및 피싱 보고 추가 기능을 사용하는 것이 좋습니다. 자세한 [내용은 보고서 메시지](./enable-the-report-message-add-in.md) 추가 기능 사용 및 [피싱](./enable-the-report-phish-add-in.md) 보고서 추가 기능 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a8db-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="6a8db-111">Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터에서 제출 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6a8db-112">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6a8db-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="6a8db-113">관리자는 사용자가 웹용 Outlook에서 Microsoft에 메시지를 보고하는 기능을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="6a8db-114">자세한 내용은 이 문서 부분의 웹용 [Outlook에서](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정크 메일 보고 사용 또는 사용 안 하도록 설정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a8db-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="6a8db-115">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6a8db-116">자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6a8db-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="6a8db-117">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6a8db-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="6a8db-118">웹용 Outlook에서 정크 메일 보고 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6a8db-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="6a8db-119">기본적으로 사용자는 웹용 Outlook에서 분석을 위해 스팸 가짓 긍정, 거짓 부정 및 피싱 메시지를 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="6a8db-120">관리자는 Exchange Online PowerShell에서 웹에서 Outlook 사서함 정책을 구성하여 사용자가 Microsoft에 스팸 가긍성 및 스팸 거짓 부정을 보고하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="6a8db-121">사용자가 Microsoft에 피싱 메시지를 보고하는 기능을 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a8db-122">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6a8db-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6a8db-123">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a8db-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6a8db-124">이 문서의 절차를 수행하려면 먼저 Exchange Online에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="6a8db-125">특히 조직 관리 및 받는 사람 관리 역할 그룹에 기본적으로  할당되는  받는 사람 정책 또는 **메일** 받는 사람 역할이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="6a8db-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="6a8db-126">Exchange Online의 역할 그룹에 대한 자세한 내용은 [Exchange Online의](/exchange/permissions-exo/permissions-exo) 사용 권한 및 Exchange Online에서 역할 그룹 [수정을 참조하세요.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="6a8db-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="6a8db-127">모든 조직에는 OwaMailboxPolicy-Default라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="6a8db-128">사용자 지정 정책은 기본 정책 전에 범위가 지정한 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="6a8db-129">웹용 Outlook 사서함 정책에 대한 자세한 내용은 Exchange Online의 웹용 [Outlook 사서함 정책을 참조하세요.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="6a8db-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="6a8db-130">정크 메일 보고를 사용할 수 없는 경우 웹용 Outlook에서 메시지를 정크 메일로 표시하거나 정크 메일 아님으로 표시하는 기능을 제거하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="6a8db-131">정크 메일 폴더에서 메시지를 선택하고 정크 메일 아님을 클릭하면 메시지가 받은 편지함으로 다시  \>  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="6a8db-132">다른 전자 메일 폴더에서 메시지를 선택하고  정크 정크를 클릭하면 메시지가 여전히 정크 메일 \>  폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="6a8db-133">더 이상 사용할 수 없는 것은 메시지를 Microsoft에 보고하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="6a8db-134">Exchange Online PowerShell을 사용하여 웹용 Outlook에서 정크 메일 보고를 사용하지 않도록 설정하거나 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6a8db-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="6a8db-135">기존 웹에서 Outlook 사서함 정책 및 정크 메일 보고 상태를 찾으면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="6a8db-136">웹용 Outlook에서 정크 메일 보고를 사용하지 않도록 설정하거나 사용하도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6a8db-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="6a8db-137">이 예에서는 기본 정책에서 정크 메일 보고를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="6a8db-138">이 예에서는 Contoso Managers라는 사용자 지정 정책에서 정크 메일 보고를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="6a8db-139">구문과 매개 변수에 대한 자세한 내용은 [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) 및 [Set-OwaMailboxPolicy를 참조하십시오.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="6a8db-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6a8db-140">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="6a8db-140">How do you know this worked?</span></span>

<span data-ttu-id="6a8db-141">웹용 Outlook에서 정크 메일 보고를 사용하도록 설정하거나 사용하지 않도록 설정한 경우 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6a8db-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="6a8db-142">Exchange Online PowerShell에서 다음 명령을 실행하고 **ReportJunkEmailEnabled 속성** 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="6a8db-143">웹에서 Outlook에서 영향을 받는 사용자의 사서함을 열고 받은 편지함에서  메시지를 선택하고 정크 정크를 클릭한 다음 메시지를 Microsoft에 보고하라는 메시지가 Microsoft에 보고되어 있는지 또는 표시되지 않는지 \>  확인<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a8db-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="6a8db-144">웹에서 Outlook에서 영향을 받는 사용자의 사서함을 열고, 정크 메일 폴더에서 메시지를 선택하고, 정크 정크를 클릭하고, 메시지를 Microsoft에 보고하라는 메시지가 Microsoft에 보고되어 있는지 또는 표시되지 않는지  \>  확인합니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a8db-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="6a8db-145"><sup>\*</sup> 사용자는 메시지를 보고하는 동안 메시지를 보고하라는 메시지를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8db-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="6a8db-146">웹에서 Outlook에서 이 설정을 확인:</span><span class="sxs-lookup"><span data-stu-id="6a8db-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="6a8db-147">웹에서 Outlook 설정 설정 아이콘 모든 Outlook 설정 정크  ![ 메일 ](../../media/owa-settings-icon.png) \>  \> **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a8db-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="6a8db-148">보고 **섹션에서** 값을 확인 합니다. **보고서를 보내기 전에 요청 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a8db-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![웹에서 Outlook 정크 메일 보고 설정](../../media/owa-junk-email-reporting-options.png)
---
title: 웹에서 Outlook에서 정크 메일 및 피싱 메일 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online의 웹용 Outlook(Outlook Web App)에서 정크 메일이 아닌 기본 제공 정크 및 피싱 전자 메일 보고 옵션에 대해 알아보고 사용자에 대해 이러한 보고 옵션을 사용하지 않도록 설정하는 방법을 알 수 있습니다.
ms.openlocfilehash: 0032e807961aed60128d6863899ae0de32d1a627
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659318"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="2081d-103">Exchange Online의 웹에서 Outlook에서 정크 메일 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="2081d-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2081d-104">Exchange Online에 사서함이 있는 Microsoft 365 조직에서는 웹용 Outlook(이전의 Outlook Web App)의 기본 제공 보고 옵션을 사용하여 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 EOP(Exchange Online Protection)에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2081d-105">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2081d-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2081d-106">Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터에서 제출 포털을 & 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2081d-107">자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 [Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="2081d-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="2081d-108">관리자는 사용자가 웹용 Outlook에서 Microsoft에 메시지를 보고하는 기능을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="2081d-109">자세한 내용은 이 문서 부분의 웹용 [Outlook](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 섹션에서 정크 메일 보고를 사용하지 않도록 설정하거나 사용하도록 설정하는 기능을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2081d-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="2081d-110">보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="2081d-111">자세한 내용은 사용자 제출 [정책을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="2081d-111">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="2081d-112">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2081d-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="2081d-113">웹에서 Outlook에서 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="2081d-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="2081d-114">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법 중 하나를 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="2081d-115">메시지를 선택하고 도구  모음에서 정크를 클릭한  다음 정크 또는 피싱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/owa-report-junk.png)

   - <span data-ttu-id="2081d-117">하나 이상의 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 정크 메일로 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="2081d-118">나타나는 대화 상자에서 보고서를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="2081d-119">마음이 바뀌면 보고 안 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="2081d-120">정크</span><span class="sxs-lookup"><span data-stu-id="2081d-120">Junk</span></span>|<span data-ttu-id="2081d-121">피싱</span><span class="sxs-lookup"><span data-stu-id="2081d-121">Phishing</span></span>|
   |:---:|:---:|
   |![정크로 보고 대화 상자](../../media/owa-report-as-junk-dialog.png)|![피싱으로 보고 대화 상자](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="2081d-124">선택한 메시지가 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2081d-125">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="2081d-126">웹용 Outlook의 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="2081d-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="2081d-127">정크 메일 폴더에서 다음 방법 중 하나를 사용하여 스팸 가긍성 또는 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="2081d-128">메시지를 선택하고 도구  모음에서 정크 메일 아님을 클릭한 다음 정크 메일 아님 또는 **피싱을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="2081d-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![리본에서 정크 메일이 아니거나 피싱 메일 보고](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="2081d-130">하나 이상의 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 정크 메일 아님으로 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="2081d-131">나타나는 대화 상자에서 정보를 읽고 보고서를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="2081d-132">마음이 바뀌면 보고 안 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2081d-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="2081d-133">정크 아님</span><span class="sxs-lookup"><span data-stu-id="2081d-133">Not Junk</span></span>|<span data-ttu-id="2081d-134">피싱</span><span class="sxs-lookup"><span data-stu-id="2081d-134">Phishing</span></span>|
   |:---:|:---:|
   |![정크 아님으로 보고 대화 상자](../../media/owa-report-as-not-junk-dialog.png)|![피싱으로 보고 대화 상자](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="2081d-137">선택한 메시지가 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2081d-138">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2081d-139">웹용 Outlook에서 정크 메일 보고를 사용하지 않도록 설정하거나 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="2081d-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="2081d-140">기본적으로 사용자는 웹용 Outlook에서 분석을 위해 스팸 오판정, 거짓 부정 및 피싱 메시지를 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="2081d-141">관리자는 Exchange Online PowerShell에서 웹에서 Outlook 사서함 정책을 구성하여 사용자가 Microsoft에 스팸 가긍성 및 스팸 거짓 부정을 보고하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="2081d-142">사용자가 Microsoft에 피싱 메시지를 보고하는 기능을 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2081d-143">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2081d-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2081d-144">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2081d-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2081d-145">이 문서의 절차를 수행하려면 먼저 Exchange Online에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-145">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="2081d-146">특히 조직 관리 및 받는 사람 관리 역할 그룹에 기본적으로  할당되는  받는 사람 정책 또는 **메일** 받는 사람 역할이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="2081d-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="2081d-147">Exchange Online의 역할 그룹에 대한 자세한 내용은 [Exchange Online의](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 사용 권한 및 Exchange Online의 역할 [그룹 수정을 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="2081d-147">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="2081d-148">모든 조직에는 OwaMailboxPolicy-Default라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="2081d-149">사용자 지정 정책은 기본 정책 전에 범위가 지정한 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="2081d-150">웹용 Outlook 사서함 정책에 대한 자세한 내용은 [Exchange Online의](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)웹용 Outlook 사서함 정책을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2081d-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="2081d-151">정크 메일 보고를 사용할 수 없는 경우 웹용 Outlook에서 메시지를 정크 메일로 표시하거나 정크 메일 아님으로 표시하는 기능을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="2081d-152">정크 메일 폴더에서 메시지를 선택하고 정크 메일 아님을 클릭하면 메시지가 받은 편지함으로 다시  \>  이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="2081d-153">다른 전자 메일 폴더에서 메시지를 선택하고  정크 메일을 클릭하면 메시지가 여전히 정크 메일 \>  폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="2081d-154">더 이상 사용할 수 없는 메시지는 Microsoft에 메시지를 보고하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2081d-155">Exchange Online PowerShell을 사용하여 웹용 Outlook에서 정크 메일 보고를 사용하지 않도록 설정하거나 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="2081d-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="2081d-156">기존 웹에서 Outlook 사서함 정책 및 정크 메일 보고 상태를 찾으면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="2081d-157">웹용 Outlook에서 정크 메일 보고를 사용하지 않도록 설정하거나 사용하도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2081d-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="2081d-158">이 예에서는 기본 정책에서 정크 메일 보고를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="2081d-159">이 예에서는 Contoso Managers라는 사용자 지정 정책에서 정크 메일 보고를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="2081d-160">구문과 매개 변수에 대한 자세한 내용은 [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) 및 [Set-OwaMailboxPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="2081d-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2081d-161">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="2081d-161">How do you know this worked?</span></span>

<span data-ttu-id="2081d-162">웹용 Outlook에서 정크 메일 보고를 사용하도록 설정하거나 사용하지 않도록 설정한 경우 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2081d-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="2081d-163">Exchange Online PowerShell에서 다음 명령을 실행하고 **ReportJunkEmailEnabled** 속성 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="2081d-164">웹에서 Outlook에서 영향을 받는 사용자의 사서함을 열고 받은 편지함에서  메시지를 선택하고 정크를 클릭한 다음 메시지를 Microsoft에 보고하라는 메시지가 \>  표시되는지 확인<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2081d-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="2081d-165">웹에서 Outlook에서 영향을 받는 사용자의 사서함을 열고, 정크 메일 폴더에서 메시지를 선택하고, 정크를 클릭하고, Microsoft에 메시지를 보고하라는 메시지가  \>  표시되는지 확인합니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2081d-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="2081d-166"><sup>\*</sup> 사용자는 메시지를 보고하는 동안 메시지를 보고하라는 메시지를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2081d-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="2081d-167">웹에서 Outlook에서 이 설정을 확인:</span><span class="sxs-lookup"><span data-stu-id="2081d-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="2081d-168">Click **Settings** ![ Outlook on the web settings icon View all ](../../media/owa-settings-icon.png) \> **Outlook settings** \> **Junk email.**</span><span class="sxs-lookup"><span data-stu-id="2081d-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="2081d-169">**Reporting(보고) 섹션에서** 값을 확인하고 보고서를 보내기 **전에 질문하세요.**</span><span class="sxs-lookup"><span data-stu-id="2081d-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![웹에서 Outlook 정크 메일 보고 설정](../../media/owa-junk-email-reporting-options.png)

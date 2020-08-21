---
title: 웹용 Outlook에서 정크 및 피싱 전자 메일 보고
f1.keywords:
- NOCSH
ms.author: chrisda
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
description: 관리자는 Exchange Online에서 웹용 Outlook(Outlook Web App)의 기본 제공 정크 메일 보고 옵션과, 사용자에 대해 이러한 보고 옵션을 사용하지 않도록 설정하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 947f9bb9c1c686b549d83b27c262e86eda0d5008
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826544"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="09134-103">Exchange Online에서 웹용 Outlook에서 정크 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="09134-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="09134-104">Exchange Online의 사서함이 있는 Microsoft 365 조직에서, 웹용 Outlook(이전의 Outlook Web App)에 있는 기본 제공 보고 옵션을 사용하여 가양성(스팸으로 정상적인 전자 메일) 오판정), 거짓 부정(잘못된 전자 메일이 허용됨) 및 EOP(Exchange Online Protection)에 피싱 메시지를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="09134-105">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="09134-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="09134-106">Exchange Online 사서함이 있는 조직의 관리자는 보안 그룹 규정 준수 센터의 전송 포털을 & 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="09134-107">자세한 내용은 [관리자 제출 사용을 참조하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출하세요.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="09134-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="09134-108">관리자는 사용자가 웹용 Outlook에서 Microsoft에 메시지를 보고하는 기능을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="09134-109">자세한 내용은 이 항목 [뒷부분에 나오는 웹 버전의 Outlook에서 정크 메일 보고를 사용하거나](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 사용하지 않도록 설정을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09134-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="09134-110">지정한 사서함으로 복사 또는 리디렉션하도록 보고된 메시지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="09134-111">자세한 내용은 [Exchange Online에서 스팸 및 피싱 메시지의 사용자 전송을 위한 사서함 지정을 참조하세요.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="09134-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="09134-112">Microsoft에 메시지를 보고하는 방법에 대한 자세한 내용은 [Microsoft로 보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="09134-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="09134-113">웹용 Outlook에서 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="09134-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="09134-114">정크 메일을 제외한 받은 편지함 또는 기타 전자 메일 폴더의 메시지의 경우, 다음 방법 중 하나를 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="09134-115">메시지를 선택하고 도구 **모음에서 정크를** 클릭한 다음 **정크 또는** **피싱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 메일 보고](../../media/owa-report-junk.png)

   - <span data-ttu-id="09134-117">하나 이상의 메시지를 선택하고 마우스 오른쪽 단추로 클릭한 다음 **정크로 표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="09134-118">대화 상자가 표시되면 보고서를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="09134-119">마이그라이드를 변경한 경우 **"보고서 금지"를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="09134-120">정크어</span><span class="sxs-lookup"><span data-stu-id="09134-120">Junk</span></span>|<span data-ttu-id="09134-121">피싱</span><span class="sxs-lookup"><span data-stu-id="09134-121">Phishing</span></span>|
   |:---:|:---:|
   |![정크 메일로 보고 대화 상자](../../media/owa-report-as-junk-dialog.png)|![피싱 대화 상자로 보고](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="09134-124">선택한 메시지가 분석을 위해 Microsoft에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="09134-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="09134-125">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="09134-126">웹용 Outlook에서 정크 메일 폴더로부터 스팸이 아닌 메시지 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="09134-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="09134-127">정크 메일 폴더에서 다음 방법 중 하나를 사용하여 스팸 가양성 또는 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="09134-128">메시지를 선택하고 도구 **모음에서 정크** 메일 아님을 클릭한 후에 정크 **또는** **피싱 아님을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 메일 보고](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="09134-130">하나 이상의 메시지를 선택하고 마우스 오른쪽 단추로 클릭한 다음 정크 메일 **아님으로 표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="09134-131">In the dialog that read the information and click **Report.**</span><span class="sxs-lookup"><span data-stu-id="09134-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="09134-132">마이그라이드를 변경한 경우 **"보고서 금지"를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="09134-133">정크 메일 아님</span><span class="sxs-lookup"><span data-stu-id="09134-133">Not Junk</span></span>|<span data-ttu-id="09134-134">피싱</span><span class="sxs-lookup"><span data-stu-id="09134-134">Phishing</span></span>|
   |:---:|:---:|
   |![정크 메일 아님 대화 상자로 보고](../../media/owa-report-as-not-junk-dialog.png)|![피싱 대화 상자로 보고](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="09134-137">선택한 메시지가 분석을 위해 Microsoft에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="09134-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="09134-138">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="09134-139">웹의 Outlook에서 정크 메일 보고 기능 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="09134-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="09134-140">기본적으로 사용자는 웹에서 Outlook에서 분석을 위해 스팸 가양성, 가양성 및 피싱 메시지를 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="09134-141">관리자는 Exchange Online PowerShell에서 웹 사서함 정책의 Outlook을 구성하여 사용자가 스팸 오판정 및 스팸 거짓 부정을 Microsoft에 보고하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="09134-142">사용자가 Microsoft에 피싱 메시지를 보고하는 기능을 사용하지 않도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="09134-143">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="09134-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="09134-144">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09134-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="09134-145">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="09134-146">특히 조직 관리 및 **받는 사람** 관리 역할 **그룹에 할당된** Exchange Online의 받는 사람 정책 **또는** **메일 받는 사람** 역할이 기본적으로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="09134-147">Exchange Online의 역할 그룹에 대한 자세한 내용은 Exchange [Online에서 역할 그룹 수정을 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="09134-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="09134-148">모든 조직에는 OwaMailboxPolicy-Default라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="09134-149">기본 정책 앞의 범위 사용자에게 사용자 지정 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09134-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="09134-150">웹에서 Outlook 사서함 정책에 대한 자세한 내용은 [Exchange Online의 웹에서 Outlook 사서함 정책을 참조하십시오.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="09134-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="09134-151">정크 메일 보고를 사용하지 않도록 설정해도 웹용 Outlook에서 메시지를 정크 메일로 표시하거나 정크 메일 아님으로 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="09134-152">정크 메일 폴더에서 메시지를 선택한 다음 정크 메일 **아님을** 클릭하면 메시지가 다시 \> **Not junk** 받은 편지함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="09134-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="09134-153">다른 전자 메일 폴더에서 메시지를 찾아 정크 **메일을** 클릭해도 메시지가 \> **Junk** 계속 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="09134-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="09134-154">더 이상 사용할 수 없는 정의는 메시지를 Microsoft에 보고하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="09134-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="09134-155">Exchange Online PowerShell을 사용하여 웹용 Outlook에서 정크 메일 보고 기능 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="09134-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="09134-156">웹에서 Outlook 사서함 정책 및 정크 메일 보고 상태를 찾으려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="09134-157">웹상의 Outlook에서 정크 메일 보고를 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="09134-158">이 예에서는 기본 정책에서 정크 메일 보고를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="09134-159">이 예에서는 Contoso Managers라는 사용자 지정 정책에서 정크 메일 보고를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="09134-160">구문과 매개 변수에 대한 자세한 내용은 [Get-OwaMailboxPolicy 및](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) [Set-OwaMailboxPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="09134-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="09134-161">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="09134-161">How do you know this worked?</span></span>

<span data-ttu-id="09134-162">웹에서 Outlook에서 정크 메일 보고를 사용하거나 사용하지 않도록 설정되었는지 확인하려면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="09134-163">Exchange Online PowerShell에서 다음 명령을 실행하고 **ReportJunkEmailEnabled 속성 값을** 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="09134-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="09134-164">웹용 Outlook에서 영향을 받는 사용자의 사서함을 열고 받은 편지함에서 메시지를 선택한 후, **정크 메일을** \> **클릭하여** Microsoft에 메시지를 보고하는 지 확인하거나 표시되지 않도록 합니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="09134-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="09134-165">웹용 Outlook에서 영향을 받는 사용자사서함을 열고 정크 메일 폴더에서 메시지를 선택한 후 정크 메일을 **Junk** 클릭하고, 정크 메일을 \> **클릭하여** Microsoft에 메시지를 보고하는지 또는 표시되지 않도록 확인합니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="09134-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="09134-166"><sup>\*</sup> 사용자는 메시지를 보고하는 동안 메시지를 보고하는 메시지를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09134-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="09134-167">웹용 Outlook에서 이 설정을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="09134-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="09134-168">웹 **설정** ![ 아이콘의 설정 Outlook을 ](../../media/owa-settings-icon.png) \> **클릭하면 모든 Outlook 설정** \> **정크 메일을 볼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="09134-169">보고 **섹션에서** 값을 확인합니다. **보고서를 보내기 전에 도와줍니다.**</span><span class="sxs-lookup"><span data-stu-id="09134-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![웹용 Outlook 정크 메일 보고 설정](../../media/owa-junk-email-reporting-options.png)

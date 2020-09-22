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
description: 관리자는 Exchange Online의 Outlook 웹 (Outlook Web App)에서 기본 제공 정크 메일, 정크 메일이 아닌 피싱 메일로 보고 옵션, 사용자를 위해 이러한 보고 옵션을 사용 하지 않도록 설정 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 75be22d6ec38ca3c8d11836ea28c7af74b93f14c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201246"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="67d97-103">Exchange Online의 웹용 Outlook에서 정크 메일 및 피싱 메일로 신고</span><span class="sxs-lookup"><span data-stu-id="67d97-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="67d97-104">Exchange Online의 사서함이 있는 Microsoft 365 조 직에서는 웹에서 Outlook (이전의 Outlook Web App)의 기본 제공 보고 옵션을 사용 하 여 가양성 (스팸으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 전자 메일 허용) 및 EOP (Exchange Online Protection)에 대 한 피싱 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67d97-105">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="67d97-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67d97-106">Exchange Online 사서함을 사용 하는 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="67d97-107">자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67d97-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="67d97-108">관리자는 사용자가 웹용 Outlook에서 Microsoft에 메시지를 보고 하는 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="67d97-109">자세한 내용은이 항목 뒷부분에 나오는 [웹용 Outlook에서 정크 메일 보고 사용 안 함 또는 사용](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d97-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="67d97-110">보고 된 메시지가 사용자가 지정한 사서함으로 복사 되거나 리디렉션되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="67d97-111">자세한 내용은 [Exchange Online의 스팸 및 피싱 메시지에 대 한 사용자 제출을 위한 사서함 지정](user-submission.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67d97-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="67d97-112">Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d97-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="67d97-113">웹용 Outlook에서 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="67d97-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="67d97-114">정크 메일을 제외한 받은 편지함 또는 다른 모든 전자 메일 폴더의 메시지에 대해 다음 방법 중 하나를 사용 하 여 스팸 및 피싱 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="67d97-115">메시지를 선택 하 고 도구 모음에서 **정크 메일** 을 클릭 한 다음 **정크** 또는 **피싱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/owa-report-junk.png)

   - <span data-ttu-id="67d97-117">하나 이상의 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일로 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="67d97-118">대화 상자가 나타나면 **보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="67d97-119">생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="67d97-120">차단할</span><span class="sxs-lookup"><span data-stu-id="67d97-120">Junk</span></span>|<span data-ttu-id="67d97-121">피싱</span><span class="sxs-lookup"><span data-stu-id="67d97-121">Phishing</span></span>|
   |:---:|:---:|
   |![정크 메일로 신고 대화 상자](../../media/owa-report-as-junk-dialog.png)|![피싱 메일로 신고 대화 상자](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="67d97-124">선택한 메시지가 분석을 위해 Microsoft로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="67d97-125">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="67d97-126">웹용 Outlook의 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지가 보고 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="67d97-127">정크 메일 폴더에서 다음 방법 중 하나를 사용 하 여 스팸 가양성 또는 피싱 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="67d97-128">메시지를 선택 하 고 도구 모음에서 **정크 메일** 아님으로 클릭 한 다음 **정크** 또는 **피싱**아님을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="67d97-130">하나 이상의 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일 아님으로 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="67d97-131">대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="67d97-132">생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="67d97-133">정크 메일 아님</span><span class="sxs-lookup"><span data-stu-id="67d97-133">Not Junk</span></span>|<span data-ttu-id="67d97-134">피싱</span><span class="sxs-lookup"><span data-stu-id="67d97-134">Phishing</span></span>|
   |:---:|:---:|
   |![정크 메일 아님으로 보고 대화 상자](../../media/owa-report-as-not-junk-dialog.png)|![피싱 메일로 신고 대화 상자](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="67d97-137">선택한 메시지가 분석을 위해 Microsoft로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="67d97-138">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="67d97-139">웹용 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용</span><span class="sxs-lookup"><span data-stu-id="67d97-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="67d97-140">기본적으로 사용자는 웹용 Outlook에서 분석을 위해 Microsoft에 가짜 긍정, 거짓 네거티브 및 피싱 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="67d97-141">관리자는 Exchange Online PowerShell에서 웹 사서함 정책에 대 한 Outlook을 구성 하 여 사용자가 스팸 가양성 및 스팸 거짓 네거티브를 Microsoft에 보고 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="67d97-142">사용자가 피싱 메시지를 Microsoft에 보고 하는 기능을 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67d97-143">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="67d97-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67d97-144">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67d97-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="67d97-145">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="67d97-146">특히 **조직 관리** 및 **받는 사람 관리** 역할 그룹에 기본적으로 할당 되는 **받는 사람 정책** 또는 **메일 받는 사람** 역할이 Exchange Online에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="67d97-147">Exchange Online의 역할 그룹에 대 한 자세한 내용은 [Exchange online에서 역할 그룹 수정을](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d97-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="67d97-148">모든 조직에는 Set-owamailboxpolicy 라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="67d97-149">사용자 지정 정책은 기본 정책 이전의 범위 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="67d97-150">웹 사서함 정책의 Outlook에 대 한 자세한 내용은 [Exchange Online의 웹 사서함 정책에서 outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d97-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="67d97-151">정크 메일 보고를 사용 하지 않도록 설정 해도 해당 메시지를 웹용 Outlook에서 정크 메일로 표시 하는 기능이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="67d97-152">정크 메일 폴더에서 메시지를 선택 하는 경우 **정크 메일이** 아닌 정크 메일이 아닌 클릭 \> **Not junk** 해도 메시지를 다시 받은 편지 함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="67d97-153">다른 전자 메일 폴더에서 메시지를 선택 하 고 **정크** \> **정크** 을 클릭 해도 메시지가 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="67d97-154">더 이상 사용할 수 없는 작업은 Microsoft에 메시지를 보고 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="67d97-155">웹에서 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용 하도록 설정 하려면 Exchange Online PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="67d97-156">웹 사서함 정책 및 정크 메일 보고 상태에 대 한 기존 Outlook을 찾으려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="67d97-157">웹용 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용 하도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="67d97-158">이 예에서는 기본 정책에서 정크 메일 보고를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="67d97-159">이 예에서는 Contoso 관리자 라는 사용자 지정 정책에서 정크 메일 보고를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="67d97-160">구문과 매개 변수에 대 한 자세한 내용은 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) 및 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d97-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="67d97-161">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="67d97-161">How do you know this worked?</span></span>

<span data-ttu-id="67d97-162">웹용 Outlook에서 정크 메일 보고를 사용 하거나 사용 하지 않도록 설정 했는지 확인 하려면 다음 단계 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="67d97-163">Exchange Online PowerShell에서 다음 명령을 실행 하 고 **ReportJunkEmailEnabled** 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="67d97-164">영향 받는 사용자의 사서함을 웹에서 열고, 받은 편지함에서 메시지를 선택 하 고, **정크** \> **메일** 을 클릭 하 고, Microsoft에 게 메시지를 보고할지 묻는 메시지가 표시 되는지 확인 합니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d97-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="67d97-165">영향을 받는 사용자의 사서함을 웹에서 열고 정크 메일 폴더에서 메시지를 선택 하 고 **정크** 메일로 확인을 클릭 하 \> **Junk** 고 Microsoft에 게 메시지를 보고할지 여부를 묻는 메시지가 표시 되는지 여부를 결정 합니다.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d97-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="67d97-166"><sup>\*</sup> 사용자는 메시지를 보고 하는 동안 메시지를 보고 하 라는 메시지가 표시 되지 않도록 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="67d97-167">웹용 Outlook에서이 설정을 확인 하려면:</span><span class="sxs-lookup"><span data-stu-id="67d97-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="67d97-168">**Settings** ![ 웹 설정 아이콘의 outlook 설정을 클릭 하 여 ](../../media/owa-settings-icon.png) \> **모든 outlook 설정** \> **정크 메일**을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="67d97-169">**보고** 섹션 **에서 다음 값**을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d97-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![웹용 Outlook 정크 메일 보고 설정](../../media/owa-junk-email-reporting-options.png)

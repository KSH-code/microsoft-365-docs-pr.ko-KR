---
title: '웹용 Outlook에서 정크 전자 메일 및 피싱 사기 보고 '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Office 365 Exchange Online 사서함이 있는 사용자는 웹에서 Outlook (Outlook Web App)을 사용 하 여 Microsoft에 분석용 스팸, 스팸 아님 및 피싱 메시지를 제출할 수 있습니다.
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033707"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="3d41b-103">Office 365에서 웹용 Outlook에 정크 및 피싱 전자 메일 보고</span><span class="sxs-lookup"><span data-stu-id="3d41b-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="3d41b-104">Exchange Online 사서함을 사용 하는 Office 365 고객의 경우에는 웹에서 Outlook (이전의 Outlook Web App)의 기본 제공 보고 옵션을 사용 하 여 가양성 (스팸으로 표시 된 좋은 전자 메일), 거짓 네거티브 (잘못 된 전자 메일 허용)를 제출할 수 있습니다. EOP (Exchange Online Protection)에 대 한 피싱 메시지</span><span class="sxs-lookup"><span data-stu-id="3d41b-104">If you're an Office 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d41b-105">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="3d41b-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3d41b-106">Exchange Online 사서함을 사용 하는 Office 365 조직의 관리자는 Office 365 보안 & 준수 센터의 전송 포털을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-106">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3d41b-107">자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d41b-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="3d41b-108">관리자는 사용자가 웹용 Outlook에서 Microsoft에 메시지를 보고 하는 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="3d41b-109">자세한 내용은이 항목 뒷부분에 나오는 [웹용 Outlook에서 정크 메일 보고 사용 안 함 또는 사용](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d41b-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="3d41b-110">Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [Office 365에서 microsoft에 메시지 및 파일](report-junk-email-messages-to-microsoft.md)보고를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d41b-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="3d41b-111">웹용 Outlook에서 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="3d41b-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="3d41b-112">정크 메일을 제외한 받은 편지함 또는 다른 모든 전자 메일 폴더의 메시지에 대해 다음 방법 중 하나를 사용 하 여 스팸 및 피싱 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="3d41b-113">메시지를 선택 하 고 도구 모음에서 **정크 메일** 을 클릭 한 다음 **정크** 또는 **피싱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/owa-report-junk.png)

   - <span data-ttu-id="3d41b-115">하나 이상의 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일로 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="3d41b-116">대화 상자가 나타나면 **보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="3d41b-117">생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-117">If you change your mind, click **Don't Report**.</span></span>

   ![정크 메일로 신고 대화 상자](../../media/owa-report-as-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="3d41b-120">선택한 메시지가 분석을 위해 Microsoft로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="3d41b-121">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="3d41b-122">웹용 Outlook의 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지가 보고 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="3d41b-123">정크 메일 폴더에서 다음 방법 중 하나를 사용 하 여 스팸 가양성 또는 피싱 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="3d41b-124">메시지를 선택 하 고 도구 모음에서 **정크 메일** 아님으로 클릭 한 다음 **정크** 또는 **피싱**아님을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="3d41b-126">하나 이상의 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일 아님으로 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="3d41b-127">대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="3d41b-128">생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-128">If you change your mind, click **Don't Report**.</span></span>

   ![정크 메일 아님으로 보고 대화 상자](../../media/owa-report-as-not-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="3d41b-131">선택한 메시지가 분석을 위해 Microsoft로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="3d41b-132">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="3d41b-133">웹용 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용</span><span class="sxs-lookup"><span data-stu-id="3d41b-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="3d41b-134">기본적으로 사용자는 웹용 Outlook에서 분석을 위해 Microsoft에 가짜 긍정, 거짓 네거티브 및 피싱 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="3d41b-135">관리자가 Exchange online의 웹 사서함 정책에서 Outlook을 사용 하 여 exchange online PowerShell 에서만이 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-135">Admins can use Outlook on the web mailbox policies in Exchange Online to disable or enable this ability, but only in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="3d41b-136">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d41b-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3d41b-137">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3d41b-138">특히 **조직 관리** 및 **받는 사람 관리** 역할 그룹에 기본적으로 할당 되는 **받는 사람 정책** 또는 **메일 받는 사람** 역할이 Exchange Online에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-138">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="3d41b-139">Exchange Online의 역할 그룹에 대 한 자세한 내용은 [Exchange online에서 역할 그룹 수정을](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d41b-139">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="3d41b-140">모든 조직에는 Set-owamailboxpolicy 라는 기본 정책이 있지만 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-140">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="3d41b-141">사용자 지정 정책은 기본 정책 이전의 범위 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-141">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="3d41b-142">웹 사서함 정책의 Outlook에 대 한 자세한 내용은 [Exchange Online의 웹 사서함 정책에서 outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d41b-142">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

1. <span data-ttu-id="3d41b-143">웹 사서함 정책 및 정크 메일 보고 상태에 대 한 기존 Outlook을 찾으려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-143">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="3d41b-144">웹용 Outlook에서 정크 메일 보고를 사용 하지 않도록 설정 하거나 사용 하도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-144">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="3d41b-145">이 예에서는 기본 정책에서 정크 메일 보고를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-145">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="3d41b-146">이 예에서는 Contoso 관리자 라는 사용자 지정 정책에서 정크 메일 보고를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-146">This example enabled junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="3d41b-147">구문과 매개 변수에 대 한 자세한 내용은 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) 및 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d41b-147">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3d41b-148">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="3d41b-148">How do you know this worked?</span></span>

<span data-ttu-id="3d41b-149">웹용 Outlook에서 정크 메일 보고를 사용 하거나 사용 하지 않도록 설정 했는지 확인 하려면 다음 단계 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-149">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="3d41b-150">Exchange Online PowerShell에서 다음 명령을 실행 하 고 **ReportJunkEmailEnabled** 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-150">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="3d41b-151">웹에서 Outlook의 영향을 받는 사용자의 사서함을 열고 정크 메일, 정크 메일이 아닌 메시지를 보고 하는 옵션을 사용할 수 있는지 또는 사용할 수 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-151">Open an affected user's mailbox in Outlook on the web, and verify the options to report junk, not junk, and phishing messages are available or not available.</span></span> <span data-ttu-id="3d41b-152">사용자는 메시지를 정크 메일 이나 피싱이 아닌 메시지로 표시할 수는 있지만 사용자가 Microsoft에 보고 하지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3d41b-152">Note that the user can still mark messages as junk, phishing, and not junk, but the user can't report them to Microsoft.</span></span>

---
title: Microsoft 365용 정크 메일 보고 추가 기능 Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 정크 메일 보고 추가 기능을 설치하고 사용하여 스팸, 스팸이 아닌 메시지 및 피싱 메시지를 Microsoft에 보고하는 방법을 알아보세요.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205467"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="ec291-103">Microsoft 365용 정크 메일 보고 추가 기능 Outlook</span><span class="sxs-lookup"><span data-stu-id="ec291-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec291-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="ec291-104">**Applies to**</span></span>
- [<span data-ttu-id="ec291-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ec291-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ec291-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="ec291-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ec291-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec291-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="ec291-108">현재 정크 메일 보고 추가 기능을 사용하지 않는 경우 보고서 메시지 [](enable-the-report-message-add-in.md) 추가 기능 또는 피싱 보고 추가 기능을 대신 사용하는 [것이](enable-the-report-phish-add-in.md) 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="ec291-109">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec291-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="ec291-110">Microsoft 365용 정크 메일 보고 추가 Outlook 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="ec291-111">조직에서 Exchange Online Protection(예: Exchange 또는 Exchange Online 메일 서비스)를 사용하지 않는 경우 정크 메일 보고서 제출은 스팸 필터링에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="ec291-112">이 항목에서는 정크 메일 보고 추가 기능을 설치하고 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ec291-113">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ec291-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ec291-114">정크 메일 보고 추가 기능을 설치하려면 [](#install-the-junk-email-reporting-add-in) 이 문서 부분의 정크 메일 보고 추가 기능 설치 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec291-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="ec291-115">정크 메일 보고 추가 기능에서는 다음 버전의 정크 메일 Outlook.</span><span class="sxs-lookup"><span data-stu-id="ec291-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="ec291-116">Outlook 2013 이상</span><span class="sxs-lookup"><span data-stu-id="ec291-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="ec291-117">Outlook 포함된 엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="ec291-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="ec291-118">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ec291-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="ec291-119">정크 메일 보고 추가 기능을 사용하여 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="ec291-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="ec291-120">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법 중 한 가지를 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="ec291-121">메시지를 선택하거나 메시지를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ec291-121">Select the message or open the message.</span></span> <span data-ttu-id="ec291-122">리본 **메뉴의** 홈 또는 **메시지** 탭에서 정크  를 클릭한 다음 정크 메일로 보고 또는 피싱으로  **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="ec291-124">메시지를 마우스 오른쪽 단추로 클릭하고 정크  를 선택한 다음 정크 메일로 보고 또는 피싱으로 **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추를 클릭하여 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="ec291-126">여러 메시지를 선택하고 마우스 오른쪽 단추로 클릭한 다음 **정크** 메일로 보고 또는 피싱으로 **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추를 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="ec291-128">나타나는 대화 상자에서 정보를 읽고 보고서를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ec291-129">마음이 바뀌면 **보고 안 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-129">If you change your mind, click **Don't Report**.</span></span>

   ![정크로 보고 대화 상자](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![피싱으로 보고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="ec291-132">선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="ec291-133">스팸으로 보고된 경우 정크 메일 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="ec291-134">피싱으로 보고된 경우 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="ec291-135">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="ec291-136">정크 메일 보고 추가 기능을 사용하여 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="ec291-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="ec291-137">정크 메일 폴더에서 다음 방법 중 한 가지를 사용하여 스팸 가긍성 또는 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="ec291-138">메시지를 선택하거나 메시지를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ec291-138">Select the message or open the message.</span></span> <span data-ttu-id="ec291-139">리본 **메뉴의** 홈 또는 **메시지** 탭에서 정크  메일 아님을 클릭한 다음 정크 메일 아님으로 보고 또는 피싱으로  **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더의 리본에서 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="ec291-141">메시지를 마우스 오른쪽 단추로 클릭하고 정크  를 **클릭한** 다음 정크 메일 아님으로 보고 또는 피싱으로 **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="ec291-143">여러 메시지를 선택하고 마우스 오른쪽 단추로 클릭한 다음 **정크** 메일 아님으로 보고 또는 피싱으로 **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 여러 정크 메일 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="ec291-145">나타나는 대화 상자에서 정보를 읽고 보고서를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ec291-146">마음이 바뀌면 **보고 안 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-146">If you change your mind, click **Don't Report**.</span></span>

   ![정크 아님으로 보고 대화 상자](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![피싱으로 보고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="ec291-149">선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="ec291-150">스팸으로 보고된 경우 정크 메일 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="ec291-151">피싱으로 보고된 경우 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="ec291-152">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="ec291-153">정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="ec291-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="ec291-154">추가 기능을 설치하는 컴퓨터에 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="ec291-155">으로 이동하여 .msi 쉽게 찾을 수 있는 위치에 Office 대한 적절한 파일 파일을 <https://www.microsoft.com/download/details.aspx?id=18275> 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="ec291-156">**32비트**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ec291-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="ec291-157">**64비트**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ec291-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="ec291-158">Outlook 2013 이상의 경우 Microsoft .NET Framework 2.0만의 선행 .NET Framework 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="ec291-159">이 Windows 10 다운로드에서 .NET Framework 2.0을 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="ec291-160">설치 마법사를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="ec291-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="ec291-161">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="ec291-162">이 Windows 10 2.0이 .NET Framework 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="ec291-163">자세한 내용은 [제어판에서 .NET Framework 3.5 사용 을 참조하세요.](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="ec291-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="ec291-164">다운로드한 .msi 파일을 찾아 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="ec291-165">**Microsoft 정크 메일 보고 추가 기능 설치 시작** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="ec291-166">사용권 계약을  검토하고 동의하는 경우 사용권 계약에 동의합니다.를 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="ec291-167">마법사가 완료되면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="ec291-168">Outlook을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-168">Start Outlook.</span></span>

<span data-ttu-id="ec291-p109">Outlook 리본에서 **정크** 단추를 찾습니다. 이제 받은 편지함에서 정크 메일 메시지를 선택하고 **정크 메일 보고** 단추를 클릭하여 Microsoft로 정크 메일 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="ec291-p110">Microsoft에 피싱 메일을 보고하려는 경우 **피싱 메일로 보고** 와 같은 기타 옵션을 보려면 **정크** 옆에 있는 아래쪽 화살표를 선택합니다. 전자 메일이 정크 메일로 잘못 식별된 경우 정크 메일 폴더에서 **정크 메일 아님으로 보고** 를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="ec291-173">자동 모드를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="ec291-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="ec291-174">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="ec291-175">다음 Windows 10 명령을 실행하여 .NET Framework 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="ec291-176">사용자 상호 작용 없이 추가 기능을 설치하려면 명령 프롬프트를 열고 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="ec291-177">`MaxMessageSelection` 는 단일 전송에 대해 선택할 수 있는 최대 메시지 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="ec291-178">유효한 값은 1에서 50까지입니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="ec291-179">기본값은 15입니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-179">The default value is 15.</span></span>

   - <span data-ttu-id="ec291-180">`BccEmailAddress` 모든 사용자 제출의 복사본을 받을 추가 Bcc 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="ec291-181">기본값은 비어 있습니다(추가 Bcc 받는 사람 없음).</span><span class="sxs-lookup"><span data-stu-id="ec291-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="ec291-182">이 예제에서는 기본 설정으로 지정된 경로에서 64비트 버전의 추가 기능을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="ec291-183">이 예제에서는 다음과 같은 추가 설정을 사용하여 지정된 경로에서 32비트 버전의 추가 기능을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="ec291-184">단일 제출에서 최대 20개 메시지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="ec291-185">junkreports@contoso.com hollyd@treyresearch.net 모든 제출의 Bcc 복사본을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ec291-186">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="ec291-186">How do you know this worked?</span></span>

<span data-ttu-id="ec291-187">정크 메일 보고 추가 기능을 성공적으로 설치한지 확인하기 위해 다음 단계 중 Outlook.</span><span class="sxs-lookup"><span data-stu-id="ec291-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="ec291-188">메시지를 선택하거나 메시지를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ec291-188">Select the message or open the message.</span></span> <span data-ttu-id="ec291-189">리본 **메뉴의 홈** 또는 **메시지** 탭에서 정크 를 클릭하고 다음 옵션을 사용할 수 있는지 확인해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="ec291-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ec291-190">**정크로 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-190">**Report as Junk**</span></span>
  - <span data-ttu-id="ec291-191">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="ec291-192">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="ec291-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="ec291-193">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-193">**Report Junk Online Help**</span></span>

  ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="ec291-195">메시지를 마우스 오른쪽 단추로 클릭하고 정크 **를** 선택한 다음 다음 옵션을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ec291-196">**정크로 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-196">**Report as Junk**</span></span>
  - <span data-ttu-id="ec291-197">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="ec291-198">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="ec291-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="ec291-199">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-199">**Report Junk Online Help**</span></span>

  ![마우스 오른쪽 단추를 클릭하여 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="ec291-201">여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 다음 옵션을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ec291-202">**정크로 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-202">**Report as Junk**</span></span>
  - <span data-ttu-id="ec291-203">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="ec291-203">**Report as Phishing**</span></span>

  ![마우스 오른쪽 단추를 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="ec291-205">정크 메일 폴더에서 이전 작업을 **수행하고** 이전 정크 보고 옵션이 이제 정크 **메일 아님으로** 확인 </span><span class="sxs-lookup"><span data-stu-id="ec291-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![정크 메일 폴더의 리본에서 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 여러 정크 메일 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="ec291-209">정크 메일 보고 추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="ec291-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="ec291-210">정크 Outlook 다음 절차에 따라 정크 메일 보고 추가 기능을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="ec291-211">**제어판:** Windows + R을 누르고 있습니다. 실행 **대화** 상자가 열리면 를 `control appwiz.cpl` 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="ec291-212">목록에서 **Microsoft 정크** 메일 보고 추가 기능을 찾아 선택한 다음 제거 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="ec291-213">**Windows 설치** 관리자 패키지: 적절한 설치 .msi 다운로드하고 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="ec291-214">**32비트**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ec291-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="ec291-215">**64비트**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ec291-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="ec291-216">나타나는 대화 상자에서 Microsoft 정크 메일 보고 추가 기능 제거를 Outlook **다음을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ec291-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="ec291-217">**자동 모드:** 적절한 자동 모드 파일을 .msi 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="ec291-218">명령 프롬프트 창에서 .msi 위치로 바꾸고 다음 명령 중 하나를 \<PathToFile\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="ec291-219">**32비트**:</span><span class="sxs-lookup"><span data-stu-id="ec291-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="ec291-220">**64비트**:</span><span class="sxs-lookup"><span data-stu-id="ec291-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="ec291-221">제거 후 Outlook 열면 정크가 아닌 정크 및 피싱 보고 옵션이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="ec291-222">정크 메일 보고 추가 기능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ec291-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="ec291-223">경우에 따라 정크 메일 보고 추가 기능을 Outlook 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="ec291-224">이 섹션에서는 발생할 수 있는 문제에 대해 설명하고 이러한 문제를 해결하기 위한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="ec291-225">사용자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ec291-225">Troubleshooting for users</span></span>

<span data-ttu-id="ec291-226">다음 문제 중 하나 이상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="ec291-227">**정크 메일 보고** 를 클릭해도 아무 작업도 수행되지 않음</span><span class="sxs-lookup"><span data-stu-id="ec291-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="ec291-228">전자 메일 메시지를 선택한 후 Outlook의 응답이 중지됨</span><span class="sxs-lookup"><span data-stu-id="ec291-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="ec291-229">"배달 불능" 응답으로 인해 보고된 정크 메일을 배달할 수 없음</span><span class="sxs-lookup"><span data-stu-id="ec291-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="ec291-230">이 문제를 해결하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="ec291-231">닫았다가 다시 Outlook.</span><span class="sxs-lookup"><span data-stu-id="ec291-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="ec291-232">테스트 메시지를 만들고 보내고 받는 사람이 메시지를 받았는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="ec291-233">문제가 계속되면 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="ec291-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="ec291-234">Microsoft에 메시지를 전송하는 데 사용할 수 있는 다른 방법은 Microsoft에 메시지 및 파일 보고를 [참조합니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ec291-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="ec291-235">관리자를 위한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ec291-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="ec291-236">문제: 사용자에게 시스템 관리자에게 문의할지 묻는 오류 메시지가 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="ec291-237">레지스트리 키를 `LoggingLevel` "Verbose" 값으로 확인하거나 설정</span><span class="sxs-lookup"><span data-stu-id="ec291-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="ec291-238">**32비트 Outlook 32비트** Windows:</span><span class="sxs-lookup"><span data-stu-id="ec291-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="ec291-239">**64비트 Outlook 32비트** Windows:</span><span class="sxs-lookup"><span data-stu-id="ec291-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="ec291-240">**64비트 Outlook**:</span><span class="sxs-lookup"><span data-stu-id="ec291-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="ec291-241">이 Outlook 다시 시작하고 사용자에게 오류 메시지가 표시될 때 다시 보고해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="ec291-242">다음 위치에 있는 로그 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="ec291-243">Exchange Online Protection 기술 지원 서비스에 문의하여 로그 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="ec291-244">문제: 사용자가 메시지를 보고할 때 확인 메시지를 받지 못하게 선택되어 메시지가 다시 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="ec291-245">"True" 값을 사용하여 `ConfirmReportJunk` 레지스트리 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="ec291-246">Outlook을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ec291-246">Restart Outlook.</span></span>
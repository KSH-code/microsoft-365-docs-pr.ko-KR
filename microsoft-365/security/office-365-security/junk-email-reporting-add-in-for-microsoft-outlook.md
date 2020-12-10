---
title: Microsoft Outlook용 정크 메일 보고 추가 기능 설치 및 사용
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 정크 메일 보고 추가 기능을 설치 및 사용하여 스팸, 스팸이 아닌 메시지 및 피싱 메시지를 Microsoft에 보고하는 방법을 알아보세요.
ms.openlocfilehash: 6f08c72ae797825695c443848429dcfd2cd485a2
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616431"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="045fc-103">Microsoft Outlook용 정크 메일 보고 추가 기능 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="045fc-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="045fc-104">현재 정크 메일 보고 추가 기능을 사용하지 않는 경우 대신 보고서 메시지 추가 기능을 사용하는 [것이](enable-the-report-message-add-in.md) 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="045fc-105">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="045fc-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="045fc-106">Microsoft Outlook용 정크 메일 보고 추가 기능을 사용하면 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="045fc-107">조직에서 Exchange Online Protection(예: Exchange Online 또는 Exchange Online이 아닌 전자 메일 서비스)을 사용하지 않는 경우 정크 메일 보고서 제출은 스팸 필터링에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="045fc-108">이 항목에서는 정크 메일 보고 추가 기능을 설치하고 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="045fc-109">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="045fc-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="045fc-110">정크 메일 보고 추가 기능을 설치하려면 [](#install-the-junk-email-reporting-add-in) 이 항목 부분의 정크 메일 보고 추가 기능 설치 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="045fc-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="045fc-111">정크 메일 보고 추가 기능에서는 다음 버전의 Outlook과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="045fc-112">Outlook 2013 이상</span><span class="sxs-lookup"><span data-stu-id="045fc-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="045fc-113">엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook</span><span class="sxs-lookup"><span data-stu-id="045fc-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="045fc-114">Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="045fc-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="045fc-115">정크 메일 보고 추가 기능을 사용하여 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="045fc-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="045fc-116">받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법 중 한 가지를 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="045fc-117">메시지를 선택하거나 메시지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-117">Select the message or open the message.</span></span> <span data-ttu-id="045fc-118">리본의 홈 **또는** 메시지 탭에서 정크를  클릭한 다음 정크 메일로 보고 또는 피싱으로  **보고를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="045fc-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="045fc-120">메시지를 마우스 오른쪽 단추로 클릭하고 정크를 선택한 다음 정크 메일로 보고 또는 피싱으로 **보고를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="045fc-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="045fc-122">여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 **정크** 메일로 보고 또는 **피싱으로 보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추를 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="045fc-124">나타나는 대화 상자에서 정보를 읽고 **보고서를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="045fc-125">마음이 바뀌면 보고 안 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-125">If you change your mind, click **Don't Report**.</span></span>

   ![정크로 보고 대화 상자](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![피싱으로 보고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="045fc-128">선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="045fc-129">스팸으로 보고된 정크 메일 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="045fc-130">피싱으로 보고된 경우 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-130">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="045fc-131">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="045fc-132">정크 메일 보고 추가 기능을 사용하여 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="045fc-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="045fc-133">정크 메일 폴더에서 다음 방법 중 한 가지를 사용하여 스팸 가긍성 또는 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="045fc-134">메시지를 선택하거나 메시지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-134">Select the message or open the message.</span></span> <span data-ttu-id="045fc-135">리본의 홈 **또는** 메시지 탭에서 정크 메일  아님을 클릭한 다음 보고를 정크 메일 아님 또는 피싱으로  **보고를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="045fc-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더의 리본에서 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="045fc-137">메시지를 마우스 오른쪽 단추로 클릭하고 정크를 클릭한 다음 보고를 정크 메일 아님 또는 피싱으로 **보고를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="045fc-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="045fc-139">여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 **보고를** 정크 메일 아님 또는 피싱으로 **보고로 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 여러 정크 메일 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="045fc-141">나타나는 대화 상자에서 정보를 읽고 **보고서를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="045fc-142">마음이 바뀌면 보고 안 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-142">If you change your mind, click **Don't Report**.</span></span>

   ![정크 아님으로 보고 대화 상자](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![피싱으로 보고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="045fc-145">선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="045fc-146">스팸으로 보고된 정크 메일 폴더로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="045fc-147">피싱으로 보고된 경우 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="045fc-148">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="045fc-149">정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="045fc-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="045fc-150">추가 기능을 설치하는 컴퓨터에 대한 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="045fc-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span><span class="sxs-lookup"><span data-stu-id="045fc-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="045fc-152">**32비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="045fc-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="045fc-153">**64비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="045fc-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="045fc-154">Outlook 2013 이상에서는 Microsoft .NET Framework 2.0만 선행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="045fc-155">Windows 10에서는 다운로드에서 .NET Framework 2.0을 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="045fc-156">설치 마법사를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="045fc-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="045fc-157">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="045fc-158">Windows 10에서 .NET Framework 2.0이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="045fc-159">자세한 내용은 제어판에서 [.NET Framework 3.5 사용을 참조하세요.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="045fc-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="045fc-160">다운로드한 .msi 파일을 찾아 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="045fc-161">**Microsoft 정크 메일 보고 추가 기능 설치 시작** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="045fc-162">사용권 계약을  검토하고 사용권 계약에 동의하는 경우 동의를 클릭한 다음 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="045fc-163">마법사가 완료되면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="045fc-164">Outlook을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-164">Start Outlook.</span></span>

<span data-ttu-id="045fc-p109">Outlook 리본에서 **정크** 단추를 찾습니다. 이제 받은 편지함에서 정크 메일 메시지를 선택하고 **정크 메일 보고** 단추를 클릭하여 Microsoft로 정크 메일 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="045fc-p110">Microsoft에 피싱 메일을 보고하려는 경우 **피싱 메일로 보고** 와 같은 기타 옵션을 보려면 **정크** 옆에 있는 아래쪽 화살표를 선택합니다. 전자 메일이 정크 메일로 잘못 식별된 경우 정크 메일 폴더에서 **정크 메일 아님으로 보고** 를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="045fc-169">자동 모드를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="045fc-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="045fc-170">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="045fc-171">Windows 10에서 다음 명령을 실행하여 .NET Framework 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="045fc-172">사용자 상호 작용 없이 추가 기능을 설치하려면 명령 프롬프트를 열고 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="045fc-173">`MaxMessageSelection` 단일 전송에 대해 선택할 수 있는 최대 메시지 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="045fc-174">유효한 값은 1에서 50까지입니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="045fc-175">기본값은 15입니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-175">The default value is 15.</span></span>

   - <span data-ttu-id="045fc-176">`BccEmailAddress` 모든 사용자 제출의 복사본을 받을 추가 Bcc 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="045fc-177">기본값은 비어 있습니다(추가 Bcc 받는 사람 없음).</span><span class="sxs-lookup"><span data-stu-id="045fc-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="045fc-178">이 예제에서는 기본 설정으로 지정된 경로에서 추가 기능의 64비트 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="045fc-179">이 예제에서는 다음과 같은 추가 설정을 사용하여 지정된 경로에서 추가 기능의 32비트 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="045fc-180">단일 제출에서 최대 20개 메시지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="045fc-181">junkreports@contoso.com 및 hollyd@treyresearch.net 모든 제출의 Bcc 복사본을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="045fc-182">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="045fc-182">How do you know this worked?</span></span>

<span data-ttu-id="045fc-183">정크 메일 보고 추가 기능을 성공적으로 설치 지 확인을 위해 Outlook에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="045fc-184">메시지를 선택하거나 메시지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-184">Select the message or open the message.</span></span> <span data-ttu-id="045fc-185">리본 **메뉴의 홈** **또는** 메시지 탭에서 정크를 클릭하고 **다음** 옵션을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="045fc-186">**정크로 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-186">**Report as Junk**</span></span>
  - <span data-ttu-id="045fc-187">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="045fc-188">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="045fc-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="045fc-189">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-189">**Report Junk Online Help**</span></span>

  ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="045fc-191">메시지를 마우스 오른쪽 단추로 클릭하고 정크를 선택한 다음 다음 옵션을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="045fc-192">**정크로 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-192">**Report as Junk**</span></span>
  - <span data-ttu-id="045fc-193">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="045fc-194">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="045fc-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="045fc-195">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-195">**Report Junk Online Help**</span></span>

  ![마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="045fc-197">여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 다음 옵션을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="045fc-198">**정크로 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-198">**Report as Junk**</span></span>
  - <span data-ttu-id="045fc-199">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="045fc-199">**Report as Phishing**</span></span>

  ![마우스 오른쪽 단추를 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="045fc-201">정크 메일 폴더에서 이전 작업을 수행하고  이전 정크 보고 옵션이 이제 정크  **메일이 아닌지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![정크 메일 폴더의 리본에서 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 여러 정크 메일 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="045fc-205">정크 메일 보고 추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="045fc-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="045fc-206">Outlook을 닫은 후 다음 절차에 따라 정크 메일 보고 추가 기능을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="045fc-207">**제어판:** Windows 키 + R을 누르는 경우 실행 **대화** 상자가 열리면 입력한 `control appwiz.cpl` 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="045fc-208">목록에서 **Microsoft 정크** 메일 보고 추가 기능을 찾아 선택한 다음 **제거를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="045fc-209">**Windows Installer 패키지:** 적절한 .msi 파일을 찾거나 다운로드한 다음 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="045fc-210">**32비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="045fc-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="045fc-211">**64비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="045fc-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="045fc-212">나타나는 대화 상자에서 **Outlook용 Microsoft 정크** 메일 보고 추가 기능 제거를 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="045fc-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="045fc-213">**자동 모드:** 적절한 .msi 파일을 찾거나 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="045fc-214">명령 프롬프트 창에서 .msi 파일의 위치로 바꾸고 다음 명령 중 \<PathToFile\> 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="045fc-215">**32비트:**</span><span class="sxs-lookup"><span data-stu-id="045fc-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="045fc-216">**64비트:**</span><span class="sxs-lookup"><span data-stu-id="045fc-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="045fc-217">제거 후 Outlook을 열면 정크가 아닌 정크 및 피싱 보고 옵션이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="045fc-218">정크 메일 보고 추가 기능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="045fc-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="045fc-219">경우에 따라 정크 메일 보고 추가 기능을 추가한 후 Outlook에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="045fc-220">이 섹션에서는 발생할 수 있는 문제에 대해 설명하고 이러한 문제를 해결하기 위한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="045fc-221">사용자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="045fc-221">Troubleshooting for users</span></span>

<span data-ttu-id="045fc-222">다음 문제 중 하나 이상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="045fc-223">**정크 메일 보고** 를 클릭해도 아무 작업도 수행되지 않음</span><span class="sxs-lookup"><span data-stu-id="045fc-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="045fc-224">전자 메일 메시지를 선택한 후 Outlook의 응답이 중지됨</span><span class="sxs-lookup"><span data-stu-id="045fc-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="045fc-225">"배달 불능" 응답으로 인해 보고된 정크 메일을 배달할 수 없음</span><span class="sxs-lookup"><span data-stu-id="045fc-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="045fc-226">이 문제를 해결하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="045fc-227">Outlook을 닫았다가 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="045fc-228">테스트 메시지를 만들고 보내고 받는 사람이 메시지를 받았는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="045fc-229">문제가 계속되면 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="045fc-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="045fc-230">Microsoft에 메시지를 전송하는 데 사용할 수 있는 다른 방법은 Microsoft에 메시지 및 [파일 보고를 참조합니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="045fc-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="045fc-231">관리자를 위한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="045fc-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="045fc-232">문제: 사용자에게 시스템 관리자에게 문의할지 묻는 오류 메시지가 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="045fc-233">레지스트리 키를 `LoggingLevel` "Verbose" 값으로 확인하거나 설정</span><span class="sxs-lookup"><span data-stu-id="045fc-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="045fc-234">**32비트 Windows의 32비트 Outlook:**</span><span class="sxs-lookup"><span data-stu-id="045fc-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="045fc-235">**64비트 Windows의 32비트 Outlook:**</span><span class="sxs-lookup"><span data-stu-id="045fc-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="045fc-236">**64비트 Outlook**:</span><span class="sxs-lookup"><span data-stu-id="045fc-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="045fc-237">Outlook을 다시 시작하고 사용자에게 오류 메시지가 표시될 때 다시 보고해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="045fc-238">다음 위치에 있는 로그 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="045fc-239">Exchange Online Protection 기술 지원 서비스에 문의하여 로그 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="045fc-240">문제: 사용자가 메시지를 보고할 때 확인 메시지를 받지 못하게 선택되어 메시지가 다시 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="045fc-241">"True" 값을 사용하여 `ConfirmReportJunk` 레지스트리 키를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="045fc-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="045fc-242">Outlook을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="045fc-242">Restart Outlook.</span></span>

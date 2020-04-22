---
title: Microsoft Outlook 용 정크 메일 보고 추가 기능 설치 및 사용
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 정크 메일 보고 추가 기능을 설치 하 고 사용 하 여 스팸, 비 스팸 및 피싱 메시지를 Microsoft에 보고 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: be087a15071114b2d1ec564cbb118dcd85e32429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638503"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="2c702-103">Office 365에서 Microsoft Outlook 용 정크 메일 보고 추가 기능 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="2c702-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="2c702-104">현재 정크 메일 보고 추가 기능을 사용 하지 않는 경우에는 대신 [보고서 메시지 추가 기능](enable-the-report-message-add-in.md) 을 사용할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="2c702-105">Microsoft Outlook 용 정크 메일 보고 추가 기능을 사용 하면 사용자가 가양성 (스팸으로 표시 된 전자 메일), 거짓 부정 (잘못 된 전자 메일 허용) 및 EOP (Exchange Online Protection)로의 피싱 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2c702-106">조직에서 EOP을 사용 하지 않는 경우 정크 메일 보고서 제출에서는 스팸 필터링에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="2c702-107">이 항목에서는 정크 메일 보고 추가 기능을 설치 하 고 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2c702-108">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="2c702-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2c702-109">정크 메일 보고 추가 기능을 설치 하려면이 항목의 뒷부분에 나오는 [정크 메일 보고 추가 기능 설치](#install-the-junk-email-reporting-add-in) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c702-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="2c702-110">정크 메일 보고 추가 기능을 사용 하는 Outlook 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="2c702-111">Outlook 2013 이상</span><span class="sxs-lookup"><span data-stu-id="2c702-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="2c702-112">Microsoft 365 for enterprise 앱에 포함 된 Outlook</span><span class="sxs-lookup"><span data-stu-id="2c702-112">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="2c702-113">Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [Office 365에서 microsoft에 메시지 및 파일](report-junk-email-messages-to-microsoft.md)보고를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c702-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="2c702-114">정크 메일 보고 추가 기능을 사용 하 여 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="2c702-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="2c702-115">받은 편지함 또는 정크 메일을 제외한 다른 모든 전자 메일 폴더의 메시지에 대해 다음 방법 중 하나를 사용 하 여 스팸 및 피싱 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="2c702-116">메시지를 선택 하거나 메시지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-116">Select the message or open the message.</span></span> <span data-ttu-id="2c702-117">리본 메뉴의 **홈** 또는 **메시지** 탭에서 **정크**을 클릭 하 고 **정크 메일로 보고** 또는 **피싱 메일로**보고서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="2c702-119">메시지를 마우스 오른쪽 단추로 클릭 하 고 **정크**을 선택한 후 **정크** 메일로 또는 **피싱**메일로 보고를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추를 클릭 하 여 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="2c702-121">여러 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크** 메일로 또는 **피싱**메일로 보고를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추를 클릭 하 여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="2c702-123">대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="2c702-124">생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-124">If you change your mind, click **Don't Report**.</span></span>

   ![정크 메일로 신고 대화 상자](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="2c702-p104">선택한 메시지가 분석을 위해 Microsoft로 전송되고 정크 메일 폴더로 이동됩니다. 메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="2c702-129">정크 메일 보고 추가 기능을 사용 하 여 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지가 보고 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="2c702-130">정크 메일 폴더에서 다음 방법 중 하나를 사용 하 여 스팸 가양성 또는 피싱 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="2c702-131">메시지를 선택 하거나 메시지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-131">Select the message or open the message.</span></span> <span data-ttu-id="2c702-132">리본 메뉴의 **홈** 또는 **메시지** 탭에서 **정크 메일**아님으로를 클릭 한 다음 **정크 메일 아님으로 보고** 또는 **피싱 메일로 보고**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더의 리본에서 정크 또는 피싱 전자 메일을 보고 하지 않습니다.](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="2c702-134">메시지를 마우스 오른쪽 단추로 클릭 하 고 **정크**메일을 클릭 한 다음 **정크 메일 아님으로 보고** 또는 **피싱 메일로 보고**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭 하면 정크 메일 또는 피싱 전자 메일이 보고 되지 않음](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="2c702-136">여러 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일 아님으로 보고** 또는 **피싱 메일로 보고**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더의 오른쪽 클릭에서 정크 메일이 아닌 전자 메일 메시지를 여러 개 보고 합니다.](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="2c702-138">대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="2c702-139">생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-139">If you change your mind, click **Don't Report**.</span></span>

   ![정크 메일 아님으로 보고 대화 상자](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="2c702-p107">선택한 메시지가 분석을 위해 Microsoft로 전송되고 정크 메일 폴더로 이동됩니다. 메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="2c702-144">정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="2c702-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="2c702-145">추가 기능을 설치 하는 컴퓨터에 대 한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="2c702-146">Office 버전 <https://www.microsoft.com/download/details.aspx?id=18275> 의 적절 한 .msi 파일을 쉽게 찾을 수 있는 위치로 이동한 후 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="2c702-147">**32 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="2c702-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="2c702-148">**64 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="2c702-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="2c702-149">Outlook 2013 이상 버전의 경우에는 Microsoft .NET Framework 2.0에만 필수 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="2c702-150">Windows 10에서는 다운로드에서 .NET Framework 2.0을 설치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="2c702-151">설치 마법사를 사용 하 여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="2c702-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="2c702-152">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="2c702-153">Windows 10에서는 .NET Framework 2.0가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="2c702-154">자세한 내용은 [제어판에서 .Net Framework 3.5을 사용 하도록 설정](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c702-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="2c702-155">다운로드 한 .msi 파일을 찾아 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="2c702-156">**Microsoft 정크 메일 보고 추가 기능 설치 시작** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="2c702-157">사용권 계약을 검토 하 고 **사용권 계약에** 동의 하는 경우 동의 함을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="2c702-158">마법사가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="2c702-159">Outlook을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-159">Start Outlook.</span></span>

<span data-ttu-id="2c702-p110">Outlook 리본에서 **정크** 단추를 찾습니다. 이제 받은 편지함에서 정크 메일 메시지를 선택하고 **정크 메일 보고** 단추를 클릭하여 Microsoft로 정크 메일 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-p110">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="2c702-p111">Microsoft에 피싱 메일을 보고하려는 경우 **피싱 메일로 보고**와 같은 기타 옵션을 보려면 **정크** 옆에 있는 아래쪽 화살표를 선택합니다. 전자 메일이 정크 메일로 잘못 식별된 경우 정크 메일 폴더에서 **정크 메일 아님으로 보고**를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="2c702-164">자동 모드를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="2c702-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="2c702-165">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="2c702-166">Windows 10에서는 다음 명령을 실행 하 여 .NET Framework 2.0을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="2c702-167">사용자 상호 작용 없이 추가 기능을 설치 하려면 명령 프롬프트를 열고 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="2c702-168">`MaxMessageSelection`단일 전송에 대해 선택할 수 있는 최대 메시지 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="2c702-169">유효한 값은 1에서 50 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="2c702-170">기본값은 15입니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-170">The default value is 15.</span></span>

   - <span data-ttu-id="2c702-171">`BccEmailAddress`모든 사용자 전송의 복사본을 받을 추가 숨은 참조 받는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="2c702-172">기본값은 빈 값 (추가 숨은 참조 받는 사람 없음)입니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="2c702-173">이 예제에서는 지정 된 경로에서 기본 설정을 사용 하 여 64 비트 버전의 추가 기능을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="2c702-174">이 예제에서는 다음 추가 설정을 사용 하 여 지정 된 경로에서 32 비트 버전의 추가 기능을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="2c702-175">단일 전송에서 최대 20 개의 메시지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="2c702-176">junkreports@contoso.com 및 hollyd@treyresearch.net는 모든 전송의 숨은 참조 복사본을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2c702-177">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="2c702-177">How do you know this worked?</span></span>

<span data-ttu-id="2c702-178">정크 메일 보고 추가 기능이 성공적으로 설치 되었는지 확인 하려면 Outlook에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="2c702-179">메시지를 선택 하거나 메시지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-179">Select the message or open the message.</span></span> <span data-ttu-id="2c702-180">리본 메뉴의 **홈** 또는 **메시지** 탭에서 **정크**을 클릭 하 고 다음 옵션을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="2c702-181">**정크로 신고**</span><span class="sxs-lookup"><span data-stu-id="2c702-181">**Report as Junk**</span></span>
  - <span data-ttu-id="2c702-182">**피싱 메일로 신고**</span><span class="sxs-lookup"><span data-stu-id="2c702-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="2c702-183">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="2c702-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="2c702-184">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="2c702-184">**Report Junk Online Help**</span></span>

  ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="2c702-186">메시지를 마우스 오른쪽 단추로 클릭 하 고 **정크**을 선택한 후 다음 옵션을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="2c702-187">**정크로 신고**</span><span class="sxs-lookup"><span data-stu-id="2c702-187">**Report as Junk**</span></span>
  - <span data-ttu-id="2c702-188">**피싱 메일로 신고**</span><span class="sxs-lookup"><span data-stu-id="2c702-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="2c702-189">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="2c702-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="2c702-190">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="2c702-190">**Report Junk Online Help**</span></span>

  ![마우스 오른쪽 단추를 클릭 하 여 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="2c702-192">여러 메시지를 선택한 다음 마우스 오른쪽 단추를 클릭 하 고 다음 옵션을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="2c702-193">**정크로 신고**</span><span class="sxs-lookup"><span data-stu-id="2c702-193">**Report as Junk**</span></span>
  - <span data-ttu-id="2c702-194">**피싱 메일로 신고**</span><span class="sxs-lookup"><span data-stu-id="2c702-194">**Report as Phishing**</span></span>

  ![마우스 오른쪽 단추를 클릭 하 여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="2c702-196">**정크 메일** 폴더에서 이전 작업을 수행 하 고 이전 **정크** 보고 옵션이 현재 **정크 메일이 아닌지**확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![정크 메일 폴더의 리본에서 정크 또는 피싱 전자 메일을 보고 하지 않습니다.](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭 하면 정크 메일 또는 피싱 전자 메일이 보고 되지 않음](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![정크 메일 폴더의 오른쪽 클릭에서 정크 메일이 아닌 전자 메일 메시지를 여러 개 보고 합니다.](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="2c702-200">정크 메일 보고 추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="2c702-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="2c702-201">Outlook을 닫은 후에는 다음 절차 중 하나를 사용 하 여 정크 메일 보고 추가 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="2c702-202">**제어판**: Windows 키 + R을 누릅니다. 열리는 **실행** 대화 상자에서를 입력 `control appwiz.cpl` 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="2c702-203">목록에서 **Microsoft 정크 메일 보고 추가 기능** 을 찾아 선택한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="2c702-204">**Windows Installer 패키지**: 해당 .msi 파일을 찾거나 다운로드 한 후에 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="2c702-205">**32 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="2c702-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="2c702-206">**64 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="2c702-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="2c702-207">대화 상자가 나타나면 **Outlook 용 Microsoft 정크 메일 보고 추가 기능 제거** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="2c702-208">**자동 모드**: 적절 한 .msi 파일을 찾거나 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="2c702-209">명령 프롬프트 창에서 pathtofile \<\> 을 .msi 파일의 위치로 바꾸고 다음 명령 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="2c702-210">**32 비트**:</span><span class="sxs-lookup"><span data-stu-id="2c702-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="2c702-211">**64 비트**:</span><span class="sxs-lookup"><span data-stu-id="2c702-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="2c702-212">제거 후 Outlook을 여는 경우 정크 메일이 아닌 정크 메일 및 피싱 보고 옵션이 없어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="2c702-213">정크 메일 보고 추가 기능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2c702-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="2c702-214">경우에 따라 정크 메일 보고 추가 기능을 추가한 후 Outlook에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="2c702-215">이 섹션에서는 이러한 문제를 해결 하기 위한 팁과 함께 발생할 수 있는 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="2c702-216">사용자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2c702-216">Troubleshooting for users</span></span>

<span data-ttu-id="2c702-217">다음 문제 중 하나 이상이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="2c702-218">**정크 메일 보고**를 클릭해도 아무 작업도 수행되지 않음</span><span class="sxs-lookup"><span data-stu-id="2c702-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="2c702-219">전자 메일 메시지를 선택한 후 Outlook의 응답이 중지됨</span><span class="sxs-lookup"><span data-stu-id="2c702-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="2c702-220">"배달 불능" 응답으로 인해 보고된 정크 메일을 배달할 수 없음</span><span class="sxs-lookup"><span data-stu-id="2c702-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="2c702-221">이 문제를 해결 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="2c702-222">Outlook을 닫았다가 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="2c702-223">테스트 메시지를 만들어 보낸 후 받는 사람이 메시지를 받았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="2c702-224">문제가 계속 되 면 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c702-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="2c702-225">Microsoft에 메시지를 전송 하는 데 사용할 수 있는 다른 방법에 대 한 자세한 내용은 [Report messages and files In microsoft](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c702-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="2c702-226">관리자를 위한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2c702-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="2c702-227">문제: 사용자에 게 시스템 관리자에 게 문의 하 라는 오류 메시지가 계속 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="2c702-228">`LoggingLevel` 레지스트리 키를 "Verbose" 값으로 확인 하거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="2c702-229">**32 비트 Windows에서 32 비트 Outlook**:</span><span class="sxs-lookup"><span data-stu-id="2c702-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="2c702-230">**64 비트 Windows에서 32 비트 Outlook**:</span><span class="sxs-lookup"><span data-stu-id="2c702-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="2c702-231">**64 비트 Outlook**:</span><span class="sxs-lookup"><span data-stu-id="2c702-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="2c702-232">Outlook을 다시 시작 하 고 오류 메시지가 표시 되 면 다시 사용자에 게 보고할지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="2c702-233">다음 위치에 있는 로그 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="2c702-234">Exchange Online Protection 기술 지원 서비스에 문의하여 로그 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="2c702-235">문제: 사용자가 메시지를 보고 했을 때 확인 메시지를 수신 하지 않도록 선택 했으며, 다시 확인 하 고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="2c702-236">"True `ConfirmReportJunk`" 값을 wih 레지스트리 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="2c702-237">Outlook을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c702-237">Restart Outlook.</span></span>

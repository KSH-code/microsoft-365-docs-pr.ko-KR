---
title: Microsoft Outlook용 정크 메일 보고 추가 기능 설치 및 사용
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 정크 메일 보고 추가 기능을 설치하고 사용하여 스팸, 스팸이 아닌 메시지 및 피싱 메시지를 Microsoft에 보고하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 42b38830b55ae3dbee4ec74a0e96531d920c24a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827102"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="6a617-103">Microsoft Outlook용 정크 메일 보고 추가 기능 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="6a617-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="6a617-104">현재 정크 메일 보고 추가 기능을 사용하고 있지 않다면 [대신 보고서 메시지 추가 기능을 사용하는 것이](enable-the-report-message-add-in.md) 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="6a617-105">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a617-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="6a617-106">Microsoft Outlook용 정크 메일 보고 추가 기능을 사용하면 가양성(스팸으로 정상 시정) 거짓 부정(잘못된 전자 메일이 허용됨) 및 피싱 메시지를 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="6a617-107">조직에서 Exchange Online Protection(예: 온-프레미스 Exchange 또는 Exchange Online 이외의 전자 메일 서비스)을 사용하지 않는 경우 정크 메일 보고서 제출은 스팸 필터링에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="6a617-108">이 항목에서는 정크 메일 보고 추가 기능을 설치 및 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a617-109">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6a617-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6a617-110">정크 메일 보고 추가 기능을 설치하려면 이 항목의 [뒷부분에 나오는 정크 메일 보고 추가 기능 설치](#install-the-junk-email-reporting-add-in) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a617-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="6a617-111">정크 메일 보고 추가 기능은 다음 버전의 Outlook에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="6a617-112">Outlook 2013 이상</span><span class="sxs-lookup"><span data-stu-id="6a617-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="6a617-113">엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook</span><span class="sxs-lookup"><span data-stu-id="6a617-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="6a617-114">Microsoft에 메시지를 보고하는 방법에 대한 자세한 내용은 [Microsoft로 보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6a617-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="6a617-115">정크 메일 보고 추가 기능을 사용하여 스팸 및 피싱 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="6a617-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="6a617-116">정크 메일을 제외한 받은 편지함 또는 기타 전자 메일 폴더의 메시지의 경우 다음 방법 중 하나를 사용하여 스팸 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="6a617-117">메시지를 선택하거나 메시지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-117">Select the message or open the message.</span></span> <span data-ttu-id="6a617-118">리본 **메뉴의** **홈 또는** 메시지 탭에서 **정크**를 클릭한 다음 **정크** 또는 피싱으로 **보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![리본 메뉴에서 정크 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="6a617-120">메시지를 마우스 오른쪽 단추로 클릭하고, **정크를**선택한 후 **피싱으로 보고를 선택합니다.** **Report as Junk**</span><span class="sxs-lookup"><span data-stu-id="6a617-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추 클릭에서 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="6a617-122">마우스 오른쪽 단추로 여러 메시지를 선택한 다음 **피싱 메일로 보고를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![마우스 오른쪽 단추로 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="6a617-124">In the dialog that read the information and click **Report.**</span><span class="sxs-lookup"><span data-stu-id="6a617-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="6a617-125">마이그라이드를 변경한 경우 **"보고서 금지"를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-125">If you change your mind, click **Don't Report**.</span></span>

   ![정크 메일로 보고 대화 상자](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![피싱 대화 상자로 보고](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="6a617-128">선택한 메시지는 분석을 위해 Microsoft에 전송되고 다음 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="6a617-129">정크 메일 폴더로 이동(스팸으로 보고된 경우)</span><span class="sxs-lookup"><span data-stu-id="6a617-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="6a617-130">피싱으로 보고된 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="6a617-131">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="6a617-132">정크 메일 보고 추가 기능을 사용하여 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="6a617-133">정크 메일 폴더에서 다음 방법 중 하나를 사용하여 스팸 가양성 또는 피싱 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="6a617-134">메시지를 선택하거나 메시지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-134">Select the message or open the message.</span></span> <span data-ttu-id="6a617-135">리본 **메뉴의** **홈 또는** 메시지 탭에서 **정크 메일 아님을**클릭한 다음 **정크 또는** **피싱으로 보고서를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더의 리본 메뉴에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="6a617-137">메시지를 마우스 오른쪽 단추로 클릭하고 **정크 메일** **아님** 또는 **피싱으로 보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="6a617-139">메시지를 여러 개 선택하고 마우스 오른쪽 단추를 클릭한 다음 **정크 메일 아님 또는** **피싱으로 보고)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![정크 메일 폴더에서 마우스 오른쪽 단추로 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="6a617-141">In the dialog that read the information and click **Report.**</span><span class="sxs-lookup"><span data-stu-id="6a617-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="6a617-142">마이그라이드를 변경한 경우 **"보고서 금지"를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-142">If you change your mind, click **Don't Report**.</span></span>

   ![정크 메일 아님 대화 상자로 보고](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![피싱 대화 상자로 보고](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="6a617-145">선택한 메시지는 분석을 위해 Microsoft에 전송되고 다음 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="6a617-146">정크 메일 폴더로 이동(스팸으로 보고된 경우)</span><span class="sxs-lookup"><span data-stu-id="6a617-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="6a617-147">피싱으로 보고된 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="6a617-148">메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="6a617-149">정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="6a617-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="6a617-150">추가 기능을 설치할 컴퓨터에 대해 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="6a617-151">Office <https://www.microsoft.com/download/details.aspx?id=18275> 버전에 적합한 .msi 파일을 찾아 간과한 위치로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="6a617-152">**32비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6a617-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="6a617-153">**64비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6a617-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="6a617-154">Outlook 2013 이상의 경우 Microsoft .NET Framework 2.0은 Outlook 2013 이상 버전의 필수 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="6a617-155">Windows 10에서는 다운로드에서 .NET Framework 2.0을 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="6a617-156">설치 마법사를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="6a617-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="6a617-157">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="6a617-158">Windows 10에서 .NET Framework 2.0이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="6a617-159">지침은 제어판에서 [.NET Framework 3.5 사용을 선택합니다.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="6a617-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="6a617-160">다운로드한 .msi 파일을 찾아 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="6a617-161">**Microsoft 정크 메일 보고 추가 기능 설치 시작** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="6a617-162">사용권 계약을 검토하고 사용권 계약에 동의하면 **동의한** 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="6a617-163">마법사가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="6a617-164">Outlook을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-164">Start Outlook.</span></span>

<span data-ttu-id="6a617-p109">Outlook 리본에서 **정크** 단추를 찾습니다. 이제 받은 편지함에서 정크 메일 메시지를 선택하고 **정크 메일 보고** 단추를 클릭하여 Microsoft로 정크 메일 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="6a617-p110">Microsoft에 피싱 메일을 보고하려는 경우 **피싱 메일로 보고**와 같은 기타 옵션을 보려면 **정크** 옆에 있는 아래쪽 화살표를 선택합니다. 전자 메일이 정크 메일로 잘못 식별된 경우 정크 메일 폴더에서 **정크 메일 아님으로 보고**를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="6a617-169">자동 모드를 사용하여 정크 메일 보고 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="6a617-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="6a617-170">컴퓨터에서 Outlook을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="6a617-171">Windows 10에서 다음 명령을 실행하여 .NET Framework 2.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="6a617-172">사용자 조작 없이 추가 기능을 설치하려면 명령 프롬프트를 열고 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="6a617-173">`MaxMessageSelection` 단일 전송에 대해 선택할 수 있는 최대 메시지 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="6a617-174">유효한 값은 1에서 50 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="6a617-175">기본값은 15입니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-175">The default value is 15.</span></span>

   - <span data-ttu-id="6a617-176">`BccEmailAddress` 모든 사용자 전송의 복사본을 받을 추가 숨은 참조 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="6a617-177">기본값은 비워 두며(추가 숨은 참조 받는 사람 없음)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="6a617-178">다음은 기본 설정을 사용하여 지정된 경로에서 64비트 버전의 추가 기능을 설치하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="6a617-179">다음은 추가 설정을 사용하여 지정된 경로에서 32비트 버전의 추가 기능을 설치하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="6a617-180">단일 제출에서 최대 20개 메시지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="6a617-181">junkreports@contoso.com 때 hollyd@treyresearch.net 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6a617-182">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="6a617-182">How do you know this worked?</span></span>

<span data-ttu-id="6a617-183">정크 메일 보고 추가 기능이 성공적으로 설치되었는지 확인하려면 Outlook에서 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="6a617-184">메시지를 선택하거나 메시지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-184">Select the message or open the message.</span></span> <span data-ttu-id="6a617-185">**리본의** **홈 또는** 메시지 탭에서 **정크 메일을 클릭하고**다음 옵션을 사용할 수 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="6a617-186">**정크 메일로 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-186">**Report as Junk**</span></span>
  - <span data-ttu-id="6a617-187">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="6a617-188">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="6a617-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="6a617-189">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-189">**Report Junk Online Help**</span></span>

  ![리본 메뉴에서 정크 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="6a617-191">메시지를 마우스 오른쪽 버가 클릭하고, **정크를 선택한**후 다음 옵션을 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="6a617-192">**정크 메일로 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-192">**Report as Junk**</span></span>
  - <span data-ttu-id="6a617-193">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="6a617-194">**정크 보고 옵션**</span><span class="sxs-lookup"><span data-stu-id="6a617-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="6a617-195">**정크 온라인 도움말 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-195">**Report Junk Online Help**</span></span>

  ![마우스 오른쪽 단추 클릭에서 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="6a617-197">여러 메시지를 선택한 후 마우스 오른쪽 단추로 클릭하고 다음 옵션을 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="6a617-198">**정크 메일로 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-198">**Report as Junk**</span></span>
  - <span data-ttu-id="6a617-199">**피싱으로 보고**</span><span class="sxs-lookup"><span data-stu-id="6a617-199">**Report as Phishing**</span></span>

  ![마우스 오른쪽 단추로 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="6a617-201">정크 메일 폴더의 이전 **작업을 수행하고** 이전 **정크 보고 옵션이 이제** 정크 메일아님을 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![정크 메일 폴더의 리본 메뉴에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추로 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="6a617-205">정크 메일 보고 추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="6a617-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="6a617-206">Outlook을 닫은 후에는 다음 절차 중 하나를 사용하여 정크 메일 보고 추가 기능을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="6a617-207">**제어판:** Windows 키 + R을 누릅니다. **열리는** 실행 대화 상자에서 확인 을 `control appwiz.cpl` 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="6a617-208">목록에서 **Microsoft 정크 메일 보고 추가 기능을 찾아서** 선택한 다음 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="6a617-209">**Windows Installer 패키지:** 해당 .msi 파일을 찾아서 다운로드한 다음, 해당 파일을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="6a617-210">**32비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6a617-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="6a617-211">**64비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6a617-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="6a617-212">표시되는 대화 상자에서 **Outlook용 Microsoft 정크 메일 보고 추가 기능 제거를 선택하고 다음을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a617-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="6a617-213">**자동 모드: 해당**.msi 파일을 찾거나 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="6a617-214">명령 프롬프트 창에서 \<PathToFile\> .msi 파일 위치로 바꾸고 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="6a617-215">**32비트:**</span><span class="sxs-lookup"><span data-stu-id="6a617-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="6a617-216">**64비트:**</span><span class="sxs-lookup"><span data-stu-id="6a617-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="6a617-217">제거 후 Outlook을 열면 정크 메일이 아님이 며며 정크 메일이 아님을 확인하고 이를 실행하면 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="6a617-218">정크 메일 보고 추가 기능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6a617-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="6a617-219">경우에 따라 정크 메일 보고 추가 기능을 추가한 후 Outlook에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="6a617-220">이 섹션에서는 문제 해결 팁과 함께 발생할 수 있는 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="6a617-221">사용자를 위한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6a617-221">Troubleshooting for users</span></span>

<span data-ttu-id="6a617-222">다음 문제 중 하나 이상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="6a617-223">**정크 메일 보고**를 클릭해도 아무 작업도 수행되지 않음</span><span class="sxs-lookup"><span data-stu-id="6a617-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="6a617-224">전자 메일 메시지를 선택한 후 Outlook의 응답이 중지됨</span><span class="sxs-lookup"><span data-stu-id="6a617-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="6a617-225">"배달 불능" 응답으로 인해 보고된 정크 메일을 배달할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6a617-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="6a617-226">이 문제를 해결하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="6a617-227">Outlook을 닫은 후 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="6a617-228">테스트 메시지를 만들고 보낸 다음 받는 사람이 메시지를 받은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="6a617-229">문제가 계속되면 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="6a617-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="6a617-230">메시지를 Microsoft에 제출하는 데 사용할 수 있는 다른 방법은 Microsoft에 [보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6a617-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="6a617-231">관리자를 위한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6a617-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="6a617-232">문제: 시스템 관리자에게 문의하라는 오류 메시지가 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="6a617-233">레지스트리 키를 `LoggingLevel` 확인하거나 설정하여 "Verbose" 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="6a617-234">**32비트 Windows의 32비트 Outlook:**</span><span class="sxs-lookup"><span data-stu-id="6a617-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="6a617-235">**64비트 Windows의 32비트 Outlook:**</span><span class="sxs-lookup"><span data-stu-id="6a617-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="6a617-236">**64비트 Outlook**:</span><span class="sxs-lookup"><span data-stu-id="6a617-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="6a617-237">Outlook을 다시 시작하고 오류 메시지가 표시되면 다시 보고하도록 사용자에게 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="6a617-238">다음 위치에 있는 로그 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="6a617-239">Exchange Online Protection 기술 지원 서비스에 문의하여 로그 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="6a617-240">문제: 사용자가 메시지를 보고할 때 확인 메시지를 수신하지 않아가 선택한 후 메시지를 다시 확인하도록</span><span class="sxs-lookup"><span data-stu-id="6a617-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="6a617-241">다음과 `ConfirmReportJunk` 문자열 속성을 사용하여 기본값 "True"로 레지스트리 키를 만들고</span><span class="sxs-lookup"><span data-stu-id="6a617-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="6a617-242">Outlook을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6a617-242">Restart Outlook.</span></span>

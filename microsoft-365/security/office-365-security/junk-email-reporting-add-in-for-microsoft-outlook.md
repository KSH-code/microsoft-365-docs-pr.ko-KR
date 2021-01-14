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
ms.openlocfilehash: 2b98fb0183cb7164ee90fb6a3a22d949e6edc2bc
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865067"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook용 정크 메일 보고 추가 기능 설치 및 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 현재 정크 메일 보고 추가 기능을 사용하지 않는 경우 대신 보고서 [](enable-the-report-message-add-in.md) 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하는 [것이](enable-the-report-phish-add-in.md) 좋습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

Microsoft Outlook용 정크 메일 보고 추가 기능을 사용하면 가음성(스팸으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 전자 메일 허용) 및 피싱 메시지를 Microsoft에 제출할 수 있습니다. 조직에서 Exchange Online Protection(예: Exchange Online 또는 Exchange Online이 아닌 전자 메일 서비스)을 사용하지 않는 경우 정크 메일 보고서 제출은 스팸 필터링에 영향을 주지 않습니다.

이 항목에서는 정크 메일 보고 추가 기능을 설치하고 사용하는 방법을 설명합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 정크 메일 보고 추가 기능을 설치하려면 [](#install-the-junk-email-reporting-add-in) 이 문서 부분의 정크 메일 보고 추가 기능 설치 섹션을 참조하세요.

- 정크 메일 보고 추가 기능에서는 다음 버전의 Outlook과 함께 작동합니다.

  - Outlook 2013 이상
  - 엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook

- Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>정크 메일 보고 추가 기능을 사용하여 스팸 및 피싱 메시지 보고

1. 받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법 중 한 가지를 사용하여 스팸 및 피싱 메시지를 보고합니다.

   - 메시지를 선택하거나 메시지를 열 수 있습니다. 리본의 홈 **또는** 메시지 탭에서 정크를  클릭한 다음 정크 메일로 보고 또는 피싱으로  **보고를 선택합니다.** 

     ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

   - 메시지를 마우스 오른쪽 단추로 클릭하고 정크를 선택한 다음 정크 메일로 보고 또는 피싱으로 **보고를 선택합니다.** 

     ![마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

   - 여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 **정크** 메일로 보고 또는 **피싱으로 보고를 선택합니다.**

     ![마우스 오른쪽 단추를 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

2. 나타나는 대화 상자에서 정보를 읽고 보고서를 **클릭합니다.** 마음이 바뀌면 보고 안 **를 클릭합니다.**

   ![정크로 보고 대화 상자](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![피싱으로 보고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.

   - 스팸으로 보고된 정크 메일 폴더로 이동되었습니다.
   - 피싱으로 보고된 경우 삭제되었습니다.

   메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>정크 메일 보고 추가 기능을 사용하여 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지 보고

1. 정크 메일 폴더에서 다음 방법 중 한 가지를 사용하여 스팸 가긍성 또는 피싱 메시지를 보고합니다.

   - 메시지를 선택하거나 메시지를 열 수 있습니다. 리본의 홈 **또는** 메시지 탭에서 정크 메일  아님을 클릭한 다음 보고를 정크 메일 아님 또는 피싱으로  **보고를 선택합니다.** 

     ![정크 메일 폴더의 리본 메뉴에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - 메시지를 마우스 오른쪽 단추로 클릭하고 정크를 클릭한 다음 보고를 정크 메일 아님 또는 피싱으로 **보고를 선택합니다.** 

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 **보고를** 정크 메일 아님 또는 피싱으로 **보고를 선택합니다.**

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 여러 정크 메일 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 나타나는 대화 상자에서 정보를 읽고 보고서를 **클릭합니다.** 마음이 바뀌면 보고 안 **를 클릭합니다.**

   ![정크 아님으로 보고 대화 상자](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![피싱으로 보고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.

   - 스팸으로 보고된 정크 메일 폴더로 이동되었습니다.
   - 피싱으로 보고된 경우 삭제되었습니다.

   메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.

## <a name="install-the-junk-email-reporting-add-in"></a>정크 메일 보고 추가 기능 설치

- 추가 기능을 설치하는 컴퓨터에 대한 관리자 권한이 필요합니다.

- Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:

  - **32비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Outlook 2013 이상에서는 Microsoft .NET Framework 2.0만 선행해야 합니다. Windows 10에서는 다운로드에서 .NET Framework 2.0을 설치하지 않습니다.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>설치 마법사를 사용하여 정크 메일 보고 추가 기능 설치

1. 컴퓨터에서 Outlook을 종료합니다.

2. Windows 10에서 .NET Framework 2.0이 사용하도록 설정되어 있는지 확인합니다. 자세한 내용은 제어판에서 [.NET Framework 3.5 사용을 참조하세요.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. 다운로드한 .msi 파일을 찾아 두 번 클릭합니다.

4. **Microsoft 정크 메일 보고 추가 기능 설치 시작** 페이지에서 **다음** 을 클릭합니다.

5. 사용권 계약을  검토하고 사용권 계약에 동의하는 경우 동의를 클릭한 후 다음을 **클릭합니다.**

6. 마법사가 완료되면 **마침** 을 클릭합니다.

Outlook을 시작합니다.

Outlook 리본에서 **정크** 단추를 찾습니다. 이제 받은 편지함에서 정크 메일 메시지를 선택하고 **정크 메일 보고** 단추를 클릭하여 Microsoft로 정크 메일 메시지를 보고할 수 있습니다.

Microsoft에 피싱 메일을 보고하려는 경우 **피싱 메일로 보고** 와 같은 기타 옵션을 보려면 **정크** 옆에 있는 아래쪽 화살표를 선택합니다. 전자 메일이 정크 메일로 잘못 식별된 경우 정크 메일 폴더에서 **정크 메일 아님으로 보고** 를 선택할 수도 있습니다.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>자동 모드를 사용하여 정크 메일 보고 추가 기능 설치

1. 컴퓨터에서 Outlook을 종료합니다.

2. Windows 10에서 다음 명령을 실행하여 .NET Framework 2.0을 설치합니다.

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. 사용자 상호 작용 없이 추가 기능을 설치하려면 명령 프롬프트를 열고 다음 구문을 사용 합니다.

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 단일 전송에 대해 선택할 수 있는 최대 메시지 수를 지정합니다. 유효한 값은 1에서 50까지입니다. 기본값은 15입니다.

   - `BccEmailAddress` 모든 사용자 제출의 복사본을 받을 추가 Bcc 받는 사람을 지정합니다. 기본값은 비어 있습니다(추가 Bcc 받는 사람 없음).

   이 예제에서는 기본 설정으로 지정된 경로에서 추가 기능의 64비트 버전을 설치합니다.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   이 예제에서는 다음과 같은 추가 설정을 사용하여 지정된 경로에서 추가 기능의 32비트 버전을 설치합니다.

   - 단일 제출에서 최대 20개 메시지를 선택할 수 있습니다.
   - junkreports@contoso.com 및 hollyd@treyresearch.net 모든 제출의 Bcc 복사본을 수신합니다.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

정크 메일 보고 추가 기능을 성공적으로 설치했다는 확인을 위해 Outlook에서 다음 단계를 수행합니다.

- 메시지를 선택하거나 메시지를 열 수 있습니다. 리본 **메뉴의 홈** **또는** 메시지 탭에서 정크를 클릭하고 **다음** 옵션을 사용할 수 있는지 확인해야 합니다.

  - **정크로 보고**
  - **피싱으로 보고**
  - **정크 보고 옵션**
  - **정크 온라인 도움말 보고**

  ![리본에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-ribbon.png)

- 메시지를 마우스 오른쪽 단추로 클릭하고 정크를 선택한 다음 다음 옵션을 사용할 수 있는지 확인해야 합니다.

  - **정크로 보고**
  - **피싱으로 보고**
  - **정크 보고 옵션**
  - **정크 온라인 도움말 보고**

  ![마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

- 여러 메시지를 선택하고 마우스 오른쪽 단추를 클릭한 다음 다음 옵션을 사용할 수 있는지 확인해야 합니다.

  - **정크로 보고**
  - **피싱으로 보고**

  ![마우스 오른쪽 단추를 클릭하여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

- 정크 메일 폴더에서 이전 작업을 수행하고  이전 정크 보고 옵션이 이제 정크  **메일이 아닌지 확인합니다.**

  ![정크 메일 폴더의 리본 메뉴에서 정크 메일 또는 피싱 메일 보고](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 정크 메일 또는 피싱 메일 아님 보고](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭하여 여러 정크 메일 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>정크 메일 보고 추가 기능 제거

Outlook을 닫은 후 다음 절차에 따라 정크 메일 보고 추가 기능을 제거합니다.

- **제어판**: Windows 키 + R을 누르는 경우 실행 **대화** 상자가 열리면 입력한 `control appwiz.cpl` 다음 확인을 **클릭합니다.**

  목록에서 **Microsoft 정크 메일** 보고 추가 기능을 찾아 선택한 다음 **제거를 클릭합니다.**

- **Windows Installer 패키지:** 적절한 .msi 파일을 찾거나 다운로드한 다음 두 번 클릭합니다.

  - **32비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64비트:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  나타나는 대화 상자에서 **Outlook용 Microsoft 정크** 메일 보고 추가 기능 제거를 선택하고 다음을 **클릭합니다.**

- **자동 모드:** 적절한 .msi 파일을 찾거나 다운로드합니다. 명령 프롬프트 창에서 .msi 파일의 위치로 바꾸고 다음 명령 중 \<PathToFile\> 하나를 실행합니다.

  - **32비트:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64비트:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

제거 후 Outlook을 열면 정크가 아닌 정크 및 피싱 보고 옵션이 사라집니다.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>정크 메일 보고 추가 기능 문제 해결

경우에 따라 정크 메일 보고 추가 기능을 추가한 후 Outlook에 문제가 있을 수 있습니다. 이 섹션에서는 발생할 수 있는 문제에 대해 설명하고 이러한 문제를 해결하기 위한 팁을 제공합니다.

### <a name="troubleshooting-for-users"></a>사용자 문제 해결

다음 문제 중 하나 이상이 발생할 수 있습니다.

- **정크 메일 보고** 를 클릭해도 아무 작업도 수행되지 않음
- 전자 메일 메시지를 선택한 후 Outlook의 응답이 중지됨
- "배달 불능" 응답으로 인해 보고된 정크 메일을 배달할 수 없음

이 문제를 해결하려면 다음 단계를 수행합니다.

1. Outlook을 닫았다가 다시 시작합니다.
2. 테스트 메시지를 만들고 보내고 받는 사람이 메시지를 받았는지 확인
3. 문제가 계속되면 관리자에게 문의하세요.

Microsoft에 메시지를 전송하는 데 사용할 수 있는 다른 방법은 Microsoft에 메시지 및 [파일 보고를 참조합니다.](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>관리자를 위한 문제 해결

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>문제: 사용자에게 시스템 관리자에게 문의할지 묻는 오류 메시지가 계속 표시됩니다.

1. 레지스트리 키를 `LoggingLevel` "Verbose" 값으로 확인하거나 설정

   - **32비트 Windows의 32비트 Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64비트 Windows의 32비트 Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64비트 Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Outlook을 다시 시작하고 사용자에게 오류 메시지가 표시될 때 다시 보고해달고 요청합니다.

3. 다음 위치에 있는 로그 정보를 수집합니다.

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection 기술 지원 서비스에 문의하여 로그 정보를 제공합니다.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>문제: 사용자가 메시지를 보고할 때 확인 메시지를 받지 못하게 선택되어 메시지가 다시 표시될 수 있습니다.

1. "True" 값을 사용하여 `ConfirmReportJunk` 레지스트리 키를 만드시다.

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Outlook을 다시 시작합니다.

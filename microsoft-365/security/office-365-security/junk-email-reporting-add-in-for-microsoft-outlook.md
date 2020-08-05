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
ms.openlocfilehash: 54b0fb634333ccb180870ab1fcc6160fd133f81e
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560524"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook 용 정크 메일 보고 추가 기능 설치 및 사용

> [!NOTE]
> 현재 정크 메일 보고 추가 기능을 사용 하지 않는 경우에는 대신 [보고서 메시지 추가 기능](enable-the-report-message-add-in.md) 을 사용할 것을 권장 합니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

Microsoft Outlook 용 정크 메일 보고 추가 기능을 사용 하면 사용자가 가양성 (스팸으로 표시 된 전자 메일), 거짓 부정 (잘못 된 전자 메일 허용), Microsoft에 피싱 메시지를 제출할 수 있습니다. 조직에서 exchange online Protection을 사용 하지 않는 경우 (예: Exchange Online 이외의 온-프레미스 Exchange 또는 전자 메일 서비스) 정크 메일 보고서 제출은 스팸 필터링에 영향을 주지 않습니다.

이 항목에서는 정크 메일 보고 추가 기능을 설치 하 고 사용 하는 방법에 대해 설명 합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 정크 메일 보고 추가 기능을 설치 하려면이 항목의 뒷부분에 나오는 [정크 메일 보고 추가 기능 설치](#install-the-junk-email-reporting-add-in) 섹션을 참조 하십시오.

- 정크 메일 보고 추가 기능을 사용 하는 Outlook 버전은 다음과 같습니다.

  - Outlook 2013 이상
  - Microsoft 365 for enterprise 앱에 포함 된 Outlook

- Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>정크 메일 보고 추가 기능을 사용 하 여 스팸 및 피싱 메시지 보고

1. 받은 편지함 또는 정크 메일을 제외한 다른 모든 전자 메일 폴더의 메시지에 대해 다음 방법 중 하나를 사용 하 여 스팸 및 피싱 메시지를 보고 합니다.

   - 메시지를 선택 하거나 메시지를 엽니다. 리본 메뉴의 **홈** 또는 **메시지** 탭에서 **정크**을 클릭 하 고 **정크 메일로 보고** 또는 **피싱 메일로**보고서를 선택 합니다.

     ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-ribbon.png)

   - 메시지를 마우스 오른쪽 단추로 클릭 하 고 **정크**을 선택한 후 **정크** 메일로 또는 **피싱**메일로 보고를 선택 합니다.

     ![마우스 오른쪽 단추를 클릭 하 여 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

   - 여러 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크** 메일로 또는 **피싱**메일로 보고를 선택 합니다.

     ![마우스 오른쪽 단추를 클릭 하 여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

2. 대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다. 생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.

   ![정크 메일로 신고 대화 상자](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 선택한 메시지는 분석을 위해 Microsoft로 전송 됩니다.

   - 스팸으로 보고 된 경우 정크 메일 폴더로 이동 됩니다.
   - 피싱 메일로 보고 된 경우 삭제 됩니다.
   
   메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>정크 메일 보고 추가 기능을 사용 하 여 정크 메일 폴더에서 스팸이 아닌 메시지 및 피싱 메시지가 보고 되도록 합니다.

1. 정크 메일 폴더에서 다음 방법 중 하나를 사용 하 여 스팸 가양성 또는 피싱 메시지를 보고 합니다.

   - 메시지를 선택 하거나 메시지를 엽니다. 리본 메뉴의 **홈** 또는 **메시지** 탭에서 **정크 메일**아님으로를 클릭 한 다음 **정크 메일 아님으로 보고** 또는 **피싱 메일로 보고**를 선택 합니다.

     ![정크 메일 폴더의 리본에서 정크 또는 피싱 전자 메일을 보고 하지 않습니다.](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - 메시지를 마우스 오른쪽 단추로 클릭 하 고 **정크**메일을 클릭 한 다음 **정크 메일 아님으로 보고** 또는 **피싱 메일로 보고**를 선택 합니다.

     ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭 하면 정크 메일 또는 피싱 전자 메일이 보고 되지 않음](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 여러 메시지를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **정크 메일 아님으로 보고** 또는 **피싱 메일로 보고**를 선택 합니다.

     ![정크 메일 폴더의 오른쪽 클릭에서 정크 메일이 아닌 전자 메일 메시지를 여러 개 보고 합니다.](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 대화 상자가 나타나면 정보를 읽고 **보고서**를 클릭 합니다. 생각이 변경 되 면 **보고서 표시 안 함을**클릭 합니다.

   ![정크 메일 아님으로 보고 대화 상자](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![피싱 메일로 신고 대화 상자](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 선택한 메시지는 분석을 위해 Microsoft로 전송 됩니다.

   - 스팸으로 보고 된 경우 정크 메일 폴더로 이동 됩니다.
   - 피싱 메일로 보고 된 경우 삭제 됩니다.

   메시지가 전송되었는지 확인하려면 **보낸 편지함** 폴더를 열고 전송한 메시지를 확인합니다.

## <a name="install-the-junk-email-reporting-add-in"></a>정크 메일 보고 추가 기능 설치

- 추가 기능을 설치 하는 컴퓨터에 대 한 관리자 권한이 있어야 합니다.

- <https://www.microsoft.com/download/details.aspx?id=18275>Office 버전의 적절 한 .msi 파일을 쉽게 찾을 수 있는 위치로 이동한 후 다운로드 합니다.

  - **32 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Outlook 2013 이상 버전의 경우에는 Microsoft .NET Framework 2.0에만 필수 구성 요소를 사용할 수 있습니다. Windows 10에서는 다운로드에서 .NET Framework 2.0을 설치 하지 않습니다.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>설치 마법사를 사용 하 여 정크 메일 보고 추가 기능 설치

1. 컴퓨터에서 Outlook을 종료합니다.

2. Windows 10에서는 .NET Framework 2.0가 사용 하도록 설정 되어 있는지 확인 합니다. 자세한 내용은 [제어판에서 .Net Framework 3.5을 사용 하도록 설정](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)을 참조 하십시오.

3. 다운로드 한 .msi 파일을 찾아 두 번 클릭 합니다.

4. **Microsoft 정크 메일 보고 추가 기능 설치 시작** 페이지에서 **다음**을 클릭합니다.

5. 사용권 계약을 검토 하 고 **사용권 계약에** 동의 하는 경우 동의 함을 클릭 한 후 **다음**을 클릭 합니다.

6. 마법사가 완료되면 **마침**을 클릭합니다.

Outlook을 시작합니다.

Outlook 리본에서 **정크** 단추를 찾습니다. 이제 받은 편지함에서 정크 메일 메시지를 선택하고 **정크 메일 보고** 단추를 클릭하여 Microsoft로 정크 메일 메시지를 보고할 수 있습니다.

Microsoft에 피싱 메일을 보고하려는 경우 **피싱 메일로 보고**와 같은 기타 옵션을 보려면 **정크** 옆에 있는 아래쪽 화살표를 선택합니다. 전자 메일이 정크 메일로 잘못 식별된 경우 정크 메일 폴더에서 **정크 메일 아님으로 보고**를 선택할 수도 있습니다.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>자동 모드를 사용하여 정크 메일 보고 추가 기능 설치

1. 컴퓨터에서 Outlook을 종료합니다.

2. Windows 10에서는 다음 명령을 실행 하 여 .NET Framework 2.0을 설치 합니다.

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. 사용자 상호 작용 없이 추가 기능을 설치 하려면 명령 프롬프트를 열고 다음 구문을 사용 합니다.

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection`단일 전송에 대해 선택할 수 있는 최대 메시지 수를 지정 합니다. 유효한 값은 1에서 50 사이입니다. 기본값은 15입니다.

   - `BccEmailAddress`모든 사용자 전송의 복사본을 받을 추가 숨은 참조 받는 사람을 지정 합니다. 기본값은 빈 값 (추가 숨은 참조 받는 사람 없음)입니다.

   이 예제에서는 지정 된 경로에서 기본 설정을 사용 하 여 64 비트 버전의 추가 기능을 설치 합니다.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   이 예제에서는 다음 추가 설정을 사용 하 여 지정 된 경로에서 32 비트 버전의 추가 기능을 설치 합니다.

   - 단일 전송에서 최대 20 개의 메시지를 선택할 수 있습니다.
   - junkreports@contoso.com 및 hollyd@treyresearch.net는 모든 전송의 숨은 참조 복사본을 받습니다.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>작동 여부는 어떻게 확인하나요?

정크 메일 보고 추가 기능이 성공적으로 설치 되었는지 확인 하려면 Outlook에서 다음 단계 중 하나를 수행 합니다.

- 메시지를 선택 하거나 메시지를 엽니다. 리본 메뉴의 **홈** 또는 **메시지** 탭에서 **정크**을 클릭 하 고 다음 옵션을 사용할 수 있는지 확인 합니다.

  - **정크로 신고**
  - **피싱 메일로 신고**
  - **정크 보고 옵션**
  - **정크 온라인 도움말 보고**

  ![리본 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-ribbon.png)

- 메시지를 마우스 오른쪽 단추로 클릭 하 고 **정크**을 선택한 후 다음 옵션을 사용할 수 있는지 확인 합니다.

  - **정크로 신고**
  - **피싱 메일로 신고**
  - **정크 보고 옵션**
  - **정크 온라인 도움말 보고**

  ![마우스 오른쪽 단추를 클릭 하 여 정크 또는 피싱 전자 메일 보고](../../media/junk-email-reporting-right-click.png)

- 여러 메시지를 선택한 다음 마우스 오른쪽 단추를 클릭 하 고 다음 옵션을 사용할 수 있는지 확인 합니다.

  - **정크로 신고**
  - **피싱 메일로 신고**

  ![마우스 오른쪽 단추를 클릭 하 여 여러 정크 또는 피싱 전자 메일 메시지 보고](../../media/junk-email-reporting-right-click-multiple.png)

- **정크 메일** 폴더에서 이전 작업을 수행 하 고 이전 **정크** 보고 옵션이 현재 **정크 메일이 아닌지**확인 합니다.

  ![정크 메일 폴더의 리본에서 정크 또는 피싱 전자 메일을 보고 하지 않습니다.](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![정크 메일 폴더에서 마우스 오른쪽 단추를 클릭 하면 정크 메일 또는 피싱 전자 메일이 보고 되지 않음](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![정크 메일 폴더의 오른쪽 클릭에서 정크 메일이 아닌 전자 메일 메시지를 여러 개 보고 합니다.](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>정크 메일 보고 추가 기능 제거

Outlook을 닫은 후에는 다음 절차 중 하나를 사용 하 여 정크 메일 보고 추가 기능을 제거 합니다.

- **제어판**: Windows 키 + R을 누릅니다. 열리는 **실행** 대화 상자에서를 입력 하 `control appwiz.cpl` 고 **확인**을 클릭 합니다.

  목록에서 **Microsoft 정크 메일 보고 추가 기능** 을 찾아 선택한 다음 **제거**를 클릭 합니다.

- **Windows Installer 패키지**: 해당 .msi 파일을 찾거나 다운로드 한 후에 두 번 클릭 합니다.

  - **32 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 비트**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  대화 상자가 나타나면 **Outlook 용 Microsoft 정크 메일 보고 추가 기능 제거** 를 선택 하 고 **다음**을 클릭 합니다.

- **자동 모드**: 적절 한 .msi 파일을 찾거나 다운로드 합니다. 명령 프롬프트 창에서 \<PathToFile\> .msi 파일의 위치로 대체 하 고 다음 명령 중 하나를 실행 합니다.

  - **32 비트**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 비트**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

제거 후 Outlook을 여는 경우 정크 메일이 아닌 정크 메일 및 피싱 보고 옵션이 없어졌습니다.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>정크 메일 보고 추가 기능 문제 해결

경우에 따라 정크 메일 보고 추가 기능을 추가한 후 Outlook에서 문제가 발생할 수 있습니다. 이 섹션에서는 이러한 문제를 해결 하기 위한 팁과 함께 발생할 수 있는 문제에 대해 설명 합니다.

### <a name="troubleshooting-for-users"></a>사용자 문제 해결

다음 문제 중 하나 이상이 발생 합니다.

- **정크 메일 보고**를 클릭해도 아무 작업도 수행되지 않음
- 전자 메일 메시지를 선택한 후 Outlook의 응답이 중지됨
- "배달 불능" 응답으로 인해 보고된 정크 메일을 배달할 수 없음

이 문제를 해결 하려면 다음 단계를 수행 합니다.

1. Outlook을 닫았다가 다시 시작 합니다.
2. 테스트 메시지를 만들어 보낸 후 받는 사람이 메시지를 받았는지 확인 합니다.
3. 문제가 계속 되 면 관리자에 게 문의 하세요.

Microsoft에 메시지를 전송 하는 데 사용할 수 있는 다른 방법에 대 한 자세한 내용은 [Report messages and files In microsoft](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.

### <a name="troubleshooting-for-admins"></a>관리자를 위한 문제 해결

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>문제: 사용자에 게 시스템 관리자에 게 문의 하 라는 오류 메시지가 계속 표시 됩니다.

1. `LoggingLevel`레지스트리 키를 "Verbose" 값으로 확인 하거나 설정 합니다.

   - **32 비트 Windows에서 32 비트 Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 비트 Windows에서 32 비트 Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 비트 Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Outlook을 다시 시작 하 고 오류 메시지가 표시 되 면 다시 사용자에 게 보고할지 묻습니다.

3. 다음 위치에 있는 로그 정보를 수집합니다.

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection 기술 지원 서비스에 문의하여 로그 정보를 제공합니다.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>문제: 사용자가 메시지를 보고 했을 때 확인 메시지를 수신 하지 않도록 선택 했으며, 다시 확인 하 고 싶습니다.

1. `ConfirmReportJunk`"True" 값을 사용 하 여 레지스트리 키를 만듭니다.

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Outlook을 다시 시작합니다.

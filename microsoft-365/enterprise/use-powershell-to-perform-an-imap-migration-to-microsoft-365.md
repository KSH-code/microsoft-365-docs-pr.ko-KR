---
title: PowerShell을 사용하여 Microsoft 365로 IMAP 마이그레이션 수행
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: PowerShell을 사용하여 IMAP(Internet Mail Access Protocol) 마이그레이션을 수행하는 방법을 Microsoft 365.
ms.openlocfilehash: 08cffcbe3a08031df05da68358da062200eb99c5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163243"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>PowerShell을 사용하여 Microsoft 365로 IMAP 마이그레이션 수행

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

사용자 사서함을 배포하는 Microsoft 365 IMAP(Internet Mail Access Protocol) 전자 메일 서비스에서 사용자 사서함의 콘텐츠를 마이그레이션하도록 선택할 수 Microsoft 365. 이 문서에서는 Exchange Online PowerShell을 사용하는 전자 메일 IMAP 마이그레이션 작업을 살펴봅니다.

> [!NOTE]
> Exchange 관리 센터를 사용하여 IMAP 마이그레이션을 수행할 수도 있습니다. [IMAP 사서함 마이그레이션을 참조합니다.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

이 작업의 예상 완료 시간: 2-5분(마이그레이션 일괄 처리 만들기에 소요되는 시간). 마이그레이션 일괄 처리가 시작되면 마이그레이션 기간은 일괄 처리의 사서함 수, 각 사서함의 크기 및 사용 가능한 네트워크 용량에 따라 달라집니다. 사서함을 마이그레이션하는 데 걸리는 시간에 영향을 주는 다른 요인에 대한 자세한 내용은 Microsoft 365 [성능 을 참조하세요.](/Exchange/mailbox-migration/office-365-migration-best-practices)

이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인하려면 [받는 사람 사용 권한](/exchange/recipients-permissions-exchange-2013-help)의 표에 나오는 "마이그레이션" 항목을 참조하세요.

Exchange Online PowerShell cmdlet을 사용하려면 로그인한 후 cmdlet을 로컬 Windows PowerShell 세션으로 가져와야 합니다. 해당 지침은 [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](/powershell/exchange/)을 참조하세요.

IMAP 마이그레이션에 적용되는 제한 사항은 다음과 같습니다.

- 사용자의 받은 편지함 또는 다른 메일 폴더에 있는 항목만 마이그레이션할 수 있습니다. 연락처, 일정 항목 또는 작업은 마이그레이션할 수 없습니다.

- 최대 500,000개 항목을 사용자 사서함에서 마이그레이션할 수 있습니다.

- 마이그레이션할 수 있는 최대 메시지 크기는 35MB입니다.

## <a name="migration-steps"></a>마이그레이션 단계

### <a name="step-1-prepare-for-an-imap-migration"></a>1단계: IMAP 마이그레이션 준비
<a name="BK_Step1"> </a>

- **IMAP 조직에 대한 도메인이 있는 경우 해당 도메인을 사용자 조직의 허용 도메인으로 Microsoft 365.** Microsoft 365 사서함에 대해 이미 소유하고 있는 동일한 도메인을 사용하려면 먼저 허용 도메인으로 추가해야 Microsoft 365. 사용자를 추가한 후 사용자 계정을 만들 수 Microsoft 365. 자세한 내용은[도메인 확인을 참조하세요.](../admin/setup/add-domain.md)

- **사서함이 Microsoft 365 각 사용자를 추가합니다.** 자세한 내용은[비즈니스용 앱에 Microsoft 365 추가를 참조하세요.](../admin/add-users/add-users.md)

- **IMAP 서버의 FQDN을 받습니다**. IMAP 마이그레이션 끝점을 만들 때 사서함 데이터를 마이그레이션할 원본 IMAP 서버의 FQDN(정규화된 도메인 이름)(전체 컴퓨터 이름이라고도 함)을 제공해야 합니다. IMAP 클라이언트나 PING 명령을 사용하여 인터넷에서 해당 FQDN으로 IMAP 서버와 통신할 수 있는지 확인합니다.

- **IMAP 연결을 허용하도록 방화벽을 구성** 합니다. 마이그레이션 도중에 Microsoft 데이터 센터에서 시작된 네트워크 트래픽이 IMAP 서버를 호스트하는 조직에 유입될 수 있도록 하기 위해 IMAP 서버를 호스트하는 조직의 방화벽에서 포트를 열어야 할 수도 있습니다. Microsoft 데이터 센터에서 사용하는 IP 주소 목록은 [Exchange Online URL 및 IP 주소 범위](./urls-and-ip-address-ranges.md)를 참조하세요.

- **관리자 계정에 IMAP 조직 내의 사서함에 액세스하기 위한 권한을 할당** 합니다. CSV 파일의 관리자 자격 증명을 사용하는 경우 사용하는 계정에 온-프레미스 사서함에 액세스하는 데 필요한 권한이 있어야 합니다. 사용자 사서함에 액세스하는 데 필요한 권한은 특정 IMAP 서버에 의해 결정됩니다.

- **Exchange Online PowerShell cmdlet** 을 사용하려면 로그인한 후 cmdlet을 로컬 Windows PowerShell 세션으로 가져와야 합니다. 해당 지침은 [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

    전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](/powershell/exchange/)을 참조하세요.

- **IMAP 서버에 연결할 수 있는지 확인** 합니다. Exchange Online PowerShell에서 다음 명령을 실행하여 IMAP 서버에 대한 연결 설정을 테스트합니다.

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    **Port** 매개 변수의 값으로는 일반적으로 암호화되지 않은 연결 또는 TLS(전송 계층 보안) 연결의 경우 143을 사용하고 SSL 연결의 경우 993을 사용합니다.

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>2단계: IMAP 마이그레이션 일괄 처리를 위한 CSV 파일 만들기
<a name="BK_Step2"> </a>

IMAP 마이그레이션 일괄 처리에서 해당 사서함을 마이그레이션할 사용자 그룹을 식별합니다. CSV 파일의 각 행에는 IMAP 메시징 시스템의 사서함에 연결하는 데 필요한 정보가 포함되어 있습니다.

각 사용자의 필수 특성은 다음과 같습니다.

- **EmailAddress는** 사용자의 사서함에 대한 사용자 ID를 Microsoft 365 지정합니다.

- **UserName** 은 IMAP 서버의 사서함에 액세스하는 데 사용할 계정의 로그온 이름을 지정합니다.

- **Password** 는 **UserName** 열에 있는 계정의 암호를 지정합니다.

다음은 CSV 파일 형식의 예입니다. 이 예에서는 다음 세 개의 사서함을 마이그레이션합니다.

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

**UserName** 특성의 경우, 사용자 이름 외에 IMAP 서버의 사서함에 액세스하는 데 필요한 권한이 할당된 계정의 자격 증명을 사용할 수 있습니다. 다음은 일부 IMAP 서버에 사용되는 특정 형식입니다.

 **Microsoft Exchange**

Microsoft Exchange의 IMAP 구현에서 전자 메일을 마이그레이션하는 경우에는 CSV 파일에서 **UserName** 특성에 **Domain/Admin_UserName/User_UserName** 형식을 사용합니다. Terry Adams, Ann Beebe, Paul Cannon의 전자 메일을 Exchange에서 마이그레이션한다고 가정해 보겠습니다. 메일 관리자 계정이 있습니다. 여기서 사용자 이름은 **mailadmin이고** 암호는 **P \@ ssw0rd입니다.** CSV 파일은 다음과 같이 나타납니다.

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**

Dovecot IMAP 서버와 같은 SASL(Simple Authentication and Security Layer)을 지원하는 IMAP 서버의 경우 **User_UserName*Admin_UserName** 형식을 사용하며, 여기서 추가 문자는 구성 가능한 구분 문자입니다. 관리자 자격 증명 **mailadmin** 및 **P \@ ssw0rd** 를 사용하여 Dovecot IMAP 서버에서 동일한 사용자의 전자 메일을 마이그레이션하고 있는 경우를 해보자. 이때 CSV 파일은 다음과 같습니다.

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**

Mirapoint Message Server에서 전자 메일을 마이그레이션하는 경우 관리자 자격 증명에 **\@ #user#Admin_UserName#** 형식을 사용하세요. 관리자 자격 증명 **mailadmin** 및 **P \@ ssw0rd를** 사용하여 Mirapoint에서 전자 메일을 마이그레이션하려면 CSV 파일은 다음과 같습니다.

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**

Courier IMAP와 같은 일부 원본 전자 메일 시스템은 사서함 관리자 자격 증명을 사용하여 사서함을 사서함으로 마이그레이션할 수 Microsoft 365. 대신, 가상 공유 폴더를 사용하도록 원본 전자 메일 시스템을 설정할 수 있습니다. 가상 공유 폴더를 사용하여 사서함 관리자 자격 증명을 통해 원본 전자 메일 시스템의 사용자 사서함에 액세스할 수 있습니다. Courier IMAP에 대한 가상 공유 폴더를 구성하는 방법에 대한 자세한 내용은 [공유 폴더](https://go.microsoft.com/fwlink/p/?LinkId=398870)를 참조하세요.

원본 전자 메일 시스템에서 가상 공유 폴더를 설정한 뒤 사서함을 마이그레이션하려면 선택적 특성인 **UserRoot** 를 마이그레이션 파일에 포함해야 합니다. 이 특성은 원본 전자 메일 시스템의 가상 공유 폴더 구조에서 각 사용자의 사서함 위치를 지정합니다. 예를 들어 Terry 사서함의 경로는 /users/terry.adams입니다.

다음은 **UserRoot** 특성을 포함하는 CSV 파일의 예입니다.

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>3단계: IMAP 마이그레이션 끝점 만들기
<a name="BK_Step3"> </a>

전자 메일을 마이그레이션하려면 Microsoft 365 전자 메일 시스템에 연결하고 통신해야 합니다. 이 작업을 수행하기 위해 Microsoft 365 끝점을 사용하게 됩니다. 또한 마이그레이션 끝점은 동시에 마이그레이션할 사서함의 수와 24시간마다 수행되는 증분 동기화 중에 동시에 동기화할 사서함 수도 정의합니다. IMAP 마이그레이션용 마이그레이션 끝점을 만들려면 먼저 [Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)합니다.

전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](/powershell/exchange/)을 참조하세요.

Exchange Online PowerShell에서 "IMAPEndpoint"라는 IMAP 마이그레이션 끝점을 만들려면 다음 명령을 실행합니다.

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

동시 마이그레이션, 동시 증분 마이그레이션 및 사용할 포트를 지정하기 위한 매개 변수를 추가할 수도 있습니다. 다음 Exchange Online PowerShell 명령은 50개의 동시 마이그레이션과 최대 25개의 동시 증분 동기화를 지원하는 "IMAPEndpoint"라는 IMAP 마이그레이션 끝점을 만듭니다. 또한 TLS 암호화를 위해 포트 143을 사용하도록 끝점을 구성합니다.

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

**New-MigrationEndpoint** cmdlet에 대한 자세한 내용은 [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)를 참조하세요.

#### <a name="verify-it-worked"></a>작동하는지 확인

Exchange Online PowerShell에서 다음 명령을 실행하여 "IMAPEndpoint"에 대한 정보를 표시합니다.

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>4단계: IMAP 마이그레이션 일괄 처리 만들기 및 시작
<a name="BK_Step4"> </a>

[New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet을 사용하여 IMAP 마이그레이션용 마이그레이션 일괄 처리를 만들 수 있습니다. _AutoStart_ 매개 변수를 포함하면 마이그레이션 일괄 처리를 만들고 자동으로 시작할 수 있습니다. 아니면 [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet을 사용해 마이그레이션 일괄 처리를 만든 다음 나중에 일괄 처리를 시작할 수도 있습니다.

다음 Exchange Online PowerShell 명령은 "IMAPEndpoint"라는 IMAP 끝점을 사용하여 "IMAPBatch1"이라는 마이그레이션 일괄 처리를 자동으로 시작합니다.

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>작동하는지 확인

[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet을 실행하여 "IMAPBatch1"에 대한 정보를 표시합니다.

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

다음 명령을 실행하여 일괄 처리가 시작되었는지 확인할 수도 있습니다.

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>5단계: 전자 메일을 메일로 Microsoft 365
<a name="BK_Step5"> </a>

전자 메일 시스템은 MX 레코드라는 DNS 레코드를 사용하여 전자 메일을 배달할 위치를 확인합니다. 전자 메일 마이그레이션 프로세스 중에는 MX 레코드가 원본 전자 메일 시스템을 가리켰습니다. 이제 전자 메일 마이그레이션을 Microsoft 365 이제 MX 레코드를 Microsoft 365. 이렇게 하면 전자 메일이 사용자 사서함으로 Microsoft 365 수 있습니다. MX 레코드를 이동하여 준비가 되었을 때 이전 전자 메일 시스템을 해제할 수도 있습니다.

DNS 공급자가 많이 있으므로 MX 레코드를 변경하기 위한 특정 지침이 제공됩니다. DNS 공급자가 포함되어 있지 않은 경우 또는 일반적인 지침을 확인하려는 경우 일반적인 [MX](https://go.microsoft.com/fwlink/?LinkId=397449) 레코드 지침도 제공됩니다.

고객 및 파트너의 전자 메일 시스템에서 변경된 MX 레코드를 인식하는 데는 최대 72시간이 걸릴 수 있습니다. 다음 작업을 계속 진행하기 전에 적어도 72시간 동안 기다립니다. 6단계: IMAP 마이그레이션 일괄 처리 삭제

### <a name="step-6-delete-imap-migration-batch"></a>6단계: IMAP 마이그레이션 일괄 처리 삭제
<a name="BK_Step6"> </a>

MX 레코드를 변경하고 모든 전자 메일이 Microsoft 365 사서함으로 라우팅되고 있는지 확인한 후 사용자에게 메일이 전송될 것 Microsoft 365. 그런 후에는 IMAP 마이그레이션 일괄 처리를 삭제해도 됩니다. 마이그레이션 일괄 처리를 삭제하기 전에 다음을 확인합니다.

- 모든 사용자가 사서함을 Microsoft 365 있습니다. 일괄 처리가 삭제된 후 해당 사서함의 Exchange Server 사서함으로 전송되는 메일은 Microsoft 365 않습니다.

- Microsoft 365 메일을 직접 보내기 시작한 후 사서함이 한 번 이상 동기화된 경우 이 작업을 수행하기 위해 마이그레이션 일괄 처리에 대한 마지막 동기화 시간 상자의 값이 메일이 사서함에 직접 라우팅하기 시작한 Microsoft 365 합니다.

Exchange Online PowerShell에서 "IMAPBatch1" 마이그레이션 일괄 처리를 삭제하려면 다음 명령을 실행합니다.

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

**Remove-MigrationBatch** cmdlet에 대한 자세한 내용은 [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)를 참조하세요.

#### <a name="verify-it-worked"></a>작동하는지 확인

Exchange Online PowerShell에서 다음 명령을 실행하여 "IMAPBatch1"에 대한 정보를 표시합니다.

```powershell
Get-MigrationBatch IMAPBatch1"
```

이 명령을 실행하면 상태가 **제거 중** 인 마이그레이션 일괄 처리가 반환되거나, 마이그레이션 일괄 처리를 찾을 수 없다는 오류가 반환됩니다. 이 경우 해당 일괄 처리가 삭제되었음을 확인할 수 있습니다.

**Get-MigrationBatch** cmdlet에 대한 자세한 내용은 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IMAP 마이그레이션 문제 해결사](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)
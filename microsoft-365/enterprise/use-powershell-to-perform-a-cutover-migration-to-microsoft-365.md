---
title: PowerShell을 사용하여 Microsoft 365로 컷오버 마이그레이션 수행
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: PowerShell을 사용하여 원본 전자 메일 시스템에서 원본 전자 메일 시스템으로 콘텐츠를 한 번씩 이동하는 방법을 Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210492"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>PowerShell을 사용하여 Microsoft 365로 컷오버 마이그레이션 수행

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

원본 전자 메일 시스템에서 사용자 사서함의 콘텐츠를 한 Microsoft 365 마이그레이션할 수 있습니다. 이 문서에서는 Exchange Online PowerShell을 사용하는 전자 메일 단독형 마이그레이션 작업을 살펴봅니다.

"마이그레이션으로의 컷오버 전자 메일 마이그레이션에 대해 알아야 할 [사항Microsoft 365 항목)을](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)검토하여 마이그레이션 프로세스에 대한 개요를 확인할 수 있습니다. 이 문서 내용을 충분히 이해할 수 있으면 다음을 사용하여 다른 전자 메일 시스템으로 사서함을 마이그레이션해 보세요.

> [!NOTE]
> Exchange 관리 센터를 사용하여 단독형 마이그레이션을 수행할 수도 있습니다. 자세한 [내용은 Perform a cutover migration of email to Microsoft 365.](/Exchange/mailbox-migration/cutover-migration-to-office-365)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

이 작업의 예상 완료 시간: 2-5분(마이그레이션 일괄 처리 만들기에 소요되는 시간). 마이그레이션 일괄 처리가 시작되면 마이그레이션 기간은 일괄 처리의 사서함 수, 각 사서함의 크기 및 사용 가능한 네트워크 용량에 따라 달라집니다. 사서함을 마이그레이션하는 데 걸리는 시간에 영향을 주는 다른 요인에 대한 자세한 내용은 Microsoft 365 [성능 을 참조하세요.](/Exchange/mailbox-migration/office-365-migration-best-practices)

이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인하려면 [받는 사람 사용 권한](/exchange/recipients-permissions-exchange-2013-help)의 표에 나오는 "마이그레이션" 항목을 참조하세요.

Exchange Online PowerShell cmdlet을 사용하려면 로그인한 후 cmdlet을 로컬 Windows PowerShell 세션으로 가져와야 합니다. 해당 지침은 [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](/powershell/exchange/)을 참조하세요.

## <a name="migration-steps"></a>마이그레이션 단계

### <a name="step-1-prepare-for-a-cutover-migration"></a>1단계: 단독형 마이그레이션 준비
<a name="BK_Step1"> </a>

- **조직의 허용 도메인으로 Exchange 조직에 대한 Microsoft 365 추가합니다.** 마이그레이션 서비스는 새 사서함에 대한 Microsoft Online Services 사용자 ID 및 전자 메일 주소를 만들기 위해 Microsoft 365 사서함의 SMTP 주소를 Microsoft 365 합니다. Exchange 도메인이 조직의 허용 도메인이나 기본 도메인이 아니면 Microsoft 365 실패합니다. 자세한 내용은 [도메인 확인을 참조하세요.](../admin/setup/add-domain.md)

- **온-프레미스 Exchange 서버에서 "외부에서 Outlook 사용" 구성** 전자 메일 마이그레이션 서비스에서 RPC over HTTP나 "외부에서 Outlook 사용"을 사용하여 온-프레미스 Exchange 서버에 연결합니다. Exchange 2010, Exchange 2007 및 Exchange 2003용 "외부에서 Outlook 사용"을 설정하는 방법은 다음을 참조하십시오.

  - [Exchange 2010: "외부에서 Outlook 사용" 설정](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: 외부에서 Outlook 사용 설정 방법](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: RPC over HTTP에 대한 배포 시나리오](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Exchange 2003: "외부에서 Outlook 사용" 구성 방법](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > "외부에서 Outlook 사용"은 신뢰할 수 있는 CA(인증 기관)에서 발급한 인증서를 통해 구성해야 합니다. 자체 서명된 인증서로는 구성할 수 없습니다. 자세한 내용은 ["외부에서 Outlook 사용"에 대한 SSL 구성 방법](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))을 참조하세요.

- **Outlook Anywhere를 사용하여 Exchange 조직에 연결할 수 있는지 확인** 다음 방법 중 하나를 사용하여 연결 설정을 테스트해 봅니다.

  - 회사 네트워크 외부에서 Microsoft Outlook을 사용하여 온-프레미스 Exchange 사서함에 연결합니다.

  - Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/)를 사용하여 연결 설정을 테스트합니다. 외부에서 Outlook 사용(RPC over HTTP)이나 Outlook 자동 검색 테스트를 사용합니다.

  - Exchange Online PowerShell에서 다음 명령을 실행합니다.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **온-프레미스 사용자 계정에 Exchange 조직의 사서함에 액세스하는 데 필요한 사용 권한 할당** 마이그레이션 관리자라고도 하는 사내 Exchange 조직에 연결하는 데 사용하는온-프레미스 사용자 계정에는 마이그레이션 관리자로 마이그레이션할온-프레미스 사서함에 액세스하는 데 필요한 권한이 Microsoft 365. 이 사용자 계정은 온-프레미스 조직에 대한 마이그레이션 끝점을 만드는 데 사용됩니다.

    다음 목록에는 단독형 마이그레이션을 사용하여 사서함을 마이그레이션하는 데 필요한 관리 권한이 나와 있으며, 세 개의 옵션이 제공됩니다.

  - 마이그레이션 관리자는 온-프레미스 조직의 Active Directory에 있는 **Domain Admins** 그룹의 구성원이어야 합니다.

    또는

  - 마이그레이션 관리자에게 각 온-프레미스 사서함에 대한 **모든 권한** 권한이 할당되어야 합니다.

    또는

  - 마이그레이션 관리자에게 사용자 사서함을 저장하는 온-프레미스 사서함 데이터베이스에 대한 **다음으로 받기** 권한이 할당되어야 합니다.

- **통합 메시징을 사용하지 않도록 설정** 마이그레이션하려는 온-프레미스 사서함이 UM(통합 메시징)을 사용할 수 있도록 설정된 경우 마이그레이션 전에 사서함에서 UM을 사용하지 않도록 설정해야 합니다. 마이그레이션이 완료된 후 사서함에서 UM을 사용하도록 설정할 수 있습니다.

- **보안 그룹 및 대리인** 전자 메일 마이그레이션 서비스는 마이그레이션된 그룹을 보안 그룹으로 프로비전할 수 없는 보안 그룹인지 여부를 검색할 수 Microsoft 365. Microsoft 365 테넌트에 보안 그룹을 사용하려면 먼저 Microsoft 365 테넌트에 빈 메일 사용이 가능한 보안 그룹을 프로비전해야 합니다. 또한 이 마이그레이션 방법을 사용하는 경우에는 사서함, 메일 사용자, 메일 연락처 및 메일 사용 가능 그룹만 이동됩니다. Microsoft 365 마이그레이션되지 않은 사용자와 같은 다른 Active Directory 개체가 마이그레이션되는 개체에 관리자 또는 대리인으로 할당된 경우 마이그레이션하기 전에 해당 개체를 개체에서 제거해야 합니다.

### <a name="step-2-create-a-migration-endpoint"></a>2단계: 마이그레이션 끝점 만들기
<a name="BK_Step2"> </a>

전자 메일을 마이그레이션하려면 Microsoft 365 전자 메일 시스템에 연결하고 통신해야 합니다. 이 작업을 수행하기 위해 Microsoft 365 끝점을 사용하게 됩니다. 단독형 마이그레이션을 위한 "외부에서 Outlook 사용" 마이그레이션 끝점을 만들려면 먼저 [Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)합니다.

전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](/powershell/exchange/)을 참조하세요.

Exchange Online PowerShell에서 다음 명령을 실행합니다.

```powershell
$Credentials = Get-Credential
```

이 예에서는 [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet을 사용하여 온-프레미스 Exchange 서버에 대한 연결 설정을 가져오고 테스트한 다음 해당 연결 설정을 사용하여 "CutoverEndpoint"라는 마이그레이션 끝점을 만듭니다.

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> **New-MigrationEndpoint** cmdlet을 사용하여 **-TargetDatabase** 옵션을 통해 서비스에서 사용할 데이터베이스를 지정할 수 있습니다. 그렇지 않으면 데이터베이스는 관리 사서함이 있는 AD FS(Active Directory Federation Services) 2.0 사이트에서 임의로 할당됩니다.

#### <a name="verify-it-worked"></a>작동하는지 확인

Exchange Online PowerShell에서 다음 명령을 실행하여 "CutoverEndpoint" 마이그레이션 끝점에 대한 정보를 표시합니다.

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>3단계: 단독형 마이그레이션 일괄 처리 만들기
<a name="BK_Step3"> </a>

Exchange Online PowerShell에서 **New-MigrationBatch** cmdlet을 사용하여 단독형 마이그레이션을 위한 마이그레이션 일괄 처리를 만들 수 있습니다. _AutoStart_ 매개 변수를 포함하면 마이그레이션 일괄 처리를 만들고 자동으로 시작할 수 있습니다. 또는 마이그레이션 일괄 처리를 만들고 **Start-MigrationBatch** cmdlet을 사용하여 나중에 마이그레이션을 수동으로 시작할 수 있습니다. 이 예에서는 "CutoverBatch"라는 마이그레이션 일괄 처리를 만든 다음 이전 예에서 만든 마이그레이션 끝점을 사용합니다.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

또한 이 예에서는 "CutoverBatch"라는 마이그레이션 일괄 처리를 만든 다음 이전 예에서 만든 마이그레이션 끝점을 사용합니다.  _AutoStart_ 매개 변수가 포함되지 않으므로 마이그레이션 일괄 처리가 마이그레이션 대시보드나 **Start-MigrationBatch** cmdlet을 사용하여 수동으로 시작되어야 합니다. 앞서 설명했듯이 단독형 마이그레이션 일괄 처리는 한 번에 하나만 실행됩니다.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>작동하는지 확인

단독형 마이그레이션을 위한 마이그레이션 일괄 처리를 성공적으로 만들었는지 확인하려면 Exchange Online PowerShell에서 다음 명령을 실행하여 새 마이그레이션 일괄 처리에 대한 정보를 표시합니다.

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>4단계: 단독형 마이그레이션 일괄 처리 시작
<a name="BK_Step4"> </a>

Exchange Online PowerShell에서 마이그레이션 일괄 처리를 시작하려면 다음 명령을 실행합니다. 그러면 "CutoverBatch"라는 마이그레이션 일괄 처리가 만들어집니다.

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>작동하는지 확인

마이그레이션 일괄 처리가 정상적으로 시작된 경우 마이그레이션 대시보드에서 해당 상태가 동기화 중으로 지정됩니다. Exchange Online PowerShell을 사용하여 마이그레이션 일괄 처리를 성공적으로 시작했는지 확인하려면 다음 명령을 실행합니다.

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>5단계: 전자 메일을 메일로 Microsoft 365
<a name="BK_Step5"> </a>

전자 메일 시스템은 MX 레코드라는 DNS 레코드를 사용하여 전자 메일을 배달할 위치를 확인합니다. 전자 메일 마이그레이션 프로세스 중에는 MX 레코드가 원본 전자 메일 시스템을 가리켰습니다. 이제 전자 메일 마이그레이션을 Microsoft 365 이제 MX 레코드를 Microsoft 365. 이렇게 하면 전자 메일이 사용자 사서함으로 Microsoft 365 수 있습니다. MX 레코드를 이동하여 준비가 되었을 때 이전 전자 메일 시스템을 해제할 수도 있습니다.

DNS 공급자가 많이 있으므로 MX 레코드를 변경하기 위한 특정 지침이 제공됩니다. DNS 공급자가 포함되어 있지 않은 경우 또는 일반적인 지침을 확인하려는 경우 일반적인 [MX](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) 레코드 지침도 제공됩니다.

고객 및 파트너의 전자 메일 시스템에서 변경된 MX 레코드를 인식하는 데는 최대 72시간이 걸릴 수 있습니다. 다음 작업을 계속 진행하기 전에 적어도 72시간 동안 기다립니다. [6단계: 단독형 마이그레이션 일괄 처리 삭제](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).

### <a name="step-6-delete-the-cutover-migration-batch"></a>6단계: 단독형 마이그레이션 일괄 처리 삭제
<a name="Bk_step6"> </a>

MX 레코드를 변경하고 모든 전자 메일이 Microsoft 365 사서함으로 라우팅되고 있는지 확인한 후 사용자에게 메일이 전송될 것 Microsoft 365. 그런 후에는 단독형 마이그레이션 일괄 처리를 삭제해도 됩니다. 마이그레이션 일괄 처리를 삭제하기 전에 다음을 확인합니다.

- 모든 사용자가 사서함을 Microsoft 365 있습니다. 일괄 처리가 삭제된 후 해당 사서함의 Exchange Server 사서함으로 전송되는 메일은 Microsoft 365 않습니다.

- Microsoft 365 메일을 직접 보내기 시작한 후 사서함이 한 번 이상 동기화된 경우 이 작업을 수행하기 위해 마이그레이션 일괄 처리에 대한 마지막 동기화 시간 상자의 값이 메일이 사서함에 직접 라우팅하기 시작한 Microsoft 365 합니다.

Exchange Online PowerShell에서 "CutoverBatch" 마이그레이션 일괄 처리를 삭제하려면 다음 명령을 실행합니다.

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>섹션 7: 사용자 라이선스 할당
<a name="BK_Step7"> </a>

 **라이선스를 Microsoft 365 마이그레이션된 계정에 대한 사용자 계정을 활성화합니다.** 라이선스를 할당하지 않은 경우 30일 유예 기간이 끝나면 사서함을 사용할 수 없습니다. 새 라이선스에 라이선스를 할당 Microsoft 365 관리 센터 라이선스 할당 또는 [할당을 해지를 참조합니다.](../admin/manage/assign-licenses-to-users.md)

### <a name="step-8-complete-post-migration-tasks"></a>8단계: 마이그레이션 후 작업 완료
<a name="BK_Step8"> </a>

- **사용자가 자신의 사서함으로 쉽게 이동할 수 있도록 자동 검색 DNS 레코드를 만듭니다.** 모든 Microsoft 365 사서함을 마이그레이션한 후 사용자가 Microsoft 365 및 모바일 클라이언트를 사용하여 새 Microsoft 365 사서함에 쉽게 연결할 수 있도록 Microsoft 365 조직에 대한 자동 검색 DNS 레코드를 구성할 Outlook 있습니다. 이 새 자동 Microsoft 365 DNS 레코드는 조직에서 사용하는 네임스페이스와 동일한 네임스페이스를 Microsoft 365 합니다. 예를 들어 클라우드 기반 네임스페이스가 cloud.contoso.com인 경우 만들어야 할 자동 검색 DNS 레코드는 autodiscover.cloud.contoso.com입니다.

    사용자 Exchange Server 보관하는 경우 자동 검색 DNS CNAME 레코드가 마이그레이션 후 내부 및 외부 DNS의 Microsoft 365 둘 다를 설정해야 Outlook 클라이언트가 올바른 사서함에 연결할 수 있습니다.

    > [!NOTE]
    >  또한 Exchange 2007, Exchange 2010 및 Exchange 2013에서  `Set-ClientAccessServer AutodiscoverInternalConnectionURI`를  `Null`로 설정해야 합니다.

    Microsoft 365 CNAME 레코드를 사용하여 클라이언트 및 모바일 클라이언트에 Outlook 서비스를 구현합니다. Autodiscover CNAME 레코드에는 다음과 같은 정보가 포함되어야 합니다.

  - **별칭:** autodiscover

  - **대상:** autodiscover.outlook.com

    자세한 내용은 [도메인에 연결하기 위해 DNS 레코드 추가를 참조하세요.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

- **온-프레미스 Exchange 서버를 해제합니다.** 모든 전자 메일이 Microsoft 365 사서함으로 직접 라우팅되고 있는 것을 확인한 후 더 이상 사내 전자 메일 조직을 유지 관리할 필요가 없는 경우 또는 SSO(Single Sign-On) 솔루션 구현을 계획하지 않은 경우 서버에서 Exchange 제거하고 Exchange 조직을 제거할 수 있습니다.

    자세한 내용은 다음 항목을 참조하십시오.

  - [Exchange 2010 수정 또는 제거](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Exchange 2007 조직 제거 방법](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Exchange Server 2003 제거 방법](/previous-versions/tn-archive/bb125110(v=exchg.65))
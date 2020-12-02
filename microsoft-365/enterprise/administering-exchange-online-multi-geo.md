---
title: Multi-Geo 환경에서 Exchange Online 사서함 관리
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: PowerShell을 사용 하 여 Microsoft 365 환경에서 Exchange Online 다중 지역 설정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552010"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Multi-Geo 환경에서 Exchange Online 사서함 관리

Microsoft 365 환경에서 다중 지역 속성을 보고 구성 하려면 Exchange Online PowerShell이 필요 합니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

사용자 개체의 **PreferredDataLocation** 속성을 보려면 v1.x에서 [Microsoft Azure Active Directory PowerShell 모듈](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 이상이 필요합니다. AAD Connect를 통해 AAD에 동기화된 사용자 개체의 **PreferredDataLocation** 값은 AAD PowerShell을 통해 직접 수정할 수 없습니다. 클라우드 전용 사용자 개체는 AAD PowerShell을 통해 수정할 수 있습니다. Azure AD PowerShell에 연결하려면 [PowerShell에 연결](connect-to-microsoft-365-powershell.md)을 참조하세요.

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Exchange Online PowerShell을 사용하여 지리적 위치에 직접 연결

일반적으로 Exchange Online PowerShell은 중앙 지리적 위치에 연결합니다. 그러나 위성 지리적 위치에 직접 연결할 수도 있습니다. 특정 위치의 사용자만 관리하는 경우 성능 개선을 위해 해당 위성 위치에 직접 연결할 것을 권장합니다.

EXO V2 모듈을 설치하고 사용하는 데 필요한 사항에 대한 자세한 내용은 [EXO V2 모듈 설치 및 유지 관리](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)를 참조하세요.

Exchange Online PowerShell을 특정 지리적 위치에 연결 하려면 *Connectionuri* 매개 변수가 일반 연결 지침과 다릅니다. 나머지 명령과 값은 동일합니다.

특히 `?email=<emailaddress>` _connectionuri_ 값의 끝에 값을 추가 해야 합니다. `<emailaddress>` 는 대상 지리적 위치에 있는 **모든** 사서함의 전자 메일 주소입니다. 해당 사서함에 대 한 사용 권한 또는 자격 증명과의 관계는 요인이 아닙니다. 전자 메일 주소는 Exchange Online PowerShell에 연결 하는 것을 간단 하 게 알려 줍니다.

Microsoft 365 또는 Microsoft 365 GCC 고객은 일반적으로 _Connectionuri_ 매개 변수를 사용 하 여 Exchange Online PowerShell에 연결할 필요가 없습니다. 그러나 특정 지리적 위치에 연결 하려면 값에 _Connectionuri_ 매개 변수를 사용 해야 `?email=<emailaddress>` 합니다.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Exchange Online PowerShell에서 지리적 위치에 연결

다음 연결 지침은 MFA (multi-factor authentication)에 대 한 구성 된 계정에 대해 작동 합니다.

1. Windows PowerShell 창에서 다음 명령을 실행하여 EXO V2 모듈을 로드합니다.

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. 다음 예제에서는 admin@contoso.onmicrosoft.com이 관리자 계정이 고, 대상 지리적 위치는 사서함 olga@contoso.onmicrosoft.com가 상주 합니다.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. 표시 되는 프롬프트에 admin@contoso.onmicrosoft.com에 대 한 암호를 입력 합니다. 계정이 MFA에 대해 구성 된 경우 보안 코드도 입력 해야 합니다.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Exchange Online 조직에서 구성된 사용 가능한 지리적 위치 보기

Microsoft 365 Multi-Geo에서 구성된 지리적 위치 목록을 보려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Exchange Online 조직의 중앙 지리적 위치 보기

테넌트의 중앙 지리적 위치를 보려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>사서함의 지리적 위치 찾기

Exchange Online PowerShell의 **Get-Mailbox** cmdlet은 사서함에 다음과 같은 Multi-Geo 관련 속성을 표시합니다.

- **Database**: 데이터베이스 이름의 첫 세 글자는 지역 코드에 해당하며, 사서함의 현재 위치를 알려줍니다. 온라인 보관 사서함의 경우 **ArchiveDatabase** 속성을 사용해야 합니다.

- **MailboxRegion**: 관리자가 설정한 지리적 위치 코드를 지정합니다(Azure AD의 **PreferredDataLocation** 에서 동기화됨).

- **MailboxRegionLastUpdateTime**: MailboxRegion이 마지막으로 업데이트(자동 또는 수동으로)된 시간을 나타냅니다.

사서함의 속성을 보려면 다음 구문을 사용합니다.

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

예를 들어 chris@contoso.onmicrosoft.com의 사서함 위치 정보를 보려면 다음 명령을 실행합니다.

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

이 명령의 출력은 다음과 같습니다.

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> 데이터베이스 이름에 있는 지리적 위치 코드가 **MailboxRegion** 값과 일치 하지 않으면 사서함이 자동으로 재배치 큐에 배치 되 고 **MailboxRegion** 값으로 지정 된 지리적 위치로 이동 됩니다 (이러한 속성 값 간에 불일치를 검색 하는 경우).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>기존 클라우드 전용 사서함을 특정 지리적 위치로 이동

클라우드 전용 사용자는 AAD Connect로 테넌트에 동기화되지 않은 사용자입니다. 이 사용자는 Azure AD에서 직접 만들어졌습니다. Windows PowerShell용 Azure AD 모듈에서 **Get-MsolUser** 및 **Set-MsolUser** cmdlet을 사용하여 클라우드 전용 사용자의 사서함을 저장할 지리적 위치를 보거나 지정할 수 있습니다.

사용자의 **PreferredDataLocation** 값을 보려면 Azure AD PowerShell에서 이 구문을 사용합니다.

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

예를 들어 사용자 michelle@contoso.onmicrosoft.com의 **PreferredDataLocation** 값을 보려면 다음 명령을 실행합니다.

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

클라우드 전용 사용자 개체의 **PreferredDataLocation** 값을 수정하려면 Azure AD PowerShell에서 다음 구문을 사용합니다.

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

예를 들어 사용자 michelle@contoso.onmicrosoft.com의 유럽 연합(EUR) 지역에 **PreferredDataLocation** 값을 설정하려면 다음 명령을 실행합니다.

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - 앞에서 설명한 것 처럼, 온-프레미스 Active Directory에서 동기화 된 사용자 개체에는이 절차를 사용할 수 없습니다. Active Directory에서 **PreferredDataLocation** 값을 변경하고 AAD Connect를 사용하여 동기화해야 합니다. 자세한 내용은 [Azure Active Directory Connect 동기화: Microsoft 365 리소스의 기본 데이터 위치 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)을 참조하세요.
>
> - 새로운 지리적 위치로 사서함 위치를 변경하는 데 걸리는 시간은 몇 가지 요인에 따라 달라집니다.
>
>   - 사서함 크기 및 유형
>   - 이동 중인 사서함 수
>   - 이동 리소스의 가용성

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>비활성 사서함을 특정 지역으로 이동

규정 준수를 위해 보존 되는 비활성 사서함 (예: 소송 보존 사서함)은 해당 **PreferredDataLocation** 값을 변경 하 여 이동할 수 없습니다. 비활성 사서함을 다른 지역으로 이동 하려면 다음 단계를 수행 합니다.

1. 비활성 사서함을 복구 합니다. 자세한 내용은 [비활성 사서함 복구](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)를 참조 하십시오.

2. \<MailboxIdentity\>사서함의 이름, 별칭, 계정 또는 전자 메일 주소로 교체 하 고 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)에서 다음 명령을 실행 하 여 관리 되는 폴더 도우미가 복구 된 사서함을 처리 하지 않도록 합니다.

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. **Exchange Online 계획 2** 라이선스를 복구 된 사서함에 할당 합니다. 이 단계는 사서함을 소송 보존 상태로 다시 설정 하는 데 필요 합니다. 자세한 내용은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.

4. 이전 섹션에 설명 된 대로 사서함에서 **PreferredDataLocation** 값을 구성 합니다.

5. 사서함이 새 지리적 위치로 이동 되었는지 확인 한 후에는 복구 된 사서함을 소송 보존 상태로 다시 설정 합니다. 자세한 내용은 [사서함에 소송 보존](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)을 참조 하십시오.

6. 소송 보존이 적용 되었는지 확인 한 후에는 관리 되는 폴더 도우미가 \<MailboxIdentity\> 사서함의 이름, 별칭, 계정 또는 전자 메일 주소로 교체 하 고 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)에서 다음 명령을 실행 하 여 사서함을 다시 처리할 수 있도록 합니다.

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. 사서함과 연결 된 사용자 계정을 제거 하 여 사서함을 다시 비활성 상태로 만듭니다. 자세한 내용은 [조직에서 사용자 삭제](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)를 참조 하십시오. 이 단계에서는 다른 용도로도 Exchange Online 계획 2 라이선스를 릴리스 합니다.

**참고**: 비활성 사서함을 다른 지리적 위치로 이동 하는 경우에는 콘텐츠 검색 결과 또는 이전 지리적 위치에서 사서함을 검색 하는 기능에 영향을 줄 수 있습니다. 자세한 내용은 [다중 지리적 환경에서 콘텐츠 검색 및 내보내기](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)를 참조 하세요.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>특정 지리적 위치에 새 클라우드 사서함 만들기

특정 지리적 위치에 새 사서함을 만들려면 다음 단계 중 하나를 수행해야 합니다.

- Exchange Online에서 사서함을 만들기 *전에* 이전 [클라우드 전용 사서함을 특정 지리적 위치까지 이동](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) 섹션에 설명 된 대로 **PreferredDataLocation** 값을 구성 합니다. 예를 들어 라이선스를 할당 하기 전에 사용자에 대해 **PreferredDataLocation** 값을 구성 합니다.

- **PreferredDataLocation** 값을 설정함과 동시에 라이선스를 할당합니다.

특정 지리적 위치에 새로운 클라우드 전용 라이선스 사용자 (AAD Connect 동기화가 아닌)를 만들려면 Azure AD PowerShell에서 다음 구문을 사용하십시오.

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

이 예제에서는 다음 값을 사용하여 Elizabeth Brunner를 위한 새 사용자 계정을 만듭니다.

- 사용자 계정 이름: ebrunner@contoso.onmicrosoft.com
- 이름: Elizabeth
- 성: Brunner
- 표시할 이름: Elizabeth Brunner
- 비밀번호: 임의로 생성되고 명령의 결과에 표시됨(*비밀번호* 매개 변수를 사용하지 않고 있기 때문)
- 라이선스: `contoso:ENTERPRISEPREMIUM` (E5)
- 위치: 오스트레일리아(AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

새 사용자 계정을 만들고 Azure AD PowerShell에서 LicenseAssignment 값을 찾는 방법에 대한 자세한 내용은 [PowerShell을 사용하여 사용자 계정 만들기](create-user-accounts-with-microsoft-365-powershell.md) 및 [PowerShell을 사용하여 라이선스 및 서비스 보기](view-licenses-and-services-with-microsoft-365-powershell.md)를 참조하세요.

> [!NOTE]
> Exchange Online PowerShell로 사서함을 사용하도록 설정하고 해당 사서함을 **PreferredDataLocation** 에 지정된 지리적 위치에 직접 만들려면 **Enable-Mailbox** 또는 **New-Mailbox** 등의 Exchange Online cmdlet을 클라우드 서비스에 직접 사용해야 합니다. 온 - 프레미스 Exchange PowerShell에서 **Enable-RemoteMailbox** cmdlet를 사용하면 사서함이 중앙 지리적 위치에 만들어집니다.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>특정 지리적 위치에 기존 온-프레미스 사서함 등록

표준 등록 도구와 프로세스를 사용하여 사서함을 온-프레미스 Exchange 조직에서 Exchange Online으로 마이그레이션할 수 있습니다([EAC의 마이그레이션 대시보드](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), Exchange Online PowerShell의 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet 포함).

첫 번째 단계는 등록될 사서함마다 사용자 개체가 있는지 확인하고 Azure AD에 올바른 **PreferredDataLocation** 값이 구성되었는지 확인하는 일입니다. 등록 도구는 **PreferredDataLocation** 값을 고려하고 사서함을 지정된 지리적 위치에 직접 마이그레이션합니다.

또는 Exchange Online PowerShell의 [새로 만들기 MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet을 사용하는 다음 단계를 통해 사서함을 특정 지리적 위치에 직접 등록할 수 있습니다.

1. 등록될 사서함마다 사용자 개체가 있고 **PreferredDataLocation** 이 Azure AD에서 원하는 값으로 설정되어 있는지 확인합니다. **PreferredDataLocation** 값은 Exchange Online에서 해당 메일 사용자 개체의 **MailboxRegion** 특성에 동기화됩니다.

2. 이 항목 앞부분의 연결 지침을 사용하여 특정 위성 지리적 위치에 직접 연결하십시오.

3. Exchange Online PowerShell에서 다음 명령을 실행하여, 변수에서 사서함 마이그레이션을 수행하는 데 사용되는 온-프레미스 관리자 자격 증명을 저장합니다.

   ```powershell
   $RC = Get-Credential
   ```

4. Exchange Online PowerShell에서 다음 예제와 비슷한 새로운 **New-MoveRequest** 를 만듭니다.

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. 온-프레미스 Exchange에서 현재 연결된 위성 지리적 위치로 마이그레이션해야 할 모든 사서함에 4단계를 반복합니다.

6. 다른 위성 지리적 위치에 추가 사서함을 마이그레이션해야 할 경우 각각의 특정 위치에 2단계에서 4단계까지를 반복합니다.

## <a name="multi-geo-reporting"></a>Multi-Geo 보고

Microsoft 365 관리자 센터의 **Multi-Geo 사용 보고서** 는 지리적 위치별 사용자 수를 표시합니다. 보고서는 이번 달의 사용자 분포를 표시하고 지난 6개월 동안의 기록 데이터를 제공합니다.

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)

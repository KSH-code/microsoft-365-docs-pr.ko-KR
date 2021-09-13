---
title: 고객 키 관리
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키를 설정한 후 AKV 키를 복원하고 사용 권한을 관리하고 데이터 암호화 정책을 만들고 할당하여 키 관리 방법을 배워야 합니다.
ms.openlocfilehash: 7fc985aaaf0cf0222a6cd02063207b2b1709ac25
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216885"
---
# <a name="manage-customer-key"></a>고객 키 관리

사용자에 대해 고객 키를 설정한 Office 365 하나 이상의 DEP(데이터 암호화 정책)를 만들고 할당해야 합니다. DEP를 할당한 후 이 문서에 설명된 바와 같이 키를 관리할 수 있습니다. 관련 항목에서 고객 키에 대해 자세히 알아보습니다.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>모든 테넌트 사용자에 대해 여러 워크로드에 사용할 DEP 만들기

시작하기 전에 Customer를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 내용은 고객 키 [설정 을 참조하세요.](customer-key-set-up.md) DEP를 만들하려면 설치 중에 획득한 키 자격 증명 모음 UR이 필요합니다. 자세한 내용은 [각 Azure Key Vault 키에 대한 URI 얻기를 참조하세요.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

다중 워크로드 DEP를 만들 수 있도록 다음 단계를 수행합니다.
  
1. 로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.

2. DEP를 만들 수 있는 New-M365DataAtRestEncryptionPolicy cmdlet을 사용 합니다.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   여기서,

   - *PolicyName은* 정책에 사용할 이름입니다. 이름에는 공백을 포함할 수 없습니다. 예를 들어 Contoso_Global.

   - *KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다. 예를 들면 <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>와 같습니다.

   - *KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다. 예를 들면 <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>와 같습니다. 두 URIS를 콤보와 공백으로 구분합니다.

   - *정책 설명은* 정책에 대한 정보를 기억하는 데 도움이 되는 정책에 대한 사용자에게 친숙한 설명입니다. 설명에 공백을 포함할 수 있습니다. 예를 들어 "테넌트의 모든 사용자에 대한 여러 워크로드에 대한 루트 정책"을 예로 들 수 있습니다.

예제:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>다중 작업 정책 할당

cmdlet을 사용하여 DEP를 Set-M365DataAtRestEncryptionPolicyAssignment. 정책을 할당한 Microsoft 365 DEP에 식별된 키로 데이터를 암호화합니다.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 여기서 *PolicyName은* 정책의 이름입니다. 예를 들어 Contoso_Global.

예제:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>사서함에 사용할 DEP Exchange Online 만들기

시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 내용은 고객 키 [설정 을 참조하세요.](customer-key-set-up.md) 원격으로 원격으로 사용자와 연결하여 Exchange Online 단계를 Windows PowerShell.

DEP는 Azure Key Vault에 저장된 키 집합과 연결됩니다. 사서함에 DEP를 할당할 Microsoft 365. Microsoft 365 정책에 식별된 키를 사용하여 사서함을 암호화합니다. DEP를 만들하려면 설치 중에 획득한 키 자격 증명 모음 UR이 필요합니다. 자세한 내용은 [각 Azure Key Vault 키에 대한 URI 얻기를 참조하세요.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

기억하세요! DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다. 두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.

사서함에 사용할 DEP를 만들 경우 다음 단계를 수행합니다.
  
1. 로컬 컴퓨터에서 전역 관리자 또는 조직에서 전역 관리자 또는 Exchange Online 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerSh Windows PowerShell ell에](/powershell/exchange/connect-to-exchange-online-powershell) 연결합니다.

2. DEP를 만들 New-DataEncryptionPolicy 명령을 입력하여 New-DataEncryptionPolicy cmdlet을 사용 합니다.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   여기서,

   - *PolicyName은* 정책에 사용할 이름입니다. 이름에는 공백을 포함할 수 없습니다. 예를 들어 USA_mailboxes.

   - *정책 설명은* 정책에 대한 정보를 기억하는 데 도움이 되는 정책에 대한 사용자에게 친숙한 설명입니다. 설명에 공백을 포함할 수 있습니다. 예를 들어 "미국 사서함과 해당 지역의 루트 키"를 예로 들 수 있습니다.

   - *KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다. 예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.

   - *KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다. 예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다. 두 URIS를 콤보와 공백으로 구분합니다.

   예제:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

구문과 매개 변수에 대한 자세한 내용은 [New-DataEncryptionPolicy를 참조하십시오.](/powershell/module/exchange/new-data-encryptionpolicy)

### <a name="assign-a-dep-to-a-mailbox"></a>사서함에 DEP 할당

사용자 지정 cmdlet을 사용하여 사서함에 DEP를 Set-Mailbox 할당합니다. 정책을 할당하면 Microsoft 365 DEP에 식별된 키로 사서함을 암호화할 수 있습니다.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

여기서 *MailboxIdParameter는* 사용자 사서함을 지정합니다. cmdlet에 대한 Set-Mailbox 자세한 내용은 [Set-Mailbox를 참조하십시오.](/powershell/module/exchange/set-mailbox)

하이브리드 환경에서는 시스템 테넌트에 동기화되는 사내 사서함 데이터에 DEP를 할당할 Exchange Online 있습니다. 이 동기화된 사서함 데이터에 DEP를 할당하기 위해 이 cmdlet을 Set-MailUser 합니다. 하이브리드 환경의 사서함 데이터에 대한 자세한 내용은 하이브리드 최신 인증을 사용하는 iOS 및 android용 Outlook 사용하는 [Outlook 사서함을 참조하세요.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

여기서 *MailUserIdParameter는* 메일 사용자(메일 사용이 가능한 사용자)를 지정합니다. cmdlet에 대한 Set-MailUser 자세한 내용은 [Set-MailUser 를 참조하십시오.](/powershell/module/exchange/set-mailuser)

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams DEP 만들기

시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 내용은 고객 키 [설정 을 참조하세요.](customer-key-set-up.md)
  
SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키를 설정하려면 SharePoint Online에 원격으로 연결하여 이러한 단계를 Windows PowerShell.
  
DEP를 Azure Key Vault에 저장된 키 집합과 연결합니다. 지역이라고도 하는 한 지리적 위치에 있는 모든 데이터에 DEP를 적용합니다. Office 365 Multi-Geo 기능을 사용하는 경우 지역마다 다른 키를 사용할 수 있는 기능을 사용하여 지역당 DEP를 하나씩 만들 수 있습니다. Multi-Geo를 사용하지 않는 경우 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 Teams 사용할 DEP를 만들 수 있습니다. Microsoft 365 DEP에 식별된 키를 사용하여 그 지리적으로 데이터를 암호화합니다. DEP를 만들하려면 설치 중에 획득한 키 자격 증명 모음 UR이 필요합니다. 자세한 내용은 [각 Azure Key Vault 키에 대한 URI 얻기를 참조하세요.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)
  
기억하세요! DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다. 두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.
  
DEP를 만들 수 있도록 원격으로 SharePoint Online에 연결해야 Windows PowerShell.
  
1. 로컬 컴퓨터에서 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 커넥트 [PowerShell을](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)SharePoint 합니다.

2. Microsoft Office SharePoint Online 관리 셸에서 다음과 Register-SPODataEncryptionPolicy cmdlet을 실행합니다.

   ```powershell
   Register-SPODataEncryptionPolicy <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   예제:
  
   ```powershell
   Register-SPODataEncryptionPolicy  https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   DEP를 등록하면 지리적 데이터에 대한 암호화가 시작됩니다. 암호화에는 시간이 걸릴 수 있습니다. 이 매개 변수를 사용하는 데 대한 자세한 내용은 [Register-SPODataEncryptionPolicy를 참조하세요.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>사서함에 대해 만든 DEP Exchange Online 보기

사서함에 대해 만든 모든 DEP의 목록을 보기 위해 powerShell cmdlet을 Get-DataEncryptionPolicy.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. 조직의 모든 DEP를 반환하기 위해 매개 변수 없이 Get-DataEncryptionPolicy cmdlet을 실행합니다.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   cmdlet에 대한 자세한 Get-DataEncryptionPolicy [Get-DataEncryptionPolicy를 참조하세요.](/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>클라우드로 사서함을 마이그레이션하기 전에 DEP 할당

DEP를 할당할 때 Microsoft 365 할당된 DEP를 사용하여 사서함의 내용을 암호화합니다. 이 프로세스는 사서함을 마이그레이션하고 DEP를 할당한 다음 암호화가 진행될 때까지 기다리는 것보다 더 효율적이며, 이 작업에는 몇 시간 또는 며칠이 걸릴 수 있습니다.

사서함으로 마이그레이션하기 전에 사서함에 DEP를 할당하려면 Office 365 PowerShell에서 Set-MailUser cmdlet을 Exchange Online 실행합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. cmdlet을 Set-MailUser 실행합니다.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   여기서 *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 *DataEncryptionPolicyIdParameter는* DEP의 ID입니다. cmdlet에 대한 Set-MailUser 자세한 내용은 [Set-MailUser 를 참조하십시오.](/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>사서함에 할당된 DEP 확인

사서함에 할당된 DEP를 확인하기 위해 Get-MailboxStatistics cmdlet을 사용 합니다. 이 cmdlet은 GUID(고유 식별자)를 반환합니다.
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   여기서 *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 DataEncryptionPolicyID는 DEP의 GUID를 반환합니다. 이 cmdlet에 대한 자세한 Get-MailboxStatistics [Get-MailboxStatistics 를 참조하세요.](/powershell/module/exchange/get-mailboxstatistics)
  
2. Get-DataEncryptionPolicy cmdlet을 실행하여 사서함이 할당된 DEP의 이름을 찾을 수 있습니다.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   여기서 *GUID는* 이전 단계에서 Get-MailboxStatistics cmdlet에서 반환된 GUID입니다.

## <a name="verify-that-customer-key-has-finished-encryption"></a>고객 키의 암호화가 완료되어 있는지 확인

고객 키를 롤링하거나 새 DEP를 할당하거나 사서함을 마이그레이션한 경우 이 섹션의 단계를 사용하여 암호화가 완료되도록 합니다.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>사서함의 암호화가 Exchange Online 확인

사서함 암호화에는 시간이 걸릴 수 있습니다. 또한 서비스가 사서함을 암호화하려면 먼저 사서함을 데이터베이스에서 다른 데이터베이스로 완전히 이동해야 합니다.
  
Get-MailboxStatistics cmdlet을 사용하여 사서함이 암호화되어 있는지 확인할 수 있습니다.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted 속성은 사서함이 암호화된 경우 **true** 값을 반환하고 사서함이 암호화되지 않은 경우 **false** 값을 반환합니다. 사서함 이동을 완료하는 시간은 처음으로 DEP를 할당하는 사서함 수와 사서함의 크기에 따라 달라 니다. DEP를 할당한 후 1주일 후에도 사서함이 암호화되지 않은 경우 Microsoft에 문의합니다.

로컬 New-MoveRequest 사서함 이동에는 더 이상 이 cmdlet을 사용할 수 없습니다. 추가 [정보는 이 공지 사항을](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 참조하세요.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 암호화 완료 확인

다음과 같이 cmdlet을 실행하여 Get-SPODataEncryptionPolicy 상태를 검사합니다.

```PowerShell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
```

이 cmdlet의 출력에는 다음이 포함됩니다.
  
- 기본 키의 URI입니다.

- 보조 키의 URI입니다.

- 지리적 암호화 상태입니다. 가능한 상태는 다음과 같습니다.

  - **등록이 등록되지 않은 경우:** 고객 키 암호화가 아직 적용되지 않았습니다.

  - **등록:** 고객 키 암호화가 적용되고 파일이 암호화 중입니다. 지역 키가 등록되는 경우 암호화 진행률을 모니터링할 수 있도록 지리적 사이트의 완료율에 대한 정보도 표시됩니다.

  - **등록:** 고객 키 암호화가 적용되고 모든 사이트의 모든 파일이 암호화되었습니다.

  - **롤링:** 키 롤이 진행 중입니다. 지역 키가 롤링되는 경우 진행 상황을 모니터링할 수 있도록 키 롤 작업을 완료한 사이트의 비율에 대한 정보도 표시됩니다.

- 또한 온보드 사이트의 백분율도 출력합니다.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>여러 워크로드에서 사용하는 DEP에 대한 세부 정보 확인

여러 워크로드에서 사용하기 위해 만든 모든 DEP에 대한 세부 정보를 얻습니다. 다음 단계를 완료합니다.

1. 로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.

   - 조직의 모든 다중 작업 DEP 목록을 반환하기 위해 이 명령을 실행합니다.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - 특정 DEP에 대한 세부 정보를 반환하기 위해 이 명령을 실행합니다. 이 예에서는 "Contoso_Global"라는 DEP에 대한 자세한 정보를 반환합니다.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>다중 작업 DEP 할당 정보 얻기

테넌트에 현재 할당된 DEP를 확인하기 위해 다음 단계를 수행합니다. 

1. 로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.

2. 이 명령을 입력합니다.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>다중 작업 DEP를 사용하지 않도록 설정

다중 작업 DEP를 사용하지 않도록 설정하기 전에 테넌트의 워크로드에서 DEP를 배정 해제합니다. 여러 워크로드에 사용되는 DEP를 사용하지 않도록 설정하기 위해 다음 단계를 완료합니다.

1. 로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.

2. cmdlet을 Set-M365DataAtRestEncryptionPolicy 실행합니다.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

여기서 *PolicyName은* 정책의 이름 또는 고유 ID입니다. 예를 들어 Contoso_Global.

예제:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault 키 복원

복원을 수행하기 전에 소프트 삭제에서 제공하는 복구 기능을 사용 합니다. 고객 키와 함께 사용되는 모든 키는 소프트 삭제를 사용하도록 설정해야 합니다. 소프트 삭제는 재활용 쓰레기 수거란처럼 사용하며 복원할 필요 없이 최대 90일 동안 복구할 수 있습니다. 복원은 키 또는 키 자격 증명 모음이 분실된 경우와 같은 극단적인 상황이나 비정상적인 상황에서만 필요합니다. 고객 키와 함께 사용할 키를 복원해야 하는 경우 Azure PowerShell cmdlet을 Restore-AzureKeyVaultKey 실행합니다.
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

예시:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

키 자격 증명 모음에 이름이 같은 키가 이미 포함되어 있는 경우 복원 작업이 실패합니다. Restore-AzKeyVaultKey 키 이름을 포함하여 키의 모든 메타데이터 및 키 버전을 복원합니다.
  
## <a name="manage-key-vault-permissions"></a>주요 자격 증명 모음 사용 권한 관리

필요한 경우 주요 자격 증명 모음 권한을 보고 제거할 수 있는 여러 cmdlet을 사용할 수 있습니다. 예를 들어 직원이 팀을 떠날 때 사용 권한을 제거해야 할 수 있습니다. 이러한 각 작업에 대해 이러한 작업을 Azure PowerShell. 자세한 내용은 Azure PowerShell [개요를 Azure PowerShell.](/powershell/azure/)

키 자격 증명 모음 사용 권한을 보기 위해 Get-AzKeyVault 실행합니다.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

예시:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

관리자의 사용 권한을 제거하려면 다음 Remove-AzKeyVaultAccessPolicy 실행합니다.
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

예시:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>고객 키에서 Microsoft 관리 키로 롤백

Microsoft 관리 키로 되전해야 하는 경우 할 수 있습니다. 오프보드를 해제하면 각 개별 워크로드에서 지원하는 기본 암호화를 사용하여 데이터가 다시 암호화됩니다. 예를 들어 microsoft Exchange Online 키를 사용하여 기본 암호화를 지원하는 경우를 예로 들 수 있습니다.

> [!IMPORTANT]
> 오프보더는 데이터 제거와는 동일하지 않습니다. 데이터 삭제는 조직의 데이터를 영구적으로 암호화로 삭제하고 Microsoft 365, 오프보더는 삭제하지 않습니다. 여러 작업 정책에 대해 데이터 제거를 수행할 수 없습니다.

다중 작업 DEP를 할당하는 데 고객 키를 사용하지 않을 경우 고객 키에서 "오프보드"를 요청하여 Microsoft 지원에 문의해야 합니다. 지원 팀에 고객 키 팀에 대한 서비스 Microsoft 365 요청합니다. 질문이 m365-ck@service.microsoft.com 문의하세요.

더 이상 사서함 수준 DEP를 사용하여 개별 사서함을 암호화하지 않을 경우 모든 사서함에서 사서함 수준 DEP를 제거하면 됩니다.

사서함 DEP의 배정을 Set-Mailbox PowerShell cmdlet을 사용 합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. cmdlet을 Set-Mailbox 실행합니다.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

이 cmdlet을 실행하면 현재 할당된 DEP 할당을 해제하고 기본 Microsoft 관리 키와 연결된 DEP를 사용하여 사서함을 다시 암호화합니다. Microsoft 관리 키에 사용되는 DEP의 배포를 unassign the unassign the로 할 수 없습니다. Microsoft 관리 키를 사용하지 않는 경우 사서함에 다른 고객 키 DEP를 할당할 수 있습니다.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>키를 해지하고 데이터 제거 경로 프로세스 시작

가용성 키를 포함하여 모든 루트 키의 해지 제어 고객 키는 규정 요구 사항의 종료 계획 측면을 제어할 수 있도록 합니다. 데이터를 삭제하고 서비스를 종료하기 위해 키를 해지하기로 결정한 경우 데이터 삭제 프로세스가 완료되면 서비스에서 가용성 키를 삭제합니다. 개별 사서함에 할당된 고객 키 DEP에 대해 지원됩니다.

Microsoft 365 제거 경로를 감사하고 유효성을 검사할 수 있습니다. 자세한 내용은 Service Trust Portal에서 사용할 수 있는 SSAE 18 SOC 2 [보고서를 참조하세요.](https://servicetrust.microsoft.com/) 또한 다음 문서가 권장됩니다.

- [Microsoft 클라우드의 금융 기관을 위한 위험 평가 및 규정 준수 가이드](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 종료 계획 고려 사항](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

다중 작업 DEP 제거는 고객 키에 Microsoft 365 지원되지 않습니다. 다중 워크로드 DEP는 모든 테넌트 사용자 전체의 여러 워크로드에서 데이터를 암호화하는 데 사용됩니다. 이러한 DEP를 제거하면 여러 워크로드에서 데이터에 액세스하지 못하게 됩니다. 서비스 Microsoft 365 종료하기로 결정한 경우 문서화된 프로세스에 따라 테넌트가 종료되는 경로를 따라야 합니다. 에서 테넌트 삭제 [방법을 Azure Active Directory.](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>고객 키 및 사용자에 대한 가용성 키 Exchange Online 비즈니스용 Skype

사용자 및 사용자 Exchange Online 비즈니스용 Skype 삭제 경로를 시작하면 DEP에 대해 영구 데이터 삭제 요청을 설정할 수 있습니다. 이렇게 하면 DEP가 할당된 사서함 내에서 암호화된 데이터가 영구적으로 삭제됩니다.

한 번의 DEP에 대해 PowerShell cmdlet만 실행할 수 있도록 데이터 삭제 경로를 시작하기 전에 모든 사서함에 단일 DEP를 다시 배정하는 것이 고려됩니다.

> [!WARNING]
> 데이터 삭제 경로를 사용하여 사서함의 하위 집합을 삭제하지 않습니다. 이 프로세스는 서비스를 종료하는 고객만 사용할 수 있습니다.

데이터 제거 경로를 시작하기 위해 다음 단계를 완료합니다.

1. Azure Key Vaults에서 "O365 Exchange Online"에 대한 래핑 및 래핑을 제거합니다.

2. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 PowerShell 에 [Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)

3. 삭제할 사서함이 포함된 각 DEP에 대해 다음과 같이 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet을 실행합니다.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   명령이 실패하는 경우 이 작업의 앞부분에서 지정한 대로 Azure Exchange Online 두 키에서 모든 키의 사용 권한을 제거해야 합니다.Set-DataEncryptionPolicy cmdlet을 사용하여 PermanentDataPurgeRequested 스위치를 설정하면 더 이상 사서함에 이 DEP를 할당할 수 없습니다.

4. Microsoft 지원에 문의하여 데이터 제거 eDocument를 요청합니다.

    요청 시 Microsoft는 데이터 선택을 승인하고 승인하기 위해 법적 문서를 전송합니다. 등록 중에 조직에서 승인자로 등록한 FastTrack 문서에 서명해야 합니다. 일반적으로 조직을 대신하여 문서에 서명할 수 있는 법적 권한이 있는 임원 또는 기타 지정된 사용자입니다.

5. 담당자가 법적 문서에 서명한 후 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).

    Microsoft가 법적 문서를 받으면 Microsoft는 cmdlet을 실행하여 정책을 처음 삭제하는 데이터 삭제를 트리거하고 사서함에 영구 삭제를 표시한 다음 가용성 키를 삭제합니다. 데이터 삭제 프로세스가 완료되면 데이터가 제거되고, 삭제된 데이터에 Exchange Online 수 있으며 복구할 수 없습니다.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 키 해지

SharePoint Online, 비즈니스용 OneDrive 및 Teams 삭제 경로를 시작하려면 다음 단계를 완료합니다.

1. Azure Key Vault 액세스를 해지합니다. 모든 주요 자격 증명 모음 관리자는 액세스를 해지하는 데 동의해야 합니다.

   온라인용 Azure Key Vault는 SharePoint 않습니다. 주요 자격 증명 모음은 여러 온라인 테넌트 및 SHAREPOINT 공유될 수 있습니다.

2. Microsoft에 문의하여 가용성 키를 삭제합니다.

    Microsoft에 연락하여 가용성 키를 삭제하면 법적 문서가 전송됩니다. 등록 중에 조직에서 승인자로 등록한 FastTrack 문서에 서명해야 합니다. 일반적으로 조직을 대신하여 문서에 서명할 수 있는 법적 권한이 있는 임원 또는 기타 지정된 사용자입니다.

3. 담당자가 법적 문서에 서명하면 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).

   Microsoft에서 법적 문서를 받으면 cmdlet을 실행하여 테넌트 키, 사이트 키 및 모든 문서별 개별 키의 암호화 삭제를 수행하여 키 계층 구조가 취소되는 데이터 삭제를 트리거합니다. 데이터 삭제 cmdlet이 완료되면 데이터가 제거됩니다.

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [가용성 키에 대해 자세히 알아보기](customer-key-availability-key-understand.md)

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [고객 Lockbox](customer-lockbox-requests.md)

- [서비스 암호화](office-365-service-encryption.md)

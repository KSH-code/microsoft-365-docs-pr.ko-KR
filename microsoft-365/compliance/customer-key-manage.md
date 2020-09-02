---
title: 고객 키 관리
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키를 설정한 후에는 AKV 키를 복원 하 고 사용 권한 및 데이터 암호화 정책을 관리 하 여이를 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 8f5f23fa1b8ce8baa8fafd3f29ca5fb8905887a1
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324260"
---
# <a name="manage-customer-key"></a>고객 키 관리

Office 365에 대 한 고객 키를 설정한 후에는이 문서에 설명 된 대로 키를 관리할 수 있습니다. 자세한 내용은 관련 항목의 고객 키를 참고 하십시오.

## <a name="restore-azure-key-vault-keys"></a>Azure 키 자격 증명 모음 키 복원

복원을 수행 하기 전에 일시 삭제로 제공 되는 복구 기능을 사용 합니다. 사용자 키와 함께 사용 되는 모든 키는 소프트 삭제를 사용 하도록 설정 해야 합니다. 일시 삭제는 휴지통 처럼 작동 하며 복원할 필요 없이 최대 90 일 동안 복구를 허용 합니다. 복구는 키 또는 키 보관소가 손실 된 경우와 같이 극단적인 상황 또는 예외적인 경우에만 필요 합니다. 고객 키와 함께 사용 하기 위해 키를 복원 해야 하는 경우 Azure PowerShell에서 다음과 같이 AzureKeyVaultKey cmdlet을 실행 합니다.
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

예를 들어,
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

키 보관소에 이름이 같은 키가 이미 있는 경우 복원 작업이 실패 합니다. AzKeyVaultKey는 키 이름을 포함 하 여 키에 대 한 모든 키 버전 및 메타 데이터를 복원 합니다.
  
## <a name="manage-key-vault-permissions"></a>키 보관소 사용 권한 관리

키 보관소 권한을 확인 하 고 제거 하는 데 사용할 수 있는 몇 가지 cmdlet이 제공 됩니다. 예를 들어 직원이 팀을 떠날 때 사용 권한을 제거 해야 할 수 있습니다. 이러한 각 작업에 대해 Azure PowerShell을 사용 합니다. Azure Powershell에 대 한 자세한 내용은 [Azure Powershell 개요](https://docs.microsoft.com/powershell/azure/)를 참조 하세요.

키 보관소 권한을 확인 하려면 AzKeyVault cmdlet을 실행 합니다.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

예를 들어,

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

관리자의 사용 권한을 제거 하려면 AzKeyVaultAccessPolicy cmdlet을 실행 합니다.
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

예를 들어,

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>고객 키를 사용 하 여 DEPs (데이터 암호화 정책) 관리

각 서비스 간에 다른 방식으로 Ps를 초기화 하는 고객 키 핸들 예를 들어 다양 한 서비스에 대해 DEPs의 수를 다르게 만들 수 있습니다.

**Exchange Online 및 비즈니스용 Skype:** 최대 50 DEPs를 만들 수 있습니다. 자세한 내용은 [Exchange Online 및 비즈니스용 Skype에서 사용할 DEP (데이터 암호화 정책) 만들기](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)를 참조 하세요.

**SharePoint Online, 비즈니스용 OneDrive 및 팀 파일:** DEP는 지리적 위치 ( _geo_라고도 함)의 데이터에 적용 됩니다. Office 365의 다중 지역 기능을 사용 하는 경우에는 각 지역에 따라 하나의 DEP를 만들 수 있습니다. 다중 geo를 사용 하지 않는 경우에는 하나의 DEP를 만들 수 있습니다. 일반적으로 고객 키를 설정할 때 DEP를 만듭니다. 자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive geo에 대 한 DEP (데이터 암호화 정책) 만들기](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)를 참조 하세요.

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype 용으로 만든 DEPs 확인

Get-DataEncryptionPolicy PowerShell cmdlet을 사용 하 여 Exchange Online 및 비즈니스용 Skype 용으로 만든 모든 DEPs의 목록을 확인 하려면 다음 단계를 완료 하세요.

1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.

2. 조직의 모든 DEPs를 반환 하려면 매개 변수를 사용 하지 않고 Get-Data과 Policy cmdlet을 실행 합니다.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Get-data과 Policy cmdlet에 대 한 자세한 내용은 [get-data과 policy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps)를 참조 하십시오.

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>클라우드로 사서함을 마이그레이션하기 전에 DEP를 할당 합니다.

DEP를 할당 하면 Microsoft 365는 마이그레이션 중에 할당 된 DEP를 사용 하 여 사서함의 내용을 암호화 합니다. 사서함을 마이그레이션하고, DEP를 할당 하 고, 암호화가 수행 될 때까지 기다리지 않고이 프로세스를 수행 하는 것이 보다 효율적입니다.

Office 365로 마이그레이션하기 전에 사서함에 DEP를 할당 하려면 Exchange Online PowerShell에서 설정-MailUser cmdlet을 실행 합니다.

1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.

2. 설정-MailUser cmdlet을 실행 합니다.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   여기서 *GeneralMailboxOrMailUserIdParameter* 는 사서함을 지정 하 고 *Dataencryptionpolicyidparameter* 는 DEP의 ID입니다. 설정-MailUser cmdlet에 대 한 자세한 내용은 [설정-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps)를 참조 하십시오.

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>사서함에 할당 된 DEP 확인

사서함에 할당 된 DEP를 확인 하려면 Get-mailboxstatistics cmdlet을 사용 합니다. Cmdlet은 고유 식별자 (GUID)를 반환 합니다.
  
1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   여기서 *GeneralMailboxOrMailUserIdParameter* 은 사서함을 지정 하 고 DataEncryptionPolicyID는 DEP의 GUID를 반환 합니다. Get-mailboxstatistics cmdlet에 대 한 자세한 내용은 [get-get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps)을 참조 하십시오.
  
2. Get-DataEncryptionPolicy cmdlet을 실행 하 여 사서함이 할당 된 DEP의 이름을 확인할 수 있습니다.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   여기서 *GUID* 는 이전 단계의 get-mailboxstatistics cmdlet에서 반환 하는 guid입니다.

## <a name="verify-that-customer-key-has-finished-encryption"></a>고객 키가 암호화를 완료 했는지 확인

단순히 고객 키를 롤백하거나 새 DEP를 할당 하거나 사서함을 마이그레이션한 적이 있는지 여부에 관계 없이이 섹션의 단계를 사용 하 여 암호화가 완료 되었는지 확인 합니다.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대 한 암호화 완료 확인

사서함을 암호화 하는 데 다소 시간이 걸릴 수 있습니다. DEP를 변경한 후 또는 사서함에 DEP를 처음 할당할 때 암호화 유효성 검사를 시도 하기 전에 72 시간을 기다리는 것이 좋습니다.
  
Get-mailboxstatistics cmdlet을 사용 하 여 사서함이 암호화 되어 있는지 여부를 확인할 수 있습니다.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

사서함이 암호화 된 경우 IsEncrypted 속성은 **true** 값을 반환 하 고 사서함이 암호화 되지 않은 경우에는 **false** 로 설정 합니다.

사서함 이동이 완료 되는 시간은 사서함의 크기에 따라 달라 집니다. 고객 키가 새 DEP를 할당 한 시간부터 72 시간 후 사서함을 완전히 암호화 하지 않은 경우 Microsoft 지원에 문의 하 여 도움을 요청 하세요. New-moverequest cmdlet은 로컬 사서함 이동에 더 이상 사용할 수 없습니다. 자세한 내용은 [이 공지](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 를 참조 하십시오.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 암호화 완료 확인

다음과 같이 SPODataEncryptionPolicy cmdlet을 실행 하 여 암호화 상태를 확인 합니다.

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

이 cmdlet의 출력은 다음과 같습니다.
  
- 기본 키의 URI입니다.

- 보조 키의 URI입니다.

- Geo의 암호화 상태입니다. 가능한 상태는 다음과 같습니다.

  - **등록 취소 됨:** 고객 키 암호화가 아직 적용 되지 않았습니다.

  - **등록:** 고객 키 암호화가 적용 되었으며 파일을 암호화 하 고 있습니다. 지역 키가 등록 되 고 있는 경우에는 geo의 사이트 비율에 대 한 정보를 표시 하 여 암호화 진행 상태를 모니터링할 수 있습니다.

  - **등록 된 경우:** 고객 키 암호화가 적용 되었으며 모든 사이트의 모든 파일이 암호화 되었습니다.

  - **롤링:** 키 롤이 진행 중입니다. 지역 키가 롤링을 진행 하는 경우 진행률을 모니터링할 수 있도록 키 롤 작업을 완료 한 사이트 비율에 대 한 정보도 표시 됩니다.

## <a name="unassign-a-dep-from-a-mailbox"></a>사서함에서 DEP 할당 해제

Set-mailbox PowerShell cmdlet을 사용 하 여 사서함에서 DEP를 할당 해제 하 고 `DataEncryptionPolicy` 를로 설정 `$NULL` 합니다. 이 cmdlet을 실행 하면 현재 할당 된 DEP를 할당 하지 않으며 기본 Microsoft 관리 키와 연결 된 DEP를 사용 하 여 사서함을 다시 암호화 합니다. Microsoft 관리 키에서 사용 하는 DEP는 할당 해제할 수 없습니다. Microsoft 관리 키를 사용 하지 않으려는 경우 다른 DEP를 사서함에 할당할 수 있습니다.

사서함 PowerShell cmdlet을 사용 하 여 사서함에서 DEP를 할당 해제 하려면 다음 단계를 완료 합니다.

1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.

2. Set-Mailbox cmdlet을 실행 합니다.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>키 해지 및 데이터 제거 경로 프로세스 시작

가용성 키를 포함 하 여 모든 루트 키의 해지를 제어할 수 있습니다. Customer 키를 통해 규정 요구 사항의 종료 계획 측면을 제어할 수 있습니다. 키를 해지 하 여 데이터를 제거 하 고 서비스를 종료 하는 경우 서비스는 데이터 제거 프로세스가 완료 된 후에 가용성 키를 삭제 합니다.

Microsoft 365에서 데이터 제거 경로를 감사 하 고 유효성을 검사 합니다. 자세한 내용은 [서비스 보안 포털](https://servicetrust.microsoft.com/)에서 사용할 수 있는 SSAE 18soc 2 보고서를 참조 하세요. 또한 Microsoft는 다음 문서를 권장 합니다.

- [Microsoft 클라우드의 금융 기관에 대 한 위험 평가 및 준수 가이드](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 종료 계획 고려 사항](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

데이터 제거 경로가 서로 다른 서비스 간에 약간씩 다릅니다.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대 한 고객 키 및 가용성 키 해지

Exchange Online 및 비즈니스용 Skype의 데이터 제거 경로를 시작할 때 DEP에 영구 데이터 제거 요청을 설정 합니다. 이렇게 하면 DEP가 할당 된 사서함 내에서 암호화 된 데이터가 영구적으로 삭제 됩니다.

한 번에 한 명의 DEP에 대해 PowerShell cmdlet을 실행할 수 있으므로 데이터 제거 경로를 시작 하기 전에 모든 사서함에 단일 DEP를 다시 할당 하는 것이 좋습니다.

> [!WARNING]
> 사서함의 하위 집합을 삭제 하는 데 데이터 제거 경로를 사용 하지 마십시오. 이 프로세스는 서비스를 종료 하는 고객 에게만 적합 합니다.

데이터 제거 경로를 시작 하려면 다음 단계를 완료 합니다.

1. Azure 키 자격 증명 모음에서 "O365 Exchange Online"에 대 한 줄 바꿈 및 래핑 해제 권한을 제거 합니다.

2. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.

3. 삭제 하려는 사서함이 포함 된 각 DEP에 대해 다음과 같이 [Set-Data\ 정책](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet을 실행 합니다.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   명령이 실패 하면이 작업의 앞부분에서 설명한 대로 Azure 키 자격 증명 모음의 두 키에서 Exchange Online 권한을 제거 했는지 확인 합니다.PermanentDataPurgeRequested 스위치를 set-DataEncryptionPolicy cmdlet을 사용 하 여 설정 하면 더 이상이 DEP를 사서함에 할당할 수 없습니다.

4. Microsoft 지원에 문의 하 여 데이터 삭제를 요청 합니다.

    요청 시 Microsoft는 데이터 삭제를 승인 하 고 권한을 부여할 수 있는 법적 문서를 보내 달라고 합니다. 온 보 딩 시에이 문서에 서명 해야 하는 경우 FastTrack의 승인자로 등록 한 조직 내의 사용자입니다. 일반적으로 회사에서 조직 대신 서류에 서명할 수 있는 권한이 부여 된 임원 또는 기타 지정 된 사람입니다.

5. 담당자가 법률 문서에 서명한 후에는 보통 eDoc 서명을 통해 Microsoft에 반송 합니다.

    Microsoft는 유효한 문서를 받은 후에 cmdlet을 실행 하 여 먼저 정책을 삭제 하는 데이터 삭제를 트리거하여, 사서함을 영구 삭제 하도록 표시 한 다음, 가용성 키를 삭제 합니다. 데이터 제거 프로세스가 완료 되 면 데이터가 제거 되 고 Exchange Online에서 액세스할 수 없으며 복구할 수 없습니다.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키 및 가용성 키 해지

SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 데이터 제거 경로를 시작 하려면 다음 단계를 완료 합니다.

1. Azure 키 자격 증명 모음 액세스를 해지 합니다. 모든 키 자격 증명 관리자는 액세스 취소에 동의 해야 합니다.

   SharePoint Online에 대 한 Azure 키 자격 증명 모음을 삭제 하지 않습니다. 키 자격 증명은 여러 SharePoint Online 테 넌 트 및 DEPs 간에 공유 될 수 있습니다.

2. Microsoft에 연락 하 여 가용성 키를 삭제 합니다.

    Microsoft에 연락 하 여 가용성 키를 삭제 하면 올바른 문서가 전송 됩니다. 온 보 딩 시에이 문서에 서명 해야 하는 경우 FastTrack의 승인자로 등록 한 조직 내의 사용자입니다. 일반적으로 회사에서 조직 대신 서류에 서명할 수 있는 권한이 있는 임원 또는 기타 지정 된 사용자입니다.

3. 담당자가 법률 문서에 서명 하면 일반적으로 eDoc 서명을 통해 Microsoft에 반송 합니다.

   Microsoft는 법률 문서를 받은 후 cmdlet을 실행 하 여 테 넌 트 키, 사이트 키 및 모든 개별 문서에 대 한 암호화 삭제를 수행 하는 데이터 삭제를 트리거하여 키 계층 구조를 영구적으로 중단 합니다. 데이터 제거 cmdlet이 완료 되 면 데이터가 제거 된 것입니다.

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [가용성 키에 대 한 자세한 정보](customer-key-availability-key-understand.md)

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [고객 Lockbox](customer-lockbox-requests.md)

- [서비스 암호화](office-365-service-encryption.md)

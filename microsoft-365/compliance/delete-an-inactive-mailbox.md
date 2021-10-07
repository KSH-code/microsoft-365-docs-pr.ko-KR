---
title: 비활성 사서함 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: 비활성 사서함의 콘텐츠를 더 Microsoft 365 비활성 사서함을 영구적으로 삭제할 수 있습니다.
ms.openlocfilehash: f0f60952db4b4a63dd0c72d1cd467e918a1a68c4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203174"
---
# <a name="delete-an-inactive-mailbox"></a>비활성 사서함 삭제

비활성 사서함은 조직에서 나서 이전 직원의 전자 메일을 보존하는 데 사용됩니다. 비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우 비활성 사서함을 영구적으로 삭제할 수 있습니다. 또한 비활성 사서함에 여러 보류가 배치될 수도 있습니다. 예를 들어 비활성 사서함은 소송 보류에 배치될 수 있으며 하나 이상의 소송 In-Place 있습니다. 또한 비활성 사서함에 보존 정책(Office 365 또는 Microsoft 365)이 적용될 수 있습니다. 비활성 사서함에서 모든 보류 및 보존 정책을 제거하여 삭제해야 합니다. 보존 및 보존 정책을 제거한 후 비활성 사서함은 삭제로 표시되고 처리된 후 영구적으로 삭제됩니다.
  
> [!IMPORTANT]
> 사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 In-Place 관리 센터에서 보존 Exchange 발표하고 있습니다. 즉, 소송 보존 및 보존 정책을 사용하여 비활성 사서함을 만들어야 합니다. 2020년 7월 1일부터는 새 보류를 In-Place 수 Exchange Online. 그러나 비활성 사서함에 배치된 보류 In-Place 변경할 수 있습니다. 그러나 2020년 10월 1일부터는 보류 기간을 변경할 수 없습니다. 비활성 사서함은 비활성 사서함을 제거하여 비활성 사서함만 삭제할 In-Place 있습니다. 보류에 있는 In-Place 비활성 사서함은 보존이 제거될 때까지 계속 보존됩니다. 보류의 사용 중지에 대한 In-Place 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.
  
[비활성 사서함에서](#more-information) 보류를 제거한 후 발생하는 일에 대한 설명은 추가 정보 섹션을 참조하세요.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>비활성 사서함을 삭제하기 전에

- PowerShell을 사용하여 Exchange Online 사서함에서 소송 보류를 제거해야 합니다. EAC(Exchange 관리 센터)는 사용할 수 없습니다. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.

- 비활성 사서함의 내용을 다른 사서함에 복사한 후 보류를 제거하고 비활성 사서함을 삭제할 수 있습니다. 자세한 내용은 [Restore an inactive mailbox in Office 365.](restore-an-inactive-mailbox.md)

- 비활성 사서함에서 보존 또는 보존 정책을 제거하고 사서함에 대한 소프트 삭제된 사서함 보존 기간이 만료된 경우 사서함은 영구적으로 삭제됩니다. 삭제된 후 복구할 수 없습니다. 보류를 제거하기 전에 사서함의 내용이 더 이상 필요하지 않습니다. 비활성 사서함을 다시 활성화 하려는 경우 복구할 수 있습니다. 자세한 내용은 [Recover an inactive mailbox in Office 365.](recover-an-inactive-mailbox.md)

- 비활성 사서함에 대한 자세한 내용은 에서 [비활성 사서함을 Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>1단계: 비활성 사서함에 대한 보류 식별

앞서 설명한 것 처럼 소송 보존, In-Place 또는 보존 정책이 비활성 사서함에 배치될 수 있습니다. 첫 번째 단계는 비활성 사서함에 대한 보류를 식별하는 것입니다.
  
다음 명령을 실행하여 조직의 모든 비활성 사서함에 대한 보류 정보를 표시합니다.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled** 속성의 **True** 값은 비활성 사서함이 소송 보류 상태임을 나타냅니다. 비활성 In-Place 사서함에 대해 보류의 GUID가 **InPlaceHolds** 속성 값으로 표시됩니다. 예를 들어 두 개의 비활성 사서함에 대한 다음 결과는 Ann Beebe에 소송 보존이 적용되어 있으며 pilar Pinilla에 In-Place 보존 정책이 적용되어 있는 것으로 나타 내보겠습니다.
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 많은 In-Place 보류 또는 보존 정책이 비활성 사서함에 배치되는 경우 모든 In-Place 보류 GUID가 표시되지 않습니다. 다음 명령을 실행하여 InPlaceHolds 속성에 모든 GUID를 표시할 수 있습니다.  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
보류를 식별하는 방법에 대한 자세한 내용은 사서함에 배치된 보류 유형을 [식별하는 방법을 참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md)

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>2단계: 비활성 사서함에서 보류 제거

비활성 사서함에 배치되는 보류 유형과 여러 보류가 있는지 여부를 확인한 후 다음 단계는 사서함의 보류를 제거하는 것입니다. 앞서 설명한 것 처럼 비활성 사서함을 영구적으로 삭제하려면 모든 보류를 제거해야 합니다.
  
### <a name="remove-a-litigation-hold"></a>소송 보류 제거

앞서 설명한 것 처럼 비활성 사서함에서 Windows PowerShell 소송 보류를 제거 하는 데 사용할 수 있습니다. EAC는 사용할 수 없습니다. 다음 명령을 실행하여 소송 보류를 제거합니다.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 비활성 사서함을 식별하는 가장 좋은 방법은 고유 이름 또는 GUID Exchange 사용하는 것입니다. 이러한 값 중 하나를 사용하면 잘못된 사서함을 실수로 지정하는 것을 방지할 수 있습니다. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>보존 정책에서 비활성 사서함 제거

비활성 사서함에서 비활성 사서함을 제거하는 Microsoft 365 정책은 비활성 사서함에 할당된 보존 정책이 조직 전체 또는 명시적인지에 따라 결정됩니다. 은 비활성 사서함에 할당된 보존 정책 유형에 대한 것입니다.

- 조직의 모든 사서함에 할당된 조직 전체 보존 정책 PowerShell에서 **Get-OrganizationConfig** cmdlet을 Exchange Online 조직 전체 보존 정책에 대한 정보를 얻습니다.

- 특정 사서함에 할당된 특정 위치 보존 정책 특정 사용자의 콘텐츠 위치에 할당되는 정책입니다. PowerShell의 **Get-Mailbox -IncludeInactiveMailbox** cmdlet을 사용하여 Exchange Online 비활성 사서함에 할당된 보존 정책에 대한 정보를 얻을 수 있습니다.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>조직 전체 보존 정책에서 비활성 사서함 제거

PowerShell에서 Exchange Online 명령을 실행하여 조직 전체 보존 정책에서 비활성 사서함을 제외합니다.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

비활성 사서함에 적용된 조직 전체 보존 정책을 식별하고 보존 정책의 GUID를 얻는 방법에 대한 자세한 내용은 사서함에 배치된 보류 유형을 식별하는 방법의 "Get-OrganizationConfig" 섹션을 [참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)

또는 다음 명령을 실행하여 모든 조직 전체 정책에서 비활성 사서함을 제거할 수 있습니다.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>특정 위치 보존 정책에서 비활성 사서함 제거

Security & Compliance [Center PowerShell에서](/powershell/exchange/connect-to-scc-powershell) 다음 명령을 실행하여 명시적 보존 정책에서 비활성 사서함을 제거합니다.

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

비활성 사서함에 적용된 특정 위치 보존 정책을 식별하고 보존 정책의 GUID를 얻는 방법에 대한 자세한 내용은 사서함에 배치된 보류 유형을 식별하는 방법의 "Get-Mailbox" 섹션을 [참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)

### <a name="remove-in-place-holds"></a>원본 위치 보존 제거

 비활성 사서함에서 보류를 In-Place 방법은 두 가지가 있습니다. 
  
- **Hold In-Place 삭제합니다.** 영구적으로 삭제할 비활성 사서함이 비활성 보류에 대한 유일한 원본 In-Place 보류 개체를 In-Place 있습니다. 

    > [!NOTE]
    > Hold 개체를 삭제하려면 먼저 보류를 In-Place 합니다. 보류를 사용하도록 In-Place Hold 개체를 삭제하려고 시도하면 오류 메시지가 표시됩니다. 
  
- 비활성 사서함을 보류의 원본 **사서함으로 In-Place 제거합니다.** 보류에 대해 다른 원본 사서함을 In-Place 경우 원본 사서함 목록에서 비활성 사서함을 제거하고 비활성 사서함을 In-Place 수 있습니다.

#### <a name="delete-an-in-place-hold"></a>보류 In-Place 삭제

1. 삭제할 보류 In-Place 속성이 포함된 변수를 생성합니다. 1단계: In-Place 사서함에 대한 보류 확인에서 획득한 보류 GUID를 [사용할 수 있습니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. 보류를 사용하지 In-Place.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. 보류 In-Place 삭제합니다.

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>비활성 사서함에서 비활성 In-Place 제거

원본 In-Place 사서함 수가 많은 경우 비활성 사서함이 EAC의 원본 페이지에 나열되지 않는  것일 수 있습니다. 보류를 편집하면 원본 페이지에 최대 3,000개 In-Place 표시됩니다.  비활성 사서함이 원본 페이지에 나열되지 않은 경우 PowerShell을 사용하여 Exchange Online 보류에서 제거할 In-Place 있습니다.  
  
1. 비활성 사서함에 배치된 In-Place 속성이 포함된 변수를 만드시오. 1단계: In-Place 사서함에 대한 보류 확인에서 획득한 보류 GUID를 [사용할 수 있습니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. 비활성 사서함이 보류의 원본 사서함으로 In-Place 합니다. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > In-Place Hold의 *Sources* 속성은 *LegacyExchangeDN* 속성으로 원본 사서함을 식별합니다. 이 속성은 비활성 사서함을 고유하게 식별하기 때문에 In-Place 보류에서 *Sources* 속성을 사용하면 잘못된 사서함을 제거하는 것을 방지할 수 있습니다. 또한 두 사서함의 별칭 또는 SMTP 주소가 같은 경우 문제를 방지하는 데에도 도움이 됩니다. 

3. 변수의 원본 사서함 목록에서 비활성 사서함을 제거합니다. 이전 단계의 명령에 의해 반환된 비활성 사서함의 **LegacyExchangeDN을** 사용해야 합니다. 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    예를 들어 다음 명령은 Pilar Pinilla의 비활성 사서함을 제거합니다.

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. 비활성 사서함이 변수의 원본 사서함 목록에서 제거되어 있는지 확인

   ```powershell
   $InPlaceHold.Sources
   ```

5. 비활성 In-Place 없는 업데이트된 원본 사서함 목록으로 보류를 수정합니다.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. 비활성 사서함이 비활성 사서함의 원본 사서함 목록에서 In-Place 확인 합니다.

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>추가 정보

- **비활성 사서함은 소프트 삭제된 사서함의 유형입니다.** 이 Exchange Online 사서함은 삭제된 사서함이지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다. 이전에 비활성 상태인 사서함은 183일 동안 Exchange Online 사서함으로 사용할 수 있습니다. 즉, 사서함이 소프트 삭제된 후 183일 이내에 복구할 수 있습니다. 183일이 지난 후 소프트 삭제된 사서함은 영구적으로 삭제된 것으로 표시되고 복구할 수 없습니다.

- **비활성 사서함에 대한 보류를 제거하면 어떻게 하나요?** 사서함은 다른 소프트 삭제된 사서함처럼 처리되고 183일의 소프트 삭제된 사서함 보존 기간이 만료된 후 영구적으로 삭제된 것으로 표시됩니다. 이 보존 기간은 사서함이 처음 비활성화된 날짜에 시작됩니다. 이 날짜를 일시 삭제 날짜(해당 사용자 계정이 삭제된 날짜 또는 **Remove-Mailbox** cmdlet을 사용하여 Exchange Online 사서함이 삭제된 날짜)라고 합니다. 일시 삭제된 날짜는 보류를 제거하는 날짜가 아니며,

- **비활성 사서함은 보류가 제거된 직후 영구적으로 삭제하나요?** 이전의 비활성 사서함은 183일 동안 소프트 삭제 상태로 사용할 수 있습니다. 183일이 지난 후 사서함은 영구 삭제로 표시됩니다.

- **보류가 제거된 후 비활성 사서함에 대한 정보를 표시하는 방법** 보류가 제거되고 비활성 사서함이 소프트 삭제된 사서함으로 되돌아가면 **Get-Mailbox** cmdlet과 *함께 InactiveMailboxOnly* 매개 변수를 사용하여 반환되지 않습니다. 그러나 **Get-Mailbox -SoftDeletedMailbox** 명령을 사용하여 사서함에 대한 정보를 표시할 수 있습니다. 예제:

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  위의 예제에서 *WhenSoftDeleted* 속성은 일시 삭제된 날짜(이 예제에서는 2020년 6월 16일)를 식별합니다. *WasInactiveMailbox* 속성은 이전에 비활성 사서함이기 때문에 `True` 나열됩니다. 사서함은 2020년 9월 30일 이후 183일 후에 영구적으로 삭제됩니다.


---
title: 보류된 사물함의 복구 가능한 항목 할당량 증가
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 보관 사서함을 사용하도록 설정하고 자동 확장 보관을 설정하여 사서함의 복구 가능한 항목 폴더 크기를 Microsoft 365.
ms.openlocfilehash: fef1a5f77551006ed6df180185ad865c8b26b285
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335625"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>보류된 사물함의 복구 가능한 항목 할당량 증가

기본 Exchange *MRM* 정책이라는 기본 Exchange Online 보존 정책에는 보관함으로 14일 이동이라는 보존 태그가 포함되어 있습니다. 이 보존 태그는 특정 항목의 보존 기간 14일이 만료되면 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 항목이 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더로 이동합니다. 이렇게 항목이 이동하려면 사용자의 보관 사서함을 반드시 사용하도록 설정해야 합니다. 보관 사서함을 사용하도록 설정하지 않은 경우, 어떠한 조치도 취하지 않으면 보류된 사서함의 복구 가능한 항목 폴더에 있는 항목이 보존 기간 14일이 만료된 후에도 보관 사서함으로 이동하지 않습니다. 보류된 사서함에서 어떤 항목도 삭제되지 않기 때문에 복구 가능한 항목 폴더의 저장소 할당량이 초과될 수 있으며 사용자의 보관 사서함을 사용하도록 설정하지 않으면 특히 이러한 경우가 발생할 수 있습니다.

이 제한을 초과할 확률을 줄이기 위해 복구 가능한 항목 폴더의 저장소 할당량은 사서함에 대해 보류가 설정될 때 자동으로 30GB에서 100GB로 Exchange Online. 보관 사서함을 사용하도록 설정하는 경우에도 보관 사서함에 있는 복구 가능한 항목 폴더의 저장소 할당량이 30GB에서 100GB로 증가합니다. Exchange Online 자동 확장 보관 기능을 사용하도록 설정한 경우 복구 가능한 항목 폴더를 포함하여 사용자의 보관 사서함에 대한 총 저장소 할당량은 1.5 TB입니다.

  다음 표는 복구 가능한 항목 폴더의 저장소 할당량을 간략하게 보여줍니다.

| 복구 가능한 항목 폴더 위치 | 보류되지 않은 사서함 | 보류된 사서함 |
|:-----|:-----|:-----|
|기본 사서함 |30GB |100GB |
|복구 가능한 항목 폴더를 포함한 보관 사서함 <sup>\*</sup> |1.5TB |1.5TB |

> [!NOTE]
> <sup>\*</sup>보관 사서함에 대한 초기 저장소 할당량은 라이선스가 있는 사용자의 경우 100GB Exchange Online(계획 2) 입니다. 그러나 보류된 사서함에 대해 자동 확장 보관이 설정되어 있는 경우 보관 사서함과 복구할 수 있는 항목 폴더의 저장소 할당량은 모두 110GB로 증가합니다. 필요한 경우 최대 1.5 TB의 추가 보관 저장소 공간(복구 가능한 항목 폴더 포함)이 프로비전됩니다. 자동 확장 보관에 대한 자세한 내용은 자동 확장 보관 개요를 [참조하세요.](autoexpanding-archiving.md)

보류된 사서함의 기본 사서함에 있는 복구 가능한 항목 폴더의 저장소 할당량이 한도에 도달하려는 경우 다음 항목을 수행할 수 있습니다.

- **보관 사서함을 사용하도록 설정하고 자동 확장 보관을 켜야 합니다.** 보관 사서함을 사용하도록 설정한 다음 보관 사서함의 자동 확장 보관 기능을 켜기만 하면 복구 가능한 항목 폴더에 대해 추가 저장소 용량을 사용하도록 설정할 수 Exchange Online. 그러면 기본 사서함의 복구 가능한 항목 폴더에 대해 110GB가 필요하고 보관함 및 복구 가능한 항목 폴더에 대해 최대 1.5 TB의 저장소 용량이 결합됩니다. 자세한 내용은 [보관](enable-archive-mailboxes.md) 사서함 사용 및 자동 확장 보관 사용 [을 참조하세요.](enable-autoexpanding-archiving.md)

    > [!NOTE]
    > 복구 가능한 항목 폴더의 저장소 할당량 초과에 가까운 사서함에 대해 보관을 사용하도록 설정한 후 관리되는 폴더 도우미를 실행하여 도우미를 수동으로 트리거하여 만료된 항목이 보관 사서함의 복구 가능한 항목 폴더로 이동하도록 사서함을 처리하도록 도우미를 수동으로 트리거할 수 있습니다. [4단계](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)에서 지침을 확인하세요. 사용자의 사서함에 있는 다른 항목이 새로운 보관 사서함으로 이동되었을 수 있다는 점에 유의하시기 바랍니다. 보관 사서함을 사용하도록 설정한 후에 이러한 일이 발생하도록 사용자에게 알려 주면 됩니다.

- **보류된 Exchange 사용자 지정 보존 정책을 만들 수 있습니다.** 보관 사서함을 사용하도록 설정하고 소송 보존 또는 In-Place 사서함에 대해 보관을 자동으로 확장하는 것 외에도 보류된 사서함에 대한 사용자 지정 Exchange 보존 정책을 만들 수도 있습니다. 이렇게 하면 보류되지 않은 사서함에 적용되는 기본 MRM 정책과는 다른 보존 정책을 보류된 사서함에 적용할 수 있으며 보류된 사서함에 대해 설계된 보존 태그를 적용할 수 있습니다. 여기에는 복구 가능한 항목 폴더에 대한 새 보존 태그 만들기가 포함됩니다.

이 항목의 나머지에서는 보류된 사서함에 대한 사용자 지정 Exchange 절차에 대해 설명합니다.

[1단계: 복구 가능한 항목 폴더에 대한 사용자 지정 보존 태그를 만듭니다.](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[2단계: 보류된 Exchange 대한 새 사서함 보존 정책 만들기](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[3단계: 보류된 Exchange 새 보존 정책 적용](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[(옵션)4단계: 관리되는 폴더 도우미를 실행하여 새로운 보존 설정을 적용합니다.](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>1단계: 복구 가능한 항목 폴더에 대한 사용자 지정 보존 태그를 만듭니다.

첫 번째 단계는 복구 가능한 항목 폴더에 대하여 사용자 지정 보존 태그(보존 정책 태그 또는 RPT라고 함)를 만드는 것입니다. 앞서 설명된 바와 같이 이 RPT는 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 항목을 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더로 이동합니다. PowerShell을 사용하여 복구 가능한 항목 폴더에 대한 RPT를 만들어야 합니다. EAC(Exchange 관리 센터)는 사용할 수 없습니다.

1. [원격 PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)

2. 복구할 수 있는 항목 폴더에 대한 새로운 RPT를 만들려면 다음 명령을 실행합니다. 

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    예를 들어 다음 명령은 보존 기간이 30일인 "보류된 사서함의 복구 가능한 항목 30일"이라는 복구 가능한 항목 폴더에 대한 RPT를 만듭니다. 이는 어떤 항목이 복구 가능한 항목 폴더에서 30일 동안 있은 후 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더로 이동함을 의미합니다.

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 복구 가능한 항목 RPT에 대한 보존  _기간(AgeLimitForRetention_ 매개 변수로 정의)은 RPT가 적용될 사서함의 삭제된 항목 보존 기간과 동일한 것이 좋습니다. 이렇게 하면 사용자가 삭제된 항목 보존 기간을 전부 활용하여 삭제된 항목이 보관 사서함으로 이동하기 전에 삭제된 항목을 복구할 수 있습니다. 이전 예에서는 사서함의 삭제된 항목 보존 기간도 30일이라는 가정 하에 보존 기간이 30일로 설정되었습니다. 기본적으로 Exchange Online 사서함은 14일 동안 삭제된 항목을 보존하도록 구성됩니다. 하지만 이 설정을 최대 30일로 변경할 수 있습니다. 자세한 내용은 [Change the deleted item retention period for a mailbox in Exchange Online.](https://www.microsoft.com/?ref=go)

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>2단계: 보류된 Exchange 대한 새 사서함 보존 정책 만들기

다음 단계는 새로운 보존 정책을 만들고 1단계에서 만든 복구 가능한 항목 RPT 등 이 새로운 보존 정책에 보존 태그를 추가하는 것입니다. 새로운 보존 정책은 다음 단계에서 보류된 사서함에 적용됩니다. 

새로운 보존 정책을 만들기 전에 추가할 추가적인 보존 태그를 결정합니다. 기본 MRM 정책에 추가되는 보존 태그의 목록 및 새로운 보존 태그에 대한 정보를 확인하려면 다음을 참조하세요.

- [Exchange Online의 기본 보존 정책](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [보존 정책 태그를 지원하는 기본 폴더](/exchange/security-and-compliance/messaging-records-management/default-folders)

- 보존 정책 만들기 항목의 "보존 태그 만들기" [섹션](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy)

EAC 또는 PowerShell을 사용하여 Exchange Online 정책을 만들 수 있습니다.

### <a name="use-the-eac-to-create-a-retention-policy"></a>EAC를 사용하여 보존 정책 만들기

1. EAC에서 준수 **관리** 보존 정책으로 이동한 다음 아이콘 \>  **추가를** ![ ](../media/ITPro-EAC-AddIcon.gif) 클릭합니다.

2. **새 보존 정책** 페이지의 **이름** 에서 **MRM Policy for Mailboxes on Hold** 등 보존 정책의 목적을 설명하는 이름을 입력합니다. 

3. 보존 **태그에서** 아이콘 **추가를** ![ ](../media/ITPro-EAC-AddIcon.gif) 클릭합니다.

4. 보존 태그 목록에서 1단계에서 만든 복구 가능한 항목 RPT를 선택한 다음 **추가** 를 클릭합니다.

    ![사용자 지정 복구 가능한 항목 보존 태그를 선택합니다.](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. 보존 정책에 추가할 추가적인 보존 태그를 선택합니다. 예를 들어 기존 MRM 정책에 포함되어 있는 것과 동일한 태그를 추가하는 것이 좋습니다.

6. 보존 태그 추가가 완료되면 **확인** 을 클릭합니다.

7. **저장** 을 클릭하여 새 보존 정책을 만듭니다.

    보존 정책에 연결된 보존 태그가 세부 정보 창에 표시된다는 점에 유의하시기 바랍니다.

    ![보존 정책에 연결된 보존 태그는 세부 정보 창에 표시됩니다.](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>PowerShell Exchange Online 사용하여 보존 정책 만들기

보류된 사서함에 대한 새 보존 정책을 만들려면 다음 명령을 실행합니다. 

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>
```

예를 들어 다음 명령은 이전 그림에 표시된 보존 정책 및 연결된 보존 태그를 만듭니다.

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>3단계: 보류된 Exchange 새 보존 정책 적용

마지막 단계는 조직의 보류된 사서함에 2단계에서 만든 새로운 보존 정책을 적용하는 것입니다. EAC 또는 PowerShell을 사용하여 Exchange Online 사서함 하나 또는 여러 사서함에 보존 정책을 적용할 수 있습니다.

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>EAC를 사용하여 새 보존 정책 적용하기

1. 받는 사람  >  **사서함으로 이동 합니다.**

2. 목록 보기에서 보존 정책을 적용할 사서함을 선택하고 편집 편집 **아이콘을** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.

3. **사용자 사서함** 페이지에서 **사서함 기능** 을 클릭합니다.

4. **보존 정책** 에서 2단계에서 만든 보존 정책을 선택하고 **저장** 을 클릭합니다.

EAC를 사용하여 여러 사서함에 보존 정책을 적용할 수도 있습니다.

1. 받는 사람  >  **사서함으로 이동 합니다.**

2. 목록 보기에서 Shift 또는 Ctrl 키를 사용하여 여러 개의 사서함을 선택합니다.

3. 세부 정보 창에서 **기타 옵션** 을 클릭합니다.

4. **보존 정책** 에서 **업데이트** 를 클릭합니다.

5. **대량 할당 보존 정책** 페이지에서 2단계에서 만든 보존 정책을 선택하고  **저장** 을 클릭합니다. 

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>PowerShell Exchange Online 사용하여 새 보존 정책 적용

PowerShell을 Exchange Online 새 보존 정책을 단일 사서함에 적용할 수 있습니다. 그러나 PowerShell의 실질적인 기능을 통해 조직의 소송 보존 또는 In-Place 보류에 있는 모든 사서함을 빠르게 식별한 다음 단일 명령으로 보류된 모든 사서함에 새 보존 정책을 적용할 수 있습니다. 다음은 PowerShell을 사용하여 하나 이상의 Exchange 보존 정책을 적용하는 몇 가지 예입니다. 모든 예에서는 2단계에서 만든 보존 정책을 적용합니다.

이 예에서는 Pilar Pinilla의 사서함에 새로운 보존 정책을 적용합니다.

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

이 예에서는 조직의 모든 소송 보존 사서함에 새로운 보존 정책을 적용합니다.

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

이 예에서는 조직의 모든 원본 위치 유지 사서함에 새로운 보존 정책을 적용합니다.

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

**Get-Mailbox** cmdlet를 사용하여 새로운 보존 정책이 적용되었는지 확인할 수 있습니다.

다음은 이전 예에서 소송 보존 사서함 및 원본 위치 유지 사서함에 "보류된 사서함에 대한 MRM 정책" 보존 정책이 적용되었는지 확인하기 위한 몇 가지 예입니다.

```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>(옵션) 4단계: 관리되는 폴더 도우미를 실행하여 새로운 보존 설정을 적용합니다.

새 Exchange 보존 정책을 보류된 사서함에 적용한 후 관리되는 폴더 Exchange Online 새 보존 정책의 설정을 사용하여 이러한 사서함을 처리하기까지 최대 7일이 걸릴 수 있습니다. 관리되는 폴더 도우미가 실행되기를 기다리는 대신 **Start-ManagedFolderAssistant** cmdlet를 사용하여 새로운 보존 정책이 적용된 사서함을 처리하도록 도우미를 수동으로 트리거할 수 있습니다.

다음 명령을 실행하여 Pilar Pinilla의 사서함에 관리되는 폴더 도우미를 실행합니다. 

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

다음 명령을 실행하여 보류된 모든 사서함에 관리되는 폴더 도우미를 실행합니다. 

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>추가 정보

- 사용자의 보관 사서함을 사용하도록 설정한 후 사용자에게 사서함에 있는 다른 항목(복구 가능한 항목 폴더에 있는 항목 외)이 보관 사서함으로 이동될 수 있다는 점을 안내하는 것이 좋습니다. Exchange Online 사서함에 할당된 기본 MRM 정책에는 항목이 사서함으로 배달되거나 사용자가 만든 날짜 이후 2년 후에 항목을 보관 사서함으로 이동하는 보존 태그(기본 2년 후 보관함으로 이동)가 포함되어 있기 때문에입니다. 자세한 내용은 Default [Retention Policy in Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- 사용자의 보관 사서함을 사용하도록 설정한 후 사용자에게 보관 사서함의 복구 가능한 항목 폴더에서 삭제된 항목을 복구할 수 있다고 안내하시기 바랍니다. 보관 사서함에서 Outlook 폴더를 선택한 다음  홈 탭에서 서버에서 삭제된 항목  복구를 클릭하여 이 작업을 할 **수** 있습니다. 삭제된 항목을 복구하는 데 대한 자세한 내용은 에서 지운 Outlook [복구를 Windows.](https://go.microsoft.com/fwlink/p/?LinkId=624829)

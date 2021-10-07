---
title: 비활성 사서함 복원
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
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 비활성 사서함의 내용을 기존 사서함에 복원(또는 병합)하는 방법을 Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b57a309ed686f2fe2aaee34fb3b89264a2de9812
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159781"
---
# <a name="restore-an-inactive-mailbox"></a>비활성 사서함 복원

비활성 사서함(소프트 삭제된 사서함의 한 유형)은 퇴사한 후 이전 직원의 전자 메일을 유지하는 데 사용됩니다. 다른 직원이 퇴사한 직원의 직무를 대신하거나 해당 직원이 조직으로 돌아오면 다음 두 가지 방법으로 사용자가 비활성 사서함의 콘텐츠를 사용할 수 있습니다.

- **비활성 사서함 복원** 다른 직원이 퇴사한 직원의 직무를 대신하거나 다른 사용자가 비활성 사서함의 콘텐츠에 액세스해야 하는 경우 비활성 사서함의 내용을 기존 사서함으로 복원하거나 병합할 수 있습니다. 비활성 사서함에서 보관 파일을 복원할 수도 있습니다. 사서함이 복원된 후 비활성 사서함은 보존되고 비활성 사서함으로 보존됩니다. 이 항목에서는 비활성 사서함을 복원하는 절차에 대해 설명합니다.

- **비활성 사서함 복구** 퇴사한 직원이 조직으로 돌아오거나 퇴사한 직원의 직무를 위해 신입 사원이 고용된 경우 비활성 사서함의 내용을 복구할 수 있습니다. 이 메서드는 비활성 사서함을 비활성 사서함의 내용이 포함된 새 사서함으로 변환합니다. 복구한 후 비활성 사서함 존재 하지 않습니다. 단계별 절차는 [에서 비활성 사서함 복구를 Office 365.](recover-an-inactive-mailbox.md)

[비활성](#more-information) 사서함 복원 및 복구 간의 차이점에 대한 자세한 내용은 이 문서의 추가 정보 섹션을 참조하세요.

> [!NOTE]
> 자동 확장 보관함으로 구성된 비활성 사서함은 복구하거나 복원할 수 없습니다. 자동 확장 보관함이 있는 비활성 사서함에서 데이터를 복구해야 하는 경우 콘텐츠 검색을 사용하여 사서함에서 데이터를 내보낼 수 있으며 다른 사서함으로 가져올 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.
>
> - [콘텐츠 검색](content-search.md)
> - [콘텐츠 검색 결과 내보내기](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>비활성 사서함 복원 요구 사항

- 비활성 사서함을 복원 Exchange Online PowerShell을 사용 하 고 있습니다. EAC(Exchange 관리 센터)는 사용할 수 없습니다. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.

- PowerShell에서 Exchange Online 명령을 실행하여 조직의 비활성 사서함에 대한 ID 정보를 얻습니다.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  이 명령에서 반환된 정보를 사용하여 특정 비활성 사서함을 복원합니다.

- 비활성 사서함에 대한 자세한 내용은 에서 [비활성 사서함을 Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="restore-inactive-mailboxes"></a>비활성 사서함 복원

SourceMailbox 및 _TargetMailbox_ 매개 변수와  함께 **New-MailboxRestoreRequest** cmdlet을 사용하여 비활성 사서함의 콘텐츠를 기존 사서함으로 복원합니다. 이 cmdlet 사용에 대한 자세한 내용은 [New-MailboxRestoreRequest 를 참조하세요.](/powershell/module/exchange/new-mailboxrestorerequest)

1. 비활성 사서함의 속성을 포함하는 변수를 만들 수 있습니다.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 이전 명령에서 **DistinguishedName** 또는 **ExchangeGUID** 속성 값을 사용하여 비활성 사서함을 식별합니다. 이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 비활성 사서함의 기본 SMTP 주소가 같을 수 있습니다.

2. 비활성 사서함의 내용을 기존 사서함으로 복원합니다. 비활성 사서함(원본 사서함)의 콘텐츠는 기존 사서함(대상 사서함)의 해당 폴더에 병합됩니다.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   또는 대상 사서함에서 비활성 사서함의 콘텐츠를 복원할 최상위 폴더를 지정할 수 있습니다. 지정한 대상 폴더 또는 대상 폴더 구조가 대상 사서함에 아직 없는 경우 복원 프로세스 중에 만들어집니다.

   이 예에서는 비활성 사서함의 사서함 항목 및 하위 폴더를 대상 사서함의 최상위 폴더 구조에 있는 "비활성 사서함"이라는 폴더에 복사합니다.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>비활성 사서함에서 보관함 복원

비활성 사서함에 보관 사서함이 있는 경우 기존 사서함의 보관 사서함으로 복원할 수도 있습니다. 비활성 사서함에서 보관 파일을 복원하기 위해 비활성 사서함을 복원하는 데 사용되는 명령에 _SourceIsArchive_ 및 _TargetIsArchive_ 스위치를 추가해야 합니다.

1. 비활성 사서함의 속성을 포함하는 변수를 만들 수 있습니다.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > 이전 명령에서 **DistinguishedName** 또는 **ExchangeGUID** 속성 값을 사용하여 비활성 사서함을 식별합니다. 이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 비활성 사서함의 기본 SMTP 주소가 같을 수 있습니다.

2. 비활성 사서함(원본 보관함)에서 기존 사서함의 보관함(대상 보관함)으로 보관함의 콘텐츠를 복원합니다. 이 예에서는 원본 보관함의 내용이 대상 사서함의 보관함에 있는 "비활성 사서함 보관함"이라는 폴더에 복사됩니다.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>추가 정보

- **비활성 사서함 복구 및 복원의 주요 차이점은 무엇입니까?** 비활성 사서함을 복구하면 기본적으로 사서함이 새 사서함으로 변환되고, 비활성 사서함의 콘텐츠와 폴더 구조가 보존되고, 사서함이 새 사용자 계정에 연결됩니다. 복구된 비활성 사서함은 더 이상 존재하지 않습니다. 새 사서함의 콘텐츠에 대한 변경 내용은 원래 비활성 사서함에 보류된 콘텐츠에 영향을 미치게 됩니다. 반대로 비활성 사서함을 복원할 때 콘텐츠는 다른 사서함으로만 복사됩니다. 비활성 사서함은 보존되고 비활성 사서함으로 유지됩니다. 대상 사서함의 콘텐츠에 대한 변경 내용은 비활성 사서함에 있는 원래 콘텐츠에 영향을 주지 않습니다. 비활성 사서함은 콘텐츠 검색 도구를 [](content-search.md)사용하여 계속 검색할 수 있습니다. 해당 콘텐츠를 다른 사서함으로 복원하거나 나중에 복구하거나 삭제할 수 있습니다.

- **비활성 사서함은 어떻게 찾을 수 있나요?** 조직의 비활성 사서함 목록을 표시하고 비활성 사서함을 복원하는 데 유용한 정보를 표시하기 위해 이 명령을 실행하면 됩니다.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **소송 보존 또는 Microsoft 365 정책을 사용하여 비활성 사서함 콘텐츠를 보존합니다.** 비활성 사서함이 복원된 후 상태를 유지하려는 경우 대상 사서함을 소송 [](create-a-litigation-hold.md) 보존 상태로 설정하거나 비활성 사서함을 복원하기 전에 Microsoft 365 보존 정책을 적용할 수 있습니다. [](retention.md) 이렇게 하면 비활성 사서함의 항목이 대상 사서함으로 복원된 후 항목이 영구적으로 삭제되지 않습니다.

- **비활성 사서함을 복원하기 전에 대상 사서함에 대한 보존을 사용하도록 설정** 비활성 사서함의 사서함 항목은 오래 될 수 있으므로 비활성 사서함을 복원 하기 전에 대상 사서함에 대 한 보존을 사용 하도록 설정 하는 것이 고려할 수 있습니다. 사서함을 보존으로 설정하면 사서함에 할당된 보존 정책은 보존 보존이 제거되거나 보존 기간이 만료될 때까지 처리되지 않습니다. 이렇게 하면 대상 사서함의 소유자가 비활성 사서함의 이전 메시지를 관리할 수 있습니다. 그렇지 않은 경우 보존 정책은 대상 사서함에 대해 구성된 보존 설정에 따라 만료된 오래된 항목을 삭제하거나 보관 사서함으로 항목을 이동할 수 있습니다. 자세한 내용은 [Place a mailbox on retention hold in Exchange Online.](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)

- **AllowLegacyDNMismatch 스위치는 어떤 작업을 하나요?** 비활성 사서함을 복원하기 위한 이전 예에서는 **AllowLegacyDNMismatch** 스위치를 사용하여 비활성 사서함을 다른 대상 사서함으로 복원할 수 있습니다. 일반적인 복원 시나리오에서 목표는 원본 사서함과 대상 사서함이 동일한 사서함인 콘텐츠를 복원하는 것입니다. 따라서 **기본적으로 New-MailboxRestoreRequest** cmdlet은 원본 및 대상 사서함의 **LegacyExchangeDN** 속성 값이 동일한지 검사합니다. 이렇게 하면 원본 사서함을 잘못된 대상 사서함으로 실수로 복원하는 것을 방지할 수 있습니다. **AllowLegacyDNMismatch** 스위치를 사용하지 않고 비활성 사서함을 복원하려고 하면 원본 사서함과 대상 사서함의 **LegacyExchangeDN** 속성 값이 다른 경우 명령이 실패할 수 있습니다.

- **cmdlet과 함께 다른 매개 변수를 New-MailboxRestoreRequest 비활성 사서함에 대해 다른 복원 시나리오를 구현할 수 있습니다.** 예를 들어 이 명령을 실행하여 비활성 사서함의 보관 파일을 대상 사서함의 기본 사서함으로 복원할 수 있습니다.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  이 명령을 실행하여 비활성 기본 사서함을 대상 사서함의 보관함으로 복원할 수도 있습니다.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **TargetRootFolder 매개 변수는 어떤 작업을 하나요?** 앞서 설명한 것 처럼 **TargetRootFolder** 매개 변수를 사용하여 비활성 사서함의 콘텐츠를 복원할 대상 사서함의 폴더 구조 맨 위에 폴더(루트라고도함)를 지정할 수 있습니다. 이 매개 변수를 사용하지 않는 경우 비활성 사서함의 사서함 항목이 대상 사서함의 해당 기본 폴더에 병합되어 사용자 지정 폴더가 대상 사서함의 루트에 다시 만들어집니다. 다음 그림에서는 **TargetRootFolder** 매개 변수를 사용하지 않는 경우와 사용하지 않는 것 간의 이러한 차이점을 강조합니다.

  **TargetRootFolder 매개 변수가 사용되지 않는 경우 대상 사서함의 폴더 계층 구조**

  ![TargetRootFolder 매개 변수를 사용 하지 않는 경우 스크린샷.](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **TargetRootFolder 매개 변수를 사용하는 경우 대상 사서함의 폴더 계층 구조**

  ![TargetRootFolder 매개 변수를 사용하는 경우의 스크린샷입니다.](../media/300da592-7323-48db-b8a4-07012259d113.png)
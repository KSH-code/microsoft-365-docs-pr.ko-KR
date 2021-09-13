---
title: 비활성 사서함 복구
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: 비활성 사서함의 콘텐츠를 포함하는 새 사서함으로 변환하여 Office 365 사서함의 콘텐츠를 복구하는 방법을 학습합니다.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185996"
---
# <a name="recover-an-inactive-mailbox"></a>비활성 사서함 복구

비활성 사서함(소프트 삭제된 사서함의 한 유형)은 퇴사한 후 이전 직원의 전자 메일을 보존하는 데 사용됩니다. 해당 직원이 조직으로 돌아오거나 다른 직원이 이전 직원의 직무를 수락하는 경우 다음 두 가지 방법으로 사용자가 비활성 사서함의 콘텐츠를 사용할 수 있습니다.

- **비활성 사서함을 복구합니다.** 이전 직원이 조직으로 돌아오거나 이전 직원의 직무를 위해 신입 사원을 고용한 경우 비활성 사서함의 내용을 복구할 수 있습니다. 이 메서드는 비활성 사서함을 비활성 사서함의 내용이 포함된 새 활성 사서함으로 변환합니다. 복구한 후 비활성 사서함 존재 하지 않습니다. 이 항목의 절차에서는 이 메서드에 대해 설명합니다.

- **비활성 사서함을 복원합니다.** 다른 직원이 이전 직원의 직무를 대신하거나 다른 사용자가 비활성 사서함의 콘텐츠에 액세스해야 하는 경우 비활성 사서함의 내용을 기존 사서함에 복원하거나 병합할 수 있습니다. 비활성 사서함에서 보관 파일을 복원할 수도 있습니다. 이 방법의 절차는 [에서 비활성 사서함 복원을 Office 365.](restore-an-inactive-mailbox.md)

[비활성](#more-information) 사서함 복구 및 복원 간의 차이점에 대한 자세한 내용과 비활성 사서함이 복구될 때 발생하는 일에 대한 설명은 추가 정보 섹션을 참조하세요.

> [!NOTE]
> 자동 확장 보관함으로 구성된 비활성 사서함은 복구하거나 복원할 수 없습니다. 자동 확장 보관함이 있는 비활성 사서함에서 데이터를 복구해야 하는 경우 콘텐츠 검색을 사용하여 사서함에서 데이터를 내보낼 수 있으며 다른 사서함으로 가져올 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.
>
> - [콘텐츠 검색](content-search.md)
> - [콘텐츠 검색 결과 내보내기](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>비활성 사서함을 복구하기 위해 필요한 요구 사항

- 비활성 사서함을 Exchange Online PowerShell을 사용하여 복구해야 합니다. EAC(Exchange 관리 센터)는 사용할 수 없습니다. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.

- 다음 명령을 실행하여 조직의 비활성 사서함에 대한 ID 정보를 얻습니다.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  이 명령에서 반환된 정보를 사용하여 특정 비활성 사서함을 복구합니다.

## <a name="recover-inactive-mailboxes"></a>비활성 사서함 복구

*InactiveMailbox* 매개 변수와 함께 **New-Mailbox** cmdlet을 사용하여 비활성 사서함을 복구합니다.

1. 비활성 사서함의 속성을 포함하는 변수를 만들 수 있습니다.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 이전 명령에서 **DistinguishedName** 또는 **ExchangeGUID** 속성 값을 사용하여 비활성 사서함을 식별합니다. 이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 비활성 사서함의 기본 SMTP 주소가 같을 수 있습니다.

2. 이 예에서는 이전 명령에서 얻은 속성을 사용하여 비활성 사서함을 사용자 Ann Beebe의 활성 사서함으로 복구합니다. *Name* 및 *MicrosoftOnlineServicesID* 매개 변수에 지정된 값은 조직 내에서 고유해야 합니다.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   복구된 비활성 사서함의 기본 SMTP 주소는  *MicrosoftOnlineServicesID*  매개 변수에 지정된 값과 동일합니다.

비활성 사서함을 복구한 후 새 사용자 계정도 만들어집니다. 라이선스를 할당하여 이 사용자 계정을 활성화해야 합니다. 에서 라이선스를 할당 Microsoft 365 관리 센터 사용자 추가 및 동시에 라이선스 [할당을 참조합니다.](../admin/add-users/add-users.md)

## <a name="more-information"></a>추가 정보

- **비활성 사서함 복구 및 복원의 주요 차이점은 무엇입니까?** 비활성 사서함을 복구 하는 경우 사서함 새 사서함으로 변환 됩니다 내용과 비활성 사서함의 폴더 구조 유지 되므로 및 사서함을 새 사용자 계정에 연결 됩니다. 복구된 비활성 사서함은 더 이상 존재하지 않습니다. 새 사서함의 콘텐츠에 대한 변경 내용은 원래 비활성 사서함에 보류된 콘텐츠에 영향을 미치게 됩니다. 반대로 비활성 사서함을 복원할 때 콘텐츠는 다른 사서함으로만 복사됩니다. 비활성 사서함은 보존되고 비활성 사서함으로 유지됩니다. 대상 사서함의 콘텐츠에 대한 변경 내용은 비활성 사서함에 있는 원래 콘텐츠에 영향을 주지 않습니다. 비활성 사서함은 eDiscovery를 사용하여 In-Place, 해당 콘텐츠를 다른 사서함으로 복원하거나 나중에 복구하거나 삭제할 수 있습니다.

- **비활성 사서함을 복구하면 어떻게 되나요?** 비활성 사서함을 복구하면 다음과 같은 상황이 발생합니다.

  - 비활성 사서함에 적용된 보류는 복구되기 전에 비활성 사서함에 적용된 보류 유형에 따라 변경되거나 제거됩니다.

    - **소송 보유.** 비활성 사서함에 대해 소송 보류를 사용하도록 설정한 경우 복구된 사서함에서 제거됩니다.

    - **In-Place Hold** In-Place 사서함에서 제거됩니다. 즉, 복구된 사서함이 모든 eDiscovery 검색에서 원본 In-Place In-Place 제거됩니다.

    - **Microsoft 365 잠금을 통해 보존 정책을 적용합니다.** 비활성 사서함이 보존 정책에 할당된 경우(잠긴 보존 정책이라고도 함) 복구된 사서함은 동일한 잠긴 보존 정책에 할당됩니다. 잠긴 보존 정책에 대한 자세한 내용은 [보존 잠금을 사용하여 보존 정책 및 보존 레이블 정책 변경 제한)을[참조하세요.](retention-preservation-lock.md)

    - **Microsoft 365 잠금이 없는 보존 정책을 적용합니다.** 비활성 사서함은 비활성 사서함에 적용된 Microsoft 365 해제된 사서함에서 제거됩니다. 그러나 특정 보존 기간보다 오래된 콘텐츠를 삭제하는 조직 전체 보존 정책에 따라 사서함 콘텐츠가 삭제되지 않도록 복구된 사서함에서 소송 보존을 사용하도록 설정합니다. 소송 보류를 유지하거나 제거할 수 있습니다. 자세한 내용은 [Create a Litigation Hold를 참조하십시오.](create-a-litigation-hold.md)

  - 단일 항목 복구 **기간(RetainDeletedItemsFor** 사서함 속성으로 정의)은 30일로 설정됩니다. 일반적으로 새 사서함이 Exchange Online 이 보존 기간은 14일로 설정됩니다. 이 값을 최대값 30일로 설정하면 비활성 사서함에서 영구적으로 삭제(또는 제거)된 데이터를 복구할 수 있는 시간이 더 많이 있습니다. 단일 항목 복구를 사용하지 않도록 설정하거나 단일 항목 복구 기간을 기본값인 14일로 다시 설정할 수도 있습니다. 자세한 내용은 [사서함에 대한 단일 항목을 사용하거나 사용하지 않도록 설정](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)을 참조하세요.

  - 보존을 사용하도록 설정하고 보존 기간을 30일로 설정합니다. 즉, 기본 Exchange 보존 정책과 새 사서함에 할당된 조직 전체 또는 Exchange Microsoft 365 전체 보존 정책은 30일 동안 처리되지 않습니다. 이렇게 하면 복구된 비활성 사서함의 반환된 직원 또는 새 소유자가 이전 메시지를 관리할 수 있습니다. 그렇지 않으면 Exchange 또는 Microsoft 365 보존 정책에서 보존 정책에 대해 구성된 설정에 따라 만료된 오래된 사서함 항목을 삭제하거나 보관 사서함으로 항목을 이동할 수 Exchange Microsoft 365 있습니다. 30일이 경과하면 보존 보존이 만료되고 **RetentionHoldEnabled** 사서함 속성이 **False로** 설정되고 관리되는 폴더 도우미가 사서함에 할당된 정책 처리를 시작합니다. 이 추가 시간이 필요하지 않은 경우 보존 보존을 제거할 수 있습니다. 또는 **Set-Mailbox -EndDateForRetentionHold** 명령을 사용하여 보존 기간을 늘일 수 있습니다. 자세한 내용은 [Place a mailbox on retention hold을 참조하십시오.](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)

- **비활성 사서함의 원래 상태를 유지해야 하는 경우 복구된 사서함을 보류합니다.** 새 사서함 소유자 또는 보존 정책이 복구된 비활성 사서함에서 메시지를 영구적으로 삭제하지 못하게 방지하기 위해 사서함을 소송 보존으로 설정하면 됩니다. 자세한 내용은 [Create a Litigation Hold를 참조하십시오.](./create-a-litigation-hold.md)

- **비활성 사서함을 복구할 때 사용할 수 있는 사용자 ID는 무엇입니까?** 비활성 사서함을 복구할 때  *MicrosoftOnlineServicesID*  매개 변수에 대해 지정하는 값은 비활성 사서함과 연결된 원래 값과 다를 수 있습니다. 또한 원래 사용자 ID를 사용할 수 있습니다. 그러나 앞서 설명한 것 처럼,  *비활성*  사서함을 복구할 때 Name 및  *MicrosoftOnlineServicesID에*  사용되는 값이 조직 내에서 고유해야 합니다.

- **비활성 사서함에 대한 사서함 보존 기간이 만료되지 않은 경우 어떻게 하나요?** 비활성 사서함이 30일 전에 소프트 삭제된 경우 **New-Mailbox -InactiveMailbox** 명령을 사용하여 복구할 수 없습니다. 해당 사용자 계정을 복원하여 복구해야 합니다. 자세한 내용은 [조직에서 사용자 삭제를 참조하세요.](../admin/add-users/delete-a-user.md)

- **비활성 사서함에 대한 소프트 삭제된 사서함 보존 기간이 만료된 경우 어떻게 알 수 있나요?** 다음 명령을 실행합니다.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  **ExternalDirectoryObjectId** 속성 값이 없는 경우 사서함 보존 기간이 만료되고 **New-Mailbox -InactiveMailbox** 명령을 실행하여 비활성 사서함을 복구할 수 있습니다. **ExternalDirectoryObjectId** 속성 값이 있는 경우 소프트 삭제된 사서함 보존 기간이 만료되지 않은 것이고 사용자 계정을 복원하여 사서함을 복구해야 합니다. [조직에서 사용자 삭제](../admin/add-users/delete-a-user.md)를 참조합니다.

- **비활성 사서함을 복구한 후 보관 사서함을 사용하도록 설정하는 것이 있습니다.** 이렇게 하면 반환된 사용자 또는 새 직원이 이전 메시지를 보관 사서함으로 이동할 수 있습니다. 또한 보존 보존이 만료되면 Exchange 사서함에 할당된 기본 Exchange Online 보존 정책의 일부인 보관 정책은 2년 이상 된 항목을 보관 사서함으로 이동합니다. 보관 사서함을 사용하도록 설정하지 않은 경우 2년이 지난 항목은 사용자의 기본 사서함에 남아 있습니다. 자세한 내용은 보관 사서함 [사용 을 참조하세요.](enable-archive-mailboxes.md)
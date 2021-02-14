---
title: Exchange online에서 In-Place 사서함을 보류
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: 비활성으로 만들고 콘텐츠를 보존하기 위해 In-Place 사서함에 대한 보류를 만드는 방법을 알아보겠습니다.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818867"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Exchange online에서 In-Place 사서함을 보류

비활성으로 만들고 콘텐츠를 보존하기 위해 In-Place 사서함에 대한 보류를 만드는 방법을 알아보겠습니다. 그런 다음 Microsoft eDiscovery 도구를 사용하여 비활성 사서함을 검색할 수 있습니다.

> [!IMPORTANT]
> 사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 EAC(Exchange 관리 센터)에서 In-Place 보류의 사용 중지를 발표하고 있습니다. 2020년 7월 1일부터는 Exchange Online에서 새 보류 In-Place 수 없습니다. 그러나 EAC에서 또는 Exchange Online PowerShell에서 **Set-MailboxSearch** cmdlet을 사용하여 In-Place 보류를 관리할 수 있습니다. 그러나 2020년 10월 1일부터는 보류를 관리할 In-Place 없습니다. EAC에서 또는 **Remove-MailboxSearch** cmdlet을 사용하여 제거해야 합니다. 보류의 사용 중지에 대한 In-Place 내용은 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.
  
사용자가 조직을 떠났고 해당 사용자 계정 및 사서함이 삭제된 상황이 있을 수 있습니다. 그런 다음 사서함에 보존해야 하는 정보가 있습니다. 어떻게 해야 하나요? 삭제된 사서함 보존 기간이 만료되지 않은 경우 In-Place 보류를 삭제된 사서함(소프트 삭제된 사서함)에 저장하고 비활성 사서함으로 만들 수 있습니다. *비활성 사서함은* 퇴사한 후 이전 직원의 전자 메일을 보존하는 데 사용됩니다. 비활성 사서함의 콘텐츠는 비활성 상태일 때 In-Place 사서함에 배치된 보존 기간 동안 보존됩니다. 사서함이 비활성으로 설정된 후 Exchange Online의 In-Place eDiscovery &, 보안 및 준수 센터의 콘텐츠 검색 또는 SharePoint Online의 eDiscovery 센터를 사용하여 사서함을 검색할 수 있습니다. 
  
> [!NOTE]
> Exchange Online에서 소프트 삭제된 사서함은 삭제되지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다. Exchange Online의 사서함 보존 기간은 30일입니다. 즉, 삭제 후 30일 이내에 사서함을 복구하거나 비활성 사서함으로 만들 수 있습니다. 30일이 지난 후 소프트 삭제된 사서함은 영구 삭제로 표시되고 복구되거나 비활성 상태일 수 없습니다. 
  
## <a name="requirements-for-in-place-holds"></a>보류 In-Place 요구 사항

- 사서함을 소프트 삭제된 사서함에 Windows PowerShell In-Place **New-MailboxSearch** cmdlet을 사용해야 합니다. SharePoint Online에서는 EAC(Exchange 관리 센터) 또는 eDiscovery 센터를 사용할 수 없습니다. 

- Windows PowerShell을 사용하여 Exchange Online에 연결하는 방법에 대한 자세한 내용은 [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.

- 다음 명령을 실행하여 조직에서 소프트 삭제된 사서함에 대한 ID 정보를 얻습니다. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 비활성 사서함에 대한 자세한 내용은 [Office 365의 비활성 사서함 개요를 참조하세요.](inactive-mailboxes-in-office-365.md)

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>사서함을 In-Place 사서함을 비활성 사서함으로 만들기 위해 보류

**New-MailboxSearch** cmdlet을 사용하여 소프트 삭제된 사서함을 비활성 사서함으로 만들 수 있습니다. 자세한 내용은 [New-MailboxSearch를 참조하십시오.](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)
  
1. 소프트 삭제된 사서함의 속성을 포함하는 변수를 만들 수 있습니다.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 이전 명령에서 **DistinguishedName** 또는 **ExchangeGuid** 속성 값을 사용하여 소프트 삭제된 사서함을 식별합니다. 이러한 속성은 조직의 각 사서함에 대해 고유하며 활성 사서함과 소프트 삭제된 사서함의 기본 SMTP 주소가 같을 수 있습니다. 
  
2. 사서함을 In-Place 사서함에 저장합니다. 이 예에서는 보류 기간을 지정하지 않습니다. 즉, 항목이 무기한으로 또는 비활성 사서함에서 보류가 제거될 때까지 보류됩니다.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   보류를 만들 때 보류 기간을 In-Place 있습니다. 이 예에서는 비활성 사서함의 항목을 약 7년 동안 보유합니다.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 잠시 후 다음 명령 중 하나를 실행하여 소프트 삭제된 사서함이 비활성 사서함인지 확인할 수 있습니다.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    또는
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>추가 정보

소프트 삭제된 사서함을 비활성 사서함으로 만들면 여러 가지 방법으로 사서함을 관리할 수 있습니다. 자세한 내용은 다음을 참조하세요.
  
- [비활성 사서함의 유지 보존 기간 변경](change-the-hold-duration-for-an-inactive-mailbox.md)

- [비활성 사서함 복구](recover-an-inactive-mailbox.md)

- [비활성 사서함 복원](restore-an-inactive-mailbox.md)

- [비활성 사서함](delete-an-inactive-mailbox.md) 삭제(보류 제거)

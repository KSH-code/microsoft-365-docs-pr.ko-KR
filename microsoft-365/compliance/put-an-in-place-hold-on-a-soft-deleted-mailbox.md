---
title: Exchange Online에서 일시 삭제 된 사서함에 원본 위치 유지
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
description: 일시 삭제 된 사서함의 원본 위치 유지를 사용 하 여 비활성 상태로 만들고 해당 콘텐츠를 보존 하는 방법을 알아봅니다.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818867"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Exchange Online에서 일시 삭제 된 사서함에 원본 위치 유지

일시 삭제 된 사서함의 원본 위치 유지를 사용 하 여 비활성 상태로 만들고 해당 콘텐츠를 보존 하는 방법을 알아봅니다. 그런 다음 Microsoft eDiscovery 도구를 사용 하 여 비활성 사서함을 검색할 수 있습니다.

> [!IMPORTANT]
> 계속 해 서 사서함 콘텐츠를 보존 하는 다양 한 방법을 사용할 때 EAC (Exchange 관리 센터)에서 원본 위치 유지의 만료를 알리는 것입니다. 2020 년 7 월 1 일부 터 시작 Exchange Online에 새로운 현재 위치 유지를 만들 수 없습니다. 그러나 여전히 EAC에서 원본 위치 유지를 관리할 수 있으며 Exchange Online PowerShell에서 **new-mailboxsearch** cmdlet을 사용할 수도 있습니다. 그러나 2020 년 10 월 1 일부 터 시작 하는 경우 원본 위치 유지를 관리할 수 없게 됩니다. EAC에서 또는 **new-mailboxsearch** cmdlet을 사용 하 여 제거 하면 됩니다. 원본 위치 유지의 만료에 대 한 자세한 내용은 [레거시 eDiscovery 도구의 만료](legacy-ediscovery-retirement.md)를 참조 하세요.
  
사용자가 조직을 떠난 경우와 해당 사용자 계정 및 사서함이 삭제 된 상황이 있을 수 있습니다. 나중에 사서함에 보존 해야 하는 정보가 있음을 알게 됩니다. 어떤 작업을 수행 해야 하나요? 삭제 된 사서함 보존 기간이 만료 되지 않은 경우에는 삭제 된 사서함 (일시 삭제 된 사서함 이라고 함)에 원본 위치 유지를 설정 하 고 비활성 사서함으로 설정할 수 있습니다. *비활성 사서함* 은 조직에서 이전 직원의 전자 메일을 보존 하는 데 사용 됩니다. 비활성 사서함의 콘텐츠는 비활성 상태로 설정 되었을 때 일시 삭제 된 사서함에 있던 원본 위치 유지 기간 동안 보존 됩니다. 사서함을 비활성화 한 후에는 Exchange Online의 원본 위치 eDiscovery, 보안 & 준수 센터의 콘텐츠 검색 또는 SharePoint Online의 eDiscovery Center를 사용 하 여 사서함을 검색할 수 있습니다. 
  
> [!NOTE]
> Exchange Online에서 일시 삭제 된 사서함은 삭제 되었지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다. Exchange Online의 일시 삭제 된 사서함 보존 기간은 30 일입니다. 즉, 삭제 된 30 일 이내에 사서함을 복구 하거나 비활성 사서함을 만들 수 있습니다. 30 일이 지나면 일시 삭제 된 사서함은 영구적으로 삭제 되도록 표시 되며 복구 하거나 비활성 상태로 설정할 수 없습니다. 
  
## <a name="requirements-for-in-place-holds"></a>원본 위치 유지에 대 한 요구 사항

- Windows PowerShell에서 **new-mailboxsearch** cmdlet을 사용 하 여 일시 삭제 된 사서함을 원본 위치 유지 상태로 설정 해야 합니다. SharePoint Online의 EAC (Exchange 관리 센터) 또는 eDiscovery 센터를 사용할 수 없습니다. 

- Windows PowerShell을 사용하여 Exchange Online에 연결하는 방법에 대한 자세한 내용은 [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조하세요.

- 다음 명령을 실행 하 여 조직의 일시 삭제 된 사서함에 대 한 id 정보를 가져옵니다. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 비활성 사서함에 대 한 자세한 내용은 [Overview In Office 365의 비활성 사서함 개요](inactive-mailboxes-in-office-365.md)를 참조 하세요.

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>일시 삭제 된 사서함에 원본 위치 유지를 적용 하 여 비활성 사서함으로 설정

**New-mailboxsearch** cmdlet을 사용 하 여 일시 삭제 된 사서함을 비활성 사서함으로 만들 수 있습니다. 자세한 내용은 [new-mailboxsearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)를 참조 하십시오.
  
1. 일시 삭제 된 사서함의 속성이 포함 된 변수를 만듭니다.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 이전 명령에서 **DistinguishedName** 또는 **ExchangeGuid** 속성 값을 사용 하 여 일시 삭제 된 사서함을 식별 합니다. 이러한 속성은 조직의 각 사서함에 대해 고유 하지만 활성 사서함과 일시 삭제 된 사서함의 기본 SMTP 주소가 같을 수 있습니다. 
  
2. 원본 위치 유지를 만들고 일시 삭제 된 사서함에 배치 합니다. 이 예에서는 보존 기간을 지정 하지 않습니다. 즉, 항목이 무기한으로 또는 비활성 사서함에서 제거 될 때까지 유지 됩니다.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   원본 위치 유지를 만들 때 보존 기간을 지정할 수도 있습니다. 이 예에서는 약 7 년 동안 비활성 사서함의 항목을 포함 합니다.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 잠시 후에 다음 명령 중 하나를 실행 하 여 일시 삭제 된 사서함이 비활성 사서함 인지 확인 합니다.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    또는
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>추가 정보

일시 삭제 된 사서함을 비활성 사서함으로 설정한 후 사서함을 관리 하는 방법에는 여러 가지가 있습니다. 자세한 내용은 다음을 참조하세요.
  
- [비활성 사서함의 유지 보존 기간 변경](change-the-hold-duration-for-an-inactive-mailbox.md)

- [비활성 사서함 복구](recover-an-inactive-mailbox.md)

- [비활성 사서함 복원](restore-an-inactive-mailbox.md)

- [비활성 사서함 삭제](delete-an-inactive-mailbox.md) (보존 제거)

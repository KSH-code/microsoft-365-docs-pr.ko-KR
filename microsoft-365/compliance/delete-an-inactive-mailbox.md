---
title: 비활성 사서함 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우 비활성 사서함을 영구적으로 삭제할 수 있습니다.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817897"
---
# <a name="delete-an-inactive-mailbox"></a>비활성 사서함 삭제

비활성 사서함은 직원이 퇴사한 후에 해당 전자 메일을 유지하는 데 사용됩니다. 비활성 사서함의 콘텐츠를 더 이상 보존할 필요가 없는 경우 비활성 사서함을 영구적으로 삭제할 수 있습니다. 또한 비활성 사서함에 여러 보류가 배치될 수 있습니다. 예를 들어 비활성 사서함은 소송 보류에 배치될 수 있으며 하나 이상의 사서함에 In-Place 있습니다. 또한 Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 만든 보존 정책이 비활성 사서함에 적용될 수 있습니다. 비활성 사서함에서 모든 보류 및 보존 정책을 제거하여 삭제해야 합니다. 보존 및 보존 정책을 제거한 후 비활성 사서함은 삭제로 표시되고 처리된 후 영구적으로 삭제됩니다.
  
> [!IMPORTANT]
> 사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 Exchange 관리 센터에서 In-Place 보존의 사용 중지를 발표하고 있습니다. 즉, 소송 보존 및 보존 정책을 사용하여 비활성 사서함을 만들어야 합니다. 2020년 7월 1일부터는 Exchange Online에서 새 보류 In-Place 수 없습니다. 하지만 여전히 비활성 사서함에 배치된 In-Place 보류 기간을 변경할 수 있습니다. 그러나 2020년 10월 1일부터는 보류 기간을 변경할 수 없습니다. 비활성 사서함은 비활성 사서함을 제거 하 In-Place 수 있습니다. 보류에 있는 In-Place 비활성 사서함은 보존이 제거될 때까지 계속 보존됩니다. 보류의 사용 중지에 대한 In-Place 내용은 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.
  
[비활성 사서함에서](#more-information) 보류를 제거한 후 발생하는 일에 대한 설명은 추가 정보 섹션을 참조하세요.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>비활성 사서함을 삭제하기 전에

- Exchange Online PowerShell을 사용하여 비활성 사서함에서 소송 보류를 제거해야 합니다. EAC(Exchange 관리 센터)는 사용할 수 없습니다. 단계별 지침은 [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/?linkid=396554)을 참조하십시오. Exchange Online PowerShell 또는 EAC를 사용하여 비활성 사서함에서 In-Place 보류를 제거할 수 있습니다. 
    
- 보류를 제거하고 비활성 사서함을 삭제하기 전에 비활성 사서함의 내용을 다른 사서함에 복사할 수 있습니다. 자세한 내용은 [Office 365에서 비활성 사서함 복원을 참조 합니다.](restore-an-inactive-mailbox.md)
    
- 비활성 사서함에서 보존 또는 보존 정책을 제거 하 고 사서함에 대 한 소프트 삭제 된 사서함 보존 기간이 만료 된 경우 사서함은 영구적으로 삭제 됩니다. 삭제한 후 복구할 수 없습니다. 보류를 제거하기 전에 사서함의 콘텐츠가 더 이상 필요하지 않습니다. 비활성 사서함을 다시 활성화 하려는 경우 복구할 수 있습니다. 자세한 내용은 [Office 365에서 비활성 사서함 복구를 참조 합니다.](recover-an-inactive-mailbox.md)
    
- 비활성 사서함에 대한 자세한 내용은 [Office 365의](inactive-mailboxes-in-office-365.md)비활성 사서함을 참조하세요.
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>1단계: 비활성 사서함에 대한 보류 식별

앞서 언급했듯이 소송 보존, In-Place 보존 또는 보존 정책이 비활성 사서함에 배치될 수 있습니다. 첫 번째 단계는 비활성 사서함에 대한 보류를 식별하는 것입니다.
  
다음 명령을 실행하여 조직의 모든 비활성 사서함에 대한 보류 정보를 표시합니다.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled** 속성의 **True** 값은 비활성 사서함이 소송 유지 상태임을 나타냅니다. 비활성 In-Place 보류의 GUID가 **InPlaceHolds** 속성 값으로 표시됩니다. 예를 들어 다음 두 개의 비활성 사서함에 대한 다음 결과는 Ann Beebe에 소송 유지가 설정되어 있으며 두 개의 In-Place 보류가 Pilar Pinilla에 배치된 것으로 나타날 수 있습니다. 
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 많은 In-Place 비활성 사서함에 배치되는 경우 모든 In-Place 보류 GUID가 표시되지는 않습니다. 다음 명령을 실행하여 모든 보류 GUID를 In-Place 수 있습니다.  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>2단계: 비활성 사서함에서 보류 제거

비활성 사서함에 배치되는 보류 유형과 여러 보류가 있는지 여부를 확인한 후 다음 단계는 사서함에 대한 보류를 제거하는 것입니다. 앞서 언급했듯이 비활성 사서함을 영구적으로 삭제하려면 모든 보류를 제거해야 합니다. 
  
### <a name="remove-a-litigation-hold"></a>소송 보류 제거

앞서 설명한 것 처럼 비활성 사서함에서 Windows PowerShell 소송 보류를 제거 하는 데 사용할 수 있습니다. EAC는 사용할 수 없습니다. 다음 명령을 실행하여 소송 보류를 제거합니다.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 비활성 사서함을 식별하는 가장 좋은 방법은 고유 이름 또는 Exchange GUID 값을 사용하는 것입니다. 이러한 값 중 하나를 사용하면 잘못된 사서함을 실수로 지정하는 것을 방지할 수 있습니다. 
  
### <a name="remove-in-place-holds"></a>원본 위치 보존 제거

 비활성 사서함에서 In-Place 보류를 제거하는 방법에는 다음 두 가지가 있습니다. 
  
- **Hold In-Place 삭제** 영구적으로 삭제하려는 비활성 사서함이 In-Place 보류의 유일한 원본 사서함인 경우 In-Place 수 있습니다. 
    
    > [!NOTE]
    > 보류 개체를 삭제하려면 먼저 보류를 In-Place 합니다. 보류가 설정된 In-Place 보류 개체를 삭제하려고 시도하면 오류 메시지가 표시됩니다. 
  
- **비활성** 사서함을 원본 사서함으로 In-Place 보류 In-Place 보류에 대한 다른 원본 사서함을 유지하려는 경우 원본 사서함 목록에서 비활성 사서함을 제거하고 In-Place 보류 개체를 유지할 수 있습니다. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>EAC를 사용하여 보류 In-Place 삭제

1. 삭제할 보류 In-Place 이름을 알고 있는 경우 다음 단계로 이동하면 됩니다. 그렇지 않은 경우 다음 명령을 실행하여 영구적으로 삭제할 In-Place 사서함에 있는 보류 상태의 이름을 얻습니다. 1단계In-Place 획득한 보류 GUID를 사용하여 비활성 사서함의 보류를 [식별합니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. EAC에서 준수 **관리** \> **In-Place eDiscovery &amp; 보류로 이동 합니다.**
    
3. 삭제할 In-Place 보류를 선택하고 편집  ![ 아이콘을 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.
    
4. **In-Place eDiscovery &amp; Hold** 속성 페이지에서 **In-Place Hold를** 클릭하고 보류 상자에서 선택한 사서함의 검색 쿼리와 일치하는 콘텐츠 저장을 선택하지 않은 다음 저장을 **클릭합니다.** 
    
5. **In-Place eDiscovery &amp; Hold** 페이지에서 In-Place 보류를 선택한 다음 삭제  ![ 아이콘을 ](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.
    
6. 경고에서 **예를** 클릭하여 보류 In-Place 삭제합니다. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Exchange Online PowerShell을 사용하여 보류 In-Place 삭제

1. 삭제할 보류 In-Place 포함하는 변수를 만드시다. 1단계In-Place 획득한 보류 GUID를 사용하여 비활성 사서함의 보류를 [식별합니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. 보류된 보류를 In-Place 해제합니다.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. 보류 In-Place 삭제합니다.
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>EAC를 사용하여 비활성 사서함을 In-Place 보류

1. 비활성 사서함에 배치된 In-Place 보류의 이름을 알고 있는 경우 다음 단계로 이동하면 됩니다. 그렇지 않은 경우 다음 명령을 실행하여 사서함에 In-Place 보류의 이름을 얻습니다. 1단계In-Place 획득한 보류 GUID를 사용하여 비활성 사서함의 보류를 [식별합니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. EAC에서 준수 **관리** \> **In-Place eDiscovery &amp; 보류로 이동 합니다.**
    
3. 비활성 In-Place 보류를 선택하고 편집 아이콘을  ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭합니다.
    
4. 원본 원본 **eDiscovery &amp; 보류** 속성 페이지에서 **원본을 클릭합니다.**
    
5. 원본 사서함 목록에서 제거할 비활성 사서함의 이름을 클릭한 다음 제거 아이콘을  ![ ](../media/adf01106-cc79-475c-8673-065371c1897b.gif) 클릭합니다.
    
6. **저장** 을 클릭하여 변경 내용을 저장합니다. 작업이 성공적으로 완료되었습니다는 메시지가 표시됩니다. 
    
7. 1-6단계를 반복하여 비활성 사서함에 In-Place 보류를 제거합니다.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Exchange Online PowerShell을 사용하여 비활성 사서함을 In-Place 보류

In-Place 사서함 수가 포함된 경우 비활성 사서함이 EAC의 원본 페이지에 나열되지 않는 것일 수 있습니다.  보류를 편집하면 원본 페이지에 최대 3,000개 In-Place 표시됩니다.  원본 페이지에 비활성 사서함이 목록에  없는 경우 Exchange Online PowerShell을 사용하여 비활성 사서함을 In-Place 수 있습니다. 
  
1. 비활성 사서함에 배치된 In-Place 속성이 포함된 변수를 만들 수 있습니다. 1단계In-Place 획득한 보류 GUID를 사용하여 비활성 사서함의 보류를 [식별합니다.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. 비활성 사서함이 비활성 사서함의 원본 사서함으로 In-Place 확인 합니다. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **참고:** In-Place Hold의 *Sources* 속성은 *LegacyExchangeDN* 속성으로 원본 사서함을 식별합니다. 이 속성은 비활성 사서함을 고유하게 식별하기 때문에 In-Place Hold의 *Sources* 속성을 사용하면 잘못된 사서함을 제거하는 것을 방지할 수 있습니다. 또한 두 사서함의 별칭 또는 SMTP 주소가 같은 경우 문제를 방지하는 데에도 도움이 됩니다. 
   
3. 변수의 원본 사서함 목록에서 비활성 사서함을 제거합니다. 이전 단계의 명령에 의해 반환된 비활성 사서함의 **LegacyExchangeDN을** 사용해야 합니다. 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    예를 들어 다음 명령은 Pilar Pinilla의 비활성 사서함을 제거합니다.
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. 비활성 사서함이 변수의 원본 사서함 목록에서 제거되어 있는지 확인해야 합니다.
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. 비활성 In-Place 사서함을 포함하지 않는 업데이트된 원본 사서함 목록으로 보류를 수정합니다.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. 비활성 사서함이 비활성 사서함의 원본 사서함 목록에서 In-Place 확인 합니다.
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>추가 정보

- **비활성 사서함은 소프트 삭제된 사서함의 유형입니다.** Exchange Online에서 소프트 삭제된 사서함은 삭제되지만 특정 보존 기간 내에 복구할 수 있는 사서함입니다. Exchange Online의 사서함 보존 기간은 30일입니다. 즉, 사서함을 소프트 삭제한 후 30일 이내에 복구할 수 있습니다. 30일이 지난 후 소프트 삭제된 사서함은 영구 삭제로 표시되고 복구할 수 없습니다. 
    
- **비활성 사서함에 대한 보류를 제거한 후 어떻게 하나요?** 사서함은 다른 소프트 삭제 사서함처럼 취급되고 30일의 소프트 삭제 사서함 보존 기간이 만료된 후 영구적으로 삭제된 것으로 표시됩니다. 이 보존 기간은 사서함이 처음 비활성화된 날짜에 시작됩니다. 이 날짜를 일시 삭제 날짜(해당 사용자 계정이 삭제된 날짜 또는 **Remove-Mailbox** cmdlet을 사용하여 Exchange Online 사서함이 삭제된 날짜)라고 합니다. 일시 삭제된 날짜는 보류를 제거하는 날짜가 아닌 경우 
    
- **비활성 사서함은 보류가 제거된 직후 영구적으로 삭제하나요?** 비활성 사서함에 대한 일시 삭제 날짜가 30일보다 오래된 경우 보류를 제거하는 즉시 사서함이 영구적으로 삭제되지 않습니다. 사서함은 영구 삭제로 표시되고 다음에 처리될 때 삭제됩니다. 
    
- **소프트 삭제된 사서함 보존 기간은 비활성 사서함에 어떤 영향을 미치나요?** 비활성 사서함에 대한 일시 삭제 날짜가 보류가 제거된 날짜보다 30일이 지난 경우 사서함은 영구 삭제로 표시됩니다. 그러나 비활성 사서함에 지난 30 일 내에 일시 삭제 된 날짜가 있는 하 고 보류를 제거 하는 경우 일시 삭제 된 사서함 보존 기간이 만료 될 때까지 사서함을 복구할 수 있습니다. 자세한 내용은 Exchange Online에서 사용자 사서함 삭제 또는 [복원을 참조하세요.](https://go.microsoft.com/fwlink/?linkid=856835) 소프트 삭제된 사서함 보존 기간이 만료되면 비활성 사서함을 복구하기 위한 절차를 따라야 합니다. 자세한 내용은 [Office 365에서 비활성 사서함 복구를 참조 합니다.](recover-an-inactive-mailbox.md)
    
- **보류가 제거된 후 비활성 사서함에 대한 정보를 표시하는 방법** 보류가 제거되고 비활성 사서함이 소프트 삭제된 사서함으로 되돌아가면 **Get-Mailbox** cmdlet과 *함께 InactiveMailboxOnly* 매개 변수를 사용하여 반환되지 않습니다. 그러나 **Get-Mailbox -SoftDeletedMailbox** 명령을 사용하여 사서함에 대한 정보를 표시할 수 있습니다. 예시: 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  위의 예제에서 *WhenSoftDeleted* 속성은 일시 삭제된 날짜(이 예제에서는 2014년 10월 30일)를 식별합니다. 이 소프트 삭제 사서함이 이전에 보류가 제거된 비활성 사서함이면 *WhenSoftDeleted* 속성 값 이후 30일 후에 영구적으로 삭제됩니다. 이 경우 사서함은 2014년 11월 30일 이후에 영구적으로 삭제됩니다.


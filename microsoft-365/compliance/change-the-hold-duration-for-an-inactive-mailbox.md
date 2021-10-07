---
title: 비활성 사서함의 보존 기간 변경
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 사서함이 비활성으로 설정된 후 비활성 사서함에 할당된 보존 Office 365 변경합니다.
ms.openlocfilehash: be7877e3087004e6b633e0967d72173fa83a3948
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170826"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>비활성 사서함의 보존 기간 변경

비활성 사서함은 퇴사한 후 이전 직원의 전자 메일을 보존하는 데 사용됩니다. 소송 보존, In-Place 보류, Microsoft 365 보존 정책 또는 eDiscovery 사례와 연결된 보류가 사서함에 배치되고 해당 사용자 계정이 삭제되면 사서함이 비활성화됩니다. 비활성 사서함의 콘텐츠는 비활성으로 설정되기 전에 사서함에 배치된 보존 기간 동안 보존됩니다. 보류 기간은 복구 가능한 항목 폴더의 항목을 보유하는 기간을 정의합니다. 복구 가능한 항목 폴더의 항목에 대한 보류 기간이 만료되면 항목이 비활성 사서함에서 영구적으로 삭제(제거)됩니다. 사서함을 비활성으로 설정한 후 비활성 사서함에 할당된 보존 Microsoft 365 기간을 변경할 수 있습니다.
  
> [!IMPORTANT]
> 사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 In-Place 관리 센터에서 보존 Exchange 발표하고 있습니다. 즉, 소송 보존을 사용하여 Microsoft 365 사서함을 만들어야 합니다. 2020년 4월 1일부터 새 보류를 만들 In-Place 수 Exchange Online. 그러나 비활성 사서함에 배치된 보류 In-Place 변경할 수 있습니다. 그러나 2020년 7월 1일부터는 보류 기간을 변경할 수 없습니다. 비활성 사서함은 비활성 사서함을 제거하여 비활성 사서함만 삭제할 In-Place 있습니다. 보류에 있는 In-Place 비활성 사서함은 보존이 제거될 때까지 계속 보존됩니다. 보류의 사용 중지에 대한 In-Place 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.
  
## <a name="connect-to-powershell"></a>커넥트 PowerShell로

- PowerShell을 사용하여 Exchange Online 사서함에 대한 소송 보류 기간을 변경해야 합니다. EAC(Exchange 관리 센터)는 사용할 수 없습니다. 그러나 PowerShell 또는 EAC를 사용하여 Exchange Online 보류 기간을 변경할 In-Place 있습니다. 보안 및 준수 센터 또는 보안 및 준수 센터 powerShell을 & 보존 정책의 보존 기간을 Microsoft 365 있습니다.
    
- PowerShell 또는 Exchange Online 보안 & PowerShell에 연결하기 위해 다음 항목 중 하나를 참조하세요.
    
  - [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)
    
- eDiscovery 사례와 연결된 보류는 무한 보류입니다. 즉, 변경할 수 있는 보류 기간이 없습니다. 항목은 영구적으로 또는 보류가 제거되고 비활성 사서함이 삭제될 때까지 유지됩니다.
    
- 비활성 사서함에 대한 자세한 내용은 에서 [비활성 사서함을 Microsoft 365.](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>1단계: 비활성 사서함에 대한 보류 식별

서로 다른 유형의 보류 또는 하나 이상의 Microsoft 365 보존 정책이 비활성 사서함에 배치될 수 있기 때문에 첫 번째 단계는 비활성 사서함의 보류를 식별하는 것입니다.
  
PowerShell에서 Exchange Online 명령을 실행하여 조직의 모든 비활성 사서함에 대한 보류 정보를 표시합니다.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

**LitigationHoldEnabled** 속성의 **True** 값은 비활성 사서함이 소송 보류 상태임을 나타냅니다. In-Place, eDiscovery 보류 또는 Microsoft 365 보존 정책이 비활성 사서함에 있는 경우 보류 또는 보존 정책의 GUID가 **InPlaceHolds** 속성 값으로 표시됩니다. 예를 들어 다음에서는 5개의 비활성 사서함에 대한 결과를 보여줍니다. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

다음 표에서는 각 사서함을 비활성화하는 데 사용된 5가지 보류 유형을 식별합니다.
  
|**비활성 사서함**|**보류 유형**|**비활성 사서함에 대한 보류를 식별하는 방법**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |소송 대기  <br/> |*LitigationHoldEnabled* 속성이 로 `True` 설정됩니다.  <br/> |
|Pilar Pinilla  <br/> |원본 위치 유지  <br/> |*InPlaceHolds* 속성에는 비활성 사서함에 In-Place Hold의 GUID가 포함되어 있습니다. ID가 In-Place 시작하지 않는 경우 보류라고 알 수 있습니다.  <br/> PowerShell에서 명령을 사용하여 Exchange Online 사서함의 보류 In-Place 정보를 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` 얻을 수 있습니다.  <br/> |
|Mario Necaise  <br/> |조직 전체의 Microsoft 365 보존 정책 Microsoft 365 규정 준수 센터  <br/> |*InPlaceHolds* 속성이 비어 있습니다. 이는 비활성 사서함에 하나 이상의 조직 전체 또는 (Exchange 전체) Microsoft 365 정책이 적용 것 입니다. 이 경우 PowerShell에서 명령을 Exchange Online 조직 전체의 보존 정책에 대한 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID Microsoft 365 있습니다. 사서함에 적용되는 조직 전체 보존 정책의 GUID는 Exchange(예: )로 `mbx` `mbxa3056bb15562480fadb46ce523ff7b02` 시작됩니다.  <br/> <br/>비활성 Microsoft 365 적용된 보존 정책을 ID로 설정하기 위해 Security & PowerShell에서 다음 명령을 실행합니다.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Microsoft 365 사서함에 Microsoft 365 규정 준수 센터 정책의 보존 정책  <br/> |*InPlaceHolds* 속성에는 비활성 사서함에 Microsoft 365 보존 정책의 GUID가 포함되어 있습니다. GUID는 prefix로 시작하기 때문에 특정 사서함에 적용되는 보존  `mbx` 정책입니다. 비활성 사서함에 적용된 보존 정책의 GUID가 prefix로 시작된 경우 보존 정책이 비즈니스용 Skype `skp` 나타냅니다.  <br/><br/> 비활성 Microsoft 365 적용된 보존 정책을 ID로 설정하기 위해 Security & PowerShell에서 다음 명령을 실행합니다.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>이 명령을 실행할 때 또는  `mbx`  `skp` prefix를 제거해야 합니다.  <br/> |
|Abraham McMahon  <br/> |eDiscovery 사례 보류 Microsoft 365 규정 준수 센터  <br/> |*InPlaceHolds* 속성에는 비활성 사서함에 배치된 eDiscovery 케이스 보류의 GUID가 포함되어 있습니다. GUID가 prefix로 시작하기 때문에 eDiscovery 케이스 보류라고 알  `UniH` 수 있습니다.  <br/> Security & Compliance Center PowerShell의 cmdlet을 사용하여 비활성 사서함의 보류가 연결된 eDiscovery 사례에 대한 정보를 얻을  `Get-CaseHoldPolicy` 수 있습니다. 예를 들어 명령을 실행하여 비활성 사서함에 있는 케이스 보류의 이름을  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 표시할 수 있습니다. 이 명령을 실행할 때 반드시  `UniH` prefix를 제거해야 합니다.  <br/><br/> 비활성 사서함의 보류가 연결된 eDiscovery 사례를 ID로 설정하기 위해 다음 명령을 실행합니다.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **참고:** 비활성 사서함에는 eDiscovery 보류를 사용하지 않는 것이 좋습니다. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. 특정 시점에 법률 사례가 종료되고 해당 사례와 연결된 보류가 제거되고 eDiscovery 사례가 닫히거나 삭제됩니다. 실제로 비활성 사서함에 배치된 보류가 eDiscovery 사례와 연결되어 있으며 보류가 릴리스되거나 eDiscovery 사례가 닫히거나 삭제되면 비활성 사서함이 영구적으로 삭제됩니다. 

보존 정책에 Microsoft 365 대한 자세한 내용은 보존 정책 및 보존 레이블에 대해 [자세히를 참조하세요.](retention.md)
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>2단계: 비활성 사서함의 보류 기간 변경

비활성 사서함에 배치되는 보류 유형과 보류가 여러 개 있는지 여부를 확인한 후 다음 단계는 보류 기간을 변경하는 것입니다. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>소송 보류 기간 변경

다음은 PowerShell을 사용하여 Exchange Online 사서함에 배치된 소송 보류의 보류 기간을 변경하는 방법입니다. EAC는 사용할 수 없습니다. 다음 명령을 실행하여 보류 기간을 변경합니다. 이 예에서는 보류 기간이 무제한 기간으로 변경됩니다.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

그 결과 비활성 사서함의 항목은 무기한 또는 보존이 제거되거나 보존 기간이 다른 값으로 변경될 때까지 보존됩니다.
  
> [!TIP]
> 비활성 사서함을 식별하는 가장 좋은  방법은 고유 이름 또는 **GUID** Exchange 사용하는 것입니다. 이러한 값 중 하나를 사용하면 잘못된 사서함을 실수로 지정하는 것을 방지할 수 있습니다. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>보류 기간 In-Place 변경

 In-Place 보류가 사용 중지되어 더 이상 수정할 수 없습니다. 비활성 사서함에 In-Place 적용 하는 경우 보류 기간을 변경할 수 없습니다. 비활성 사서함이 In-Place 보류만 제거할 수 있습니다. 자세한 내용은 비활성 사서함 [삭제를 참조하세요.](delete-an-inactive-mailbox.md#remove-in-place-holds)
  
## <a name="more-information"></a>추가 정보

- **비활성 사서함의 항목에 대한 보류 기간은 어떻게 계산되나요?** 기간은 사서함 항목을 받거나 만든 원래 날짜부터 계산됩니다. 
    
- **보류 기간이 만료되면 어떻게 됩니까?** 복구 가능한 항목 폴더의 사서함 항목에 대한 보류 기간이 만료되면 해당 항목이 비활성 사서함에서 영구적으로 삭제(제거)됩니다. 비활성 사서함에 배치된 보류에 대해 지정된 기간이 없는 경우 비활성 사서함의 보류 기간이 변경되지 않는 한 복구 가능한 항목 폴더의 항목은 제거되지 않습니다. 
    
- **비활성 Exchange 보존 정책이 여전히 처리하나요?** 비활성 상태일 때 Exchange 보존 정책(메시징 레코드 관리 또는 MRM, Exchange Online의 기능)이 사서함에 적용된 경우 삭제 정책(삭제 보존 작업으로  구성된 보존 태그)은 비활성 사서함에서 계속 처리됩니다. 즉, 삭제 정책으로 태그가 지정되는 항목은 보존 기간이 만료되면 복구 가능한 항목 폴더로 이동됩니다. 이러한 항목은 항목의 보류 기간이 만료되면 비활성 사서함에서 제거됩니다. 
    
    이와 반대로 비활성 사서함에 할당 된 보존 정책에 포함 된 모든 보관 정책 (인, **보관 폴더로 이동** 보존 작업을 사용 하 여 구성 하는 보존 태그)은 무시 됩니다. 즉, 보관 정책으로 태그가 지정되는 비활성 사서함의 항목은 보존 기간이 만료될 때 기본 사서함에 남아 있습니다. 보관 사서함으로 또는 보관 사서함의 복구 가능한 항목 폴더를 이동 하지는 합니다. 사용자가 비활성 사서함에 로그인할 수 없는 경우 데이터 센터 리소스를 사용하여 보관 정책을 처리해야 할 이유가 없습니다. 

- **소송 보류에 대한 새 보류 기간을 확인하기 위해 다음 명령을 실행합니다.** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **일반 사서함과 마찬가지로 MFA(관리되는 폴더 도우미)도 비활성 사서함을 처리합니다.** 이 Exchange Online MFA는 약 7일마다 한 번씩 사서함을 처리합니다. 비활성 사서함의 보류 기간을 변경한 후 **Start-ManagedFolderAssistant** cmdlet을 사용하여 비활성 사서함에 대한 새 보류 기간 처리를 즉시 시작할 수 있습니다. 다음 명령을 실행합니다. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **많은 보류가 비활성 사서함에 배치되는 경우 모든 보류 GUID가 표시되지 않습니다.** 다음 명령을 실행하여 비활성 사서함에 있는 모든 보류(소송 보류 제외)에 대한 GUID를 표시할 수 있습니다. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
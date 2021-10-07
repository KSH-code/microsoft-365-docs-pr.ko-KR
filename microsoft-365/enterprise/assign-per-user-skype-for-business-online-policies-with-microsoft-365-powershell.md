---
title: PowerShell을 비즈니스용 Skype 온라인 정책을 사용자 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: '요약: PowerShell을 사용하여 Microsoft 365 Online 정책을 사용하여 사용자 비즈니스용 Skype 할당합니다.'
ms.openlocfilehash: c49d465ffe0a6f1379681be0ae4faaf9982b6ef0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178950"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>PowerShell을 비즈니스용 Skype 온라인 정책을 사용자 Microsoft 365

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

PowerShell을 사용하여 Microsoft 365 온라인 정책을 사용하여 사용자당 통신 설정을 효율적으로 비즈니스용 Skype 있습니다.
  
## <a name="prepare-to-run-the-powershell-commands"></a>PowerShell 명령 실행 준비

다음 지침을 사용하여 명령을 실행하기 위한 설정(이미 완료한 단계 건너뛰기)을 수행합니다.
  
  > [!Note]
   > Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

1. [Teams PowerShell 모듈](/microsoftteams/teams-powershell-install)를 설치합니다.
    
2. Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행합니다. 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   메시지가 표시될 때 비즈니스용 Skype 계정 이름과 암호를 입력합니다.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>사용자 계정에 대한 외부 통신 설정 업데이트

사용자 계정에서 외부 통신 설정을 변경하려는 경우를 가정해 가정합니다. 예를 들어 Alex가 페더임 사용자와 통신할 수 있도록 허용할 수 있지만(EnableFederationAccess가 True와 같음) Windows Live 사용자와는 통신하지 않을 수 있습니다(EnablePublicCloudAccess는 False임). 이를 위해 다음 두 가지 작업을 해야 합니다.
  
1. 기준을 충족하는 외부 액세스 정책을 찾습니다.
    
2. 해당 외부 액세스 정책을 Alex에게 할당합니다.
    
Alex를 할당할 외부 액세스 정책을 결정하는 방법 다음 명령은 EnableFederationAccess가 True로 설정되고 EnablePublicCloudAccess가 False로 설정된 모든 외부 액세스 정책을 반환합니다.
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

ExternalAccessPolicy의 사용자 지정 인스턴스를 만들지 않은 경우 이 명령은 조건(FederationOnly)을 충족하는 정책 하나를 반환합니다. 예를 들면 다음과 같습니다.
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Alex에게 할당할 정책을 알고 있습니다. [이제 Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet을 사용하여 해당 정책을 할당할 수 있습니다. 예를 들면 다음과 같습니다.
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

정책을 할당하는 것은 매우 간단합니다. 단순히 사용자의 ID와 할당할 정책의 이름을 지정하면 됩니다. 
  
또한 정책 및 정책 할당과 관련되어 사용자 계정 작업을 한 번만 수행하도록 제한되지는 않습니다. 페더레이션 파트너 및 Windows Live 사용자와 통신할 수 있는 모든 사용자의 목록이 필요한 경우를 예로 들어 보겠습니다. 여기서 해당 사용자에게는 외부 사용자 액세스 정책 FederationAndPICDefault가 이미 할당되어 있습니다. 따라서 하나의 간단한 명령을 실행하여 모든 사용자 목록을 표시할 수 있습니다. 해당 명령은 다음과 같습니다.
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

이처럼 ExternalAccessPolicy 속성이 FederationAndPICDefault로 설정된 모든 사용자가 표시됩니다. 화면에 나타나는 정보의 양을 제한하기 위해 Select-Object cmdlet을 사용하여 각 사용자의 표시 이름만 표시합니다. 
  
모든 사용자 계정이 동일한 정책을 사용하도록 구성하기 위해 다음 명령을 사용 합니다.
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

이 명령은 Get-CsOnlineUser 사용하여 Lync를 사용하도록 설정된 모든 사용자 컬렉션을 반환한 다음 해당 모든 정보를 Grant-CsExternalAccessPolicy에 전송하여 컬렉션의 모든 사용자에게 FederationAndPICDefault 정책을 할당합니다.
  
추가 예로 이전에 FederationAndPICDefault 정책에 Alex를 할당했다가 이제 글로벌 외부 액세스 정책을 통해 Alex를 관리하고자 했던 경우를 가정해 보겠습니다. 전역 정책은 명시적으로 누구에게도 할당할 수 없습니다. 대신 해당 사용자에게 사용자당 정책이 할당되지 않은 경우 지정된 사용자에 대해 글로벌 정책이 사용됩니다. 따라서 글로벌 정책에 의해 Alex를 관리하려면 이전에 할당된 사용자 정책의 할당을 해지해야 합니다.  예제 명령은 다음과 같습니다.
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

이 명령은 Alex에게 할당된 외부 액세스 정책의 이름을 null 값($Null)으로 $Null. Null은 "nothing"을 의미합니다. 즉, Alex에게 외부 액세스 정책이 할당되지 않습니다. 사용자에게 외부 액세스 정책이 할당되지 않은 경우 해당 사용자는 전역 정책에 의해 관리됩니다.

## <a name="managing-large-numbers-of-users"></a>많은 수의 사용자 관리

많은 수의 사용자(1,000명 이상)를 관리하려면 [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet을 사용하여 스크립트 블록을 통해 명령을 일괄 처리해야 합니다.  이전 예제에서는 cmdlet이 실행될 때마다 호출을 설정한 다음 결과를 다시 보내기 전에 대기해야 합니다.  스크립트 블록을 사용하는 경우 cmdlet을 원격으로 실행할 수 있으며 완료되면 데이터를 다시 보낼 수 있습니다.

```powershell
$s = Get-PSSession | Where-Object { ($.ComputerName -like '*.online.lync.com' -or $.Computername -eq 'api.interfaces.records.teams.microsoft.com') -and $.State -eq 'Opened' -and $.Availability -eq 'Available' }

$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

이 경우 클라이언트 정책이 없는 사용자는 한에 500명까지 검색됩니다. 클라이언트 정책 "ClientPolicyNoIMURL" 및 외부 액세스 정책 "FederationAndPicDefault"를 부여합니다. 결과는 50개 그룹으로 일괄 처리된 다음 각 일괄 처리 50개가 원격 컴퓨터로 전송됩니다.
  
## <a name="see-also"></a>참고 항목

[PowerShell을 통해 비즈니스용 Skype Oline 관리](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)

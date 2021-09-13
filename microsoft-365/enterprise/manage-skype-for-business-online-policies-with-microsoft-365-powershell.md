---
title: PowerShell을 사용하여 온라인 비즈니스 정책용 Skype 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: '요약: PowerShell을 사용하여 정책으로 비즈니스용 Skype 온라인 사용자 계정 속성을 관리합니다.'
ms.openlocfilehash: aea57c836403918e4c236f766ed211a31ea2ceec
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189622"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>PowerShell을 사용하여 온라인 비즈니스 정책용 Skype 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

비즈니스용 Skype Online에 대한 사용자 계정의 여러 속성을 관리하려면 이러한 속성을 PowerShell에서 정책의 속성으로 Microsoft 365.
  
## <a name="before-you-begin"></a>시작하기 전에

다음 지침을 사용하여 명령을 실행하기 위한 설정(이미 완료한 단계 건너뛰기)을 수행합니다.

  > [!Note]
  > Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

1. [Teams PowerShell 모듈](/microsoftteams/teams-powershell-install)를 설치합니다.
    
2. Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행합니다. 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   메시지가 표시될 때 비즈니스용 Skype 계정 이름과 암호를 입력합니다.
    
## <a name="manage-user-account-policies"></a>사용자 계정 정책 관리

대부분의 비즈니스용 Skype Online 사용자 계정 속성은 정책을 사용하여 구성됩니다. 정책은 한 개 이상의 사용자에게 적용할 수 있는 설정 컬렉션입니다. 정책이 구성된 방법을 살펴보기 위해 FederationAndPICDefault 정책에 대해 다음 예제 명령을 실행하면 됩니다.
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

그러면 다음을 통해 유사한 기능을 얻을 수 있습니다.
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

이 예에서 이 정책 내의 값은 페더링 사용자와 통신할 때 사용할 수 있는 작업을 결정하거나 할 수 없습니다. 예를 들어 사용자가 조직 외부의 사용자와 통신할 수 있도록 EnableOutsideAccess 속성을 True로 설정해야 합니다. 이 속성은 이 속성이 Microsoft 365 관리 센터. 대신 선택한 다른 선택에 따라 속성이 자동으로 True 또는 False로 설정됩니다. 다른 두 가지 관심 속성은 다음입니다.
  
- **EnableFederationAccess는** 사용자가 페더전된 도메인의 사용자와 통신할 수 있는지 여부를 나타냅니다.
    
- **EnablePublicCloudAccess는** 사용자가 Live 사용자와 통신할 Windows 여부를 나타냅니다.
    
따라서 사용자 계정(예: **Set-CsUser -EnableFederationAccess** 및 )에서 페더ation 관련 속성을 직접 변경하지는 $True. 대신 원하는 속성 값이 미리 구성된 외부 액세스 정책을 계정에 할당합니다. 사용자가 페더니트 사용자 및 Windows Live 사용자와 통신할 수 있게 하려는 경우 해당 사용자 계정에 이러한 유형의 통신을 허용하는 정책이 할당되어야 합니다.
  
조직 외부의 사용자와 통신할 수 있는지 여부를 확인하려는 경우 다음을해야 합니다.
  
- 해당 사용자에게 할당된 외부 액세스 정책을 파악합니다.
    
- 해당 정책에서 허용되거나 허용되지 않는 기능을 파악합니다.
    
예를 들어 다음 명령을 사용하여 이 작업을 할 수 있습니다.
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

이 명령은 사용자에게 할당된 정책을 찾은 다음 해당 정책 내에서 사용 또는 사용되지 않도록 설정된 기능을 찾습니다.
  
PowerShell을 비즈니스용 Skype 온라인 정책을 관리하기 위해 다음에 대한 cmdlet을 참조하세요.

- [클라이언트 정책](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [회의 정책](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [모바일 정책](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [온라인 음성메일 정책](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [음성 라우팅 정책](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> 비즈니스용 Skype 온라인 다이얼 플랜은 이름을 제외한 모든 측면에서 정책입니다. "전화 걸기 정책" 대신 "다이얼 플랜"의 이름이 선택되어 Office Communications Server 및 Exchange. 
  
예를 들어 사용 가능한 모든 음성 정책을 확인하기 위해 다음 명령을 실행합니다.
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> 이 경우 사용 가능한 모든 음성 정책의 목록이 반환됩니다. 그러나 일부 정책을 모든 사용자에게 할당할 수 있는 것은 아니라는 사실에 유의해야 합니다. 이는 라이선싱 및 지리적 위치와 관련된 다양한 제한 때문에입니다. (소위 "[사용 위치.")](/previous-versions/azure/dn194136(v=azure.100)) 특정 사용자에게 할당할 수 있는 외부 액세스 정책 및 회의 정책을 알고 싶은 경우 다음 명령을 사용 합니다. 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

ApplicableTo 매개 변수는 반환되는 데이터를 지정된 사용자에게 할당할 수 있는 정책(예: Alex Darrow)으로 제한합니다. 라이선스 및 사용 위치 제한에 따라 사용 가능한 모든 정책의 하위 집합을 나타내는 것일 수 있습니다. 
  
정책 속성이 Microsoft 지원 담당자만 관리할 Microsoft 365 정책 속성이 사용되지 않는 경우도 있습니다. 
  
온라인 비즈니스용 Skype 사용자는 일종의 정책을 통해 관리해야 합니다. 유효한 정책 관련 속성이 비어 있는 경우, 즉 해당 사용자가 사용자 지정 정책을 특별히 할당하지 않는 한 사용자에게 자동으로 적용되는 정책인 글로벌 정책에 의해 관리됩니다. 사용자 계정에 대한 클라이언트 정책이 나열되지 않는 경우 글로벌 정책에 의해 관리됩니다. 다음 명령을 사용하여 전역 클라이언트 정책을 확인할 수 있습니다.
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>참고 항목

[PowerShell을 통해 비즈니스용 Skype Oline 관리](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
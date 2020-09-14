---
title: PowerShell을 통해 비즈니스용 Skype Oline 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Microsoft 365용 PowerShell을 사용하여 비즈니스용 Skype Online 정책, 사용자별 정책 및 모임 설정을 관리할 수 있습니다.
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430037"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>PowerShell을 통해 비즈니스용 Skype Oline 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

비즈니스용 Skype Online 관리자는 정책 관리를 담당합니다. Microsoft 365 관리 센터에서 이러한 작업 중 일부를 수행할 수 있지만 다른 작업은 PowerShell에서 보다 간편하게 수행할 수 있습니다.

## <a name="before-you-start"></a>시작하기 전에

[비즈니스용 Skype Online Windows PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드하여 설치하고 컴퓨터를 다시 시작합니다.


## <a name="connect-using-skype-for-business-online-admin-credentials"></a>비즈니스용 Skype Online 관리자 자격 증명을 사용하여 연결

1. Windows PowerShell 명령 프롬프트 창을 열고 다음의 명령을 실행합니다.
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. **Windows PowerShell 자격 증명 요청** 대화 상자에서 비즈니스용 Skype Online 관리자 계정 이름과 암호를 입력한 다음 **확인**을 선택합니다.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>다단계 인증과 함께 관리자 계정을 사용하여 연결

1. Windows PowerShell 명령 프롬프트 창을 열고 다음의 명령을 실행합니다.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. **New-CsOnlineSession** 명령에 메시지가 표시되면 비즈니스용 Skype Online 관리자 계정 이름을 입력 합니다.

3. **계정에 로그인** 대화 상자에서 비즈니스용 Skype Online 관리자 암호를 입력한 다음 **로그인**을 선택합니다.

4. **계정에 로그인** 대화 상자에서 지침에 따라 확인 코드와 같은 인증 정보를 추가한 다음 **확인**을 선택합니다.

자세한 내용은 다음을 참조하세요.
  
- [PowerShell을 사용하여 온라인 비즈니스 정책용 Skype 관리](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Powershell 비즈니스 온라인 정책에 대 한 사용자당 Skype 할당](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>기타 참고 항목

[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)

[비즈니스용 Skype Online PowerShell cmdlet 참조자료](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

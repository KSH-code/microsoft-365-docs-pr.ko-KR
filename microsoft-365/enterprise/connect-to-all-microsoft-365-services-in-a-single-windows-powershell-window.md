---
title: 단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: '요약: 단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결합니다.'
ms.openlocfilehash: d7684debae5ba0cc6679acf7a0cb6f590cca11c5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201712"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결

PowerShell을 사용하여 Microsoft 365를 관리하는 경우 여러 PowerShell 세션을 동시에 열 수 있습니다. 사용자 계정, SharePoint Online, Exchange Online, 비즈니스용 Skype Online, Microsoft Teams 및 보안 &amp; 준수 센터를 관리하기 위해 다른 PowerShell 창이 있을 수 있습니다.
  
서비스 관리 창 간에 데이터를 교환할 수 없기 때문에 최적의 Microsoft 365 관리 방법이 아닙니다. 이 문서에서는 Microsoft 365 계정, 비즈니스용 Skype 온라인, Exchange Online, SharePoint Online, Microsoft Teams, 보안 &amp; 준수 센터를 관리하는 데 사용할 수 있는 PowerShell의 단일 인스턴스를 사용하는 방법을 설명합니다.

>[!Note]
>현재 이 문서에는 전 세계(+GCC) 클라우드에 연결하는 명령만 포함되어 있습니다. 노트에서는 Microsoft 365 클라우드에 연결하는 방법에 대한 문서 링크를 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

단일 PowerShell 인스턴스에서 모든 Microsoft 365를 관리하려면 먼저 다음 필수 구성 요소를 고려하세요.
  
- 사용하는 Microsoft 365 회사 또는 학교 계정은 Microsoft 365 관리자 역할의 구성원이어야 합니다. 자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요. 이러한 Microsoft 365 PowerShell 요구 사항은 모든 Microsoft 365 서비스 요구 사항이 아닙니다.
    
- 다음 64비트 Windows 버전을 사용할 수 있습니다.
    
  - Windows 10
    
  - Windows 8.1 또는 Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 또는 Windows Server 2012
    
  - Windows 7 SP1(서비스 팩 1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*Microsoft .NET Framework 4.5.*x* 및 Windows Management Framework 3.0 또는 4.0을 설치해야 합니다. 자세한 내용은 [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview)를 참조하세요.
    
    비즈니스용 Skype 온라인과 하나의 Microsoft 365 모듈 요구 사항 때문에 64비트 버전의 Windows를 사용해야 합니다.
    
- Azure Active Directory(Azure AD), Exchange 온라인, SharePoint 온라인, 비즈니스용 Skype 온라인 및 Teams에 필요한 모듈을 설치해야 합니다.
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online 관리 셸](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [비즈니스용 Skype Online PowerShell 모듈](/microsoftteams/teams-powershell-overview)
  - [Exchange 온라인 PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell 개요](/microsoftteams/teams-powershell-overview)
    
-  비즈니스용 Skype 온라인과 보안 &amp; 준수 센터에 대해 서명된 스크립트를 실행하기 위해 PowerShell을 구성해야 합니다. 관리자 권한이 있는 PowerShell 세션에서 다음 명령을 실행 합니다 (**관리자 권한으로 실행** PowerShellPowerShell 세션).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>암호만 사용하는 경우 연결 단계

로그인에 암호만 사용하는 경우 단일 PowerShell 창에서 모든 서비스에 연결하려면 다음 단계를 따르세요.
  
1. Windows PowerShell을 엽니다.
    
2. 이 명령을 실행하여 Microsoft 365 회사 또는 학교 계정 자격 증명을 입력합니다.
    
   ```powershell
   $credential = Get-Credential
   ```

3. 이 명령을 실행하여 Azure Active Directory PowerShell for Grap 모듈을 사용해 Azure AD에 연결합니다.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   또는, Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하고 있는 경우, 이 명령을 실행하세요.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다. 사용자는 PowerShell의 이러한 cmdlet을 실행해야 합니다.

4. SharePoint 온라인에 연결 하려면 이 명령을 실행하세요. 도메인에 대한 조직 이름을 지정합니다. 예를 들어 "litwareinc\.onmicrosoft.com"의 경우 조직 이름 값은 "litwareinc"입니다.
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Exchange Online에 연결하려면 이 명령을 실행하세요.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > 전 세계 이외의 Microsoft 365 클라우드용 Exchange Online에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

6. 다음 명령을 실행하여 보안 &amp; 준수 센터에 연결합니다.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > 전 세계 이외의 Microsoft 365 클라우드에 대한 보안 &amp; 준수 센터에 연결하려면 [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)을 참조하세요.

7. 다음 명령을 실행하여 Teams PowerShell(및 비즈니스용 Skype Online)에 연결합니다.
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.
  
   > [!Note]
   > *전 세계* 이외의 Microsoft Teams 클라우드에 연결하려면 [연결-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams)를 참조하세요.
  


### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell for Grap 모듈

다음은 그래프 모듈용 Azure Active Directory PowerShell을 사용할 때 단일 블록의 모든 서비스에 대한 명령입니다. 로그인을 위해 도메인 호스트 이름 및 UPN을 지정하고 한 번에 모두 실행합니다.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈

다음은 Windows PowerShell 모듈용 Microsoft Azure Active Directory 모듈을 사용할 때 단일 블록의 모든 서비스에 대한 명령입니다. 로그인을 위해 도메인 호스트 이름 및 UPN을 지정하고 한 번에 모두 실행합니다.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>다단계 인증을 사용하는 경우 연결 단계

### <a name="azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell

다음은 그래프 모듈용 Azure Active Directory PowerShell과 함께 다단계 인증을 사용할 때 여러 Microsoft 365 서비스에 연결하기 위한 단일 블록의 모든 명령입니다.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈

다음은 Windows PowerShell 모듈용 Microsoft Azure Active Directory 모듈과 함께 다단계 인증을 사용할 때 여러 Microsoft 365 서비스에 연결하기 위한 단일 블록의 모든 명령입니다.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>PowerShell 창 닫기

PowerShell 창을 닫으려면 이 명령을 실행하여 비즈니스용 Skype 온라인, SharePoint Online 및 Teams에 대한 활성 세션을 제거합니다.
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>참고 항목

- [PowerShell로 Microsoft 365에 연결](connect-to-microsoft-365-powershell.md)
- [PowerShell로 SharePoint 온라인 관리](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

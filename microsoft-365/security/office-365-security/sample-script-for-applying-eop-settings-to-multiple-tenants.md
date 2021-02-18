---
title: EOP 설정에 대한 샘플 스크립트 - 여러 테넌트
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 PowerShell을 사용하여 EOP(Microsoft Exchange Online Protection)의 테넌트에 구성 설정을 적용하는 방법을 배우게 됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4823ed09cd8a9d72aef21df3d51213cb4512b4f9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288540"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

다음 샘플 스크립트를 사용하면 여러 테넌트(회사)를 관리하는 EOP(Microsoft Exchange Online Protection) 관리자가 Exchange Online PowerShell을 사용하여 해당 테넌트에 구성 설정을 보고/또는 적용할 수 있습니다.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>여러 테넌트에 대해 스크립트 또는 cmdlet을 실행하려면

1. 아직 설치하지 않은 경우 [Exchange Online V2 모듈을 설치합니다.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

2. 스프레드시트 앱(예: Excel)을 사용하여 다음 세부 정보가 있는 .csv 파일을 생성합니다.

   - UserName 열: 연결하는 데 사용할 계정(예: `admin@contoso.onmicrosoft.com` ).
   - cmdlet 열: 실행할 cmdlet 또는 명령(예: `Get-AcceptedDomain` `Get-AcceptedDomain | FT Name`

   파일은 다음과 같이 표시됩니다.

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. .csv 파일을 찾기 쉬운 위치에 저장합니다(예: c:\scripts\inputfile.csv.

4. RunCmdletOnMultipleTenants.ps1[](#runcmdletonmultipletenantsps1) 스크립트를 메모장에 복사한 다음 파일을 찾기 쉬운 위치(예: c:\scripts)에 저장합니다.

5. 다음 구문을 사용하여 스크립트를 실행합니다.

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   예를 들면 다음과 같습니다.

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 각 테넌트가 로그온되어 스크립트가 실행됩니다.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 사용자 환경과 일치하도록 스크립트의 `Connect-IPPSSession` 줄을 수정해야 할 수 있습니다. 예를 들어 Office 365 Germany의 경우 스크립트의 현재 값과 다른 _ConnectionUri_ 값이 필요합니다. 자세한 내용은 [Exchange Online Powershell에 연결 을 참조하세요.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {

# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```

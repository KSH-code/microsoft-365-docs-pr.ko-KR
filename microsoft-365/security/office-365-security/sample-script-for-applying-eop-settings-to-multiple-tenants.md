---
title: EOP 설정에 대 한 샘플 스크립트-여러 테 넌 트
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 PowerShell을 사용 하 여 Microsoft EOP (Exchange Online Protection)의 테 넌 트에 구성 설정을 적용 하는 방법을 알아봅니다.
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376570"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


다음 예제 스크립트에서는 여러 테 넌 트 (회사)를 관리 하는 Microsoft EOP (Exchange Online Protection) 관리자가 Exchange Online PowerShell을 사용 하 여 해당 테 넌 트에 구성 설정을 보고 적용 합니다.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>여러 테넌트에 대해 스크립트 또는 cmdlet을 실행하려면

1. 아직 없는 경우 [Exchange Online V2 모듈을 설치](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)합니다.

2. 스프레드시트 앱 (예: Excel)을 사용 하 여 다음과 같은 세부 정보로 .csv 파일을 만듭니다.

   - 사용자 이름 열: 연결 하는 데 사용할 계정 등을 예로 들 수 있습니다 `admin@contoso.onmicrosoft.com` .
   - Cmdlet 열: 실행할 cmdlet 또는 명령입니다 (예를 들면 `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name` ).

   파일은 다음과 같이 표시 됩니다.

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. .Csv 파일을 찾기 쉬운 위치 (예: c:\scripts\inputfile.csv)로 저장 합니다.

4. [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 스크립트를 메모장에 복사한 후 찾기 쉬운 위치 (예: c:\scripts)에 파일을 저장 합니다.

5. 다음 구문을 사용하여 스크립트를 실행합니다.

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   예를 들면 다음과 같습니다.

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 각 테 넌 트가 로그온 되 고 스크립트가 실행 됩니다.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 스크립트의 줄을 환경에 맞게 수정 해야 할 수도 있습니다 `Connect-IPPSSession` . 예를 들어 Office 365 독일에는 스크립트의 현재 값과 다른 _Connectionuri_ 값이 필요 합니다. 자세한 내용은 [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)에 연결을 참조 하십시오.

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

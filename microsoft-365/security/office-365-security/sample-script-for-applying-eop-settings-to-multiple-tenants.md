---
title: EOP 설정에 대 한 샘플 스크립트-여러 테 넌 트
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 PowerShell을 사용 하 여 Microsoft EOP (Exchange Online Protection)의 테 넌 트에 구성 설정을 적용 하는 방법을 알아봅니다.
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209142"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트

다음 샘플 스크립트를 사용하여 여러 테넌트(회사)를 관리하는 Microsoft EOP(Exchange Online Protection) 관리자는 Windows PowerShell을 사용하여 해당 테넌트에 구성 설정을 적용할 수 있습니다.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>여러 테넌트에 대해 스크립트 또는 cmdlet을 실행하려면

1. Excel과 같은 응용 프로그램을 사용하여 .csv 파일(예: c:\scripts\inputfile.csv)을 만듭니다.

2. .csv 파일에서 두 개의 열 이름 UserName 및 Cmdlet을 지정합니다.

3. .csv 파일의 각 행에서 UserName 열에는 테넌트의 관리자 이름을 추가하고 cmdlet 열에는 해당 테넌트에 대해 실행할 cmdlet을 추가합니다. 예를 들어 admin@contoso.com 및 Get-AcceptedDomain을 사용합니다.

4. [Runcmdletonmultipletenants.ps1](#runcmdletonmultipletenantsps1) 스크립트를 메모장에 복사한 다음 찾기 쉬운 위치 (예: c:\scripts)에 파일을 저장 합니다.

5. 다음 구문을 사용하여 스크립트를 실행합니다.

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   예를 들면 다음과 같습니다.

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. 각 테 넌 트가 로그온 되 고 스크립트가 실행 됩니다.

## <a name="runcmdletonmultipletenantsps1"></a>Runcmdletonmultipletenants.ps1. ps1

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```

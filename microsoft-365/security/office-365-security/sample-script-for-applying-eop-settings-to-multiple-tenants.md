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
description: 이 문서에서는 PowerShell을 사용하여 EOP(Microsoft Exchange Online 보호)의 테넌트에 구성 설정을 적용하는 방법을 배우게 됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928511"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="df1c2-103">여러 테넌트에 EOP 설정을 적용하기 위한 샘플 스크립트</span><span class="sxs-lookup"><span data-stu-id="df1c2-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="df1c2-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="df1c2-104">**Applies to**</span></span>
-  [<span data-ttu-id="df1c2-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="df1c2-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="df1c2-106">다음 샘플 스크립트를 사용하면 여러 테넌트(회사)를 관리하는 EOP(Microsoft Exchange Online Protection) 관리자가 Exchange Online PowerShell을 사용하여 해당 테넌트에 구성 설정을 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="df1c2-107">여러 테넌트에 대해 스크립트 또는 cmdlet을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="df1c2-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="df1c2-108">아직 설치하지 않은 경우 Exchange Online V2 모듈 [을 설치합니다.](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)</span><span class="sxs-lookup"><span data-stu-id="df1c2-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="df1c2-109">스프레드시트 앱(예: Excel)을 사용하여 다음 세부 정보가 있는 .csv 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="df1c2-110">UserName 열: 연결하는 데 사용할 계정(예: `admin@contoso.onmicrosoft.com` )입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="df1c2-111">Cmdlet 열: 실행할 cmdlet 또는 명령(예: `Get-AcceptedDomain` 또는 `Get-AcceptedDomain | FT Name` )입니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="df1c2-112">파일은 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="df1c2-113">.csv 파일을 찾기 쉬운 위치에 저장합니다(예: c:\scripts\inputfile.csv.</span><span class="sxs-lookup"><span data-stu-id="df1c2-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="df1c2-114">RunCmdletOnMultipleTenants.ps1[](#runcmdletonmultipletenantsps1) 스크립트를 메모장에 복사한 다음 파일을 찾기 쉬운 위치(예: c:\scripts)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="df1c2-115">다음 구문을 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="df1c2-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="df1c2-117">각 테넌트가 로그온되어 스크립트가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="df1c2-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="df1c2-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="df1c2-119">사용자 환경과 일치하도록 스크립트의 `Connect-IPPSSession` 줄을 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="df1c2-120">예를 들어 Office 365 Germany에는 스크립트의 현재 값과 다른 _ConnectionUri_ 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c2-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="df1c2-121">자세한 내용은 [Exchange Online Powershell에 연결을 참조하세요.](/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="df1c2-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
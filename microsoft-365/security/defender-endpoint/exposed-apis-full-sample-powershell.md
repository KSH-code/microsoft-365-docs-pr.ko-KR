---
title: PowerShell API 가이드를 사용하는 고급 헌팅
ms.reviewer: ''
description: 다음 코드 예제를 사용하여 끝점 API에 대한 여러 Microsoft Defender를 쿼리합니다.
keywords: api, 지원되는 api, 고급 헌팅, 쿼리
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/24/2018
ms.technology: mde
ms.custom: api
ms.openlocfilehash: c0589818e35ef065f41f40f3b101ba0daab060b1
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588376"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a>PowerShell을 사용하여 끝점 API용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

끝점용 Microsoft Defender의 여러 API를 사용하는 전체 시나리오입니다.

이 섹션에서는 PowerShell 샘플을 공유합니다. 
- 토큰 검색 
- 토큰을 사용하여 끝점용 Microsoft Defender에서 최신 경고 검색
- 각 경고에 대해 알림의 우선 순위가 보통 또는 높음인 경우 장치가 의심스러운 URL에 연결한 시간을 확인합니다.

**선행 작업:** 먼저 앱을 [만들어야 합니다.](apis-intro.md)

## <a name="preparation-instructions"></a>준비 지침

- PowerShell 창을 엽니다.
- 정책에서 PowerShell 명령을 실행할 수 없는 경우 다음 명령을 실행할 수 있습니다.
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

자세한 내용은 [PowerShell 설명서를 참조하세요.](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>토큰을 얻다

아래를 실행합니다.

- $tenantId: 쿼리를 실행할 테넌트의 ID입니다(즉, 이 테넌트의 데이터에 대해 쿼리가 실행됩니다).
- $appId: AAD 앱의 ID(앱에 Endpoint용 Defender에 대한 '고급 쿼리 실행' 권한이 있어야 합니다.
- $appSecret: Azure AD 앱의 비밀

- $suspiciousUrl: URL


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a>참고 항목
- [끝점 API용 Microsoft Defender](apis-intro.md)
- [고급 헌팅 API](run-advanced-query-api.md)
- [Python을 사용하는 지능형 헌팅](run-advanced-query-sample-python.md)

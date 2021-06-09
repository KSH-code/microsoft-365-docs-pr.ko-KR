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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: ef6d05bb27018bb72f731da2e8b7837c9d9f0127
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842065"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="c72aa-104">PowerShell을 사용하여 끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c72aa-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c72aa-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c72aa-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="c72aa-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c72aa-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c72aa-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="c72aa-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c72aa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c72aa-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="c72aa-110">끝점용 Microsoft Defender의 여러 API를 사용하는 전체 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="c72aa-111">이 섹션에서는 PowerShell 샘플을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="c72aa-112">토큰 검색</span><span class="sxs-lookup"><span data-stu-id="c72aa-112">Retrieve a token</span></span> 
- <span data-ttu-id="c72aa-113">토큰을 사용하여 끝점용 Microsoft Defender에서 최신 경고 검색</span><span class="sxs-lookup"><span data-stu-id="c72aa-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="c72aa-114">각 경고에 대해 알림의 우선 순위가 보통 또는 높음인 경우 장치가 의심스러운 URL에 연결한 시간을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="c72aa-115">**선행 작업:** 먼저 앱을 [만들어야 합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c72aa-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="c72aa-116">준비 지침</span><span class="sxs-lookup"><span data-stu-id="c72aa-116">Preparation instructions</span></span>

- <span data-ttu-id="c72aa-117">PowerShell 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="c72aa-118">정책에서 PowerShell 명령을 실행할 수 없는 경우 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="c72aa-119">자세한 내용은 [PowerShell 설명서를 참조하세요.](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="c72aa-119">For more information, see [PowerShell documentation](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="c72aa-120">토큰을 얻다</span><span class="sxs-lookup"><span data-stu-id="c72aa-120">Get token</span></span>

<span data-ttu-id="c72aa-121">아래를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-121">Run the below:</span></span>

- <span data-ttu-id="c72aa-122">$tenantId: 쿼리를 실행할 테넌트의 ID입니다(즉, 이 테넌트의 데이터에 대해 쿼리가 실행됩니다).</span><span class="sxs-lookup"><span data-stu-id="c72aa-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="c72aa-123">$appId: AAD 앱의 ID(앱에 끝점용 Defender에 대한 '고급 쿼리 실행' 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c72aa-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="c72aa-124">$appSecret: Azure AD 앱의 비밀</span><span class="sxs-lookup"><span data-stu-id="c72aa-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="c72aa-125">$suspiciousUrl: URL</span><span class="sxs-lookup"><span data-stu-id="c72aa-125">$suspiciousUrl: The URL</span></span>


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


## <a name="see-also"></a><span data-ttu-id="c72aa-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c72aa-126">See also</span></span>
- [<span data-ttu-id="c72aa-127">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c72aa-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="c72aa-128">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="c72aa-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="c72aa-129">Python을 사용하는 지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="c72aa-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)

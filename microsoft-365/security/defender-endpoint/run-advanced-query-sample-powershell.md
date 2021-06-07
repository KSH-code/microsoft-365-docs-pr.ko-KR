---
title: PowerShell API 기본을 사용하는 고급 헌팅
ms.reviewer: ''
description: PowerShell을 사용하여 끝점 API용 Microsoft Defender를 쿼리하는 기본 방법을 학습합니다.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9192662b8d4ed23a5903dddb555f07bf182ab17f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771504"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="07de6-104">PowerShell을 사용하는 지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="07de6-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07de6-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="07de6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="07de6-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="07de6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07de6-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="07de6-108">PowerShell을 사용하여 고급 쿼리를 실행합니다. 고급 헌팅 [API를 참조합니다.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="07de6-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="07de6-109">이 섹션에서는 PowerShell 샘플을 공유하여 토큰을 검색하고 이를 사용하여 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="07de6-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="07de6-110">Before you begin</span></span>
<span data-ttu-id="07de6-111">먼저 앱을 [만들어야 합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="07de6-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="07de6-112">준비 지침</span><span class="sxs-lookup"><span data-stu-id="07de6-112">Preparation instructions</span></span>

- <span data-ttu-id="07de6-113">PowerShell 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="07de6-114">정책에서 PowerShell 명령을 실행할 수 없는 경우 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="07de6-115">자세한 내용은 [PowerShell 설명서를 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="07de6-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="07de6-116">토큰을 얻다</span><span class="sxs-lookup"><span data-stu-id="07de6-116">Get token</span></span>

- <span data-ttu-id="07de6-117">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="07de6-118">여기서</span><span class="sxs-lookup"><span data-stu-id="07de6-118">where</span></span>
- <span data-ttu-id="07de6-119">$tenantId: 쿼리를 실행할 테넌트의 ID입니다(즉, 이 테넌트의 데이터에 대해 쿼리가 실행됩니다).</span><span class="sxs-lookup"><span data-stu-id="07de6-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="07de6-120">$appId: Azure AD 앱의 ID(앱에 Endpoint용 Defender에 대한 '고급 쿼리 실행' 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="07de6-121">$appSecret: Azure AD 앱의 비밀</span><span class="sxs-lookup"><span data-stu-id="07de6-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="07de6-122">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="07de6-122">Run query</span></span>

<span data-ttu-id="07de6-123">다음 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="07de6-124">$results 결과 포함</span><span class="sxs-lookup"><span data-stu-id="07de6-124">$results contain the results of your query</span></span>
- <span data-ttu-id="07de6-125">$schema 쿼리 결과의 스마마가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="07de6-126">복잡한 쿼리</span><span class="sxs-lookup"><span data-stu-id="07de6-126">Complex queries</span></span>

<span data-ttu-id="07de6-127">복잡한 쿼리(또는 여러 줄 쿼리)를 실행하려는 경우 쿼리를 파일에 저장하고 위의 예제의 첫 번째 줄 대신 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="07de6-128">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="07de6-128">Work with query results</span></span>

<span data-ttu-id="07de6-129">이제 쿼리 결과를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-129">You can now use the query results.</span></span>

<span data-ttu-id="07de6-130">파일 형식의 CSV 형식으로 쿼리 결과를 출력 file1.csv 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="07de6-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="07de6-131">아래 작업을 수행하여 파일 형식의 JSON file1.js결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="07de6-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="07de6-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="07de6-132">Related topic</span></span>
- [<span data-ttu-id="07de6-133">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="07de6-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="07de6-134">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="07de6-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="07de6-135">Python을 사용하는 지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="07de6-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)

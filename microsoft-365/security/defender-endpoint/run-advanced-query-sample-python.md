---
title: Python API 가이드를 사용하는 고급 헌팅
ms.reviewer: ''
description: 예제와 함께 Python을 사용하여 Microsoft Defender for Endpoint API를 사용하여 쿼리하는 방법을 설명합니다.
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
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771452"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="924f3-104">Python을 사용하는 지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="924f3-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="924f3-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="924f3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="924f3-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="924f3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="924f3-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="924f3-108">Python을 사용하여 고급 쿼리를 실행합니다. 고급 헌팅 [API를 참조합니다.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="924f3-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="924f3-109">이 섹션에서는 Python 샘플을 공유하여 토큰을 검색하고 이를 사용하여 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="924f3-110">**선행 작업:** 먼저 앱을 [만들어야 합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="924f3-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="924f3-111">토큰을 얻다</span><span class="sxs-lookup"><span data-stu-id="924f3-111">Get token</span></span>

- <span data-ttu-id="924f3-112">다음의 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="924f3-113">여기서</span><span class="sxs-lookup"><span data-stu-id="924f3-113">where</span></span>
- <span data-ttu-id="924f3-114">tenantId: 쿼리를 실행하려는 테넌트의 ID입니다(즉, 이 테넌트의 데이터에 대해 쿼리가 실행됩니다).</span><span class="sxs-lookup"><span data-stu-id="924f3-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="924f3-115">appId: Azure AD 앱의 ID(앱에 끝점용 Microsoft Defender에 대한 '고급 쿼리 실행' 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="924f3-116">appSecret: Azure AD 앱의 비밀</span><span class="sxs-lookup"><span data-stu-id="924f3-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="924f3-117">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="924f3-117">Run query</span></span>

 <span data-ttu-id="924f3-118">다음 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="924f3-119">schema contains the schema of the results of your query</span><span class="sxs-lookup"><span data-stu-id="924f3-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="924f3-120">결과에 쿼리 결과가 포함</span><span class="sxs-lookup"><span data-stu-id="924f3-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="924f3-121">복잡한 쿼리</span><span class="sxs-lookup"><span data-stu-id="924f3-121">Complex queries</span></span>

<span data-ttu-id="924f3-122">복잡한 쿼리(또는 여러 줄 쿼리)를 실행하려는 경우 쿼리를 파일에 저장하고 위의 예제의 첫 번째 줄 대신 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="924f3-123">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="924f3-123">Work with query results</span></span>

<span data-ttu-id="924f3-124">이제 쿼리 결과를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-124">You can now use the query results.</span></span>

<span data-ttu-id="924f3-125">결과를 이행하기 위해 아래를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="924f3-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="924f3-126">파일 형식의 CSV 형식으로 쿼리 결과를 출력 file1.csv 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="924f3-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="924f3-127">아래 작업을 수행하여 파일 형식의 JSON file1.js결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="924f3-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="924f3-128">관련 항목</span><span class="sxs-lookup"><span data-stu-id="924f3-128">Related topic</span></span>
- [<span data-ttu-id="924f3-129">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="924f3-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="924f3-130">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="924f3-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="924f3-131">PowerShell을 사용하는 지능형 헌팅</span><span class="sxs-lookup"><span data-stu-id="924f3-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)

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
ms.technology: mde
ms.openlocfilehash: 78b6097ea9c3a83f35585f3b13fec4d9056ac25a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199720"
---
# <a name="advanced-hunting-using-python"></a>Python을 사용한 고급 헌팅

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Python을 사용하여 고급 쿼리를 실행합니다. 고급 헌팅 [API를 참조합니다.](run-advanced-query-api.md)

이 섹션에서는 Python 샘플을 공유하여 토큰을 검색하고 이를 사용하여 쿼리를 실행합니다.

>**선행 작업:** 먼저 앱을 [만들어야 합니다.](apis-intro.md)

## <a name="get-token"></a>토큰을 얻다

- 다음의 명령을 실행합니다.

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

여기서
- tenantId: 쿼리를 실행하려는 테넌트의 ID입니다(즉, 이 테넌트의 데이터에 대해 쿼리가 실행됩니다).
- appId: Azure AD 앱의 ID(앱에 끝점용 Microsoft Defender에 대한 '고급 쿼리 실행' 권한이 있어야 합니다.
- appSecret: Azure AD 앱의 비밀

## <a name="run-query"></a>쿼리 실행

 다음 쿼리를 실행합니다.

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

- schema contains the schema of the results of your query
- 결과에 쿼리 결과가 포함

### <a name="complex-queries"></a>복잡한 쿼리

복잡한 쿼리(또는 여러 줄 쿼리)를 실행하려는 경우 쿼리를 파일에 저장하고 위의 예제의 첫 번째 줄 대신 다음 명령을 실행합니다.

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>쿼리 결과 작업

이제 쿼리 결과를 사용할 수 있습니다.

결과를 이행하기 위해 아래를 참조하세요.

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


파일 형식의 CSV 형식으로 쿼리 결과를 출력 file1.csv 다음을 수행하십시오.

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

아래 작업을 수행하여 파일 형식의 JSON file1.js결과를 출력합니다.

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>관련 항목
- [끝점 API용 Microsoft Defender](apis-intro.md)
- [고급 헌팅 API](run-advanced-query-api.md)
- [PowerShell을 사용한 고급 헌팅](run-advanced-query-sample-powershell.md)

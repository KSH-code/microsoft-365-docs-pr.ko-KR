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
ms.openlocfilehash: e207978dbb65863764c66c5afc5c467552100461
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220315"
---
# <a name="advanced-hunting-using-powershell"></a>PowerShell을 사용하는 지능형 헌팅

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

PowerShell을 사용하여 고급 쿼리를 실행합니다. 고급 헌팅 [API를 참조합니다.](run-advanced-query-api.md)

이 섹션에서는 PowerShell 샘플을 공유하여 토큰을 검색하고 이를 사용하여 쿼리를 실행합니다.

## <a name="before-you-begin"></a>시작하기 전에
먼저 앱을 [만들어야 합니다.](apis-intro.md)

## <a name="preparation-instructions"></a>준비 지침

- PowerShell 창을 엽니다.
- 정책에서 PowerShell 명령을 실행할 수 없는 경우 다음 명령을 실행할 수 있습니다.
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>자세한 내용은 [PowerShell 설명서를 참조하세요.](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>토큰을 얻다

- 다음 명령을 실행합니다.

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

여기서
- $tenantId: 쿼리를 실행할 테넌트의 ID입니다(즉, 이 테넌트의 데이터에 대해 쿼리가 실행됩니다).
- $appId: Azure AD 앱의 ID(앱에 Endpoint용 Defender에 대한 '고급 쿼리 실행' 권한이 있어야 합니다.
- $appSecret: Azure AD 앱의 비밀

## <a name="run-query"></a>쿼리 실행

다음 쿼리를 실행합니다.

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

- $results 결과 포함
- $schema 쿼리 결과의 스마마가 포함되어 있습니다.

### <a name="complex-queries"></a>복잡한 쿼리

복잡한 쿼리(또는 여러 줄 쿼리)를 실행하려는 경우 쿼리를 파일에 저장하고 위의 예제의 첫 번째 줄 대신 다음 명령을 실행합니다.

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>쿼리 결과 작업

이제 쿼리 결과를 사용할 수 있습니다.

파일 형식의 CSV 형식으로 쿼리 결과를 출력 file1.csv 다음을 수행하십시오.

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

아래 작업을 수행하여 파일 형식의 JSON file1.js결과를 출력합니다.

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>관련 항목
- [끝점 API용 Microsoft Defender](apis-intro.md)
- [고급 헌팅 API](run-advanced-query-api.md)
- [Python을 사용하는 지능형 헌팅](run-advanced-query-sample-python.md)

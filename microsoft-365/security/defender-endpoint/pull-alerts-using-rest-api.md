---
title: REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기
description: SIEM REST API를 사용하여 Microsoft Defender for Endpoint API 끝점을 호출하여 JSON 형식으로 검색을 끌어오는 방법을 학습합니다.
keywords: 검색, 검색 끌어오기, rest api, 요청, 응답
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 29aa8008dc3674760e4e720f155d6df82068ab55
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59402181"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>SIEM REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

> [!NOTE]
>
> - [끝점용 Microsoft Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.
> - [끝점 검색을 위한 Microsoft Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.
> s-The Microsoft Defender for Endpoint Alert API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 제공합니다. 자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)

끝점용 Microsoft Defender는 API에서 검색을 끌어오는 OAuth 2.0 프로토콜을 지원합니다.

일반적으로 OAuth 2.0 프로토콜은 다음 네 가지 유형의 흐름을 지원합니다.

- 권한 부여 흐름
- 암시적 흐름
- 클라이언트 자격 증명 흐름
- 자원 소유자 흐름

OAuth 사양에 대한 자세한 내용은 [OAuth](http://www.oauth.net)웹 사이트를 참조하십시오.

끝점용 Microsoft Defender는  권한 부여  흐름 및 클라이언트 자격 증명 흐름을 지원하여 권한 부여 서버로 AAD(Azure Active Directory)를 사용하여 검색을 끌어오기 위한 액세스 권한을 얻습니다.

권한 _부여 흐름은_ 사용자 자격 증명을 사용하여 권한 부여 코드를 얻은 다음 액세스 토큰을 얻는 데 사용됩니다.

클라이언트 _자격 증명 흐름은_ 클라이언트 자격 증명을 사용하여 끝점용 Microsoft Defender 끝점 URL에 대해 인증합니다. 이 흐름은 OAuth 클라이언트가 사용자 자격 증명이 필요하지 않은 API에 대한 요청을 만드는 시나리오에 적합합니다.

Microsoft Defender for Endpoint API에서 다음 메서드를 사용하여 JSON 형식으로 검색을 끌어오는 방법을 사용합니다.

> [!NOTE]
> Microsoft Defender 보안 센터 경고 검색을 단일 경고로 병합할 수 있습니다. 이 API는 설정한 쿼리 매개 변수에 따라 원시 양식의 경고 검색을 끌어와서 자체 그룹화 및 필터링을 적용할 수 있도록 합니다.

## <a name="before-you-begin"></a>시작하기 전에

- 검색을 끌어오기 위해 끝점용 Microsoft Defender 끝점을 호출하기 전에 AAD(Microsoft Defender)에서 SIEM 통합 응용 프로그램을 Azure Active Directory 합니다. 자세한 내용은 [Enable SIEM integration in Microsoft Defender for Endpoint을 참조하세요.](enable-siem-integration.md)

- Azure 응용 프로그램 등록에서 다음 값을 참고하십시오. 서비스 또는 데몬 앱에서 OAuth 흐름을 구성하려면 다음 값이 필요합니다.
  - 응용 프로그램 ID(응용 프로그램에 고유)
  - 앱 키 또는 비밀(응용 프로그램에 고유한)
  - 앱의 OAuth 2.0 토큰 끝점
    - 앱 페이지의 Azure  관리 포털 아래쪽에서 끝점 보기를 클릭하여 이 값을 찾으십시오. 끝점은 처럼 보이게 `https://login.microsoftonline.com/{tenantId}/oauth2/token` 됩니다.

## <a name="get-an-access-token"></a>액세스 토큰을 얻게 됩니다.

끝점에 대한 호출을 만들기 전에 액세스 토큰을 만들어야 합니다.

액세스 토큰을 사용하여 보호된 리소스(끝점용 Microsoft Defender의 검색)에 액세스합니다.

액세스 토큰을 얻기 위해 토큰을 발행하는 끝점에 대한 POST 요청을 해야 합니다. 샘플 요청은 다음과 같습니다.

```http
POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```

응답에는 액세스 토큰 및 만료 정보가 포함됩니다.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```

이제 끝점 API에  대한 요청에서 access_token 필드의 값을 사용할 수 있습니다.

## <a name="request"></a>요청

액세스 토큰을 사용하여 앱은 끝점 API용 Microsoft Defender에 인증된 요청을 만들 수 있습니다. 앱은 각 요청의 Authorization 헤더에 액세스 토큰을 추가해야 합니다.

### <a name="request-syntax"></a>요청 구문

방법|요청 URI
---|---
GET|해당 지역에 적용할 수 있는 URI를 사용 합니다. <p> **EU의 경우**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` <p> **미국의 경우**: `https://wdatp-alertexporter-us.windows.com/api/alerts` <p> **영국의** 경우 : `https://wdatp-alertexporter-uk.windows.com/api/alerts`

### <a name="request-header"></a>요청 헤더

헤더|유형|설명|
---|---|---
권한 부여|문자열|필수 특성입니다. **Bearer** 토큰 형식의 Azure AD 액세스 &lt; *토큰입니다.* &gt;|

### <a name="request-parameters"></a>요청 매개 변수

선택적 쿼리 매개 변수를 사용하여 응답에 반환되는 데이터의 양을 지정하고 제어합니다. 매개 변수 없이 이 메서드를 호출하면 응답에는 지난 2시간 동안 조직의 모든 경고가 포함됩니다.

이름|값|설명
---|---|---
sinceTimeUtc|날짜/시간|필드에 따라 바운드 경고가 검색된 하위 시간을 정의합니다. <p> `LastProcessedTimeUtc` <p> 시간 범위는 sinceTimeUtc 시간에서 현재 시간까지입니다. <p> **참고:** 지정하지 않으면 지난 2시간 동안 생성된 모든 경고가 검색됩니다.
untilTimeUtc|날짜/시간|바운드 경고가 검색된 상위 시간을 정의합니다. <p> 시간 범위는 `sinceTimeUtc` 다음을 수시로 `untilTimeUtc` 합니다. <p> **참고:** 지정하지 않으면 기본값은 현재 시간입니다.
ago|문자열|경고를 끌어오는 시간 범위는 다음과 `(current_time - ago)` `current_time` 같습니다. <p> 값은 **ISO 8601** 기간 형식에 따라 설정해야 합니다. <p> 예: 지난 10분 동안 수신된 경고를 `ago=PT10M` 끌어오는 예제입니다.
limit|int|검색할 알림 수를 정의합니다. 가장 최근 알림은 정의된 수에 따라 검색됩니다.<p> **참고:** 지정하지 않으면 시간 범위에서 사용할 수 있는 모든 경고가 검색됩니다.
machinegroups|문자열|경고를 끌어오기 위해 장치 그룹을 지정합니다. <p> **참고:** 지정하지 않으면 모든 장치 그룹의 경고가 검색됩니다. <p> 예제: <br><br> `https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines`
DeviceCreatedMachineTags|문자열|레지스트리의 단일 장치 태그입니다.
CloudCreatedMachineTags|문자열|디바이스에서 만든 장치 태그 Microsoft Defender 보안 센터.

### <a name="request-example"></a>요청 예제

다음 예제에서는 조직의 모든 검색을 검색하는 방법을 보여 제공합니다.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

다음 예제에서는 2016-09-12 00:00:00 이후의 마지막 20개 검색을 요청하는 데 사용됩니다.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>응답

반환 값은 JSON 형식의 경고 개체 배열입니다.

반환 값의 예는 다음과 같습니다.

```json
[
{
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>코드 예제

### <a name="get-access-token"></a>액세스 토큰을 얻다

다음 코드 예제에서는 Endpoint SIEM API용 Microsoft Defender를 호출하기 위한 액세스 토큰을 얻는 방법을 보여 제공합니다.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials"|cut -d "{" -f2|cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]}|cut -d "\"" -f2|cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>토큰을 사용하여 검색 끝점에 연결

다음 코드 예제에서는 끝점용 Defender SIEM API를 호출하는 데 액세스 토큰을 사용하여 경고를 표시하는 방법을 보여 제공합니다.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token"
}

#Send the webrequest and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results. This works for SIEM API:
$alerts =  $response.Content|ConvertFrom-Json|ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o|foreach {$_ -replace ":", "."}

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw|ConvertFrom-Json|Select-Object -ExpandProperty value|Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token"|cut -d "[" -f2|cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>오류 코드

끝점 REST용 Microsoft Defender API는 잘못된 요청으로 인해 발생하는 다음 오류 코드를 반환합니다.

HTTP 오류 코드|설명
---|---
401|잘못된 요청 또는 잘못된 토큰
403|무단 예외 - 테넌트 관리자가 관리하지 않는 도메인 또는 테넌트 상태가 삭제됩니다.
500|서비스에 오류가 발생했습니다.

## <a name="related-topics"></a>관련 항목

- [끝점용 Microsoft Defender에서 SIEM 통합 사용](enable-siem-integration.md)
- [끝점 검색을 위해 Microsoft Defender를 끌어오도록 ArcSight 구성](configure-arcsight.md)
- [SIEM 도구로 검색 끌어오기](configure-siem.md)
- [끝점 검색 필드용 Microsoft Defender](api-portal-mapping.md)
- [SIEM 도구 통합 문제 해결](troubleshoot-siem.md)

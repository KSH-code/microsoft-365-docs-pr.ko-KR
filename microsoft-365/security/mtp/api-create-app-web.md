---
title: 사용자 없이 Microsoft Threat Protection에 액세스 하기 위한 앱 만들기
description: 사용자 없이 Microsoft Threat Protection에 액세스 하기 위한 앱을 만드는 방법을 알아봅니다.
keywords: 앱, 액세스, api, 만들기
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: be637bab97083cb857e3983dd9b82290590c1302
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650460"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a>사용자 없이 Microsoft Threat Protection에 액세스 하기 위한 앱 만들기

**적용 대상:**
- Microsoft 위협 방지

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

이 페이지에서는 사용자 없이 Microsoft Threat Protection에 프로그래밍 방식으로 액세스할 수 있도록 응용 프로그램을 만드는 방법에 대해 설명 합니다. 사용자를 대신 하 여 Microsoft Threat Protection에 프로그래밍 방식으로 액세스 해야 하는 경우에는 [사용자 컨텍스트를 사용 하 여 액세스 권한을](api-create-app-user-context.md)참조 하세요. 필요한 액세스를 모르는 경우 [시작 하기](api-access.md)를 참조 하세요.

Microsoft Threat Protection은 대부분의 데이터와 작업을 다양 한 Api 집합을 통해 제공 합니다. 이러한 Api를 사용 하면 Microsoft 위협 방지 기능을 기반으로 작업 흐름과를 자동으로 자동화할 수 있습니다. API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다. 자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.

일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.
- Azure AD (Active Directory) 응용 프로그램을 만듭니다.
- 이 응용 프로그램을 사용 하 여 액세스 토큰을 가져옵니다.
- 토큰을 사용 하 여 Microsoft Threat Protection API에 액세스 합니다.

이 문서에서는 Azure AD 응용 프로그램을 만들고, Microsoft 위협 보호에 액세스 토큰을 가져오고, 토큰의 유효성을 검사 하는 방법에 대해 설명 합니다.

## <a name="create-an-app"></a>앱 만들기

1. **전역 관리자** 역할이 있는 사용자를 사용 하 여 [Azure](https://portal.azure.com) 에 로그온 합니다.

2. **Azure Active Directory**  >  **앱 등록**  >  **새 등록**으로 이동 합니다. 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. 등록 양식에서 응용 프로그램의 이름을 선택한 다음 **레지스터**를 선택 합니다.

4. 앱이 Microsoft threat protection에 액세스 하 고 사용 권한을 할당할 수 있도록 하려면 응용 프로그램 페이지에서 **api 사용**권한 api를 선택  >  **Add permission**  >  합니다.**내 조직에서 사용 하는** >에는 **microsoft threat protection**을 입력 한 다음 **microsoft**threat protection을 선택 합니다.

   > [!NOTE]
   > Microsoft Threat Protection이 원래 목록에 표시 되지 않습니다. 텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.

   ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)

   - **응용 프로그램 사용 권한** > 시나리오에 관련 된 사용 권한 (예: **읽음**)을 선택 하 고 **사용 권한 추가**를 선택 합니다.

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >시나리오에 대 한 관련 권한을 선택 해야 합니다. **' 모든 문제 읽기 '** 는 단지 예 일 뿐입니다. 필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요.

5. **동의 허용**을 선택 합니다.

     > [!NOTE]
     > 사용 권한을 추가할 때마다 새 사용 권한을 적용 하려면 **동의 허용** 을 선택 해야 합니다.

    ![권한 부여 이미지](../../media/grant-consent.PNG)

6. 응용 프로그램에 비밀을 추가 하려면 **인증서 & 비밀**을 선택 하 고 비밀에 대 한 설명을 추가한 다음 **추가**를 선택 합니다.

    > [!NOTE]
    > **추가**를 선택한 후에 **는 생성 된 비밀 값 복사**를 선택 합니다. 나간 후에는이 값을 검색할 수 없습니다.

    ![앱 만들기 키의 이미지](../../media/webapp-create-key2.png)

7. 응용 프로그램 ID 및 테 넌 트 ID를 적어 둡니다. 응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.

   ![만든 앱 id의 이미지](../../media/app-and-tenant-ids.png)

8. **Microsoft Threat Protection 파트너에만**해당 합니다. [지침을 따릅니다](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access). 앱이 여러 tenanted (동의 후 모든 테 넌 트에서 사용 가능)로 설정 합니다. 이는 타사 앱 (예: 여러 고객의 테 넌 트에서 실행 하기 위한 앱을 만드는 경우)에 **필요** 합니다. 테 넌 트에만 실행 하려는 서비스를 만드는 경우에는이 작업을 수행할 필요가 **없습니다** (예: 자신만의 데이터와 상호 작용 하는 응용 프로그램을 만드는 경우). 앱을 다중 tenanted 설정 하려면 다음을 수행 합니다.

    - **인증**으로 이동 하 고 https://portal.azure.com **리디렉션 URI**로 추가 합니다.

    - 페이지 아래쪽의 **지원 되는 계정 유형**아래에서 다중 테 넌 트 앱에 대 한 조직 디렉터리 응용 프로그램 동의 **에서 계정을** 선택 합니다.

    응용 프로그램이 사용 하려는 각 테 넌 트에서 승인 되도록 해야 합니다. 이는 응용 프로그램이 고객을 대신 하 여 Microsoft Threat Protection을 상호 작용 하기 때문입니다.

    사용자 (또는 타사 앱을 작성 하는 경우) 동의 링크를 선택 하 고 앱을 승인 해야 합니다. Active Directory에 관리 권한이 있는 사용자에 대 한 동의를 수행 해야 합니다.

    승인 링크는 다음과 같이 구성 됩니다. 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    여기에서 00000000-0000-0000-0000-000000000000는 응용 프로그램 ID로 대체 됩니다.


**수행!** 응용 프로그램을 성공적으로 등록 했습니다! 토큰 획득 및 유효성 검사에 대 한 아래 예제를 참조 하세요.

## <a name="get-an-access-token"></a>액세스 토큰 가져오기

Azure AD 토큰에 대 한 자세한 내용은 [AZURE ad 자습서](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)를 참조 하세요.

### <a name="use-powershell"></a>PowerShell 사용

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>C #을 사용 합니다.

다음 코드는 Nuget Microsoft.identitymodel ActiveDirectory 3.19.8에서 테스트 되었습니다.

1. 새 콘솔 응용 프로그램을 만듭니다.
1. Nuget Microsoft.identitymodel을 설치 합니다 [.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
1. 다음을 추가 합니다.

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 응용 프로그램에 다음 코드를 복사 하 여 붙여넣습니다 (세 가지 변수를 업데이트 하는 것을 잊지 않음 ```tenantId, appId, appSecret``` ).

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Python 사용 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

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
### <a name="use-curl"></a>말아 넘기기 사용

> [!NOTE]
> 다음 절차에서는 Windows 용 말아 넘기기가 컴퓨터에 이미 설치 되어 있는 것으로 가정 합니다.

1. 명령 프롬프트를 열고 CLIENT_ID를 Azure 응용 프로그램 ID로 설정 합니다.
1. CLIENT_SECRET Azure application SECRET로 설정 합니다.
1. 앱을 사용 하 여 Microsoft Threat Protection에 액세스 하려는 고객의 Azure 테 넌 트 ID로 TENANT_ID를 설정 합니다.
1. 다음 명령을 실행합니다.

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

다음 형식으로 대답을 얻을 수 있습니다.

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>토큰 유효성 검사

올바른 토큰을가지고 있는지 확인 합니다.

1. 이전 단계에서 얻은 토큰을 복사 하 여 [디코딩하여에 붙여](https://jwt.ms) 넣습니다.
1. 원하는 사용 권한으로 ' 역할 ' 클레임이 제공 되는지 확인 합니다.
1. 다음 그림에서는 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 및 사용 권한으로 앱에서 얻은 디코딩된 토큰을 볼 수 있습니다 ```AdvancedHunting.Read.All``` .

![토큰 유효성 검사 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>토큰을 사용 하 여 Microsoft Threat Protection API 액세스

1. 사용할 API를 선택 합니다. 자세한 내용은 [지원 되는 Microsoft Threat Protection api](api-supported.md)를 참조 하세요.

2. 전송 하는 http 요청에서 "전달자 {토큰}"으로 보내는 인증 헤더를 설정 합니다 (전달자는 인증 체계).

3. 토큰의 만료 시간은 1 시간입니다. 동일한 토큰을 사용 하 여 두 개 이상의 요청을 보낼 수 있습니다.

다음은 **c #을 사용 하 여**인시던트 목록을 가져오기 위한 요청을 보내는 예입니다. 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>관련 항목
- [Microsoft Threat Protection Api 액세스](api-access.md)
- [응용 프로그램 컨텍스트를 사용 하 여 Microsoft 위협 방지 액세스](api-create-app-web.md)
- [사용자 컨텍스트를 사용 하 여 Microsoft Threat Protection에 액세스](api-create-app-user-context.md)

---
title: Microsoft 365 Defender API를 통한 파트너 액세스
description: 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 방식의 액세스 권한을 부여하는 앱을 만드는 방법을 배워야 합니다.
keywords: 파트너, 액세스, api, 다중 테넌트, 동의, 액세스 토큰, 앱
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 07afb0baf5c115f2029abfe03795b081a4f253a8
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929401"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Microsoft 365 Defender API에 대한 파트너 액세스가 있는 앱 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

이 페이지에서는 여러 테넌트의 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 방식의 액세스 권한이 있는 Azure Active Directory 앱을 만드는 방법을 설명합니다. 다중 테넌트 앱은 대규모 사용자 그룹을 제공하는 데 유용합니다.

단일 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 액세스해야 하는 경우 사용자 대신 [Microsoft 365 Defender API에](api-create-app-user-context.md)액세스하는 앱 만들기를 참조하세요. 사용자가 명시적으로 정의되지 않은 액세스가 필요한 경우(예: 백그라운드 앱 또는 디먼을 작성하는 경우) 사용자 없이 [Microsoft 365 Defender에](api-create-app-web.md)액세스하기 위한 앱 만들기를 참조하세요. 필요한 액세스 종류가 확실하지 않은 경우 [시작을 참조합니다.](api-access.md)

Microsoft 365 Defender는 프로그래밍 API 집합을 통해 많은 데이터 및 작업을 노출합니다. 이러한 API는 워크플로를 자동화하고 Microsoft 365 Defender의 기능을 활용하는 데 도움이 됩니다. 이 API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 권한 부여 코드 흐름을 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

일반적으로 이러한 API를 사용하려면 다음 단계를 수행해야 합니다.

- Azure AD(Azure Active Directory) 응용 프로그램을 만드십시오.
- 이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.
- 토큰을 사용하여 Microsoft 365 Defender API에 액세스합니다.

이 앱은 다중 테넌트이기 때문에 [](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 사용자를 대신하여 각 테넌트의 관리자 동의도 필요합니다.

이 문서에서는 방법을 설명합니다.

- 다중 **테넌트** Azure AD 응용 프로그램 만들기
- 응용 프로그램에 대한 사용자 관리자의 승인을 얻어 필요한 Microsoft 365 Defender에 액세스합니다.
- Microsoft 365 Defender에 대한 액세스 토큰 다운로드
- 토큰 유효성 검사

Microsoft 365 Defender는 프로그래밍 API 집합을 통해 많은 데이터 및 작업을 노출합니다. 이러한 API는 Microsoft 365 Defender 기능을 기반으로 작업 흐름을 자동화하고 혁신하는 데 도움이 됩니다. API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 권한 부여 코드 흐름을 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.

- 다중 **테넌트** Azure AD 응용 프로그램을 만들 수 있습니다.
- 응용 프로그램에 대한 사용자 관리자가 필요한 Microsoft 365 Defender 리소스에 액세스하도록 승인(동의)합니다.
- 이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.
- 토큰을 사용하여 Microsoft 365 Defender API에 액세스합니다.

다중 테넌트 Azure AD 응용 프로그램을 만들고, Microsoft 365 Defender에 대한 액세스 토큰을 다운로드하고, 토큰의 유효성을 검사하는 방법을 안내하는 다음 단계를 안내합니다.

## <a name="create-the-multi-tenant-app"></a>다중 테넌트 앱 만들기

1. 전역 관리자 역할을 사용하여 [Azure에](https://portal.azure.com) **사용자로 로그인합니다.**

2. Azure **Active Directory**  >  **앱 등록 새**  >  **등록으로 이동합니다.**

   ![Microsoft Azure의 이미지 및 응용 프로그램 등록 탐색](../../media/atp-azure-new-app2.png)

3. 등록 양식에 다음이 있습니다.

   - 응용 프로그램의 이름을 선택하십시오.
   - 지원되는 **계정 유형에서** 모든 조직 디렉터리(모든 **Azure AD 디렉터리) - 다중텐트에서 계정을 선택합니다.**
   - 리디렉션 **URI 섹션을 작성합니다.** 웹 **형식을 선택하고** 리디렉션 URI를 **https://portal.azure.com** .로 제공

   양식 작성을 완료한 후 등록을 **선택합니다.**

   ![응용 프로그램 등록 양식의 이미지](../..//media/atp-api-new-app-partner.png)

4. 응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 API를 선택하고 > Microsoft Threat Protection을 입력한 다음  >    >   Microsoft **Threat Protection을 선택합니다.**  이제 앱이 Microsoft 365 Defender에 액세스할 수 있습니다.

   > [!TIP]
   > *Microsoft 위협 방지는* Microsoft 365 Defender의 이전 이름으로, 원래 목록에는 나타나지 않습니다. 표시하려면 텍스트 상자에 해당 이름을 쓰기 시작해야 합니다.

   ![API 권한 선택 이미지](../../media/apis-in-my-org-tab.PNG)

5. 응용 **프로그램 사용 권한을 선택합니다.** 시나리오에 대한 관련 사용 권한(예: **Incident.Read.All)을** 선택한 다음 사용 권한 **추가를 선택합니다.**

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > 시나리오에 대한 관련 사용 권한을 선택해야 합니다. *모든 인시던트 읽기는* 예시일 수 있습니다. 필요한 사용 권한을 확인하려면 호출할 API의 **사용** 권한 섹션을 참조하세요.
    >
    > 예를 들어 고급 [쿼리를 실행하려면](api-advanced-hunting.md)'고급 쿼리 실행' 권한을 선택합니다. 장치를 [격리하려면](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)'컴퓨터 격리' 권한을 선택합니다.

6. 관리자 **동의 부여를 선택합니다.** 권한을 추가할 때마다 권한을 적용하려면  관리자 동의 부여를 선택해야 합니다.

    ![권한 부여 이미지](../../media/grant-consent.PNG)

7. 응용 프로그램에 비밀을 추가하려면 인증서를 선택하고 & 설명을 추가한 다음 추가를 **선택합니다.**

    > [!TIP]
    > 추가를 **선택한 후** 생성된 **비밀 값 복사를 선택합니다.** 나가면 비밀 값을 검색할 수 없습니다.

    ![앱 키 만들기 이미지](../../media/webapp-create-key2.png)

8. 안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다. 응용 프로그램 페이지의 **개요** 아래에 나열됩니다.

   ![생성된 앱 ID의 이미지](../../media/app-and-tenant-ids.png)

9. 사용자의 테넌트에 응용 프로그램을 추가합니다.

   응용 프로그램이 사용자를 대신하여 Microsoft 365 Defender와 상호 작용하기 때문에 응용 프로그램을 사용하려는 모든 테넌트에 대해 승인이 필요합니다.

   사용자 **테넌트의** 전역 관리자는 동의 링크를 보고 응용 프로그램을 승인해야 합니다.

   동의 링크 형식:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   숫자는 `00000000-0000-0000-0000-000000000000` 응용 프로그램 ID로 바야 합니다.

   동의 링크를 클릭한 후 사용자의 테넌트의 전역 관리자에게 로그인하고 응용 프로그램에 동의합니다.

   ![동의 이미지](../../media/app-consent-partner.png)

   또한 테넌트 ID를 사용자에게 요청해야 합니다. 테넌트 ID는 액세스 토큰을 획득하는 데 사용되는 식별자 중 하나입니다.

- **완료!** 응용 프로그램을 성공적으로 등록했습니다.
- 토큰 획득 및 유효성 검사는 아래 예제를 참조하세요.

## <a name="get-an-access-token"></a>액세스 토큰을 얻게 됩니다.

Azure AD 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> 이 섹션의 예제에서는 테스트 목적으로 비밀 값에 붙여 넣는 것이 까다로우지만 프로덕션에서 실행되는 응용 프로그램에 암호를 하드코드하면 안 됩니다.  제3자에서 사용자 비밀을 사용하여 리소스에 액세스할 수 있습니다. Azure Key Vault를 사용하여 앱의 비밀을 안전하게 [유지할 수 있습니다.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) 앱을 보호하는 방법에 대한 실제 예제는 Azure Key Vault를 사용하여 서버 앱의 암호 [관리를 참조하세요.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)

> [!TIP]
> 다음 예제에서는 사용자의 테넌트 ID를 사용하여 스크립트가 작동하고 있는지 테스트합니다.

### <a name="get-an-access-token-using-powershell"></a>PowerShell을 사용하여 액세스 토큰 얻기

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a>C를 사용하여 액세스 토큰 얻기\#

> [!NOTE]
> 다음 코드는 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8을 사용하여 테스트되었습니다.

1. 새 콘솔 응용 프로그램을 만들 수 있습니다.
1. NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory를 설치합니다.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
1. 다음 줄을 추가합니다.

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 다음 코드를 복사하여 앱에 붙여 넣습니다(세 가지 변수를 업데이트하는 것을 잊지 마세요. `tenantId` `clientId` , , `appSecret` ):

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>Python을 사용하여 액세스 토큰 얻기

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>컬을 사용하여 액세스 토큰 얻기

> [!NOTE]
> 컬은 Windows 10 버전 1803 이상에 미리 설치되어 있습니다. 다른 버전의 Windows의 경우 공식 컬 웹 사이트에서 직접 도구를 [다운로드하여 설치합니다.](https://curl.haxx.se/windows/)

1. 명령 프롬프트를 열고 azure CLIENT_ID ID로 설정하십시오.
1. Azure CLIENT_SECRET 비밀로 설정하세요.
1. 앱을 TENANT_ID Microsoft 365 Defender에 액세스하려는 사용자의 Azure 테넌트 ID로 설정할 수 있습니다.
1. 다음 명령을 실행합니다.

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

성공적인 응답은 다음과 같습니다.

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>토큰 유효성 검사

1. 토큰을 복사하여 JSON 웹 토큰 유효성 검사 웹 사이트 [JWT에](https://jwt.ms) 붙여넣어 디코드합니다.
1. 디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인

다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 토큰을 ```AdvancedHunting.Read.All``` 볼 수 있습니다.

![토큰 유효성 검사의 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>토큰을 사용하여 Microsoft 365 Defender API 액세스

1. 사용할 API(인시던트 또는 고급 헌팅)를 선택하십시오. 자세한 내용은 지원되는 [Microsoft 365 Defender API를 참조하세요.](api-supported.md)
2. 보낼 http 요청에서 권한 부여 헤더를 권한 부여 체계인 Bearer로 설정하고 유효성이 검사된 토큰인 `"Bearer" <token>` 토큰을 사용합니다.  
3. 토큰은 1시간 이내에 만료됩니다. 이 시간 동안 동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.

다음 예에서는 C#을 사용하여 인시던트 목록을 들이는 요청을 **보내는 방법을 보여 주며,**

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 Defender API 개요](api-overview.md)
- [Microsoft 365 Defender API 액세스](api-access.md)
- ['Hello world' 응용 프로그램 만들기](api-hello-world.md)
- [사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기](api-create-app-web.md)
- [사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기](api-create-app-user-context.md)
- [API 제한 및 라이선싱에 대해 자세히](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
- [Azure Key Vault를 사용하여 서버 앱의 비밀 관리](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

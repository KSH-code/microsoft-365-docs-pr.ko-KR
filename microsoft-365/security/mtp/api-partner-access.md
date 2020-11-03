---
title: Microsoft 365 Defender Api를 통한 파트너 액세스
description: 고객을 대신 하 여 Microsoft 365 Defender에 프로그래밍 방식으로 액세스할 수 있도록 AAD 응용 프로그램을 만드는 방법을 알아봅니다.
keywords: 파트너, 액세스, api, 다중 테 넌 트, 동의, 액세스 토큰, 앱
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
ms.openlocfilehash: eb40d5d2d82f57be225515ad0aa566038397bbbd
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844987"
---
# <a name="partner-access-through-microsoft-365-defender-apis"></a>Microsoft 365 Defender Api를 통한 파트너 액세스

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


이 페이지에서는 고객을 대신 하 여 Microsoft 365 Defender에 프로그래밍 방식으로 액세스할 수 있도록 AAD 응용 프로그램을 만드는 방법에 대해 설명 합니다.

Microsoft 365 Defender는 프로그래밍 Api 집합을 통해 대부분의 데이터와 작업을 제공 합니다. 이러한 Api는 Microsoft 365 Defender 기능을 기반으로 하는 워크플로 및 작업 흐름을 자동화 하는 데 도움이 됩니다. API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다. 자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.

일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.
- **다중 테 넌 트** AAD 응용 프로그램을 만듭니다.
- 고객 관리자가 필요한 Microsoft 365 Defender 리소스에 액세스 하려면 해당 응용 프로그램에 대 한 승인 된 (동의)를 받습니다.
- 이 응용 프로그램을 사용 하 여 액세스 토큰을 가져옵니다.
- 토큰을 사용 하 여 Microsoft 365 Defender API에 액세스 합니다.

다음 단계에서는 AAD 응용 프로그램을 만들어 Microsoft 365 Defender에 액세스 토큰을 가져오고 토큰의 유효성을 검사 하는 방법에 대해 설명 합니다.

## <a name="create-the-multi-tenant-app"></a>다중 테 넌 트 앱 만들기

1. **전역 관리자** 역할이 있는 사용자로 [Azure 테 넌 트](https://portal.azure.com) 에 로그온 합니다.

2. **Azure Active Directory**  >  **앱 등록**  >  **새 등록** 으로 이동 합니다. 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. 등록 양식에서 다음을 수행 합니다.

    - 응용 프로그램의 이름을 선택 합니다.

    - 지원 되는 계정 유형-모든 조직 디렉터리의 계정입니다.

    - 리디렉션 URI-유형: Web, URI: https://portal.azure.com

    ![Microsoft Azure 파트너 응용 프로그램 등록의 이미지](../../media/atp-api-new-app-partner.png)


4. 응용 프로그램에서 Microsoft 365 Defender에 액세스 하 고 통합을 완료 하는 데 필요한 최소한의 사용 권한 집합을 할당할 수 있도록 허용 합니다.

   - 응용 프로그램 페이지에서 **API 사용 권한을** 클릭  >  **Add permission**  >  **하 고 조직에서 사용 하는** 사용 권한 api 추가 > **microsoft 365 defender** 를 입력 하 고 **microsoft 365 defender** 를 클릭 합니다.

   >[!NOTE]
   >Microsoft 365 Defender가 원래 목록에 표시 되지 않습니다. 텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.

   ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a>API 사용 권한 요청

   필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요. 

   다음 예제에서는 **' 모든 인시던트 읽기 '** 권한을 사용 합니다.

   **응용 프로그램 사용 권한**  >  **인시던트를** 선택 합니다. 모두 > **사용 권한 추가** 를 클릭 합니다.

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)


5. **동의 허용** 을 클릭 합니다.

    >[!NOTE]
    >사용 권한을 추가할 때마다 새 사용 권한에 대 한 **동의 부여** 를 클릭 하 여 적용 해야 합니다.

    ![권한 부여 이미지](../../media/grant-consent.PNG)

6. 응용 프로그램에 비밀을 추가 합니다.

    - **인증서 & 비밀** 을 클릭 하 고, 비밀에 설명을 추가 하 고, **추가** 를 클릭 합니다.

    >[!IMPORTANT]
    > **추가** 를 선택한 후에 **생성 된 비밀 값을 복사** 합니다. 나간 후에는 검색할 수 없게 됩니다.

    ![앱 만들기 키의 이미지](../../media/webapp-create-key2.png)

7. 응용 프로그램 ID를 적어 둡니다.

   - 응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.

   ![만든 앱 id의 이미지](../../media/app-id.png)

8. 고객의 테 넌 트에 응용 프로그램을 추가 합니다.

    응용 프로그램이 사용 하려는 각 고객 테 넌 트에서 승인 되도록 해야 합니다. 이는 응용 프로그램이 고객을 대신 하 여 Microsoft 365 Defender 응용 프로그램과 상호 작용 하기 때문입니다.

    고객의 테 넌 트의 **전역 관리자** 가 있는 사용자는 동의 링크를 클릭 하 고 응용 프로그램을 승인 해야 합니다.

    승인 링크 형식은 다음과 같습니다.

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    여기서 00000000-0000-0000-0000-000000000000는 응용 프로그램 ID로 교체 해야 합니다.

    승인 링크를 클릭 한 후에는 고객의 테 넌 트의 전역 관리자에 로그인 하 여 응용 프로그램에 동의 합니다.

    ![승인 이미지](../../media/app-consent-partner.png)

    또한 고객에 게 해당 테 넌 트 ID를 묻고 토큰을 취득할 때 나중에 사용할 수 있도록 저장 해야 합니다.

- **수행!** 응용 프로그램을 성공적으로 등록 했습니다! 
- 토큰 획득 및 유효성 검사에 대 한 아래 예제를 참조 하세요.

## <a name="get-an-access-token-examples"></a>액세스 토큰 예제를 가져옵니다.

>[!NOTE]
> 고객을 대신 하 여 액세스 토큰을 가져오려면 다음 토큰 합병에 고객의 테 넌 트 ID를 사용 합니다.

<br>AAD 토큰에 대 한 자세한 내용은 [aad 자습서](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds) 를 참조 하세요.

### <a name="using-powershell"></a>PowerShell 사용

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

### <a name="using-c"></a>C # 사용

>다음 코드는 Nuget Microsoft.identitymodel를 사용 하 여 테스트 되었습니다. ActiveDirectory

- 새 콘솔 응용 프로그램 만들기
- Nuget [microsoft.identitymodel을](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) 설치 합니다. ActiveDirectory
- 다음을 사용 하 여 다음을 추가 합니다.

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- 응용 프로그램에서 아래 코드를 복사/붙여 넣습니다 (3 개의 변수를 업데이트 하는 것을 잊지 않음 ```tenantId, appId, appSecret``` ).

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a>말아 넘기기 사용

> [!NOTE]
> Windows 용 말아 넘기기가 컴퓨터에 이미 설치 되어 있는 절차

- 명령 창 열기
- Azure 응용 프로그램 ID로 CLIENT_ID 설정
- Azure 응용 프로그램 비밀으로 CLIENT_SECRET 설정
- 응용 프로그램을 사용 하 여 Microsoft 365 Defender 응용 프로그램에 액세스 하려는 고객의 Azure 테 넌 트 ID로 TENANT_ID 설정
- 다음 명령을 실행 합니다.

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

다음과 같은 양식의 대답이 제공 됩니다.

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>토큰 유효성 검사

온전성 검사를 통해 올바른 토큰이 있는지 확인 합니다.

- [JWT](https://jwt.ms) 에 복사/붙여넣기 이전 단계에서 가져오는 토큰을 디코드 합니다.
- ' 역할 ' 클레임이 원하는 사용 권한으로 제공 되는지 확인
- 아래 스크린샷에서는 Microsoft 365 Defender에 대 한 여러 권한을 가진 응용 프로그램에서 얻은 디코딩된 토큰을 확인할 수 있습니다.
- "Tid" 클레임은 토큰이 속해 있는 테 넌 트 ID입니다.

![토큰 유효성 검사 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a>토큰을 사용 하 여 Microsoft 365 Defender API에 액세스

- 사용할 API 선택 자세한 내용은 [지원 되는 Microsoft 365 Defender api](api-supported.md) 를 참조 하세요.
- 전송 하는 Http 요청에서 "전달자 {토큰}"으로 보내는 인증 헤더 설정 (전달자는 인증 체계)
- 토큰의 만료 시간은 1 시간 (동일한 토큰을 사용 하 여 요청을 하나 이상 보낼 수 있음)

- **C #을 사용 하 여** 인시던트 목록을 가져오기 위한 요청을 보내는 예제 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a>관련 항목 

- [Microsoft 365 Defender Api 액세스](api-access.md)
- [응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender에 액세스](api-create-app-web.md)
- [사용자 컨텍스트를 사용 하 여 Microsoft 365 Defender 액세스](api-create-app-user-context.md)

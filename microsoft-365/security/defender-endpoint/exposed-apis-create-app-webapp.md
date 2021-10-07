---
title: 사용자 없이 끝점용 Microsoft Defender에 액세스하는 앱 만들기
ms.reviewer: ''
description: 사용자 없이 끝점용 Microsoft Defender에 프로그래밍 방식 액세스 권한을 부여하도록 웹앱을 디자인하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 배우, 경고, 장치, 사용자, 도메인, ip, 파일, 고급 헌팅, 쿼리
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d98a642450dd47088446144db01fab0a73e24855
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157977"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>사용자 없이 끝점용 Microsoft Defender에 액세스하는 앱 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

이 페이지에서는 사용자가 없는 끝점용 Defender에 프로그래밍 방식 액세스 권한을 부여하는 응용 프로그램을 만드는 방법을 설명합니다. 사용자를 대신하여 Endpoint용 Defender에 프로그래밍식 액세스 권한이 필요한 경우 사용자 컨텍스트를 통해 [액세스하기를 참조합니다.](exposed-apis-create-app-nativeapp.md) 필요한 액세스 권한이 확실하지 않은 경우 [시작을 참조합니다.](apis-intro.md)

끝점용 Microsoft Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API는 작업 흐름을 자동화하고 끝점용 Defender 기능을 기반으로 혁신하는 데 도움이 됩니다. API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.
- Azure AD(Azure Active Directory 응용 프로그램을 만들 수 있습니다.
- 이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.
- 토큰을 사용하여 Endpoint API용 Defender에 액세스합니다.

이 문서에서는 Azure AD 응용 프로그램을 만들고, 끝점용 Microsoft Defender에 대한 액세스 토큰을 다운로드하고, 토큰의 유효성을 검사하는 방법을 설명합니다.

## <a name="create-an-app"></a>앱 만들기

1. 전역 관리자 역할이 있는 사용자로 [Azure에](https://portal.azure.com) **로그온합니다.**

2. 앱 등록 **Azure Active Directory** \> **새** \> **등록으로 이동합니다.** 

   ![응용 프로그램 Microsoft Azure 탐색하는 이미지입니다.](images/atp-azure-new-app2.png)

3. 등록 양식에서 응용 프로그램의 이름을 선택한 다음 등록을 **선택합니다.**

4. 앱이 끝점용 Defender에 액세스하여 '모든 경고 **읽기'** 권한을 할당할 수 있도록 설정하려면 응용 프로그램 페이지에서 **API** 사용 권한 추가 권한 API를 선택하고 > \>  \>  **WindowsDefenderATP를 입력한 다음 WindowsDefenderATP를** 선택합니다. 

   > [!NOTE]
   > *WindowsDefenderATP는* 원래 목록에 나타나지 않습니다. 텍스트 상자에 이름을 입력하여 표시를 시작하십시오.

   ![사용 권한을 추가합니다.](images/add-permission.png)

   - 응용 **프로그램 권한** \> **Alert.Read.All** 을 선택한 다음 사용 권한 **추가를 선택합니다.**

   ![앱 사용 권한.](images/application-permissions.png)

     관련 권한을 선택해야 합니다. '모든 경고 읽기'는 예일 뿐입니다. 예:

     - 고급 [쿼리를 실행하려면](run-advanced-query-api.md)'고급 쿼리 실행' 권한을 선택합니다.
     - 장치를 [격리하려면](isolate-machine.md)'컴퓨터 격리' 권한을 선택합니다.
     - 필요한 사용 권한을 확인하려면 호출할 API의 사용 권한 섹션을 참조하세요. 

5. 동의 **부여를 선택합니다.**

     > [!NOTE]
     > 권한을 추가할 때마다 새 사용 권한을 **적용하기** 위해 동의 부여를 선택해야 합니다.

    ![사용 권한을 부여합니다.](images/grant-consent.png)

6. 응용 프로그램에 비밀을 추가하려면 인증서 & **를** 선택하고 비밀에 설명을 추가한 다음 추가를 **선택합니다.**

    > [!NOTE]
    > 추가를 **선택한** 후 생성된 **비밀 값 복사 를 선택합니다.** 나가면 이 값을 검색할 수 없습니다.

    ![앱 키 만들기의 이미지입니다.](images/webapp-create-key2.png)

7. 응용 프로그램 ID와 테넌트 ID를 기록해 써야 합니다. 응용 프로그램 페이지에서 개요로 이동하여 **다음을** 복사합니다.

   ![생성된 앱 ID의 이미지입니다.](images/app-and-tenant-ids.png)

8. **끝점 파트너용 Microsoft Defender의 경우만 입니다.** 앱을 다중 테넌트로 설정(동의 후 모든 테넌트에서 사용 가능) 타사 **앱(예:** 여러 고객의 테넌트에서 실행되는 앱을 만드는 경우)에 필요합니다. 테넌트에서만 실행할 서비스를 만드는 경우(예: 자체 데이터와만 상호 작용하는 응용 프로그램을 직접 만드는 경우)에는 필요하지 않습니다.  앱을 다중 테넌트로 설정하는 경우:

    - 인증으로 **이동하여** `https://portal.azure.com` 리디렉션 **URI로 추가합니다.**

    - 페이지 아래쪽의 지원되는 계정 유형에서 다중  테넌트 앱에 대한 조직 디렉터리 응용 프로그램 동의의 계정을 선택합니다.

    응용 프로그램을 사용하려는 각 테넌트에서 응용 프로그램을 승인해야 합니다. 이는 응용 프로그램이 고객을 대신하여 끝점용 Defender와 상호 작용하기 때문에입니다.

    사용자(또는 타사 앱을 작성하는 경우 고객)는 동의 링크를 선택하고 앱을 승인해야 합니다. Active Directory에 관리 권한이 있는 사용자와 동의해야 합니다.

    동의 링크는 다음과 같이 구성됩니다. 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    여기서 000000000-0000-0000-0000-000000000000은 응용 프로그램 ID로 대체됩니다.


**완료!** 응용 프로그램을 성공적으로 등록했습니다. 토큰 획득 및 유효성 검사에 대한 자세한 내용은 아래 예제를 참조하세요.

## <a name="get-an-access-token"></a>액세스 토큰을 얻게 됩니다.

Azure AD 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="use-powershell"></a>PowerShell 사용

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
```

### <a name="use-c"></a>다음 C#.

다음 코드는 Microsoft.IdentityModel.Clients.NuGet 3.19.8을 사용하여 테스트되었습니다.

1. 새 콘솔 응용 프로그램을 만들 수 있습니다.
1. [Microsoft.NuGet.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)를 설치합니다.
1. 다음을 추가합니다.

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 앱에서 다음 코드를 복사하여 붙여넣습니다(세 개의 변수를 업데이트하는 것을 잊지 마세요. ```tenantId, appId, appSecret``` ):

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Python 사용

[Python을 사용하여 토큰을 얻습니다.를 참조합니다.](run-advanced-query-sample-python.md#get-token)

### <a name="use-curl"></a>컬 사용

> [!NOTE]
> 다음 절차에서는 컴퓨터에 Windows Curl이 이미 설치되어 있는 것으로 가정합니다.

1. 명령 프롬프트를 열고 azure CLIENT_ID ID로 설정하십시오.
1. Azure CLIENT_SECRET 비밀로 설정하세요.
1. 앱을 TENANT_ID 끝점용 Defender에 액세스하려는 고객의 Azure 테넌트 ID로 설정할 수 있습니다.
1. 다음 명령을 실행합니다.

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

다음 형식의 답변을 얻게 됩니다.

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>토큰 유효성 검사

올바른 토큰이 올바른지 확인합니다.

1. 이전 단계에서 사용한 토큰을 복사하여 [JWT에](https://jwt.ms) 붙여넣어 디코딩합니다.
1. 원하는 사용 권한으로 '역할' 클레임이 유효한지 확인
1. 다음 이미지에서는 끝점의 모든 역할에 대한 사용 권한이 있는 앱에서 획득한 디코딩된 토큰을 볼 수 있습니다.

![토큰 유효성 검사의 이미지입니다.](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>토큰을 사용하여 끝점 API용 Microsoft Defender에 액세스

1. 사용할 API를 선택 합니다. 자세한 내용은 [Supported Defender for Endpoint API를 참조하세요.](exposed-apis-list.md)
1. "Bearer {token}"(Bearer는 권한 부여 체계)으로 보내는 http 요청에서 권한 부여 헤더를 설정하십시오.
1. 토큰의 만료 시간은 1시간입니다. 동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.

다음 예는 다음을 사용하여 경고 목록을 을(를) 요청하는 **C#.** 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a>참고 항목
- [지원되는 엔드포인트용 Microsoft Defender API](exposed-apis-list.md) 
- [사용자를 대신하여 끝점용 Microsoft Defender 액세스](exposed-apis-create-app-nativeapp.md)

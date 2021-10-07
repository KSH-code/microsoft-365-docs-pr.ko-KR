---
title: REST API용 Hello World Microsoft 365 Defender API
description: 앱을 만들고 토큰을 사용하여 앱 API에 액세스하는 Microsoft 365 Defender 방법
keywords: 앱, 토큰, 액세스, aad, 앱, 응용 프로그램 등록, powershell, 스크립트, 전역 관리자, 사용 권한, Microsoft 365 defender
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
ms.openlocfilehash: 9b4280999786cda02c183bb0eb03bea8c2c93c84
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202646"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>REST API용 Hello World Microsoft 365 Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

## <a name="get-incidents-using-a-simple-powershell-script"></a>간단한 PowerShell 스크립트를 사용하여 인시던트 발생

이 프로젝트를 완료하는 데 5~10분 정도 걸립니다. 이 예상 기간에는 응용 프로그램을 등록하고 PowerShell 샘플 스크립트의 코드를 적용하는 것이 포함됩니다.

### <a name="register-an-app-in-azure-active-directory"></a>앱에 Azure Active Directory

1. 전역 관리자 역할을 사용하여 [사용자로 Azure에](https://portal.azure.com) **로그인합니다.**

2. 앱 등록 **Azure Active Directory**  >  **새**  >  **등록으로 이동합니다.**

   ![응용 프로그램 Microsoft Azure 탐색하는 이미지입니다.](../../media/atp-azure-new-app2.png)

3. 등록 양식에서 응용 프로그램의 이름을 선택한 다음 등록을 **선택합니다.** 리디렉션 URI는 선택 사항입니다. 이 예제를 완료하는 데는 이 예제가 필요하지 않습니다.

4. 응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 api를 >  >    >   Microsoft **Threat Protection을** 입력하고 **Microsoft Threat Protection을 선택합니다.** 이제 앱에서 앱에 액세스할 Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection은* 이전 이름인 Microsoft 365 Defender 목록에 나타나지 않습니다. 표시하려면 텍스트 상자에 이름을 쓰기 시작해야 합니다.
   ![API 권한 선택의 이미지입니다.](../../media/apis-in-my-org-tab.PNG)

   - 응용 **프로그램 권한**  >  **Incident.Read.All을 선택하고** 사용 권한 **추가를 선택합니다.**

   ![API 액세스 및 API 선택 이미지입니다.](../../media/request-api-permissions.PNG)

5. 관리자 **동의 부여를 선택합니다.** 권한을 추가할 때마다 권한을 적용하려면 **관리자** 동의 부여를 선택해야 합니다.

    ![권한 부여 이미지.](../../media/grant-consent.PNG)

6. 응용 프로그램에 비밀을 추가합니다. 인증서를 **& 를 선택하고** 비밀에 설명을 추가한 다음 추가를 **선택합니다.**

    > [!TIP]
    > 추가를 **선택한** 후 생성된 **비밀 값 복사 를 선택합니다.** 나가면 비밀 값을 검색할 수 없습니다.

    ![앱 키 만들기의 이미지입니다.](../../media/webapp-create-key2.png)

7. 안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다. 응용 프로그램 페이지 **개요** 아래에 나열됩니다.

   ![생성된 앱 ID의 이미지입니다.](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>앱을 사용하여 토큰을 다운로드하고 토큰을 사용하여 API에 액세스

토큰에 대한 Azure Active Directory [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> 이 데모 앱의 예제에서는 테스트를 위해 비밀 값에 붙여 넣는 것이 까다로우지만 프로덕션에서 실행되는 응용 프로그램에 암호를 하드코드하면 안 됩니다.  제3자에서 해당 비밀을 사용하여 리소스에 액세스할 수 있습니다. Azure Key Vault를 사용하여 앱의 비밀을 안전하게 [유지할 수 있습니다.](/azure/key-vault/general/about-keys-secrets-certificates) 앱을 보호하는 방법에 대한 실제 예제는 Azure Key Vault를 사용하여 서버 앱의 암호 [관리를 참조하세요.](/learn/modules/manage-secrets-with-azure-key-vault/)

1. 아래 스크립트를 복사하여 즐겨 찾는 텍스트 편집기에 붙여 넣습니다. 을 로 **Get-Token.ps1.** PowerShell ISE에서 코드를 있는 있는 것으로 실행할 수도 있지만, 다음 섹션에서 인시던트 페치 스크립트를 사용할 때 다시 실행해야 하기 때문에 코드를 저장해야 합니다.

    이 스크립트는 토큰을 생성하고 의 이름 아래 작업 *폴더에Latest-token.txt.*

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a>토큰 유효성 검사

1. 받은 토큰을 [복사하여 JWT에](https://jwt.ms) 붙여넣어 디코딩합니다.
1. *JWT는* *JSON 웹 토큰을 지어 입니다.* 디코딩된 토큰에는 다양한 JSON 형식의 항목 또는 클레임이 포함되어 있습니다. 디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인

    다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 토큰을 볼 수 있습니다.

    ![이미지 jwt.ms.](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>최근 인시던트 목록 표시

아래 스크립트는 API에 **Get-Token.ps1** 데 사용할 것입니다. 그런 다음 지난 48시간 내에 마지막으로 업데이트된 인시던트 목록을 검색하고 목록을 JSON 파일로 저장합니다.

> [!IMPORTANT]
> 이 스크립트를 저장한 폴더와 동일한 폴더에 **Get-Token.ps1.**

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

모두 완료했습니다! 다음을 성공적으로 완료했습니다.

- 응용 프로그램을 만들어 등록했습니다.
- 해당 응용 프로그램에 대해 경고를 읽을 수 있는 권한이 부여됩니다.
- API에 연결됩니다.
- PowerShell 스크립트를 사용하여 지난 48시간 동안 업데이트된 인시던트 반환

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 Defender API 개요](api-overview.md)
- [MICROSOFT 365 DEFENDER API에 액세스](api-access.md)
- [사용자가 없는 앱에 액세스하는 Microsoft 365 Defender 만들기](api-create-app-web.md)
- [사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기](api-create-app-user-context.md)
- [다중 테넌트 파트너가 액세스하여 테넌트 API에 Microsoft 365 Defender 만들기](api-partner-access.md)
- [Azure Key Vault를 사용하여 서버 앱의 비밀 관리](/learn/modules/manage-secrets-with-azure-key-vault/)
- [사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
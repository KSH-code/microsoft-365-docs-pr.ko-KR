---
title: Microsoft 365 Defender REST API용 Hello World
description: 앱을 만들고 토큰을 사용하여 Microsoft 365 Defender API에 액세스하는 방법을 배우기
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072756"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="795cb-104">Microsoft 365 Defender REST API용 Hello World</span><span class="sxs-lookup"><span data-stu-id="795cb-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="795cb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="795cb-105">**Applies to:**</span></span>

- <span data-ttu-id="795cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="795cb-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="795cb-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="795cb-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="795cb-109">간단한 PowerShell 스크립트를 사용하여 인시던트 발생</span><span class="sxs-lookup"><span data-stu-id="795cb-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="795cb-110">이 프로젝트를 완료하는 데 5~10분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="795cb-111">이 예상 기간에는 응용 프로그램을 등록하고 PowerShell 샘플 스크립트의 코드를 적용하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="795cb-112">Azure Active Directory에 앱 등록</span><span class="sxs-lookup"><span data-stu-id="795cb-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="795cb-113">전역 관리자 역할을 사용하여 [사용자로 Azure에](https://portal.azure.com) **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="795cb-114">Azure **Active Directory**  >  **앱 등록 새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure의 이미지 및 응용 프로그램 등록 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="795cb-116">등록 양식에서 응용 프로그램의 이름을 선택한 다음 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="795cb-117">리디렉션 URI는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="795cb-118">이 예제를 완료하는 데는 이 예제가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="795cb-119">응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 api를 >  >    >   Microsoft **Threat Protection을** 입력하고 **Microsoft Threat Protection을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="795cb-120">이제 앱이 Microsoft 365 Defender에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="795cb-121">*Microsoft Threat Protection은* Microsoft 365 Defender의 이전 이름으로, 원래 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="795cb-122">표시하려면 텍스트 상자에 이름을 쓰기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="795cb-123">![API 권한 선택 이미지](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="795cb-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="795cb-124">응용 **프로그램 권한**  >  **Incident.Read.All을 선택하고** 사용 권한 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="795cb-126">관리자 **동의 부여를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="795cb-127">권한을 추가할 때마다 권한을 적용하려면 **관리자** 동의 부여를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![권한 부여 이미지](../../media/grant-consent.PNG)

6. <span data-ttu-id="795cb-129">응용 프로그램에 비밀을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-129">Add a secret to the application.</span></span> <span data-ttu-id="795cb-130">인증서를 **& 를 선택하고** 비밀에 설명을 추가한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="795cb-131">추가를 **선택한** 후 생성된 **비밀 값 복사 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="795cb-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="795cb-132">나가면 비밀 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![앱 키 만들기 이미지](../../media/webapp-create-key2.png)

7. <span data-ttu-id="795cb-134">안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="795cb-135">응용 프로그램 페이지 **개요** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-135">They're listed under **Overview** on your application page.</span></span>

   ![생성된 앱 ID의 이미지](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="795cb-137">앱을 사용하여 토큰을 다운로드하고 토큰을 사용하여 API에 액세스</span><span class="sxs-lookup"><span data-stu-id="795cb-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="795cb-138">Azure Active Directory 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="795cb-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="795cb-139">이 데모 앱의 예제에서는 테스트를 위해 비밀 값에 붙여 넣는 것이 까다로우지만 프로덕션에서 실행되는 응용 프로그램에 암호를 하드코드하면 안 됩니다. </span><span class="sxs-lookup"><span data-stu-id="795cb-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="795cb-140">제3자에서 해당 비밀을 사용하여 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="795cb-141">Azure Key Vault를 사용하여 앱의 비밀을 안전하게 [유지할 수 있습니다.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="795cb-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="795cb-142">앱을 보호하는 방법에 대한 실제 예제는 Azure Key Vault를 사용하여 서버 앱의 암호 [관리를 참조하세요.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="795cb-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="795cb-143">아래 스크립트를 복사하여 즐겨 찾는 텍스트 편집기에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="795cb-144">을 로 **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="795cb-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="795cb-145">PowerShell ISE에서 코드를 있는 있는 것으로 실행할 수도 있지만, 다음 섹션에서 인시던트 페치 스크립트를 사용할 때 다시 실행해야 하기 때문에 코드를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="795cb-146">이 스크립트는 토큰을 생성하고 의 이름 아래 작업 *폴더에Latest-token.txt.*</span><span class="sxs-lookup"><span data-stu-id="795cb-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="795cb-147">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="795cb-147">Validate the token</span></span>

1. <span data-ttu-id="795cb-148">받은 토큰을 [복사하여 JWT에](https://jwt.ms) 붙여넣어 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="795cb-149">*JWT는* *JSON 웹 토큰을 지어 입니다.*</span><span class="sxs-lookup"><span data-stu-id="795cb-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="795cb-150">디코딩된 토큰에는 다양한 JSON 형식의 항목 또는 클레임이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="795cb-151">디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="795cb-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="795cb-152">다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 토큰을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![이미지 jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="795cb-154">최근 인시던트 목록 표시</span><span class="sxs-lookup"><span data-stu-id="795cb-154">Get a list of recent incidents</span></span>

<span data-ttu-id="795cb-155">아래 스크립트는 API에 **Get-Token.ps1** 데 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="795cb-156">그런 다음 지난 48시간 내에 마지막으로 업데이트된 인시던트 목록을 검색하고 목록을 JSON 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="795cb-157">이 스크립트를 저장한 폴더와 동일한 폴더에 **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="795cb-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="795cb-158">모두 완료했습니다!</span><span class="sxs-lookup"><span data-stu-id="795cb-158">You're all done!</span></span> <span data-ttu-id="795cb-159">다음을 성공적으로 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-159">You've successfully:</span></span>

- <span data-ttu-id="795cb-160">응용 프로그램을 만들어 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-160">Created and registered an application.</span></span>
- <span data-ttu-id="795cb-161">해당 응용 프로그램에 대해 경고를 읽을 수 있는 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="795cb-162">API에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="795cb-162">Connected to the API.</span></span>
- <span data-ttu-id="795cb-163">PowerShell 스크립트를 사용하여 지난 48시간 동안 업데이트된 인시던트 반환</span><span class="sxs-lookup"><span data-stu-id="795cb-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="795cb-164">관련 문서</span><span class="sxs-lookup"><span data-stu-id="795cb-164">Related articles</span></span>

- [<span data-ttu-id="795cb-165">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="795cb-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="795cb-166">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="795cb-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="795cb-167">사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="795cb-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="795cb-168">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="795cb-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="795cb-169">Microsoft 365 Defender API에 대한 다중 테넌트 파트너 액세스가 있는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="795cb-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="795cb-170">Azure Key Vault를 사용하여 서버 앱의 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="795cb-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="795cb-171">사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여</span><span class="sxs-lookup"><span data-stu-id="795cb-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
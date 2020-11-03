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
# <a name="partner-access-through-microsoft-365-defender-apis"></a><span data-ttu-id="95b61-104">Microsoft 365 Defender Api를 통한 파트너 액세스</span><span class="sxs-lookup"><span data-stu-id="95b61-104">Partner access through Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="95b61-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95b61-105">**Applies to:**</span></span>
- <span data-ttu-id="95b61-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95b61-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="95b61-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="95b61-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="95b61-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="95b61-109">이 페이지에서는 고객을 대신 하 여 Microsoft 365 Defender에 프로그래밍 방식으로 액세스할 수 있도록 AAD 응용 프로그램을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-109">This page describes how to create an AAD application to get programmatic access to Microsoft 365 Defender on behalf of your customers.</span></span>

<span data-ttu-id="95b61-110">Microsoft 365 Defender는 프로그래밍 Api 집합을 통해 대부분의 데이터와 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-110">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="95b61-111">이러한 Api는 Microsoft 365 Defender 기능을 기반으로 하는 워크플로 및 작업 흐름을 자동화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-111">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="95b61-112">API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-112">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="95b61-113">자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="95b61-113">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="95b61-114">일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-114">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="95b61-115">**다중 테 넌 트** AAD 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-115">Create a **multi-tenant** AAD application.</span></span>
- <span data-ttu-id="95b61-116">고객 관리자가 필요한 Microsoft 365 Defender 리소스에 액세스 하려면 해당 응용 프로그램에 대 한 승인 된 (동의)를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-116">Get authorized (consent) by your customer administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="95b61-117">이 응용 프로그램을 사용 하 여 액세스 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-117">Get an access token using this application.</span></span>
- <span data-ttu-id="95b61-118">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-118">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="95b61-119">다음 단계에서는 AAD 응용 프로그램을 만들어 Microsoft 365 Defender에 액세스 토큰을 가져오고 토큰의 유효성을 검사 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-119">The following steps with guide you how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="95b61-120">다중 테 넌 트 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="95b61-120">Create the multi-tenant app</span></span>

1. <span data-ttu-id="95b61-121">**전역 관리자** 역할이 있는 사용자로 [Azure 테 넌 트](https://portal.azure.com) 에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-121">Log on to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="95b61-122">**Azure Active Directory**  >  **앱 등록**  >  **새 등록** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="95b61-124">등록 양식에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-124">In the registration form:</span></span>

    - <span data-ttu-id="95b61-125">응용 프로그램의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-125">Choose a name for your application.</span></span>

    - <span data-ttu-id="95b61-126">지원 되는 계정 유형-모든 조직 디렉터리의 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-126">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="95b61-127">리디렉션 URI-유형: Web, URI: https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="95b61-127">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![Microsoft Azure 파트너 응용 프로그램 등록의 이미지](../../media/atp-api-new-app-partner.png)


4. <span data-ttu-id="95b61-129">응용 프로그램에서 Microsoft 365 Defender에 액세스 하 고 통합을 완료 하는 데 필요한 최소한의 사용 권한 집합을 할당할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-129">Allow your Application to access Microsoft 365 Defender and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="95b61-130">응용 프로그램 페이지에서 **API 사용 권한을** 클릭  >  **Add permission**  >  **하 고 조직에서 사용 하는** 사용 권한 api 추가 > **microsoft 365 defender** 를 입력 하 고 **microsoft 365 defender** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-130">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and click on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="95b61-131">Microsoft 365 Defender가 원래 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-131">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="95b61-132">텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="95b61-134">API 사용 권한 요청</span><span class="sxs-lookup"><span data-stu-id="95b61-134">Request API permissions</span></span>

   <span data-ttu-id="95b61-135">필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="95b61-135">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span> 

   <span data-ttu-id="95b61-136">다음 예제에서는 **' 모든 인시던트 읽기 '** 권한을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-136">In the following example we will use **'Read all incidents'** permission:</span></span>

   <span data-ttu-id="95b61-137">**응용 프로그램 사용 권한**  >  **인시던트를** 선택 합니다. 모두 > **사용 권한 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-137">Choose **Application permissions** > **Incidents.Read.All** > Click on **Add permissions**</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)


5. <span data-ttu-id="95b61-139">**동의 허용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-139">Click **Grant consent**</span></span>

    >[!NOTE]
    ><span data-ttu-id="95b61-140">사용 권한을 추가할 때마다 새 사용 권한에 대 한 **동의 부여** 를 클릭 하 여 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-140">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![권한 부여 이미지](../../media/grant-consent.PNG)

6. <span data-ttu-id="95b61-142">응용 프로그램에 비밀을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-142">Add a secret to the application.</span></span>

    - <span data-ttu-id="95b61-143">**인증서 & 비밀** 을 클릭 하 고, 비밀에 설명을 추가 하 고, **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-143">Click **Certificates & secrets** , add description to the secret and click **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="95b61-144">**추가** 를 선택한 후에 **생성 된 비밀 값을 복사** 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-144">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="95b61-145">나간 후에는 검색할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-145">You won't be able to retrieve after you leave!</span></span>

    ![앱 만들기 키의 이미지](../../media/webapp-create-key2.png)

7. <span data-ttu-id="95b61-147">응용 프로그램 ID를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-147">Write down your application ID:</span></span>

   - <span data-ttu-id="95b61-148">응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-148">On your application page, go to **Overview** and copy the following:</span></span>

   ![만든 앱 id의 이미지](../../media/app-id.png)

8. <span data-ttu-id="95b61-150">고객의 테 넌 트에 응용 프로그램을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-150">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="95b61-151">응용 프로그램이 사용 하려는 각 고객 테 넌 트에서 승인 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-151">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="95b61-152">이는 응용 프로그램이 고객을 대신 하 여 Microsoft 365 Defender 응용 프로그램과 상호 작용 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-152">This is because your application interacts with Microsoft 365 Defender application on behalf of your customer.</span></span>

    <span data-ttu-id="95b61-153">고객의 테 넌 트의 **전역 관리자** 가 있는 사용자는 동의 링크를 클릭 하 고 응용 프로그램을 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-153">A user with **Global Administrator** from your customer's tenant need to click the consent link and approve your application.</span></span>

    <span data-ttu-id="95b61-154">승인 링크 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-154">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="95b61-155">여기서 00000000-0000-0000-0000-000000000000는 응용 프로그램 ID로 교체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-155">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="95b61-156">승인 링크를 클릭 한 후에는 고객의 테 넌 트의 전역 관리자에 로그인 하 여 응용 프로그램에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-156">After clicking on the consent link, login with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![승인 이미지](../../media/app-consent-partner.png)

    <span data-ttu-id="95b61-158">또한 고객에 게 해당 테 넌 트 ID를 묻고 토큰을 취득할 때 나중에 사용할 수 있도록 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-158">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="95b61-159">**수행!**</span><span class="sxs-lookup"><span data-stu-id="95b61-159">**Done!**</span></span> <span data-ttu-id="95b61-160">응용 프로그램을 성공적으로 등록 했습니다!</span><span class="sxs-lookup"><span data-stu-id="95b61-160">You have successfully registered an application!</span></span> 
- <span data-ttu-id="95b61-161">토큰 획득 및 유효성 검사에 대 한 아래 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95b61-161">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-examples"></a><span data-ttu-id="95b61-162">액세스 토큰 예제를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-162">Get an access token examples:</span></span>

>[!NOTE]
> <span data-ttu-id="95b61-163">고객을 대신 하 여 액세스 토큰을 가져오려면 다음 토큰 합병에 고객의 테 넌 트 ID를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-163">To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="95b61-164">AAD 토큰에 대 한 자세한 내용은 [aad 자습서](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95b61-164">For more details on AAD token, refer to [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="95b61-165">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="95b61-165">Using PowerShell</span></span>

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

### <a name="using-c"></a><span data-ttu-id="95b61-166">C # 사용</span><span class="sxs-lookup"><span data-stu-id="95b61-166">Using C#:</span></span>

><span data-ttu-id="95b61-167">다음 코드는 Nuget Microsoft.identitymodel를 사용 하 여 테스트 되었습니다. ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="95b61-167">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="95b61-168">새 콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="95b61-168">Create a new Console Application</span></span>
- <span data-ttu-id="95b61-169">Nuget [microsoft.identitymodel을](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) 설치 합니다. ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="95b61-169">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="95b61-170">다음을 사용 하 여 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-170">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="95b61-171">응용 프로그램에서 아래 코드를 복사/붙여 넣습니다 (3 개의 변수를 업데이트 하는 것을 잊지 않음 ```tenantId, appId, appSecret``` ).</span><span class="sxs-lookup"><span data-stu-id="95b61-171">Copy/Paste the below code in your application (do not forget to update the 3 variables: ```tenantId, appId, appSecret```)</span></span>

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



### <a name="using-curl"></a><span data-ttu-id="95b61-172">말아 넘기기 사용</span><span class="sxs-lookup"><span data-stu-id="95b61-172">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="95b61-173">Windows 용 말아 넘기기가 컴퓨터에 이미 설치 되어 있는 절차</span><span class="sxs-lookup"><span data-stu-id="95b61-173">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="95b61-174">명령 창 열기</span><span class="sxs-lookup"><span data-stu-id="95b61-174">Open a command window</span></span>
- <span data-ttu-id="95b61-175">Azure 응용 프로그램 ID로 CLIENT_ID 설정</span><span class="sxs-lookup"><span data-stu-id="95b61-175">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="95b61-176">Azure 응용 프로그램 비밀으로 CLIENT_SECRET 설정</span><span class="sxs-lookup"><span data-stu-id="95b61-176">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="95b61-177">응용 프로그램을 사용 하 여 Microsoft 365 Defender 응용 프로그램에 액세스 하려는 고객의 Azure 테 넌 트 ID로 TENANT_ID 설정</span><span class="sxs-lookup"><span data-stu-id="95b61-177">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft 365 Defender application</span></span>
- <span data-ttu-id="95b61-178">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-178">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="95b61-179">다음과 같은 양식의 대답이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-179">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="95b61-180">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="95b61-180">Validate the token</span></span>

<span data-ttu-id="95b61-181">온전성 검사를 통해 올바른 토큰이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-181">Sanity check to make sure you got a correct token:</span></span>

- <span data-ttu-id="95b61-182">[JWT](https://jwt.ms) 에 복사/붙여넣기 이전 단계에서 가져오는 토큰을 디코드 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-182">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="95b61-183">' 역할 ' 클레임이 원하는 사용 권한으로 제공 되는지 확인</span><span class="sxs-lookup"><span data-stu-id="95b61-183">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="95b61-184">아래 스크린샷에서는 Microsoft 365 Defender에 대 한 여러 권한을 가진 응용 프로그램에서 얻은 디코딩된 토큰을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-184">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to Microsoft 365 Defender:</span></span>
- <span data-ttu-id="95b61-185">"Tid" 클레임은 토큰이 속해 있는 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="95b61-185">The "tid" claim is the tenant ID the token belongs to.</span></span>

![토큰 유효성 검사 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a><span data-ttu-id="95b61-187">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="95b61-187">Use the token to access Microsoft 365 Defender API</span></span>

- <span data-ttu-id="95b61-188">사용할 API 선택 자세한 내용은 [지원 되는 Microsoft 365 Defender api](api-supported.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95b61-188">Choose the API you want to use, for more information, see [Supported Microsoft 365 Defender APIs](api-supported.md)</span></span>
- <span data-ttu-id="95b61-189">전송 하는 Http 요청에서 "전달자 {토큰}"으로 보내는 인증 헤더 설정 (전달자는 인증 체계)</span><span class="sxs-lookup"><span data-stu-id="95b61-189">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="95b61-190">토큰의 만료 시간은 1 시간 (동일한 토큰을 사용 하 여 요청을 하나 이상 보낼 수 있음)</span><span class="sxs-lookup"><span data-stu-id="95b61-190">The Expiration time of the token is 1 hour (you can send more then one request with the same token)</span></span>

- <span data-ttu-id="95b61-191">**C #을 사용 하 여** 인시던트 목록을 가져오기 위한 요청을 보내는 예제</span><span class="sxs-lookup"><span data-stu-id="95b61-191">Example of sending a request to get a list of incidents **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a><span data-ttu-id="95b61-192">관련 항목</span><span class="sxs-lookup"><span data-stu-id="95b61-192">Related topics</span></span> 

- [<span data-ttu-id="95b61-193">Microsoft 365 Defender Api 액세스</span><span class="sxs-lookup"><span data-stu-id="95b61-193">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="95b61-194">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="95b61-194">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="95b61-195">사용자 컨텍스트를 사용 하 여 Microsoft 365 Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="95b61-195">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)

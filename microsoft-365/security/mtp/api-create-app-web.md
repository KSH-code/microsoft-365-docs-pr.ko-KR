---
title: 사용자 없이 Microsoft 365 Defender에 액세스할 앱 만들기
description: 사용자가 없는 Microsoft 365 Defender에 액세스 하기 위한 앱을 만드는 방법을 알아봅니다.
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
ms.openlocfilehash: 446db803cc47bfd519642928a4a0257c4b3d57c8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846071"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="3f9f8-104">사용자 없이 Microsoft 365 Defender에 액세스할 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="3f9f8-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3f9f8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3f9f8-105">**Applies to:**</span></span>
- <span data-ttu-id="3f9f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f9f8-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="3f9f8-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3f9f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3f9f8-109">이 페이지에서는 사용자 없이 Microsoft 365 Defender에 프로그래밍 방식으로 액세스 하는 응용 프로그램을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a user.</span></span> <span data-ttu-id="3f9f8-110">사용자를 대신 하 여 Microsoft 365 Defender에 프로그래밍 방식으로 액세스 해야 하는 경우 [사용자 컨텍스트로 Get 액세스](api-create-app-user-context.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-110">If you need programmatic access to Microsoft 365 Defender on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="3f9f8-111">필요한 액세스를 모르는 경우 [시작 하기](api-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="3f9f8-112">Microsoft 365 Defender는 프로그래밍 Api 집합을 통해 대부분의 데이터와 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="3f9f8-113">이러한 Api는 Microsoft 365 Defender 기능을 기반으로 하는 워크플로 및 작업 흐름을 자동화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-113">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="3f9f8-114">API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="3f9f8-115">자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="3f9f8-116">일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="3f9f8-117">Azure AD (Active Directory) 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="3f9f8-118">이 응용 프로그램을 사용 하 여 액세스 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-118">Get an access token using this application.</span></span>
- <span data-ttu-id="3f9f8-119">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="3f9f8-120">이 문서에서는 Azure AD 응용 프로그램을 만들고, Microsoft 365 Defender에 액세스 토큰을 가져오고, 토큰의 유효성을 검사 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-120">This article explains how to create an Azure AD application, get an access token to Microsoft 365 Defender, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="3f9f8-121">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="3f9f8-121">Create an app</span></span>

1. <span data-ttu-id="3f9f8-122">**전역 관리자** 역할이 있는 사용자를 사용 하 여 [Azure](https://portal.azure.com) 에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="3f9f8-123">**Azure Active Directory**  >  **앱 등록**  >  **새 등록** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="3f9f8-125">등록 양식에서 응용 프로그램의 이름을 선택한 다음 **레지스터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="3f9f8-126">앱에서 Microsoft 365 Defender에 액세스 하 고 사용 권한을 할당할 수 있도록 설정 하려면 응용 프로그램 페이지에서 **api 사용** 권한을 선택 합니다.  >  **Add permission**  >  **내 조직에서 사용 하는** 사용 권한 api 추가 >에 **microsoft 365 defender** 를 입력 한 다음 **microsoft 365 defender** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-126">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f9f8-127">Microsoft 365 Defender가 원래 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-127">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="3f9f8-128">텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="3f9f8-130">**응용 프로그램 사용 권한** > 시나리오에 관련 된 사용 권한 (예: **읽음** )을 선택 하 고 **사용 권한 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All** , and then select **Add permissions**.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="3f9f8-132">시나리오에 대 한 관련 권한을 선택 해야 합니다. **' 모든 문제 읽기 '** 는 단지 예 일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="3f9f8-133">필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="3f9f8-134">**동의 허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3f9f8-135">사용 권한을 추가할 때마다 새 사용 권한을 적용 하려면 **동의 허용** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![권한 부여 이미지](../../media/grant-consent.PNG)

6. <span data-ttu-id="3f9f8-137">응용 프로그램에 비밀을 추가 하려면 **인증서 & 비밀** 을 선택 하 고 비밀에 대 한 설명을 추가한 다음 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-137">To add a secret to the application, select **Certificates & secrets** , add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3f9f8-138">**추가** 를 선택한 후에 **는 생성 된 비밀 값 복사** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-138">After you select **Add** , select **copy the generated secret value**.</span></span> <span data-ttu-id="3f9f8-139">나간 후에는이 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-139">You won't be able to retrieve this value after you leave.</span></span>

    ![앱 만들기 키의 이미지](../../media/webapp-create-key2.png)

7. <span data-ttu-id="3f9f8-141">응용 프로그램 ID 및 테 넌 트 ID를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="3f9f8-142">응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![만든 앱 id의 이미지](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="3f9f8-144">**Microsoft 365 Defender 파트너 전용** 입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-144">**For Microsoft 365 Defender Partners only**.</span></span> <span data-ttu-id="3f9f8-145">[지침을 따릅니다](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span><span class="sxs-lookup"><span data-stu-id="3f9f8-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="3f9f8-146">앱이 여러 tenanted (동의 후 모든 테 넌 트에서 사용 가능)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="3f9f8-147">이는 타사 앱 (예: 여러 고객의 테 넌 트에서 실행 하기 위한 앱을 만드는 경우)에 **필요** 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="3f9f8-148">테 넌 트에만 실행 하려는 서비스를 만드는 경우에는이 작업을 수행할 필요가 **없습니다** (예: 자신만의 데이터와 상호 작용 하는 응용 프로그램을 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="3f9f8-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="3f9f8-149">앱을 다중 tenanted 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="3f9f8-150">**인증** 으로 이동 하 고 https://portal.azure.com **리디렉션 URI** 로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-150">Go to **Authentication** , and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="3f9f8-151">페이지 아래쪽의 **지원 되는 계정 유형** 아래에서 다중 테 넌 트 앱에 대 한 조직 디렉터리 응용 프로그램 동의 **에서 계정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-151">On the bottom of the page, under **Supported account types** , select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="3f9f8-152">응용 프로그램이 사용 하려는 각 테 넌 트에서 승인 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="3f9f8-153">이는 응용 프로그램이 고객을 대신 하 여 Microsoft 365 Defender를 상호 작용 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-153">This is because your application interacts Microsoft 365 Defender on behalf of your customer.</span></span>

    <span data-ttu-id="3f9f8-154">사용자 (또는 타사 앱을 작성 하는 경우) 동의 링크를 선택 하 고 앱을 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="3f9f8-155">Active Directory에 관리 권한이 있는 사용자에 대 한 동의를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="3f9f8-156">승인 링크는 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="3f9f8-157">여기에서 00000000-0000-0000-0000-000000000000는 응용 프로그램 ID로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="3f9f8-158">**수행!**</span><span class="sxs-lookup"><span data-stu-id="3f9f8-158">**Done!**</span></span> <span data-ttu-id="3f9f8-159">응용 프로그램을 성공적으로 등록 했습니다!</span><span class="sxs-lookup"><span data-stu-id="3f9f8-159">You have successfully registered an application!</span></span> <span data-ttu-id="3f9f8-160">토큰 획득 및 유효성 검사에 대 한 아래 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="3f9f8-161">액세스 토큰 가져오기</span><span class="sxs-lookup"><span data-stu-id="3f9f8-161">Get an access token</span></span>

<span data-ttu-id="3f9f8-162">Azure AD 토큰에 대 한 자세한 내용은 [AZURE ad 자습서](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="3f9f8-163">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="3f9f8-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="3f9f8-164">C #을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-164">Use C#:</span></span>

<span data-ttu-id="3f9f8-165">다음 코드는 Nuget Microsoft.identitymodel ActiveDirectory 3.19.8에서 테스트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="3f9f8-166">새 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-166">Create a new console application.</span></span>
1. <span data-ttu-id="3f9f8-167">Nuget Microsoft.identitymodel을 설치 합니다 [.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="3f9f8-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="3f9f8-168">다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="3f9f8-169">응용 프로그램에 다음 코드를 복사 하 여 붙여넣습니다 (세 가지 변수를 업데이트 하는 것을 잊지 않음 ```tenantId, appId, appSecret``` ).</span><span class="sxs-lookup"><span data-stu-id="3f9f8-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

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


### <a name="use-python"></a><span data-ttu-id="3f9f8-170">Python 사용</span><span class="sxs-lookup"><span data-stu-id="3f9f8-170">Use Python</span></span> 

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
### <a name="use-curl"></a><span data-ttu-id="3f9f8-171">말아 넘기기 사용</span><span class="sxs-lookup"><span data-stu-id="3f9f8-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="3f9f8-172">다음 절차에서는 Windows 용 말아 넘기기가 컴퓨터에 이미 설치 되어 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="3f9f8-173">명령 프롬프트를 열고 CLIENT_ID를 Azure 응용 프로그램 ID로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="3f9f8-174">CLIENT_SECRET Azure application SECRET로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="3f9f8-175">앱을 사용 하 여 Microsoft 365 Defender에 액세스 하려는 고객의 Azure 테 넌 트 ID로 TENANT_ID를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="3f9f8-176">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="3f9f8-177">다음 형식으로 대답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="3f9f8-178">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="3f9f8-178">Validate the token</span></span>

<span data-ttu-id="3f9f8-179">올바른 토큰을가지고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="3f9f8-180">이전 단계에서 얻은 토큰을 복사 하 여 [디코딩하여에 붙여](https://jwt.ms) 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="3f9f8-181">원하는 사용 권한으로 ' 역할 ' 클레임이 제공 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="3f9f8-182">다음 그림에서는 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 및 사용 권한으로 앱에서 얻은 디코딩된 토큰을 볼 수 있습니다 ```AdvancedHunting.Read.All``` .</span><span class="sxs-lookup"><span data-stu-id="3f9f8-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![토큰 유효성 검사 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a><span data-ttu-id="3f9f8-184">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="3f9f8-184">Use the token to access Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="3f9f8-185">사용할 API를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-185">Choose the API you want to use.</span></span> <span data-ttu-id="3f9f8-186">자세한 내용은 [지원 되는 Microsoft 365 Defender api](api-supported.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-186">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="3f9f8-187">전송 하는 http 요청에서 "전달자 {토큰}"으로 보내는 인증 헤더를 설정 합니다 (전달자는 인증 체계).</span><span class="sxs-lookup"><span data-stu-id="3f9f8-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="3f9f8-188">토큰의 만료 시간은 1 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="3f9f8-189">동일한 토큰을 사용 하 여 두 개 이상의 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="3f9f8-190">다음은 **c #을 사용 하 여** 인시던트 목록을 가져오기 위한 요청을 보내는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f8-190">The following is an example of sending a request to get a list of incidents **using C#** :</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="3f9f8-191">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3f9f8-191">Related topics</span></span>
- [<span data-ttu-id="3f9f8-192">Microsoft 365 Defender Api 액세스</span><span class="sxs-lookup"><span data-stu-id="3f9f8-192">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3f9f8-193">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="3f9f8-193">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="3f9f8-194">사용자 컨텍스트를 사용 하 여 Microsoft 365 Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="3f9f8-194">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)

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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2d78b7ea31c45220735a8579d728f9c0f7bda181
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842113"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="8e46b-104">사용자 없이 끝점용 Microsoft Defender에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="8e46b-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8e46b-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8e46b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8e46b-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8e46b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8e46b-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="8e46b-108">이 페이지에서는 사용자가 없는 끝점용 Defender에 프로그래밍 방식 액세스 권한을 부여하는 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="8e46b-109">사용자를 대신하여 Endpoint용 Defender에 프로그래밍식 액세스 권한이 필요한 경우 사용자 컨텍스트를 통해 [액세스하기를 참조합니다.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="8e46b-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="8e46b-110">필요한 액세스 권한이 확실하지 않은 경우 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8e46b-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="8e46b-111">끝점용 Microsoft Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8e46b-112">이러한 API는 작업 흐름을 자동화하고 끝점용 Defender 기능을 기반으로 혁신하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="8e46b-113">API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8e46b-114">자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="8e46b-114">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8e46b-115">일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="8e46b-116">Azure AD(Azure Active Directory 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="8e46b-117">이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-117">Get an access token using this application.</span></span>
- <span data-ttu-id="8e46b-118">토큰을 사용하여 Endpoint API용 Defender에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="8e46b-119">이 문서에서는 Azure AD 응용 프로그램을 만들고, 끝점용 Microsoft Defender에 대한 액세스 토큰을 다운로드하고, 토큰의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="8e46b-120">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="8e46b-120">Create an app</span></span>

1. <span data-ttu-id="8e46b-121">전역 관리자 역할이 있는 사용자로 [Azure에](https://portal.azure.com) **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="8e46b-122">앱 등록 **Azure Active Directory**  >  **새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![응용 Microsoft Azure 탐색 및 이미지](images/atp-azure-new-app2.png)

3. <span data-ttu-id="8e46b-124">등록 양식에서 응용 프로그램의 이름을 선택한 다음 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="8e46b-125">앱이 끝점용 Defender에 액세스하여 '모든 경고 **읽기'** 권한을 할당할 수 있도록 설정하려면 응용 프로그램 페이지에서 **API** 사용 권한 추가 권한 API를 선택하고 >  >    >   **WindowsDefenderATP를 입력한 다음 WindowsDefenderATP를** 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="8e46b-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8e46b-126">*WindowsDefenderATP는* 원래 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="8e46b-127">텍스트 상자에 이름을 입력하여 표시를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e46b-127">Start writing its name in the text box to see it appear.</span></span>

   ![사용 권한 추가](images/add-permission.png)

   - <span data-ttu-id="8e46b-129">응용 **프로그램 권한**  >  **Alert.Read.All** 을 선택한 다음 사용 권한 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![앱 사용 권한](images/application-permissions.png)

     <span data-ttu-id="8e46b-131">관련 권한을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="8e46b-132">'모든 경고 읽기'는 예일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="8e46b-133">예를 들면,</span><span class="sxs-lookup"><span data-stu-id="8e46b-133">For instance:</span></span>

     - <span data-ttu-id="8e46b-134">고급 [쿼리를 실행하려면](run-advanced-query-api.md)'고급 쿼리 실행' 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="8e46b-135">장치를 [격리하려면](isolate-machine.md)'컴퓨터 격리' 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="8e46b-136">필요한 사용 권한을 확인하려면 호출할 API의 사용 권한 섹션을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="8e46b-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="8e46b-137">동의 **부여를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8e46b-138">권한을 추가할 때마다 새 사용 권한을 **적용하기** 위해 동의 부여를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![사용 권한 부여](images/grant-consent.png)

6. <span data-ttu-id="8e46b-140">응용 프로그램에 비밀을 추가하려면 인증서 & **를** 선택하고 비밀에 설명을 추가한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8e46b-141">추가를 **선택한** 후 생성된 **비밀 값 복사 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="8e46b-142">나가면 이 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-142">You won't be able to retrieve this value after you leave.</span></span>

    ![앱 키 만들기 이미지](images/webapp-create-key2.png)

7. <span data-ttu-id="8e46b-144">응용 프로그램 ID와 테넌트 ID를 기록해 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="8e46b-145">응용 프로그램 페이지에서 개요로 이동하여 **다음을** 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![생성된 앱 ID의 이미지](images/app-and-tenant-ids.png)

8. <span data-ttu-id="8e46b-147">**끝점 파트너용 Microsoft Defender의 경우만 입니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="8e46b-148">앱을 다중 테넌트로 설정(동의 후 모든 테넌트에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="8e46b-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="8e46b-149">타사 **앱(예:** 여러 고객의 테넌트에서 실행되는 앱을 만드는 경우)에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="8e46b-150">테넌트에서만 실행할 서비스를 만드는 경우(예: 자체 데이터와만 상호 작용하는 응용 프로그램을 직접 만드는 경우)에는 필요하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="8e46b-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="8e46b-151">앱을 다중 테넌트로 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="8e46b-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="8e46b-152">인증으로 **이동하여** `https://portal.azure.com` 리디렉션 **URI로 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="8e46b-153">페이지 아래쪽의 지원되는 계정 유형에서 다중  테넌트 앱에 대한 조직 디렉터리 응용 프로그램 동의의 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="8e46b-154">응용 프로그램을 사용하려는 각 테넌트에서 응용 프로그램을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="8e46b-155">이는 응용 프로그램이 고객을 대신하여 끝점용 Defender와 상호 작용하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="8e46b-156">사용자(또는 타사 앱을 작성하는 경우 고객)는 동의 링크를 선택하고 앱을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="8e46b-157">Active Directory에 관리 권한이 있는 사용자와 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="8e46b-158">동의 링크는 다음과 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="8e46b-159">여기서 000000000-0000-0000-0000-000000000000은 응용 프로그램 ID로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="8e46b-160">**완료!**</span><span class="sxs-lookup"><span data-stu-id="8e46b-160">**Done!**</span></span> <span data-ttu-id="8e46b-161">응용 프로그램을 성공적으로 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-161">You have successfully registered an application!</span></span> <span data-ttu-id="8e46b-162">토큰 획득 및 유효성 검사에 대한 자세한 내용은 아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e46b-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="8e46b-163">액세스 토큰을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-163">Get an access token</span></span>

<span data-ttu-id="8e46b-164">Azure AD 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="8e46b-164">For more information on Azure AD tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="8e46b-165">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8e46b-165">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="8e46b-166">다음 C#.</span><span class="sxs-lookup"><span data-stu-id="8e46b-166">Use C#:</span></span>

<span data-ttu-id="8e46b-167">다음 코드는 Microsoft.IdentityModel.Clients.NuGet 3.19.8을 사용하여 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="8e46b-168">새 콘솔 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-168">Create a new console application.</span></span>
1. <span data-ttu-id="8e46b-169">[Microsoft.NuGet.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="8e46b-170">다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="8e46b-171">앱에서 다음 코드를 복사하여 붙여넣습니다(세 개의 변수를 업데이트하는 것을 잊지 마세요. ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="8e46b-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

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


### <a name="use-python"></a><span data-ttu-id="8e46b-172">Python 사용</span><span class="sxs-lookup"><span data-stu-id="8e46b-172">Use Python</span></span>

<span data-ttu-id="8e46b-173">[Python을 사용하여 토큰을 얻습니다.를 참조합니다.](run-advanced-query-sample-python.md#get-token)</span><span class="sxs-lookup"><span data-stu-id="8e46b-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="8e46b-174">컬 사용</span><span class="sxs-lookup"><span data-stu-id="8e46b-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="8e46b-175">다음 절차에서는 컴퓨터에 Windows Curl이 이미 설치되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="8e46b-176">명령 프롬프트를 열고 azure CLIENT_ID ID로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e46b-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="8e46b-177">Azure CLIENT_SECRET 비밀로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="8e46b-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="8e46b-178">앱을 TENANT_ID 끝점용 Defender에 액세스하려는 고객의 Azure 테넌트 ID로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="8e46b-179">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="8e46b-180">다음 형식의 답변을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="8e46b-181">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8e46b-181">Validate the token</span></span>

<span data-ttu-id="8e46b-182">올바른 토큰이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="8e46b-183">이전 단계에서 사용한 토큰을 복사하여 [JWT에](https://jwt.ms) 붙여넣어 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="8e46b-184">원하는 사용 권한으로 '역할' 클레임이 유효한지 확인</span><span class="sxs-lookup"><span data-stu-id="8e46b-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="8e46b-185">다음 이미지에서는 끝점의 모든 역할에 대한 사용 권한이 있는 앱에서 획득한 디코딩된 토큰을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![토큰 유효성 검사 이미지](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="8e46b-187">토큰을 사용하여 끝점 API용 Microsoft Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="8e46b-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="8e46b-188">사용할 API를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-188">Choose the API you want to use.</span></span> <span data-ttu-id="8e46b-189">자세한 내용은 [Supported Defender for Endpoint API를 참조하세요.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="8e46b-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="8e46b-190">"Bearer {token}"(Bearer는 권한 부여 체계)으로 보내는 http 요청에서 권한 부여 헤더를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e46b-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="8e46b-191">토큰의 만료 시간은 1시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="8e46b-192">동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e46b-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="8e46b-193">다음 예는 다음을 사용하여 경고 목록을 을(를) 요청하는 **C#.**</span><span class="sxs-lookup"><span data-stu-id="8e46b-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="8e46b-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e46b-194">See also</span></span>
- <span data-ttu-id="8e46b-195">[지원되는 엔드포인트용 Microsoft Defender API](exposed-apis-list.md) </span><span class="sxs-lookup"><span data-stu-id="8e46b-195">[Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- [<span data-ttu-id="8e46b-196">사용자를 대신하여 끝점용 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="8e46b-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)

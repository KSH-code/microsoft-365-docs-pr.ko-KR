---
title: 사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기
description: 사용자 없이 Microsoft 365 Defender에 액세스하기 위한 앱을 만드는 방법을 배워야 합니다.
keywords: 앱, 액세스, api, 만들기
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
ms.openlocfilehash: f438189b4ba9fb66124650782b3de2ee34dfee64
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928441"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="ce660-104">사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ce660-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ce660-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ce660-105">**Applies to:**</span></span>

- <span data-ttu-id="ce660-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce660-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce660-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ce660-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ce660-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ce660-109">이 페이지에서는 정의된 사용자 없이 Microsoft 365 Defender에 프로그래밍 방식 액세스(예: 디먼 또는 백그라운드 서비스를 만드는 경우)를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="ce660-110">하나 이상의 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍된 액세스가 필요한 경우 사용자를 대신하여 [Microsoft 365 Defender](api-create-app-user-context.md) API에 액세스하는 앱 만들기 및 Microsoft [365 Defender](api-partner-access.md)API에 대한 파트너 액세스가 있는 앱 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce660-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="ce660-111">필요한 액세스 종류가 확실하지 않은 경우 [시작을 참조합니다.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="ce660-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="ce660-112">Microsoft 365 Defender는 프로그래밍 API 집합을 통해 많은 데이터 및 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="ce660-113">이러한 API는 워크플로를 자동화하고 Microsoft 365 Defender의 기능을 활용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="ce660-114">이 API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="ce660-115">자세한 내용은 [OAuth 2.0 권한 부여 코드 흐름을 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="ce660-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="ce660-116">일반적으로 이러한 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="ce660-117">Azure AD(Azure Active Directory) 응용 프로그램을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="ce660-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="ce660-118">이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-118">Get an access token using this application.</span></span>
- <span data-ttu-id="ce660-119">토큰을 사용하여 Microsoft 365 Defender API에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="ce660-120">이 문서에서는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-120">This article explains how to:</span></span>

- <span data-ttu-id="ce660-121">Azure AD 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="ce660-121">Create an Azure AD application</span></span>
- <span data-ttu-id="ce660-122">Microsoft 365 Defender에 대한 액세스 토큰 다운로드</span><span class="sxs-lookup"><span data-stu-id="ce660-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="ce660-123">토큰의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="ce660-124">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ce660-124">Create an app</span></span>

1. <span data-ttu-id="ce660-125">전역 관리자 역할을 사용하여 [Azure에](https://portal.azure.com) **사용자로 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="ce660-126">Azure **Active Directory**  >  **앱 등록 새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure의 이미지 및 응용 프로그램 등록 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="ce660-128">양식에서 응용 프로그램의 이름을 선택한 다음 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="ce660-129">응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 API를 선택하고 > Microsoft Threat Protection을 입력한 다음  >    >   Microsoft **Threat Protection을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="ce660-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="ce660-130">이제 앱이 Microsoft 365 Defender에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="ce660-131">*Microsoft Threat Protection은* Microsoft 365 Defender의 이전 이름으로, 원래 목록에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="ce660-132">표시하려면 텍스트 상자에 해당 이름을 쓰기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 권한 선택 이미지](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="ce660-134">응용 **프로그램 사용 권한을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-134">Select **Application permissions**.</span></span> <span data-ttu-id="ce660-135">시나리오에 대한 관련 사용 권한(예: **Incident.Read.All)을** 선택한 다음 사용 권한 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="ce660-137">시나리오에 대한 관련 사용 권한을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="ce660-138">*모든 인시던트 읽기는* 예시일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="ce660-139">필요한 사용 권한을 확인하려면 호출할 API의 **사용** 권한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce660-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="ce660-140">예를 들어 고급 [쿼리를 실행하려면](api-advanced-hunting.md)'고급 쿼리 실행' 권한을 선택합니다. 장치를 [격리하려면](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)'컴퓨터 격리' 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="ce660-141">관리자 **동의 부여를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="ce660-142">권한을 추가할 때마다 권한을 적용하려면  관리자 동의 부여를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![권한 부여 이미지](../../media/grant-consent.PNG)

7. <span data-ttu-id="ce660-144">응용 프로그램에 비밀을 추가하려면 인증서를 선택하고 & 설명을 추가한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="ce660-145">추가를 **선택한 후** 생성된 **비밀 값 복사를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="ce660-146">나가면 비밀 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![앱 키 만들기 이미지](../../media/webapp-create-key2.png)

8. <span data-ttu-id="ce660-148">안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="ce660-149">응용 프로그램 페이지의 **개요** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-149">They're listed under **Overview** on your application page.</span></span>

   ![생성된 앱 ID의 이미지](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="ce660-151">**Microsoft 365 Defender 파트너만:** [](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) Microsoft 365 Defender API를 통해 파트너 액세스에 대한 다음 지침을 따르고, 앱을 다중 테넌트로 설정하여 관리자 동의를 받은 후 모든 테넌트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="ce660-152">타사 앱에 대해 파트너 액세스가 필요합니다. 예를 들어 여러 고객의 테넌트에서 실행되는 앱을 만드는 경우. </span><span class="sxs-lookup"><span data-stu-id="ce660-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="ce660-153">테넌트에서만 실행할 서비스를 만드는 경우(예: 사용자 데이터와만 상호 작용하는 응용 프로그램) 필요하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="ce660-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="ce660-154">앱을 다중 테넌트로 설정:</span><span class="sxs-lookup"><span data-stu-id="ce660-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="ce660-155">인증으로 **이동하여** https://portal.azure.com 리디렉션 **URI로 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce660-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="ce660-156">페이지 아래쪽의 지원되는 계정 유형에서 다중 테넌트 앱에 대한 조직 **디렉터리** 응용 프로그램 동의의 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="ce660-157">응용 프로그램이 사용자를 대신하여 Microsoft 365 Defender와 상호 작용하기 때문에 응용 프로그램을 사용하려는 모든 테넌트에 대해 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="ce660-158">각 테넌트의 Active Directory 전역 관리자는 동의 링크를 선택하고 앱을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="ce660-159">동의 링크의 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="ce660-160">숫자는 `00000000-0000-0000-0000-000000000000` 응용 프로그램 ID로 바야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="ce660-161">**완료!**</span><span class="sxs-lookup"><span data-stu-id="ce660-161">**Done!**</span></span> <span data-ttu-id="ce660-162">응용 프로그램을 성공적으로 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-162">You've successfully registered an application!</span></span> <span data-ttu-id="ce660-163">토큰 획득 및 유효성 검사는 아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce660-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="ce660-164">액세스 토큰을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-164">Get an access token</span></span>

<span data-ttu-id="ce660-165">Azure Active Directory 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="ce660-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce660-166">이 섹션의 예제에서는 테스트를 위해 비밀 값에 붙여 넣는 것이 까다로우지만 프로덕션에서 실행되는 응용 프로그램에 암호를 하드코드하면 안 됩니다. </span><span class="sxs-lookup"><span data-stu-id="ce660-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="ce660-167">제3자에서 사용자 비밀을 사용하여 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="ce660-168">Azure Key Vault를 사용하여 앱의 비밀을 안전하게 [유지할 수 있습니다.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="ce660-168">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="ce660-169">앱을 보호하는 방법에 대한 실제 예제는 Azure Key Vault를 사용하여 서버 앱의 암호 [관리를 참조하세요.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="ce660-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="ce660-170">PowerShell을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="ce660-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="ce660-171">C를 사용하여 액세스 토큰 얻기\#</span><span class="sxs-lookup"><span data-stu-id="ce660-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="ce660-172">다음 코드는 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8을 사용하여 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="ce660-173">새 콘솔 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-173">Create a new console application.</span></span>

1. <span data-ttu-id="ce660-174">NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory를 설치합니다.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="ce660-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="ce660-175">다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="ce660-176">다음 코드를 복사하여 앱에 붙여 넣습니다(세 가지 변수를 업데이트하는 것을 잊지 마세요. `tenantId` `clientId` , , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="ce660-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="ce660-177">Python을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="ce660-177">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="ce660-178">컬을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="ce660-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="ce660-179">컬은 Windows 10 버전 1803 이상에 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="ce660-180">다른 버전의 Windows의 경우 공식 컬 웹 사이트에서 직접 도구를 [다운로드하여 설치합니다.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="ce660-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="ce660-181">명령 프롬프트를 열고 azure CLIENT_ID ID로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce660-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="ce660-182">Azure CLIENT_SECRET 비밀로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="ce660-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="ce660-183">앱을 TENANT_ID Microsoft 365 Defender에 액세스하려는 고객의 Azure 테넌트 ID로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="ce660-184">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="ce660-185">성공적인 응답은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="ce660-186">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ce660-186">Validate the token</span></span>

1. <span data-ttu-id="ce660-187">토큰을 복사하여 JSON 웹 토큰 유효성 검사기 웹 사이트 [JWT에](https://jwt.ms) 붙여넣어 디코드합니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="ce660-188">디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ce660-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="ce660-189">다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 `Incidents.Read.All` `Incidents.ReadWrite.All` 토큰을 `AdvancedHunting.Read.All` 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![토큰 유효성 검사의 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="ce660-191">토큰을 사용하여 Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="ce660-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="ce660-192">사용할 API(인시던트 또는 고급 헌팅)를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce660-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="ce660-193">자세한 내용은 지원되는 [Microsoft 365 Defender API를 참조하세요.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="ce660-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="ce660-194">보낼 http 요청에서 권한 부여 헤더를 권한 부여 체계인 Bearer로 설정하고 유효성이 검사된 토큰인 `"Bearer" <token>` 토큰을 사용합니다.  </span><span class="sxs-lookup"><span data-stu-id="ce660-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="ce660-195">토큰은 1시간 이내에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-195">The token will expire within one hour.</span></span> <span data-ttu-id="ce660-196">이 시간 동안 동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce660-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="ce660-197">다음 예에서는 C#을 사용하여 인시던트 목록을 들이는 요청을 **보내는 방법을 보여 주며,**</span><span class="sxs-lookup"><span data-stu-id="ce660-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="ce660-198">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ce660-198">Related articles</span></span>

- [<span data-ttu-id="ce660-199">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="ce660-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="ce660-200">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="ce660-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ce660-201">'Hello world' 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="ce660-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="ce660-202">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ce660-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="ce660-203">Microsoft 365 Defender API에 대한 다중 테넌트 파트너 액세스가 있는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ce660-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="ce660-204">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="ce660-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="ce660-205">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="ce660-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="ce660-206">Azure Key Vault를 사용하여 서버 앱의 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="ce660-206">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="ce660-207">사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여</span><span class="sxs-lookup"><span data-stu-id="ce660-207">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

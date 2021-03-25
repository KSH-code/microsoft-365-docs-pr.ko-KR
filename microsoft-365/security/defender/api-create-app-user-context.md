---
title: 사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기
description: 사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 방법을 학습합니다.
keywords: 액세스, 사용자 대신 api, 응용 프로그램, 사용자, 액세스 토큰, 토큰,
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
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076703"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="2df9f-104">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="2df9f-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2df9f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2df9f-105">**Applies to:**</span></span>

- <span data-ttu-id="2df9f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2df9f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2df9f-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2df9f-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2df9f-109">이 페이지에서는 단일 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 방식 액세스 권한을 부여하는 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="2df9f-110">정의된 사용자 없이 Microsoft 365 Defender에 프로그래밍된 액세스 권한이 필요한 경우(예: 백그라운드 앱 또는 디먼을 작성하는 경우) 사용자 없이 [Microsoft 365 Defender에](api-create-app-web.md)액세스하는 앱 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2df9f-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="2df9f-111">대규모 조직 또는 고객 그룹에게 서비스를 제공하는 경우와 같은 여러 테넌트에 대한 액세스를 제공해야 하는 경우 [Microsoft 365 Defender API에](api-partner-access.md)대한 파트너 액세스로 앱 만들기를 참조하세요. 필요한 액세스 종류가 확실하지 않은 경우 [시작을 참조합니다.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="2df9f-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="2df9f-112">Microsoft 365 Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2df9f-113">이러한 API는 워크플로를 자동화하고 Microsoft 365 Defender의 기능을 활용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="2df9f-114">이 API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2df9f-115">자세한 내용은 [OAuth 2.0 권한 부여 코드 흐름을 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="2df9f-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="2df9f-116">일반적으로 이러한 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="2df9f-117">Azure AD(Azure Active Directory) 응용 프로그램을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="2df9f-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="2df9f-118">이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-118">Get an access token using this application.</span></span>
- <span data-ttu-id="2df9f-119">토큰을 사용하여 Microsoft 365 Defender API에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2df9f-120">이 문서에서는 이러한 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-120">This article explains how to:</span></span>

- <span data-ttu-id="2df9f-121">Azure AD 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="2df9f-121">Create an Azure AD application</span></span>
- <span data-ttu-id="2df9f-122">Microsoft 365 Defender에 대한 액세스 토큰 다운로드</span><span class="sxs-lookup"><span data-stu-id="2df9f-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="2df9f-123">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2df9f-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="2df9f-124">사용자를 대신하여 Microsoft 365 Defender API에 액세스할 때 올바른 응용 프로그램 사용 권한 및 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="2df9f-125">포털에서 작업을 수행할 수 있는 권한이 있는 경우 API에서 작업을 수행할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="2df9f-126">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="2df9f-126">Create an app</span></span>

1. <span data-ttu-id="2df9f-127">전역 관리자 역할을 사용하여 [사용자로 Azure에](https://portal.azure.com) **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="2df9f-128">Azure **Active Directory**  >  **앱 등록 새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure의 이미지 및 응용 프로그램 등록 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="2df9f-130">양식에서 응용 프로그램의 이름을 선택하고 리디렉션 URI에 대해 다음 정보를 입력한 다음 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![응용 프로그램 만들기 창의 이미지](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="2df9f-132">**응용 프로그램 유형:** 공용 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2df9f-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="2df9f-133">**리디렉션 URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="2df9f-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="2df9f-134">응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 api를 >  >    >   Microsoft **Threat Protection을** 입력하고 **Microsoft Threat Protection을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="2df9f-135">이제 앱이 Microsoft 365 Defender에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="2df9f-136">*Microsoft Threat Protection은* Microsoft 365 Defender의 이전 이름으로, 원래 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="2df9f-137">표시하려면 텍스트 상자에 이름을 쓰기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 권한 선택 이미지](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="2df9f-139">사용 **권한 위임 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="2df9f-140">시나리오에 대한 관련 사용 권한(예: **Incident.Read)을** 선택한 다음 사용 권한 추가 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="2df9f-142">시나리오에 대한 관련 권한을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="2df9f-143">*모든 인시던트 읽기는* 예시일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="2df9f-144">필요한 사용 권한을 확인하려면 호출할  API의 사용 권한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2df9f-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="2df9f-145">예를 들어 고급 [쿼리를 실행하려면](api-advanced-hunting.md)'고급 쿼리 실행' 권한을 선택합니다. 장치를 [격리하려면](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)'컴퓨터 격리' 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="2df9f-146">관리자 **동의 부여를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="2df9f-147">권한을 추가할 때마다 권한을 적용하려면 **관리자** 동의 부여를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![권한 부여 이미지](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="2df9f-149">안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="2df9f-150">응용 프로그램 페이지 **개요** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-150">They're listed under **Overview** on your application page.</span></span>

   ![생성된 앱 ID의 이미지](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="2df9f-152">액세스 토큰을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-152">Get an access token</span></span>

<span data-ttu-id="2df9f-153">Azure Active Directory 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="2df9f-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="2df9f-154">PowerShell을 사용하여 액세스 토큰을 얻다</span><span class="sxs-lookup"><span data-stu-id="2df9f-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="2df9f-155">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2df9f-155">Validate the token</span></span>

1. <span data-ttu-id="2df9f-156">토큰을 복사하여 [JWT에](https://jwt.ms) 붙여넣어 디코드합니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="2df9f-157">디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="2df9f-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="2df9f-158">다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 토큰을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![토큰 유효성 검사 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="2df9f-160">토큰을 사용하여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="2df9f-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="2df9f-161">사용할 API(인시던트 또는 고급 헌팅)를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="2df9f-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="2df9f-162">자세한 내용은 지원되는 [Microsoft 365 Defender API를 참조하세요.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="2df9f-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="2df9f-163">보내고자 하는 http 요청에서 권한 부여 헤더를 로 설정하고, 권한 부여 체계인 `"Bearer" <token>` *Bearer를* 로 설정하고 유효성이 검사된 토큰이 됩니다. </span><span class="sxs-lookup"><span data-stu-id="2df9f-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="2df9f-164">토큰은 1시간 이내에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-164">The token will expire within one hour.</span></span> <span data-ttu-id="2df9f-165">이 시간 동안 동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df9f-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="2df9f-166">다음 예에서는 를 사용하여 인시던트 목록을 을(를) **요청하는 방법을 C#.**</span><span class="sxs-lookup"><span data-stu-id="2df9f-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="2df9f-167">관련 문서</span><span class="sxs-lookup"><span data-stu-id="2df9f-167">Related articles</span></span>

- [<span data-ttu-id="2df9f-168">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="2df9f-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2df9f-169">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="2df9f-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2df9f-170">'Hello world' 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="2df9f-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="2df9f-171">사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="2df9f-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="2df9f-172">Microsoft 365 Defender API에 대한 다중 테넌트 파트너 액세스가 있는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="2df9f-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="2df9f-173">API 제한 및 라이선싱에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="2df9f-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="2df9f-174">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="2df9f-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="2df9f-175">사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여</span><span class="sxs-lookup"><span data-stu-id="2df9f-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
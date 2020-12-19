---
title: Microsoft 365 Defender API를 통한 파트너 액세스
description: 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 방식의 액세스 권한을 부여하는 앱을 만드는 방법을 배워야 합니다.
keywords: 파트너, 액세스, api, 다중 테넌트, 동의, 액세스 토큰, 앱
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719443"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="a8aad-104">Microsoft 365 Defender API에 대한 파트너 액세스가 있는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a8aad-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a8aad-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a8aad-105">**Applies to:**</span></span>

- <span data-ttu-id="a8aad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8aad-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8aad-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a8aad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a8aad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a8aad-109">이 페이지에서는 여러 테넌트의 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 방식의 액세스 권한이 있는 Azure Active Directory 앱을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="a8aad-110">다중 테넌트 앱은 대규모 사용자 그룹을 제공하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="a8aad-111">단일 사용자를 대신하여 Microsoft 365 Defender에 프로그래밍 액세스해야 하는 경우 사용자 대신 [Microsoft 365 Defender API에](api-create-app-user-context.md)액세스하는 앱 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8aad-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="a8aad-112">사용자가 명시적으로 정의되지 않은 액세스가 필요한 경우(예: 백그라운드 앱 또는 디먼을 작성하는 경우) 사용자 없이 [Microsoft 365 Defender에](api-create-app-web.md)액세스하기 위한 앱 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8aad-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="a8aad-113">필요한 액세스 종류가 확실하지 않은 경우 [시작을 참조합니다.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="a8aad-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="a8aad-114">Microsoft 365 Defender는 프로그래밍 API 집합을 통해 많은 데이터 및 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="a8aad-115">이러한 API는 워크플로를 자동화하고 Microsoft 365 Defender의 기능을 활용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="a8aad-116">이 API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="a8aad-117">자세한 내용은 [OAuth 2.0 권한 부여 코드 흐름을 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="a8aad-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="a8aad-118">일반적으로 이러한 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="a8aad-119">Azure AD(Azure Active Directory) 응용 프로그램을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="a8aad-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="a8aad-120">이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-120">Get an access token using this application.</span></span>
- <span data-ttu-id="a8aad-121">토큰을 사용하여 Microsoft 365 Defender API에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="a8aad-122">이 앱은 다중 테넌트이기 때문에 [](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 사용자를 대신하여 각 테넌트의 관리자 동의도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="a8aad-123">이 문서에서는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-123">This article explains how to:</span></span>

- <span data-ttu-id="a8aad-124">다중 **테넌트** Azure AD 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="a8aad-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="a8aad-125">응용 프로그램에 대한 사용자 관리자의 승인을 얻어 필요한 Microsoft 365 Defender에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="a8aad-126">Microsoft 365 Defender에 대한 액세스 토큰 다운로드</span><span class="sxs-lookup"><span data-stu-id="a8aad-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="a8aad-127">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a8aad-127">Validate the token</span></span>

<span data-ttu-id="a8aad-128">Microsoft 365 Defender는 프로그래밍 API 집합을 통해 많은 데이터 및 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="a8aad-129">이러한 API는 Microsoft 365 Defender 기능을 기반으로 작업 흐름을 자동화하고 혁신하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="a8aad-130">API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="a8aad-131">자세한 내용은 [OAuth 2.0 권한 부여 코드 흐름을 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="a8aad-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="a8aad-132">일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="a8aad-133">다중 **테넌트** Azure AD 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="a8aad-134">응용 프로그램에 대한 사용자 관리자가 필요한 Microsoft 365 Defender 리소스에 액세스하도록 승인(동의)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="a8aad-135">이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-135">Get an access token using this application.</span></span>
- <span data-ttu-id="a8aad-136">토큰을 사용하여 Microsoft 365 Defender API에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="a8aad-137">다중 테넌트 Azure AD 응용 프로그램을 만들고, Microsoft 365 Defender에 대한 액세스 토큰을 다운로드하고, 토큰의 유효성을 검사하는 방법을 안내하는 다음 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="a8aad-138">다중 테넌트 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a8aad-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="a8aad-139">전역 관리자 역할을 사용하여 [Azure에](https://portal.azure.com) **사용자로 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="a8aad-140">Azure **Active Directory**  >  **앱 등록 새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure의 이미지 및 응용 프로그램 등록 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="a8aad-142">등록 양식에 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-142">In the registration form:</span></span>

   - <span data-ttu-id="a8aad-143">응용 프로그램의 이름을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8aad-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="a8aad-144">지원되는 **계정 유형에서** 모든 조직 디렉터리(모든 **Azure AD 디렉터리) - 다중텐트에서 계정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="a8aad-145">리디렉션 **URI 섹션을 작성합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="a8aad-146">웹 **형식을 선택하고** 리디렉션 URI를 **https://portal.azure.com** .로 제공</span><span class="sxs-lookup"><span data-stu-id="a8aad-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="a8aad-147">양식 작성을 완료한 후 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-147">After you're done filling out the form, select **Register**.</span></span>

   ![응용 프로그램 등록 양식의 이미지](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="a8aad-149">응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 API를 선택하고 > Microsoft Threat Protection을 입력한 다음  >    >   Microsoft **Threat Protection을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="a8aad-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="a8aad-150">이제 앱이 Microsoft 365 Defender에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="a8aad-151">*Microsoft Threat Protection은* Microsoft 365 Defender의 이전 이름으로, 원래 목록에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="a8aad-152">표시하려면 텍스트 상자에 해당 이름을 쓰기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 권한 선택 이미지](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="a8aad-154">응용 **프로그램 사용 권한을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-154">Select **Application permissions**.</span></span> <span data-ttu-id="a8aad-155">시나리오에 대한 관련 사용 권한(예: **Incident.Read.All)을** 선택한 다음 사용 권한 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="a8aad-157">시나리오에 대한 관련 사용 권한을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="a8aad-158">*모든 인시던트 읽기는* 예시일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="a8aad-159">필요한 사용 권한을 확인하려면 호출할 API의 **사용** 권한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8aad-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="a8aad-160">예를 들어 고급 [쿼리를 실행하려면](api-advanced-hunting.md)'고급 쿼리 실행' 권한을 선택합니다. 장치를 [격리하려면](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)'컴퓨터 격리' 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="a8aad-161">관리자 **동의 부여를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="a8aad-162">권한을 추가할 때마다 권한을 적용하려면  관리자 동의 부여를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![권한 부여 이미지](../../media/grant-consent.PNG)

7. <span data-ttu-id="a8aad-164">응용 프로그램에 비밀을 추가하려면 인증서를 선택하고 & 설명을 추가한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a8aad-165">추가를 **선택한 후** 생성된 **비밀 값 복사를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8aad-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="a8aad-166">나가면 비밀 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![앱 키 만들기 이미지](../../media/webapp-create-key2.png)

8. <span data-ttu-id="a8aad-168">안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="a8aad-169">응용 프로그램 페이지의 **개요** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-169">They're listed under **Overview** on your application page.</span></span>

   ![생성된 앱 ID의 이미지](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="a8aad-171">사용자의 테넌트에 응용 프로그램을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="a8aad-172">응용 프로그램이 사용자를 대신하여 Microsoft 365 Defender와 상호 작용하기 때문에 응용 프로그램을 사용하려는 모든 테넌트에 대해 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="a8aad-173">사용자 **테넌트의** 전역 관리자는 동의 링크를 보고 응용 프로그램을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="a8aad-174">동의 링크 형식:</span><span class="sxs-lookup"><span data-stu-id="a8aad-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="a8aad-175">숫자는 `00000000-0000-0000-0000-000000000000` 응용 프로그램 ID로 바야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="a8aad-176">동의 링크를 클릭한 후 사용자의 테넌트의 전역 관리자에게 로그인하고 응용 프로그램에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![동의 이미지](../../media/app-consent-partner.png)

   <span data-ttu-id="a8aad-178">또한 테넌트 ID를 사용자에게 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="a8aad-179">테넌트 ID는 액세스 토큰을 획득하는 데 사용되는 식별자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="a8aad-180">**완료!**</span><span class="sxs-lookup"><span data-stu-id="a8aad-180">**Done!**</span></span> <span data-ttu-id="a8aad-181">응용 프로그램을 성공적으로 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="a8aad-182">토큰 획득 및 유효성 검사는 아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8aad-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="a8aad-183">액세스 토큰을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-183">Get an access token</span></span>

<span data-ttu-id="a8aad-184">Azure AD 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="a8aad-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8aad-185">이 섹션의 예제에서는 테스트를 위해 비밀 값에 붙여 넣는 것이 까다로우지만 프로덕션에서 실행되는 응용 프로그램에 암호를 하드코드하면 안 됩니다. </span><span class="sxs-lookup"><span data-stu-id="a8aad-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="a8aad-186">제3자에서 사용자 비밀을 사용하여 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="a8aad-187">Azure Key Vault를 사용하여 앱의 비밀을 안전하게 [유지할 수 있습니다.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="a8aad-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="a8aad-188">앱을 보호하는 방법에 대한 실제 예제는 Azure Key Vault를 사용하여 서버 앱의 암호 [관리를 참조하세요.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="a8aad-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="a8aad-189">다음 예제에서는 사용자의 테넌트 ID를 사용하여 스크립트가 작동하고 있는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="a8aad-190">PowerShell을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="a8aad-190">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="a8aad-191">C를 사용하여 액세스 토큰 얻기\#</span><span class="sxs-lookup"><span data-stu-id="a8aad-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="a8aad-192">다음 코드는 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8을 사용하여 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="a8aad-193">새 콘솔 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-193">Create a new console application.</span></span>
1. <span data-ttu-id="a8aad-194">NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory를 설치합니다.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="a8aad-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="a8aad-195">다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="a8aad-196">다음 코드를 복사하여 앱에 붙여 넣습니다(세 가지 변수를 업데이트하는 것을 잊지 마세요. `tenantId` `clientId` , , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="a8aad-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="a8aad-197">Python을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="a8aad-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="a8aad-198">컬을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="a8aad-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="a8aad-199">컬은 Windows 10 버전 1803 이상에 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="a8aad-200">다른 버전의 Windows의 경우 공식 컬 웹 사이트에서 직접 도구를 [다운로드하여 설치합니다.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="a8aad-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="a8aad-201">명령 프롬프트를 열고 azure CLIENT_ID ID로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8aad-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="a8aad-202">Azure CLIENT_SECRET 비밀로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="a8aad-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="a8aad-203">앱을 TENANT_ID Microsoft 365 Defender에 액세스하려는 사용자의 Azure 테넌트 ID로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="a8aad-204">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="a8aad-205">성공적인 응답은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="a8aad-206">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a8aad-206">Validate the token</span></span>

1. <span data-ttu-id="a8aad-207">토큰을 복사하여 JSON 웹 토큰 유효성 검사 웹 사이트 [JWT에](https://jwt.ms) 붙여넣어 디코드합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="a8aad-208">디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="a8aad-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="a8aad-209">다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 토큰을 ```AdvancedHunting.Read.All``` 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![토큰 유효성 검사의 이미지](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="a8aad-211">토큰을 사용하여 Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="a8aad-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="a8aad-212">사용할 API(인시던트 또는 고급 헌팅)를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8aad-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="a8aad-213">자세한 내용은 지원되는 [Microsoft 365 Defender API를 참조하세요.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="a8aad-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="a8aad-214">보낼 http 요청에서 권한 부여 헤더를 권한 부여 체계인 Bearer로 설정하고 유효성이 검사된 토큰인 `"Bearer" <token>` 토큰을 사용합니다.  </span><span class="sxs-lookup"><span data-stu-id="a8aad-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="a8aad-215">토큰은 1시간 이내에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-215">The token will expire within one hour.</span></span> <span data-ttu-id="a8aad-216">이 시간 동안 동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="a8aad-217">다음 예에서는 C#을 사용하여 인시던트 목록을 들이는 요청을 **보내는 방법을 보여 주며,**</span><span class="sxs-lookup"><span data-stu-id="a8aad-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="a8aad-218">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a8aad-218">Related articles</span></span>

- [<span data-ttu-id="a8aad-219">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="a8aad-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a8aad-220">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="a8aad-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a8aad-221">'Hello world' 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="a8aad-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="a8aad-222">사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a8aad-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="a8aad-223">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a8aad-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="a8aad-224">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="a8aad-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a8aad-225">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="a8aad-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a8aad-226">Azure Key Vault를 사용하여 서버 앱의 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="a8aad-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="a8aad-227">사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a8aad-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

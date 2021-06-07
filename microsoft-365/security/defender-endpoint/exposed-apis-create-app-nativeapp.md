---
title: 끝점 API에 Microsoft Defender 사용
ms.reviewer: ''
description: 사용자 없이 끝점용 Microsoft Defender에 프로그래밍 Windows 프로그래밍 방식의 앱을 디자인하는 방법을 학습합니다.
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
ms.openlocfilehash: 8f23a0b269986f4caa199ad3744c563fcc6ff6b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769104"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="9fa9a-104">끝점 API에 Microsoft Defender 사용</span><span class="sxs-lookup"><span data-stu-id="9fa9a-104">Use Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9fa9a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9fa9a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9fa9a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="9fa9a-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9fa9a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9fa9a-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="9fa9a-109">이 페이지에서는 사용자를 대신하여 끝점용 Defender에 프로그래밍 방식 액세스 권한을 부여하는 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-109">This page describes how to create an application to get programmatic access to Defender for Endpoint on behalf of a user.</span></span>

<span data-ttu-id="9fa9a-110">사용자가 없는 프로그래밍식 액세스가 필요한 경우 응용 프로그램 컨텍스트를 통해 [끝점용 Microsoft Defender 액세스를 참조합니다.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-110">If you need programmatic access Microsoft Defender for Endpoint without a user, refer to [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).</span></span>

<span data-ttu-id="9fa9a-111">필요한 액세스 권한이 확실하지 않은 경우 소개 페이지를 [읽어 하세요.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-111">If you are not sure which access you need, read the [Introduction page](apis-intro.md).</span></span>

<span data-ttu-id="9fa9a-112">끝점용 Microsoft Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-112">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="9fa9a-113">이러한 API를 사용하면 작업 흐름을 자동화하고 끝점용 Microsoft Defender 기능을 기반으로 혁신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="9fa9a-114">API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="9fa9a-115">자세한 내용은 [OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="9fa9a-116">일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="9fa9a-117">AAD 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9fa9a-117">Create an AAD application</span></span>
- <span data-ttu-id="9fa9a-118">이 응용 프로그램을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="9fa9a-118">Get an access token using this application</span></span>
- <span data-ttu-id="9fa9a-119">토큰을 사용하여 Endpoint API용 Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="9fa9a-119">Use the token to access Defender for Endpoint API</span></span>

<span data-ttu-id="9fa9a-120">이 페이지에서는 AAD 응용 프로그램을 만들고, 끝점용 Microsoft Defender에 대한 액세스 토큰을 다운로드하고, 토큰의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-120">This page explains how to create an AAD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="9fa9a-121">사용자를 대신하여 Microsoft Defender for Endpoint API에 액세스할 때 올바른 응용 프로그램 권한 및 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-121">When accessing Microsoft Defender for Endpoint API on behalf of a user, you will need the correct Application permission and user permission.</span></span>
> <span data-ttu-id="9fa9a-122">끝점용 Microsoft Defender에 대한 사용자 권한에 익숙하지 않은 경우 역할 기반 액세스 제어를 사용하여 포털 액세스 [관리를 참조합니다.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-122">If you are not familiar with user permissions on Microsoft Defender for Endpoint, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="9fa9a-123">포털에서 작업을 수행할 수 있는 권한이 있는 경우 API에서 작업을 수행할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-123">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="9fa9a-124">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="9fa9a-124">Create an app</span></span>

1. <span data-ttu-id="9fa9a-125">전역 관리자 역할이 있는 사용자 계정으로 [Azure에](https://portal.azure.com) **로그온합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-125">Log on to [Azure](https://portal.azure.com) with a user account that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="9fa9a-126">앱 등록 **Azure Active Directory**  >  **새**  >  **등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![응용 Microsoft Azure 탐색 및 이미지](images/atp-azure-new-app2.png)

3. <span data-ttu-id="9fa9a-128">응용 **프로그램 등록 페이지가** 나타나면 응용 프로그램의 등록 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-128">When the **Register an application** page appears, enter your application's registration information:</span></span>

   - <span data-ttu-id="9fa9a-129">**이름** - 앱 사용자에게 표시할 의미 있는 응용 프로그램 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-129">**Name** - Enter a meaningful application name that will be displayed to users of the app.</span></span>
   - <span data-ttu-id="9fa9a-130">**지원되는 계정 유형** - 응용 프로그램에서 지원할 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-130">**Supported account types** - Select which accounts you would like your application to support.</span></span>

       | <span data-ttu-id="9fa9a-131">지원되는 계정 유형</span><span class="sxs-lookup"><span data-stu-id="9fa9a-131">Supported account types</span></span> | <span data-ttu-id="9fa9a-132">설명</span><span class="sxs-lookup"><span data-stu-id="9fa9a-132">Description</span></span> |
       |-------------------------|-------------|
       | <span data-ttu-id="9fa9a-133">**이 조직 디렉터리의 계정만**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-133">**Accounts in this organizational directory only**</span></span> | <span data-ttu-id="9fa9a-134">LOB(LOB) 응용 프로그램을 구축하는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-134">Select this option if you're building a line-of-business (LOB) application.</span></span> <span data-ttu-id="9fa9a-135">디렉터리에 응용 프로그램을 등록하지 않는 경우 이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-135">This option is not available if you're not registering the application in a directory.</span></span><br><br><span data-ttu-id="9fa9a-136">이 옵션은 Azure AD 단일 테넌트에만 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-136">This option maps to Azure AD only single-tenant.</span></span><br><br><span data-ttu-id="9fa9a-137">디렉터리 외부에서 앱을 등록하지 않는 한 이 옵션이 기본 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-137">This is the default option unless you're registering the app outside of a directory.</span></span> <span data-ttu-id="9fa9a-138">앱이 디렉터리 외부에 등록되는 경우 기본값은 Azure AD 다중 테넌트 및 개인 Microsoft 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-138">In cases where the app is registered outside of a directory, the default is Azure AD multi-tenant and personal Microsoft accounts.</span></span> |
       | <span data-ttu-id="9fa9a-139">**조직 디렉터리의 계정**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-139">**Accounts in any organizational directory**</span></span> | <span data-ttu-id="9fa9a-140">모든 비즈니스 및 교육 고객을 대상으로 지정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-140">Select this option if you would like to target all business and educational customers.</span></span><br><br><span data-ttu-id="9fa9a-141">이 옵션은 Azure AD 전용 다중 테넌트에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-141">This option maps to an Azure AD only multi-tenant.</span></span><br><br><span data-ttu-id="9fa9a-142">Azure AD 전용 단일 테넌트로 앱을 등록한 경우 Azure AD 다중 테넌트로 업데이트하고 인증 블레이드를 통해 다시 단일 테넌트로 업데이트할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-142">If you registered the app as Azure AD only single-tenant, you can update it to be Azure AD multi-tenant and back to single-tenant through the **Authentication** blade.</span></span> |
       | <span data-ttu-id="9fa9a-143">**조직 디렉터리 및 개인 Microsoft 계정의 계정**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-143">**Accounts in any organizational directory and personal Microsoft accounts**</span></span> | <span data-ttu-id="9fa9a-144">가장 광범위한 고객을 대상으로 지정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-144">Select this option to target the widest set of customers.</span></span><br><br><span data-ttu-id="9fa9a-145">이 옵션은 Azure AD 다중 테넌트 및 개인 Microsoft 계정에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-145">This option maps to Azure AD multi-tenant and personal Microsoft accounts.</span></span><br><br><span data-ttu-id="9fa9a-146">Azure AD 다중 테넌트 및 개인 Microsoft 계정으로 앱을 등록한 경우 UI에서 이 계정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-146">If you registered the app as Azure AD multi-tenant and personal Microsoft accounts, you cannot change this in the UI.</span></span> <span data-ttu-id="9fa9a-147">대신 응용 프로그램 매니페스트 편집기를 사용하여 지원되는 계정 유형을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-147">Instead, you must use the application manifest editor to change the supported account types.</span></span> |

   - <span data-ttu-id="9fa9a-148">**리디렉션 URI(선택 사항)** - 구축할 앱의 **유형,** 웹 또는 공용 클라이언트(모바일 & 데스크톱)를 선택한 다음 응용 프로그램에 대한 리디렉션 URI(또는 회신 **URL)를** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-148">**Redirect URI (optional)** - Select the type of app you're building, **Web** or **Public client (mobile & desktop)**, and then enter the redirect URI (or reply URL) for your application.</span></span>
       - <span data-ttu-id="9fa9a-149">웹 응용 프로그램의 경우 앱의 기본 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-149">For web applications, provide the base URL of your app.</span></span> <span data-ttu-id="9fa9a-150">예를 들어 로컬 컴퓨터로 실행되는 `http://localhost:31544` 웹앱의 URL일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-150">For example, `http://localhost:31544` might be the URL for a web app running on your local machine.</span></span> <span data-ttu-id="9fa9a-151">사용자는 이 URL을 사용하여 웹 클라이언트 응용 프로그램에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-151">Users would use this URL to sign in to a web client application.</span></span>
       - <span data-ttu-id="9fa9a-152">공용 클라이언트 응용 프로그램의 경우 Azure AD에서 토큰 응답을 반환하는 데 사용하는 URI를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-152">For public client applications, provide the URI used by Azure AD to return token responses.</span></span> <span data-ttu-id="9fa9a-153">응용 프로그램 관련 값(예: )을 `myapp://auth` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-153">Enter a value specific to your application, such as `myapp://auth`.</span></span>

     <span data-ttu-id="9fa9a-154">웹 응용 프로그램 또는 네이티브 응용 프로그램에 대한 특정 예제를 확인한 다음 빠른 [시작 을 참조합니다.](/azure/active-directory/develop/#quickstarts)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-154">To see specific examples for web applications or native applications, check out our [quickstarts](/azure/active-directory/develop/#quickstarts).</span></span>

     <span data-ttu-id="9fa9a-155">완료되면 등록을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-155">When finished, select **Register**.</span></span>

4. <span data-ttu-id="9fa9a-156">응용 프로그램에서 끝점용 Microsoft Defender에 액세스하여 '경고 읽기' 권한을 할당하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-156">Allow your Application to access Microsoft Defender for Endpoint and assign it 'Read alerts' permission:</span></span>

    - <span data-ttu-id="9fa9a-157">응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 API를 선택하고  >    >   **windowsDefenderATP를 > WindowsDefenderATP를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-157">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

    - <span data-ttu-id="9fa9a-158">**참고:** *WindowsDefenderATP가* 원래 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-158">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="9fa9a-159">텍스트 상자에 이름을 입력하여 표시를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-159">Start writing its name in the text box to see it appear.</span></span>

      ![사용 권한 추가](images/add-permission.png)

    - <span data-ttu-id="9fa9a-161">사용 **권한 위임 선택**  >  **Alert.Read** > 사용 권한 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-161">Choose **Delegated permissions** > **Alert.Read** > select **Add permissions**</span></span>

      ![응용 프로그램 권한](images/application-permissions-public-client.png)

    - <span data-ttu-id="9fa9a-163">**중요 참고** 사항: 관련 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-163">**Important note**: Select the relevant permissions.</span></span> <span data-ttu-id="9fa9a-164">읽기 알림은 예시일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-164">Read alerts is only an example.</span></span>

      <span data-ttu-id="9fa9a-165">예를 들어</span><span class="sxs-lookup"><span data-stu-id="9fa9a-165">For instance,</span></span>

      - <span data-ttu-id="9fa9a-166">고급 [쿼리를 실행하려면](run-advanced-query-api.md)'고급 쿼리 실행' 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-166">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
      - <span data-ttu-id="9fa9a-167">장치를 [격리하려면](isolate-machine.md)'컴퓨터 격리' 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-167">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>
      - <span data-ttu-id="9fa9a-168">필요한 사용 권한을 확인하려면  호출할 API의 사용 권한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-168">To determine which permission you need, view the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="9fa9a-169">동의 **부여를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-169">Select **Grant consent**</span></span>

      <span data-ttu-id="9fa9a-170">**참고:** 권한을 추가할 때마다 **새** 사용 권한을 적용하기 위한 동의 부여에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-170">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

      ![권한 부여 이미지](images/grant-consent.png)

6. <span data-ttu-id="9fa9a-172">응용 프로그램 ID 및 테넌트 ID를 기록해 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-172">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="9fa9a-173">응용 프로그램 페이지에서 개요로 이동하여 **다음** 정보를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-173">On your application page, go to **Overview** and copy the following information:</span></span>

   ![생성된 앱 ID의 이미지](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a><span data-ttu-id="9fa9a-175">액세스 토큰을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-175">Get an access token</span></span>

<span data-ttu-id="9fa9a-176">AAD 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-176">For more information on AAD tokens, see [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-c"></a><span data-ttu-id="9fa9a-177">C 사용 #</span><span class="sxs-lookup"><span data-stu-id="9fa9a-177">Using C#</span></span>

- <span data-ttu-id="9fa9a-178">응용 프로그램에서 아래 클래스를 복사/붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-178">Copy/Paste the below class in your application.</span></span>
- <span data-ttu-id="9fa9a-179">응용 프로그램 ID, 테넌트 ID, 사용자 이름 및 암호와 함께 **AcquireUserTokenAsync** 메서드를 사용하여 토큰을 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-179">Use **AcquireUserTokenAsync** method with your application ID, tenant ID, user name, and password to acquire a token.</span></span>

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a><span data-ttu-id="9fa9a-180">토큰 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9fa9a-180">Validate the token</span></span>

<span data-ttu-id="9fa9a-181">올바른 토큰이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-181">Verify to make sure you got a correct token:</span></span>
- <span data-ttu-id="9fa9a-182">이전 단계에서 얻은 토큰을 디코딩하기 위해 [JWT에](https://jwt.ms) 복사/붙여넣기</span><span class="sxs-lookup"><span data-stu-id="9fa9a-182">Copy/paste into [JWT](https://jwt.ms) the token you got in the previous step in order to decode it</span></span>
- <span data-ttu-id="9fa9a-183">원하는 앱 사용 권한으로 'scp' 클레임 확인</span><span class="sxs-lookup"><span data-stu-id="9fa9a-183">Validate you get a 'scp' claim with the desired app permissions</span></span>
- <span data-ttu-id="9fa9a-184">아래 스크린샷에서는 자습서에서 앱에서 획득한 디코딩된 토큰을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa9a-184">In the screenshot below you can see a decoded token acquired from the app in the tutorial:</span></span>

![토큰 유효성 검사 이미지](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="9fa9a-186">토큰을 사용하여 끝점 API용 Microsoft Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="9fa9a-186">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="9fa9a-187">사용하려는 API 선택 - [끝점 API에](exposed-apis-list.md) 지원되는 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9fa9a-187">Choose the API you want to use - [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="9fa9a-188">"Bearer {token}"으로 보내는 HTTP 요청에서 권한 부여 헤더 설정(Bearer는 권한 부여 체계)</span><span class="sxs-lookup"><span data-stu-id="9fa9a-188">Set the Authorization header in the HTTP request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="9fa9a-189">토큰의 만료 시간은 1시간입니다(동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="9fa9a-189">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="9fa9a-190">다음을 사용하여 경고 목록을 들이기 위한 요청을 **보내는 C#**</span><span class="sxs-lookup"><span data-stu-id="9fa9a-190">Example of sending a request to get a list of alerts **using C#**</span></span> 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="9fa9a-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fa9a-191">See also</span></span>
- [<span data-ttu-id="9fa9a-192">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9fa9a-192">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="9fa9a-193">응용 프로그램 컨텍스트를 통해 끝점용 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="9fa9a-193">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)

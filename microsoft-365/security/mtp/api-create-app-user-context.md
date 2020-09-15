---
title: 사용자 대신 사용 하 여 Microsoft Threat Protection Api에 액세스
description: 사용자 대신 사용 하 여 Microsoft Threat Protection Api에 액세스 하는 방법 알아보기
keywords: 사용자, api, 응용 프로그램, 사용자, 액세스 토큰, 토큰을 대신 하 여 액세스
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
ms.openlocfilehash: c3e5b758336f1a6ac57fcfcb448de93b7473591d
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650464"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a><span data-ttu-id="652e6-104">사용자 대신 Microsoft 위협 보호 Api에 액세스</span><span class="sxs-lookup"><span data-stu-id="652e6-104">Access Microsoft Threat Protection APIs on behalf of user</span></span>

<span data-ttu-id="652e6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="652e6-105">**Applies to:**</span></span>
- <span data-ttu-id="652e6-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="652e6-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="652e6-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="652e6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="652e6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="652e6-109">이 페이지에서는 사용자를 대신 하 여 Microsoft Threat Protection에 프로그래밍 방식으로 액세스할 수 있도록 응용 프로그램을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection on behalf of a user.</span></span>

<span data-ttu-id="652e6-110">사용자 없이 프로그래밍 방식으로 Microsoft Threat Protection에 액세스 해야 하는 경우에는 [사용자 없이 Microsoft Threat protection에 액세스 하는 앱 만들기](api-create-app-web.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="652e6-110">If you need programmatic access Microsoft Threat Protection without a user, refer to [Create an app to access Microsoft Threat Protection without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="652e6-111">필요한 액세스를 모르는 경우에는 [Microsoft Threat Protection Api 액세스](api-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="652e6-111">If you are not sure which access you need, read the [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="652e6-112">Microsoft Threat Protection은 대부분의 데이터와 작업을 다양 한 Api 집합을 통해 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="652e6-113">이러한 Api를 사용 하면 Microsoft 위협 방지 기능을 기반으로 하 여 작업 흐름과 로깅을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="652e6-114">API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="652e6-115">자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="652e6-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="652e6-116">일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="652e6-117">AAD 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="652e6-117">Create an AAD application</span></span>
- <span data-ttu-id="652e6-118">이 응용 프로그램을 사용 하 여 액세스 토큰 가져오기</span><span class="sxs-lookup"><span data-stu-id="652e6-118">Get an access token using this application</span></span>
- <span data-ttu-id="652e6-119">토큰을 사용 하 여 Microsoft Threat Protection API 액세스</span><span class="sxs-lookup"><span data-stu-id="652e6-119">Use the token to access Microsoft Threat Protection API</span></span>

<span data-ttu-id="652e6-120">이 페이지에서는 AAD 응용 프로그램을 만들고, Microsoft Threat Protection에 대 한 액세스 토큰을 가져오고, 토큰의 유효성을 검사 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-120">This page explains how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="652e6-121">사용자를 대신 하 여 Microsoft Threat Protection API에 액세스 하는 경우 올바른 응용 프로그램 권한 및 사용자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-121">When accessing Microsoft Threat Protection API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="652e6-122">포털에서 작업을 수행할 수 있는 권한이 있는 경우 API에서 해당 작업을 수행할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="652e6-123">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="652e6-123">Create an app</span></span>

1. <span data-ttu-id="652e6-124">**전역 관리자** 역할이 있는 사용자를 사용 하 여 [Azure](https://portal.azure.com) 에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="652e6-125">**Azure Active Directory**  >  **앱 등록**  >  **새 등록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 이미지 및 응용 프로그램 등록에 대 한 탐색](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="652e6-127">등록에서 다음 정보를 입력 하 고 **등록**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![응용 프로그램 만들기 창의 이미지](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="652e6-129">**이름:** 응용 프로그램 이름</span><span class="sxs-lookup"><span data-stu-id="652e6-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="652e6-130">**응용 프로그램 유형:** 공용 클라이언트</span><span class="sxs-lookup"><span data-stu-id="652e6-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="652e6-131">**리디렉션 URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="652e6-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="652e6-132">앱이 Microsoft threat protection에 액세스 하 고 사용 권한을 할당할 수 있도록 하려면 응용 프로그램 페이지에서 **api 사용**권한 api를 선택  >  **Add permission**  >  합니다.**내 조직에서 사용 하는** >에는 **microsoft threat protection**을 입력 한 다음 **microsoft**threat protection을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-132">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="652e6-133">Microsoft Threat Protection이 원래 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-133">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="652e6-134">텍스트 상자에 이름을 입력 하 여 표시 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![API 액세스 및 API 선택 이미지](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="652e6-136">**위임 된 사용 권한을** 선택 하 > 시나리오에 대 한 관련 사용 권한 (예: **읽음**)을 선택 하 고 **사용 권한 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read**, and then select **Add permissions**.</span></span>

      ![API 액세스 및 API 선택 이미지](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="652e6-138">관련 사용 권한을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="652e6-139">필요한 사용 권한을 확인 하려면 통화할 API에서 **사용 권한** 섹션을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="652e6-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="652e6-140">**동의 허용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="652e6-141">사용 권한을 추가할 때마다 새 사용 권한에 대 한 **동의 부여** 를 클릭 하 여 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![권한 부여 이미지](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="652e6-143">응용 프로그램 ID 및 테 넌 트 ID를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="652e6-144">응용 프로그램 페이지에서 **개요** 로 이동 하 여 다음을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e6-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![만든 앱 id의 이미지](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="652e6-146">PowerShell을 사용 하 여 액세스 토큰 가져오기</span><span class="sxs-lookup"><span data-stu-id="652e6-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="652e6-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="652e6-147">Related topics</span></span>
- [<span data-ttu-id="652e6-148">Microsoft Threat Protection Api 액세스</span><span class="sxs-lookup"><span data-stu-id="652e6-148">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="652e6-149">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 위협 방지 액세스</span><span class="sxs-lookup"><span data-stu-id="652e6-149">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)

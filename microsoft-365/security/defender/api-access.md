---
title: MICROSOFT 365 DEFENDER API에 액세스
description: 앱 API에 액세스하는 Microsoft 365 Defender 방법 학습
keywords: 액세스, api, 응용 프로그램 컨텍스트, 사용자 컨텍스트, aad 응용 프로그램, 액세스 토큰
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
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028802"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="20c5b-104">MICROSOFT 365 DEFENDER API에 액세스</span><span class="sxs-lookup"><span data-stu-id="20c5b-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="20c5b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="20c5b-105">**Applies to:**</span></span>

- <span data-ttu-id="20c5b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20c5b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20c5b-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="20c5b-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="20c5b-109">Microsoft 365 Defender API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="20c5b-110">이러한 API를 사용하면 워크플로를 자동화하고 워크플로의 기능을 Microsoft 365 Defender 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="20c5b-111">일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="20c5b-112">응용 Azure Active Directory 만들기</span><span class="sxs-lookup"><span data-stu-id="20c5b-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="20c5b-113">이 응용 프로그램을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="20c5b-113">Get an access token using this application</span></span>
- <span data-ttu-id="20c5b-114">토큰을 사용하여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="20c5b-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="20c5b-115">API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="20c5b-116">자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="20c5b-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="20c5b-117">이러한 단계를 완료하면 특정 컨텍스트를 사용하여 Microsoft 365 Defender API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="20c5b-118">응용 프로그램 컨텍스트(권장)</span><span class="sxs-lookup"><span data-stu-id="20c5b-118">Application context (Recommended)</span></span>

<span data-ttu-id="20c5b-119">백그라운드 서비스 또는 데몬과 같이 로그인한 사용자가 없는 실행된 앱에 대해 이 컨텍스트를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="20c5b-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="20c5b-120">웹 Azure Active Directory 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="20c5b-121">응용 프로그램에 원하는 사용 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="20c5b-122">응용 프로그램에 대한 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-122">Create a key for the application.</span></span>
4. <span data-ttu-id="20c5b-123">응용 프로그램 및 해당 키를 사용하여 보안 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="20c5b-124">토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-124">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="20c5b-125">자세한 내용은 사용자 없이 앱 만들기를 **[Microsoft 365 Defender 참조하세요.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="20c5b-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="20c5b-126">사용자 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="20c5b-126">User context</span></span>

<span data-ttu-id="20c5b-127">이 컨텍스트를 사용하여 단일 사용자를 대신하여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="20c5b-128">기본 Azure Active Directory 만들기</span><span class="sxs-lookup"><span data-stu-id="20c5b-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="20c5b-129">원하는 권한을 응용 프로그램에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="20c5b-130">응용 프로그램의 사용자 자격 증명을 사용하여 보안 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="20c5b-131">토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-131">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="20c5b-132">자세한 내용은 사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 **[만들기를 참조하세요.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="20c5b-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="20c5b-133">파트너 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="20c5b-133">Partner context</span></span>

<span data-ttu-id="20c5b-134">여러 테넌트에서 많은 사용자에게 앱을 제공해야 하는 경우 이 [컨텍스트를 사용하세요.](/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="20c5b-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="20c5b-135">다중 Azure Active Directory 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="20c5b-136">원하는 권한을 응용 프로그램에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="20c5b-137">각 [테넌트에서](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 앱에 대한 관리자 동의를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="20c5b-138">고객의 테넌트 ID에 따라 사용자 자격 증명을 사용하여 보안 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="20c5b-139">토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20c5b-139">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="20c5b-140">자세한 내용은 Api에 대한 파트너 액세스로 앱 **[만들기를 Microsoft 365 Defender 참조하세요.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="20c5b-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="20c5b-141">관련 문서</span><span class="sxs-lookup"><span data-stu-id="20c5b-141">Related articles</span></span>

- [<span data-ttu-id="20c5b-142">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="20c5b-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="20c5b-143">사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여</span><span class="sxs-lookup"><span data-stu-id="20c5b-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="20c5b-144">Azure Key Vault를 사용하여 서버 앱의 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="20c5b-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="20c5b-145">앱 API에 액세스하는 'Hello world' Microsoft 365 만들기</span><span class="sxs-lookup"><span data-stu-id="20c5b-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
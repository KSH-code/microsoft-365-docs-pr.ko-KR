---
title: Microsoft 365 Defender Api 액세스
description: Microsoft 365 Defender Api에 액세스 하는 방법 알아보기
keywords: 액세스, api, 응용 프로그램 컨텍스트, 사용자 컨텍스트, aad 응용 프로그램, 액세스 토큰
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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845023"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="0196a-104">Microsoft 365 Defender Api 액세스</span><span class="sxs-lookup"><span data-stu-id="0196a-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0196a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0196a-105">**Applies to:**</span></span>
- <span data-ttu-id="0196a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0196a-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="0196a-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0196a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="0196a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="0196a-109">Microsoft 365 Defender는 프로그래밍 Api 집합을 통해 대부분의 데이터와 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0196a-110">이러한 Api를 사용 하면 Microsoft 365 Defender 기능을 기반으로 워크플로와 로깅을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="0196a-111">API 액세스를 사용 하려면 OAuth 2.0 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0196a-112">자세한 내용은 [OAuth 2.0 인증 코드 흐름](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0196a-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="0196a-113">일반적으로 Api를 사용 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="0196a-114">AAD 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="0196a-114">Create an AAD application</span></span>
- <span data-ttu-id="0196a-115">이 응용 프로그램을 사용 하 여 액세스 토큰 가져오기</span><span class="sxs-lookup"><span data-stu-id="0196a-115">Get an access token using this application</span></span>
- <span data-ttu-id="0196a-116">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="0196a-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="0196a-117">**응용 프로그램 컨텍스트** 또는 **사용자 컨텍스트** 를 사용 하 여 Microsoft 365 Defender API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="0196a-118">**응용 프로그램 컨텍스트: (권장)**</span><span class="sxs-lookup"><span data-stu-id="0196a-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="0196a-119">로그인 한 사용자 없이 실행 되는 앱에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="0196a-120">예를 들어 백그라운드 서비스 또는 daemons 실행 되는 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="0196a-121">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender API에 액세스 하기 위해 수행 해야 하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="0196a-122">AAD 웹 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="0196a-123">해당 하는 경우 applicationFor 원하는 사용 권한 (예: **AdvancedHunting** **, all** )을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="0196a-124">이 응용 프로그램에 대 한 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="0196a-125">해당 키로 응용 프로그램을 사용 하 여 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="0196a-126">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="0196a-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="0196a-127">자세한 내용은 [Get access with application context](api-create-app-web.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0196a-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="0196a-128">**사용자 컨텍스트:**</span><span class="sxs-lookup"><span data-stu-id="0196a-128">**User Context:**</span></span> <br>
    <span data-ttu-id="0196a-129">사용자를 대신 하 여 API에서 작업을 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="0196a-130">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender API에 액세스 하기 위해 수행 해야 하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="0196a-131">AAD 네이티브 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="0196a-132">원하는 사용 권한을 응용 프로그램에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="0196a-133">예를 들어 AdvancedHunting, read, **read** **를 예로** 들 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="0196a-134">사용자 자격 증명으로 응용 프로그램을 사용 하 여 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0196a-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="0196a-135">토큰을 사용 하 여 Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="0196a-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="0196a-136">자세한 내용은 [사용자 컨텍스트로 액세스 가져오기](api-create-app-user-context.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0196a-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="0196a-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0196a-137">Related topics</span></span>
- [<span data-ttu-id="0196a-138">Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="0196a-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="0196a-139">응용 프로그램 컨텍스트를 사용 하 여 Microsoft 365 Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="0196a-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="0196a-140">사용자 컨텍스트를 사용 하 여 Microsoft 365 Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="0196a-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)

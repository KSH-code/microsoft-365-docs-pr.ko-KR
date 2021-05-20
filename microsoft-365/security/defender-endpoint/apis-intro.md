---
title: 엔드포인트용 Microsoft Defender API에 액세스
ms.reviewer: ''
description: API를 사용하여 워크플로우를 자동화하고 엔드포인트 기능에 대한 Microsoft Defender를 기반으로 혁신하는 방법을 알아보십시오.
keywords: apis, api, wdatp, 오픈 API, 엔드 포인트 API용 마이크로 소프트 수비수, 마이크로 소프트 수비수 ATP, 공개 API, 지원 api, 경고, 장치, 사용자, 도메인, IP, 파일, 고급 사냥, 쿼리
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571832"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="95d4b-104">엔드포인트용 Microsoft Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="95d4b-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95d4b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95d4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="95d4b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="95d4b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95d4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95d4b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="95d4b-108">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="95d4b-108">**Applies to:**</span></span> 
- [<span data-ttu-id="95d4b-109">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="95d4b-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="95d4b-110">엔드포인트에 대한 마이크로 소프트 디펜더를 경험하고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="95d4b-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95d4b-111">무료 평가판에 가입하십시오.</span><span class="sxs-lookup"><span data-stu-id="95d4b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="95d4b-112">엔드포인트의 수비수는 프로그래밍 방식API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="95d4b-113">이러한 API를 사용하면 워크플로우를 자동화하고 엔드포인트 용 Defender 기능을 기반으로 혁신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="95d4b-114">API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="95d4b-115">자세한 내용은 [OAuth 2.0 권한 부여 코드 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95d4b-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="95d4b-116">엔드포인트의 API에 대한 수비수에 대한 간략한 개요를 보려면 이 비디오를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="95d4b-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="95d4b-117">일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="95d4b-118">[AAD 응용 프로그램](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp) 만들기</span><span class="sxs-lookup"><span data-stu-id="95d4b-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="95d4b-119">이 응용 프로그램을 사용하여 액세스 토큰 받기</span><span class="sxs-lookup"><span data-stu-id="95d4b-119">Get an access token using this application</span></span>
- <span data-ttu-id="95d4b-120">토큰을 사용하여 끝점 API에 대한 Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="95d4b-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="95d4b-121">응용 프로그램 컨텍스트 또는 사용자 **컨텍스트가** 있는 끝점 API에 대한 Defender에 액세스할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="95d4b-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="95d4b-122">**응용 프로그램 컨텍스트: (권장)**</span><span class="sxs-lookup"><span data-stu-id="95d4b-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="95d4b-123">로그인한 사용자 없이 실행되는 앱에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="95d4b-124">예를 들어 백그라운드 서비스 또는 데몬으로 실행되는 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="95d4b-125">응용 프로그램 컨텍스트를 사용하여 끝점 API에 대한 Defender에 액세스하려면 수행해야 하는 단계:</span><span class="sxs-lookup"><span data-stu-id="95d4b-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="95d4b-126">AAD 웹 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="95d4b-127">응용 프로그램에 원하는 권한을 할당합니다(예: '경고 읽기', '컴퓨터 격리').</span><span class="sxs-lookup"><span data-stu-id="95d4b-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="95d4b-128">이 응용 프로그램에 대한 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="95d4b-129">키가 있는 응용 프로그램을 사용하여 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="95d4b-130">토큰을 사용하여 엔드포인트 API에 대한 Microsoft Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="95d4b-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="95d4b-131">자세한 내용은 [응용 프로그램 컨텍스트를 통해 액세스 하기 를](exposed-apis-create-app-webapp.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95d4b-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="95d4b-132">**사용자 컨텍스트:**</span><span class="sxs-lookup"><span data-stu-id="95d4b-132">**User Context:**</span></span> <br>
    <span data-ttu-id="95d4b-133">사용자를 대신하여 API에서 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="95d4b-134">응용 프로그램 컨텍스트를 사용하여 끝점 API에 대한 Defender에 액세스하는 단계:</span><span class="sxs-lookup"><span data-stu-id="95d4b-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="95d4b-135">AAD 네이티브 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="95d4b-136">응용 프로그램에 원하는 권한을 할당합니다(예: '경고 읽기', '컴퓨터 격리' 등)</span><span class="sxs-lookup"><span data-stu-id="95d4b-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="95d4b-137">사용자 자격 증명이 있는 응용 프로그램을 사용하여 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95d4b-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="95d4b-138">토큰을 사용하여 엔드포인트 API에 대한 Microsoft Defender에 액세스</span><span class="sxs-lookup"><span data-stu-id="95d4b-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="95d4b-139">자세한 내용은 [사용자 컨텍스트를 통해 액세스 하기 를](exposed-apis-create-app-nativeapp.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95d4b-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="95d4b-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="95d4b-140">Related topics</span></span>
- [<span data-ttu-id="95d4b-141">엔드포인트 API용 마이크로소프트 수비수</span><span class="sxs-lookup"><span data-stu-id="95d4b-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="95d4b-142">응용 프로그램 컨텍스트와 끝점에 대 한 마이크로소프트 수비수 액세스</span><span class="sxs-lookup"><span data-stu-id="95d4b-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="95d4b-143">사용자 컨텍스트를 통해 엔드포인트에 대한 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="95d4b-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)

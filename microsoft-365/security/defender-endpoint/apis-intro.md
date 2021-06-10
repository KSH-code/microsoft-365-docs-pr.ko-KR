---
title: 엔드포인트용 Microsoft Defender API에 액세스
ms.reviewer: ''
description: API를 사용하여 워크플로를 자동화하고 끝점용 Microsoft Defender 기능을 기반으로 혁신하는 방법을 배우기
keywords: api, api, wdatp, open api, 끝점 api용 Microsoft Defender, microsoft defender atp, 공개 api, 지원되는 api, 경고, 장치, 사용자, 도메인, ip, 파일, 고급 헌팅, 쿼리
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9d3f4431825193d189f7ea1d73b6a99163cac428
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843701"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="6aced-104">엔드포인트용 Microsoft Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="6aced-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6aced-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6aced-105">**Applies to:**</span></span>
- [<span data-ttu-id="6aced-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6aced-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6aced-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6aced-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="6aced-108">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6aced-108">**Applies to:**</span></span> 
- [<span data-ttu-id="6aced-109">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6aced-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="6aced-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6aced-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6aced-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="6aced-112">Endpoint용 Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6aced-113">이러한 API를 통해 워크플로를 자동화하고 끝점용 Defender 기능을 기반으로 혁신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="6aced-114">API 액세스에는 OAuth2.0 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6aced-115">자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="6aced-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="6aced-116">끝점 API용 Defender에 대한 간략한 개요는 이 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="6aced-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="6aced-117">일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="6aced-118">[AAD 응용 프로그램 만들기](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="6aced-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="6aced-119">이 응용 프로그램을 사용하여 액세스 토큰 얻기</span><span class="sxs-lookup"><span data-stu-id="6aced-119">Get an access token using this application</span></span>
- <span data-ttu-id="6aced-120">토큰을 사용하여 Endpoint API용 Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="6aced-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="6aced-121">응용 프로그램 컨텍스트 또는 사용자  컨텍스트를 사용하여 Endpoint API용 Defender에 **액세스할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6aced-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="6aced-122">**응용 프로그램 컨텍스트: (권장)**</span><span class="sxs-lookup"><span data-stu-id="6aced-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="6aced-123">로그인한 사용자가 없는 실행 앱에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="6aced-124">예를 들어 백그라운드 서비스 또는 데몬으로 실행된 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="6aced-125">응용 프로그램 컨텍스트를 통해 Endpoint API용 Defender에 액세스하는 데 필요한 단계:</span><span class="sxs-lookup"><span data-stu-id="6aced-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="6aced-126">AAD 웹 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="6aced-127">원하는 사용 권한을 응용 프로그램에 할당합니다(예: '경고 읽기', '컴퓨터 격리').</span><span class="sxs-lookup"><span data-stu-id="6aced-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="6aced-128">이 응용 프로그램에 대한 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="6aced-129">응용 프로그램을 키와 함께 사용하여 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="6aced-130">토큰을 사용하여 끝점용 Microsoft Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="6aced-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="6aced-131">자세한 내용은 응용 프로그램 [컨텍스트를 통해 액세스 를 참조하세요.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="6aced-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="6aced-132">**사용자 컨텍스트:**</span><span class="sxs-lookup"><span data-stu-id="6aced-132">**User Context:**</span></span> <br>
    <span data-ttu-id="6aced-133">사용자를 대신하여 API에서 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="6aced-134">응용 프로그램 컨텍스트를 통해 Endpoint API용 Defender에 액세스하기 위해 수행해야 하는 단계:</span><span class="sxs-lookup"><span data-stu-id="6aced-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="6aced-135">AAD 네이티브 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="6aced-136">원하는 사용 권한을 응용 프로그램에 할당합니다(예: '경고 읽기', '컴퓨터 격리' 등).</span><span class="sxs-lookup"><span data-stu-id="6aced-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="6aced-137">사용자 자격 증명과 함께 응용 프로그램을 사용하여 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6aced-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="6aced-138">토큰을 사용하여 끝점용 Microsoft Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="6aced-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="6aced-139">자세한 내용은 [사용자 컨텍스트를 통해 액세스 를 참조하세요.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="6aced-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="6aced-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6aced-140">Related topics</span></span>
- [<span data-ttu-id="6aced-141">끝점 API용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6aced-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="6aced-142">응용 프로그램 컨텍스트를 통해 끝점용 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="6aced-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="6aced-143">사용자 컨텍스트를 통해 끝점용 Microsoft Defender 액세스</span><span class="sxs-lookup"><span data-stu-id="6aced-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)

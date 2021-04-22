---
title: 끝점용 Microsoft Defender의 API 탐색기
ms.reviewer: ''
description: API 탐색기를 사용하여 API 쿼리를 생성하고, 테스트하고, 사용 가능한 모든 API에 대한 요청을 전송합니다.
keywords: api, 탐색기, 보내기, 요청, get, post,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: b8d0d991e46464bae3b4d21d6218b9b3b2d2b4cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930116"
---
# <a name="api-explorer"></a><span data-ttu-id="7676a-104">API 탐색기</span><span class="sxs-lookup"><span data-stu-id="7676a-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7676a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7676a-105">**Applies to:**</span></span>
- [<span data-ttu-id="7676a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7676a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="7676a-107">끝점 API 탐색기용 Microsoft Defender는 대화형으로 끝점 API용 다양한 Defender를 탐색하는 데 도움이 되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="7676a-108">API 탐색기를 사용하면 끝점 API 끝점에 대해 사용 가능한 모든 Defender에 대한 API 쿼리를 쉽게 생성하고, 테스트하고, 요청을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="7676a-109">API 탐색기를 사용하여 작업을 수행하거나 사용자 인터페이스를 통해 아직 사용할 수 없는 데이터를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="7676a-110">이 도구는 앱 개발 중에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-110">The tool is useful during app development.</span></span> <span data-ttu-id="7676a-111">이를 통해 사용자 액세스 설정을 사용하는 API 쿼리를 수행하여 액세스 토큰 생성 필요성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="7676a-112">이 도구를 사용하여 샘플 쿼리 갤러리를 탐색하고 결과 코드 샘플을 복사하고 디버그 정보를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="7676a-113">API 탐색기를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="7676a-114">모든 메서드에 대한 요청을 실행하고 실시간으로 응답을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="7676a-115">API 샘플을 빠르게 탐색하고 지원되는 매개 변수에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="7676a-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="7676a-116">API 호출을 쉽게 만들 수 있습니다. 관리 포털 로그인 이상으로 인증할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="7676a-117">Access API 탐색기</span><span class="sxs-lookup"><span data-stu-id="7676a-117">Access API Explorer</span></span>

<span data-ttu-id="7676a-118">왼쪽 탐색 메뉴에서 Api **API &**  >  **파트너를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7676a-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="7676a-119">지원되는 API</span><span class="sxs-lookup"><span data-stu-id="7676a-119">Supported APIs</span></span>

<span data-ttu-id="7676a-120">API 탐색기는 끝점용 Defender에서 제공하는 모든 API를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="7676a-121">지원되는 API 목록은 API 설명서에서 사용할 [수 있습니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7676a-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="7676a-122">API 탐색기 시작</span><span class="sxs-lookup"><span data-stu-id="7676a-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="7676a-123">왼쪽 창에는 사용할 수 있는 샘플 요청 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="7676a-124">링크를 따라가고 쿼리 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7676a-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="7676a-125">일부 샘플에서는 URL에 매개 변수를 지정해야 할 수 있습니다(예: {machine- ID}).</span><span class="sxs-lookup"><span data-stu-id="7676a-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="7676a-126">FAQ</span><span class="sxs-lookup"><span data-stu-id="7676a-126">FAQ</span></span>

<span data-ttu-id="7676a-127">**API 탐색기를 사용하려면 API 토큰이 필요한가요?**</span><span class="sxs-lookup"><span data-stu-id="7676a-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="7676a-128">API에 액세스하기 위한 자격 증명은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="7676a-129">API 탐색기는 요청을 할 때마다 Endpoint용 Defender 관리 포털 토큰을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="7676a-130">로그인한 사용자 인증 자격 증명은 API 탐색기가 사용자를 대신하여 데이터에 액세스할 수 있는 권한이 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="7676a-131">특정 API 요청은 RBAC 권한에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="7676a-132">예를 들어 "제출 표시기"에 대한 요청은 보안 관리자 역할로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="7676a-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 

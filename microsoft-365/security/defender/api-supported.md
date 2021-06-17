---
title: 지원되는 Microsoft 365 Defender API
description: 지원되는 Microsoft 365 Defender API
keywords: Microsoft 365 Defender, API, api
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
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985087"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="b3bce-104">지원되는 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="b3bce-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b3bce-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b3bce-105">**Applies to:**</span></span>
- <span data-ttu-id="b3bce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3bce-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3bce-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b3bce-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="b3bce-109">사용 가능한 API 목록</span><span class="sxs-lookup"><span data-stu-id="b3bce-109">List of available APIs</span></span>

<span data-ttu-id="b3bce-110">문서</span><span class="sxs-lookup"><span data-stu-id="b3bce-110">Article</span></span> | <span data-ttu-id="b3bce-111">설명</span><span class="sxs-lookup"><span data-stu-id="b3bce-111">Description</span></span>
-|-
[<span data-ttu-id="b3bce-112">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="b3bce-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="b3bce-113">고급 헌팅 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="b3bce-114">인시던트 API</span><span class="sxs-lookup"><span data-stu-id="b3bce-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="b3bce-115">다른 실용적인 작업과 함께 인시던트 나열 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="b3bce-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="b3bce-116">[스트리밍 API(미리](streaming-api.md) 보기)</span><span class="sxs-lookup"><span data-stu-id="b3bce-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="b3bce-117">단일 데이터 스트림에서 발생하는 실시간 이벤트 및 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="b3bce-118">끝점 URIS</span><span class="sxs-lookup"><span data-stu-id="b3bce-118">Endpoint URIs</span></span>

<span data-ttu-id="b3bce-119">두 기본 API의 기본 URI는 https://api.security.microsoft.com 입니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="b3bce-120">더 나은 성능을 위해 지리적 위치와 더 가까운 서버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="b3bce-121">미국: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b3bce-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="b3bce-122">유럽: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b3bce-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="b3bce-123">영국: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b3bce-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="b3bce-124">토큰은 에 액세스하여 획득할 수 https://api.security.microsoft.com 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="b3bce-125">경로의 모든 `/api` API는 [OData](/odata/overview) 프로토콜(예: )을 https://api.security.microsoft.com/api/incidents 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bce-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b3bce-126">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b3bce-126">Related articles</span></span>

- [<span data-ttu-id="b3bce-127">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="b3bce-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="b3bce-128">MICROSOFT 365 DEFENDER API에 액세스</span><span class="sxs-lookup"><span data-stu-id="b3bce-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b3bce-129">스트리밍 API</span><span class="sxs-lookup"><span data-stu-id="b3bce-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="b3bce-130">API 제한 및 라이선싱에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="b3bce-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b3bce-131">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="b3bce-131">Understand error codes</span></span>](api-error-codes.md)

---
title: 지원 되는 Microsoft 365 Defender Api
description: 지원 되는 Microsoft 365 Defender Api
keywords: MTP, Api, api
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844963"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="e1151-104">지원 되는 Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="e1151-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e1151-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e1151-105">**Applies to:**</span></span>
- <span data-ttu-id="e1151-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1151-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e1151-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1151-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e1151-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e1151-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="e1151-109">끝점 Uri:</span><span class="sxs-lookup"><span data-stu-id="e1151-109">End Point URIs:</span></span>

- <span data-ttu-id="e1151-110">서비스 기본 URI는 다음과 같습니다. https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1151-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="e1151-111">성능 향상을 위해 서버를 지리적 위치에 더 가깝게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1151-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="e1151-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1151-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="e1151-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1151-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="e1151-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1151-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="e1151-115">토큰 취득 리소스는 다음과 같아야 합니다. https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1151-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="e1151-116">Path 아래의 모든 Api는 ```/api``` OData api입니다.</span><span class="sxs-lookup"><span data-stu-id="e1151-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="e1151-117">예:. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="e1151-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="e1151-118">사용 가능한 Api 목록:</span><span class="sxs-lookup"><span data-stu-id="e1151-118">List of available APIs:</span></span>

<span data-ttu-id="e1151-119">항목</span><span class="sxs-lookup"><span data-stu-id="e1151-119">Topic</span></span> | <span data-ttu-id="e1151-120">설명</span><span class="sxs-lookup"><span data-stu-id="e1151-120">Description</span></span>
:---|:---
[<span data-ttu-id="e1151-121">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="e1151-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="e1151-122">API에서 고급 구하기 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1151-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="e1151-123">인시던트 API</span><span class="sxs-lookup"><span data-stu-id="e1151-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="e1151-124">인시던트 목록, 업데이트 인시던트 등의 관련 API 호출을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1151-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>

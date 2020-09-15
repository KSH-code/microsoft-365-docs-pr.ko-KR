---
title: 지원 되는 Microsoft Threat Protection Api
description: 지원 되는 Microsoft Threat Protection Api
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650438"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="5be2b-104">지원 되는 Microsoft Threat Protection Api</span><span class="sxs-lookup"><span data-stu-id="5be2b-104">Supported Microsoft Threat Protection APIs</span></span> 
<span data-ttu-id="5be2b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5be2b-105">**Applies to:**</span></span>
- <span data-ttu-id="5be2b-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="5be2b-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="5be2b-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be2b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5be2b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5be2b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="5be2b-109">끝점 Uri:</span><span class="sxs-lookup"><span data-stu-id="5be2b-109">End Point URIs:</span></span>

- <span data-ttu-id="5be2b-110">서비스 기본 URI는 다음과 같습니다. https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5be2b-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="5be2b-111">성능 향상을 위해 서버를 지리적 위치에 더 가깝게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be2b-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="5be2b-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5be2b-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="5be2b-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5be2b-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="5be2b-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5be2b-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="5be2b-115">토큰 취득 리소스는 다음과 같아야 합니다. https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5be2b-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="5be2b-116">Path 아래의 모든 Api는 ```/api``` OData api입니다.</span><span class="sxs-lookup"><span data-stu-id="5be2b-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="5be2b-117">예:. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="5be2b-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="5be2b-118">사용 가능한 Api 목록:</span><span class="sxs-lookup"><span data-stu-id="5be2b-118">List of available APIs:</span></span>

<span data-ttu-id="5be2b-119">항목</span><span class="sxs-lookup"><span data-stu-id="5be2b-119">Topic</span></span> | <span data-ttu-id="5be2b-120">설명</span><span class="sxs-lookup"><span data-stu-id="5be2b-120">Description</span></span>
:---|:---
[<span data-ttu-id="5be2b-121">고급 구하기 API</span><span class="sxs-lookup"><span data-stu-id="5be2b-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="5be2b-122">API에서 고급 구하기 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2b-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="5be2b-123">인시던트 Api</span><span class="sxs-lookup"><span data-stu-id="5be2b-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="5be2b-124">인시던트 목록, 업데이트 인시던트 등의 관련 API 호출을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2b-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>

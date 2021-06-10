---
title: KB 컬렉션 API 사용
description: Microsoft Defender for Endpoint를 사용하여 기술 자료(KB) 및 KB 세부 정보 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167178"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="7ee2f-104">KB 컬렉션 API 사용</span><span class="sxs-lookup"><span data-stu-id="7ee2f-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ee2f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7ee2f-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ee2f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7ee2f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7ee2f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ee2f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7ee2f-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7ee2f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ee2f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="7ee2f-110">KB 및 KB 세부 정보 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="7ee2f-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="7ee2f-111">Permissions</span></span>
<span data-ttu-id="7ee2f-112">사용자에게 읽기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="7ee2f-113">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="7ee2f-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="7ee2f-114">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="7ee2f-114">Request headers</span></span>

<span data-ttu-id="7ee2f-115">머리글</span><span class="sxs-lookup"><span data-stu-id="7ee2f-115">Header</span></span> | <span data-ttu-id="7ee2f-116">값</span><span class="sxs-lookup"><span data-stu-id="7ee2f-116">Value</span></span> 
:---|:---
<span data-ttu-id="7ee2f-117">권한 부여</span><span class="sxs-lookup"><span data-stu-id="7ee2f-117">Authorization</span></span> | <span data-ttu-id="7ee2f-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-118">Bearer {token}.</span></span> <span data-ttu-id="7ee2f-119">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-119">**Required**.</span></span>
<span data-ttu-id="7ee2f-120">콘텐츠 형식</span><span class="sxs-lookup"><span data-stu-id="7ee2f-120">Content type</span></span> | <span data-ttu-id="7ee2f-121">application/json</span><span class="sxs-lookup"><span data-stu-id="7ee2f-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="7ee2f-122">요청 본문</span><span class="sxs-lookup"><span data-stu-id="7ee2f-122">Request body</span></span>
<span data-ttu-id="7ee2f-123">비어 있음</span><span class="sxs-lookup"><span data-stu-id="7ee2f-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7ee2f-124">응답</span><span class="sxs-lookup"><span data-stu-id="7ee2f-124">Response</span></span>
<span data-ttu-id="7ee2f-125">성공적이면 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="7ee2f-126">예시</span><span class="sxs-lookup"><span data-stu-id="7ee2f-126">Example</span></span>

<span data-ttu-id="7ee2f-127">**요청**</span><span class="sxs-lookup"><span data-stu-id="7ee2f-127">**Request**</span></span>

<span data-ttu-id="7ee2f-128">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="7ee2f-129">**응답**</span><span class="sxs-lookup"><span data-stu-id="7ee2f-129">**Response**</span></span>

<span data-ttu-id="7ee2f-130">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7ee2f-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```

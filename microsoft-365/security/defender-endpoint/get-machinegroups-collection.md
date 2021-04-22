---
title: RBAC 컴퓨터 그룹 컬렉션 수집 API 사용
description: KB 컬렉션 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 RBAC 장치 그룹 컬렉션을 검색하는 방법을 확인합니다.
keywords: api, 그래프 api, 지원되는 api, get, RBAC, 그룹
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932778"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="0e9b2-104">KB 컬렉션 API 사용</span><span class="sxs-lookup"><span data-stu-id="0e9b2-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e9b2-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0e9b2-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="0e9b2-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0e9b2-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e9b2-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="0e9b2-108">RBAC 장치 그룹 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="0e9b2-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="0e9b2-109">Permissions</span></span>
<span data-ttu-id="0e9b2-110">사용자에게 읽기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="0e9b2-111">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="0e9b2-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="0e9b2-112">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="0e9b2-112">Request headers</span></span>

<span data-ttu-id="0e9b2-113">머리글</span><span class="sxs-lookup"><span data-stu-id="0e9b2-113">Header</span></span> | <span data-ttu-id="0e9b2-114">값</span><span class="sxs-lookup"><span data-stu-id="0e9b2-114">Value</span></span> 
:---|:---
<span data-ttu-id="0e9b2-115">권한 부여</span><span class="sxs-lookup"><span data-stu-id="0e9b2-115">Authorization</span></span> | <span data-ttu-id="0e9b2-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-116">Bearer {token}.</span></span> <span data-ttu-id="0e9b2-117">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-117">**Required**.</span></span>
<span data-ttu-id="0e9b2-118">콘텐츠 형식</span><span class="sxs-lookup"><span data-stu-id="0e9b2-118">Content type</span></span> | <span data-ttu-id="0e9b2-119">application/json</span><span class="sxs-lookup"><span data-stu-id="0e9b2-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="0e9b2-120">요청 본문</span><span class="sxs-lookup"><span data-stu-id="0e9b2-120">Request body</span></span>
<span data-ttu-id="0e9b2-121">비어 있음</span><span class="sxs-lookup"><span data-stu-id="0e9b2-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0e9b2-122">응답</span><span class="sxs-lookup"><span data-stu-id="0e9b2-122">Response</span></span>
<span data-ttu-id="0e9b2-123">성공적이면 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="0e9b2-124">예시</span><span class="sxs-lookup"><span data-stu-id="0e9b2-124">Example</span></span>

<span data-ttu-id="0e9b2-125">**요청**</span><span class="sxs-lookup"><span data-stu-id="0e9b2-125">**Request**</span></span>

<span data-ttu-id="0e9b2-126">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="0e9b2-127">**응답**</span><span class="sxs-lookup"><span data-stu-id="0e9b2-127">**Response**</span></span>

<span data-ttu-id="0e9b2-128">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-128">Here is an example of the response.</span></span>
<span data-ttu-id="0e9b2-129">필드 ID에는 장치 그룹 **ID가** 포함되어 있으며 디바이스 정보의 **필드 rbacGroupId와** 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="0e9b2-130">**그룹화되지 않은** 필드는 그룹에 할당되지 않은 모든 장치에 대해 하나의 그룹에만 true입니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="0e9b2-131">이 그룹은 평소와 같이 이름이 "UnassignedGroup"입니다.</span><span class="sxs-lookup"><span data-stu-id="0e9b2-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
